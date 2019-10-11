---
title: Nieuwe functies in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 571974e1736fb78ae633c02fcfd6e6233056379b
ms.sourcegitcommit: 78f9750712c254d8b123ef15b74f30ca999aa128
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/03/2019
ms.locfileid: "71920117"
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook [belangrijke kennisgevingen](#notices), [oudere releases](whats-new-archive.md) en informatie over [hoe service-updates voor Intune worden uitgebracht](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728).

> [!Note]
> Het kan voor elke [maandelijkse update](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Service-Updates/ba-p/358728) tot drie dagen duren totdat deze wordt geïmplementeerd. Dit gebeurt in de volgende volgorde:
>
> - Dag 1: Azië en Stille Oceaan (APAC)
> - Dag 2: Europa, Midden-Oosten en Afrika (EMEA)
> - Dag 3: Noord-Amerika
>
> Sommige functies worden gedurende een aantal weken geïmplementeerd en zijn mogelijk niet voor alle gebruikers in de eerste week beschikbaar.
>
> Controleer de [pagina In ontwikkeling](in-development.md) voor een lijst met nieuwe functies in een versie.

**RSS-feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22What%27s+new+in+microsoft+intune%3F+-+Azure%22&locale=en-us`

<!-- Common categories:  
### App management
### Device configuration
### Device enrollment
### Device management
### Device security
### Intune apps
### Monitor and troubleshoot
### Role-based access control

-->  

<!-- ########################## -->

## <a name="week-of-september-23-2019"></a>Week van 23 september 2019

#### <a name="ios-user-enrollment-in-preview----4817900---"></a>Inschrijving van iOS-gebruikers in Preview <!-- 4817900 -->
De iOS 13.1-release van Apple bevat Gebruikersinschrijving, een nieuwe vorm van Lightweight Management voor iOS-apparaten. Deze functie kan worden gebruikt in plaats van Apparaatinschrijving of Automatische apparaatinschrijving (voorheen Device Enrollment Program) voor apparaten die persoonlijk eigendom zijn. De Preview-versie van Intune ondersteunt deze functieset zodat u het volgende kunt doen:

- Gebruikersinschrijving richten op gebruikersgroepen.
- Eindgebruikers de mogelijkheid geven om te kiezen tussen het lichtere Gebruikersregistratie of het sterkere Apparaatinschrijving bij het inschrijven van hun apparaten.

Vanaf 24 september 2019, met de release van iOS 13.1, worden deze updates geïmplementeerd voor alle klanten. We verwachten dat dit proces eind volgende week is voltooid.
Van toepassing op:

iOS 13.1 en hoger

#### <a name="intune-support-for-ipados-and-ios-131-devices---5439574--"></a>Intune-ondersteuning voor iPadOS- en iOS 13.1-apparaten <!--5439574-->
Intune biedt nu ondersteuning voor iPadOS- en iOS 13.1-apparaten Lees [dit blogbericht](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-1-and-iPadOS/ba-p/873094) voor meer informatie.

<!-- ########################## -->

## <a name="week-of-september-16-2019"></a>Week van 16 september 2019

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="app-management"></a>Appbeheer 

#### <a name="managed-google-play-private-lob-apps----1464182----"></a>Privé-LOB-apps uit de beheerde Google Play Store <!-- 1464182  -->
In Intune is nu toegestaan dat IT-beheerders privé-LOB-apps van Android publiceren in de beheerde Google Play Store, via een iFrame ingesloten in de Intune-console.  Voorheen moesten IT-beheerders LOB-apps rechtstreeks publiceren in de publicatieconsole van de Google Play Store. Hiervoor zijn verschillende stappen nodig en het is tijdrovend. Met deze nieuwe functie kunnen LOB-apps eenvoudig worden gepubliceerd met een minimaal aantal stappen, zonder de Intune-console te verlaten.  Beheerders hoeven zich niet meer handmatig als een ontwikkelaar te registreren bij Google, en ze hoeven de registratiekosten van $ 25 niet te betalen.  Elk van deze scenario’s voor Android Enterprise-beheer waarin de beheerde Google Play Store wordt gebruikt, kunnen profiteren van deze functie (werkprofiel, toegewezen, volledig beheerd, en niet-ingeschreven apparaten). Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Beheerde Google Play** in de lijst met **App-typen**. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie over beheerde Google Play-apps.

#### <a name="windows-company-portal-experience----1473353-3598357---"></a>Versie van de Windows-bedrijfsportal-app <!-- 1473353, 3598357 -->
De Windows-bedrijfsportal wordt bijgewerkt. U kunt meerdere filters gebruiken op de apps-pagina in de Windows-bedrijfsportal. De pagina met apparaatdetails is ook bijgewerkt met een verbeterde gebruikerservaring. Deze updates worden momenteel geïmplementeerd voor alle klanten. We verwachten dat dit proces eind volgende week is voltooid.

#### <a name="macos-support-for-web-apps----3174427---"></a>macOS-ondersteuning voor web-apps <!-- 3174427 -->
Web-apps, waarmee u een snelkoppeling naar een URL op het web kunt toevoegen, kunnen in de Dock worden geïnstalleerd met behulp van de bedrijfsportal voor macOS. Eindgebruikers hebben toegang tot de actie **Installeren** op de pagina met app-details voor een web-app in de macOS-bedrijfsportal. Zie [Apps toevoegen aan Microsoft Intune](../apps/apps-add.md) en [Web-apps toevoegen aan Microsoft Intune](../apps/web-app.md) voor meer informatie over het app-type **Webkoppeling**.

#### <a name="macos-support-for-vpp-apps----3173501----"></a>macOS-ondersteuning voor VPP-apps <!-- 3173501  -->
macOS-apps, gekocht met Apple Business Manager, worden in de console weergegeven wanneer Apple VPP-tokens worden gesynchroniseerd in Intune. Met de Intune-console kunt u op apparaten en gebruikers gebaseerde licenties voor groepen toewijzen, intrekken en opnieuw toewijzen. Microsoft Intune maakt het makkelijker om VPP-apps te beheren die voor gebruik in uw bedrijf zijn gekocht door:

- Licentiegegevens rapporteren vanuit de App Store.
- Bijhouden hoeveel van de licenties u hebt gebruikt.
- U te helpen voorkomen dat er meer exemplaren van de app worden geïnstalleerd dan waarvan u eigenaar bent.

Voor meer informatie over Intune en VPP raadpleegt u [Apps en boeken met Microsoft Intune beheren die via het Volume Purchase Program zijn gekocht](../apps/vpp-apps.md).

#### <a name="managed-google-play-iframe-support----2871756----"></a>Ondersteuning voor de beheerde Google Play-iFrame <!-- 2871756  -->
Intune biedt nu ondersteuning voor het rechtstreeks toevoegen en beheren van webkoppelingen in de Intune-console via de beheerde Google Play-iFrame.  Hiermee kunnen IT-beheerders een URL en pictogramafbeelding verzenden, en deze koppelingen vervolgens implementeren op apparaten, zoals gewone Android-apps. Elk van deze scenario’s voor Android Enterprise-beheer waarin de beheerde Google Play Store wordt gebruikt, kunnen profiteren van deze functie (werkprofiel, toegewezen, volledig beheerd, en niet-ingeschreven apparaten). Vanuit Intune selecteert u **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Beheerde Google Play** in de lijst met **App-typen**. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie over beheerde Google Play-apps.

#### <a name="silently-install-android-lob-apps-on-zebra-devices----4252734----"></a>LOB-apps van Android op de achtergrond installeren op Zebra-apparaten <!-- 4252734  -->
Wanneer u LOB-apps (Line-of-Business) van Android installeert op [Zebra-apparaten](../configuration/android-zebra-mx-overview.md), kunt u de app op de achtergrond installeren, in plaats van dat u wordt gevraagd om de LOB-app zowel te downloaden als te installeren. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer in het deelvenster **App toevoegen** de optie **Line-Of-Business-app**. Zie [Een Android Line-Of-Business-app toevoegen aan Microsoft Intune](../apps/lob-apps-android.md) voor meer informatie.

Momenteel wordt, nadat de LOB-app is gedownload, een melding over het **slagen van de download** weergegeven op het apparaat van de gebruiker. U kunt deze melding alleen negeren door in de schaduw van de melding te tikken op **Alles wissen**. Dit meldingsprobleem wordt opgelost in een toekomstige release, en de installatie vindt volledig op de achtergrond plaats, zonder dat dit zichtbaar is.

#### <a name="read-and-write-graph-api-operations-for-intune-apps----5031704----"></a>Graph API-bewerkingen voor Intune-apps lezen en schrijven <!-- 5031704  -->
De Intune Graph API kan via lees- en schrijfbewerkingen worden aangeroepen voor toepassingen, met behulp van de app-id zonder gebruikersreferenties. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) (Werken met intune in Microsoft Graph) voor meer informatie over het openen van de Microsoft Graph API voor Intune.

#### <a name="protected-data-sharing-and-encryption-for-intune-app-sdk-for-ios----3586942----"></a>Het delen en versleutelen van beveiligde gegevens voor Intune App SDK voor iOS <!-- 3586942  -->
De Intune App-SDK voor iOS gebruikt 256-bits versleutelingssleutels wanneer versleuteling is ingeschakeld door app-beveiligingsbeleid. Alle apps moeten eerst over een SDK-versie 8.1.1 beschikken, als u het delen van beveiligde gegevens wilt toestaan.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438-----"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS <!-- 1943438   -->
In deze update kunt u met het IKEv2-protocol VPN-profielen maken voor de systeemeigen VPN-client van iOS. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Verbindingstype**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of gepusht naar beheerde apparaten. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [VPN-instellingen configureren op iOS-apparaten](../configuration/vpn-settings-ios.md).

Van toepassing op:
- iOS

#### <a name="device-features-device-restrictions-and-extension-profiles-for-ios-and-macos-settings-are-shown-by-enrollment-type----4886161-----"></a>Apparaatfuncties, apparaatbeperkingen, en extensieprofielen voor iOS- en macOS-instellingen worden weergegeven op inschrijvingstype <!-- 4886161   -->

In Intune maakt u profielen voor iOS- en macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatfuncties**, **Apparaatbeperkingen**, of **Extensies** voor profieltype). 

In deze update zijn de beschikbare instellingen in de Intune-portal gecategoriseerd op basis van het inschrijvingstype waarop ze zijn toegepast:

- iOS
  - Gebruikersinschrijving
  - Apparaatinschrijving
  - Automatische apparaatinschrijving (onder toezicht)
  - Alle inschrijvingstypen

- macOS
  - Goedgekeurd door de gebruiker
  - Apparaatinschrijving
  - Automatische apparaatinschrijving
  - Alle inschrijvingstypen

Van toepassing op:
- iOS

#### <a name="new-voice-control-settings-for-supervised-ios-devices-running-in-kiosk-mode----4892835-----"></a>Nieuwe instellingen voor spraakbeheer voor iOS-apparaten onder supervisie die worden uitgevoerd in de kioskmodus <!-- 4892835   -->
In Intune kunt u beleid maken om iOS-apparaten onder supervisie uit te voeren als een kiosk of toegewezen apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Kiosk**). 

Deze update bevat nieuwe instellingen die u kunt beheren:
- **Spraakbeheer**: Hiermee wordt Spraakbeheer ingeschakeld op het apparaat, wanneer het apparaat in de kioskmodus is.
- **Aanpassing van spraakbeheer**: Gebruikers toestaan de instelling voor spraakbeheer te wijzigen op het apparaat, wanneer het apparaat in de kioskmodus is.

Als u de huidige instellingen wilt zien, gaat u naar de [iOS Kiosk-instellingen](../configuration/device-restrictions-ios.md#kiosk).

Van toepassing op:
- iOS 13.0 en hoger

#### <a name="use-single-sign-on-for-apps-and-websites-on-your-ios-and-macos-devices----4893175-----"></a>Eenmalige aanmelding gebruiken voor apps en websites op iOS- en macOS-apparaten <!-- 4893175   -->
Deze update bevat enkele nieuwe instellingen voor eenmalige aanmelding voor iOS- en macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatfuncties**, voor profieltype).

Gebruik deze instellingen om eenmalige aanmelding te configureren, speciaal bedoeld voor apps en websites die gebruikmaken van Kerberos-verificatie. U kunt kiezen tussen een algemene app-extensie voor referenties met eenmalige aanmelding, en de ingebouwde Kerberos-extensie van Apple.

Als u wilt zien welke huidige apparaatfuncties u kunt configureren, gaat u naar [iOS-apparaatfuncties](../configuration/ios-device-features-settings.md) en [macOS-apparaatfuncties](../configuration/macos-device-features-settings.md).

Van toepassing op:
- iOS 13.0 en hoger
- macOS 10.15 of hoger

#### <a name="associate-domains-to-apps-on-macos-1015-devices----4898079-----"></a>Domeinen koppelen aan apps op macOS 10.15-apparaten en hoger <!-- 4898079   -->
Op macOS-apparaten kunt u verschillende functies configureren en deze functies naar uw apparaten pushen met behulp van beleid (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatfuncties** voor profieltype). In deze update kunt u domeinen koppelen aan uw apps. Deze functie helpt bij het delen van referenties op websites die verband houden met uw app, en kan worden gebruikt met de extensie voor eenmalige aanmelding, universele koppelingen, en automatisch invullen van wachtwoorden van Apple. 

Ga naar [Instellingen van macOS-apparaatfuncties in Intune](../configuration/macos-device-features-settings.md) om te zien welke huidige functies u kunt configureren.

Van toepassing op:
- macOS 10.15 of hoger

#### <a name="use-itunes-and-apps-in-the-itunes-app-store-url-when-showing-or-hiding-apps-on-ios-supervised-devices----4928474-----"></a>Gebruik 'iTunes' en 'apps' in de iTunes App Store-URL bij het weergeven of verbergen van apps op iOS-apparaten onder supervisie <!-- 4928474   --> 
In Intune kunt u beleid maken om apps weer te geven of te verbergen op iOS-apparaten onder supervisie (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Apps weergeven of verbergen**). 

U kunt de iTunes App Store-URL invoeren, zoals `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`. In deze update kan zowel `apps` als `itunes` worden gebruikt in de URL, zoals:
- `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8`
- `https://apps.apple.com/us/app/work-folders/id950878067?mt=8`

Zie [Apps weergeven of verbergen](../configuration/device-restrictions-ios.md#show-or-hide-apps) voor meer informatie over deze instellingen.

Van toepassing op:
- iOS

#### <a name="windows-10-compliance-policy-password-type-values-are-clearer-and-match-csp---5138985---"></a>Waarden voor het wachtwoordtype voor Windows 10-nalevingsbeleid zijn duidelijker en komen niet overeen met CSP<!-- 5138985 -->
Op Windows 10-apparaten kunt u nalevingsbeleid maken waarvoor specifieke wachtwoordfuncties zijn vereist (**Apparaatcompatibiliteit** > **beleid** > **Beleid maken** > **Windows 10 en later** voor platform > **Systeembeveiliging**). In deze update:
- De waarden voor **Wachtwoordtype** zijn duidelijker, en zijn bijgewerkt om overeen te komen met de [DeviceLock/AlphanumericDevicePasswordRequired CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-devicelock#devicelock-alphanumericdevicepasswordrequired).
- De instelling **Wachtwoordverlooptijd (dagen)** is bijgewerkt om waarden toe te staan van minimaal 1 en maximaal 730 dagen. 

Zie [Instellingen voor Windows 10 en later om apparaten te markeren als compatibel of niet-compatibel](../protect/compliance-policy-create-windows.md) voor meer informatie over instellingen voor Windows 10-naleving. 

Van toepassing op:
- Windows 10 en hoger

 #### <a name="updated-ui-for-configuring-microsoft-exchange-on-premises-access-------4092920---"></a>Bijgewerkte gebruikersinterface voor het configureren van on-premises toegang tot Microsoft Exchange    <!-- 4092920 -->  
De console is bijgewerkt, zodat u [on-premises toegang tot Microsoft Exchange kunt configureren](../protect/conditional-access-exchange-create.md). Alle configuraties voor on-premises toegang tot Exchange zijn nu beschikbaar in hetzelfde deelvenster van de console waar u *Beheer voor on-premises toegang tot Exchange kunt inschakelen*.  

#### <a name="allow-or-restrict-adding-app-widgets-to-the-home-screen-on-android-enterprise-work-profile-devices----1109650----"></a>Het toevoegen van app-widgets aan het startscherm in apparaten met Android Enterprise-werkprofielen toestaan of beperken <!-- 1109650  --> 
Op Android Enterprise-apparaten kunt u functies in het werkprofiel configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Alleen werkprofiel > Apparaatbeperkingen** voor profieltype). In deze update kunt u gebruikers toestaan om widgets die worden weergegeven in werkprofiel-apps, toe te voegen aan het startscherm van het apparaat.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op:
- Android Enterprise - Werkprofiel

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="new-tenants-will-default-away-from-android-device-administrator-management----4869790-----"></a>Nieuwe tenants worden standaard verwijderd uit het beheer van Android-apparaatbeheerders <!-- 4869790   -->
De beheermogelijkheden voor Android-apparaten zijn vervangen door Android Enterprise. Daarom raden we u aan om vanaf nu Android Enterprise te gebruiken voor nieuwe inschrijvingen. Bij een toekomstige update moeten de volgende vereiste stappen voor Android-inschrijving worden uitgevoerd voor nieuwe tenants, om beheer van apparaatbeheerders te gebruiken: Ga naar **Intune** > **Apparaatinschrijving** > **Android-inschrijving** > **Persoonlijke apparaten en apparaten in bedrijfseigendom met bevoegdheden voor het beheren van apparaten** > **Apparaatbeheer gebruiken om apparaten te beheren**.

De omgevingen van bestaande tenants worden niet gewijzigd. 

Zie [Inschrijving van Android-apparaatbeheerders](https://docs.microsoft.com/intune/android-enroll-device-administrator) voor meer informatie over Android-apparaatbeheerders in Intune.

#### <a name="list-of-dep-devices-associated-with-a-profile----5012045-idmiss---"></a>Lijst met DEP-apparaten die zijn gekoppeld aan een profiel <!-- 5012045 idmiss -->
U kunt nu een lijst met pagina’s bekijken met geautomatiseerde DEP-apparaten van Apple (Device Enrollment Program) die zijn gekoppeld aan een profiel. U kunt in de lijst zoeken vanaf elke pagina in de lijst. Als u deze lijst wilt bekijken, gaat u naar **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > kies een token > **Profielen** > kies een profiel > **Toegewezen apparaten** (onder**Monitor**). 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-management"></a>Apparaatbeheer

#### <a name="more-android-fully-managed-support----3464667-4631425-4631440-5227935-4062195-----"></a>Meer ondersteuning voor volledig beheerde Android-apparaten <!-- 3464667, 4631425, 4631440, 5227935, 4062195   -->
We hebben de volgende ondersteuning toegevoegd voor volledig beheerde Android-apparaten:

- SCEP-certificaten voor volledig beheerde Android-apparaten zijn beschikbaar voor certificaatverificatie op apparaten die worden beheerd als Apparaateigenaar. SCEP-certificaten worden al ondersteund op Werkprofiel-apparaten.  Met SCEP-certificaten voor Apparaateigenaar kunt u het volgende doen: <!-- 5227935 -->
    - SCEP-profiel maken onder de DO-sectie van Android Enterprise
    - SCEP-certificaten koppelen aan een DO-Wi-Fi-profiel voor verificatie
    - SCEP-certificaten koppelen aan DO-VPN-profielen voor verificatie
    - SCEP-certificaten koppelen aan DO-e-mailprofielen voor verificatie (via AppConfig)
- Systeem-apps worden ondersteund op Android Enterprise-apparaten. Voeg in Intune een Android Enterprise-systeem-app toe door **Client-apps** > **Apps** > **Toevoegen** te selecteren. Selecteer in de lijst **App-type** het type **Android Enterprise-systeem-app**. Zie [Android Enterprise-systeem-apps toevoegen aan Microsoft Intune](../apps/apps-ae-system.md) voor meer informatie. <!-- 4062195 -->
- In **Apparaatcompatibiliteit** > **Android Enterprise** > **Apparaateigenaar**, kunt u nalevingsbeleid maken waarmee het niveau van SafetyNet-attestation wordt ingesteld.   <!-- 4631425 -->
- Op volledig beheerde Android Enterprise-apparaten worden de Mobile Threat Defense-providers ondersteund. In **Apparaatcompatibiliteit** > **Android Enterprise** > **Apparaateigenaar**, kunt u een acceptabel bedreigingsniveau kiezen. <!-- 4631440 --> In [Android Enterprise-instellingen om te markeren of apparaten wel of niet conform zijn met behulp van Intune](../protect/compliance-policy-create-android-for-work.md#device-owner) worden de huidige instellingen vermeld.
- De Microsoft Launcher-app kan nu op volledig beheerde Android Enterprise-apparaten worden geconfigureerd via app-configuratiebeleid, voor een gestandaardiseerde eindgebruikerservaring op volledig beheerde apparaten. De Microsoft Launcher-app kan worden gebruikt om uw Android-apparaat te personaliseren. Door de app te gebruiken samen met een Microsoft-account of werk/school-account hebt u toegang tot uw agenda, documenten en recente activiteiten in uw gepersonaliseerde feed. <!-- 5334044 -->

We zijn blij te kunnen aankondigen dat met deze update Intune-ondersteuning voor volledig beheerde Android Enterprise-apparaten nu algemeen beschikbaar is.

Van toepassing op:

- Volledig beheerde Android Enterprise-apparaten

#### <a name="send-custom-notifications-to-a-single-device-----4928910---"></a>Aangepaste meldingen verzenden naar één apparaat  <!-- 4928910 -->
U kunt nu één apparaat selecteren en vervolgens een externe apparaatactie gebruiken om [een aangepaste melding te verzenden naar alleen dit specifieke apparaat](../remote-actions/custom-notifications.md#send-a-custom-notification-to-a-single-device).

#### <a name="wipe-and-passcode-reset-actions-arent-available-for-ios-devices-that-are-enrolled-by-using-user-enrollment----4950491---"></a>Acties voor wissen en het opnieuw instellen van wachtwoordcode zijn niet beschikbaar voor iOS-apparaten die zijn ingeschreven met behulp van gebruikersinschrijving <!-- 4950491 -->
Gebruikersinschrijving is een nieuw type inschrijving voor Apple-apparaten. Wanneer u apparaten inschrijft met behulp van gebruikersinschrijving, zijn de externe acties voor wissen en het opnieuw instellen van wachtwoordcode niet beschikbaar voor dergelijke apparaten.

#### <a name="intune-support-for-ios-13-and-macos-catalina-devices----4665317---"></a>Intune-ondersteuning voor iOS 13- en macOS Catalina-apparaten <!-- 4665317 -->
Intune biedt nu ondersteuning voor iOS 13- en macOS Catalina-apparaten. Zie de [blogpost Microsoft Intune-ondersteuning voor iOS 13 en iPadOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Microsoft-Intune-Support-for-iOS-13-and-iPadOS/ba-p/861998) voor meer informatie.

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="bitlocker-support-for-client-driven-recovery-password-rotation-------3444125---"></a>BitLocker-ondersteuning voor clientgestuurde rotatie van herstelwachtwoorden   <!--  3444125 -->
Gebruik Intune Endpoint Protection om [Clientgestuurde rotatie van herstelwachtwoorden](../protect/endpoint-protection-windows-10.md#windows-encryption) voor BitLocker te configureren voor apparaten waarop Windows-versie 1909 of later wordt uitgevoerd.

Met deze instelling wordt een clientgestuurde vernieuwing van het herstelwachtwoord geïnitieerd na het herstellen van het OS-station (hetzij met behulp van bootmgr of WinRE) en het ontgrendelen van het herstelwachtwoord op een vaste-gegevensstations. Met deze instelling wordt het specifieke gebruikte herstelwachtwoord vernieuwd. Andere niet-gebruikte wachtwoorden in het volume blijven ongewijzigd. Raadpleeg de BitLocker CSP-documentatie voor [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) voor meer informatie.

#### <a name="tamper-protection-for-windows-defender-antivirus-----4705448----------"></a>Manipulatiebeveiliging voor Windows Defender Antivirus  <!-- 4705448        -->
Gebruik Intune om *Manipulatiebeveiliging* te beheren voor Windows Defender Antivirus. U vindt de [instelling voor Manipulatiebeveiliging](../protect/endpoint-protection-windows-10.md#windows-defender-security-center) in de groep Microsoft Defender-beveiligingscentrum wanneer u apparaatconfiguratieprofielen gebruikt voor Windows 10 Endpoint Protection. U kunt Manipulatiebeveiliging instellen op *Ingeschakeld* om beperkingen voor manipulatiebeveiliging in te schakelen, op *Uitgeschakeld* om deze uit te schakelen, of op *Niet geconfigureerd* om de huidige configuratie van apparaten te behouden.  

Zie [Wijzigingen in beveiligingsinstellingen voorkomen met Manipulatiebeveiliging](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) voor meer informatie over Manipulatiebeveiliging in de Windows-documentatie. 

#### <a name="advanced-settings-for-windows-defender-firewall-are-now-generally-available-----5317392---------"></a>Geavanceerde instellingen voor Windows Defender Firewall zijn nu algemeen beschikbaar <!--  5317392       -->  
De [aangepaste Windows Defender-firewallregels voor eindpuntbescherming](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) die u configureert als onderdeel van een apparaatconfiguratieprofiel, zijn niet meer in de openbare preview-versie en zijn algemeen beschikbaar (GA).  U kunt deze regels gebruiken om inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten op te geven. Deze regels zijn in juli uitgebracht als een openbare preview-versie. 

<!-- vvvvvvvvvvvvvvvvvvvvvv -->
### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-now-support-terms-of-use-policies----2358863-idmiss---"></a>Bereiktags bieden nu ondersteuning voor beleid voor gebruiksvoorwaarden <!-- 2358863 idmiss -->
U kunt nu [bereiktags](scope-tags.md) toewijzen aan beleid voor gebruiksvoorwaarden. Hiervoor gaat u naar **Intune** > **Apparaatinschrijving** > **Voorwaarden** > kies een item in de lijst > **Eigenschappen** > **Bereiktags** > kies een bereiktag.

## <a name="week-of-september-9-2019"></a>Week van 9 september 2019

### <a name="app-management"></a>Appbeheer

#### <a name="updates-to-microsoft-intune-app----4997846---"></a>Updates voor de Microsoft Intune-app <!-- 4997846 -->
De Microsoft Intune-app voor Android is bijgewerkt met de volgende verbeteringen:
- De lay-out is bijgewerkt en verbeterd, zodat de belangrijkste navigatiehandelingen nu onderaan staan.
- Er is een extra pagina toegevoegd waarop het gebruikersprofiel wordt weergegeven.
- Er is een weergave van meldingen toegevoegd waarvoor de gebruiker handelingen moet verrichten, zoals wanneer apparaatinstellingen moeten worden bijgewerkt.
- Er is een weergave van aangepaste pushmeldingen toegevoegd. Dit is in lijn met de ondersteuning die recent is toegevoegd in de bedrijfsportal-apps voor iOS en Android. Zie [Aangepaste meldingen verzenden in Intune](../remote-actions/custom-notifications.md) voor meer informatie.

#### <a name="for-ios-devices-customize-the-enrollment-process-privacy-screen-of-the-company-portal----4394993---"></a>Voor iOS-apparaten past u het privacyvenster voor het inschrijvingsproces van de Bedrijfsportal aan <!-- 4394993 -->
Met behulp van Markdown kunt u het privacyvenster van de Bedrijfsportal aanpassen dat eindgebruikers te zien krijgen tijdens de iOS-registratie. U kunt met name de lijst met dingen aanpassen die uw organisatie niet op het apparaat kan zien of doen. Zie [De app Intune-bedrijfsportal configureren](../apps/company-portal-app.md#privacy-statement-customization) voor meer informatie.


## <a name="week-of-september-2-2019"></a>Week van 2 september 2019

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-user-interface-update--tenant-status-dashboard-----5273210----"></a>Update voor Intune-gebruikersinterface – dashboard Tenantstatus  <!-- 5273210  -->
De gebruikersinterface voor het dashboard Tenantstatus is bijgewerkt om deze in lijn te brengen met de stijlen van de Azure-gebruikersinterface. Zie [Tenantstatus](../tenant-status.md) voor meer informatie.


## <a name="week-of-august-26-2019"></a>Week van 26 augustus 2019

### <a name="configure-microsoft-edge-settings-using-administrative-templates-for-windows-10-and-newer----5228061---"></a>Microsoft Edge-instellingen configureren met beheersjablonen voor Windows 10 en nieuwer <!-- 5228061 -->

Op Windows 10- en nieuwere apparaten kunt u beheersjablonen maken om instellingen voor groepsbeleid te configureren in Intune. In deze update kunt u instellingen configureren die van toepassing zijn op Microsoft Edge-versie 77 en nieuwer.

Zie [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Intune](../configuration/administrative-templates-windows.md) voor meer informatie over deze beheersjalbonen.

Van toepassing op:

- Windows 10 en nieuwer (Windows RS4+)

## <a name="week-of-august-12-2019"></a>Week van 12 augustus 2019

### <a name="app-management"></a>Appbeheer

#### <a name="control-ios-app-uninstall-behavior-at-device-unenrollment----3504144-----"></a>Gedrag van het verwijderen van iOS-apps beheren bij het uitschrijven van apparaten <!-- 3504144   -->
Beheerders kunnen beheren of een app wordt verwijderd of behouden op een apparaat wanneer het apparaat wordt uitgeschreven op het niveau van een gebruikers- of apparaatgroep. 

#### <a name="categorize-microsoft-store-for-business-apps----3926922---"></a>Microsoft Store voor Bedrijven-apps categoriseren <!-- 3926922 -->
U kunt Microsoft Store voor Bedrijven-apps categoriseren. Selecteer hiertoe **Intune** > **Client-apps** > **Apps** > selecteer een Microsoft Store voor Bedrijven-app > **App-gegevens** > **Categorie**. Wijs een categorie toe in de vervolgkeuzelijst.

#### <a name="customized-notifications-for-microsoft-intune-app-users----4843354----"></a>Aangepaste meldingen voor gebruikers van Microsoft Intune-apps <!-- 4843354  -->
De Microsoft Intune-app voor Android ondersteunt nu het weergeven van aangepaste pushmeldingen. Dit is in lijn met de ondersteuning die recent is toegevoegd in de bedrijfsportal-apps voor iOS en Android. Zie [Aangepaste meldingen verzenden in Intune](../remote-actions/custom-notifications.md) voor meer informatie.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="new-features-for-android-enterprise-dedicated-devices-in-multi-app-mode----3755304-3041943-3041946-----"></a>Nieuwe functies voor aan Android Enterprise toegewezen apparaten in de modus voor meerdere apps <!-- 3755304 3041943 3041946   -->

U kunt in Intune functies en instellingen beheren in een kioskstijl op uw toegewezen Android Enterprise-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Alleen apparaateigenaar, Apparaatbeperkingen** voor profieltype).

In deze update worden de volgende functies toegevoegd:

- **Toegewezen apparaten** > Meerdere apps **:** de **Virtuele startknop** kan worden weergegeven door op het apparaat te vegen of op het scherm te zweven zodat gebruikers deze kunnen verplaatsen.
- **Toegewezen apparaten** > Meerdere apps **:** met **zaklantaarn**toegang kunnen gebruikers de zaklantaarn gebruiken. 
- **Toegewezen apparaten** > Meerdere apps **:** met **volumeregeling van media** kunnen gebruikers het mediavolume van het apparaat beheren met behulp van een schuifregelaar. 
- **Toegewezen apparaten** > Meerdere apps **:**  **een schermbeveiliging inschakelen**, een aangepaste afbeelding uploaden en bepalen wanneer de schermbeveiliging wordt weergegeven.

Ga naar [Android Enterprise-apparaatinstellingen om beperkingsfuncties toe te staan of te beperken met behulp van Intune](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings) om de huidige instellingen te zien.

Van toepassing op:

- Toegewezen Android Enterprise-apparaten

#### <a name="new-app-and-configuration-profiles-for-android-enterprise-fully-managed-devices----3574215-3574238-3574235-3574232-----"></a>Nieuwe app- en configuratieprofielen voor volledig beheerde Android Enterprise-apparaten <!-- 3574215 3574238 3574235 3574232   -->
Met behulp van profielen kunt u instellingen configureren die VPN-, e-mail-en Wi-Fi-instellingen toepassen op uw (volledig beheerde) Android Enterprise-apparaten in zakelijk eigendom. In deze update kunt u het volgende doen:

- [App-configuratiebeleid](../apps/app-configuration-policies-use-android.md) gebruiken voor het implementeren van e-mail instellingen van Outlook, Gmail en Nine Work.
- Apparaatconfiguratieprofielen gebruiken om [instellingen voor vertrouwde basiscertificaten](../protect/certificates-configure.md) te implementeren.
- Apparaatconfiguratieprofielen gebruiken om instellingen voor [VPN](../configuration/vpn-settings-android-enterprise.md) en [Wi-Fi](../configuration/wi-fi-settings-android-enterprise.md) te implementeren.

> [!IMPORTANT]
> Met deze functie gebruiken gebruikers hun gebruikersnaam en wachtwoord voor verificatie bij VPN-, Wi-Fi- en e-mailprofielen. Op dit moment is verificatie op basis van certificaten niet beschikbaar.

Van toepassing op:  
- Android Enterprise-apparaten in zakelijk eigendom (volledig beheerd)

#### <a name="control-the-apps-files-documents-and-folders-that-open-when-users-sign-in-to-macos-devices---3914202-----"></a>De apps, bestanden, documenten en mappen beheren die worden geopend wanneer gebruikers zich aanmelden bij macOS-apparaten <!--3914202   -->
U kunt functies inschakelen en configureren op macOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatfuncties** voor profieltype). 

In deze update is er een nieuwe instelling voor Aanmeldingsitems om te bepalen welke apps, bestanden, documenten en mappen worden geopend wanneer een gebruiker zich aanmeldt bij het geregistreerde apparaat. 

Ga naar [Instellingen van apparaatfuncties voor macOS in Intune](../configuration/macos-device-features-settings.md) om de huidige instellingen te zien.

Van toepassing op:  
- macOS

#### <a name="deadlines-replace-engaged-restart-settings-for-windows-update-rings------4464404----------"></a>Deadlines vervangen instellingen voor gepland opnieuw opstarten voor Windows-updateringen   <!-- 4464404        -->
In lijn met recente [wijzigingen in Windows-onderhoud](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903#servicing) ondersteunen de Windows 10-updateringen van Intune nu [instellingen voor deadlines](../protect/windows-update-settings.md). *Deadlines* bepalen wanneer door een apparaat functie-en beveiligingsupdates worden geïnstalleerd.  Op apparaten waarop Windows 10 1903 of hoger wordt uitgevoerd, vervangen *deadlines* de configuraties voor *gepland opnieuw opstarten*.  In de toekomst gaan *deadlines* ook *gepland opnieuw opstarten* in eerdere versies van Windows 10 vervangen.  

Wanneer u geen *deadlines*configureert, blijven apparaten de instellingen voor *gepland opnieuw opstarten* gebruiken. In een toekomstige update gaat [Intune ondersteuning voor gepland opnieuw opstarten echter stopzetten](whats-new.md#plan-for-change-new-windows-updates-settings-in-intune-).  

Plan het *gebruik* van deadlines voor al uw Windows 10-apparaten. Nadat de instellingen voor *deadlines* zijn ingesteld, kunt u de Intune-configuraties voor *gepland opnieuw opstarten* wijzigen in Niet geconfigureerd. Als deze zijn ingesteld op Niet geconfigureerd, stopt Intune het beheer van deze instellingen op apparaten, maar worden de laatste configuraties voor de instelling niet van het apparaat verwijderd. Daarom blijven de laatste configuraties die zijn ingesteld voor *gepland opnieuw opstarten* actief en in gebruik op apparaten totdat deze instellingen worden gewijzigd door een andere methode dan Intune. Later, wanneer de apparaatversie van Windows verandert of wanneer Intune ondersteuning voor *deadlines* uitbreidt naar de Windows-versie van het apparaat, gaat het apparaat de nieuwe instellingen gebruiken, die al aanwezig zijn.

#### <a name="support-for-multiple-microsoft-intune-certificate-connectors--------4704642--------"></a>Ondersteuning voor meerdere Microsoft Intune Certificate Connectors   <!--   4704642      -->
InTune biedt nu ondersteuning voor installatie en gebruik van meerdere [Microsoft Intune Certificate Connectors voor PKCS-bewerkingen](../protect/certficates-pfx-configure.md). Deze wijziging ondersteunt taakverdeling en hoge beschikbaarheid van de connector. Elke connectorinstantie kan certificaataanvragen van Intune verwerken.  Als er geen connector beschikbaar is, blijven andere connectors aanvragen verwerken. 

Als u meerdere connectors wilt gebruiken, hoeft u geen upgrade uit te voeren naar de nieuwste versie van de connectorsoftware.  

#### <a name="new-settings-and-changes-to-existing-settings-to-restrict-features-on-ios-and-macos-devices----4867699-4867709-----"></a>Nieuwe instellingen en wijzigingen in bestaande instellingen om functies op iOS-en macOS-apparaten te beperken <!-- 4867699 4867709   -->
U kunt profielen maken om instellingen te beperken op apparaten waarop iOS en macOS worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** of **macOS** voor platform > **Apparaatbeperkingen**). Deze update bevat onder andere de volgende functies:

- Gebruik in **macOS** > **Apparaatbeperkingen** > **Cloud en opslag** de nieuwe **Handoff**-instellingen om te blokkeren dat gebruikers werk starten op een macOS-apparaat en blijven werken op een ander macOS- of iOS-apparaat.

  Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-macos.md).

- Er zijn enkele wijzigingen in **iOS** > **Apparaatbeperkingen**:

  - **Ingebouwde apps** > **Zoek mijn iPhone (alleen onder supervisie)** : nieuwe instelling die deze functie blokkeert in de functie Zoek mijn app. 
  - **Ingebouwde apps** > **Zoek mijn vrienden (alleen onder supervisie)** : nieuwe instelling die deze functie blokkeert in de functie Zoek mijn app. 
  - **Draadloos** > **Wijziging van Wi-Fi-status (alleen onder supervisie)** : nieuwe instelling die voorkomt dat gebruikers Wi-Fi op het apparaat in- of uitschakelen.
  - **Toetsenbord en woordenboek** > **QuickPath (alleen onder toezicht)** : nieuwe instelling die de QuickPath-functie blokkeert.
  - **Cloud en opslag**: de naam van de term **Voortzetting van activiteit** is gewijzigd in **Handoff**.

  Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:  
- macOS 10.15 of hoger
- iOS 13 en hoger

#### <a name="some-unsupervised-ios-device-restrictions-will-become-supervised-only-with-the-ios-130-release----4867809-----"></a>Sommige iOS-apparaatbeperkingen zonder supervisie worden pas met de release van iOS 13.0 onder supervisie geplaatst <!-- 4867809   -->
In deze update zijn sommige instellingen alleen van toepassing op apparaten met supervisie met de release van iOS 13.0. Als deze instellingen zijn geconfigureerd en toegewezen aan apparaten zonder supervisie vóór de iOS 13.0-release, worden de instellingen nog steeds toegepast op deze apparaten zonder supervisie. Ze zijn ook nog steeds van toepassing nadat de apparaten zijn bijgewerkt naar iOS 13.0. Deze beperkingen worden verwijderd op apparaten zonder supervisie waarvan een back-up is gemaakt en die zijn hersteld. 

Deze instellingen omvatten:

- App Store, documenten bekijken, gamen
  - App Store
  - Expliciete muziek-, podcast- of nieuwsinhoud op iTunes
  - Game Center-vrienden toevoegen
  - Games voor meerdere spelers
- Ingebouwde apps
  - Camera
    - FaceTime
  - Safari
    - Automatisch doorvoeren
- Cloud en opslag
  - Back-up naar iCloud
  - ICloud-documentsynchronisatie blokkeren
  - Synchronisatie van iCloud-sleutelhanger blokkeren

Als u de huidige instellingen wilt zien, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-ios.md).

Van toepassing op:  
- iOS 13.0 en hoger

#### <a name="improved-device-status-for-macos-filevault-encryption-----4944983-----------"></a>Verbeterde apparaatstatus voor macOS FileVault-versleuteling  <!-- 4944983         -->
We hebben een aantal van de [statusberichten](../protect/encryption-monitor.md#device-encryption-status) voor FileVault-versleuteling op macOS-apparaten bijgewerkt.

#### <a name="some-windows-defender-antivirus-scan-settings-in-the-reporting-show-a-failed-status----5119229---"></a>Sommige scaninstellingen voor Windows Defender Antivirus geven in de rapporten de status Mislukt weer <!-- 5119229 -->
In Intune kunt u beleidsregels maken om Windows Defender Antivirus te gebruiken voor het scannen van uw Windows 10-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Apparaatbeperkingen** voor profieltype > **Windows Defender Antivirus**). De rapporten **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd** en **Type systeemscan dat moet worden uitgevoerd** bevatten de status Mislukt, terwijl het in werkelijkheid de status Geslaagd was. 

In deze update is dit opgelost. De instellingen **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd** en **Type systeemscan dat moet worden uitgevoerd** geven nu de status Geslaagd weer wanneer de scans met succes zijn uitgevoerd en geven de status Mislukt weer als de instellingen niet kunnen worden toegepast. 

Zie [Apparaatinstellingen van Windows 10 (en hoger) voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus) voor meer informatie over de instellingen van Windows Defender Antivirus. 

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="default-scope-tags----3702875----"></a>Standaardbereiktags <!-- 3702875  -->
Er is nu een nieuwe ingebouwde standaardbereiktag beschikbaar. Alle niet-getagde Intune-objecten die bereiktags ondersteunen, worden automatisch toegewezen aan de standaardbereiktag. De **standaard**bereiktag wordt toegevoegd aan alle bestaande roltoewijzingen om pariteit met de beheerderservaring te behouden. Als u niet wilt dat een beheerder Intune-objecten met de standaardbereiktag ziet, verwijdert u de standaardbereiktag uit de roltoewijzing. Deze functie is vergelijkbaar met de functie voor beveiligingsbereiken in System Center Configuration Manager. Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) voor meer informatie.

#### <a name="android-enrollment-device-administrator-support----4869749-----"></a>Ondersteuning voor inschrijving van Android-apparaatbeheerder <!-- 4869749   -->
De optie voor inschrijving van Android-apparaatbeheerders is toegevoegd aan de inschrijvingspagina voor Android (**Intune** > **Apparaatinschrijving** > **Android-inschrijving**). Android-apparaatbeheerders worden nog steeds standaard ingeschakeld voor alle tenants.  Zie [Inschrijving van Android-apparaatbeheerders](../enrollment/android-enroll-device-administrator.md) voor meer informatie.

#### <a name="skip-more-screens-in-setup-assistant---4877451----"></a>Meer schermen in de Configuratieassistent overslaan <!--4877451  -->
U kunt Device Enrollment Program-profielen instellen om de volgende schermen van de Configuratieassistent over te slaan:
- Voor iOS
    - Uiterlijk
    - Express-taal
    - Voorkeurstaal
    - Migratie van apparaat naar apparaat
- Voor macOS
    - Schermtijd
    - Touch ID instellen

Zie [Een Apple-inschrijvingsprofiel maken voor iOS ](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) en [Een Apple-inschrijvingsprofiel maken voor macOS ](../enrollment/device-enrollment-program-enroll-macos.md#create-an-apple-enrollment-profile) voor meer informatie over het aanpassen van de Configuratieassistent.

#### <a name="add-a-user-column-to-the-autopilot-device-csv-upload-process----3823054---"></a>Een gebruikerskolom toevoegen aan het CSV-uploadproces van het Autopilot-apparaat <!-- 3823054 -->
U kunt nu een gebruikerskolom toevoegen aan de CSV-upload voor Autopilot-apparaten. Zo kunt u gebruikers bulksgewijs toewijzen op het moment dat u het CSV-bestand importeert. Zie [Windows-apparaten in Intune inschrijven met Windows Autopilot](../enrollment/enrollment-autopilot.md) voor meer informatie.


### <a name="device-management"></a>Apparaatbeheer

#### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>De tijdslimiet voor het automatisch opschonen van apparaten verkorten tot 30 dagen <!--4231059  -->
U kunt de tijdslimiet voor automatische opschoning van apparaten instellen op 30 dagen (in plaats van de vorige limiet van 90 dagen) na de laatste aanmelding. Als u dit wilt doen, gaat u naar **intune** > **apparaten** > regels voor het opschonen**van**apparaten**instellen** > .

#### <a name="build-number-included-on-android-device-hardware-page----4461910-----"></a>Buildnummer opgenomen op de hardwarepagina van het Android-apparaat <!-- 4461910   -->
Een nieuw item op de hardwarepagina voor elk Android-apparaat bevat het buildnummer van het besturingssysteem van het apparaat. Zie [Apparaatdetails weergeven in Intune](../remote-actions/device-inventory.md) voor meer informatie.


<!-- ########################## -->

## <a name="week-of-august-5-2019"></a>Week van 5 augustus 2019

### <a name="zebra-technologies-is-a-supported-oem-for-oemconfig-on-android-enterprise-devices-----4843713---"></a>Zebra Technologies is een ondersteunde OEM voor OEMConfig op Android Enterprise-apparaten  <!-- 4843713 -->

In Intune kunt u apparaatconfiguratieprofielen maken, en instellingen toepassen op Android Enterprise-apparaten met behulp van OEMConfig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **OEMConfig** voor profieltype).

In deze update is Zebra Technologies een ondersteunde OEM (Original Equipment Manufacturer) voor OEMConfig. Zie [Android Enterprise-apparaten gebruiken en beheren met OEMConfig](../configuration/android-oem-configuration-overview.md) voor meer informatie over OEMConfig.

Van toepassing op:  
- Android Enterprise

<!-- ########################## -->

## <a name="week-of-july-22-2019"></a>Week van 22 juli 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="customized-notifications-for-users-and-groups-------16766574------------"></a>Aangepaste meldingen voor gebruikers en groepen    <!-- 16766574          -->
Verzend aangepaste pushmeldingen vanaf de bedrijfsportaltoepassing naar gebruikers met iOS- en Android-apparaten die u met Intune beheert. Deze mobiele pushmeldingen zijn zeer goed met vrije tekst aan te passen en kunnen voor elk doeleinde worden gebruikt. U kunt ze voor verschillende gebruikersgroepen in uw organisatie gebruiken. Zie [aangepaste meldingen](../remote-actions/custom-notifications.md) voor meer informatie.

#### <a name="googles-device-policy-controller-app----3041950----"></a>App Device Policy Controller van Google <!-- 3041950  -->
De app Managed Home Screen biedt nu toegang tot de app Android Device Policy van Google. De app Managed Home Screen is een aangepast startprogramma dat wordt gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) op basis van de kioskmodus voor meerdere apps. U kunt de app Android Device Policy openen of gebruikers naar de app leiden voor ondersteuning en foutopsporing. De opstartmogelijkheid is beschikbaar op het moment dat het apparaat wordt ingeschreven en wordt gekoppeld aan Managed Home Screen. Er zijn geen extra installaties nodig voor het gebruik van deze functionaliteit.

#### <a name="outlook-protection-settings-for-ios-and-android-devices----3212619---"></a>Outlook-beveiligingsinstellingen voor iOS- en Android-apparaten <!-- 3212619 -->
U kunt nu de algemene configuratie-instellingen voor apps en gegevensbeveiliging configureren voor Outlook voor iOS en Android met behulp van besturingselementen voor eenvoudig Intune-beheer zonder apparaatregistratie. De algemene instellingen voor het configureren van apps bieden pariteit met de instellingen die beheerders kunnen inschakelen bij het beheren van Outlook voor iOS en Android op geregistreerde apparaten. Zie [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (Configuratie-instellingen voor apps implementeren voor Outlook voor iOS en Android) voor meer informatie over instellingen in Outlook.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910-eeready---idstaged---"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 eeready   idstaged -->

U kunt configuratieprofielen voor een Windows 10-apparaat maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform > **Toepasbaarheidsregels**). In deze update kunt u een **toepassingsregel** maken, zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Zie [Toepasbaarheidsregels](../configuration/device-profile-create.md#applicability-rules) om een toepasbaarheidsregel toe te voegen.

Van toepassing op: Windows 10 en hoger

#### <a name="use-tokens-to-add-device-specific-information-in-custom-profiles-for-ios-and-macos-devices----3330008----"></a>Tokens gebruiken om apparaatspecifieke informatie toe te voegen aan aangepaste profielen voor iOS- en macOS-apparaten <!-- 3330008  -->
U kunt aangepaste profielen op iOS- en macOS-apparaten gebruiken om instellingen en functies te configureren die niet zijn ingebouwd in Intune (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **IOS** of **macOS** als platform > **Aangepast** voor profieltype). In deze update kunt u tokens toevoegen aan uw `.mobileconfig`-bestanden om apparaatspecifieke informatie toe te voegen. U kunt bijvoorbeeld `Serial Number: {{serialnumber}}` toevoegen aan uw configuratiebestand om het serienummer van het apparaat weer te geven.

Zie [Aangepaste iOS-instellingen](../configuration/custom-settings-ios.md) of [Aangepaste macOS-instellingen](../configuration/custom-settings-macos.md) als u een aangepast profiel wilt maken.

Van toepassing op:
- iOS
- macOS

#### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769-----"></a>Nieuwe configuratieontwerper bij het maken van een OEMConfig-profiel voor Android Enterprise <!-- 3712769   -->
U kunt in Intune een apparaatconfiguratieprofiel maken dat gebruikmaakt van een OEMConfig-app (Apparaatconfiguratie > Profielen > Profiel maken > Android Enterprise als platform > OEMConfig als profieltype). Wanneer u dit doet, wordt er een JSON-editor geopend met een sjabloon en waarden die u kunt wijzigen. 

Deze update bevat een versie van Configuratieontwerper met een verbeterde gebruikerservaring, waarin in de app ingesloten details worden weergegeven, waaronder titels, beschrijvingen en meer. De JSON-editor is nog steeds beschikbaar en toont wijzigingen die u aanbrengt in Configuratieontwerper.

Als u de huidige instellingen wilt bekijken, gaat u naar [Android Enterprise-apparaten gebruiken en beheren met OEMConfig](../configuration/android-oem-configuration-overview.md).

Van toepassing op: Android Enterprise

#### <a name="updated-ui-for-configuring-windows-hello-----4089576--------------"></a>Bijgewerkte gebruikersinterface voor het configureren van Windows Hello  <!-- 4089576            -->
De console waar u [Intune kunt configureren voor het gebruik van Windows Hello voor Bedrijven](../protect/windows-hello.md) is bijgewerkt. Alle configuratie-instellingen zijn nu beschikbaar in hetzelfde deelvenster van de console waar u ondersteuning voor Windows Hello inschakelt. 


#### <a name="intune-powershell-sdk----4924113---"></a>Intune PowerShell SDK <!-- 4924113 --> 
De Intune PowerShell SDK, die ondersteuning biedt voor de Intune API via Microsoft Graph, is bijgewerkt naar versie 6.1907.1.0. De SDK ondersteunt nu het volgende:
- Werkt met Azure Automation.
- Ondersteunt leesbewerkingen ter verificatie voor alleen apps. 
- Ondersteunt beschrijvende namen als aliassen.
- Voldoet aan de naamgevingsconventies voor PowerShell. Specifiek is parameter `PSCredential` (in cmdlet `Connect-MSGraph`) gewijzigd in `Credential`.
- Ondersteunt het handmatig opgeven van de waarde van de `Content-Type`-header bij gebruik van cmdlet `Invoke-MSGraphRequest`.

Zie [PowerShell SDK for Microsoft Intune Graph API](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune) (PowerShell SDK voor Microsoft Intune Graph API) voor meer informatie.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="updates-for-enrollment-restrictions-----2871968---"></a>Updates voor inschrijvingsbeperkingen  <!-- 2871968 -->
Inschrijvingsbeperkingen voor nieuwe tenants zijn bijgewerkt, zodat Android Enterprise-werkprofielen standaard worden toegestaan. Bestaande tenants worden niet gewijzigd. Als u Android Enterprise-werkprofielen wilt gebruiken, moet u [uw Intune-account koppelen aan uw beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md).

#### <a name="ui-updates-for-apple-enrollment-and-enrollment-restrictions---4089575-4089579----"></a>UI-updates voor Apple-inschrijvingen en inschrijvingsbeperkingen <!--4089575, 4089579  -->
De volgende twee processen maken gebruik van een gebruikersinterface in wizardstijl:
- Inschrijving van Apple-apparaten. Zie [iOS-apparaten automatisch inschrijven met het Device Enrollment Program van Apple](../enrollment/device-enrollment-program-enroll-ios.md) voor meer informatie.
- Inschrijvingsbeperkingen maken. Zie [Inschrijvingsbeperkingen instellen](../enrollment/enrollment-restrictions-set.md) voor meer informatie.

#### <a name="handling-pre-configuration-of-corporate-device-identifiers-for-android-q-devices----4711509--idmiss---"></a>Voorbereiding van de configuratie van bedrijfsapparaat-id's voor Android Q-apparaten <!-- 4711509  idmiss -->
In Android Q (v10) verwijdert Google de mogelijkheid voor MDM-agents om op Android-apparaten met verouderd beheer (apparaatbeheerder) informatie over de apparaat-id te verzamelen.  Intune bevat een functie waarmee IT-beheerders [vooraf een lijst met serienummers of IMEI's kunnen configureren](../enrollment/corporate-identifiers-add.md#identify-corporate-owned-devices-with-imei-or-serial-number) om deze apparaten automatisch aan te merken als bedrijfseigendom. Deze functie werkt niet voor Android Q-apparaten die door een apparaatbeheerder worden beheerd.  Ongeacht of het serienummer of IMEI voor het apparaat wordt geüpload, wordt dit tijdens de inschrijving bij Intune altijd als een persoonlijk apparaat beschouwd.  U kunt het eigendom na de inschrijving handmatig overzetten naar het bedrijf.  Dit is alleen van invloed op nieuwe inschrijvingen. Bestaande ingeschreven apparaten worden hierdoor niet beïnvloed.  Android-apparaten die worden beheerd met werkprofielen, worden door deze wijziging niet beïnvloed en blijven werken zoals ze dit momenteel doen.  Ook kunnen Android Q-apparaten die als apparaatbeheerder zijn ingeschreven, niet langer een serienummer of IMEI als apparaateigenschappen rapporteren in de Intune-console.

#### <a name="icons-have-changed-for-android-enterprise-enrollments-work-profile-dedicated-devices-and-fully-managed-devices----4977730---"></a>Voor Android Enterprise zijn enkele pictogrammen gewijzigd (werkprofiel, toegewezen apparaten en volledig beheerde apparaten) <!-- 4977730 -->
De pictogrammen voor Android Enterprise-inschrijvingsprofielen zijn gewijzigd. Als u de nieuwe pictogrammen wilt zien, gaat u naar **Intune** > **Inschrijving** > **Android-inschrijving** > en kijkt u onder **Inschrijvingsprofielen**.


#### <a name="windows-diagnostic-data-collection-change----4113859---"></a>Wijziging in het verzamelen van diagnostische gegevens <!-- 4113859 -->
De standaardwaarde voor het verzamelen van diagnostische gegevens is gewijzigd voor apparaten met Windows 10, versie 1903 en hoger. Vanaf Windows 10 1903 is het verzamelen van diagnostische gegevens standaard ingeschakeld. Diagnostische gegevens van Windows zijn vitale technische gegevens van Windows-apparaten over het apparaat en over hoe Windows en gerelateerde software worden uitgevoerd. Zie [Diagnostische gegevens van Windows in uw organisatie configureren](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization) voor meer informatie. Autopilot-apparaten worden ook ingeschreven voor 'volledige' telemetrie, tenzij dit anders is ingesteld in het Autopilot-profiel met [System/AllowTelemetry](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry).

### <a name="device-management"></a>Apparaatbeheer

#### <a name="improve-device-location---3855417----"></a>Lokalisatie van apparaat verbeteren<!-- 3855417  -->
U kunt inzoomen op de exacte coördinaten van een apparaat met behulp van de actie **Apparaat zoeken**. Zie [Verloren iOS-apparaten zoeken](../remote-actions/device-locate.md) voor meer informatie over het zoeken naar verloren iOS-apparaten.


### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="advanced-settings-for-windows-defender-firewall--public-preview------1311949-------"></a>Geavanceerde instellingen voor Windows Defender Firewall (openbare preview)  <!--  1311949     -->  
Gebruik Intune voor het beheren van [aangepaste firewallregels als onderdeel van een configuratieprofiel voor een apparaat](../protect/endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices) voor eindpuntbeveiliging in Windows 10. Met regels kunt u inkomend en uitgaand gedrag voor toepassingen, netwerkadressen en poorten opgeven. 

#### <a name="updated-ui-for-managing-security-baselines------4091125-------"></a>Bijgewerkte gebruikersinterface voor het beheren van beveiligingsbasislijnen   <!-- 4091125     -->
[Maken en bewerken](../protect/security-baselines.md#create-the-profile) in de Intune-console voor de beveiligingsbasislijnen is bijgewerkt. De wijzigingen zijn onder andere:

Een eenvoudigere wizardstijl die op één blade is samengevoegd. binnen één blade. In dit nieuwe ontwerp wordt niet langer gebruikgemaakt van meerdere blades, waarbij IT-professionals in meerdere, afzonderlijke deelvensters moeten inzoomen.  
U kunt nu toewijzingen maken als onderdeel van het maken en bewerken. Hierdoor hoeft u later geen basislijnen meer toe te voegen. Er is een samenvatting van de instellingen toegevoegd die u kunt bekijken voordat u een nieuwe basislijn maakt of een bestaande regel bewerkt. Tijdens het bewerken toont de samenvatting alleen de lijst met items die zijn ingesteld binnen de categorie met eigenschappen die worden bewerkt.



<!-- ########################## -->

## <a name="week-of-july-15-2019"></a>Week van 15 juli 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="managed-home-screen-and-managed-settings-icons----4918107---"></a>Pictogrammen Managed Home Screen en Beheerde instellingen <!-- 4918107 -->
Het app-pictogram Managed Home Screen en het pictogram **Beheerde instellingen** zijn bijgewerkt. De app Managed Home Screen wordt alleen gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) en die worden uitgevoerd in de kioskmodus voor meerdere apps. Zie [De app Microsoft Managed Home Screen voor Android Enterprise configureren](../apps/app-configuration-managed-home-screen-app.md) voor meer informatie over de app Managed Home Screen.

#### <a name="android-device-policy-on-android-enterprise-dedicated-devices----4918136---"></a>Android Device Policy op toegewezen Android Enterprise-apparaten <!-- 4918136 -->
U kunt de toepassing Android Device Policy openen vanuit het scherm voor het opsporen van fouten in de app Managed Home Screen. De app Managed Home Screen wordt alleen gebruikt voor apparaten die bij Intune zijn ingeschreven als toegewezen Android Enterprise-apparaat (AE) en die worden uitgevoerd in de kioskmodus voor meerdere apps. Zie [De app Microsoft Managed Home Screen voor Android Enterprise](../apps/app-configuration-managed-home-screen-app.md) voor meer informatie.

#### <a name="ios-company-portal-updates----3902931---"></a>Updates voor de iOS-bedrijfsportal <!-- 3902931 -->
De naam van uw bedrijf in prompts van iOS-app-beheer vervangt de huidige tekst 'i.manage.microsoft.com'. Gebruikers zien bijvoorbeeld hun bedrijfsnaam in plaats van 'i.manage.microsoft.com' wanneer ze een iOS-app willen installeren vanuit de bedrijfsportal of wanneer ze beheer van de app toestaan. Dit wordt de komende dagen voor alle klanten uitgebracht.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="manage-filevault-for-macos-------3858502--4557986--1210104----"></a>FileVault voor macOS beheren   <!--  3858502 + 4557986 + 1210104  -->
U kunt Intune gebruiken voor het [beheren van FileVault-versleuteling van sleutels voor macOS-apparaten](../protect/encrypt-devices.md). Gebruik een configuratieprofiel voor apparaten met eindpuntbeveiliging als u een apparaat wilt versleutelen.

De ondersteuning voor FileVault omvat het versleutelen van niet-versleutelde apparaten, borgstelling van de persoonlijke herstelsleutel voor apparaten, automatische of handmatige rotatie van persoonlijke versleutelingssleutels en het ophalen van sleutels voor uw zakelijke apparaten. Eindgebruikers kunnen ook de website van de bedrijfsportal gebruiken om de persoonlijke herstelsleutel voor hun versleutelde apparaten op te halen. 

Het versleutelingsrapport is aangevuld met [informatie over FileVault](../protect/encryption-monitor.md) en informatie over BitLocker, zodat u alle gegevens over de apparaatversleuteling op één plek kunt bekijken. 

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-autopilot-reset-removes-the-devices-primary-user----4156123---"></a>Met Windows Autopilot opnieuw instellen wordt de primaire gebruiker van het apparaat verwijderd <!-- 4156123 -->
Wanneer Autopilot opnieuw instellen op een apparaat wordt gebruikt, wordt de primaire gebruiker van het apparaat verwijderd. De volgende gebruiker die zich na het opnieuw instellen aanmeldt, wordt ingesteld als primaire gebruiker. Deze functie wordt de komende dagen voor alle klanten uitgebracht.

## <a name="week-of-july-8-2019"></a>Week van 8 juli 2019

### <a name="new-office-windows-and-onedrive-settings-in-windows-10-administrative-templates----3510695---"></a>Nieuwe instellingen voor Office, Windows en OneDrive in Windows 10-beheersjablonen <!-- 3510695 -->

In Intune kunt u beheersjablonen maken die het on-premises beheer van het groepsbeleid nabootsen (**Apparaatbeheer** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Beheersjabloon** als profieltype).

Deze update bevat meer instellingen voor Office, Windows en OneDrive die u aan uw sjablonen kunt toevoegen. Met deze nieuwe instellingen kunt u nu meer dan 2500 instellingen configureren die voor 100% op de cloud gebaseerd zijn.

Zie [Windows 10-sjablonen gebruiken voor het configureren van instellingen voor groepsbeleid in Intune](../configuration/administrative-templates-windows.md) voor meer informatie over deze functie.

Van toepassing op: Windows 10 en hoger

## <a name="week-of-july-1-2019"></a>Week van 1 juli, 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="aad-and-app-on-android-enterprise-devices----3574267---"></a>AAD en APP op Android Enterprise-apparaten <!-- 3574267 -->
Bij het onboarden van volledig beheerde Android Enterprise-apparaten registreren gebruikers zich tijdens de eerste installatie van hun nieuwe apparaat (of hun apparaat die naar de fabrieksinstellingen is teruggezet) voortaan bij Azure Active Directory (AAD). Voor een volledig beheerd apparaat was het voorheen zo dat de gebruiker de Microsoft Intune-app na voltooiing van de installatie handmatig moest starten om AAD-registratie te starten. Als de gebruiker nu na de initiële installatie op de startpagina van het apparaat terechtkomt, wordt het apparaat ingeschreven en geregistreerd.

Naast de AAD-updates worden beleidsregels voor Intune-app-beveiliging (APP) voortaan ondersteund op volledig beheerde Android Enterprise-apparaten. Deze functionaliteit wordt beschikbaar tijdens de implementatie. Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](../apps/apps-add-android-for-work.md) voor meer informatie.

## <a name="week-of-june-24-2019"></a>Week van 24 juni 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="configure-which-browser-is-allowed-to-link-to-organization-data----3145939---"></a>Configureren welke browser een koppeling met organisatiegegevens mag maken <!-- 3145939 -->
Met beleidsregels voor Intune-app-beveiliging (APP) op Android- en iOS-apparaten kunt u webkoppelingen van een organisatie overbrengen naar een specifieke browser buiten Intune Managed Browser of Microsoft Edge.  Zie [Wat is beveiligingsbeleid voor apps?](../apps/app-protection-policy.md) voor meer informatie over APP.

#### <a name="all-apps-page-identifies-onlineoffline-microsoft-store-for-business-apps--4089647---"></a>Op de pagina Alle apps worden online/offline Microsoft Store voor zakelijke apps geïdentificeerd<!--4089647 -->
De pagina **Alle apps** bevat nu labels voor het identificeren van MSFB-apps (Microsoft Store for Business) als online- of offline-apps. Elke MSFB-app bevat nu een achtervoegsel voor **Online** of **Offline**. De pagina met app-details bevat ook informatie over het **licentietype** en **ondersteunt de installatie van apparaatcontext** (alleen offline gelicentieerde apps).

#### <a name="company-portal-app-on-windows-shared-devices---4393553---"></a>Bedrijfsportal-app op gedeelde Windows-apparaten <!--4393553 -->
Gebruikers hebben nu toegang tot de Bedrijfsportal-app op gedeelde Windows-apparaten. Eindgebruikers krijgen het label **Gedeeld** op de apparaattegel te zien. Dit geldt voor versie 10.3.45609.0 en hoger van de Windows Bedrijfsportal-app.

#### <a name="view-all-installed-apps-from-new-company-portal-web-page----4224326---"></a>Alle geïnstalleerde apps weergeven op de nieuwe webpagina van de bedrijfsportal <!-- 4224326 -->
De nieuwe pagina **Geïnstalleerde apps** van de website van de bedrijfsportal geeft alle beheerde apps (zowel vereiste als beschikbare) weer die op het apparaat van een gebruiker zijn geïnstalleerd. Naast het type toewijzing kunnen gebruikers de uitgever van de app, de publicatiedatum en de huidige installatiestatus weergeven. Als u geen apps voor uw gebruikers verplicht of beschikbaar hebt gesteld, zien zij het bericht dat er geen bedrijfs-apps zijn geïnstalleerd. Ga naar de [website van de bedrijfsportal](https://portal.manage.microsoft.com) en klik op **Geïnstalleerde apps** om de nieuwe pagina op het web te zien.  

#### <a name="new-view-lets-app-users-see-all-managed-apps-installed-on-device----2352913---"></a>In de nieuwe weergave kunnen app-gebruikers alle beheerde apps zien die op het apparaat zijn geïnstalleerd <!-- 2352913 -->  
De bedrijfsportal voor Windows toont nu alle beheerde apps (zowel vereiste als beschikbare) die op het apparaat van een gebruiker zijn geïnstalleerd. Gebruikers kunnen ook geprobeerde en in behandeling zijnde app-installaties weergeven met de huidige status ervan. Als u geen apps voor uw gebruikers verplicht of beschikbaar hebt gesteld, zien zij het bericht dat er geen bedrijfs-apps zijn geïnstalleerd. Ga naar het navigatievenster in de bedrijfsportal en selecteer **Apps** > **Geïnstalleerde apps** om de nieuwe weergave weer te geven.    

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="configure-settings-for-kernel-extensions-on-macos-devices----2043024---"></a>Instellingen voor kernelextensies configureren op macOS-apparaten <!-- 2043024 -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** kies > **macOS** als platform). Deze update bevat een nieuwe groep instellingen waarmee u kernelextensies op uw apparaten kunt configureren en gebruiken. U kunt specifieke extensies toevoegen, maar ook alle uitbreidingen van een specifieke partner of ontwikkelaar toestaan.

Zie [overzicht van de kernelextensies](../configuration/kernel-extensions-overview-macos.md) en [instellingen voor de kernelextensie](../configuration/kernel-extensions-settings-macos.md) voor meer informatie over deze functie.

Van toepassing op: macOS 10.13.2 en hoger

#### <a name="apps-from-the-store-only-setting-for-windows-10-devices-includes-more-configuration-options----2697002---"></a>Instelling Alleen apps van de Store voor Windows 10-apparaten bevat meer configuratieopties <!-- 2697002 -->
Wanneer u een apparaatbeperkingsprofiel voor Windows-apparaten maakt, kunt u de instelling **Alleen apps van de Store** gebruiken, zodat gebruikers alleen apps van Windows App Store installeren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** voor platform > **Apparaatbeperkingen** voor profieltype). In deze update wordt deze instelling uitgebreid om meer opties te ondersteunen. 

Als u de nieuwe instelling wilt zien, gaat u naar [Apparaatinstellingen voor Windows 10 (en hoger) voor het toestaan of beperken van functies](../configuration/device-restrictions-windows-10.md#app-store).

Van toepassing op: Windows 10 en hoger

#### <a name="deploy-multiple-zebra-mobility-extensions-device-profiles-to-a-device-same-user-group-or-same-devices-group----4089955---"></a>Meerdere apparaatprofielen voor Zebra-mobiliteitsextensies op een apparaat of voor dezelfde gebruikersgroep of groep apparaten implementeren <!-- 4089955 -->
U kunt in Intune Zebra-mobiliteitsextensies (MX) gebruiken in een apparaatconfiguratieprofiel om instellingen aan te passen voor Zebra-apparaten die niet in Intune zijn ingebouwd. Op dit moment kunt u één profiel op één apparaat implementeren. In deze update kunt u meerdere profielen implementeren voor het volgende:
- Dezelfde gebruikersgroep
- Dezelfde groep apparaten
- Eén apparaat

In [Use and manage Zebra devices with Zebra Mobility Extensions in Microsoft Intune](../configuration/android-zebra-mx-overview.md) (Zebra-apparaten gebruiken en beheren met Zebra Mobility Extensions in Microsoft Intune) ziet u hoe u MX in Intune gebruikt.

Van toepassing op: Android

#### <a name="some-kiosk-settings-on-ios-devices-are-set-using-block-replacing-allow----4404075----"></a>Sommige kioskinstellingen op iOS-apparaten worden ingesteld met behulp van Blokkeren, waardoor Toestaan wordt vervangen <!-- 4404075  -->
Wanneer u een apparaatbeperkingsprofiel maakt op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Kiosk**), stelt u de **automatisch vergrendeling**, **schakelaar voor het belsignaal**, **schermrotatie**, **schermsluimerknop** en **volumeknoppen** in. 

In deze update gaat het om de waarden **Blokkeren** (blokkeert de functie) of **Niet geconfigureerd** (staat de functie toe). Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies](../configuration/device-restrictions-ios.md#kiosk). 

Van toepassing op: iOS

#### <a name="use-face-id-for-password-authentication-on-ios-devices----4490704---"></a>Face ID voor wachtwoordverificatie op iOS-apparaten gebruiken <!-- 4490704 -->
Wanneer u een apparaatbeperkingsprofiel voor iOS-apparaten maakt, kunt u een vingerafdruk als wachtwoord gebruiken. In deze update is met de instellingen voor vingerafdrukwachtwoorden ook gezichtsherkenning mogelijk (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** als platform > **Apparaatbeperkingen** als profieltype > **Wachtwoord**). Als gevolg hiervan zijn de volgende instellingen gewijzigd:

- **Ontgrendelen met vingerafdruk** is nu **Touch ID en Face ID ontgrendelen**.
- **Wijziging van vingerafdruk (alleen onder supervisie)** is nu **Aanpassing van Touch ID en Face ID (alleen onder supervisie)** .

Face ID is beschikbaar in iOS 11.0 en hoger. Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md#password).

Van toepassing op: iOS

#### <a name="restricting-gaming-and-app-store-features-on-ios-devices-is-now-dependent-on-ratings-region----4593948---"></a>Het beperken van gaming- en App Store-functies op iOS-apparaten is nu afhankelijk van de regio voor restricties <!-- 4593948 -->
Op iOS-apparaten kunt u functies toestaan of beperken met betrekking tot gaming, de App Store en het weergeven van documenten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documentweergave, gaming**). U kunt ook de classificatieregio kiezen, zoals de Verenigde Staten. 

In deze update wordt de functie **Apps** een onderliggend element van **Regio voor restricties** en is deze afhankelijk van **Regio voor restricties**. Als u de instellingen wilt bekijken, gaat u naar [iOS-apparaatinstellingen voor het toestaan of beperken van functies met behulp van Intune](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-autopilot-support-for-hybrid-azure-ad-join----4809146--"></a>Ondersteuning voor Windows Autopilot voor Hybrid Azure AD Join <!-- 4809146-->
Windows Autopilot voor bestaande apparaten ondersteunt nu Hybrid Azure AD Join (naast de bestaande ondersteuning voor Azure AD Join). Is van toepassing op Windows 10-apparaten, versie 1809 en hoger. Zie [Windows Autopilot voor bestaande apparaten](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) voor meer informatie.



### <a name="device-management"></a>Apparaatbeheer

#### <a name="see-the-security-patch-level-for-android-devices----4461911---"></a>Het niveau van de beveiligingspatch voor Android-apparaten bekijken <!-- 4461911 -->
U kunt nu het niveau van de beveiligingspatch voor Android-apparaten bekijken. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Hardware**.
Het patchniveau wordt weergegeven in het gedeelte **Besturingssysteem**.

#### <a name="assign-scope-tags-to-all-managed-devices-in-a-security-group----3173810---"></a>Bereiktags toewijzen aan alle beheerde apparaten in een beveiligingsgroep <!-- 3173810 -->
U kunt nu bereiktags toewijzen aan een beveiligingsgroep waarbij ook alle apparaten in de beveiligingsgroep aan die bereiktags worden gekoppeld. De bereiktag wordt ook aan alle apparaten in deze groepen toegewezen. De bereiktags die worden ingesteld met deze functie, vervangen de bereiktags die zijn ingesteld met de huidige stroom voor apparaatbereiktags. Zie [RBAC en bereiktags gebruiken voor gedistribueerde IT](scope-tags.md) voor meer informatie.

### <a name="device-security"></a>Apparaatbeveiliging

#### <a name="use-keyword-search-with-security-baselines-------"></a>Zoekopdrachten met trefwoorden gebruiken met Beveiligingsbasislijnen <!--  -->
Wanneer u [beveiligingsbasislijnprofielen](../protect/security-baselines.md#create-the-profile) maakt of bewerkt, kunt u trefwoorden opgeven in de nieuwe *zoekbalk* om de beschikbare groepen instellingen te filteren op degene die de zoekcriteria bevatten. 

#### <a name="the-security-baselines-feature-is-now-generally-available-----3785395---"></a>De functie Beveiligingsbasislijnen is nu algemeen beschikbaar  <!-- 3785395 -->
Voor de functie **Beveiligingsbasislijnen** is de previewfase beëindigd. De functie is nu algemeen beschikbaar.  Dit betekent dat de functie gereed is voor gebruik in productie. De afzonderlijke basislijnsjablonen blijven mogelijk echter wel in de previewfase, en worden geëvalueerd en op basis van hun eigen planningen algemeen uitgebracht.

#### <a name="the-mdm-security-baseline-template-is-now-generally-available------3794072-4217151--3534649---"></a>De sjabloon MDM-beveiligingsbasislijn is algemeen beschikbaar   <!-- 3794072, 4217151,  3534649 -->
Voor de sjabloon MDM-beveiligingsbasislijn is de previewfase beëindigd. De functie is nu algemeen beschikbaar. De algemeen beschikbare sjabloon wordt geïdentificeerd als **MDM-beveiligingsbasislijn voor mei 2019**.  Dit is een nieuwe sjabloon en geen upgrade van de previewversie.  Voor een nieuwe sjabloon moet u de [instellingen die deze bevat](../protect/security-baseline-settings-mdm.md), controleren en vervolgens nieuwe profielen maken om de sjabloon voor uw apparaat te implementeren. Andere beveiligingsbasislijnsjablonen blijven mogelijk in de previewfase. Zie [Beschikbare beveiligingsbasislijnen](../protect/security-baselines.md#available-security-baselines) voor een lijst met beschikbare basislijnen.  

De nieuwe sjabloon *MDM-beveiligingsbasislijn voor mei 2019* bevat de twee instellingen die onlangs zijn aangekondigd in het artikel In ontwikkeling:  
- Vergrendeling boven: Door spraak geactiveerde apps vanaf een vergrendeld scherm  
- DeviceGuard: Gebruik Beveiliging op basis van virtualisatie (VBS) als de apparaten de volgende keer opnieuw worden opgestart.  

Voor de *MDM-beveiligingsbasislijn voor mei 2019* geldt dat er ook een aantal nieuwe instellingen is toegevoegd, andere eruit zijn verwijderd en de standaardwaarde van één instelling is gewijzigd. Zie **wat is er gewijzigd in de nieuwe sjabloon** voor een uitgebreide lijst met de wijzigingen van de previewversie (nu algemeen uitgebracht).

#### <a name="security-baseline-versioning-----3194322---"></a>Versiebeheer van beveiligingsbasislijnen  <!-- 3194322 -->
Beveiligingsbasislijnen voor versiebeheer van de ondersteuning voor Intune. Nu er nieuwe versies van elke beveiligingsbasislijn worden uitgebracht, kunt u dankzij deze ondersteuning uw bestaande beveiligingsbasislijnprofielen bijwerken voor gebruik van de nieuwere basislijnversie, zonder dat u zelf opnieuw een geheel nieuwe basislijn hoeft te maken en te implementeren. Daarnaast kunt u in de Intune-console informatie bekijken over elke basislijn, zoals het aantal afzonderlijke profielen die gebruikmaken van de basislijn, hoeveel verschillende basislijnversies er door uw profielen worden gebruikt en wanneer de meest recente release van een bepaalde beveiligingbasislijn is geweest.  Zie **Beveiligingsbasislijnen** voor meer informatie.

#### <a name="the-use-security-keys-for-sign-in-setting-has-moved-----4501151---"></a>De instelling Beveiligingssleutels gebruiken voor aanmelden is verplaatst  <!-- 4501151 -->
De instelling voor apparaatconfiguratie voor identiteitsbeveiliging met de naam **Beveiligingssleutels gebruiken voor aanmelden** is niet meer aanwezig als subinstelling van *Windows Hello voor Bedrijven configureren*. Het is nu een instelling op het hoogste niveau die altijd beschikbaar is, ook als u het gebruik van Windows Hello voor Bedrijven niet inschakelt. Zie [Identity Protection](../protect/identity-protection-windows-settings.md) voor meer informatie.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="new-permissions-for-assigned-group-admins------4504437-----"></a>Nieuwe machtigingen voor toegewezen groepsbeheerders   <!-- 4504437   -->
De in Intune ingebouwde rol School Administrator bevat nu machtigingen voor maken, lezen, bijwerken en verwijderen (CRUD-machtigingen) voor beheerde apps. Deze update betekent dat als u in Intune for Education bent toegewezen als groepsbeheerder, u voortaan het iOS MDM-pushcertificaat, iOS MDM-servertokens en iOS VPP-tokens kunt maken, weergeven, bijwerken en verwijderen, in combinatie met [alle bestaande machtigingen die u hebt](https://docs.microsoft.com/intune-education/group-admin-delegate#group-admin-permissions). Als u een van deze acties wilt uitvoeren, gaat u naar **Tenantinstellingen** > **iOS-apparaatbeheer**.  

#### <a name="applications-can-use-the-graph-api-to-call-read-operations-without-user-credentials----4655885---"></a>Toepassingen kunnen gebruikmaken van de Graph API om leesbewerkingen aan te roepen zonder gebruikersreferenties <!-- 4655885 -->
Toepassingen kunnen met app-identiteiten Intune Graph API-leesbewerkingen aanroepen, zonder dat er gebruikersreferenties nodig zijn. Zie [Working with Intune in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/intune-graph-overview?view=graph-rest-1.0) (Werken met intune in Microsoft Graph) voor meer informatie over het openen van de Microsoft Graph API voor Intune.

#### <a name="apply-scope-tags-to-microsoft-store-for-business-apps----4392555---"></a>Bereiktags toepassen op Microsoft Store voor Bedrijven-apps <!-- 4392555 -->
U kunt voortaan bereiktags toepassen op Microsoft Store voor Bedrijven-apps. Zie [Use role-based access control and scope tags for distributed IT](scope-tags.md) (Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT) voor meer informatie over bereiktags.

## <a name="week-of-june-17-2019"></a>Week van 17 juni 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="new-features-in-microsoft-intune-app"></a>Nieuwe functies in Microsoft Intune-app
We hebben nieuwe functies toegevoegd aan de Microsoft Intune-app (preview) voor Android. Gebruikers op volledig beheerde Android-apparaten kunnen nu:  

* De apparaten weergeven en beheren die zij hebben ingeschreven via de Intune-bedrijfsportal of de Microsoft Intune-app.    
* Contact opnemen met hun organisatie voor ondersteuning.    
* Feedback naar Microsoft sturen.    
* Algemene voorwaarden bekijken als deze zijn ingesteld door hun organisatie.    

## <a name="week-of-june-10-2019"></a>Week van 10 juni 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="new-sample-apps-showing-intune-sdk-integration-available-on-github----2653471---"></a>Er zijn nieuwe voorbeeld-apps met Intune SDK-integratie beschikbaar op GitHub <!-- 2653471 -->
Met het GitHub-account msintuneappsdk zijn nieuwe voorbeeldtoepassingen toegevoegd voor iOS (Swift), Android, Xamarin.iOS, Xamarin Forms en Xamarin.Android. Deze apps zijn bedoeld als aanvulling op onze bestaande documentatie en demonstraties van hoe u de Intune APP SDK kunt integreren in uw eigen mobiele apps. Als u als app-ontwikkelaar aanvullende begeleiding bij de Intune SDK nodig hebt, raadpleegt u de volgende gekoppelde voorbeelden:
- [Chatr](https://github.com/msintuneappsdk/Chatr-Sample-Intune-iOS-App): een systeemeigen iOS (Swift)-berichtenapp die gebruikmaakt van de Azure Active Directory Authentication Library (ADAL) voor verificatie via een broker.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Android-App): een systeemeigen Android-app voor takenlijsten die gebruikmaakt van ADAL voor verificatie via een broker.
- [Taskr](https://github.com/msintuneappsdk/Taskr-Sample-Intune-Xamarin-Android-Apps): een Xamarin.Android-app voor takenlijsten die gebruikmaakt van ADAL voor verificatie via een broker. Deze opslagplaats bevat ook de Xamarin.Forms-app.
- [Voorbeeld-app voor Xamarin.iOS](https://github.com/msintuneappsdk/sample-intune-xamarin-ios): een barebones Xamarin.iOS-voorbeeld-app.

## <a name="week-of-may-27-2019"></a>Week van 27 mei 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="reporting-for-potentially-harmful-apps-on-android-devices----4223162---"></a>Rapportage voor mogelijk schadelijke apps op Android-apparaten <!-- 4223162 -->
Intune biedt nu aanvullende rapportagegegevens over mogelijk schadelijke apps op Android-apparaten. 

## <a name="week-of-may-20-2019"></a>Week van 20 mei 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="windows-company-portal-app----3316993---"></a>Windows-bedrijfsportal-app <!-- 3316993 -->
De Windows-bedrijfsportal-app heeft nu een nieuwe pagina met het label **Apparaten**. Op de pagina **Apparaten** staan de eindgebruikers van alle ingeschreven apparaten. Gebruikers zien deze wijziging in de bedrijfsportal als ze versie 10.3.4291.0 of hoger gebruiken. Voor informatie over het configureren van de bedrijfsportal-app, ziet u [How to configure the Microsoft Intune Company Portal app](../apps/company-portal-app.md) (De app Microsoft Intune-bedrijfsportal configureren).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="autopilot-device-orderid-attribute-name-changed-to-group-tag----4659453---"></a>De kenmerknaam OrderID voor Autopilot-apparaten is gewijzigd in Groepstag <!-- 4659453 -->

Voor een meer intuïtieve benadering is de kenmerknaam **OrderID** voor Autopilot-apparaten gewijzigd in **Groepstag**. Als u CSV's gebruikt voor het uploaden van Autopilot-apparaatgegevens, moet u Groepstag als kolomkop gebruiken en niet OrderID.  

## <a name="week-of-may-13-2019"></a>Week van 13 mei 2019 

### <a name="app-management"></a>Appbeheer

#### <a name="intune-policies-update-authentication-method-and-company-portal-app-installation-----1927359----"></a>Intune-beleid werkt de verificatiemethode en installatie van de Bedrijfsportal-app bij  <!-- 1927359  -->
Intune biedt geen ondersteuning meer voor de Bedrijfsportal wanneer deze handmatig door eindgebruikers uit de appstore wordt geïnstalleerd op apparaten die al met behulp van Configuratieassistent zijn ingeschreven via een van de Apple-registratiemethoden voor bedrijfsapparaten. Deze wijziging is alleen relevant wanneer u tijdens de inschrijving verifieert met Apple Setup Assistant. Deze wijziging is eveneens alleen van invloed op iOS-apparaten die zijn ingeschreven via:  
* Apple Configurator

* Apple Business Manager

* Apple School Manager

* Apple Device Enrollment Program (DEP)

Als gebruikers de Bedrijfsportal-app installeren uit de App Store en vervolgens apparaten via de app proberen te registreren, treedt er een foutmelding op. Er wordt van uitgegaan dat deze apparaten de Bedrijfsportal alleen gebruiken wanneer het automatisch door Intune tijdens de registratie is gepusht. Inschrijvingsprofielen in Intune in de Azure-portal worden bijgewerkt zodat u kunt opgeven hoe apparaten zich verifiëren en hoe zij de Bedrijfsportal-app ontvangen. Als u wilt dat uw DEP-apparaatgebruikers de Bedrijfsportal hebben, moet u uw voorkeuren in een inschrijvingsprofiel opgeven. 

Bovendien wordt het scherm **Uw apparaat identificeren** in de Bedrijfsportal-app van iOS binnenkort niet meer gebruikt. Beheerders die voorwaardelijke toegang willen inschakelen of bedrijfs-apps willen implementeren moeten daarom het DEP-inschrijvingsprofiel bijwerken. Deze vereiste geldt alleen als de DEP-inschrijving wordt geverifieerd met Configuratieassistent. In dat geval moet u de Bedrijfsportal naar het apparaat pushen. Hiervoor kiest u **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijfprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > stel **Bedrijfsportal installeren** in op **Ja**.

Als u de Bedrijfsportal wilt installeren op DEP-apparaten die al zijn ingeschreven, gaat u naar Intune > Client-apps en pusht u de app als beheerde app met app-configuratiebeleid. 

#### <a name="configure-how-end-users-update-a-line-of-business-lob-app-using-an-app-protection-policy----3568384---"></a>Configureren hoe eindgebruikers een LOB-app (Line-Of-Business) bijwerken met behulp van een beveiligingsbeleid voor apps <!-- 3568384 -->
U kunt nu configureren waar uw eindgebruikers een bijgewerkte versie van een LOB-app (Line-Of-Business) kunnen downloaden. Eindgebruikers zien deze functie in het dialoogvenster **minimale app-versie** van de functie voor voorwaardelijk starten, waarin eindgebruikers wordt gevraagd om bij te werken naar een minimale versie van de LOB-app. U moet deze informatie opgeven als onderdeel van uw het beveiligingsbeleid voor uw LOB-app (APP). Deze functie is beschikbaar voor iOS en Android. Voor iOS vereist deze functie dat de app is geïntegreerd (of verpakt met behulp van het wrapping-programma) met de Intune SDK voor iOS versie 10.0.7 of hoger. Voor Android vereist deze functie de meest recente versie van de Bedrijfsportal. Als u wilt configureren hoe een eindgebruiker een LOB-app kan bijwerken, moet er configuratiebeleid voor een beheerde app worden verzonden naar de app met de sleutel `com.microsoft.intune.myappstore`. De verzonden waarde bepaalt uit welke store de eindgebruiker de app kan downloaden. Als de app wordt geïmplementeerd via de Bedrijfsportal-app, moet de waarde `CompanyPortal` zijn. Voor iedere andere store moet u een volledige URL opgeven.

#### <a name="intune-management-extension-powershell-scripts-----3734186----"></a>Intune-beheerextensie voor PowerShell-scripts  <!-- 3734186  -->
U kunt configureren dat PowerShell-scripts worden uitgevoerd met de beheerdersbevoegdheden van de gebruiker op het apparaat. Zie [PowerShell-scripts op Windows 10-apparaten gebruiken in Intune](../apps/intune-management-extension.md) en [Win32 app management](../apps/app-management.md) (Beheer van Win32-apps) voor meer informatie.

#### <a name="android-enterprise-app-management----4459905---"></a>Beheer van Android Enterprise-apps <!-- 4459905 -->
Om het eenvoudiger te maken voor IT-beheerders om Android Enterprise-beheer te configureren en gebruiken, voegt Intune automatisch vier veelgebruikte Android Enterprise apps toe aan de beheerconsole van Intune. Het betreft de volgende vier Android Enterprise-apps:

- **[Microsoft Intune](https://play.google.com/store/apps/details?id=com.microsoft.intune)** : wordt gebruikt voor scenario's met volledig beheer door Android Enterprise.
- **[Microsoft Authenticator](https://play.google.com/store/apps/details?id=com.azure.authenticator)** : om u aan te melden bij uw accounts als u verificatie in twee stappen gebruikt.
- **[Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)** : wordt gebruikt voor beleidsregels voor app-beveiliging (APP) en werkprofielscenario's van Android Enterprise.
- [Managed Home Screen](https://play.google.com/store/apps/details?id=com.microsoft.launcher.enterprise): wordt gebruikt voor toegewezen/kiosk-scenario's van Android Enterprise.

Eerder moesten IT-beheerders deze apps als onderdeel van de installatie handmatig zoeken en goedkeuren in de [beheerde Google Play Store](https://play.google.com/store/apps). Met deze wijziging worden deze eerdere handmatige stappen weggenomen om het gemakkelijker en sneller te maken voor klanten om Android Enterprise-beheer te gebruiken.

Deze vier apps worden automatisch toegevoegd aan de lijst met Intune-apps van beheerders op het moment dat ze hun Intune-tenant voor het eerst verbinden met de beheerde Google Play Store. Zie [Uw Intune-account verbinden met uw Beheerde Google Play-account](../enrollment/connect-intune-android-enterprise.md) voor meer informatie. Beheerders die hun tenant al hebben verbonden of die al gebruikmaken van Android Enterprise hoeven niets te doen. Zeven dagen na het voltooien van de implementatie van de service-update van mei 2019 zijn deze vier apps automatisch beschikbaar.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune-----1533038---"></a>Bijgewerkte PFX-certificaatconnector voor Microsoft Intune  <!-- 1533038 -->
We hebben een update uitgebracht voor de [PFX Certificate Connector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors) die een oplossing biedt voor een probleem waarbij bestaande PFX-certificaten steeds opnieuw worden verwerkt. Hierdoor stopt de connector met het verwerken van nieuwe aanvragen.

#### <a name="intune-security-tasks-for-defender-atp-in-public-preview--------3208597---"></a>Intune-beveiligingstaken voor Defender ATP (in openbare preview)     <!-- 3208597 -->
In de openbare preview-versie kunt u Intune gebruiken voor het beheren van [beveiligingstaken voor Microsoft Defender Advanced Threat Protection (ATP)](../protect/atp-manage-vulnerabilities.md). Door deze integratie met ATP wordt er een op risico's gebaseerde aanpak voor het detecteren, classificeren en oplossen van beveiligingsproblemen en onjuiste configuraties van eindpunten toegevoegd, terwijl er ook minder tijd zit tussen het detecteren en oplossen van beveiligingsproblemen.

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---idstaged--"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt <!-- 3617671   idstaged-->
Veel apparaten met Windows 10 en hoger hebben TPM-chipsets (Trusted Platform Module). Deze update bevat een nieuwe nalevingsinstelling die de versie van de TPM-chip in het apparaat controleert. 

Deze instelling wordt beschreven in [Instellingen voor nalevingsbeleid voor apparaten met Windows 10 en later](../protect/compliance-policy-create-windows.md#device-security).

Van toepassing op: Windows 10 en hoger

#### <a name="prevent-end-users-from-modifying-their-personal-hotspot-and-disable-siri-server-logging-on-ios-devices----4097904-----"></a>Voorkomen dat gebruikers hun persoonlijke hotspot wijzigen en logboekregistratie van Siri-server op iOS-apparaten uitschakelen <!-- 4097904   -->  
U maakt een profiel met apparaatbeperkingen op het iOS-apparaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen die u kunt configureren:

- **Ingebouwde apps**: logboekregistratie op de server voor Siri-opdrachten
- **Draadloos**: wijzing van persoonlijke hotspot door gebruiker (alleen onder supervisie)

Als u deze instellingen wilt zien, gaat u naar [ingebouwde app-instellingen voor iOS](../configuration/device-restrictions-ios.md#built-in-apps) en [draadloze instellingen voor iOS](../configuration/device-restrictions-ios.md#wireless).

Van toepassing op: iOS 12.2 en nieuwer

#### <a name="new-classroom-app-device-restriction-settings-for-macos-devices----4097905-----"></a>Nieuwe instellingen voor apparaatbeperkingen voor Klaslokaal-app op macOS-apparaten <!-- 4097905   --> 
U kunt apparaatconfiguratieprofiel voor macOS-apparaten maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Deze update bevat nieuwe instellingen voor de Classroom-app, de optie om schermopnamen te blokkeren en de optie om de iCloud-fotobibliotheek uit te schakelen.

Als u de huidige instellingen wilt zien, gaat u naar [macOS-apparaatinstellingen voor het toestaan of beperken van functies met Intune](../configuration/device-restrictions-macos.md).

Is van toepassing op: macOS

#### <a name="the-ios-password-to-access-app-store-setting-is-renamed---4557891----"></a>De naam van het iOS-wachtwoord voor toegang tot App Store-instellingen is gewijzigd<!-- 4557891  -->
De naam van de instelling **Wachtwoord voor toegang tot de App Store** is gewijzigd in **iTunes Store-wachtwoord vereisen voor alle aankopen** (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documenten bekijken, gamen**).

Als u de beschikbare instellingen wilt zien, gaat u naar [App Store, documenten bekijken, gamen](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

Van toepassing op: iOS

#### <a name="microsoft-defender-advanced-threat-protection--baseline--preview------3754134---"></a>Microsoft Defender Advanced Threat Protection-basislijn (preview)  <!--  3754134 -->
We hebben een preview van een basislijn voor beveiliging toegevoegd voor [Microsoft Defender Advanced Threat Protection](../protect/security-baseline-settings-defender-atp.md)-instellingen. Deze basislijn is beschikbaar als uw omgeving voldoet aan de vereisten voor het gebruik van [Microsoft Defender Advanced Threat Protection](../protect/advanced-threat-protection.md#prerequisites).

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="windows-enrollment-status-page-esp-is-now-generally-available----3605348---"></a>Pagina Status van inschrijving is nu algemeen beschikbaar <!-- 3605348 -->
De pagina Status van inschrijving is nu uit preview en algemeen beschikbaar. Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.


#### <a name="intune-user-interface-update---autopilot-enrollment-profile-creation-----4593669---"></a>Update van Intune-gebruikersinterface - Autopilot-inschrijvingsprofiel maken  <!-- 4593669 -->
De gebruikersinterface voor het maken van een Autopilot-inschrijvingsprofiel is bijgewerkt om deze in lijn te brengen met de stijlen van de Azure-gebruikersinterface. Zie [Een Autopilot-inschrijvingsprofiel maken](../enrollment/enrollment-autopilot.md#create-an-autopilot-deployment-profile) voor meer informatie. Binnenkort worden ook andere Intune-scenario's bijgewerkt naar deze nieuwe stijl voor de gebruikersinterface.

#### <a name="enable-autopilot-reset-for-all-windows-devices----4225665---"></a>Autopilot opnieuw instellen voor alle Windows-apparaten inschakelen <!-- 4225665 -->
Autopilot opnieuw instellen werkt nu voor alle Windows-apparaten, ook als deze niet zijn geconfigureerd voor het gebruik van de pagina Status van inschrijving. Als er tijdens de eerste apparaatregistratie geen pagina voor de status van inschrijving is geconfigureerd voor het apparaat, wordt op het apparaat direct het bureaublad weergegeven na het aanmelden. Het duurt maximaal acht uur totdat de synchronisatie is voltooid en het apparaat als compatibel wordt weergegeven in Intune. Zie [Reset devices with remote Windows Autopilot Reset](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-reset-remote) (Apparaten op afstand opnieuw instellen met Autopilot opnieuw instellen van Windows) voor meer informatie.

#### <a name="exact-imei-format-not-required-when-searching-all-devices---30407680---"></a>Exacte IME-indeling niet vereist bij het zoeken naar alle apparaten <!--30407680 -->
U hoeft geen spaties op te nemen in IMEI-nummers wanneer u zoekt met **Alle apparaten**.

#### <a name="deleting-a-device-in-the-apple-portal-will-be-reflected-in-the-intune-portal---2489996---"></a>Verwijderen van apparaat in de Apple-portal wordt doorgevoerd in de Intune-portal <!--2489996 -->
Als een apparaat wordt verwijderd uit de portal van het Device Enrollment Program van Apple of van Apple Business Manager, wordt het apparaat bij de volgende synchronisatie automatisch verwijderd uit Intune.

### <a name="the-enrollment-status-page-now-tracks-win32-apps----2714451---"></a>Op de pagina Status van inschrijving worden nu Win32-apps bijgehouden <!-- 2714451 -->
Dit is alleen van toepassing op apparaten met Windows 10 versie 1903 en hoger. Raadpleeg [Een pagina voor de status van de inschrijving instellen](../enrollment/windows-enrollment-status.md) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="reset-and-wipe-devices-in-bulk-by-using-the-graph-api----3295288---"></a>Apparaten in bulk opnieuw instellen en wissen met behulp van de Graph API <!-- 3295288 -->
U kunt nu in één bulkbewerking tot wel 100 apparaten opnieuw instellen en wissen met behulp van de Graph API.


### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="the-encryption-report-is-out-of-public-preview------4587546--------"></a>Het rapport Versleuteling is uit openbare preview   <!-- 4587546      -->
Het [rapport voor BitLocker- en apparaatversleuteling](../protect/encryption-monitor.md) is nu algemeen beschikbaar en maakt geen deel meer uit van de openbare preview. 

<!-- ########################## -->

#### <a name="outlook-signature-and-biometric-settings-for--ios-and-android-devices----4050557---"></a>Outlook-handtekening en biometrische instellingen voor iOS- en Android-apparaten <!-- 4050557 -->
U kunt nu opgeven of de standaardhandtekening moet worden ingeschakeld in Outlook voor iOS- en Android-apparaten. Bovendien kunt u eventueel toestaan dat gebruikers de biometrische instelling wijzigen in Outlook voor iOS.

## <a name="week-of-may-6-2019"></a>Week van 6 mei 2019 

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="network-access-control-nac-support-for-f5-access-for-ios-devices----4500808---"></a>Ondersteuning voor netwerktoegangsbeheer (NAC) voor F5 Access voor iOS-apparaten <!-- 4500808 -->

F5 heeft een update voor BIG-IP 13 uitgebracht waardoor de NAC-functionaliteit is toegestaan voor F5-toegang op iOS in Intune. Om deze functie te gebruiken, moet u ook het volgende doen:

- Werk BIG-IP bij naar 13.1.1.5, vernieuwen. BIG-IP 14 wordt niet ondersteund.
- Integreer BIG-IP met Intune voor NAC. Stappen in [Overzicht: APM configureren voor apparaatpostuurcontroles met eindpuntbeheersystemen](https://techdocs.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html).
- Schakel de instelling **Netwerktoegangsbeheer (NAC) inschakelen** in het VPN-profiel in Intune in.

Ga naar [VPN-instellingen configureren op iOS-apparaten](../configuration/vpn-settings-ios.md) om de beschikbare instelling te zien.

Van toepassing op: iOS

#### <a name="updated-pfx-certificate-connector-for-microsoft-intune----doc-vso-1521237----"></a>Bijgewerkte PFX-certificaatconnector voor Microsoft Intune <!-- doc-vso 1521237  -->  
We hebben een update uitgebracht voor de [PFX-certificaatconnector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors), waardoor de polling-interval wordt verlaagd van 5 minuten naar 30 seconden.

## <a name="week-of-april-22-2019"></a>Week van 22 april 2019

### <a name="use-compliance-manager-to-create-assessments-for-microsoft-intune---4404750---"></a>Met behulp van Conformiteitsmanager een evaluatie voor Microsoft Intune maken<!-- 4404750 -->

[Conformiteitsmanager](https://servicetrust.microsoft.com/ComplianceManager) (hiermee opent u een andere Microsoft-website) is een hulpprogramma voor op werkstromen gebaseerde risicoanalyses in Microsoft Service Trust Portal. Hiermee kunt u activiteiten van uw organisatie op het gebied van naleving van regelgeving met betrekking tot Microsoft-services bijhouden, toewijzen en verifiëren. U kunt uw eigen nalevingsevaluatie maken met Office 365, Azure, Dynamics, Professional-Services en Intune. Intune heeft twee evaluaties beschikbaar - FFIEC en AVG.

Met Conformiteitsmanager kunt u uw inspanningen richten door besturingselementen in te delen: besturingselementen die worden beheerd door Microsoft en besturingselementen die worden beheerd door uw organisatie. U kunt de evaluaties uitvoeren en deze vervolgens exporteren en afdrukken.

[FFIEC-compliance (FFIEC: Federal Financial Institutions Examination Council)](https://www.microsoft.com/trustcenter/compliance/FFIEC) (hiermee opent u een andere Microsoft-website) is een verzameling standaarden voor internetbankieren die is uitgegeven door FFIEC. Het is de meest aangevraagde evaluatie voor financiële instellingen die gebruikmaken van Intune. Deze biedt een interpretatie van de wijze waarop u met behulp van Intune kunt voldoen aan de FFIEC-richtlijnen voor cyberbeveiliging met betrekking tot workloads in de openbare cloud. De FFIEC-evaluatie van Intune is de tweede FFIEC-evaluatie in Conformiteitsmanager.

In het volgende voorbeeld ziet u de indeling van FFIEC-besturingselementen. Microsoft gaat over 64-besturingselementen. U bent verantwoordelijk voor de resterende 12 besturingselementen.

![Bekijk een voorbeeld van een Intune-evaluatie voor FFIEC, met inbegrip van de acties van de klant en van Microsoft](./media/whats-new/intune-ffiec-assessment-status.png)

[AVG (Algemene Verordening Gegevensbescherming)](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-overview) (hiermee opent u een andere Microsoft-website) is een wet van de Europese Unie (EU) waarmee de rechten van personen en hun gegevens worden beschermd. De AVG is de meest aangevraagde evaluatie om te voldoen aan privacy-regelgeving. 

In het volgende voorbeeld ziet u de indeling van AVG-besturingselementen. Microsoft gaat over 49-besturingselementen. U bent verantwoordelijk voor de resterende 66 besturingselementen.

![Bekijk een voorbeeld van een Intune-evaluatie voor AVG, met inbegrip van de acties van de klant en van Microsoft](./media/whats-new/intune-assessment-status.png)

## <a name="week-of-april-15-2019"></a>Week van 15 april 2019

### <a name="app-management"></a>Appbeheer

#### <a name="openssl-encryption-for-android-app-protection-policies----3747362---"></a>OpenSSL-versleuteling voor app-beveiligingsbeleid voor Android <!-- 3747362 -->
Intune app-beveiligingsbeleid (APP) op Android-apparaten maakt nu gebruik van een OpenSSL-versleutelingsbibliotheek die compatibel is met FIPS 140-2. Zie de sectie over [versleuteling](../apps/app-protection-policy-settings-android.md#encryption) van [instellingen van app-beveiligingsbeleid voor Android in Microsoft Intune](../apps/app-protection-policy-settings-android.md) voor meer informatie.

#### <a name="enable-win32-app-dependencies----2617348----"></a>Win32-app-afhankelijkheden inschakelen <!-- 2617348  -->
Als beheerder kunt u vereisen dat andere apps worden geïnstalleerd als afhankelijkheden voordat uw Win32-app wordt geïnstalleerd. Op het apparaat moet(e) met name de afhankelijke app(s) worden geïnstalleerd voordat de Win32-app wordt geïnstalleerd. Selecteer in Intune, **Client-apps** > **Apps** > **Toevoegen** om de blade **App toevoegen** weer te geven. Selecteer **Windows-app (Win32)** als **App-type**. Nadat u de app hebt toegevoegd, kunt u **Afhankelijkheden** selecteren om de afhankelijke apps toe te voegen die moeten worden geïnstalleerd voordat de Win32-app kan worden geïnstalleerd. Zie [Intune Standalone - Win32-app-beheer](./../apps/app-management.md) voor meer informatie. 

#### <a name="app-version-installation-information-for-microsoft-store-for-business-apps----3537391-----"></a>Installatie-informatie voor de app-versie voor Microsoft Store voor Bedrijven-apps <!-- 3537391   -->
App-installatierapporten bevatten informatie over de app-versie voor Microsoft Store voor bedrijven-apps. Selecteer in Intune **Client-apps** > **Apps**. Selecteer een **Microsoft Store voor bedrijven-app** en selecteer vervolgens **Installatiestatus apparaat** onder de sectie **Monitor**.

#### <a name="additions-to-win32-apps-requirement-rules----3676883-----"></a>Toevoegingen aan de vereisteregels voor Win32-apps <!-- 3676883   -->
U kunt vereisteregels maken op basis van PowerShell-scripts, registerwaarden en informatie over het bestandssysteem. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer vervolgens **Windows-app (Win32)** als **App-type** in de blade **App toevoegen**.  Selecteer **Vereisten** > **Toevoegen** om aanvullende vereisteregels te configureren. Selecteer vervolgens een **Bestandstype**, **Register** of **Script** als **Vereistetype**. Zie [Win32 app-beheer](./../apps/app-management.md) voor meer informatie.

#### <a name="configure-your-win32-apps-to-be-installed-on-intune-enrolled-azure-ad-joined-devices----3695227----"></a>Uw Win32-apps configureren voor een installatie op bij Intune ingeschreven apparaten die met Azure AD zijn gekoppeld <!-- 3695227  -->
U kunt uw Win32-apps toewijzen voor een installatie op bij Intune ingeschreven apparaten die met Azure AD zijn gekoppeld. Zie [Win32-app-beheer](./../apps/app-management.md) voor meer informatie over Win32-apps in Intune.

#### <a name="device-overview-shows-primary-user---3794259----"></a>Overzicht van apparaat geeft de primaire gebruiker weer <!--3794259  -->
In de overzichtspagina van het apparaat ziet u de primaire gebruiker, ook wel de UDA-gebruiker genoemd (UDA: User Device Affinity, gebruikersaffiniteit apparaat). Als u de primaire gebruiker van een apparaat wilt zien, kiest u **Intune** > **Apparaten** > **Alle apparaten** > Een apparaat kiezen. De primaire gebruiker wordt bovenaan de pagina **Overzicht** weergegeven.

#### <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices----4105925----"></a>Aanvullende rapportage van beheerde Google Play-apps voor apparaten met Android Enterprise-werkprofiel <!-- 4105925  -->
Voor beheerde Google Play-apps die op apparaten met Android Enterprise-werkprofiel zijn geïmplementeerd, kunt u het specifieke versienummer van de op een apparaat geïnstalleerde app weergeven. Dit geldt alleen voor vereiste apps.  

#### <a name="ios-third-party-keyboards----4111843-----"></a>iOS-toetsenborden van derden <!-- 4111843   -->
De ondersteuning voor het Intune-app-beveiligingsbeleid (APP) voor de instelling **Toetsenborden van derden** voor iOS wordt beëindigd vanwege een iOS-platformwijziging. U zult deze instelling niet meer kunnen configureren op de Intune-beheerconsole en deze wordt niet meer afgedwongen op de client in de Intune App SDK.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="set-login-settings-and-control-restart-options-on-macos-devices----1210083----"></a>Aanmeldingsinstellingen configureren en opties voor opnieuw opstarten beheren op macOS-apparaten <!-- 1210083  -->
U kunt op macOS-apparaten een apparaatconfiguratieprofiel maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **macOS** kiezen als platform > **Apparaatfuncties** als profieltype). Deze update bevat nieuwe aanmeldingsvensterinstellingen, zoals het weergeven van een aangepaste banner, het kiezen hoe gebruikers zich aanmelden, het weergeven of verbergen van de energie-instellingen enzovoort.

Zie [Instellingen van macOS-apparaatfuncties](../configuration/macos-device-features-settings.md) voor het bekijken van deze instellingen.

#### <a name="configure-wifi-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode---3041940----"></a>Wi-Fi configureren op aan de apparaateigenaar toegewezen Android Enterprise-apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps <!--3041940  -->
U kunt de instellingen voor Android Enterprise-apparaateigenaar inschakelen wanneer deze als toegewezen apparaat in kioskmodus voor meerdere apps wordt uitgevoerd. In deze update kunt u gebruikers in staat stellen om Wi-Fi-netwerken te configureren en ermee verbinding te maken (**Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform > **Alleen apparaateigenaar, Apparaatbeperkingen** als profieltype >  **Toegewezen apparaten** > **Kioskmodus**: **Voor meerdere apps** > **Wi-Fi-configuratie**). 

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps


#### <a name="configure-bluetooth-and-pairing-on-android-enterprise-device-owner-dedicated-devices-running-in-multi-app-kiosk-mode----3041941----"></a>Bluetooth en koppelen configureren op aan apparaateigenaar toegewezen Android Enterprise-apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps <!-- 3041941  -->
U kunt de instellingen voor Android Enterprise-apparaateigenaar inschakelen wanneer deze als toegewezen apparaat in kioskmodus voor meerdere apps wordt uitgevoerd. In deze update kunt u gebruikers toestaan om Bluetooth in te schakelen en via Bluetooth apparaten te koppelen (**Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform > **Alleen apparaateigenaar, Apparaatbeperkingen** als profieltype >  **Toegewezen apparaten** > **Kioskmodus**: **Voor meerdere apps** > **Bluetooth-configuratie**). 

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) als u alle configureerbare instellingen wilt bekijken.

Van toepassing op: aan Android Enterprise toegewezen apparaten die worden uitgevoerd in de kioskmodus voor meerdere apps

#### <a name="create-and-use-oemconfig-device-configuration-profiles-in-intune----3305883----"></a>OEMConfig-apparaatconfiguratieprofielen in Microsoft Intune maken en gebruiken <!-- 3305883  -->
In deze update biedt Intune ondersteuning voor het configureren van Android Enterprise-apparaten met OEMConfig. U kunt specifiek een apparaatconfiguratieprofiel maken, en instellingen toepassen op Android Enterprise-apparaten met behulp van OEMConfig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** als platform).

Ondersteuning voor OEM's is momenteel per OEM. Als de gewenste OEMConfig app niet beschikbaar is in de lijst met OEMConfig-apps, neemt u contact op met `IntuneOEMConfig@microsoft.com`.

Ga naar [Android-bedrijfsapparaten met OEMConfig gebruiken en beheren in Microsoft Intune](../configuration/android-oem-configuration-overview.md) voor meer informatie over deze functie.

Van toepassing op: Android Enterprise

#### <a name="windows-update-notifications-----3316758-3316782----"></a>Windows Update-meldingen  <!-- 3316758, 3316782  -->
We hebben twee *instellingen voor de gebruikerservaring* toegevoegd aan de Windows Update-ringconfiguraties die u vanuit de Intune-console kunt beheren. U kunt nu het volgende doen:
- Gebruikers weigeren of toestaan om [te scannen op Windows-updates](../protect/windows-update-settings.md).
- Het [meldingsniveau van Windows Update](../protect/windows-update-settings.md) dat gebruikers zien, beheren.

#### <a name="new-device-restriction-settings-for-android-enterprise-device-owner----3574254----"></a>Nieuwe apparaatbeperkingsinstellingen voor Android Enterprise-apparaateigenaar <!-- 3574254  -->
Op Android Enterprise-apparaten kunt u een profiel voor apparaatbeperking maken om functies toe te staan of te beperken en regels voor wachtwoorden in te stellen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > Kies **Android Enterprise** als platform > **Alleen apparaateigenaar > Apparaatbeperkingen** als profieltype). 

Deze update bevat nieuwe wachtwoordinstellingen, verleent volledige toegang tot apps in de Google Play Store voor volledig beheerde apparaten enzovoort. Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) voor de huidige lijst met instellingen. 

Van toepassing op: Volledig beheerde Android Enterprise-apparaten

#### <a name="check-for-a-tpm-chipset-in-a-windows-10-device-compliance-policy----3617671---"></a>Controleren of er zich een TPM-chipset in een nalevingsbeleid voor Windows 10-apparaten bevindt <!-- 3617671 -->

Deze functie is vertraagd en wordt later uitgebracht.

#### <a name="updated-ui-changes-for-microsoft-edge-browser-on-windows-10-and-later-devices----3775833-----"></a>Bijgewerkte wijzigingen aan de gebruikersinterface voor de Microsoft Edge-browser op Windows 10 en hoger <!-- 3775833   -->
Wanneer u een apparaatconfiguratieprofiel maakt, kunt u Microsoft Edge-functies op Windows 10 en hoger toestaan of beperken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Apparaatbeperkingen** als profieltype >  **Microsoft Edge-browser**). In deze update worden de instellingen voor Microsoft Edge meer beschrijvend en gemakkelijker te begrijpen. 

Als u deze functies wilt bekijken, gaat u naar [Apparaatbeperkingsinstellingen voor de Microsoft Edge-browser](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser).

Van toepassing op: Windows 10 en hoger

#### <a name="expanded-support-for-android-enterprise-fully-managed-devices--preview-------3903241-3903244-3903246-----"></a>Uitgebreide ondersteuning voor volledig beheerde Android Enterprise-apparaten (preview)  <!--   3903241, 3903244, 3903246   -->
Wij hebben onze ondersteuning, die nog steeds in openbare preview is, uitgebreid voor volledig beheerde Android Enterprise-apparaten ([voor het eerst aangekondigd in januari 2019](whats-new.md#week-of-january-14-2019) en het volgende erin opgenomen: 

- Op volledig beheerde en toegewezen apparaten kunt u [nalevingsbeleid](../protect/compliance-policy-create-android-for-work.md) maken met inbegrip van regels voor wachtwoorden en vereisten voor besturingssystemen (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Android Enterprise** als platform > **Apparaateigenaar** als profieltype). 

  Op toegewezen apparaten kan het apparaat mogelijk worden weergegeven als **niet-compatibel**. Voorwaardelijke toegang is niet beschikbaar op toegewezen apparaten. Zorg ervoor dat u alle taken of acties uitvoert om de toegewezen apparaten compatibel te maken met uw toegewezen beleid.

- [Voorwaardelijke toegang](../protect/conditional-access.md): beleid voor voorwaardelijke toegang dat van toepassing is op Android, is ook van toepassing op volledig beheerde Android Enterprise-apparaten. Gebruikers kunnen nu hun volledig beheerd apparaat registreren bij Azure Active Directory met behulp van de **Microsoft Intune-app**. Bekijk vervolgens eventuele nalevingsproblemen voor toegang tot resources van de organisatie en los deze op.

- Nieuwe eindgebruiker-app (Microsoft Intune-app): er is een nieuwe eindgebruiker-app voor volledig beheerde Android-apparaten met de naam **Microsoft Intune**. Deze nieuwe app is licht en modern en biedt een functionaliteit die vergelijkbaar is met de bedrijfsportal-app, maar dan voor volledig beheerde apparaten. Zie [Microsoft Intune-app in Google Play](https://play.google.com/store/apps/details?id=com.microsoft.intune) voor meer informatie.

Ga naar **Apparaatinschrijving** > **Android-inschrijving** > **Bedrijfseigendom, volledig beheerde gebruikersapparaten** om volledige beheerde Android-apparaten in te stellen. Ondersteuning voor volledig beheerde Android-apparaten blijft in preview en bepaalde Intune-functies werken mogelijk niet volledig.  

Zie onze blog [Microsoft Intune - Preview 2 voor volledig beheerde Android Enterprise-apparaten](https://aka.ms/preview2_AE_fullymanaged) voor meer informatie over deze preview.


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="configure-profile-to-skip-some-screens-during-setup-assistant----2276470----"></a>Profiel configureren om bepaalde vensters over te slaan tijdens het doorlopen van de configuratieassistent <!-- 2276470  -->
Wanneer u een macOS-registratieprofiel maakt, kunt u binnenkort instellen dat de configuratieassistent de volgende schermen overslaat:
- Uiterlijk
- Weergavekleur
- iCloudStorage Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server.  Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.
Raadpleeg [MacOS-apparaten automatisch inschrijven met het Device Enrollment Program of Apple School Manager](../enrollment/device-enrollment-program-enroll-macos.md) voor meer informatie.

#### <a name="bulk-device-naming-when-enrolling-corporate-ios-devices--3566569----"></a>Bulksgewijs apparaten benoemen bij het inschrijven van zakelijke iOS-apparaten<!--3566569  -->
Wanneer u een van de zakelijke inschrijvingsmethoden van Apple (DEP/ABM/ASM) gebruikt, kunt u de naamindeling van een apparaat zo instellen dat binnenkomende iOS-apparaten automatisch worden benoemd. U kunt een indeling opgeven waarin het apparaattype en serienummer in uw sjabloon wordt opgenomen. Als u dit wilt doen, kiest u **Intune** > **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor het inschrijvingsprogramma** > **Een token selecteren** >**Profiel maken** > **Naamgevingsindeling voor apparaten**. U kunt bestaande profielen bewerken, maar alleen bij zojuist gesynchroniseerde apparaten wordt de naam toegepast.

#### <a name="updated-default-timeout-message-on-enrollment-status-page----3959331---"></a>Bijgewerkt standaard time-outbericht op de pagina Inschrijvingsstatus <!-- 3959331 -->
We hebben het standaard time-outbericht bijgewerkt dat gebruikers zien wanneer de pagina Status van inschrijving (ESP) de time-outwaarde overschrijdt die is opgegeven in het ESP-profiel. Het nieuwe standaardbericht is wat gebruikers zien en waarin duidelijk wordt gemaakt welke volgende acties ze kunnen ondernemen met hun ESP-implementatie.  

### <a name="device-management"></a>Apparaatbeheer

#### <a name="retire-noncompliant-devices-----1827291-----"></a>Niet-compatibele apparaten buiten gebruik stellen  <!-- 1827291   -->
Deze functie is vertraagd en wordt in een toekomstige release geïntroduceerd.


### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="intune-data-warehouse-v10-changes-reflecting-back-to-beta----4403765---"></a>Wijzigingen in Intune Data Warehouse V1.0 worden doorgevoerd in de bètaversie <!-- 4403765 -->
Toen V1.0 voor het eerst werd uitgebracht in 1808, verschilde deze op belangrijke punten van de bètaversie-API. In 1903 zullen deze wijzigingen in de bètaversie-API worden doorgevoerd. Als u belangrijke rapporten hebt die gebruikmaken van de bètaversie-API, wordt u ten zeerste aangeraden deze rapporten over te zetten naar V1.0 om wijzigingen te voorkomen die fouten veroorzaken. Zie [Wijzigingenlogboek voor Intune Data Warehouse-API](../developer/reports-changelog.md#1903-part-2) voor meer informatie.

#### <a name="monitor-security-baseline-status-public-preview----3082047---"></a>Status beveiligingsbasislijnen controleren (openbare preview) <!-- 3082047 --> 
We hebben een [weergave per categorie](../protect/security-baselines-monitor.md#per-category-view) toegevoegd aan de controle van beveiligingsbasislijnen. (Beveiligingsbasislijnen blijven in preview). De weergave per categorie geeft elke categorie weer van de basislijn, samen met het percentage apparaten dat in elke statusgroep voor die categorie kan worden onderverdeeld. U kunt nu zien hoeveel apparaten niet overeenkomen met de afzonderlijke categorieën, onjuist zijn geconfigureerd of niet van toepassing zijn.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-apple-vpp-tokens---2371886----"></a>Bereiktags voor Apple VPP-tokens <!--2371886  -->
U kunt nu bereiktags toevoegen aan Apple VPP-tokens. Alleen gebruikers aan wie dezelfde bereiktag is toegewezen, hebben toegang tot het Apple VPP-token met die tag. VPP-apps en e-Books die zijn gekocht met dit token nemen de bereiktags ervan over. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie over bereiktags.







## <a name="week-of-april-1-2019"></a>Week van 1 april 2019

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="updated-certificate-connectors-----icm-113304612---"></a>Bijgewerkte certificaatconnectors  <!-- ICM 113304612 -->
We hebben updates uitgebracht voor zowel de [Intune-certificaatconnector als de PFX-certificaatconnector voor Microsoft Intune](../protect/certficates-pfx-configure.md#whats-new-for-connectors). Met de nieuwe releases worden verschillende bekende problemen opgelost.  

### <a name="app-management"></a>Appbeheer

#### <a name="user-experience-update-for-the-company-portal-app-for-ios----2536024---"></a>Update van de gebruikerservaring voor de bedrijfsportal-app voor iOS <!-- 2536024 -->
De startpagina van de bedrijfsportal-app voor iOS-apparaten is opnieuw ontworpen. Door deze wijziging kan de startpagina beter patronen volgen van de iOS-gebruikersinterface en ook een verbeterde zichtbaarheid bieden voor apps en e-Books.

#### <a name="changes-to-company-portal-enrollment-for-ios-12-device-users---3448635---"></a>Wijzigingen in de bedrijfsportal-App-registratie voor gebruikers van iOS-12-apparaten <!--3448635 -->  
De schermen en stappen in de bedrijfsportal-app voor iOS-inschrijving zijn bijgewerkt, zodat deze overeenkomen met de wijzigingen in de MDM-inschrijving die zijn uitgebracht in Apple iOS 12.2. In de bijgewerkte werkstroom wordt gebruikers het volgende gevraagd:  

* Safari te openen op de bedrijfsportalwebsite en het beheerprofiel te downloaden voordat zij terugkeren naar de bedrijfsportal-app.  
* De app instellingen te openen voor het installeren van het beheerprofiel op hun apparaat.
* Terug te gaan naar de bedrijfsportal-app om de inschrijving te voltooien.  

Zie [iOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) voor de bijgewerkte stappen en schermen voor de inschrijving.  

## <a name="week-of-march-25-2019"></a>Week van 25 maart 2019

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

### <a name="support-for-the-power-bi-compliance-app-from-the-data-warehouse-blade-in-microsoft-intune----4260871---"></a>Ondersteuning voor de Power BI-compatibiliteit-app vanuit de blade Datawarehouse in Microsoft Intune <!-- 4260871 -->
Voorheen werd via de koppeling **Power BI-bestand downloaden** in de blade **Intune-datawarehouse** een Intune-datawarehouserapport (pbix-bestand) gedownload. Dit rapport is vervangen door de Power BI-compatibiliteit-app. De Power BI-compatibiliteit-app hoeft niet speciaal te worden geladen of ingesteld. U kunt deze rechtstreeks in de online Power BI-portal openen en ermee gegevens speciaal voor uw Intune-tenant weergeven op basis van uw referenties. Selecteer in Intune de koppeling **Intune-datawarehouse instellen** aan de rechterkant van de Intune-blade. Klik vervolgens op **Power BI-app ophalen**. Zie [Verbinding maken met het datawarehouse met Power BI](../developer/reports-proc-get-a-link-powerbi.md) voor meer informatie.

## <a name="week-of-march-18-2019"></a>Week van 18 maart 2019

### <a name="app-management"></a>Appbeheer

#### <a name="deploy-microsoft-visio-and-microsoft-project----3725386----"></a>Microsoft Visio en Microsoft Project implementeren <!-- 3725386  -->
U kunt nu Microsoft Visio Pro voor Office 365 en Microsoft Project Online-desktopclient implementeren als onafhankelijke apps voor Windows 10-apparaten met behulp van Microsoft Intune, mits u licenties hebt voor deze apps. Selecteer vanuit Intune **Client-apps** > **Apps** > **Toevoegen** om de blade **App toevoegen** weer te geven. Selecteer in de blade **App toevoegen** **Windows 10** als **App-type**. Selecteer daarna **App-pakket configureren** om de te installeren apps te selecteren. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](../apps/apps-add-office365.md) voor meer informatie over Office 365-apps voor Windows 10-apparaten.

#### <a name="microsoft-visio-pro-for-office-365-product-name-change----3593653----"></a>Wijziging van de productnaam Microsoft Visio Pro voor Office 365 <!-- 3593653  -->
**Microsoft Visio Pro voor Office 365** heet nu **Microsoft Visio Online-abonnement 2**.  Zie [Visio Online-abonnement 2](https://products.office.com/visio/visio-online-plan-2) voor meer informatie over Microsoft Visio. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](../apps/apps-add-office365.md) voor meer informatie over Office 365-apps voor Windows 10-apparaten.

#### <a name="intune-app-protection-policy-app-character-limit-setting----3291302----"></a>Instelling van Intune app-beveiligingsbeleid (APP) voor maximum aantal tekens <!-- 3291302  -->
Intune-beheerders kunnen een uitzondering opgeven voor de Intune-app-beveiligingsbeleidsinstelling **Knippen, kopiëren en plakken met andere apps beperken**.  Als beheerder kunt u het aantal tekens opgeven dat mag worden geknipt of gekopieerd uit een beheerde app. Met deze instelling kunt u het opgegeven aantal tekens voor elke app delen, ongeacht de instelling Knippen, kopiëren en plakken met andere apps beperken. Houd er rekening mee dat de versie van de Intune-bedrijfsportal-app voor Android versie 5.0.4364.0 of hoger moet zijn. Zie [iOS-gegevensbeveiliging](../apps/app-protection-policy-settings-ios.md#data-protection), [Android-gegevensbeveiliging](../apps/app-protection-policy-settings-android.md#data-protection) en [Logboeken voor client-app-beveiliging controleren](../apps/app-protection-policy-settings-log.md#app-protection-policy-settings) voor meer informatie.

#### <a name="office-deployment-tool-odt-xml-for-office-proplus-deployment----3192477-----"></a>ODT-XML (ODT: Office Deployment Tool) voor de implementatie van Office ProPlus <!-- 3192477   -->
U kunt voorzien in een ODT-XML bij het maken van een Office Professional Plus-exemplaar in de Intune-beheerconsole. Dit biedt meer aanpassingsmogelijkheden, indien de bestaande Intune gebruikersinterfaceopties niet voldoen aan uw behoeften. Zie [Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune](../apps/apps-add-office365.md) en [Configuratieopties voor de Office Deployment Tool](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool) voor meer informatie.

#### <a name="app-icons-will-now-be-displayed-with-an-automatically-generated-background----1429026----"></a>App-pictogrammen worden nu weergegeven met een automatisch gegenereerde achtergrond <!-- 1429026  -->
In de Windows-bedrijfsportal-app-worden app-pictogrammen nu weergegeven met een automatisch gegenereerde achtergrond op basis van de overheersende kleur van het pictogram (mits deze detecteerbaar is). Indien van toepassing wordt de grijze rand die voorheen zichtbaar was op app-tegels, vervangen door deze achtergrond. Gebruikers zullen deze wijziging zien in bedrijfsportal-app-versies die hoger zijn dan 10.3.3451.0.

#### <a name="install-available-apps-using-the-company-portal-app-after-windows-bulk-enrollment----2751523-----"></a>Beschikbare apps installeren met behulp van de bedrijfsportal-app na de Windows-bulkinschrijving <!-- 2751523   -->
Windows-apparaten die zijn geregistreerd bij Intune via [Windows-bulkinschrijving](../enrollment/windows-bulk-enroll.md) (inrichtingspakketten) kunnen de bedrijfsportal-app gebruiken voor het installeren van beschikbare apps. Zie [De Windows 10-bedrijfsportal handmatig toevoegen](../apps/store-apps-company-portal-app.md) en [De Microsoft Intune-bedrijfsportal-app configureren](../apps/company-portal-app.md) voor meer informatie over de bedrijfsportal-app.

#### <a name="the-microsoft-teams-app-can-be-selected-as-part-of-the-office-app-suite----3828932----"></a>De Microsoft Teams-app kan worden geselecteerd als onderdeel van het Office-app-pakket <!-- 3828932  -->
De Microsoft Teams-app kan worden opgenomen of uitgesloten als onderdeel van de installatie van het Office Pro Plus-app-pakket. Deze functie werkt voor Office Professional Plus-buildnummer 16.0.11328.20116+. De gebruiker moet zich afmelden en vervolgens weer aanmelden op het apparaat om de installatie te voltooien. Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. Selecteer een van de app-typen van de **Office 365-Suite** en selecteer vervolgens **App-pakket configureren**.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="automatically-start-an-app-when-running-multiple-apps-in-kiosk-mode-on-windows-10-and-later-devices----2351390---"></a>Een app automatisch starten wanneer meerdere apps in de kioskmodus worden uitgevoerd op Windows 10-apparaten en hoger <!-- 2351390 -->

U kunt op Windows 10-apparaten en hoger een apparaat in de kioskmodus uitvoeren en veel apps uitvoeren. In deze update is een instelling **AutoLaunch** aanwezig (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform > **Kiosk** als profieltype > **Kiosk voor meerdere apps**). Gebruik deze instelling om een app automatisch te starten wanneer de gebruiker zich aanmeldt bij het apparaat.

Zie [Instellingen van Windows 10-apparaten en hoger die als kiosk moet worden uitgevoerd in Intune](../configuration/kiosk-settings-windows.md) voor een lijst en een beschrijving van alle kioskinstellingen.

Van toepassing op: Windows 10 en hoger

#### <a name="operational-logs-also-show-details-on-non-compliant-devices----4063755----"></a>Operationele logboeken geven ook details weer over niet-compatibele apparaten <!-- 4063755  -->
Wanneer u Intune-logboeken naar Azure Monitor-functies stuurt, kunt u tevens de operationele logboeken sturen. In deze update bieden de operationele logboeken ook informatie over niet-compatibele apparaten. 

Raadpleeg [Logboekgegevens verzenden naar opslag, Event Hubs of Log Analytics in Intune](../review-logs-using-azure-monitor.md) voor meer informatie over deze functie.

#### <a name="route-logs-to-azure-monitor-in-more-intune-workloads----3804627---"></a>Logboeken sturen naar Azure Monitor in meer Intune-workloads <!-- 3804627 -->
In Intune kunt u auditlogboeken en operationele logboeken sturen naar Event Hubs,opslag en Log Analytics in Azure Monitor (**Intune** > **Bewaking** > **Diagnose-instellingen**). In deze update kunt u deze logboeken routeren in meer Intune-workloads, met inbegrip van naleving, configuraties en client-apps enzovoort. 

Zie [logboekgegevens verzenden naar Event Hubs, opslag en Log Analytics](../review-logs-using-azure-monitor.md) voor meer informatie over routering van logboeken naar Azure Monitor.

#### <a name="create-and-use-mobility-extensions-on-android-zebra-devices-in-intune----3305880-----"></a>Mobility-extensies maken en gebruiken op Android Zebra-apparaten in Intune <!-- 3305880   -->
In deze update biedt Intune ondersteuning voor het configureren van Android Zebra-apparaten. U kunt specifiek een apparaatconfiguratieprofiel maken en instellingen toepassen op Android Zebra-apparaten met behulp van MX-profielen (MX: Mobility-extensies) die worden gegenereerd door StageNow (**Apparaatconfiguratie** >  **Profielen** > **Profiel maken** > **Android** als platform > **MX-profiel (alleen Zebra)** als profieltype).

Zie [Zebra-apparaten gebruiken en beheren met Mobility-extensies in Intune](../configuration/android-zebra-mx-overview.md) voor meer informatie over deze functie.

Van toepassing op: Android

### <a name="device-management"></a>Apparaatbeheer

#### <a name="encryption-report-for-windows-10-devices-in-public-preview---2351538---"></a>Versleutelingsrapport voor Windows 10-apparaten (in openbare preview)<!-- 2351538 -->  
U kunt met het nieuwe [versleutelingsrapport (preview)](../protect/encryption-monitor.md) details weergeven over de versleutelingsstatus van uw Windows 10-apparaten. Beschikbare details bestaan onder meer uit een TPM-versie van apparaten, de versleutelingsgereedheid en -status, foutrapportage en meer.  

#### <a name="access-bitlocker-recovery-keys-from-the-intune-portal-in-public-preview----2351547-----"></a>Toegang krijgen tot BitLocker-herstelsleutels vanuit de Intune-portal (in openbare preview) <!-- 2351547   -->  
U kunt nu Intune gebruiken om [details weer te geven](../protect/encryption-monitor.md) over BitLocker-sleutelidentificatie en BitLocker-herstelsleutels vanuit Azure Active Directory.

#### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Microsoft Edge-ondersteuning voor Intune-scenario's op iOS- en Android-apparaten <!-- 3411007 -->
Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser, met een verbeterde ervaring voor eindgebruikers. Microsoft Edge-functies voor bedrijven die zijn ingeschakeld door het Intune-beleid zijn onder meer dubbele identiteit, integratie van app-beveiligingsbeleid, integratie van Azure-toepassingsproxy's, beheerde favorieten en snelkoppelingen voor de startpagina. Zie de [ondersteuning voor Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support) voor meer informatie.

#### <a name="exchange-onlineintune-connector-deprecate-support-for-eas-only-devices---3105122----"></a>Exchange Online-/Intune-connector bieden geen ondersteuning meer voor apparaten voor alleen EAS <!--3105122  -->
De Intune-console ondersteunt niet langer de weergave en het beheer van apparaten voor alleen EAS die met Exchange Online zijn verbonden met de Intune-connector. U hebt in plaats daarvan de volgende opties:
- Apparaten registreren in Mobile Device Management (MDM)
- Beleid voor Intune-app-beveiliging gebruiken om uw apparaten te beheren
- Exchange-besturingselementen gebruiken zoals wordt beschreven in [Clients en mobiel in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/clients-and-mobile-in-exchange-online)

### <a name="search-the-all-devices-page-for-an-exact-device-by-using-name---4254930---"></a>De pagina Alle apparaten doorzoeken voor een exact apparaat met behulp van [naam] <!--4254930 -->
U kunt nu zoeken naar een exacte apparaatnaam. Ga naar **Intune** > **Apparaten** > **Alle apparaten** > plaats in het zoekvak de naam van het apparaat tussen {} om naar een exacte overeenkomst te zoeken. Bijvoorbeeld **{Device12345}** .

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="support-for-additional-connectors-on-the-tenant-status-page----3617202----"></a>Ondersteuning voor extra connectors op de pagina Tenantstatus <!-- 3617202  -->
De pagina [Tenantstatus](../tenant-status.md) geeft nu de statusinformatie weer voor extra connectors, inclusief *Windows Defender Advanced Threat Protection* (ATP) en andere Mobile Threat Defense-connectors.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="granting-intune-read-only-access-to-some-azure-active-directory-roles----3637917----"></a>Alleen-lezentoegang voor Intune verlenen aan bepaalde Azure Active Directory-rollen <!-- 3637917  -->
Alleen-lezentoegang voor Intune is verleend aan de volgende Azure AD-rollen. Machtigingen met Azure AD-rollen hebben voorrang boven machtigingen die zijn verleend via de op rollen gebaseerd toegangsbeheer (RBAC) in Intune.

Alleen-lezentoegang tot Intune-controlegegevens:

- Beheerder voor naleving
- Beheerder voor nalevingsgegevens

Alleen-lezentoegang tot alle Intune-gegevens:

- Beveiligingsbeheerder
- Beveiligingsoperator
- Beveiligingslezer

Zie [Op rollen gebaseerd toegangsbeheer](role-based-access-control.md) voor meer informatie.

#### <a name="scope-tags-for-ios-app-provisioning-profiles---2934430-----"></a>Bereiktags voor inrichtingsprofielen voor iOS-apps <!--2934430   -->
U kunt een bereiktag toevoegen aan een inrichtingsprofiel voor iOS-apps, zodat alleen personen met rollen die ook aan die bereiktag zijn toegewezen toegang hebben tot de app. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie.

#### <a name="scope-tags-for-app-configuration-policies---2371891-----"></a>Bereiktags voor app-configuratiebeleid <!--2371891   -->
U kunt een bereiktag toevoegen aan app-configuratiebeleid, zodat alleen personen met rollen die ook zijn toegewezen aan de bereiktag, toegang hebben tot het app-configuratiebeleid. Het app-configuratiebeleid kan alleen doel zijn voor of worden gekoppeld aan apps waaraan dezelfde bereiktag is toegewezen. Zie [RBAC en bereiktags gebruiken](scope-tags.md) voor meer informatie.

### <a name="microsoft-edge-support-for-intune-scenarios-on-ios-and-android-devices----3411007---"></a>Microsoft Edge-ondersteuning voor Intune-scenario's op iOS- en Android-apparaten <!-- 3411007 -->
Microsoft Edge biedt ondersteuning voor dezelfde beheerscenario's als de Intune Managed Browser met de toevoeging van verbeteringen in de eindgebruikerervaring. Microsoft Edge-functies voor bedrijven die zijn ingeschakeld door het Intune-beleid zijn onder meer dubbele identiteit, integratie van app-beveiligingsbeleid, integratie van Azure-toepassingsproxy's, beheerde favorieten en snelkoppelingen voor de startpagina. Zie de [ondersteuning voor Microsoft Edge](../apps/app-configuration-managed-browser.md#microsoft-edge-support) voor meer informatie.

## <a name="week-of-february-25-2019"></a>Week van 25 februari 2019

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="intune-powershell-module----951068----"></a>Intune PowerShell-module <!-- 951068  -->
De Intune PowerShell-module die ondersteuning biedt voor de Intune-API via Microsoft Graph, is nu beschikbaar in de [Microsoft PowerShell Gallery](https://www.powershellgallery.com/packages/Microsoft.Graph.Intune/6.1902.1.10).

- [Informatie over het gebruik van deze module](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/README.md)
- [Voorbeelden van scenario's waarbij deze module wordt gebruikt](https://github.com/Microsoft/Intune-PowerShell-SDK/blob/master/Samples/README.md)

#### <a name="improved-support-for-delivery-optimization----3183757----"></a>Verbeterde ondersteuning voor Delivery Optimization  <!--3183757  -->
We hebben de ondersteuning in Intune uitgebreid voor het configureren van Delivery Optimization. U kunt nu een uitgebreide lijst configureren met [Delivery Optimization-instellingen](../configuration/delivery-optimization-settings.md) en deze rechtstreeks vanuit de Intune-console toepassen op uw apparaten.


## <a name="week-of-february-18-2019"></a>Week van 18 februari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="intune-will-leverage-google-play-protect-apis-on-android-devices----2577355-----"></a>Intune gaat gebruikmaken van Google Play Protect-API’s op Android-apparaten <!-- 2577355   -->
Sommige IT-beheerders hebben te maken met een BYOD-landschap waar eindgebruikers mogelijk rooting of jailbreaking van hun mobiele telefoon veroorzaken. Dit gedrag leidt, in sommige gevallen onbewust, tot omzeiling van vele Intune-beleidsregels die zijn ingesteld om gegevens van de organisatie op de apparaten van eindgebruikers te beveiligen. Intune biedt daarom root- en jailbreakdetectie voor zowel geregistreerde als niet-geregistreerde apparaten. Met deze release zal Intune Google Play Protect-API’s aan onze bestaande rootdetectiecontroles toevoegen voor niet-geregistreerde apparaten. Hoewel Google niet alle rootdetectiecontroles die plaatsvinden deelt, verwachten we wel dat met deze API’s gebruikers worden gedetecteerd die hun apparaten om wat voor reden dan ook hebben geroot, variërend van apparaataanpassing tot de mogelijkheid nieuwere besturingssysteemupdates te krijgen op oudere apparaten. Toegang van deze gebruikers tot bedrijfsgegevens kan vervolgens worden geblokkeerd, of hun zakelijke accounts kunnen worden gewist uit via beleid ingeschakelde apps. Als extra waarde heeft de IT-beheerder nu verschillende rapportupdates op de blade Intune-app-beveiliging. Het rapport Gemarkeerde gebruikers toont welke gebruikers via de SafetyNet API-scan van Google Play Protect zijn gedetecteerd. Het rapport Mogelijk schadelijke apps toont aan welke apps zijn gedetecteerd via de scan die met de Verify Apps-API van Google is uitgevoerd. Deze functie is beschikbaar voor Android.

#### <a name="win32-app-information-available-in-troubleshooting-blade----2617342-----"></a>Informatie over Win32-apps, beschikbaar in de blade Probleemoplossing <!-- 2617342   -->
U kunt nu logboekbestanden over fouten bij een Win32-app-installatie verzamelen via de blade **Probleemoplossing** in de Intune-app. Zie [Problemen met de installatie oplossen](./../apps/troubleshoot-app-install.md) en [Problemen met Win32-apps oplossen](./../apps/troubleshoot-app-install.md#win32-app-installation-troubleshooting) voor meer informatie over problemen oplossen met de installatie van apps.

#### <a name="app-status-details-for-ios-apps----3761235-----"></a>Informatie over de appstatus voor iOS-apps <!-- 3761235   -->
Er zijn nieuwe meldingen voor installatiefouten van apps beschikbaar met betrekking tot het volgende:
- Fout tijdens het installeren van VPP-apps op een gedeelde iPad
- Fout tijdens uitschakelen van App Store
- Fout tijdens het zoeken van een VPP-licentie voor de app
- Fout tijdens het installeren van systeemapps met MDM-provider
- Fout tijdens het installeren van apps wanneer apparaat zich in de verloren-modus of kioskmodus bevindt
- Fout tijdens het installeren van apps wanneer gebruiker niet bij de App Store is aangemeld

In Intune selecteert u **Client-apps** > **Apps** > naam van de app > **Apparaatinstallatiestatus**. Nieuwe foutmeldingen zijn beschikbaar in de kolom **Statusdetails**.

#### <a name="new-app-categories-screen-in-the-company-portal-app-for-windows-10---3834780----"></a>Het scherm Nieuwe app-categorieën in de bedrijfsportal-app voor Windows 10<!-- 3834780  -->
Een nieuw scherm met de naam **App-categorieën** is toegevoegd om de blader- en selectie-ervaring voor apps te verbeteren in de bedrijfsportal voor Windows 10. Gebruikers zien nu hun apps gesorteerd onder categorieën, zoals **Aanbevolen**, **Opleiding** en **Productiviteit**. Deze wijziging wordt weergegeven in de bedrijfsportal-app-versies 10.3.3451.0 en hoger. Zie [Wat is er nieuw in de gebruikersinterface van de app?](whats-new-app-ui.md) om het nieuwe scherm te bekijken. Zie [Apps installeren en delen op uw apparaat](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows) voor meer informatie over apps in de bedrijfsportal.  

#### <a name="power-bi-compliance-app----1455231-doc-work-item---"></a>Power BI-compatibiliteit-app <!-- 1455231 doc-work-item -->
Krijg toegang tot uw Intune-datawarehouse in Power BI Online met behulp van de [Intune-compatibiliteit-app (datawarehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Met deze Power BI-app kunt u nu vooraf gemaakte rapporten openen en delen zonder iets te hoeven instellen en zonder uw webbrowser te verlaten. Zie [Wijzigingenlogboek - Power BI-compatibiliteit-app](../developer/reports-changelog.md#power-bi-compliance-app) voor meer informatie.


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="powershell-scripts-can-run-in-a-64-bit-host-on-64-bit-devices----1862675-----"></a>PowerShell-scripts kunnen worden uitgevoerd in een 64-bits host op 64-bits apparaten <!-- 1862675   -->
Wanneer u een PowerShell-script aan een apparaatconfiguratieprofiel toevoegt, wordt het script altijd uitgevoerd in 32 bits, zelfs op 64-bits besturingssystemen. Met deze update kan een beheerder het script uitvoeren in een 64-bits PowerShell-host op 64-bits apparaten (**Apparaatconfiguratie** > **PowerShell-scripts** > **Toevoegen** > **Configureren** > **Script uitvoeren in 64-bits PowerShell-host**).

Zie [PowerShell-scripts in Intune](../apps/intune-management-extension.md) voor meer details over het gebruik van PowerShell.

Van toepassing op: Windows 10 en hoger

#### <a name="macos-users-are-prompted-to-update-their-password----1873216---"></a>macOS-gebruikers wordt gevraagd hun wachtwoord bij te werken <!-- 1873216 -->
In Intune wordt de instelling **ChangeAtNextAuth** afgedwongen op macOS-apparaten. Deze instelling heeft gevolgen voor eindgebruikers en apparaten met wachtwoordbeleid voor naleving of wachtwoordprofielen voor apparaatbeperkingen. Eindgebruikers wordt eenmalig gevraagd hun wachtwoord bij te werken. Dit gebeurt wanneer een gebruiker voor het eerst een taak uitvoert die moet worden geverifieerd, zoals het aanmelden bij het apparaat. Gebruikers kunnen ook worden gevraagd hun wachtwoord bij te werken wanneer zij iets doen waarvoor beheerdersrechten zijn vereist, zoals het aanvragen van sleutelhangertoegang. 

Wijzigingen in nieuw of bestaand wachtwoordbeleid door de beheerder zorgt ervoor dat opnieuw aan eindgebruikers wordt gevraagd om hun wachtwoord bij te werken.

Van toepassing op:  
macOS

#### <a name="assign-scep-certificates-to-a-userless-macos-device-------2340521------"></a>SCEP-certificaten aan een macOS-apparaat zonder gebruikers toewijzen    <!-- 2340521    -->
U kunt met behulp van apparaatkenmerken SCEP-certificaten (SCEP: Simple Certificate Enrollment Protocol) toewijzen aan macOS-apparaten, inclusief apparaten zonder gebruikersaffiniteit, en het certificaatprofiel met Wi-Fi -of VPN-profielen koppelen. Dit is een uitbreiding van de bestaande ondersteuning voor het [toewijzen van SCEP-certificaten aan apparaten zonder gebruikersaffiniteit](../protect/certificates-profile-scep.md) die worden uitgevoerd op Windows, iOS en Android.  In deze update wordt de optie toegevoegd waarmee een certificaattype van *Apparaat* wordt geselecteerd wanneer u een SCEP-certificaatprofiel voor macOS configureert.

Van toepassing op: 
- macOS

#### <a name="intune-conditional-access-ui-update------2432313-----"></a>Update voor gebruikersinterface voor voorwaardelijke toegang tot Intune   <!-- 2432313   -->
We hebben verbeteringen aangebracht in de gebruikersinterface voor voorwaardelijke toegang in de Intune-console. Deze omvatten:
- Vervanging van de Intune-blade *Voorwaardelijke toegang* door de blade van Azure Active Directory. Hiermee hebt u toegang tot alle instellingen en configuraties voor [voorwaardelijke toegang](../protect/conditional-access.md) (die een Azure AD-technologie blijven) vanuit de Intune-console. 
- We hebben de naam van de blade *On-premises toegang* gewijzigd in *Toegang tot Exchange* en de configuratie van de *Exchange-serviceconnector* verplaatst naar deze hernoemde blade.  Door deze wijziging worden de locaties gecombineerd waar u [details met betrekking tot Exchange online en on-premises configureert en bewaakt](../protect/exchange-connector-install.md).  

#### <a name="kiosk-browser-and-microsoft-edge-browser-apps-can-run-on-windows-10-devices-in-kiosk-mode----2935135-----"></a>Kiosk Browser- en Microsoft Edge Browser-apps kunnen worden uitgevoerd op Windows 10-apparaten in de kioskmodus <!-- 2935135   -->
In de kioskmodus kunnen één of meerdere apps op Windows 10-apparaten worden uitgevoerd. Deze update omvat verschillende wijzigingen in het gebruik van browserapps in de kioskmodus, waaronder:

- Voeg de Microsoft Edge Browser of Kiosk Browser toe om deze als apps uit te voeren op het kioskapparaat (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en later** voor platform > **Kiosk** voor profieltype).
- Er zijn nieuwe functies en instellingen beschikbaar voor toestaan of beperken (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **Windows 10 en hoger** als platform > **Apparaatbeperkingen** als profieltype), waaronder:

- Microsoft Edge-browser:
  - Gebruik van Microsoft Edge-kioskmodus
  - De browser vernieuwen na niet-actieve tijd

- Favorieten en zoeken:
  - Wijzigingen in de zoekmachine toestaan

Ga voor een lijst met deze instellingen naar:

- [Instellingen voor apparaten met Windows 10 en hoger om ze als kiosk uit te voeren](../configuration/kiosk-settings-windows.md)
- [Microsoft Edge Browser-apparaatbeperkingen](../configuration/device-restrictions-windows-10.md#microsoft-edge-browser)
- [Apparaatbeperkingen voor favorieten en zoeken](../configuration/device-restrictions-windows-10.md##favorites-and-search)

Van toepassing op: Windows 10 en hoger

#### <a name="new-device-restriction-settings-for-ios-and-macos-devices----3448774-----"></a>Nieuwe apparaatbeperkingsinstellingen voor iOS- en macOS-apparaten <!-- 3448774   -->
U kunt een aantal instellingen en functies beperken op apparaten waarop iOS en macOS worden uitgevoerd (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** of **macOS** voor platform > **Apparaatbeperkingen** voor profieltype). Met deze update worden meer functies en instellingen toegevoegd die u kunt beheren, waaronder het instellen van schermtijd, het wijzigen van eSIM-instellingen en mobiele abonnementen en meer op iOS-apparaten. Andere functies zijn het vertragen van de zichtbaarheid voor de gebruiker van software-updates en het blokkeren van cacheopslag van inhoud op macOS-apparaten. 

Als u de functies en instellingen wilt zien die u kunt beperken, raadpleegt u:

- [Beperkingsinstellingen voor iOS-apparaten](../configuration/device-restrictions-ios.md)
- [Beperkingsinstellingen voor macOS-apparaten](../configuration/device-restrictions-macos.md)

Van toepassing op:

- iOS
- macOS

#### <a name="kiosk-devices-are-now-called-dedicated-devices-on-android-enterprise-devices----3598402-----"></a>Apparaten in de kioskmodus heten voortaan 'toegewezen apparaten' op Android Enterprise-apparaten <!-- 3598402   -->
Voor de afstemming met Android terminologie wordt **kiosk** gewijzigd in **toegewezen apparaten** voor Android Enterprise-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > ** Android Enterprise als platform > **Alleen apparaateigenaar** > **Apparaatbeperkingen** > **Toegewezen apparaten**).

Als u de beschikbare instellingen wilt zien, gaat u naar [Apparaatinstellingen voor het toestaan of beperken van functies](../configuration/device-restrictions-android-for-work.md#dedicated-device-settings).

Van toepassing op:  
Android Enterprise

#### <a name="safari-and-delaying-user-software-update-visibility-ios-settings-are-moving-in-the-intune-ui----3640850-3803313-----"></a>iOS-instellingen voor de zichtbaarheid van Safari-software-updates en het vertragen van die zichtbaarheid voor gebruikers worden verplaatst in de Intune-gebruikersinterface <!-- 3640850, 3803313   -->
Voor iOS-apparaten kunt u Safari-instellingen instellen en software-updates configureren. In deze update worden deze instellingen naar verschillende delen van de Intune-gebruikersinterface verplaatst:

- De Safari-instellingen zijn verplaatst van **Safari** (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** als platform > **Apparaatbeperkingen** als profieltype) naar **[Ingebouwde apps](../configuration/device-restrictions-ios.md#built-in-apps)** .
- De instelling **Zichtbaarheid van software-updates voor gebruikers voor iOS-apparaten onder toezicht vertragen** (**Software-updates** > **Updatebeleid voor iOS**) wordt verplaatst naar **Apparaatbeperkingen** >  **[Algemeen](../configuration/device-restrictions-ios.md#general)** .  Zie [Software-updates voor iOS](../protect/software-updates-ios.md#configure-the-policy) voor meer informatie over de gevolgen voor bestaand beleid. 

Ga voor een lijst met de instellingen naar:

- [Beperkingen voor iOS-apparaten](../configuration/device-restrictions-ios.md) 
- [Updates van iOS-software](../protect/software-updates-ios.md)

Deze functie is van toepassing op: 

- iOS

#### <a name="enabling-restrictions-in-the-device-settings-is-renamed-to-screen-time-on-ios-devices----3699164-----"></a>De naam Beperkingen inschakelen bij de apparaatinstellingen wordt gewijzigd in Schermtijd op iOS-apparaten <!-- 3699164   -->
U kunt **Beperkingen inschakelen bij de apparaatinstellingen** op iOS-apparaten onder toezicht configureren (**Apparaatconfiguratie** > **Profielen** > **Nieuw profiel** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **Algemeen**). In deze update wordt de naam van deze instelling gewijzigd in **Schermtijd (alleen onder toezicht)** . 

Het gedrag blijft hetzelfde. Specifiek: 

- iOS 11.4.1 en eerder: **Blokkeren** voorkomt dat eindgebruikers hun eigen beperkingen kunnen instellen bij de apparaatinstellingen. 
- iOS 12.0 en hoger: **Blokkeren** voorkomt dat eindgebruikers hun eigen **Schermtijd** kunnen instellen bij de apparaatinstellingen, waaronder inhouds- en privacybeperkingen. Op apparaten die naar iOS 12.0 zijn geüpgraded is het tabblad Beperkingen niet meer zichtbaar bij de apparaatinstellingen. Deze instellingen vindt u onder **Schermtijd**. 

Zie [Beperkingen voor iOS-apparaten](../configuration/device-restrictions-ios.md#general) voor een lijst met de instellingen.

Van toepassing op: 
- iOS


### <a name="device-management"></a>Apparaatbeheer

#### <a name="rename-an-enrolled-windows-device----1911112----"></a>De naam van een geregistreerd Windows-apparaat wijzigen <!-- 1911112  -->
U kunt nu de naam van geregistreerde Windows 10-apparaten (RS4 of later) wijzigen. Kies hiervoor **Intune** > **Apparaten** > **Alle apparaten** > kies een apparaat > **Naam van apparaat wijzigen**. Deze functie biedt momenteel geen ondersteuning voor de naamwijziging van hybride Azure AD Windows-apparaten.

#### <a name="auto-assign-scope-tags-to-resources-created-by-an-admin-with-that-scope----3173823----"></a>Bereiktags automatisch toewijzen aan resources die door een beheerder met dat bereik zijn gemaakt <!-- 3173823  -->
Wanneer een beheerder een resource maakt, worden alle bereiktags die aan de beheerder zijn toegewezen automatisch toegewezen aan die nieuwe resources.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="failed-enrollment-report-moves-to-the-device-enrollment-blade----3560202----"></a>Mislukte verplaatsing van registratierapporten naar de blade Apparaatregistratie <!-- 3560202  -->
Het rapport **Mislukte registraties** is verplaatst naar het gedeelte **Bewaking** van de blade **Apparaatregistratie**. Twee nieuwe kolommen (Registratiemethode en besturingssysteemversie) zijn ook toegevoegd.

#### <a name="company-portal-abandonment-report-renamed-to-incomplete-user-enrollments---3815076-eemiss---"></a>De naam van het rapport Bedrijfsportal afbreken is gewijzigd in Onvolledig gebruikersinschrijvingen <!--3815076 eemiss -->
De naam van het rapport **Bedrijfsportal afbreken** is gewijzigd in **Onvolledig gebruikersinschrijvingen**.


<!-- ########################## -->
## <a name="week-of-february-4-2019"></a>Week van 4 februari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="intune-macos-company-portal-dark-mode----3300524----"></a>Donkere modus van Intune macOS-bedrijfsportal <!-- 3300524  -->
De Intune macOS Bedrijfsportal biedt nu ondersteuning voor de donkere modus voor macOS. Wanneer u de donkere modus inschakelt op een macOS 10.14+-apparaat, wordt de vormgeving door de Bedrijfsportal aangepast naar kleuren die overeenkomen met die modus.

<!-- ########################## -->
## <a name="week-of-january-21-2019"></a>De week van 21 januari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="toast-notifications-for-win32-apps----3136566-----"></a>Toast-meldingen voor Win32-apps <!-- 3136566   -->
U kunt per app-toewijzing onderdrukken dat toast-meldingen voor eindgebruikers worden weergegeven. Selecteer vanuit Intune de optie **Client-apps** > **Apps** > selecteer de app > **Toewijzingen** > **Groepen opnemen**. 

#### <a name="intune-app-protection-policies-ui-update----3251427----"></a>Update van de gebruikersinterface voor beveiligingsbeleid voor apps in Intune <!-- 3251427  -->
We hebben de labels voor instellingen en knoppen voor App-beveiliging van Intune gewijzigd om ze duidelijker te maken. De wijzigingen zijn onder meer:  
- Besturingselementen zijn gewijzigd van **ja** / **nee** naar primair **blokkeren** / **toestaan** en **uitschakelen** / **inschakelen**. De labels zijn ook bijgewerkt.  
- De instellingen zijn opnieuw ingedeeld, zodat de instellingen en bijbehorende labels naast elkaar in het besturingselement staan, wat betere navigatie biedt.   

De standaardinstellingen en een aantal instellingen blijven dezelfde, maar met deze wijziging kan de gebruiker de instellingen beter begrijpen, gebruiken en er door navigeren om het geselecteerde app-beveiligingsbeleid toe te passen. Zie [iOS-instellingen](../apps/app-protection-policy-settings-ios.md) en [Android-instellingen](../apps/app-protection-policy-settings-android.md) voor meer informatie.

### <a name="additional-settings-for-outlook----3301182----"></a>Extra instellingen voor Outlook <!-- 3301182  -->
U kunt nu de volgende aanvullende instellingen voor Outlook voor iOS en Android configureren met Intune:

- Instellen dat alleen werk- of schoolaccounts mogen worden gebruikt in Outlook in iOS en Android
- Moderne verificatie implementeren voor Office 365 en hybride moderne verificatie voor on-premises accounts
- `SAMAccountName` gebruiken in het gebruikersnaamveld in het e-mailprofiel als basisverificatie wordt geselecteerd
- Toestaan dat contactpersonen worden opgeslagen
- E-mailtips voor externe ontvangers configureren
- Het **Postvak IN met prioriteit** configureren
- Biometrie vereisten voor toegang tot Outlook in iOS
- Externe afbeeldingen blokkeren

> [!NOTE]
> Als u gebruikmaakt van Intune-app-beveiligingsbeleid voor het beheren van toegang tot bedrijfs-id's, wordt afgeraden **biometrie te vereisen**. Zie **Bedrijfsreferenties vereisen voor toegang** voor [iOS-toegangsinstellingen](../apps/app-protection-policy-settings-ios.md#access-requirements) en [Android-toegangsinstellingen](../apps/app-protection-policy-settings-android.md#access-requirements).

Zie [Configuratie-instellingen voor Microsoft Outlook](../apps/app-configuration-policies-outlook.md) voor meer informatie.

#### <a name="delete-android-enterprise-apps----1352553---"></a>Android Enterprise-apps verwijderen <!-- 1352553 -->
U kunt beheerde Google Play-apps verwijderen uit Microsoft Intune. Als u een beheerde Google Play-app wilt verwijderen, opent u Microsoft Intune in de Azure-portal en selecteert u **Client-apps** > **Apps**. In de lijst met apps selecteert u het beletselteken (...) rechts naast de beheerde Google Play-app en vervolgens **Verwijderen** in de weergegeven lijst. Wanneer u een beheerde Google Play-app uit de lijst met apps verwijdert, wordt de goedkeuring voor de beheerde Google Play-app automatisch verwijderd.

#### <a name="managed-google-play-app-type----1352580---"></a>Type beheerde Google Play-app <!-- 1352580 -->
Met het type **beheerde Google Play-app** hebt u toestemming om specifiek [beheerde Google Play-apps](https://play.google.com/work/search?q=microsoft&c=apps) aan Intune toe te voegen. Als Intune-beheerder kunt u nu door goedgekeurde beheerde Google Play-apps bladeren en goedgekeurde beheerde Google Play-apps zoeken, goedkeuren, synchroniseren en toewijzen in Intune.  U hoeft niet langer afzonderlijk naar de beheerde Google Play-console te bladeren en u hoeft niet opnieuw een verificatie uit te voeren.  Selecteer in Intune de optie **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** selecteert u **Beheerd Google Play** als app-type.

### <a name="default-android-pin-keyboard----3802457---"></a>Standaardpincodetoetsenbord van Android <!-- 3802457 -->
Eindgebruikers die een Intune APP-pincode (App Protection Policy) op hun Android-apparaten hebben ingesteld met pincodetype Numeriek, zien nu het Android-standaardtoetsenbord in plaats van de gebruikelijke Android-toetsenbordgebruikersinterface die eerder is ontworpen. Deze wijziging is doorgevoerd voor consistentie met standaardtoetsenborden op zowel Android als iOS, voor de pincodetypen Numeriek en/of Wachtwoordcode. Zie [Android-toegangsvereisten](../apps/app-protection-policy-settings-android.md#access-requirements) voor meer informatie over de toegangsinstellingen voor eindgebruiker op Android, zoals de APP-pincode.

### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="use-microsoft-recommended-settings-with-security-baselines-public-preview----2055484-----"></a>Door Microsoft aanbevolen instellingen gebruiken met beveiligingsbasislijnen (openbare preview) <!-- 2055484   -->

Intune is geïntegreerd met andere services die op beveiliging gericht zijn, inclusief Windows Defender ATP en Office 365 ATP. Klanten vragen om een gemeenschappelijke strategie en een samenhangende set van end-to-end beveiligingsworkflows voor alle Microsoft 365-diensten. Ons doel is om strategieën af te stemmen en oplossingen te ontwikkelen die beveiligingsactiviteiten en gebruikelijke beheerderstaken combineren. In Intune willen we dit doel bereiken door het publiceren van een set beveiligingsbasislijnen die door Microsoft zijn aanbevolen (**Intune** >  **Beveiligingsbasislijnen**).  Beheerders kunnen direct op basis van deze basislijnen een beveiligingsbeleid opstellen en dit vervolgens voor hun gebruikers implementeren. U kunt ook de aanbevelingen voor procedures aanpassen aan de behoeften van uw organisatie. Intune zorgt ervoor dat apparaten deze basislijnen blijven naleven, en waarschuwt beheerders wanneer gebruikers of apparaten van de basislijnen afwijken.

Deze functie is beschikbaar als openbare preview, dus alle profielen die nu worden gemaakt, worden niet verplaatst naar beveiligingsbasislijnsjablonen die algemeen beschikbaar zijn. U moet deze previewsjablonen niet voor uw productieomgeving gebruiken.

Zie [Een Windows 10-beveiligingsbasislijn maken in Intune](../protect/security-baselines-monitor.md) voor meer informatie over beveiligingsbasislijnen.

Deze functie is van toepassing op: Windows 10 en hoger

#### <a name="non-administrators-can-enable-bitlocker-on-windows-10-devices-joined-to-azure-ad---2147379-----"></a>Niet-beheerders kunnen BitLocker gebruiken op Windows 10-apparaten die zijn gekoppeld aan Azure AD<!-- 2147379   -->
Wanneer u BitLocker-instellingen op Windows 10-apparaten inschakelt (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **Endpoint Protection** als profieltype > **Windows-versleuteling**), voegt u BitLocker-instellingen toe. 

Deze update bevat een nieuwe BitLocker-instellingen waarmee standaardgebruikers (niet-beheerders) versleuteling kunnen inschakelen. 

Ga naar [Instellingen voor de beveiliging van eindpunten voor Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption) om de instellingen te bekijken.

#### <a name="check-for-configuration-manager-compliance----2192052--eepublished----"></a>Controleren op Configuration Manager-compatibiliteit <!-- 2192052  eepublished  -->
Deze update bevat een nieuwe instelling voor System Center Configuration Manager-compatibiliteit (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Windows 10 en hoger** > **Configuration Manager-compatibiliteit**). Configuration Manager verzendt signalen naar Intune-naleving. Met deze instelling kunt u vereisen dat alle Configuration Manager-signalen de waarde 'compatibel' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in Configuration Manager de status 'Geïnstalleerd'. Als programma's op het apparaat een onbekende status hebben, is het apparaat niet-compatibel in Intune.

In [Configuration Manager-compatibiliteit](../protect/compliance-policy-create-windows.md#configuration-manager-compliance) wordt deze instelling beschreven.

Van toepassing op: Windows 10 en hoger

#### <a name="customize-wallpaper-on-supervised-ios-devices-using-a-device-configuration-profile----2809324-----"></a>Achtergronden op iOS-apparaten die onder toezicht staan aanpassen met behulp van een apparaatconfiguratieprofiel <!-- 2809324   -->
Wanneer u een apparaatconfiguratieprofiel voor iOS-apparaten maakt, kunt u sommige functies aanpassen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatfuncties** voor profieltype). Deze update bevat nieuwe **achtergrond**instellingen waarmee een beheerder een .png-, .jpg- of .jpeg-afbeelding op het startscherm of het vergrendelingsscherm kan gebruiken. Deze achtergrondinstellingen zijn alleen van toepassing op apparaten die onder supervisie staan. 

Zie [Instellingen van apparaatfuncties voor iOS](../configuration/ios-device-features-settings.md) voor een lijst met deze instellingen.

#### <a name="windows-10-kiosk-is-generally-available----3594661----"></a>Windows 10-kiosk is algemeen beschikbaar <!-- 3594661  -->
In deze update is de Kiosk-functie in Windows 10 en hoger algemeen beschikbaar. Zie [Kiosk-instellingen voor Windows 10 (en hoger)](../configuration/kiosk-settings.md) voor alle instellingen die u kunt toevoegen en configureren.

#### <a name="contact-sharing-via-bluetooth-is-removed-in-device-restrictions--device-owner-for-android-enterprise----3598396-----"></a>Contactpersonen delen via Bluetooth wordt verwijderd uit Apparaatbeperkingen > Apparaateigenaar voor Android Enterprise <!-- 3598396   -->
Wanneer u een apparaatbeperkingsbeleid voor Android Enterprise-apparaten maakt, is de instelling **Contactpersoon delen via Bluetooth** beschikbaar. In deze update is de instelling **Contactpersoon delen via Bluetooth** verwijderd (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen > Apparaateigenaar** voor Profieltype > **Algemeen**). 

De instelling **Contactpersoon delen via Bluetooth** wordt niet ondersteund voor het beheer van Android Enterprise-apparaateigenaren. Wanneer deze instelling wordt verwijderd, heeft dit dus geen invloed op apparaten of tenants, zelfs als deze instelling is ingeschakeld en geconfigureerd in uw omgeving.

Ga naar [Met Android Enterprise-apparaatinstellingen functies toestaan of beperken](../configuration/device-restrictions-android-for-work.md) voor de huidige lijst met instellingen.

Van toepassing op: Android Enterprise-apparaateigenaar

### <a name="device-management"></a>Apparaatbeheer

#### <a name="selective-wipe-support-for-wip-without-enrollment-devices----1434452---"></a>Ondersteuning voor selectief wissen voor WIP Without Enrollment-apparaten <!-- 1434452 -->
Met Windows Information Protection Without Enrollment (WIP-WE) kunnen klanten hun bedrijfsgegevens op Windows 10-apparaten beveiligen zonder gebruik te maken van volledige MDM-inschrijving. Zodra documenten met WIP-WE-beleid zijn beveiligd, kunnen de beschermde gegevens selectief worden gewist door een Intune-beheerder. Door een gebruiker en een apparaat te selecteren en een wisaanvraag te versturen, worden alle gegevens onbruikbaar die met het WIP-WE-beleid zijn beschermd. Vanuit Intune in de Azure-portal selecteert u hiervoor **Mobiele app** > **App selectief wissen**.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="new-operational-logs-and-ability-to-send-logs-to-azure-monitor-services----3762211----"></a>Nieuwe operationele logboeken en de mogelijkheid om logboeken te verzenden met Azure Monitor-services <!-- 3762211  -->
Intune beschikt over ingebouwde logboekregistratie waarmee gebeurtenissen worden bijgehouden als wijzigingen worden aangebracht. Deze update bevat nieuwe functies voor logboekregistratie, waaronder: 
- Operationele logboeken (preview), waarin details over gebruikers en apparaten die zich hebben geregistreerd worden weergegeven, inclusief geslaagde en mislukte pogingen.
- Deze auditlogboeken en operationele logboeken kunnen worden verzonden naar Azure Monitor-services, inclusief Storage Accounts, Event Hubs, en Log Analytics. Met deze services kunt u opslaan, analytics als Splunk en QRadar gebruiken en visualisaties van uw logboekregistratiegegevens verkrijgen.

In [Logboekgegevens verzenden naar Storage, Event Hubs of Log Analytics in Intune](../review-logs-using-azure-monitor.md) vindt u meer informatie over deze functie.

### <a name="skip-more-setup-assistant-screens-on-an-ios-dep-device----2687509----"></a>Meer Setup Assistant-schermen overslaan op een iOS-DEP-apparaat <!-- 2687509  -->
Naast de schermen die u op dit moment kunt overslaan, kunt u instellen dat iOS DEP-apparaten de volgende schermen in de Setup-assistent overslaan wanneer een gebruiker het apparaat registreert: Weergavetoon, Privacy, Android-migratie, Startknop, iMessage en FaceTime, Onboarding, Migratie weergeven, Weergave, Schermtijd, Software-update, SIM-installatie.
Als u wilt kiezen welke schermen moeten worden overgeslagen, gaat u naar **Apparaatinschrijving** > **Apple-inschrijving** > **Tokens voor inschrijvingsprogramma** > kies een token > **Profielen** > kies een profiel > **Eigenschappen** > **Setup Assistant aanpassen** > kies **Verbergen** voor schermen die u wilt overslaan > **OK**.
Als u een nieuw profiel maakt of een profiel bewerkt, moeten de geselecteerde skip-schermen worden gesynchroniseerd met de Apple MDM-server. Gebruikers kunnen de opdracht tot een handmatige synchronisatie van de apparaten geven, zodat er geen vertraging in het ophalen van de profielwijzigingen is.

#### <a name="android-enterprise-app-we-app-deployment----1171203---"></a>Android Enterprise APP WE-app-implementatie <!-- 1171203 -->
Voor Android-apparaten in een niet-geregistreerd APP-WE-implementatiescenario (App Protection Policy Without Enrollment), gebruikt u de beheerde Google Play Store om store-apps en LOB-apps te implementeren bij gebruikers. In het bijzonder kunt u eindgebruikers voorzien van een app-catalogus en een installatie waarbij het niet langer nodig is dat eindgebruikers de beveiligingsstatus van hun apparaten versoepelen door installaties uit onbekende bronnen toe te staan. Bovendien biedt dit implementatiescenario een verbeterde eindgebruikerservaring.

<!-- ########################## -->
## <a name="week-of-january-14-2019"></a>De week van 14 januari 2019

### <a name="preview-of-support-for-android-corporate-owned-fully-managed-devices----1574342----"></a>Voorbeeld van volledig beheerde, zakelijke Android-apparaten <!-- 1574342  -->
Intune ondersteunt nu volledig beheerde Android-apparaten, een scenario waarin apparaten 'zakelijk eigendom' zijn en nauw worden beheerd door de IT-afdeling en gekoppeld zijn aan afzonderlijke gebruikers. Hierdoor kunnen beheerders het hele apparaat beheren, een uitgebreide reeks beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen en gebruikers beperken tot de installatie van apps uit de beheerde Google Play Store. Zie [Intune-inschrijving van volledig beheerde Android-apparaten instellen](../enrollment/android-fully-managed-enroll.md) en [Uw toegewezen apparaten of volledig beheerde apparaten inschrijven](../enrollment/android-dedicated-devices-fully-managed-enroll.md) voor meer informatie.  Let op: deze functie wordt momenteel als preview aangeboden. Sommige Intune-mogelijkheden, zoals certificaten, naleving en voorwaardelijke toegang, zijn momenteel niet beschikbaar voor volledig beheerde Android-gebruikersapparaten.

<!-- ########################## -->
## <a name="week-of-january-7-2019"></a>De week van 7 januari 2019

### <a name="app-management"></a>Appbeheer

#### <a name="intune-app-pin----2298397---"></a>Pincode voor de Intune-app <!-- 2298397 -->
Als IT-beheerder kunt u nu het aantal dagen configureren dat een eindgebruiker kan wachten voordat zijn pincode voor de Intune-app moet worden gewijzigd. De nieuwe instelling is *Pincode opnieuw instellen na aantal dagen* en is beschikbaar in Azure Portal als u **Intune** > **Client-apps** > **App-beveiligingsbeleid** > **Beleid maken** > **Instellingen** > **Toegangsvereisten** kiest. Deze functie is beschikbaar voor [iOS](../apps/app-protection-policy-settings-ios.md)- en [Android](../apps/app-protection-policy-settings-android.md)-apparaten en biedt ondersteuning voor een positief geheel getal.


#### <a name="intune-device-reporting-fields----2748738---"></a>Rapportvelden voor Intune-apparaat <!-- 2748738 -->
Intune biedt aanvullende velden voor apparaatrapporten, waaronder de registratie-id van de app, de Android-fabrikant, het model, de versie van de beveiligingspatch en het iOS-model. In Intune zijn deze velden beschikbaar door **Client-apps** > **App-beveiligingsstatus** te selecteren en vervolgens **App-beveiligingsrapport: iOS, Android** te kiezen. Bovendien helpen deze parameters u de lijst **Toestaan** te configureren voor de apparaatfabrikant (Android), evenals de lijst **Toestaan** voor het apparaatmodel (Android en iOS) en de versie-instellingen van de minimale Android-beveiligingspatch. 


### <a name="device-configuration"></a>Apparaatconfiguratie

#### <a name="administrative-templates-are-in-public-preview-and-moved-to-their-own-configuration-profile----3322847---"></a>Beheersjablonen zijn in openbare preview en verplaatst naar hun eigen configuratieprofiel <!-- 3322847 -->

Beheersjablonen in Intune (**Apparaatconfiguratie** > **Beheersjablonen**) zijn momenteel in openbare preview. Bij deze update:

- Beheersjablonen omvatten circa 300 instellingen die kunnen worden beheerd in Intune. Eerder bestonden deze instellingen alleen in de editor voor groepsbeleid.
- Beheersjablonen zijn beschikbaar in openbare preview.
- Beheersjablonen worden verplaatst van **Apparaatconfiguratie** > **Beheersjablonen** naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies als **Platform** **Windows 10 en hoger** > kies in **Profieltype** **Beheersjablonen**.
- Rapportage is ingeschakeld

Ga naar [Windows 10 templates to configure group policy settings](../configuration/administrative-templates-windows.md) (Windows 10-sjablonen voor het configureren van instellingen voor groepsbeleid) voor meer informatie over deze functie.

Van toepassing op: Windows 10 en hoger

#### <a name="use-smime-to-encrypt-and-sign-multiple-devices-for-a-user-----1333642---"></a>S/MIME gebruiken om meerdere apparaten van een gebruiker te versleutelen en ondertekenen  <!-- 1333642 -->
Deze update bevat een S/MIME-e-mailversleuteling met een nieuw profiel voor een geïmporteerd certificaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > selecteer het platform > profieltype **Geïmporteerd PKCS-certificaat**). In Intune kunt u certificaten importeren in PFX-indeling. Intune kan deze certificaten dan leveren aan meerdere apparaten die zijn geregistreerd door één gebruiker. Dit omvat ook:
- Het systeemeigen iOS-e-mailprofiel ondersteunt het inschakelen van S/MIME-versleuteling met behulp van geïmporteerde certificaten in de PFX-indeling.
- De systeemeigen e-mail-app op Windows Phone 10-apparaten gebruikt automatisch het S/MIME-certificaat.
- De persoonlijke certificaten kunnen worden afgeleverd op meerdere platformen. Maar niet alle e-mail-apps ondersteunen S/MIME.
- Op andere platformen moet u mogelijk de mail-app handmatig configureren om S/MIME in te schakelen.  
- E-mail-apps die ondersteuning bieden voor S/MIME-versleuteling, kunnen het ophalen van certificaten voor S/MIME-e-mailversleuteling verwerken op een manier die een MDM niet kan ondersteunen, zoals het lezen van het certificaatarchief van de uitgever.
Zie [S/MIME overview to sign and encrypt email](../protect/certificates-s-mime-encryption-sign.md) (S/MIME voor e-mailondertekening en -versleuteling) voor meer informatie over deze functie.
Ondersteund in: Windows, Windows Phone 10, macOS, iOS, Android

#### <a name="new-options-to-automatically-connect-and-persist-rules-when-using-dns-settings-on-windows-10-and-later-devices----1333665-2999078---"></a>Nieuwe opties om automatisch verbinding te maken en regels te behouden met DNS-instellingen in Windows 10 en hoger <!-- 1333665, 2999078 -->
Op apparaten met Windows 10 en hoger kunt u een VPN-configuratieprofiel maken dat een lijst DNS-servers bevat om domeinen om te zetten, zoals contoso.com. Deze update bevat nieuwe instellingen voor naamomzetting: (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **Windows 10 en hoger** als platform > kies **VPN** als profieltype > **DNS-instellingen** >**Toevoegen**): 
- **Automatisch verbinding maken**: Als deze optie is **ingeschakeld**, maakt het apparaat automatisch verbinding met VPN wanneer een apparaat een domein oproept dat u invoert, bijvoorbeeld contoso.com.
- **Permanent**: Standaard zijn alle NRPT-tabelregels voor Naamomzettingsbeleid (NRPT) actief zolang het apparaat is verbonden met behulp van dit VPN-profiel. Wanneer deze instelling is **ingeschakeld** voor een NRPT-regel, blijft de regel actief op het apparaat, zelfs wanneer de VPN-verbinding wordt verbroken. De regel blijft totdat het VPN-profiel is verwijderd of totdat de regel handmatig wordt verwijderd, wat mogelijk is met behulp van PowerShell.
In [Windows 10 VPN-instellingen](../configuration/vpn-settings-windows-10.md) worden instellingen beschreven. 

#### <a name="use-trusted-network-detection-for-vpn-profiles-on-windows-10-devices----1500165---"></a>Detectie van vertrouwde netwerken gebruiken voor VPN-profielen in Windows 10-apparaten <!-- 1500165 -->
Wanneer u gebruikmaakt van detectie van vertrouwde netwerken, kunt u voorkomen dat VPN-profielen automatisch een VPN-verbinding maken wanneer de gebruiker zich al op een vertrouwd netwerk bevindt. Met deze update kunt u DNS-achtervoegsels toevoegen om detectie van vertrouwde netwerken in te schakelen op apparaten met Windows 10 en hoger (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** als platform en **VPN** als profieltype).
In [VPN-instellingen voor Windows 10](../configuration/vpn-settings-windows-10.md) worden de huidige VPN-instellingen vermeld.

#### <a name="manage-windows-holographic-for-business-devices-used-by-multiple-users----1907917-1063203---"></a>Windows Holographic for Business-apparaten beheren die worden gebruikt door meerdere gebruikers <!-- 1907917, 1063203 -->
U kunt momenteel gedeelde pc-instellingen configureren op Windows 10- en Windows Holographic for Business-apparaten met een aangepaste OMA-URI-instelling. Met deze update wordt een nieuw profiel toegevoegd om instellingen voor gedeelde apparaten te configureren (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Gedeeld apparaat met meerdere gebruikers**).
Ga naar [Intune settings to manage shared devices](../configuration/shared-user-device-settings.md) (Intune-instellingen voor het beheren van gedeelde apparaten) voor meer informatie over deze functie.
Van toepassing op: Windows 10 en hoger, Windows Holographic for Business

#### <a name="new-windows-10-update-settings---2626030--2512994----"></a>Nieuwe Windows 10-update-instellingen <!--2626030  2512994  -->
Voor uw [Windows 10-update-ringen](../protect/windows-update-for-business-configure.md) kunt u het volgende configureren:
- **Gedrag van automatische updates** : gebruik de nieuwe optie *Standaardinstellingen opnieuw instellen* om de oorspronkelijke instellingen voor automatische updates te herstellen op een Windows 10-computer waarop de *update van oktober 2018* is geïnstalleerd
- **Blokkeren dat gebruikers Windows-updates kunnen onderbreken**: configureer een nieuwe instelling voor software-updates waarmee u kunt toestaan of blokkeren dat gebruikers de installatie van updates kunnen onderbreken via de *Instellingen* op hun computer. 

#### <a name="ios-email-profiles-can-use-smime-signing-and-encryption----2662949---"></a>iOS-e-mailprofielen kunnen gebruikmaken van S/MIME-ondertekening en versleuteling <!-- 2662949 -->
U kunt een e-mailprofiel maken dat verschillende instellingen bevat. Deze update bevat onder andere S/MIME-instellingen die kunnen worden gebruikt voor de ondertekening en versleuteling van e-mailcommunicatie op iOS-apparaten (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform en **E-mail** als profieltype).
In [Configuratie-instellingen voor iOS-e-mail](../configuration/email-settings-ios.md) worden de instellingen vermeld.

#### <a name="some-bitlocker-settings-support-windows-10-pro-edition---2727036---"></a>Sommige BitLocker-instellingen ondersteunen Windows 10 Pro<!-- 2727036 -->
U kunt een configuratieprofiel maken waarmee Endpoint Protection-instellingen op Windows 10-apparaten wordt ingesteld, waaronder BitLocker. Met deze update wordt voor sommige BitLocker-instellingen ondersteuning toegevoegd voor Windows 10 Professional. Ga naar [Instellingen voor de beveiliging van eindpunten voor Windows 10](../protect/endpoint-protection-windows-10.md#windows-encryption) om deze beveiligingsinstellingen te bekijken.

#### <a name="shared-device-configuration-is-renamed-to-lock-screen-message-for-ios-devices-in-the-azure-portal---2809362---"></a>In Azure Portal is de naam Configuratie voor gedeelde apparaten voor iOS-apparaten gewijzigd in Bericht voor vergrendelingsscherm<!-- 2809362 -->
Wanneer u een configuratieprofiel voor iOS-apparaten maakt, kunt u de instelling **Configuratie voor gedeelde apparaten** toevoegen, zodat er specifieke tekst op het vergrendelingsscherm wordt weergegeven. Deze update bevat onder andere de volgende wijzigingen: 
- De instellingen voor **Configuratie voor gedeelde apparaten** in de Azure-portal worden hernoemd naar 'Vergrendelingsschermbericht (alleen onder supervisie)' (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > kies **iOS** als platform > kies **Apparaatfuncties** als profieltype > **Vergrendelingsschermbericht**).
- Wanneer u vergrendelingsschermberichten toevoegt, kunt u een serienummer, apparaatnaam of een andere apparaatspecifieke waarde als variabele invoegen in **Informatie over de assettag** en **Voetnoot voor het vergrendelingsscherm** . U kunt bijvoorbeeld `Device name: {{devicename}}` of `Serial number is {{serialnumber}}` invoeren met accolades. De lijst [iOS-tokens](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat de beschikbare tokens die kunnen worden gebruikt.
Het gedeelte [Instellingen om berichten op het vergrendelingsscherm weer te geven](../configuration/ios-device-features-settings.md#lock-screen-message) bevat de huidige instellingen.

#### <a name="new-app-store-doc-viewing-gaming-device-restriction-settings-added-to-ios-devices----2827760--"></a>Nieuwe App Store-, documentweergave-, gaminginstellingen voor apparaatbeperking toegevoegd aan iOS-apparaten <!-- 2827760-->
In **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **Apparaatbeperkingen** voor profieltype > **App Store, documentweergave, gaming** zijn de volgende instellingen toegevoegd: Beheerde apps toestaan om contacten naar niet-beheerde contactenaccounts te schrijven Niet-beheerde apps toestaan om beheerde contactenaccounts te lezen Als u de instellingen wilt weergeven, gaat u naar [iOS-apparaatbeperkingen](../configuration/device-restrictions-ios.md#app-store-doc-viewing-gaming).

#### <a name="new-notification-hints-and-keyguard-settings-to-android-enterprise-device-owner-devices----3201839-3201843---"></a>Nieuwe instellingen voor meldingen, hints en keyguard voor Android Enterprise-apparaten in zakelijk eigendom <!-- 3201839 3201843 -->
Deze update omvat verschillende nieuwe functies in Android Enterprise-apparaten wanneer deze worden uitgevoerd in zakelijk eigendom. Als u deze functies wilt gebruiken, gaat u naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Android Enterprise** > in **Profieltype** kiest u **Alleen zakelijk eigendom** > **Apparaatbeperkingen**.

Nieuwe functies omvatten: 

- Systeemmeldingen uitschakelen, waaronder binnenkomende oproepen, systeemwaarschuwingen, systeemfouten en meer.
- Suggestie om zelfstudies en tips over te slaan voor apps die voor de eerste keer worden geopend.
- Geavanceerde keyguard-instellingen uitschakelen, bijvoorbeeld de camera, meldingen, ontgrendelen met vingerafdruk en meer.


Ga naar [Android Enterprise device restriction settings](../configuration/device-restrictions-android-for-work.md) (Apparaatbeperkingsinstellingen voor Android Enterprise-apparaten) om de instellingen wilt bekijken.

#### <a name="android-enterprise-device-owner-devices-can-use-always-on-vpn-connections----3202194---"></a>Android Enterprise-apparaten in zakelijk eigendom kunnen AlwaysOn-VPN-verbindingen gebruiken <!-- 3202194 -->
In deze update kunt u ingeschakelde VPN-verbindingen gebruiken op Android Enterprise-apparaten in zakelijk eigendom. Altijd ingeschakelde VPN-verbindingen blijven verbonden en maken direct opnieuw verbinding wanneer gebruikers hun apparaat ontgrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. U kunt de verbinding ook in de vergrendelingsmodus zetten. Hiermee wordt al het netwerkverkeer geblokkeerd totdat de VPN-verbinding actief is.
U vindt altijd ingeschakelde VPN in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Android Enterprise** voor platform > **Apparaatbeperkingen** voor apparaten in zakelijk eigendom > **Connectiviteit**. Ga naar [Android Enterprise device restriction settings](../configuration/device-restrictions-android-for-work.md) (Apparaatbeperkingsinstellingen voor Android Enterprise-apparaten) om de instellingen wilt bekijken.

#### <a name="new-setting-to-end-processes-in-task-manager-on-windows-10-devices----3285177---"></a>Nieuwe instelling om processen in Taakbeheer in Windows 10-apparaten te beëindigen <!-- 3285177 --> 
Deze update omvat een nieuwe instelling om processen via Taakbeheer in Windows 10-apparaten te beëindigen. Met behulp van een apparaatconfiguratieprofiel (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > als **Platform** kiest u **Windows 10** > in **Profieltype** kiest u **Apparaatbeperkingen** > **Algemene** instellingen) kunt u deze instellingen toestaan of blokkeren.
Ga naar [Apparaatbeperkingsinstellingen voor Windows 10-apparaten](../configuration/device-restrictions-windows-10.md) als u de instellingen wilt bekijken.
Van toepassing op: Windows 10 en hoger

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="more-detailed-enrollment-restriction-failure-messaging----3111564---"></a>Gedetailleerdere berichten over fouten bij inschrijvingsbeperking <!-- 3111564 -->
Er komen meer gedetailleerdere foutberichten beschikbaar wanneer er niet wordt voldaan de inschrijvingsbeperkingen. Als u deze berichten wilt bekijken, gaat u naar **Intune** > **Probleemoplossing** en bekijkt u het tabel Inschrijvingsfouten. Zie de [lijst met mislukte inschrijvingen](help-desk-operators.md#enrollment-failure-reference) voor meer informatie.

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="tenant-status-dashboard-----1124854---"></a>Dashboard Tenantstatus  <!-- 1124854 -->
De nieuwe [pagina Tenantstatus](tenant-status.md) biedt één locatie waar u de status en gerelateerde details voor uw tenant kunt bekijken.  Het dashboard is opgedeeld in vier gebieden:
- **Tenantdetails**: bevat uiteenlopende informatie, zoals uw tenantnaam en -locatie, uw MDM-instantie, het totale aantal ingeschreven apparaten in uw tenant en uw aantal licenties. Dit gedeelte bevat ook de huidige servicerelease voor uw tenant.
- **Connectorstatus**: bevat informatie over de beschikbare connectors die u hebt geconfigureerd. Daarnaast kunt u die connectors vermelden die u nog niet hebt ingeschakeld.  
   Op basis van de huidige status worden de connectors gemarkeerd als In orde, Waarschuwing of Niet in orde. Selecteer een connector die u gedetailleerd wilt analyseren om details of aanvullende informatie voor de connector weer te geven.
- **Intune Service Health**: bevat gedetailleerde informatie over actieve incidenten of storingen voor uw tenant. De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center.
- **Intune-nieuws** : bevat actieve berichten voor uw tenant. Berichten omvatten onder andere meldingen wanneer uw tenant de nieuwste functies van Intune ontvangt.  De informatie in deze sectie wordt rechtstreeks opgehaald uit het Office Message Center.

#### <a name="new-help-and-support-experience-in-company-portal-for-windows-10----1488939--"></a>Nieuw Help en ondersteuning-ervaring in de bedrijfsportal voor Windows 10 <!-- 1488939-->
Gebruikers kunnen de nieuwe pagina Help en ondersteuning van Bedrijfsportal gebruiken om problemen op te lossen en hulp te vragen voor app- en toegangsproblemen. Via deze pagina kunnen gebruikers details uit foutenlogboeken en diagnostisch logboeken mailen en kunnen ze de gegevens van de helpdesk van de organisatie vinden. Daarnaast bevat de pagina een gedeelte met veelgestelde vragen met koppelingen naar de relevante Intune-documentatie. 

#### <a name="new-help-and-support-experience-for-intune------3307080---"></a>Nieuwe Help en ondersteuning-ervaring voor Intune   <!-- #3307080 -->
De nieuwe Help en ondersteuning-ervaring wordt de komende paar dagen uitgerold naar alle tenants. Deze nieuwe ervaring is beschikbaar voor Intune en is toegankelijk wanneer de Intune-blades in [Azure Portal](https://portal.azure.com/) worden gebruikt.
Met de nieuwe ervaring kunt u uw probleem in uw eigen woorden beschrijven en informatie over probleemoplossing en op internet gevonden informatie over het oplossen van het probleem ontvangen. Deze oplossingen worden aangeboden via een op regels gebaseerde machine learning-algoritme, dat wordt aangestuurd door zoekvragen van gebruikers. Naast informatie die specifiek is voor problemen kunt u gebruikmaken van de nieuwe werkstroom voor het openen van een ondersteuningsvraag via e-mail of telefoon. Deze nieuwe ervaring vervangt de vorige Help en ondersteuning-ervaring die bestaat uit een statistische verzameling vooraf geselecteerde opties die zijn gebaseerd op het gebied van de console waarin u zich bevindt wanneer u Help en ondersteuning opent. Zie [Ondersteuning voor Microsoft Intune krijgen](get-support.md) voor meer informatie.

### <a name="role-based-access-control"></a>Op rollen gebaseerd toegangsbeheer

#### <a name="scope-tags-for-apps----1081941---"></a>Bereiktags voor apps <!-- 1081941 -->
U kunt bereiktags maken om de toegang voor rollen en apps te beperken. U kunt een bereiktag toevoegen aan een app, zodat alleen personen met rollen die ook zijn toegewezen aan de bereiktag, toegang tot de app hebben. Momenteel kunnen er geen bereiktags worden toegewezen aan apps die vanuit de beheerde Google Play Store aan Intune zijn toegevoegd of aan apps die met behulp van het Apple Volume Purchase Program (VPP) zijn aangeschaft (er zijn wel plannen voor ondersteuning in de toekomst). Zie [Bereiktags gebruiken om beleidsregels te filteren](scope-tags.md) voor meer informatie.

## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](../includes/intune-notices.md)]
