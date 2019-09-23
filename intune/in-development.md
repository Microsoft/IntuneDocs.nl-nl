---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4bd5392abba3ea22127cb9bcbbb53ec4929f2d5e
ms.sourcegitcommit: 1494ff4b33c13a87f20e0f3315da79a3567db96e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "71166357"
---
# <a name="in-development-for-microsoft-intune---september-2019"></a>In ontwikkeling voor Microsoft Intune - september 2019

Als ondersteuning bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Daarnaast:

- Als we verwachten dat u actie moet ondernemen vóór een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Als er een functie wordt uitgebracht in productie, ofwel als preview ofwel als algemeen beschikbare functie, wordt de functiebeschrijving verplaatst van deze pagina naar de [pagina Nieuwe functies](whats-new.md).
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [M365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!Note]
> Deze items representeren de huidige verwachtingen van Microsoft over Intune-mogelijkheden in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Niet alle items in ontwikkeling hebben een functieomschrijving op deze pagina.

**RSS feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer

### <a name="managed-google-play-private-lob-apps----1464182----"></a>Beheerde Google Play particuliere LOB-apps <!-- 1464182  -->
InTune biedt IT-beheerders de mogelijkheid om persoonlijke Android LOB-apps te publiceren naar beheerde Google Play via een IFRAME dat is inge sloten in de intune-console.  Momenteel moet de IT-beheerder LOB-apps rechtstreeks publiceren naar de Play-publicatie console van Google, waarvoor veel stappen nodig zijn en die zeer tijdrovend zijn.  Met deze nieuwe functie kunt u op eenvoudige wijze LOB-apps publiceren met een minimale set stappen zonder dat u de intune-console hoeft te verlaten.  Een van de Android-bedrijfs beheer scenario's die gebruikmaken van beheerde Google Play, kan profiteren van deze functie (werk profiel, toegewezen, volledig beheerde en niet-Inge schreven apparaten).  Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **beheerde Google Play** in de lijst **app-type** . Zie [beheerde Google Play apps toevoegen aan Android Enter prise-apparaten met intune](apps-add-android-for-work.md)voor meer informatie over beheerde Google Play-apps.

### <a name="company-portal-app-installation-status-messages----2514416----"></a>Berichten over de installatie status van Bedrijfsportal-app <!-- 2514416  -->
In de Bedrijfsportal-app worden aanvullende status berichten voor de app-installatie weer gegeven voor eind gebruikers. De volgende voor waarden zijn van toepassing op nieuwe Win32-afhankelijkheids functies:
- App installeren mislukt. Er is niet voldaan aan de afhankelijkheden die zijn gedefinieerd door de beheerder.
- De app is geïnstalleerd, maar moet opnieuw worden opgestart.
- De app wordt geïnstalleerd, maar moet opnieuw worden opgestart om verder te gaan.

### <a name="managed-google-play-iframe-support----2871756----"></a>Ondersteuning voor beheerde Google Play IFRAME <!-- 2871756  -->
InTune biedt ondersteuning voor het rechtstreeks toevoegen en beheren van webkoppelingen in de intune-console via de beheerde Google Play IFRAME.  Hiermee kunnen IT-beheerders een URL en pictogram afbeelding verzenden en deze koppelingen vervolgens implementeren op apparaten, net als gewone Android-apps. Een van de Android-bedrijfs beheer scenario's die gebruikmaken van beheerde Google Play, kan profiteren van deze functie (werk profiel, toegewezen, volledig beheerde en niet-Inge schreven apparaten).  Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **beheerde Google Play** in de lijst **app-type** . Zie [beheerde Google Play apps toevoegen aan Android Enter prise-apparaten met intune](apps-add-android-for-work.md)voor meer informatie over beheerde Google Play-apps.

### <a name="macos-support-for-vpp-apps----3173501----"></a>macOS-ondersteuning voor VPP-apps <!-- 3173501  -->
macOS-apps die u hebt aangeschaft met Apple Business Manager, worden weer gegeven in de console wanneer Apple VPP-tokens worden gesynchroniseerd in intune. Via de-console kunt u op apparaten en gebruikers gebaseerde licenties toewijzen, intrekken en opnieuw toewijzen voor groepen. Microsoft Intune helpt u bij het beheren van VPP-apps die in uw bedrijf zijn gekocht voor gebruik door:
- Licentiegegevens rapporteren vanuit de App Store.
- Bijhouden hoeveel van de licenties u hebt gebruikt.
- Niet meer exemplaren van de app installeren dan waar u recht op hebt.
Voor meer informatie over Intune en VPP raadpleegt u [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](vpp-apps.md).

