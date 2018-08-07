---
title: Apparaatbeperkingen voor Windows Holographic for Business in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over de configuratie van instellingen voor apparaatbeperkingen in Microsoft Intune voor Windows Holographic for Business, waaronder uitschrijving, geolocatie, wachtwoorden, apps installeren uit de App Store, cookies en pop-ups in Edge, Windows Defender, zoeken, cloud en opslag, bluetooth-connectiviteit, systeemtijd en gebruiksgegevens in Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9d7f54ce0e288025a4a7f0f45bf5b10de5323021
ms.sourcegitcommit: e8e8164586508f94704a09c2e27950fe6ff184c3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/27/2018
ms.locfileid: "39321673"
---
# <a name="device-restriction-settings-for-windows-holographic-for-business-in-intune"></a>Instellingen voor apparaatbeperkingen voor Windows Holographic for Business in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

De volgende instellingen voor apparaatbeperking worden ondersteund op apparaten met Windows Holographic for Business, zoals Microsoft Hololens.

## <a name="general"></a>Algemeen

- **Registratie handmatig ongedaan maken**: hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen.
- **Cortana**: hiermee schakelt u de spraakassistent Cortana in en uit.
- **Geolocatie**: hiermee geeft u aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt.

## <a name="password"></a>Wachtwoord
-   **Wachtwoord**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**: hiermee geeft u aan dat de gebruiker een wachtwoord moet opgeven om het apparaat te ontgrendelen.

## <a name="app-store"></a>App Store

-   **Apps uit Store automatisch bijwerken**: apps die zijn geïnstalleerd vanuit Microsoft Store, kunnen automatisch worden bijgewerkt.
-   **Installatie van vertrouwde app**: voor apps die zijn ondertekend met een vertrouwd certificaat is sideloaden mogelijk.
-   **Ontgrendeling voor ontwikkelaars**: de eindgebruiker mag instellingen voor Windows-ontwikkelaars wijzigen, zoals het toestaan van sideloaden van apps.

## <a name="edge-browser"></a>Microsoft Edge-browser

-   **Cookies**: hiermee kunnen internetcookies in de browser op het apparaat worden opgeslagen.
-   **Pop-ups**: hiermee kunt u pop-upvensters in de browser blokkeren (alleen van toepassing op Windows 10-desktop).
-   **Zoeksuggesties**: hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt.
-   **Wachtwoordbeheer**: hiermee schakelt u de functie Wachtwoordbeheer van Microsoft Edge in of uit.
- **Do Not Track-headers verzenden**: hiermee configureert u de Microsoft Edge-browser zodanig, dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen voor Microsoft Edge**: schakel Edge SmartScreen in voor toegang tot site- en bestanddownloads.

## <a name="search"></a>Zoeken
- **Zoeklocatie**: geef op of een zoekactie locatiegegevens mag gebruiken. informatie

## <a name="cloud-and-storage"></a>Cloud en opslag
-   **Microsoft-account**: hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit

-   **Bluetooth**: hiermee bepaalt u of de gebruiker Bluetooth op het apparaat kan inschakelen en configureren.
-   **Bluetooth-detectie**: hiermee geeft u aan dat het apparaat kan worden gedetecteerd door andere Bluetooth-apparaten.
-   **Aankondigingen via Bluetooth**: hiermee geeft u aan dat het apparaat aankondigingen via Bluetooth kan ontvangen.

## <a name="control-panel-and-settings"></a>Configuratiescherm en instellingen

- **Systeemtijd wijzigen**: hiermee voorkomt u dat de eindgebruiker de datum en tijd van het apparaat wijzigt.

## <a name="kiosk---obsolete"></a>Kiosk - Verouderd

Deze instellingen zijn alleen-lezen en kunnen niet worden gewijzigd. Zie [Kioskinstellingen](kiosk-settings.md#windows-holographic-for-business) voor het configureren van de kioskmodus.

Op een kioskapparaat wordt doorgaans een specifieke app uitgevoerd. Gebruikers hebben geen toegang tot functies op het apparaat buiten de kiosk-app.

- **Kioskmodus**: hiermee identificeert u het type kioskmodus dat wordt ondersteund door het beleid. Opties zijn onder andere:

  - **Niet geconfigureerd** (standaard): door het beleid wordt geen kioskmodus ingeschakeld. 
  - **Kiosk voor één enkele app**: volgens het profiel kan het apparaat slechts één enkele app uitvoeren. Wanneer de gebruiker zich aanmeldt, wordt een specifieke app gestart. Deze modus voorkomt ook dat de gebruiker nieuwe apps kan openen of de actieve app kan wijzigen.
  - **Kiosk voor meerdere apps**: volgens het profiel kan het apparaat meerdere apps uitvoeren. Alleen de apps die u toevoegt, zijn beschikbaar voor de gebruiker. Het voordeel van een kiosk voor meerdere apps, of apparaat voor een vast doel, is dat het een eenvoudige ervaring biedt voor gebruikers door alleen toegang te geven tot apps die ze nodig hebben. En apps die ze niet nodig hebben, uit hun weergave verwijderen. 
  
    Wanneer u apps toevoegt voor een kioskervaring met meerdere apps, kunt u ook een opmaakbestand voor het startmenu toevoegen. [Opmaakbestand voor startmenu](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) bevat voorbeeld-XML die kan worden gebruikt in Intune. 

#### <a name="single-app-kiosks"></a>Kiosken voor één enkele app
Voer de volgende instellingen in:

- **Gebruikersaccount**: voer het lokale (op het apparaat) gebruikersaccount of de aanmelding in van het Azure AD-account dat is gekoppeld aan de kiosk-app. Voor accounts die zijn gekoppeld aan Azure AD-domeinen geeft u het account op in de indeling `domain\username@tenant.org`. 

    Voor kiosken in openbare omgevingen waarvoor automatische aanmelding is ingeschakeld, moet een gebruikerstype met minimale bevoegdheden (zoals het lokale standaardgebruikersaccount) worden gebruikt. Voor de configuratie van een Azure Active Directory-account voor de kioskmodus gebruikt u de indeling `AzureAD\user@contoso.com`.

- **Model-id van toepassingsgebruiker (AUMID)**: voer de AUMID van de kiosk-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) voor meer informatie.

## <a name="reporting-and-telemetry"></a>Rapportage en telemetrie

- **Gebruiksgegevens delen**: selecteer het niveau voor het verzenden van diagnostische gegevens.
