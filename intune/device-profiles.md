---
title: Apparaatprofielen in Microsoft Intune - Azure | Microsoft Docs
description: Overzicht van de verschillende Microsoft Intune-apparaatprofielen, waaronder functies, beperkingen, e-mail, Wi-Fi, VPN, onderwijs, certificaten, Windows 10-upgrade, BitLocker en Windows Defender, Windows Information Protection en aangepaste configuratie-instellingen voor apparaten in de Azure-portal. Gebruik deze profielen om gegevens en apparaten in uw bedrijf te beheren en beveiligen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 07/25/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8bb03becae1f28a3f5490a53576d5183c0b3ffaa
ms.sourcegitcommit: 0d08daa162212e6cdd8a6ee3ad7ed42c6e6824e4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2018
ms.locfileid: "39335823"
---
# <a name="what-are-microsoft-intune-device-profiles"></a>Wat zijn Microsoft Intune-apparaatprofielen?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Microsoft Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt inschakelen of uitschakelen. Deze instellingen en functies worden beheerd met behulp van profielen. Enkele profielvoorbeelden zijn: 

- Een Wi-Fiprofiel dat verschillende apparaten toegang geeft tot uw zakelijke wifinetwerk
- Een VPN-profiel dat verschillende apparaten toegang geeft tot uw VPN-server in uw bedrijfsnetwerk

Dit artikel bevat een overzicht van de verschillende profielen die u kunt maken voor uw apparaten. Gebruik deze profielen om bepaalde functies op de apparaten toe te staan of niet toe te staan.