### <a name="macos-support-for-web-apps----3174427----"></a>macOS-ondersteuning voor web-apps <!-- 3174427  -->
U kunt web-apps installeren, zodat u een snelkoppeling kunt toevoegen aan een URL op het web, met behulp van de macOS-Bedrijfsportal. Eind gebruikers hebben toegang tot de **installatie** actie op de pagina met app-Details voor een web-app in de macOS-bedrijfsportal. Zie [apps toevoegen aan Microsoft intune](apps-add.md)voor meer informatie over het app-type **webkoppeling** .

#### <a name="assign-microsoft-edge-beta-for-macos----4678761----"></a>Micro soft Edge Beta toewijzen voor macOS <!-- 4678761  -->
U kunt de nieuwste versie van micro soft Edge Beta toevoegen en toewijzen aan intune voor macOS-apparaten. Selecteer in intune**apps** > voor **client-apps** > **app** > **micro soft Edge-macOS**toevoegen. Wijs vervolgens micro soft Edge Beta toe aan de gewenste groepen. Micro soft auto update (MAU) houdt micro soft Edge up-to-date. Zie voor meer informatie over micro soft Edge [webtoegang beheren met behulp van micro soft Edge met Microsoft intune](manage-microsoft-edge.md).

### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Graph API bewerkingen voor intune-apps lezen en schrijven <!-- 5031704  -->
Toepassingen kunnen de intune-Graph API aanroepen met lees-en schrijf bewerkingen met behulp van de app-identiteit zonder gebruikers referenties. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) (Werken met intune in Microsoft Graph) voor meer informatie over het openen van de Microsoft Graph API voor Intune.

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>Inhoud van app-meldingen voor organisatie accounts configureren <!-- 2576686 -->
Met intune app-beveiligings beleid (APP) op Android-en iOS-apparaten kunt u inhoud voor app-meldingen beheren voor organisatie accounts. Deze functie vereist ondersteuning van toepassingen en is mogelijk niet beschikbaar voor alle toepassingen die zijn ingeschakeld voor apps. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie over APP.

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Beschikbare rapportage over Google Play-apps voor Android-werkprofielen <!-- 3041956  -->
U kunt voor beschikbare app-installaties op apparaten met Android-werkprofielen de status van de app-installatie en de geïnstalleerde versie van beheerde Google Play-apps bekijken. Zie [How to monitor app protection policies](app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren), [Manage Android work profile devices with Intune](android-enterprise-overview.md) (Apparaten met Android-werkprofielen beheren met Intune) en [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-types) (Type beheerde Google Play-app) voor meer informatie.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie

### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161----"></a>Apparaatfuncties, beperkingen van apparaten en extensie profielen voor iOS-en macOS-instellingen worden weer gegeven op registratie type <!-- 4886161  -->

In intune maakt u profielen voor IOS-en macOS-apparaten **(configuratie** > **profielen** > voor apparaten**profiel** > maken**IOS** of **MacOS** voor platform >- **apparaatfuncties** , **Beperkingen van apparaten**of **uitbrei dingen** voor profiel type). Op dit moment worden de beschik bare instellingen in deze profielen vermeld. 

In een toekomstige update wordt de beschik bare instellingen in de intune-Portal gecategoriseerd op basis van het registratie type waarmee ze worden toegepast:

- iOS
  - Alle inschrijvings typen
  - Registratie van apparaten en automatische apparaatregistratie
  - Automatische registratie van apparaten

- macOS
  - Alle inschrijvings typen
  - Apparaatinschrijving
  - Door de gebruiker goedgekeurde en geautomatiseerde apparaatregistratie
  - Automatische registratie van apparaten

Van toepassing op:

- iOS
  - [Apparaatfuncties](ios-device-features-settings.md)
  - [Apparaatbeperkingen](device-restrictions-ios.md)

- macOS
  - [Apparaatfuncties](macos-device-features-settings.md)
  - [Apparaatbeperkingen](device-restrictions-macos.md)
  - [Extensies](kernel-extensions-settings-macos.md)

### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835----"></a>Nieuwe instellingen voor spraak controle voor iOS-apparaten onder Super visie die worden uitgevoerd in de kiosk modus <!-- 4892835  -->

U kunt in intune beleids regels maken om IOS-apparaten onder Super visie te laten uitvoeren als kiosk of speciaal apparaat (**configuratie** > **profielen** > voor apparaten**profiel** > maken**IOS** voor platform >  **Beperkingen voor apparaten** voor profiel type > **kiosk (alleen onder Super visie)** ). 

In een toekomstige update zijn er nieuwe instellingen die u kunt beheren:

- **Spraak controle**: Hiermee schakelt u spraak besturing in op het apparaat in de kiosk modus.
- **Aanpassing van spraak controle**: Hiermee staat u gebruikers toe de instelling voor spraak besturing op het apparaat te wijzigen in de kiosk modus.

