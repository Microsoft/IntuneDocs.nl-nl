---
title: Apparaatfuncties en -instellingen gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Overzicht van de verschillende Microsoft Intune-apparaatprofielen, waaronder functies, beperkingen, e-mail, Wi-Fi, VPN, onderwijs, certificaten, Windows 10-upgrade, BitLocker en Windows Defender, Windows Information Protection, beheersjablonen en aangepaste configuratie-instellingen voor apparaten in Azure Portal. Gebruik deze profielen om gegevens en apparaten in uw bedrijf te beheren en te beveiligen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: bc28bca31c43140a7bca528655825bab60c53be1
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203515"
---
# <a name="apply-features-settings-on-your-devices-using-device-profiles-in-microsoft-intune"></a>Functie-instellingen toepassen op uw apparaten met apparaatprofielen in Microsoft Intune

Microsoft Intune omvat instellingen en functies die u op verschillende apparaten binnen uw organisatie kunt in- of uitschakelen. Deze instellingen en functies worden toegevoegd aan 'configuratieprofielen'. U kunt profielen maken voor verschillende apparaten en verschillende platforms, waaronder iOS, Android en Windows, en vervolgens via Intune het profiel toepassen op apparaten in uw organisatie.

Enkele profielvoorbeelden zijn:

- Gebruik op Windows 10-apparaten een profielsjabloon die ActiveX-besturingselementen blokkeert in Internet Explorer.
- Sta gebruikers van iOS- en macOS-apparaten toe om in uw organisatie AirPrint-printers te gebruiken.
- Sta wel of geen toegang toe tot bluetooth op het apparaat.
- Maak een Wi-Fi of VPN-profiel waarmee verschillende apparaten toegang hebben tot uw bedrijfsnetwerk.
- Beheer software-updates, inclusief het moment wanneer deze worden geïnstalleerd.
- Voer een Android-apparaat uit op een speciaal kioskapparaat dat één app kan uitvoeren of veel apps kan uitvoeren.

Dit artikel bevat de stappen om een profiel te maken en een overzicht van de verschillende typen profielen die u kunt maken. Gebruik deze profielen om bepaalde functies op de apparaten al dan niet toe te staan.

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.

2. Selecteer **Apparaatconfiguratie**. U hebt de volgende opties:

    - **Overzicht**: geeft de status van uw profielen weer en biedt aanvullende details over de profielen die u aan gebruikers en apparaten hebt toegewezen.
    - **Beheren**: maak apparaatprofielen en upload aangepaste [PowerShell-scripts](intune-management-extension.md) die binnen het profiel worden uitgevoerd, en voeg met [eSIM](esim-device-configuration.md) gegevensplannen toe aan apparaten.
    - **Bewaken**: controleer de status van een profiel op slagen of falen, en bekijk ook logboeken over uw profielen.
    - **Configureren**: voeg een certificeringsinstantie (SCEP of PFX) toe of schakel [Telecom-onkostenbeheer](telecom-expenses-monitor.md) aan het profiel toe.

3. Selecteer **Profielen** > **Profiel maken**. Voer de volgende eigenschappen in:

   - **Naam**: Voer een beschrijvende naam in voor het profiel.
   - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
   - **Platform**: Kies het platform van uw apparaten. Uw opties zijn:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 en hoger**
       - **Windows 10 en hoger**

   - **Profieltype**: Selecteer het type instellingen dat u wilt configureren. De lijst die wordt getoond, is afhankelijk van het **platform** dat u kiest:

       - [Beheersjablonen](administrative-templates-windows.md)
       - [Aangepast](custom-settings-configure.md)
       - [Delivery optimization](delivery-optimization-windows.md)
       - [Apparaatfuncties](device-features-configure.md)
       - [Apparaatbeperkingen](device-restrictions-configure.md)
       - [Editie-upgrade en modusschakelaar](edition-upgrade-configure-windows-10.md)
       - [Onderwijs](education-settings-configure.md)
       - [E-mail](email-settings-configure.md)
       - [Endpoint Protection](endpoint-protection-configure.md)
       - [Identiteitsbescherming](identity-protection-configure.md)  
       - [Kiosk](kiosk-settings.md)
       - [PKCS-certificaat](certficates-pfx-configure.md)
       - [SCEP-certificaat](certificates-scep-configure.md)
       - [Vertrouwd certificaat](certificates-configure.md)
       - [Updatebeleid](software-updates-ios.md)
       - [VPN](vpn-settings-configure.md)
       - [Wi-Fi](wi-fi-settings-configure.md)
       - [Windows Defender ATP](advanced-threat-protection.md)
       - [Windows Information Protection](windows-information-protection-configure.md)

     Als u bijvoorbeeld **iOS** selecteert als platform, zien uw opties voor het profieltype er ongeveer als volgt uit:

     ![iOS-profiel maken in Intune](./media/create-device-profile.png)

