---
title: Android-apparaten inschrijven in Intune
titlesuffix: Microsoft Intune
description: Meer informatie over het inschrijven van Android-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d74f59f1df0a4a4e1285b58d7ac5b3677d3c5e48
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als Intune-beheerder kunt u Android-apparaten beheren, waaronder Samsung Knox Standard-apparaten. U kunt ook het werkprofiel [Android for Work-apparaten](#enable-enrollment-of-android-for-work-devices) beheren.

Apparaten waarop Samsung Knox Standard wordt uitgevoerd, bieden ondersteuning voor beheer van meerdere gebruikers in Intune. Eindgebruikers kunnen hun Azure AD-referenties gebruiken om zich aan en af te melden bij het apparaat. Het apparaat wordt centraal beheerd, ongeacht of het in gebruik is of niet. Wanneer gebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

## <a name="prerequisite"></a>Vereiste

U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](mdm-authority-set.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.

## <a name="set-up-android-enrollment"></a>Android-inschrijving instellen

Standaard staat Intune de registratie van Android- en Samsung Knox Standard-apparaten toe.

Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md) als u de inschrijving wilt blokkeren van Android-apparaten of alleen Android-apparaten die het eigendom van de gebruiker zijn.

Als u apparaatbeheer wilt inschakelen, moeten uw gebruikers hun apparaat inschrijven door de app Intune-bedrijfsportal te downloaden (beschikbaar via Google Play) en vervolgens de app te openen en de prompts te volgen. Zodra Android-apparaten worden beheerd, kunt u [nalevingsbeleid toewijzen](compliance-policy-create-android.md), [apps beheren](app-management.md) en meer.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Registratie van Android for Work-apparaten inschakelen

Als u het werkprofiel op apparaten met [ondersteuning voor Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) wilt beheren, moet u een Android for Work-binding toevoegen aan Intune. Als u apparaten wilt registreren in Android for Work, maar die apparaten zijn al geregistreerd als gewone Android-apparaten, moet u de inschrijving van de apparaten ongedaan maken en ze vervolgens opnieuw inschrijven.

Als u Android for Work-apparaten inschrijft met een [Device Enrollment Manager](device-enrollment-manager-enroll.md)-account, kunt u per account 10 apparaten inschrijven.

Zie [Gegevens die Intune naar Google stuurt](data-intune-sends-to-google.md) voor meer informatie.

## <a name="add-android-for-work-binding-for-intune"></a>Android for Work-binding toevoegen voor Intune

> [!NOTE]
> Als gevolg van interactie tussen domeinen van Google en Microsoft moet u in deze stap mogelijk uw browserinstellingen aanpassen om te kunnen voltooien.  Zorg ervoor dat 'portal.azure.com' en 'play.google.com' zich in dezelfde beveiligingszone bevinden in uw browser.

