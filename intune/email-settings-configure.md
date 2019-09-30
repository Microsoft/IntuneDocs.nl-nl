---
title: E-mailinstellingen in Microsoft Intune configureren - Azure | Microsoft Docs
titleSuffix: ''
description: Een e-mailprofiel maken in Microsoft Intune en dit profiel implementeren op Android Enterprise-, iOS- en Windows-apparaten. Een e-mailprofiel gebruiken om algemene e-mailinstellingen te configureren, inclusief een e-mailserver en verificatiemethode om verbinding te maken met zakelijke e-mail op apparaten die u beheert.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2a534aef3cdb989376dc1c148abedfb4f4e4f78b
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71162889"
---
# <a name="add-email-settings-to-devices-using-intune"></a>E-mailinstellingen toevoegen aan apparaten met Intune

Microsoft Intune omvat verschillende e-mailinstellingen die u op apparaten in uw organisatie kunt implementeren. Een IT-beheerder maakt e-mailprofielen met specifieke instellingen om verbinding te maken met een e-mailserver, zoals Office 365 en Gmail. Eindgebruikers kunnen vervolgens verbinding maken, verifiëren en het e-mailaccount van hun organisatie op hun mobiele apparaten synchroniseren. Door een e-mailprofiel te maken en te implementeren, kunt u bevestigen dat instellingen op veel apparaten standaard zijn. Ook kan dit het aantal ondersteuningsaanvragen verminderen dat wordt ingediend door eindgebruikers die de juiste e-mailinstellingen niet weten.

U kunt e-mailprofielen gebruiken om de ingebouwde e-mailinstellingen te configureren voor de volgende apparaten:

- Android Samsung Knox Standard 4.0 en hoger
- Android Enterprise
- iOS 8.0 en hoger
- Windows Phone 8.1 en hoger
- Windows 10 (Desktop) en Windows 10 Mobile

In dit artikel wordt uitgelegd hoe u een e-mailprofiel maakt in Microsoft Intune. Het bevat ook koppelingen naar de verschillende platforms voor meer specifieke instellingen.

## <a name="create-a-device-profile"></a>Een apparaatprofiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het beleid. Geef uw beleid een naam zodat u het later eenvoudig kunt identificeren. Een goede beleidsnaam is bijvoorbeeld **E-mailinstellingen voor alle Windows-apparaten**.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies het platform van uw apparaten. Uw opties zijn:

        - **Android** (alleen Samsung Android Knox Standard)
        - **Android Enterprise**
        - **iOS/iPadOS**
        - **Windows Phone 8.1**
        - **Windows 10 en hoger**

    - **Profieltype**: Selecteer **E-mail**.

4. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Kies uw platform voor gedetailleerde instellingen:

    - [Instellingen voor Android Samsung Knox Standard](email-settings-android.md)
    - [Instellingen voor Android Enterprise](email-settings-android-enterprise.md)
    - [Instellingen voor iOS/iPadOS](email-settings-ios.md)
    - [Windows Phone 8.1-instellingen](email-settings-windows-phone-8-1.md)
    - [Windows 10-instellingen](email-settings-windows-10.md)

5. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Nadat u uw instellingen hebt ingevoerd en het profiel maakt, wordt uw profiel weergegeven in de lijst met profielen. Vervolgens [wijst u dit profiel toe aan enkele groepen](device-profile-assign.md).

## <a name="remove-an-email-profile"></a>Een e-mailprofiel verwijderen

E-mailprofielen worden toegewezen aan apparaatgroepen, niet aan gebruikersgroepen. Er zijn verschillende manieren om een e-mailprofiel van een apparaat te verwijderen, zelfs als het apparaat maar één e-mailprofiel bevat:

- **Optie 1**: open het e-mailprofiel (**Apparaatconfiguratie** > **Profielen**) en kies **Toewijzingen**. Op het tabblad **Opnemen** worden de groepen weergegeven waaraan het profiel is toegewezen. Klik met de rechtermuisknop op de groep > **Verwijderen**. Klik vervolgens op **Opslaan** om uw wijzigingen op te slaan.