4. Selecteer **Instellingen**. De instellingen zijn ingedeeld per categorie. Selecteer een categorie voor een lijst van alle instellingen die u kunt configureren.

5. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Lees de volgende secties in dit artikel voor meer informatie over de verschillende profieltypen.

## <a name="administrative-templates-preview"></a>Beheersjablonen (Preview)

[Beheersjablonen](administrative-templates-windows.md) bevat honderden instellingen die u kunt configureren voor Internet Explorer, OneDrive, extern bureaublad, Word, Excel en andere Office-programma's, en nog veel meer.

Deze sjablonen bieden beheerders een handige en vereenvoudigde weergave van instellingen die vergelijkbaar zijn met groepsbeleid, maar ze zijn voor 100% gebaseerd op de cloud. 

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="device-features"></a>Apparaatfuncties

Met [Apparaatfuncties](device-features-configure.md) kunt u functies op iOS- en macOS-apparaten beheren, zoals AirPrint, meldingen en berichten voor schermvergrendeling.

Deze functie ondersteunt:

- iOS 
- macOS

## <a name="device-restrictions"></a>Apparaatbeperkingen

[Apparaatbeperkingen](device-restrictions-configure.md) beheert beveiliging, hardware, delen van gegevens en meer instellingen op de apparaten. U kunt bijvoorbeeld een apparaatbeperkingsprofiel maken waarmee wordt voorkomen dat gebruikers van iOS-apparaten de camera van het apparaat gebruiken. 

Deze functie ondersteunt:

- Android
- Android Enterprise
- iOS
- macOS
- Windows 10
- Windows 10 Team

## <a name="delivery-optimization"></a>Delivery Optimization

[Delivery optimization](delivery-optimization-windows.md) biedt een betere ervaring voor het leveren van software-updates. Deze instellingen vervangen de instellingen **Software-Updates** > **Windows 10-updatering**.

Gebruik deze instellingen om te bepalen hoe software-updates worden gedownload naar apparaten in uw organisatie. U kunt bijvoorbeeld gebruikers krijgen hun eigen updates laten downloaden of updates binnenhalen met behulp van de cloudservices voor delivery optimization in een apparaatprofiel.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="endpoint-protection"></a>Endpoint Protection

[Endpoint Protection-instellingen voor Windows 10](endpoint-protection-windows-10.md) configureert BitLocker- en Windows Defender-instellingen voor Windows 10-apparaten.