Als u de huidige instellingen wilt zien, gaat u naar de [instellingen voor IOS kiosk (alleen onder Super visie)](device-restrictions-ios.md#kiosk).

Van toepassing op:

- iOS 13.0 en hoger

### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175----"></a>Eenmalige aanmelding gebruiken voor apps en websites op iOS-en macOS-apparaten <!-- 4893175  -->
In een toekomstige update zijn er enkele nieuwe instellingen voor eenmalige aanmelding voor IOS-en macOS-apparaten (**configuratie** > **profielen** > voor apparaten**maken profiel** > **IOS** of **MacOS** voor platform **functies** > voor profiel type).

Gebruik deze instellingen om eenmalige aanmelding te configureren, met name voor apps en websites die gebruikmaken van Kerberos-verificatie. U kunt kiezen tussen een algemene referentie voor een app-extensie voor eenmalige aanmelding en de ingebouwde Kerberos-uitbrei ding van Apple.

Als u de huidige apparaatfuncties wilt zien die u kunt configureren, gaat u naar [IOS-apparaatfuncties](ios-device-features-settings.md) en functies van [macOS-apparaten](macos-device-features-settings.md).

Van toepassing op:

- iOS 13.0 en hoger
- macOS 10.15 of hoger

### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079----"></a>Domeinen koppelen aan apps op macOS 10.15 +-apparaten <!-- 4898079  -->
Op macOS-apparaten kunt u verschillende functies configureren en deze functies naar uw apparaten pushen met behulp van een beleid (**apparaat-configuratie** > **profielen** > **profiel** > **macOS** maken voor platform **functies** > voor profiel type). In een toekomstige update kunt u domeinen koppelen aan uw apps. Deze functie helpt bij het delen van referenties met websites die aan uw app zijn gerelateerd, en kan worden gebruikt met de extensie voor eenmalige aanmelding, universele koppelingen en het automatisch door voeren van wacht woorden. 

Ga naar de [functie-instellingen van macOS-apparaten in intune](macos-device-features-settings.md)voor een overzicht van de huidige functies die u kunt configureren.

Van toepassing op:

- macOS 10.15 of hoger

### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474----"></a>' ITunes ' en ' apps ' in de iTunes App Store-URL gebruiken voor het weer geven of verbergen van apps op apparaten met Super visie op iOS <!-- 4928474  --> 
U kunt in intune beleids regels maken om apps op uw IOS-apparaten onder Super visie weer te geven of te verbergen (**apparaatconfiguratie** > **profielen** > **profiel** > maken**IOS** voor platform > **apparaat beperkingen** voor profiel type > **apps weer geven of verbergen (alleen onder Super visie)** ). 

U kunt de iTunes App Store-URL invoeren, zoals `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. In een toekomstige update kunt u zowel `apps` `itunes` als gebruiken in de URL, zoals:

- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Zie [apps weer geven of verbergen](device-restrictions-ios.md#show-or-hide-apps)voor meer informatie over deze instellingen.

Van toepassing op:

- iOS

### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS <!-- 1943438 -->
U kunt met het IKEv2-protocol VPN-profielen voor de systeemeigen VPN-client van iOS maken. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Instellingen**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of naar beheerde apparaten gepusht. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md) (VPN-instellingen configureren op iOS-apparaten in Microsoft Intune).

Van toepassing op: iOS


<!-- ***********************************************-->
## <a name="device-enrollment"></a>Apparaatinschrijving

### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790----"></a>Nieuwe tenants worden standaard verwijderd uit beheer van Android-apparaten <!-- 4869790  -->
De mogelijkheden voor het beheer van Android-apparaten zijn vervangen door Android Enter prise. Daarom raden we aan om Android Enter prise voor nieuwe inschrijvingen te gebruiken. Bij een toekomstige update moeten nieuwe tenants de volgende vereiste stappen uitvoeren in Android-inschrijving om beheer van Apparaatbeheer te gebruiken: Ga naar **intune** > **apparaatregistratie** > inschrijving**Android** Persoonlijke en **apparaten in bedrijfs eigendom met** > de beheerders bevoegdheden**Apparaatbeheer gebruiken om apparaten te beheren.**  > 

Bestaande tenants ondervinden geen wijzigingen in hun omgevingen. 

Zie voor meer informatie over de beheerder van Android-apparaten in intune [registratie van Android Device Administrator](android-enroll-device-administrator.md).

### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993----"></a>Voor iOS-apparaten past u het scherm voor inschrijvings proces van de Bedrijfsportal aan <!-- 4394993  -->
Met prijs verlaging kunt u het privacy-scherm van de Bedrijfsportal aanpassen dat eind gebruikers te zien krijgen tijdens de iOS-registratie. U kunt met name de lijst met dingen aanpassen die uw organisatie niet kan zien of op het apparaat kan doen.

<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer

### <a name="deploy-software-updates-to-macos-devices----3194876---"></a>Software-updates implementeren op macOS-apparaten <!-- 3194876 -->
U kunt software-updates implementeren op groepen macOS-apparaten. Deze functie omvat essentiële, firmware, configuratie bestand en andere updates. U kunt updates verzenden via de volgende check van het apparaat of een wekelijkse planning selecteren voor het implementeren van updates in of een periode waarin Windows is ingesteld. Dit helpt u bij het bijwerken van apparaten buiten de standaard werk uren of wanneer uw Help Desk volledig is gewerkt. U krijgt ook een gedetailleerd rapport van alle macOS-apparaten waarop updates zijn geïmplementeerd. U kunt inzoomen op het rapport per apparaat om de status van bepaalde updates te bekijken.

### <a name="send-custom-notifications-to-a-device----4928910----"></a>Aangepaste meldingen naar een apparaat verzenden <!-- 4928910  -->
U kunt aangepaste meldingen verzenden naar specifieke apparaten waarop de Bedrijfsportal-of intune-app is geïnstalleerd. Als u dit wilt doen, gaat u naar **intune** > -**apparaten** > **alle apparaten** > een apparaat kiezen > **meer** > **aangepaste meldingen verzenden**. 

### <a name="updates-to-android-enterprise-fully-managed-features----3464667-5227935-4062195-4631425-4631440---"></a>Updates voor volledig beheerde functies van Android Enter prise <!-- 3464667, 5227935, 4062195, 4631425, 4631440 -->

We voegen de volgende ondersteuning toe voor volledig beheerde Android-apparaten:

- SCEP-certificaten voor volledig beheerde Android zijn beschikbaar voor certificaat verificatie op apparaten die als de eigenaar van het apparaat worden beheerd. SCEP-certificaten worden al ondersteund op werk profiel apparaten.  Met SCEP-certificaten voor de eigenaar van het apparaat kunt u het volgende doen: <!-- 5227935 -->
    - SCEP-profiel maken onder DO section of Android Enter prise
    - SCEP-certificaten koppelen aan Wi-Fi-profiel voor verificatie
    - SCEP-certificaten koppelen aan VPN-profielen voor verificatie
    - SCEP-certificaten koppelen aan e-mail profielen voor authenticatie (via app-configuratie)
- Systeem-apps worden ondersteund op Android Enter prise-apparaten. In intune voegt u een Android-bedrijfs systeem-app toe door **client apps** > **apps** > **toevoegen**te selecteren. In de lijst **app-type** selecteert u **Android Enter prise System-app**. Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over apps toevoegen aan Intune. <!-- 4062195 -->
- **Inapparaatcompatibiliteit**: de eigenaarvaneen > **Android Enterprise** > **apparaat kunt u een** nalevings beleid maken waarmee de Google wordt ingesteld SafetyNet Attestation-niveau.   <!-- 4631425 -->
- Op Android Enter prise volledig beheerde apparaten worden de providers voor de beveiliging van mobiele dreigingen ondersteund. **Inapparaatcompatibiliteit**: de eigenaarvaneen > **Android Enterprise** >  **-apparaat kunt u een** acceptabel bedreigings niveau kiezen. <!-- 4631440 --> In [Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune](compliance-policy-create-android-for-work.md#device-owner) worden de huidige instellingen vermeld.


Van toepassing op: 
- Volledig beheerde Android Enterprise-apparaten

<!-- ***********************************************-->
## <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

### <a name="updated-support-experience-------5012398------"></a>Bijgewerkte ondersteunings ervaring   <!--  5012398    -->
Als onderdeel van de voortdurende verbeteringen wordt de ondersteunings ervaring van de console voor intune bijgewerkt.  We verbeteren de zoek opdracht in de console en feedback voor veelvoorkomende problemen en stroom lijnen de werk stroom om contact op te nemen met de ondersteuning.     

<!-- ***********************************************-->
## <a name="security"></a>Beveiliging

### <a name="tamper-protection-for-windows-defender-antivirus-----4705448---------"></a>Bescherming tegen knoeien voor Windows Defender anti virus  <!-- 4705448       -->
Er wordt *onrecht matige beveiliging* toegevoegd aan de instellingen die door intune kunnen worden beheerd voor Windows Defender anti virus. U kunt een apparaatconfiguratie-profiel voor Windows 10 Endpoint Protection gebruiken om de beveiliging tegen knoeien in of uit te scha kelen.  Zie voor meer informatie over onrecht matige beveiliging de [wijzigingen in beveiligings instellingen voor komen met knoei beveiliging](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) in de Windows-documentatie. 


<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.




