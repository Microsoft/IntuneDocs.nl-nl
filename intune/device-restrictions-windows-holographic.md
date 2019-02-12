---
title: Instellingen voor apparaten met Windows Holographic for Business in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over de configuratie van instellingen voor apparaatbeperkingen in Microsoft Intune voor Windows Holographic for Business, waaronder uitschrijving, geolocatie, wachtwoorden, apps installeren uit de App Store, cookies en pop-ups in Microsoft Edge, Windows Defender, zoeken, cloud en opslag, bluetooth-connectiviteit, systeemtijd en gebruiksgegevens in Azure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 477b8a0c9b4cdb575988524cea1f73615254baec
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838475"
---
# <a name="windows-holographic-for-business-device-settings-to-allow-or-restrict-features-using-intune"></a>Windows Holographic for Business-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dit artikel bevat een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op Windows Holographic for Business-apparaten, zoals Microsoft Hololens. Gebruik deze instellingen als onderdeel van de oplossing Mobile Device Management (MDM) voor het toestaan of uitschakelen van functies, het beheren van de beveiliging en nog veel meer.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Algemeen

- **Handmatige uitschrijving**: Hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen.
- **Cortana**: Hiermee schakelt u de spraakassistent Cortana in of uit.
- **Geolocatie**: Geeft aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt.

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: Hiermee stelt u dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
- **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**: Dit houdt in dat de gebruiker een wachtwoord moet opgeven om het apparaat te ontgrendelen.

## <a name="app-store"></a>App Store

- **Apps uit de Store automatisch bijwerken**: Apps die zijn geïnstalleerd vanuit Microsoft Store, kunnen automatisch worden bijgewerkt.
- **Installatie van vertrouwde app**: Voor apps die zijn ondertekend met een vertrouwd certificaat is sideloaden mogelijk.
- **Ontgrendeling voor ontwikkelaars**: De eindgebruiker mag instellingen voor Windows-ontwikkelaars wijzigen, zoals het toestaan van sideloaden van apps.

## <a name="microsoft-edge-browser"></a>Microsoft Edge-browser

- **Cookies**: Hiermee kunnen internetcookies in de browser op het apparaat worden opgeslagen.
- **Pop-ups**: Hiermee kunt u pop-upvensters in de browser blokkeren (alleen van toepassing op Windows 10-desktop).
- **Zoeksuggesties**: Hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt.
- **Wachtwoordbeheer**: Hiermee schakelt u de functie Wachtwoordbeheer van Microsoft Edge in of uit.
- **Do Not Track headers toestaan**: Hiermee configureert u de browser Microsoft Edge zodanig dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen voor Microsoft Edge**: Schakel SmartScreen voor Microsoft Edge in voor toegang tot site- en bestanddownloads.

## <a name="search"></a>Zoeken

- **Zoeklocatie**: geef op of een zoekactie locatiegegevens mag gebruiken. informatie

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Microsoft-account**: Hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit

- **Bluetooth**: Hiermee bepaalt u of de gebruiker Bluetooth op het apparaat kan inschakelen en configureren.
- **Bluetooth-detectie**: Hiermee bepaalt u of het apparaat kan worden gedetecteerd door andere Bluetooth-apparaten.
- **Bluetooth-promotie**: Hiermee bepaalt u of het apparaat reclame via Bluetooth kan ontvangen.

## <a name="control-panel-and-settings"></a>Configuratiescherm en instellingen

- **Systeemtijd wijzigen**: Hiermee voorkomt u dat de eindgebruiker de datum en tijd van het apparaat wijzigt.

## <a name="kiosk---obsolete"></a>Kiosk - Verouderd

Deze instellingen zijn alleen-lezen en kunnen niet worden gewijzigd. Zie [Kioskinstellingen](kiosk-settings-holographic.md) voor het configureren van de kioskmodus.

Op een kioskapparaat wordt doorgaans een specifieke app uitgevoerd. Gebruikers hebben geen toegang tot functies op het apparaat buiten de kiosk-app.

- **Kioskmodus**: Hiermee bepaalt u het type kioskmodus dat door het beleid wordt ondersteund. Opties zijn onder andere:

  - **Niet geconfigureerd** (standaardinstelling): Er wordt door het beleid geen kioskmodus ingeschakeld. 
  - **Kiosk voor één app**: Volgens het profiel kan het apparaat slechts één enkele app uitvoeren. Wanneer de gebruiker zich aanmeldt, wordt een specifieke app gestart. Deze modus voorkomt ook dat de gebruiker nieuwe apps kan openen of de actieve app kan wijzigen.
  - **Kiosk voor meerdere apps**: Volgens het profiel kan het apparaat meerdere apps uitvoeren. Alleen de apps die u toevoegt, zijn beschikbaar voor de gebruiker. Het voordeel van een kiosk voor meerdere apps, of apparaat voor een vast doel, is dat het een eenvoudige ervaring biedt voor gebruikers door alleen toegang te geven tot apps die ze nodig hebben. En apps die ze niet nodig hebben, uit hun weergave verwijderen. 
  
    Wanneer u apps toevoegt voor een kioskervaring met meerdere apps, kunt u ook een opmaakbestand voor het startmenu toevoegen. [Opmaakbestand voor startmenu](https://docs.microsoft.com/hololens/hololens-kiosk#start-layout-file-for-intune) bevat voorbeeld-XML die kan worden gebruikt in Intune. 

#### <a name="single-app-kiosks"></a>Kiosken voor één enkele app

Voer de volgende instellingen in:

- **Gebruikersaccount**: Voer het lokale (op het apparaat) gebruikersaccount of de aanmelding in van het Azure AD-account dat is gekoppeld aan de kiosk-app. Voor accounts die zijn gekoppeld aan Azure AD-domeinen geeft u het account op in de indeling `domain\username@tenant.org`. 

    Voor kiosken in openbare omgevingen waarvoor automatische aanmelding is ingeschakeld, moet een gebruikerstype met minimale bevoegdheden (zoals het lokale standaardgebruikersaccount) worden gebruikt. Voor de configuratie van een Azure Active Directory-account voor de kioskmodus gebruikt u de indeling `AzureAD\user@contoso.com`.

- **Model-id van toepassingsgebruiker (AUMID) van app**: Voer de AUMID van de kiosk-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) voor meer informatie.

## <a name="reporting-and-telemetry"></a>Rapportage en telemetrie

- **Gebruiksgegevens delen**: Selecteer het niveau voor het verzenden van diagnostische gegevens.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