Zie het Engelstalige artikel [Configure endpoints using Mobile Device Management (MDM) tools](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-mdm-windows-defender-advanced-threat-protection) (Eindpunten configureren met MDM-hulpprogramma's (Mobile Device Management)) als u Windows Defender Advanced Threat Protection (WDATP) wilt vrijgeven met Microsoft Intune.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="identity-protection"></a>Identiteitsbescherming

Met [Identiteitsbescherming](identity-protection-configure.md) beheert u de Windows Hello voor Bedrijven-ervaring op Windows 10 en Windows 10 Mobile-apparaten. Configureer deze instellingen om Windows Hello voor Bedrijven beschikbaar maken voor gebruikers en apparaten, en om de vereisten op te geven voor pincodes en gebaren voor apparaten.  

Deze functie ondersteunt:  

- Windows 10 en hoger
- Windows Holographic for Business  

## <a name="kiosk"></a>Kiosk

Het profiel [Kiosk-instellingen](kiosk-settings.md) configureert een apparaat om één app uit te voeren of om verschillende apps uit te voeren. U kunt ook andere functies op uw kiosks aanpassen, waaronder een startmenu en een webbrowser.

Deze functie ondersteunt:

- Windows 10 en hoger

Kiosk-instellingen zijn ook beschikbaar als apparaatbeperkingen voor [Android](device-restrictions-android.md#kiosk), [Android Enterprise](device-restrictions-android-for-work.md#kiosk-settings) en [iOS](device-restrictions-ios.md#kiosk-supervised-only).

## <a name="email"></a>E-mail

[E-mailinstellingen](email-settings-configure.md) maakt en bewaakt de e-mailinstellingen voor Exchange ActiveSync op de apparaten en wijst deze toe. E-mailprofielen helpen met consistentie, verminderen het aantal ondersteuningsaanvragen en bieden uw eindgebruikers toegang tot bedrijfse-mail op hun eigen apparaten zonder dat ze instellingen hoeven op te geven. 

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

Met [mobiele eSIM-profielen](esim-device-configuration.md) kunnen beheerders mobiele data-abonnementen op uw beheerde apparaten configureren voor toegang tot internet en gegevens. Nadat u activeringscodes van uw mobiele operator hebt ontvangen, kunt u deze activeringscodes met Intune importeren en vervolgens toewijzen aan apparaten die geschikt zijn voor eSIM.

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

Zie [Delivery optimization](delivery-optimization-windows.md) voor updatebeleid op Windows-apparaten. 

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

[Windows Information Protection](windows-information-protection-configure.md) helpt bij de beveiliging tegen gegevenslekken zonder dat de gebruikerservaring van werknemers hierdoor wordt beïnvloed. Het helpt ook om zakelijke apps en gegevens te beschermen tegen onbedoelde gegevenslekken op apparaten die eigendom zijn van de onderneming en op persoonlijke apparaten die werknemers op het werk gebruiken. De omgeving of andere apps hoeven niet te worden gewijzigd om Windows Information Protection te gebruiken.

Deze functie ondersteunt:

- Windows 10 en hoger

## <a name="shared-multi-user-device"></a>Gedeelde apparaat voor meerdere gebruikers

[Windows 10](shared-user-device-settings-windows.md) en [Windows Holographic for Business](shared-user-device-settings-windows-holographic.md) omvatten instellingen voor het beheren van apparaten met meerdere gebruikers, ook wel bekend als gedeelde apparaten of gedeelde pc's. Wanneer een gebruiker zich aanmeldt met het apparaat, kiest u of de gebruiker de opties voor slaapstand kan wijzigen of bestanden op het apparaat kan opslaan. In een ander voorbeeld kunt u beleid maken waarmee inactieve referenties van Windows HoloLens-apparaten worden verwijderd om ruimte te maken.

Via deze instellingen voor gedeelde apparaten voor meerdere gebruikers kan een beheerder bepaalde apparaatfuncties beheren en deze gedeelde apparaten met Intune beheren.

Deze functie ondersteunt:

- Windows 10 en hoger
- Windows Holographic for Business

## <a name="custom-profile"></a>Aangepast profiel

Met [Aangepaste instellingen](custom-settings-configure.md) kunnen beheerders apparaatinstellingen toewijzen die niet zijn ingebouwd in Intune. Op Android-apparaten kunt u bijvoorbeeld OMA-URI-waarden invoeren. Voor iOS-apparaten kunt u een configuratiebestand importeren dat u in Apple Configurator hebt gemaakt. 

Deze functie ondersteunt:

- Android
- iOS
- macOS
- Windows Phone 8.1

## <a name="manage-and-troubleshoot"></a>Beheren en problemen oplossen

[Beheer uw profielen](device-profile-monitor.md) om de status van apparaten te controleren en te bekijken welke profielen zijn toegewezen. U kunt hiermee ook conflicten oplossen: u ziet welke instellingen leiden tot een conflict en welke profielen deze instellingen bevatten. [Veelvoorkomende problemen en oplossingen](device-profile-troubleshoot.md) bevat een lijst met vragen en antwoorden over profielen. Hierin leest u onder andere wat er gebeurt wanneer een profiel wordt verwijderd of wanneer meldingen naar apparaten worden verzonden.

## <a name="next-steps"></a>Volgende stappen
Kies uw platform en ga aan de slag:

