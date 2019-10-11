---
title: Apparaatfuncties en -instellingen gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Overzicht van de verschillende Microsoft Intune-apparaatprofielen. Krijg informatie over functies, beperkingen, e-mail, Wi-Fi, VPN, onderwijs, certificaten, Windows 10-upgrade, BitLocker en Windows Defender, Windows Information Protection, beheersjablonen en aangepaste configuratie-instellingen voor apparaten in de Azure-portal. Gebruik deze profielen om gegevens en apparaten in uw bedrijf te beheren en te beveiligen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3afdb365d0ed88a58028287cc7010bb334e9001e
ms.sourcegitcommit: fca2670142c083d7562c0a36547a6a451863e315
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2019
ms.locfileid: "72036443"
---
# <a name="apply-features-and-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Functies en instellingen toepassen op uw apparaten met apparaatprofielen in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt in- of uitschakelen. Deze instellingen en functies worden toegevoegd aan 'configuratieprofielen'. U kunt profielen voor verschillende apparaten en verschillende platforms maken, waaronder iOS, Android en Windows. Gebruik vervolgens Intune om het profiel toe te passen of toe te wijzen aan de apparaten.

Als onderdeel van uw MDM-oplossing (Mobile Device Management) kunt u deze configuratieprofielen gebruiken om verschillende taken te voltooien. Enkele profielvoorbeelden zijn:

- Gebruik op Windows 10-apparaten een profielsjabloon die ActiveX-besturingselementen blokkeert in Internet Explorer.
- Sta gebruikers van iOS- en macOS-apparaten toe om in uw organisatie AirPrint-printers te gebruiken.
- Sta wel of geen toegang toe tot bluetooth op het apparaat.
- Maak een Wi-Fi of VPN-profiel waarmee verschillende apparaten toegang hebben tot uw bedrijfsnetwerk.
- Beheer software-updates, inclusief het moment wanneer deze worden geïnstalleerd.
- Voer een Android-apparaat uit als een speciaal kioskapparaat dat één app kan uitvoeren of veel apps kan uitvoeren.

Dit artikel biedt een overzicht van de verschillende typen profielen die u kunt maken. Gebruik deze profielen om bepaalde functies op de apparaten al dan niet toe te staan.

## <a name="administrative-templates"></a>Beheersjablonen

[Beheersjablonen](administrative-templates-windows.md) bevatten honderden instellingen die u kunt configureren voor Internet Explorer, OneDrive, extern bureaublad, Word, Excel en andere Office-programma's.

Deze sjablonen bieden beheerders een vereenvoudigde weergave van instellingen die vergelijkbaar zijn met groepsbeleid, maar ze zijn voor 100% gebaseerd op de cloud.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="certificates"></a>Certificaten

Via [Certificaten](../protect/certificates-configure.md) worden vertrouwde , SCEP- en PKCS-certificaten geconfigureerd die zijn toegewezen aan apparaten. Met deze certificaten worden WiFi-, VPN- en e-mailprofielen geverifieerd.

Deze functie ondersteunt: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 en hoger

## <a name="custom-profile"></a>Aangepast profiel

Met [Aangepaste instellingen](../custom-settings-configure.md) kunnen beheerders apparaatinstellingen toewijzen die niet zijn ingebouwd in Intune. Op Android-apparaten kunt u OMA-URI-waarden invoeren. Voor iOS-apparaten kunt u een configuratiebestand importeren dat u in Apple Configurator hebt gemaakt.

Deze functie ondersteunt:

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8.1

## <a name="delivery-optimization"></a>Delivery Optimization

[Delivery optimization](../delivery-optimization-windows.md) biedt een betere ervaring voor het leveren van software-updates. Deze instellingen vervangen de instellingen **Software-Updates** > **Windows 10-updatering**.

Gebruik deze instellingen om te bepalen hoe software-updates worden gedownload naar apparaten in uw organisatie. U kunt bijvoorbeeld gebruikers krijgen hun eigen updates laten downloaden of updates binnenhalen met behulp van de cloudservices voor delivery optimization in een apparaatprofiel.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="device-features"></a>Apparaatfuncties

Met [Apparaatfuncties](../device-features-configure.md) kunt u functies op iOS- en macOS-apparaten beheren, zoals AirPrint, meldingen en berichten voor schermvergrendeling.

Deze functie ondersteunt:

- iOS/iPadOS
- macOS

## <a name="device-restrictions"></a>Apparaatbeperkingen

[Apparaatbeperkingen](device-restrictions-configure.md) beheert beveiliging, hardware, delen van gegevens en meer instellingen op de apparaten. U kunt bijvoorbeeld een apparaatbeperkingsprofiel maken waarmee wordt voorkomen dat gebruikers van iOS-apparaten de camera van het apparaat gebruiken. 

Deze functie ondersteunt:

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 10 en hoger
- Windows 10 Team