1. **Intune MDM instellen**<br>
Als u dit nog niet hebt gedaan, moet u het beheer van mobiele apparaten voorbereiden door [de instantie voor het beheer van mobiele apparaten in te stellen](mdm-authority-set.md) als **Microsoft Intune**.
2. **Android for Work-binding configureren**<br>
    
   a. Meld u aan bij [Intune in de Azure Portal](https://aka.ms/intuneportal), selecteer **Apparaatinschrijving** > **Android-inschrijving** > **Beheerd Google Play**.
   ![Android for Work-registratiescherm](./media/android-work-bind.png)

   b. Selecteer **Ik ga akkoord** om Microsoft toestemming te geven om [gebruikers- en apparaatgegevens naar Google te verzenden](data-intune-sends-to-google.md). 
   
   c. Selecteer **Google nu starten om verbinding te maken** om de Android for Work-website van Google Play te openen. De website wordt op een nieuw tabblad in de browser geopend.
  
   d. **Aanmelden bij Google**<br>
   Meld u aan op de aanmeldingspagina van Google met het Google-account dat wordt gekoppeld aan alle Android for Work-beheertaken voor deze tenant. Dit is het Google-account dat de IT-beheerders van uw bedrijf gebruiken voor het beheren en publiceren van apps in de Play for Work-console. U kunt een bestaand Google-account gebruiken of een nieuw account maken.  Het account dat u kiest moet niet worden gekoppeld aan een G-Suite-domein.

   e. **Organisatiegegevens opgeven**<br>
   Geef bij **Organization name** (Organisatienaam) de naam van uw bedrijf op. Bij **Enterprise mobility management (EMM) provider** moet **Microsoft Intune** worden weergegeven. Ga akkoord met de overeenkomst voor Android for Work en kies **Confirm** (Bevestigen). Uw aanvraag wordt verwerkt.

## <a name="specify-android-for-work-enrollment-settings"></a>Inschrijvingsinstellingen voor Android for Work opgeven
Android for Work wordt alleen ondersteund op bepaalde Android-apparaten. Zie de [vereisten voor Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22) van Google voor meer informatie. Elk apparaat dat ondersteuning biedt voor Android for Work biedt ook ondersteuning voor conventioneel Android-beheer. In Intune kunt u opgeven hoe apparaten met ondersteuning voor Android for Work moeten worden beheerd. Ga hiervoor naar [Inschrijvingsbeperkingen](enrollment-restrictions-set.md).

- **Blokkeren (standaard ingesteld)**: alle Android-apparaten, ook de apparaten met ondersteuning voor Android for Work, worden ingeschreven als conventionele Android-apparaten.
- **Toestaan**: alle apparaten met ondersteuning voor Android for Work worden ingeschreven als Android for Work-apparaten. Alle Android-apparaten die geen ondersteuning bieden voor Android for Work, worden geregistreerd als conventionele Android-apparaten.

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>De bedrijfsportal-app in de beheerde Google Play Store goedkeuren
U moet de bedrijfsportal-app voor Android in de beheerde Google Play Store goedkeuren om ervoor te zorgen dat deze automatische app-updates ontvangt. Als u deze niet goedkeurt, wordt de bedrijfsportal uiteindelijk verouderd en worden er geen nieuwe belangrijke oplossingen voor problemen of nieuwe functies ontvangen wanneer deze door Microsoft worden uitgegeven.

Volg deze stappen voor het goedkeuren van de Intune bedrijfsportal:

1.  Ga naar de bedrijfsportal-app in de [beheerde Google Play Store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Meld u aan bij de beheerde Google Play Store met hetzelfde Google-account dat u hebt gebruikt om de binding voor Android for Work te configureren.
3.  Klik op **Goedkeuren** om een nieuw dialoogvenster te openen.
4.  Controleer de machtigingen in dit dialoogvenster en klik vervolgens op **Goedkeuren**. U moet deze machtigingen toestaan om de bedrijfsportal-app het werkprofiel op het apparaat te laten beheren.
5.  Selecteer **Goedgekeurd houden wanneer de app nieuwe machtigingen aanvraagt** en klik vervolgens op **Opslaan.**

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Uw gebruikers vertellen hoe ze hun apparaten moeten inschrijven om toegang te krijgen tot bedrijfsresources

Vertel uw gebruikers dat ze naar Google Play moeten gaan om de app Intune-bedrijfsportal te downloaden en vervolgens de app moeten openen en de prompts voor inschrijving van hun apparaat moeten volgen. De app leidt gebruikers door het inschrijvingsproces en legt uit wat gebruikers kunnen verwachten en wat IT-beheerders wel en niet kunnen zien op hun apparaten.

U kunt hen ook een link naar online inschrijvingsstappen sturen: [Uw Android-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Zie de volgende artikelen voor meer informatie over andere taken voor gebruikers:

- [Bronnen over de eindgebruikerservaring in Microsoft Intune](end-user-educate.md)
- [Uw Android-apparaat gebruiken met Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Binding van uw Android for Work-beheerdersaccount ongedaan maken

U kunt Android for Work-registratie en -beheer uitschakelen. Als u **Binding verwijderen** in de Intune-beheerconsole kiest, verwijdert u alle ingeschreven Android for Work-apparaten voor inschrijving. U verwijdert ook de relatie tussen het Android for Work-account en Intune.

### <a name="to-unbind-an-android-for-work-account"></a>Binding van een Android for Work-account ongedaan maken

1. **Android for Work-binding ongedaan maken**<br>
    Meld u als Intune-beheerder aan bij [Azure Portal](https://portal.azure.com) en kies **Alle services** > **Bewaking en beheer** > **Intune**.  Kies in het deelvenster **Intune** **Apparaatinschrijving** > **Inschrijving van Android for Work** en kies **Verbinding verbreken**.

2. **Verwijderen van Android for Work-binding bevestigen**<br>
  Kies **Ja** om de binding te verwijderen en de inschrijving van alle Android for Work-apparaten in Intune ongedaan te maken.

## <a name="end-user-experience-when-enrolling-a-samsung-knox-device"></a>Ervaring van eindgebruikers bij het inschrijven van een Samsung Knox-apparaat
Er zijn verschillende overwegingen bij het inschrijven van Samsung Knox-apparaten:
-   Zelfs als er voor geen enkel beleid een pincode is vereist, moet het apparaat over ten minste één viercijferige pincode beschikken om te kunnen worden ingeschreven. Als het apparaat niet over een pincode beschikt, wordt de gebruiker gevraagd er een te maken.
-   Er is geen gebruikersinteractie voor Workplace Join Certificates (WPJ).
-   De gebruiker krijgt een overzicht van informatie over inschrijving bij de service en de functies van de app.
-   De gebruiker krijgt een overzicht van informatie over inschrijving bij Knox en de functies van Knox.
-   Als er een versleutelingsbeleid van kracht is, moeten gebruikers een complex wachtwoord van zes tekens instellen als wachtwoordcode voor het apparaat.
-   De gebruiker wordt niet gevraagd extra certificaten te installeren die door een service voor toegang tot bedrijfsrecoures worden gepusht.
- Op sommige oudere Knox-apparaten worden gebruikers om aanvullende certificaten gevraagd die voor toegang tot bedrijfsresources worden gebruikt.
- Als de WPJ niet kan worden geïnstalleerd op een Samsung Mini-apparaat, met ofwel de foutmelding **Certificaat niet gevonden** of de fout **Kan apparaat niet registreren**, dient u de nieuwste Samsung Firmware-updates te installeren.