- **Optie 2**: [het apparaat wissen of buiten gebruik stellen](devices-wipe.md). U kunt met deze handelingen een aantal of alle gegevens en instellingen verwijderen.

## <a name="secure-email-access"></a>Toegang tot e-mail beveiligen

U kunt e-mailprofielen beveiligen met behulp van de volgende opties:

- **Certificaten**: wanneer u het e-mailprofiel maakt, kiest u een certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit certificaat wordt het identiteitscertificaat genoemd. Het wordt geverifieerd aan de hand van een vertrouwd-certificaatprofiel of een basiscertificaat om te bepalen of een apparaat van de gebruiker verbinding mag maken. Het vertrouwde certificaat wordt toegewezen aan de computer die de e-mailverbinding verifieert. Dit is meestal de systeemeigen e-mailserver.

  Zie [How to configure certificates with Intune](certificates-configure.md) (Certificaten configureren met Intune) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.

- **Gebruikersnaam en wachtwoord**: de gebruiker wordt geverifieerd op de systeemeigen e-mailserver door de gebruikersnaam en het wachtwoord in te voeren. Het wachtwoord is niet aanwezig in het e-mailprofiel. De gebruiker voert dus het wachtwoord in wanneer verbinding wordt gemaakt met de e-mail.

## <a name="how-intune-handles-existing-email-accounts"></a>Hoe Intune omgaat met bestaande e-mailaccounts

Als de gebruiker al een e-mailaccount heeft geconfigureerd, is wordt het e-mailprofiel, afhankelijk van het platform, anders toegewezen.

- **iOS**: Een bestaand, dubbel e-mailprofiel wordt gedetecteerd op basis van de hostnaam en het e-mailadres. De toewijzing van een Intune-profiel wordt geblokkeerd op basis van het dubbele e-mailprofiel. In dit geval deelt de bedrijfsportal-app de gebruiker mee dat deze niet voldoet aan de eisen en wordt de eindgebruiker gevraagd het geconfigureerde profiel handmatig te verwijderen. Als u dit scenario wilt voorkomen, vertelt u uw eindgebruikers dat ze het apparaat eerst moeten inschrijven *voordat* ze een e-mailprofiel installeren, zodat Intune het profiel kan instellen.

- **Windows:** Een bestaand, dubbel e-mailprofiel wordt gedetecteerd op basis van de hostnaam en het e-mailadres. Intune overschrijft het bestaande e-mailprofiel dat is gemaakt door de eindgebruiker.

- **Android Samsung Knox - Standard**: Een bestaand, dubbel e-mailprofiel wordt gedetecteerd op basis van het e-mailadres. Het bestaande e-mailprofiel wordt overschreven door het Intune-profiel. Android gebruikt geen hostnaam om het profiel te identificeren. Maak niet meerdere e-mailprofielen met hetzelfde e-mailadres op verschillende hosts. De profielen overschrijven elkaar.

- **Android-werkprofielen**: Intune bevat twee Android-profielen voor zakelijke e-mail, een voor de app van Gmail en een voor de app van Nine Work. Deze apps zijn beschikbaar in de Google Play Store en worden geïnstalleerd in het werkprofiel van het apparaat. Door deze apps worden geen dubbele profielen gemaakt. Beide apps ondersteunen verbindingen met Exchange. Voor het gebruik van connectiviteit voor e-mail, implementeert u een van deze e-mail-apps op apparaten van uw gebruikers. Maak en implementeer vervolgens het juiste e-mailprofiel. E-mail-apps zoals Nine Work zijn mogelijk niet gratis. Raadpleeg de licentiegegevens van de app of neem contact op met het bedrijf dat de app heeft gemaakt voor meer informatie.

## <a name="changes-to-assigned-email-profiles"></a>Wijzigingen in toegewezen e-mailprofielen

Als u wijzigingen aanbrengt aan een e-mailprofiel dat u eerder had toegewezen, zien eindgebruikers mogelijk een bericht waarin ze wordt gevraagd de herconfiguratie van hun e-mailinstellingen goed te keuren.

## <a name="next-steps"></a>Volgende stappen

Als het profiel is gemaakt, doet het nog niets. [Wijs het profiel vervolgens toe aan enkele apparaten](device-profile-assign.md).