## <a name="before-you-begin"></a>Voordat u begint
Als u de beschikbare functies wilt zien, opent u de [Azure Portal](https://portal.azure.com) en opent u uw Intune-resource. 

**Apparaatconfiguratie** omvat de volgende opties:

- **Overzicht**: geeft de status van de profielen weer en biedt aanvullende details over de profielen die u hebt toegewezen aan gebruikers en apparaten
- **Beheren**: apparaatprofielen maken en aangepaste [PowerShell-scripts](intune-management-extension.md) uploaden om uit te voeren binnen het profiel
- **Bewaken**: de status van een profiel controleren op slagen of falen en ook logboeken op uw profielen bekijken
- **Configureren**: een certificeringsinstantie (SCEP of PFX) toevoegen of Telecom-onkostenbeheer aan het profiel toevoegen

## <a name="create-the-profile"></a>Het profiel maken

[Apparaatprofielen maken](device-profile-create.md) biedt stapsgewijze instructies om een profiel te maken. 

## <a name="device-features---ios-and-macos"></a>Apparaatfuncties - iOS en macOS

Met [Apparaatfuncties](device-features-configure.md) kunt u functies op iOS- en macOS-apparaten beheren, zoals AirPrint, meldingen en configuraties voor gedeelde apparaten.

Deze functie ondersteunt:
- iOS 
- macOS

## <a name="device-restrictions"></a>Apparaatbeperkingen
[Apparaatbeperkingen](device-restrictions-configure.md) beheert beveiliging, hardware, delen van gegevens en meer instellingen op de apparaten. U kunt bijvoorbeeld een apparaatbeperkingsprofiel maken waarmee wordt voorkomen dat gebruikers van iOS-apparaten de camera van het apparaat gebruiken. 

Deze functie ondersteunt:

- Android
- iOS
- macOS
- Windows 10
- Windows 10 Team

## <a name="endpoint-protection"></a>Endpoint Protection
[Endpoint Protection-instellingen voor Windows 10](endpoint-protection-windows-10.md) configureert BitLocker- en Windows Defender-instellingen voor Windows 10-apparaten.

Zie het Engelstalige artikel [Configure endpoints using Mobile Device Management (MDM) tools](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection) (Eindpunten configureren met MDM-hulpprogramma's (Mobile Device Management)) als u Windows Defender Advanced Threat Protection (WDATP) wilt vrijgeven met Microsoft Intune.

Deze functie ondersteunt:
- Windows 10 en hoger

## <a name="kiosk"></a>Kiosk

Het profiel [Kiosk-instellingen](kiosk-settings.md) configureert een apparaat om één app uit te voeren of om meerdere apps uitvoeren. U kunt ook andere functies op uw kiosks aanpassen, waaronder een startmenu en een webbrowser.

Deze functie ondersteunt:
- Windows 10 en hoger

## <a name="email"></a>E-mail
Het profiel [E-mailinstellingen](email-settings-configure.md) maakt en bewaakt de e-mailinstellingen voor Exchange ActiveSync op de apparaten en wijst deze toe. E-mailprofielen zorgen voor consistentie, verminderen het aantal ondersteuningsaanvragen en bieden uw eindgebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze instellingen hoeven op te geven. 

Deze functie ondersteunt: 

- Android
- iOS
- Windows Phone 8.1
- Windows 10

## <a name="vpn"></a>VPN
[VPN-instellingen](vpn-settings-configure.md) wijst VPN-profielen toe aan gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk kunnen maken. 

Met virtuele particuliere netwerken (VPN's) hebben gebruikers veilige externe toegang tot uw bedrijfsnetwerk. Apparaten gebruiken een VPN-verbindingsprofiel om een verbinding met uw VPN-server op te zetten. 

Deze functie ondersteunt: 

- Android
- iOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="wi-fi"></a>Wi-Fi
[Wi-Fi-instellingen](wi-fi-settings-configure.md) wijst instellingen voor draadloze netwerken toe aan gebruikers en apparaten. Wanneer u een Wi-Fi-profiel toewijst, hebben uw gebruikers toegang tot uw zakelijke Wi-Fi zonder dat ze dit zelf hoeven te configureren. 

Deze functie ondersteunt: 

- Android
- iOS
- macOS
- Windows 8.1 (alleen importeren)

## <a name="esim-cellular---public-preview"></a>eSIM - Openbare preview

Met [mobiele eSIM-profielen](esim-device-configuration.md) kunt u mobiele data-abonnementen op uw beheerde apparaten configureren voor internet en toegang tot gegevens.  Nadat u de activeringscodes van uw mobiele operator hebt ontvangen, kunt u deze activeringscodes met Intune importeren en vervolgens toewijzen aan apparaten die geschikt zijn voor eSIM.

Deze functie ondersteunt:
- Windows 10 Fall Creators Update en hoger

## <a name="education"></a>Education
Met [Onderwijsinstellingen - Windows 10](education-settings-configure.md) kunt u opties configureren voor de [Windows-app Toets maken](https://education.microsoft.com/gettrained/win10takeatest). Wanneer u deze opties configureert, kunnen er geen andere apps op het apparaat worden uitgevoerd totdat de toets is voltooid.

[Onderwijsinstellingen - iOS](education-settings-configure-ios-shared.md) gebruikt de iOS-app Classroom om het leren te kunnen begeleiden en de apparaten van studenten in het leslokaal te kunnen beheren. U kunt iPads zo configureren dat meerdere studenten één apparaat kunnen delen.

## <a name="edition-upgrade"></a>Editie-upgrade
[Windows 10-editie-upgrades](edition-upgrade-configure-windows-10.md) voert automatisch een upgrade naar een nieuwere functie uit op apparaten waarop een bepaalde versie van Windows 10 wordt uitgevoerd.

Deze functie ondersteunt: 
- Windows 10 en hoger

## <a name="update-policies"></a>Updatebeleid
In [Updatebeleid voor iOS](software-updates-ios.md) ziet u hoe u iOS-beleid maakt en toewijst om software-updates te installeren op uw iOS-apparaten. U kunt ook de status van de installatie bekijken.

Deze functie ondersteunt:
- iOS

## <a name="certificates"></a>Certificaten
Met [Certificaten](certificates-configure.md) kunt u vertrouwde, SCEP- en PKCS-certificaten configureren die kunnen worden toegewezen aan apparaten en kunnen worden gebruikt voor het verifiëren van Wi-Fi-, VPN- en e-mailprofielen.

Deze functie ondersteunt: 

- Android
- iOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10

## <a name="windows-information-protection-profile"></a>Profiel Windows Information Protection
[Windows Information Protection](windows-information-protection-configure.md) helpt bij de beveiliging tegen gegevenslekken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Het helpt tevens zakelijke apps en gegevens te beschermen tegen onbedoelde gegevenslekken op apparaten die eigendom zijn van de onderneming en persoonlijke apparaten die werknemers op het werk gebruiken. Dit gebeurt zonder wijzigingen aan uw omgeving of andere apps.

Deze functie ondersteunt:
- Windows 10 en hoger

## <a name="custom-profile"></a>Aangepast profiel
Met [Aangepaste instellingen](custom-settings-configure.md) kunt u apparaatinstellingen toewijzen die niet zijn ingebouwd in Intune. Op Android-apparaten kunt u bijvoorbeeld OMA-URI-waarden invoeren. Voor iOS-apparaten kunt u een configuratiebestand importeren dat u in Apple Configurator hebt gemaakt. 

Deze functie ondersteunt:

- Android
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Beheren en problemen oplossen

[Beheer uw profielen](device-profile-monitor.md) om de status van apparaten te controleren en te bekijken welke profielen zijn toegewezen. U kunt hiermee ook conflicten oplossen: u ziet welke instellingen leiden tot een conflict en welke profielen deze instellingen bevatten. [Veelvoorkomende problemen en oplossingen](device-profile-troubleshoot.md) bevat een lijst met vragen en antwoorden over profielen. Hierin leest u onder andere wat er gebeurt wanneer een profiel wordt verwijderd of wanneer meldingen naar apparaten worden verzonden.