## <a name="edition-upgrade"></a>Editie-upgrade

[Windows 10-editie-upgrades](edition-upgrade-configure-windows-10.md) voert automatisch een upgrade naar een nieuwere functie uit op apparaten waarop een bepaalde versie van Windows 10 wordt uitgevoerd.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="education"></a>Education

Met [Onderwijsinstellingen - Windows 10](education-settings-configure.md) kunt u opties configureren voor de [Windows-app Toets maken](https://education.microsoft.com/gettrained/win10takeatest). Wanneer u deze opties configureert, kunnen er geen andere apps op het apparaat worden uitgevoerd totdat de toets is voltooid.

[Onderwijsinstellingen - iOS](../fundamentals/education-settings-configure-ios-shared.md) gebruikt de iOS-app Classroom om het leren te kunnen begeleiden en de apparaten van studenten in het leslokaal te kunnen beheren. U kunt iPads zo configureren dat meerdere studenten één apparaat kunnen delen.

## <a name="email"></a>E-mail

[E-mailinstellingen](email-settings-configure.md) maakt en bewaakt de e-mailinstellingen voor Exchange ActiveSync op de apparaten en wijst deze toe. E-mailprofielen helpen met consistentie, verminderen het aantal ondersteuningsaanvragen en bieden uw eindgebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze instellingen hoeven op te geven. 

Deze functie ondersteunt: 

- Android
- Android Enterprise
- iOS/iPadOS
- Windows Phone 8.1
- Windows 10 en hoger

## <a name="endpoint-protection"></a>Endpoint Protection

[Endpoint Protection-instellingen voor Windows 10](../protect/endpoint-protection-windows-10.md) configureert BitLocker- en Windows Defender-instellingen voor Windows 10-apparaten.

Zie het Engelstalige artikel [Configure endpoints using Mobile Device Management (MDM) tools](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-mdm) (Eindpunten configureren met MDM-hulpprogramma's (Mobile Device Management)) als u Microsoft Defender Advanced Threat Protection (WDATP) wilt vrijgeven met Microsoft Intune.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="esim-cellular---public-preview"></a>eSIM - Openbare preview

Met [mobiele eSIM-profielen](esim-device-configuration.md) kunnen beheerders mobiele data-abonnementen op uw beheerde apparaten configureren voor toegang tot internet en gegevens. Nadat u activeringscodes van uw mobiele operator hebt ontvangen, kunt u deze activeringscodes met Intune importeren en vervolgens toewijzen aan apparaten die geschikt zijn voor eSIM.

Deze functie ondersteunt:

- Windows 10 Fall Creators Update en hoger

## <a name="extensions"></a>Uitbreidingen

Met [Kernelextensies](kernel-extensions-overview-macos.md) kunnen beheerders functies of programma's op kernelniveau toevoegen op macOS-apparaten. Configureer deze instellingen voor het vertrouwen van alle extensies van een specifieke ontwikkelaar of partner, of sta specifieke kernelextensies toe.

Deze functie ondersteunt:

- macOS

## <a name="identity-protection"></a>Identiteitsbescherming

Met [Identiteitsbescherming](../protect/identity-protection-configure.md) beheert u de Windows Hello voor Bedrijven-ervaring op Windows 10 en Windows 10 Mobile-apparaten. Configureer deze instellingen om Windows Hello voor Bedrijven beschikbaar maken voor gebruikers en apparaten, en om de vereisten op te geven voor pincodes en gebaren voor apparaten.  

Deze functie ondersteunt:  

- Windows 10 en hoger
- Windows Holographic for Business  

## <a name="kiosk"></a>Kiosk

Het profiel [Kiosk-instellingen](kiosk-settings.md) configureert een apparaat om één app uit te voeren of om verschillende apps uit te voeren. U kunt ook andere functies op uw kiosks aanpassen, waaronder een startmenu en een webbrowser.

Deze functie ondersteunt:

- Windows 10 en hoger

Kiosk-instellingen zijn ook beschikbaar als apparaatbeperkingen voor [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) en [iOS](device-restrictions-ios.md#kiosk).

## <a name="oemconfig"></a>OEMConfig

[OEMConfig](android-oem-configuration-overview.md) is een standaard waarmee OEM's (Original Equipment Manufacturers) en EMMs (Enterprise Mobility Management) OEM-specifieke functies op een gestandaardiseerde manier kunnen bouwen en ondersteunen op Android Enterprise-apparaten. Met OEMConfig kunnen OEM's een schema maken waarin OEM-specifieke beheerfuncties worden gedefinieerd en dat insluiten in een app die wordt geüpload naar Google Play. Het schema van de app wordt ingelezen in Intune zodat Intune-beheerders de instellingen in het schema kunnen configureren.

Deze functie ondersteunt:

- Android Enterprise (OEMConfig)

## <a name="powershell-scripts"></a>PowerShell-scripts

[PowerShell-scripts op Windows 10-apparaten](../apps/intune-management-extension.md) gebruikt de Intune-beheerextensie om uw PowerShell-scripts te uploaden naar Intune en deze scripts vervolgens uit te voeren op uw apparaten. Zie ook de vereisten voor het gebruik van de extensie, hoe u deze toevoegt aan Intune, en andere belangrijke informatie.


Deze functie ondersteunt:

- Windows 10 en hoger
- Windows Holographic for Business

## <a name="shared-multi-user-device"></a>Gedeelde apparaat voor meerdere gebruikers

[Windows 10](shared-user-device-settings-windows.md) en [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) omvatten instellingen voor het beheren van apparaten met meerdere gebruikers, ook wel bekend als gedeelde apparaten of gedeelde pc's. Wanneer een gebruiker zich aanmeldt met het apparaat, kiest u of de gebruiker de opties voor slaapstand kan wijzigen of bestanden op het apparaat kan opslaan. In een ander voorbeeld kunt u, om ruimte te besparen, een profiel maken waarmee inactieve referenties van Windows HoloLens-apparaten worden verwijderd.

Via deze instellingen voor gedeelde apparaten voor meerdere gebruikers kan een beheerder bepaalde apparaatfuncties beheren en deze gedeelde apparaten met Intune beheren.

Deze functie ondersteunt:

- Windows 10 en hoger
- Windows Holographic for Business

## <a name="update-policies"></a>Updatebeleid

In [Updatebeleid voor iOS](../software-updates-ios.md) ziet u hoe u iOS-beleid maakt en toewijst om software-updates te installeren op uw iOS-apparaten. U kunt ook de status van de installatie bekijken.

Zie [Delivery optimization](../delivery-optimization-windows.md) voor updatebeleid op Windows-apparaten. 

Deze functie ondersteunt:

- iOS/iPadOS

## <a name="vpn"></a>VPN

[VPN-instellingen](vpn-settings-configure.md) wijst VPN-profielen toe aan gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk kunnen maken. 

Met virtuele particuliere netwerken (VPN's) hebben gebruikers veilige externe toegang tot uw bedrijfsnetwerk. Apparaten gebruiken een VPN-verbindingsprofiel om een verbinding met uw VPN-server op te zetten. 

Deze functie ondersteunt: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows Phone 8.1
- Windows 8.1
- Windows 10 en hoger

## <a name="wi-fi"></a>Wi-Fi

[Wi-Fi-instellingen](wi-fi-settings-configure.md) wijst instellingen voor draadloze netwerken toe aan gebruikers en apparaten. Wanneer u een Wi-Fi-profiel toewijst, hebben uw gebruikers toegang tot uw zakelijke Wi-Fi zonder dat ze dit zelf hoeven te configureren. 

Deze functie ondersteunt: 

- Android
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 (alleen importeren)
- Windows 10 en hoger

## <a name="windows-information-protection-profile"></a>Profiel Windows Information Protection

[Windows Information Protection](../protect/windows-information-protection-configure.md) helpt bij de beveiliging tegen gegevenslekken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Het helpt ook om zakelijke apps en gegevens te beschermen tegen onbedoelde gegevenslekken op apparaten die eigendom zijn van de onderneming en op persoonlijke apparaten die werknemers op het werk gebruiken. De omgeving of andere apps hoeven niet te worden gewijzigd om Windows Information Protection te gebruiken.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="zebra-mobility-extensions-mx"></a>Zebra Mobility Extensions (MX)

Met [Zebra Mobility Extensions (MX)](android-zebra-mx-overview.md) kunnen beheerders Zebra-apparaten gebruiken en beheren in Intune. In de instellingen kunt u StageNow-profielen maken, en vervolgens Intune gebruiken om deze profielen toe te wijzen aan en te implementeren op uw Zebra-apparaten. De documentatie [StageNow-logboeken en veelvoorkomende problemen](android-zebra-mx-logs-troubleshoot.md) is een handige resource voor het oplossen van problemen met profielen, en voor inzicht in potentiële problemen bij het gebruik van StageNow.

Deze functie ondersteunt:

- Android (Mobility Extensions)

## <a name="manage-and-troubleshoot"></a>Beheren en problemen oplossen

[Beheer uw profielen](../device-profile-monitor.md) om de status van apparaten te controleren en te bekijken welke profielen zijn toegewezen. U kunt hiermee ook conflicten oplossen: u ziet welke instellingen leiden tot een conflict en welke profielen deze instellingen bevatten. De documentatie [Veelvoorkomende problemen en oplossingen](device-profile-troubleshoot.md) helpt beheerders bij het werken met profielen. Hierin wordt beschreven wat er gebeurt wanneer u een profiel verwijdert, waarom meldingen worden verzonden naar apparaten, en meer.

## <a name="next-steps"></a>Volgende stappen

Kies uw platform en ga aan de slag.
