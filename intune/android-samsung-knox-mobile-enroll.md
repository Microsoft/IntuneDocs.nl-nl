---
title: Android-apparaten automatisch registreren met behulp van de Knox Mobile Enrollment van Samsung
titlesuffix: Microsoft Intune
description: Meer informatie over de registratie van Android-apparaten met behulp van Samsung KME
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: ''
ms.date: 05/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 30df0f9e-6e9e-4d75-a722-3819e33d480d
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88cb733c688019b2fc5455a0184e968d91e77806
ms.sourcegitcommit: b0ad42fe5b5627e5555b2f9e5bb81bb44dbff078
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/09/2018
ms.locfileid: "33915808"
---
# <a name="automatically-enroll-android-devices-by-using-samsungs-knox-mobile-enrollment"></a>Android-apparaten automatisch registreren met behulp van de Knox Mobile Enrollment van Samsung

In dit onderwerp leest u hoe u Intune kunt instellen voor het registreren van Android-apparaten met behulp van Samsung KME (Knox Mobile Enrollment). Met Intune en Samsung KME kunt u een groot aantal Android-apparaten in bedrijfseigendom registreren wanneer eindgebruikers hun apparaten de eerste keer inschakelen en verbinding maken met een Wi-Fi- of mobiel netwerk. Apparaten kunnen ook met Bluetooth of NFC worden geregistreerd als de Knox-registratie-app wordt gebruikt.

Als u Intune-registratie met Samsung KME wilt inschakelen, gebruikt u de Intune- en Samsung Knox-portals in deze volgorde:

1. In de Knox-portal doet u het volgende:
    1. [Een MDM-profiel maken](#create-mdm-profile)
    2. [Apparaten toevoegen](#add-devices)
    3. [Een MDM-profiel toewijzen aan de apparaten](#assign-an-mdm-profile-to-devices)
2. In de Azure Portal [identificeert u apparaten als bedrijfseigendom](#identify-devices-as-corporate-owned).
3. In de Knox-portal [configureert u de aanmelding van eindgebruikers](#configure-how-end-users-sign-in).
4. [De apparaten distribueren](#distribute-devices).


Een lijst met apparaat-id's (serienummers en IMEI's) wordt automatisch aan de Knox-portal toegevoegd wanneer apparaten worden gekocht bij geautoriseerde resellers die deel uitmaken van het Knox Deployment Program.


## <a name="prerequisites"></a>Vereisten

Voor registratie bij Intune met KME moet u uw bedrijf eerst registreren op de Samsung Knox-portal met de volgende stappen:
1.  [Controleer of KME beschikbaar is in uw regio](https://www.samsungknox.com/en/solutions/it-solutions/knox-configure/available-countries): KME is beschikbaar in meer dan 55 landen. Controleer of uw land van implementatie wordt ondersteund.

2.  [Ondersteunde apparaten](https://www.samsungknox.com/en/knox-platform/supported-devices/2.4+): KME is beschikbaar op alle Samsung-apparaten met minimaal Knox 2.4.

3.  [Netwerkvereisten](https://docs.samsungknox.com/KME-Getting-Started/Content/firewall_exceptions.htm): controleer of de benodigde firewall- en netwerktoegangsregels zijn toegestaan in uw netwerk.

4.  [Registreren voor een Samsung-account](https://www2.samsungknox.com/en/user/register): u hebt een Samsung-account nodig om KME te registreren en in te schakelen en alle Knox Enterprise-rechten op één plaats te beheren.

5.  Registratiecontrole: wanneer uw profiel is voltooid en ingediend, controleert Samsung uw toepassing. De registratie wordt onmiddellijk goedgekeurd of krijgt de status Controle in behandeling voor verdere opvolging. Wanneer uw account is goedgekeurd, kunt u doorgaan met de overige stappen.

## <a name="create-mdm-profile"></a>MDM-profiel maken

Wanneer uw bedrijf is geregistreerd, kunt u uw MDM-profiel voor Microsoft Intune in de Knox-portal maken met behulp van de onderstaande informatie. Zie de instructies in de [installatiewizard voor Samsung Knox-profiel](https://docs.samsungknox.com/KME-Getting-Started/Content/getting-started-wizard.htm) voor stapsgewijze richtlijnen.

| MDM-profielvelden| Vereist? | Waarden |
|-------------------|-----------|-------|
|MDM Server URI (URI van MDM-server)     | Nee        |Laat dit leeg.
|Profile Name (Profielnaam)       | Ja       |Voer een profielnaam naar keuze in.
|description        | Nee        |Voer een beschrijvende tekst voor het profiel in.
|MDM Agent APK (APK van MDM-agent)      | Ja       |https://aka.ms/intune_kme
|Skip Setup wizard (Installatiewizard) overslaan  | Nee        |Kies deze optie als u de standaardvragen voor de installatie van het apparaat namens de gebruiker wilt overslaan.
|Allow End User to Cancel Enrollment (Toestaan dat eindgebruiker de registratie annuleert) | Nee | Kies deze optie als gebruikers KME mogen annuleren.
|Custom JSON (Aangepaste JSON)        | Nee        |Laat dit leeg.
| EULAs, Terms of Service & User Agreements (Gebruiksrechtovereenkomsten, servicevoorwaarden en gebruikersovereenkomsten)| Nee | Kies deze optie om Knox-gerelateerde overeenkomsten weer te geven voor acceptatie door de gebruiker.
Associate a Knox license with this profile (Een Knox-licentie koppelen aan dit profiel) | Nee | Laat deze optie uitgeschakeld. Voor registratie bij Intune met KME is geen Knox-licentie vereist.

## <a name="add-devices"></a>Apparaten toevoegen

Als u MDM-profielen aan apparaten wilt toewijzen, moeten ondersteunde Samsung Knox-apparaten aan de Knox-portal worden toegevoegd. Daarvoor kunt u een van de volgende methoden gebruiken:
- **Met door Samsung goedgekeurde reseller(s):** gebruik deze methode als u apparaten van een van de door Samsung goedgekeurde resellers hebt gekocht. Resellers kunnen apparaten automatisch voor u uploaden wanneer dit is goedgekeurd. [Raadpleeg de gebruikershandleiding van Samsung Knox Enrollment voor meer informatie over het toevoegen van resellers](https://docs.samsungknox.com/KME-Getting-Started/Content/Register_resellers.htm).

- **De Knox Deployment App (KDA) gebruiken:** gebruik deze methode als u bestaande apparaten wilt registreren met KME. Met deze methode kunt u zowel via Bluetooth als via NFC apparaten toevoegen aan de Knox-portal. [Raadpleeg de gebruikershandleiding van Samsung Knox Enrollment voor meer informatie over KDA](https://docs.samsungknox.com/KME-Getting-Started/Content/add-device-info.htm).

## <a name="assign-an-mdm-profile-to-devices"></a>Een MDM-profiel toewijzen aan apparaten
U moet een MDM-profiel aan toegevoegde apparaten toewijzen in de Knox-portal voordat ze kunnen worden geregistreerd. [Raadpleeg de gebruikershandleiding van Samsung Knox Enrollment voor meer informatie over apparaatconfiguratie](https://docs.samsungknox.com/KME-Getting-Started/Content/configure-devices.htm).

## <a name="identify-devices-as-corporate-owned"></a>Apparaten identificeren als bedrijfseigendom
U kunt apparaten die met behulp van KME zijn geregistreerd, identificeren als bedrijfseigendom. Dit moet worden gedaan voordat de apparaten worden geregistreerd. Hiermee kunt u extra beheertaken uitvoeren en aanvullende informatie verzamelen, zoals het volledige telefoonnummer en een inventaris van apps.

Volg deze stappen om apparaten te identificeren als bedrijfseigendom:

1. Exporteer de lijst met apparaten vanuit de Knox-portal als een CSV-bestand.

2. Maak het CSV-bestand op met het IMEI- of serienummer zoals [hier](https://docs.microsoft.com/en-us/intune/corporate-identifiers-add#identify-corporate-owned-devices-with-imei-or-serial-number) is uitgelegd.

3. In Azure Portal uploadt u het CSV-bestand naar **Apparaatregistratie** > **Bedrijfsapparaat-id's** > **Toevoegen**.

Nu worden geïdentificeerde apparaten die worden geregistreerd, gemarkeerd als bedrijfseigendom.

> [!NOTE]
>In Intune wordt de status Bedrijfseigendom automatisch toegewezen aan apparaten die worden geregistreerd met het [Device Enrollment Manager](https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll)-account.

## <a name="configure-how-end-users-sign-in"></a>Configureren hoe eindgebruikers zich aanmelden

Voor apparaten die in Intune worden geregistreerd met KME, kunt u als volgt configureren hoe een eindgebruiker zich aanmeldt:

- **Zonder koppeling met gebruikersnaam:** laat in de Knox-portal onder **Device details** (Apparaatdetails) de velden **User ID** (gebruikers-id) en **Password** (wachtwoord) leeg voor de toegevoegde apparaten. De gebruiker moet dan gebruikersnaam en wachtwoord invoeren tijdens de registratie bij Intune.

- **Met koppeling met naam van gebruiker:** geef in de Knox-portal onder **Device Details** (Apparaatdetails) een **gebruikers-id** op (bijvoorbeeld een gebruikersnaam voor de toegewezen gebruiker of een [Device Enrollment Manager](https://docs.microsoft.com/en-us/intune/device-enrollment-manager-enroll)-account) voor de toegevoegde apparaten. De gebruikersnaam wordt dan al ingevuld en de gebruiker hoeft alleen een wachtwoord in te voeren tijdens de registratie bij Intune.

> [!NOTE]
>
>Als een gebruikerskoppeling is gedefinieerd, kan alleen de gekoppelde gebruiker het apparaat met KME registreren. Dit geldt zelfs nadat de fabrieksinstellingen van het apparaat zijn teruggezet. Als in de Knox-portal geen gebruikerskoppeling is gedefinieerd, kan elke gebruiker met een geldige Intune-licentie het apparaat met KME registreren.
>

## <a name="distribute-devices"></a>Apparaten distribueren

Wanneer een MDM-profiel is gemaakt en toegewezen, een gebruikersnaam is gekoppeld en de apparaten in Intune als bedrijfseigendom zijn geïdentificeerd, kunt u apparaten aan gebruikers distribueren.

Nog hulp nodig? Bekijk de volledige [gebruikershandleiding van Knox Mobile Enrollment](https://docs.samsungknox.com/KME-Getting-Started/Content/get-started.htm).

## <a name="frequently-asked-questions"></a>Veelgestelde vragen
- **Google Play-account:** u hebt geen Google Play-account nodig om het apparaat te registreren bij Microsoft Intune. Maar voor toekomstige updates van de Intune-bedrijfsportal-app hebt u mogelijk wel een Google Play-account op het apparaat nodig.

- **Google-modus Apparaateigenaar:** registratie in de Google-modus Apparaateigenaar met KME wordt niet ondersteund in deze preview-versie. Dit scenario wordt momenteel onderzocht.

- **Veld 'Password' wordt genegeerd:** als het veld **Password** in **Device Details** van de Knox-portal is ingevuld, wordt het genegeerd door de Intune-bedrijfsportal-app. De eindgebruiker moet een wachtwoord invoeren op het apparaat om registratie van het apparaat te voltooien.

## <a name="getting-support"></a>Ondersteuning
Meer informatie over [ondersteuning voor Samsung KME](https://docs.samsungknox.com/KME-Getting-Started/Content/to-get-kme-support.htm).


