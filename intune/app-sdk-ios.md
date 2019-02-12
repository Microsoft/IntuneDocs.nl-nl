---
title: Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS
description: Met de Microsoft Intune App SDK voor iOS kunt u Intune-beveiligingsbeleid voor apps (ook wel APP- of MAM-beleid genoemd) opnemen in uw systeemeigen iOS-app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: eaffed2af38e269000dd951cec536e1f80be705f
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841348"
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Ontwikkelaarshandleiding voor Microsoft Intune App SDK voor iOS

> [!NOTE]
> U kunt eerst het artikel [Aan de slag met Intune App SDK](app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.

Met de Microsoft Intune App SDK voor iOS kunt u Intune-beveiligingsbeleid voor apps (ook wel **APP-** of **MAM-beleid** genoemd) opnemen in uw systeemeigen iOS-app. Een MAM-app is geïntegreerd met de Intune App SDK. IT-beheerders kunnen app-beveiligingsbeleid implementeren in uw mobiele app wanneer die actief door Intune wordt beheerd.

## <a name="prerequisites"></a>Vereisten

* U hebt een Mac OS-computer met OS X 10.8.5 of hoger nodig, waarop Xcode 9 of hoger is geïnstalleerd.

* Uw app moet geschikt zijn voor iOS 10 of hoger.

* Controleer de [Licentievoorwaarden voor de Intune App SDK voor iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS.pdf). Druk een kopie van de licentievoorwaarden af voor uw administratie. Door de Intune App SDK voor iOS te downloaden en gebruiken, gaat u akkoord met deze licentievoorwaarden.  Als u deze niet accepteert, mag u de software niet gebruiken.

* Download de bestanden voor de Intune App SDK voor iOS op [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios).

## <a name="whats-in-the-sdk"></a>Inhoud van de SDK

De ontwikkelaarshandleiding voor Intune App SDK voor iOS bevat een statische bibliotheek, resourcebestanden, API-headers, een PLIST-bestand met foutopsporingsinstellingen en een configuratiehulpprogramma. Client-apps omvatten mogelijk de bronbestanden en kunnen statisch aan de meeste bibliotheken voor beleidsafdwinging worden gekoppeld. Geavanceerde APP-functies van Intune worden afgedwongen met behulp van API's.

In deze handleiding wordt ingegaan op het gebruik van de volgende onderdelen van de Intune App SDK voor iOS:

* **libIntuneMAM.a**: de statische bibliotheek van Intune App SDK. Als uw app geen extensies gebruikt, moet u deze bibliotheek aan uw project koppelen, zodat uw app gebruik kan maken van Intune Client Application Management.

* **IntuneMAM.framework**: het Intune App SDK-framework. Koppel dit framework aan uw project, zodat uw app Intune Client Application Management kan gebruiken. Gebruik het framework in plaats van de statische bibliotheek als uw app gebruikmaakt van extensies, zodat uw project niet meerdere exemplaren van de statische bibliotheek maakt.

* **IntuneMAMResources.bundle**: een bundel met resources waarvan de SDK afhankelijk is.

* **Kopteksten**: beschrijft de Intune App SDK-API's. Als u een API gebruikt, moet u het headerbestand met de API opnemen. De volgende header-bestanden bevatten de API's, gegevenstypen en protocollen die de Intune App SDK beschikbaar maken voor ontwikkelaars:

    * IntuneMAMAppConfig.h
    * IntuneMAMAppConfigManager.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMDefs.h
    * IntuneMAMEnrollmentDelegate.h
    * IntuneMAMEnrollmentManager.h
    * IntuneMAMEnrollmentStatus.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMLogger.h
    * IntuneMAMPolicy.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMPolicyManager.h
    * IntuneMAMVersionInfo.h

Ontwikkelaars kunnen de inhoud van de bovenstaande headers beschikbaar maken door IntuneMAM.h te importeren


## <a name="how-the-intune-app-sdk-works"></a>De werking van de Intune App SDK

Het doel van de Intune App SDK voor iOS is het toevoegen van beheermogelijkheden voor iOS-toepassingen met minimale codewijzigingen. Hoe minder codewijzigingen, hoe sneller u een mobiele app op de markt kunt brengen zonder negatieve gevolgen voor de consistentie en stabiliteit van de app.


## <a name="build-the-sdk-into-your-mobile-app"></a>De SDK in uw mobiele app inbouwen

Als u de Intune App SDK wilt inschakelen, voert u de volgende stappen uit:

1. **Optie 1 (aanbevolen)**: koppel `IntuneMAM.framework` aan uw project. Sleep `IntuneMAM.framework` naar de lijst met **ingesloten binaire bestanden** van het projectdoel.

   > [!NOTE]
   > Als u het framework gebruikt, moet u de simulatorarchitecturen handmatig verwijderen uit het universele framework voordat u uw app naar de App Store verzendt. Zie [Uw app naar de App Store verzenden](#Submit-your-app-to-the-App-Store) voor meer informatie.

   **Optie 2**: maak een koppeling naar de `libIntuneMAM.a`-bibliotheek. Sleep de bibliotheek `libIntuneMAM.a` naar de lijst **Linked Frameworks and Libraries** van het projectdoel.

    ![Intune App SDK iOS: gekoppelde frameworks en bibliotheken](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Voeg `-force_load {PATH_TO_LIB}/libIntuneMAM.a` toe aan een van de volgende ter vervanging van `{PATH_TO_LIB}` met de Intune App SDK-locatie:
   * de buildconfiguratie-instelling `OTHER_LDFLAGS` van het project
   * De **Other Linker Flags** van de gebruikersinterface van Xcode

     > [!NOTE]
     > Voor het zoeken naar `PATH_TO_LIB`, selecteert u het bestand `libIntuneMAM.a` en kiest u **Get Info** in het menu **File**. Kopieer en plak de informatie onder **Where** (het pad) in het gedeelte **General** van het venster **Info**.

     Voeg de resourcebundel `IntuneMAMResources.bundle` toe aan het project door deze binnen **Build Phases** naar **Copy Bundle Resources** te slepen.

     ![Intune App SDK iOS: bundelresources kopiëren](./media/intune-app-sdk-ios-copy-bundle-resources.png)

2. Voeg de volgende iOS-frameworks toe aan het project:  
    * MessageUI.framework  
    * Security.framework  
    * MobileCoreServices.framework  
    * SystemConfiguration.framework  
    * libsqlite3.tbd  
    * libc++.tbd  
    * ImageIO.framework  
    * LocalAuthentication.framework  
    * AudioToolbox.framework  
    * QuartzCore.framework  
    * WebKit.framework

3. Schakel het delen van sleutelhangers in (indien nog niet ingeschakeld) door in elk projectdoel op **Capabilities** te klikken en de schakelaar **Keychain Sharing** in te schakelen. Het delen van sleutelhangers is vereist als u wilt doorgaan met de volgende stap.

   > [!NOTE]
   > Uw inrichtingsprofiel moet ondersteuning bieden voor nieuwe waarden voor het delen van sleutelhangers. De toegangsgroepen van de sleutelhanger moeten een jokerteken ondersteunen. U kunt dit controleren door het bestand .mobileprovision in een teksteditor te openen, te zoeken naar **keychain-access-groups** en te controleren of u een jokerteken ziet. Bijvoorbeeld:
   >  ```xml
   >  <key>keychain-access-groups</key>
   >  <array>
   >  <string>YOURBUNDLESEEDID.*</string>
   >  </array>
   >  ```

4. Nadat u het delen van sleutelketens hebt ingeschakeld, volgt u deze stappen voor het maken van een afzonderlijke toegangsgroep waarin de gegevens van de Intune App SDK worden opgeslagen. U kunt een toegangsgroep voor de sleutelketen maken via de gebruikersinterface of met behulp van het rechtenbestand. Als u de toegangsgroep voor de sleutelketen maakt met de gebruikersinterface, moet u de onderstaande stappen uitvoeren:

    1. Als uw mobiele app geen toegangsgroepen voor de sleutelketen heeft gedefinieerd, moet u de bundel-id van de app toevoegen als **eerste** groep.
    
    2. Voeg de groep voor de gedeelde sleutelketen `com.microsoft.intune.mam` aan uw bestaande toegangsgroepen toe. De Intune App SDK gebruikt deze toegangsgroepen voor het opslaan van gegevens.
    
    3. Voeg `com.microsoft.adalcache` aan uw bestaande toegangsgroepen toe.
    
        ![Intune App SDK iOS: Sleutelhanger delen](./media/intune-app-sdk-ios-keychain-sharing.png)
    
    4. Als u het rechtenbestand rechtstreeks wilt bewerken om toegangsgroepen voor de sleutelketen te maken, in plaats van met behulp van de Xcode-UI die hierboven wordt weergegeven, voegt u vóór de toegangsgroepen voor de sleutelketen `$(AppIdentifierPrefix)` toe (Xcode doet dit automatisch). Bijvoorbeeld:
    
        - `$(AppIdentifierPrefix)com.microsoft.intune.mam`
        - `$(AppIdentifierPrefix)com.microsoft.adalcache`
    
        > [!NOTE]
        > Een rechtenbestand is een uniek XML-bestand voor uw mobiele toepassing. Het wordt gebruikt om speciale machtigingen en mogelijkheden in uw iOS-app op te geven. Als uw app geen nog een rechtenbestand had, zou het inschakelen van het delen van de sleutelhanger (stap 3) ervoor moeten zorgen dat Xcode er één voor uw app genereert. Zorg ervoor dat de bundel-id van de app het eerste item in de lijst is.

5. Neem elk protocol dat door uw mobiele app wordt doorgegeven aan `UIApplication canOpenURL` op in de matrix `LSApplicationQueriesSchemes` van het bestand Info.plist van uw app. Zorg ervoor dat u de wijzigingen opslaat voordat u doorgaat met de volgende stap.

6. Als uw app nog geen Face ID gebruikt, controleert u of de [sleutel NSFaceIDUsageDescription Info.plist](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251-SW75) is geconfigureerd met een standaardbericht. Dit is vereist om gebruikers in iOS te laten weten hoe de app Face ID gaat gebruiken. Met een beleidsinstelling voor de beveiliging van een Intune-app kan Face ID worden gebruikt als methode voor toegang tot apps wanneer deze instelling is geconfigureerd door de IT-beheerder.

7. Gebruik het hulpprogramma IntuneMAMConfigurator dat is opgenomen in de [SDK-opslagplaats](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) om de configuratie van de Info.plist van uw app te voltooien. Het hulpprogramma heeft drie parameters:

   |Eigenschap|Gebruik|
   |---------------|--------------------------------|
   |- i |  `<Path to the input plist>` |
   |- e | `<Path to the entitlements file>` |
   |- o |  (optioneel) `<Path to the output plist>` |

Als de parameter 'o' niet wordt opgegeven, wordt in plaats daarvan het invoerbestand gewijzigd. Het hulpprogramma is idempotent en moet telkens worden gestart wanneer er wijzigingen in de Info.plist of rechten van de app zijn aangebracht. U moet ook de meest recente versie van het hulpprogramma downloaden en dat uitvoeren wanneer u de Intune SDK bijwerkt, voor het geval de config-vereisten voor Info.plist in de nieuwste versie zijn gewijzigd.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Azure Active Directory Authentication Library (ADAL) configureren

De Intune App SDK gebruikt [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) voor scenario's voor verificatie en voorwaardelijk starten. De SDK maakt ook gebruik van ADAL om de gebruikers-id te registreren bij de MAM-service om zonder scenario's voor apparaatinschrijving beheertaken uit te voeren.

Normaal gesproken vereist ADAL dat apps worden geregistreerd via Azure Active Directory (AAD) en een unieke id (de zogeheten client-id) en andere id's worden opgehaald om de beveiliging te waarborgen van de tokens die aan de app worden toegekend. Tenzij anders opgegeven, gebruikt de Intune App SDK standaardregistratiewaarden voor de communicatie met Azure AD.  

Als uw app al ADAL gebruikt om gebruikers te verifiëren, moet de app de bestaande registratiewaarden gebruiken en de standaardwaarden van de Intune App SDK overschrijven. Dit zorgt ervoor dat eindgebruikers niet tweemaal om verificatie wordt gevraagd (eenmaal door de Intune App SDK en een tweede maal door de app).

Het verdient aanbeveling dat uw app is gekoppeld aan de [meest recente versie van ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) op de hoofdvertakking. De Intune App SDK gebruikt momenteel de brokervertakking van ADAL om ondersteuning te bieden voor apps waarvoor voorwaardelijke toegang is vereist. (Deze apps zijn daarom afhankelijk van de Microsoft Authenticator-app.) Maar de SDK is nog steeds compatibel met de hoofdvertakking van de ADAL. Gebruik de vertakking die geschikt is voor uw app.

### <a name="link-to-adal-binaries"></a>Koppelen aan binaire ADAL-bestanden

Volg de onderstaande stappen om uw app te koppelen aan de binaire ADAL-bestanden:

1. Download de [Azure Active Directory Authentication Library (ADAL) voor Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) vanuit GitHub en volg hierna de [instructies](https://github.com/AzureAD/azure-activedirectory-library-for-objc#download) voor het downloaden van ADAL met Git-submodules of CocoaPods.

2. Voeg het ADAL-framework (optie 1) of de statische bibliotheek (optie 2) aan uw project toe.

3. Als uw app geen toegangsgroepen voor de sleutelhanger heeft gedefinieerd, moet u de bundel-id van de app toevoegen als eerste groep.

4. Schakel eenmalige aanmelding van ADAL in door `com.microsoft.adalcache` en `com.microsoft.workplacejoin` toe te voegen aan de sleutelketenrechten.

5. Als u de gedeelde cachesleutelketengroep van ADAL expliciet instelt, zorg er dan voor dat deze is ingesteld op `<appidprefix>.com.microsoft.adalcache`. ADAL stelt dit automatisch in tenzij u dit overschrijft. Als u wilt opgeven dat een aangepaste sleutelketengroep `com.microsoft.adalcache` vervangt, geeft u dat op in het bestand Info.plist onder 'IntuneMAMSettings', met de sleutel `ADALCacheKeychainGroupOverride`.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>ADAL-instellingen voor de Intune App SDK configureren

Als uw app al ADAL voor verificatie gebruikt en eigen ADAL-instellingen heeft, kunt u afdwingen dat de Intune App SDK dezelfde instellingen gebruikt tijdens verificatie met Azure Active Directory. Dit zorgt ervoor dat de app de gebruiker niet tweemaal om verificatie vraagt. Zie [Instellingen configureren voor de Intune App SDK](#configure-settings-for-the-intune-app-sdk) voor informatie over het invullen van de volgende instellingen:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Als uw app ADAL al gebruikt, zijn de volgende configuraties vereist:

1. Geef in het bestand Info.plist van het project onder de woordenlijst **IntuneMAMSettings** met de sleutelnaam `ADALClientId` de client-id op die voor ADAL-aanroepen moet worden gebruikt.

2. Geef onder de woordenlijst **IntuneMAMSettings** met de sleutelnaam `ADALAuthority` ook de Azure AD-instantie op.

3. Geef onder de woordenlijst **IntuneMAMSettings** met de sleutelnaam `ADALRedirectUri` ook de omleidings-URI op die voor ADAL-aanroepen moet worden gebruikt. U kunt in plaats daarvan ook `ADALRedirectScheme` opgeven als de omleidings-URI van de toepassing de indeling `scheme://bundle_id` heeft.

Apps kunnen bovendien deze Azure AD-instellingen tijdens runtime overschrijven. U kunt dit doen door de eigenschappen `aadAuthorityUriOverride`, `aadClientIdOverride` en `aadRedirectUriOverride` voor de instantie `IntuneMAMPolicyManager` in te stellen.

4. Zorg ervoor dat de stappen om uw iOS-app te machtigen voor het app-beschermingsbeleid (APP) zijn gevolgd. Gebruik de instructies in de handleiding [Aan de slag met de Intune-SDK](https://docs.microsoft.com/intune/app-sdk-get-started#next-steps-after-integration) onder 'Uw app toegang geven tot de Intune-app-beveiliging (optioneel)'.  

> [!NOTE]
> De methode Info.plist wordt aanbevolen voor alle instellingen die statisch zijn en niet tijdens runtime hoeven te worden vastgesteld. Waarden die zijn toegewezen aan de `IntuneMAMPolicyManager`-eigenschappen hebben voorrang op eventuele bijbehorende waarden die zijn opgegeven in de Info.plist en blijven behouden ook nadat de app opnieuw wordt gestart. De SDK blijft deze gebruiken voor het inchecken van beleid totdat de gebruiker wordt uitgeschreven of de waarden worden gewist of gewijzigd.

### <a name="if-your-app-does-not-use-adal"></a>Als uw app ADAL niet gebruikt

Zoals eerder vermeld, maakt de Intune App SDK gebruik van [Azure Active Directory Authentication Library](https://github.com/AzureAD/azure-activedirectory-library-for-objc) voor scenario's voor verificatie en voorwaardelijk starten. Het is ook afhankelijk van ADAL dat de gebruikers-id wordt geregistreerd bij de MAM-service om zonder scenario's voor apparaatinschrijving beheertaken uit te voeren. Als **uw app ADAL niet gebruikt** als eigen verficatiemechanisme, zorgt de Intune App SDK voor de standaardwaarden voor ADAL-parameters en de verificatie met Azure AD. U hoeft geen waarden op te geven voor de hierboven vermelde ADAL-instellingen. Elk verificatiemechanisme, indien aanwezig, dat wordt gebruikt door uw app wordt weergegeven boven op de ADAL-prompts. 

## <a name="configure-settings-for-the-intune-app-sdk"></a>De instellingen van de Intune App SDK configureren

U kunt de **IntuneMAMSettings**-woordenlijst gebruiken die deel uitmaakt van het bestand Info.plist van de toepassing voor het configureren en instellen van de Intune App SDK. Als de IntuneMAMSettings-woordenlijst niet zichtbaar is in het bestand Info.plist, moet u deze maken.

U kunt in de woordenlijst IntuneMAMSettings de volgende ondersteunde instellingen toevoegen om de Intune App SDK te configureren.

Sommige van deze instellingen zijn mogelijk in eerdere secties aan bod gekomen en sommige zijn niet op alle apps van toepassing.

Instelling  | Type  | Definitie | Vereist?
--       |  --   |   --       |  --
ADALClientId  | Tekenreeks  | De Azure AD-client-id van de app. | Vereist als de app gebruikmaakt van ADAL. |
ADALAuthority | Tekenreeks | De Azure AD-instantie van de app wordt gebruikt. U moet uw eigen omgeving gebruiken waar AAD-accounts zijn geconfigureerd. | Vereist als de app gebruikmaakt van ADAL. Als deze waarde niet aanwezig is, wordt een standaard Intune-waarde gebruikt.|
ADALRedirectUri  | Tekenreeks  | De Azure AD-omleidings-URI van de app. | ADALRedirectUri of ADALRedirectScheme is vereist als de app gebruikmaakt van ADAL.  |
ADALRedirectScheme  | Tekenreeks  | Het Azure AD-omleidingsschema van de app. Dit kan worden gebruikt in plaats van ADALRedirectUri als de omleidings-URI van de app de notatie `scheme://bundle_id` heeft. | ADALRedirectUri of ADALRedirectScheme is vereist als de app gebruikmaakt van ADAL. |
ADALLogOverrideDisabled | Boolean-waarde  | Geeft aan of de SDK alle ADAL-logboeken (inclusief ADAL-aanroepen van de app, indien van toepassing) naar een eigen logboekbestand routeert. De standaardwaarde is NO (Nee). De waarde is YES (Ja) als de app een eigen ADAL-logboek wil aanroepen. | Optioneel. |
ADALCacheKeychainGroupOverride | Tekenreeks  | Hiermee wordt aangegeven welke sleutelhangergroep voor de ADAL-cache moet worden gebruikt in plaats van 'com.microsoft.adalcache'. Houd er rekening mee dat deze niet het voorvoegsel app-id heeft. Dat wordt tijdens runtime als voorvoegsel toegevoegd aan de gegeven tekenreeks. | Optioneel. |
AppGroupIdentifiers | Stringarray  | Matrix van toepassingsgroepen van het gedeelte com.apple.security.application-groups met rechten van de app. | Vereist als de app toepassingsgroepen gebruikt. |
ContainingAppBundleId | Tekenreeks | Deze geeft de bundel-id aan van de extensie waarvan app onderdeel uitmaakt. | Vereist voor iOS-extensies. |
DebugSettingsEnabled| Boolean-waarde | Indien ingesteld op YES (Ja), kan testbeleid binnen de bundel Instellingen worden toegepast. Apps moeten *niet* worden verzonden als deze instelling is ingeschakeld. | Optioneel. De standaardwaarde is No (Nee).|
MainNibFile <br> MainNibFile~ipad  | Tekenreeks  | Deze instelling moet de bestandsnaam van de hoofd-nib van de app hebben.  | Vereist als de app MainNibFile in definieert in Info.plist. |
MainStoryboardFile <br> MainStoryboardFile~ipad  | Tekenreeks  | Deze instelling moet de bestandsnaam van het hoofd-storyboard van de app hebben. | Vereist als de app UIMainStoryboardFile definieert in Info.plist. |
MAMPolicyRequired| Boolean-waarde| Dit geeft aan of de app wordt geblokkeerd en niet kan worden gestart als de app geen Intune APP-beleid heeft. De standaardwaarde is NO (Nee). <br><br> Opmerking: apps kunnen niet worden verzonden naar de App Store als MAMPolicyRequired is ingesteld op YES (Ja). | Optioneel. De standaardwaarde is No (Nee).|
MAMPolicyWarnAbsent | Boolean-waarde| Deze geeft aan of de app tijdens het opstarten een waarschuwing verzendt naar de gebruiker als de app geen Intune APP-beleid heeft. <br><br> Opmerking: het is gebruikers nog steeds toegestaan de app zonder beleid te gebruiken, nadat ze de waarschuwing hebben genegeerd. | Optioneel. De standaardwaarde is No (Nee). |
MultiIdentity | Boolean-waarde| Hiermee wordt aangegeven of de app in staat is om met meerdere identiteiten te werken. | Optioneel. De standaardwaarde is No (Nee). |
SplashIconFile <br> SplashIconFile~ ipad | Tekenreeks  | Geeft het pictogrambestand van het Intune-opstartscherm aan. | Optioneel. |
SplashDuration | Getal | Minimale tijdsduur in seconden voor de weergave van het Intune-opstartscherm bij het opstarten van de app. De standaardwaarde is 1,5 seconden. | Optioneel. |
BackgroundColor| Tekenreeks| Hiermee geeft u de achtergrondkleur aan voor het opstartscherm en het scherm waarop een pincode moet worden ingevoerd. Accepteert een hexadecimale RGB-tekenreeks in de vorm van #XXXXXX, waarbij elke X een teken van 0-9 of A-F kan zijn. Het hekje kan worden weggelaten.   | Optioneel. De standaardkleur is lichtgrijs. |
ForegroundColor| Tekenreeks| Hiermee geeft u de voorgrondkleur aan voor het opstartscherm en het scherm waarop een pincode moet worden ingevoerd, voor bijvoorbeeld tekstkleur. Accepteert een hexadecimale RGB-tekenreeks in de vorm #XXXXXX, waarbij elke X een teken van 0-9 of A-F kan zijn. Het hekje kan worden weggelaten.  | Optioneel. De standaardkleur is zwart. |
AccentColor | Tekenreeks| Hiermee geeft u de accentkleur aan voor schermen waarop een pincode moet worden ingevoerd, voor bijvoorbeeld knoptekst en de kleur voor het markeren van vakken. Accepteert een hexadecimale RGB-tekenreeks in de vorm van #XXXXXX, waarbij elke X een teken van 0-9 of A-F kan zijn. Het hekje kan worden weggelaten.| Optioneel. De standaardkleur is systeemblauw. |
MAMTelemetryDisabled| Boolean-waarde| Hiermee wordt aangegeven dat de SDK geen telemetriegegevens verzendt naar de back-end.| Optioneel. De standaardwaarde is No (Nee). |
MAMTelemetryUsePPE | Boolean-waarde | Hiermee wordt aangegeven of MAM SDK gegevens verstuurt naar de back-end van de PPE-telemetrie. Gebruik deze instelling als u wilt testen of uw apps voldoen aan Intune-beleid zodat telemetrietestgegevens niet worden verward met klantgegevens. | Optioneel. De standaardwaarde is No (Nee). |
MaxFileProtectionLevel | Tekenreeks | Optioneel. Hiermee kan de app de maximale `NSFileProtectionType` opgeven die hierdoor kan worden ondersteund. Deze waarde overschrijft het beleid dat is verzonden door de service als het niveau hoger is dan wat door de toepassing kan worden ondersteund. Mogelijke waarden: `NSFileProtectionComplete`, `NSFileProtectionCompleteUnlessOpen`, `NSFileProtectionCompleteUntilFirstUserAuthentication`, `NSFileProtectionNone`.|
OpenInActionExtension | Boolean-waarde | Ingesteld op Ja voor uitbreidingen van Open-In-acties. Zie de sectie Gegevens delen via UIActivityViewController voor meer informatie. |
WebViewHandledURLSchemes | Matrix van tekenreeksen | Hiermee worden de URL-schema's opgegeven die door de webweergave van de app worden afgehandeld. | Verplicht, indien de app gebruikmaakt van een webweergave die URL's afhandelt via koppelingen en/of JavaScript. |

## <a name="receive-app-protection-policy"></a>Beleid voor app-beveiliging ontvangen

### <a name="overview"></a>Overzicht

Apps moeten een aanvraag voor registratie bij de Intune MAM-service starten om beveiligingsbeleid voor Intune-apps te ontvangen. Apps kunnen worden geconfigureerd in de Intune-console om beveiligingsbeleid voor apps met of zonder apparaatregistratie te ontvangen. Met beveiligingsbeleid voor apps zonder registratie, ook wel **APP-WE** of MAM-WE genoemd, kunnen apps worden beheerd door Intune zonder dat het apparaat hoeft te worden geregistreerd in Intune Mobile Device Management (MDM). In beide gevallen is registratie bij de Intune MAM-service vereist om beleid te ontvangen.

### <a name="apps-that-use-adal"></a>Apps die gebruikmaken van ADAL

Apps die al gebruikmaken van ADAL, moeten de `registerAndEnrollAccount`-methode in de `IntuneMAMEnrollmentManager`-instantie aanroepen nadat de gebruiker is geverifieerd:

```objc
/*
 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;
```

Door de methode `registerAndEnrollAccount` aan te roepen, kan het gebruikersaccount door de SDK worden geregistreerd en kan de app namens dit account worden ingeschreven. Als de inschrijving om een bepaalde reden mislukt, onderneemt de SDK 24 uur later automatisch een nieuwe poging om de app in te schrijven. Om fouten te kunnen opsporen, kan de app via een gemachtigde [meldingen](#Status-result-and-debug-notifications) ontvangen over de resultaten van een inschrijvingsaanvraag.

Nadat deze API is aangeroepen, blijft de app gewoon functioneren. Als de inschrijving is gelukt, laat de SDK aan de gebruiker weten dat de app opnieuw moet worden opgestart. Op dat moment kan de gebruiker de app onmiddellijk opnieuw opstarten.

```objc
[[IntuneMAMEnrollmentManager instance] registerAndEnrollAccount:@”user@foo.com”];
```

### <a name="apps-that-do-not-use-adal"></a>Apps waarvoor geen gebruik wordt gemaakt van ADAL

Apps waarbij de gebruiker niet wordt aangemeld met ADAL kunnen nog wel app-beveiligingsbeleid ontvangen van de Intune MAM-service door de API aan te roepen, waardoor de SDK die verificatie afhandelt. Apps moeten deze techniek gebruiken wanneer ze een gebruiker niet hebben geverifieerd met Azure AD, maar wel beveiligingsbeleid voor apps moeten ophalen ter bescherming van gegevens. Deze situatie kan zich voordoen wanneer een andere verificatieservice wordt gebruikt voor het aanmelden bij de app, of de app helemaal geen aanmelding vereist. Om dit te bereiken, kan de met app de methode `loginAndEnrollAccount` in de `IntuneMAMEnrollmentManager`-instantie worden aangeroepen:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;
```

Door deze methode aan te roepen, vraagt de SDK de gebruiker om referenties als er geen token wordt gevonden. De SDK probeert dan de app bij de Intune MAM-service in te schrijven namens het opgegeven gebruikersaccount. De methode kan worden aangeroepen met 'nil' als identiteit. In dat geval zal de SDK een inschrijving uitvoeren met de bestaande beheerde gebruiker op het apparaat (in het geval van MDM) of zal de gebruiker worden gevraagd een gebruikersnaam op te geven als er geen bestaande gebruiker is gevonden.

Als de inschrijving mislukt, moet de app overwegen om deze API op een later tijdstip opnieuw aan te roepen, afhankelijk van de foutinformatie. De app kan via een gemachtigde [meldingen](#Status-result-and-debug-notifications) ontvangen over de resultaten van een inschrijvingsaanvraag.

Nadat deze API is aangeroepen, blijft de app gewoon functioneren. Als de inschrijving is gelukt, laat de SDK aan de gebruiker weten dat de app opnieuw moet worden opgestart.

Voorbeeld:
```objc
[[IntuneMAMEnrollmentManager instance] loginAndEnrollAccount:@”user@foo.com”];
```

### <a name="let-intune-handle-authentication-and-enrollment-at-launch"></a>Intune de verificatie en registratie laten afhandelen bij het opstarten

Als u wilt dat de Intune SDK alle verificatie met behulp van de ADAL en de registratie afhandelt voordat uw app klaar is met opstarten, en uw app altijd APP-beleid vereist, hoeft u geen `loginAndEnrollAccount`-API te gebruiken. U kunt gewoon de twee instellingen hieronder op Ja instellen in de IntuneMAMSettings-woordenlijst in de Info.plist van de app.

Instelling  | Type  | Definitie |
--       |  --   |   --       |  
AutoEnrollOnLaunch| Boolean-waarde| Hiermee geeft u op of de app moet proberen automatisch in te schrijven bij het starten als een bestaande beheerde identiteit wordt gedetecteerd en dit nog niet is gebeurd. De standaardwaarde is NO (Nee). <br><br> Opmerking: als er geen beheerde identiteit wordt gevonden of er geen geldig token voor de identiteit beschikbaar is in de ADAL-cache, dan zal de poging om in te schrijven zonder melding en zonder te vragen om referenties mislukken, tenzij in de app MAMPolicyRequired tevens is ingesteld op YES (Ja). |
MAMPolicyRequired| Boolean-waarde| Deze geeft aan of de app is geblokkeerd en niet kan worden gestart als de app geen Intune-beveiligingsbeleid voor apps heeft. De standaardwaarde is NO (Nee). <br><br> Opmerking: apps kunnen niet worden verzonden naar de App Store als MAMPolicyRequired is ingesteld op YES (Ja). Wanneer MAMPolicyRequired wordt ingesteld op YES, moet AutoEnrollOnLaunch ook worden ingesteld op YES. |

Als u deze optie voor uw app kiest, hoeft u er niet voor te zorgen dat uw app opnieuw opstart na registratie.

### <a name="deregister-user-accounts"></a>De registratie van gebruikersaccounts ongedaan maken

Voordat een gebruiker wordt afmeldt bij een app, moet de registratie van de gebruiker bij de SDK ongedaan worden gemaakt door de app. Zo kunt u er zeker van zijn:

1. Dat niet langer wordt geprobeerd om inschrijvingen voor het gebruikersaccount uit te voeren.

2. Het app-beveiligingsbeleid wordt verwijderd.

3. Als de app een (optionele) selectieve wisbewerking uitvoert, worden alle zakelijke gegevens verwijderd.

Voordat de gebruiker wordt afgemeld, moet de app de volgende methode aanroepen in de `IntuneMAMEnrollmentManager`-instantie:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune APP AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */
(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Deze methode moet worden aangeroepen voordat de Azure AD-tokens van het gebruikersaccount worden verwijderd. De SDK heeft de AAD-token(s) van het gebruikersaccount nodig om namens de gebruiker specifieke aanvragen naar de Intune MAM-service te sturen.

Als de app automatisch zakelijke gegevens van de gebruiker verwijdert, kan de vlag `doWipe` worden ingesteld op false (onwaar). Anders kan de app een selectieve wisbewerking door de SDK initiëren. Dit heeft tot gevolg dat de gemachtigde voor selectief wissen van de app wordt aangeroepen.

Voorbeeld:
```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

## <a name="status-result-and-debug-notifications"></a>Status-, resultaat- en foutopsporingsmeldingen

De app kan status-, resultaat- en foutopsporingsmeldingen ontvangen over de volgende aanvragen voor de Intune MAM-service:

* Inschrijvingsaanvragen
* Aanvragen voor beleidsupdates
* Uitschrijvingsaanvragen

De meldingen worden weergegeven via gemachtigdenmethoden in `IntuneMAMEnrollmentDelegate.h`:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;
```

Deze gemachtigdenmethoden retourneren een object `IntuneMAMEnrollmentStatus` met de volgende gegevens:

* De identiteit van het account dat is gekoppeld aan de aanvraag
* Een statuscode die het resultaat van de aanvraag aanduidt
* Een fouttekenreeks met een beschrijving van de statuscode
* Een `NSError`-object. Dit object wordt gedefinieerd in `IntuneMAMEnrollmentStatus.h`, samen met de specifieke statuscodes die kunnen worden geretourneerd.

> [!NOTE]
> Deze informatie is uitsluitend voor foutopsporing. Er moet geen bedrijfslogica in uw app zijn gebaseerd op deze meldingen. Deze informatie kan naar een telemetrieservice worden verzonden om fouten te kunnen opsporen en voor bewakingsdoeleinden.

### <a name="sample-code"></a>Voorbeeldcode

Hier volgen voorbeeldimplementaties van de gemachtigdenmethoden:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus*)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}
```

## <a name="application-restart"></a>Toepassing opnieuw starten

Wanneer een app voor de eerste keer MAM-beleid ontvangt, moet deze opnieuw worden opgestart om de vereiste hooks toe te passen. Als u wilt aangeven dat de app opnieuw moet worden opgestart, biedt de SDK een gemachtigdenmethode in `IntuneMAMPolicyDelegate.h`.

```objc
 - (BOOL) restartApplication
```

De geretourneerde waarde van deze methode geeft voor de SDK aan of de app het vereiste opnieuw opstarten moet afhandelen:

* Als true (waar) wordt geretourneerd, moet de app het opnieuw opstarten afhandelen.

* Als false (onwaar) wordt geretourneerd, start de SDK de app opnieuw op nadat deze methode wordt geretourneerd. De SDK geeft onmiddellijk een dialoogvenster weer waarin de gebruiker wordt gevraagd de app opnieuw op te starten.

## <a name="customize-your-apps-behavior-with-apis"></a>Uw app-gedrag aanpassen met API's

De Intune App SDK heeft verschillende API's die u kunt aanroepen met informatie over het Intune APP-beleid voor apps dat op de app is geïmplementeerd. U kunt met deze gegevens uw app-gedrag aanpassen. De onderstaande tabel bevat informatie over sommige essentiële Intune-klassen die u gaat gebruiken.

Klasse | Beschrijving
----- | -----------
IntuneMAMPolicyManager.h | De klasse IntuneMAMPolicyManager beschrijft het Intune APP-beleid voor apps dat in de toepassing wordt geïmplementeerd. Beschrijft met name API's die nuttig zijn voor [Meerdere identiteiten inschakelen](app-sdk-ios.md#enable-multi-identity-optional). |
IntuneMAMPolicy.h | De klasse IntuneMAMPolicy beschrijft enkele MAM-beleidsinstellingen die van toepassing zijn op de app. Deze beleidsinstellingen worden beschreven, zodat de app de gebruikersinterface kan aanpassen. De meeste beleidsinstellingen worden afgedwongen door de SDK en niet door de app. Het enige dat de app moet implementeren is het besturingselement Opslaan als. Deze klasse beschrijft een aantal API's die nodig zijn voor het implementeren van Opslaan als. |
IntuneMAMDataProtectionManager.h | De klasse IntuneMAMFileProtectionManager beschrijft API’s die de app kan gebruiken voor het expliciet beveiligen van bestanden en mappen op basis van een opgegeven identiteit. De identiteit kan worden beheerd door Intune of onbeheerd blijven, en de SDK past het juiste MAM-beleid toe. Het gebruik van deze klasse is optioneel. |
IntuneMAMDataProtectionManager.h | De klasse IntuneMAMDataProtectionManager beschrijft API’s die de app kan gebruiken voor het beveiligen van gegevensbuffers op basis van een opgegeven identiteit. De identiteit kan worden beheerd door Intune of onbeheerd blijven, en de SDK past de versleuteling op correcte wijze toe. |

## <a name="implement-save-as-controls"></a>Besturingselementen voor Opslaan als implementeren

IT-beheerders kunnen met Intune selecteren op welke opslaglocaties een beheerde app gegevens kan opslaan. Apps kunnen de toegestane opslaglocaties bij de Intune App SDK opvragen met de `isSaveToAllowedForLocation`-API in `IntuneMAMPolicy.h`.

Voordat apps beheerde gegevens kunnen opslaan in een opslagruimte in de cloud of op een lokale locatie, moeten deze met de `isSaveToAllowedForLocation`-API controleren of de IT-beheerder toestaat dat de gegevens daar mogen worden opgeslagen.

Bij het gebruik van de `isSaveToAllowedForLocation`-API moeten apps de UPN voor de opslaglocatie doorgeven als deze beschikbaar is.

### <a name="supported-save-locations"></a>Ondersteunde opslaglocaties

De `isSaveToAllowedForLocation`-API biedt constanten om te controleren of de IT-beheerder toestaat dat gegevens worden opgeslagen op de volgende locaties die in `IntuneMAMPolicy.h` zijn gedefinieerd:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Apps moeten de constanten in de `isSaveToAllowedForLocation` gebruiken om te controleren of gegevens kunnen worden opgeslagen op locaties die worden beschouwd als 'beheerd', zoals OneDrive voor Bedrijven, of als 'persoonlijk'. Daarnaast moet de API worden gebruikt wanneer de app niet kan controleren of een locatie wordt 'beheerd' of 'persoonlijk' is.

Locaties die bekend zijn als 'persoonlijk' worden vertegenwoordigd door de `IntuneMAMSaveLocationOther`-constante.

De `IntuneMAMSaveLocationLocalDrive`-constante moet worden gebruikt wanneer de app gegevens opslaat op een locatie op het lokale apparaat.

## <a name="share-data-via-uiactivityviewcontroller"></a>Gegevens delen via UIActivityViewController

Vanaf versie 8.0.2 kan de Intune App SDK `UIActivityViewController`-acties filteren zodanig dat alleen door Intune beheerde locaties voor delen beschikbaar zijn om te selecteren. Dit gedrag wordt gecontroleerd via het overdrachtsbeleid voor toepassingsgegevens.

### <a name="copy-to-actions"></a>'Kopiëren naar'-acties

Wanneer er via de `UIActivityViewController` en `UIDocumentInteractionController` gegevens worden gedeeld, geeft iOS 'Kopiëren naar'-acties weer voor elke toepassing die het openen van gedeelde documenten ondersteunt. Toepassingen declareren de documenttypen die worden ondersteund via de instelling `CFBundleDocumentTypes` in Info.plist. Deze manier van delen is niet meer beschikbaar als het beleid verbiedt om met onbeheerde applicaties te delen. Ter vervanging moet een gebruiker een niet-UI Action-extensie toevoegen aan hun toepassing en deze koppelen met de Intune App SDK. De Action-extensie fungeert als stub. De SDK implementeert het gedrag voor bestandsdeling. Volg de onderstaande stappen:

1. In uw toepassing moet ten minste één schemeURL zijn gedefinieerd onder `CFBundleURLTypes` in Info.plist.

2. Uw toepassing en extensie moeten ten minste één app-groep delen en de app-groep moet worden vermeld in de matrix `AppGroupIdentifiers` in de IntuneMAMSettings-woordenlijst van de app en de extensie.

3. Noem de Action-extensie 'Open in', gevolgd door de naam van de toepassing. U kunt indien nodig de Info.plist lokaliseren.

4. Voorzie in een sjabloonpictogram voor de extensie zoals wordt beschreven in [Apple-documentatie voor ontwikkelaars](https://developer.apple.com/ios/human-interface-guidelines/extensions/sharing-and-actions/). U kunt ook het hulpprogramma IntuneMAMConfigurator gebruiken om deze pictogrammen te genereren vanuit de .app-directory van de toepassing. Voer hiervoor het volgende uit:

    ```bash
    IntuneMAMConfigurator -generateOpenInIcons /path/to/app.app -o /path/to/output/directory
    ```

5. Voeg onder IntuneMAMSettings in de Info.plist van de extensie een Booleaanse instelling toe met de naam `OpenInActionExtension` en de waarde YES.

6. Configureer de `NSExtensionActivationRule` ter ondersteuning van een enkel bestand en alle typen uit de `CFBundleDocumentTypes` van de toepassing die worden voorafgegaan door `com.microsoft.intune.mam`. Als de toepassing bijvoorbeeld public.text en public.image ondersteunt, is de activeringsregel:

    ```objc
    SUBQUERY (
        extensionItems,
        $extensionItem,
        SUBQUERY (
            $extensionItem.attachments,
            $attachment,
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.text” ||
            ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image”).@count == 1
    ).@count == 1
    ```

### <a name="update-existing-share-and-action-extensions"></a>Bestaande Share- en Action-extensies bijwerken

Als uw app al Share- of Action-extensies bevat, moet de `NSExtensionActivationRule` worden aangepast om Intune-typen toe te staan. Voeg voor elk door de extensie ondersteund type een aanvullend type voorafgegaan door `com.microsoft.intune.mam` toe. Als de bestaande activeringsregel bijvoorbeeld de volgende is:  

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data"
    ).@count > 0
).@count > 0
```

moet deze worden gewijzigd in:

```objc
SUBQUERY (
    extensionItems,
    $extensionItem,
    SUBQUERY (
        $extensionItem.attachments,
        $attachment,
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "public.data" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.url" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.plain-text" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.image" ||
        ANY $attachment.registeredTypeIdentifiers UTI-CONFORMS-TO "com.microsoft.intune.mam.public.data
    ).@count > 0
).@count > 0
```

> [!NOTE]
> Het hulpprogramma IntuneMAMConfigurator kan worden gebruikt om de Intune-typen toe te voegen aan de activeringsregel. Als uw bestaande activeringsregel de vooraf gedefinieerde tekenreeksconstanten gebruikt (bijvoorbeeld NSExtensionActivationSupportsFileWithMaxCount, NSExtensionActivationSupportsText, enz.), kan het predicaat van de syntaxis erg complex worden. Het hulpprogramma IntuneMAMConfigurator kan ook worden gebruikt om de activeringsregel te converteren van de tekenreeksconstanten in een predicate tekenreeks terwijl de Intune-typen worden toegevoegd.

### <a name="what-the-ui-should-look-like"></a>Hoe de gebruikersinterface eruit moet zien

Oude gebruikersinterface:

![gegevens delen - oude iOS- gebruikersinterface voor delen](./media/sharing-UI-old.png)

Nieuwe gebruikersinterface:

![gegevens delen - nieuwe iOS-gebruikersinterface voor delen](./media/sharing-UI-new.png)

## <a name="enable-targeted-configuration-appmam-app-config-for-your-ios-applications"></a>Gericht configuratiebeleid (APP-/ MAM-app-configuratie) voor uw iOS-toepassingen inschakelen

Via een op MAM gerichte configuratie (tevens bekend als MAM-app-configuratie) kan een app configuratiegegevens ontvangen via de Intune SDK. De indeling en varianten van deze gegevens moeten door de eigenaar/ontwikkelaar van de app worden gedefinieerd en gecommuniceerd aan de klanten van Intune.

Intune-beheerders kunnen configuratiegegevens gericht implementeren via Intune Azure Portal en de Intune Graph-API. Vanaf versie 7.0.1 van de Intune App SDK voor iOS kunnen apps die deelnemen aan op MAM gerichte configuratie, op MAM gerichte configuratiegegevens ontvangen via de MAM-service. De configuratiegegevens van de toepassing worden via onze MAM-service direct naar de app gepusht en niet via het MDM-kanaal. De Intune App SDK biedt een klasse voor toegang tot gegevens die uit deze consoles worden opgehaald. De volgende items zijn vereist:

* De app moet worden geregistreerd bij de Intune MAM-service voordat u toegang krijgt tot de gebruikersinterface van op MAM gerichte configuratie. Zie [Beleid voor app-beveiliging ontvangen](#receive-app-protection-policy) voor meer informatie.

* Voeg `IntuneMAMAppConfigManager.h` toe aan het bronbestand van uw app.

* Verstuur een aanroep naar `[[IntuneMAMAppConfigManager instance] appConfigForIdentity:]` om het AppConfig-object op te halen.

* Verstuur een aanroep naar de juiste selector voor het object `IntuneMAMAppConfig`. Als de sleutel van uw toepassing bijvoorbeeld een tekenreeks is, moet u `stringValueForKey` of `allStringsForKey` gebruiken. Zie `IntuneMAMAppConfig.h` voor een gedetailleerde beschrijving van retourwaarden en foutcondities.

Zie [Graph API Reference](https://developer.microsoft.com/graph/docs/concepts/overview) (Naslaginformatie over Graph API) voor meer informatie over de mogelijkheden van Graph API.

Als u meer wilt weten over het maken van een op MAM gericht app-configuratiebeleid in iOS, raadpleegt u het onderwerp over op MAM gerichte app-configuratie in [How to use Microsoft Intune app configuration policies for iOS](https://docs.microsoft.com/intune/app-configuration-policies-use-ios) (App-configuratiebeleid van Microsoft Intune voor iOS gebruiken).

## <a name="telemetry"></a>Telemetrie

De Intune App SDK voor iOS verzamelt standaard telemetriegegevens van de volgende typen gebeurtenissen:

* **Het starten van de app**: om Microsoft Intune meer inzicht te geven in het MAM-gebruik van de app per beheertype (MAM met MDM-, MAM zonder MDM-inschrijving, enzovoort).

* **Inschrijvingsaanroepen**: om Microsoft Intune inzicht te geven in het slagingspercentage en andere meetwaarden van inschrijvingsaanroepen vanaf de client.

* **Intune-acties**: voor de diagnose van problemen en ter waarborging van de Intune-functionaliteit, wordt informatie verzameld over de Intune SDK-acties.

> [!NOTE]
> Als u ervoor kiest geen telemetriegegevens van de Intune App SDK naar Microsoft Intune te verzenden, moet u het vastleggen van telemetriegegevens in de SDK uitschakelen. Stel de eigenschap `MAMTelemetryDisabled` in op YES in de IntuneMAMSettings-woordenlijst.

## <a name="enable-multi-identity-optional"></a>Meerdere identiteiten inschakelen (optioneel)

Standaard past de SDK een beleid toe op de gehele app. Meerdere identiteiten is een MAM-functie waarmee u beleid kunt toepassen per identiteit. Hiervoor wordt meer deelname van een app vereist dan bij andere MAM-functies.

De app moet aan de app-SDK melden wanneer de actieve identiteit zal worden gewijzigd. De SDK meldt ook aan de app wanneer er een identiteitswijziging is vereist. Op dit moment wordt slechts één beheerde identiteit ondersteund. Nadat de gebruiker het apparaat of de app inschrijft, gebruikt de SDK deze identiteit en beschouwt de SDK deze identiteit als de primaire beheerde identiteit. Andere gebruikers in de app worden beschouwd als niet-beheerd met onbeperkte beleidsinstellingen.

Een identiteit wordt gewoon als een tekenreeks gedefinieerd. Identiteiten zijn niet hoofdlettergevoelig. In identiteitsaanvragen die door de SDK worden geretourneerd, wordt mogelijk niet hetzelfde gebruik van hoofd- en kleine letters toegepast als bij het instellen van de identiteit.

### <a name="identity-overview"></a>Overzicht van identiteit

Een identiteit is gewoon de gebruikersnaam van een account (zoals user@contoso.com). Ontwikkelaars kunnen de identiteit van de app instellen op de volgende niveaus:

* **Procesidentiteit**: stelt de identiteit voor het hele proces in en wordt hoofdzakelijk gebruikt voor toepassingen met één identiteit. Deze identiteit is van invloed op alle taken, bestanden en de gebruikersinterface.

* **Gebruikersinterface-identiteit**: bepaalt welk beleid wordt toegepast op taken van de gebruikersinterface op de hoofdthread zoals knippen/kopiëren/plakken, pincode, verificatie en gegevens delen. De gebruikersinterface-identiteit heeft geen invloed op taken zoals versleuteling en het maken van back-ups.

* **Threadidentiteit**: beïnvloedt welk beleid wordt toegepast op de huidige thread. Deze identiteit is van invloed op alle taken, bestanden en de gebruikersinterface.

Het is de verantwoordelijkheid van de app om de identiteiten juist in te stellen, ongeacht of de gebruiker wordt beheerd of niet.

Elke thread heeft op ieder moment een effectieve identiteit voor gebruikersinterface- en bestandstaken. Dit is de identiteit die wordt gebruikt om te controleren welk beleid er eventueel moet worden toegepast. Als de identiteit 'geen identiteit' is of als de gebruiker niet wordt beheerd, wordt er geen beleid toegepast. De volgende diagrammen tonen hoe de effectieve identiteiten worden bepaald.

  ![Intune App SDK iOS: proces voor bepaling identiteit](./media/ios-thread-identities.png)

### <a name="thread-queues"></a>Threadwachtrijen

Apps verzenden vaak asynchrone en synchrone taken naar threadwachtrijen. De SDK onderschept GCD-aanroepen (Grand Central Dispatch) en koppelt de huidige threadidentiteit aan de verzonden taken. Wanneer de taken zijn voltooid, wijzigt de SDK tijdelijk de threadidentiteit in de identiteit die is gekoppeld aan de taak, voltooit de taken en zet vervolgens de oorspronkelijke threadidentiteit terug.


Omdat `NSOperationQueue` bovenop GCD is gebouwd, worden `NSOperations` uitgevoerd op de identiteit van de thread op het tijdstip dat de taken worden toegevoegd aan de `NSOperationQueue`. `NSOperations` of functies die rechtstreeks zijn verzonden via GCD hebben ook de mogelijkheid om de huidige threadidentiteit te wijzigen terwijl ze worden uitgevoerd. Deze identiteit overschrijft de identiteit die is overgenomen van de verzendende thread.

### <a name="file-owner"></a>Bestandseigenaar

De SDK houdt de identiteiten van de lokale bestandseigenaars bij en past op basis daarvan beleid toe. De bestandseigenaar wordt ingesteld wanneer een bestand wordt gemaakt of wordt geopend in de afkapmodus. De eigenaar wordt ingesteld op de effectieve bestandstaakidentiteit van de thread die de taak uitvoert.

Apps kunnen echter de identiteit van de bestandseigenaar ook expliciet instellen met behulp van de `IntuneMAMFilePolicyManager`. Apps kunnen `IntuneMAMFilePolicyManager` gebruiken om de bestandseigenaar op te halen en de gebruikersinterface-identiteit in te stellen voordat de bestandsinhoud wordt weergegeven.

### <a name="shared-data"></a>Gedeelde gegevens

Als de app bestanden maakt die gegevens van beheerde en onbeheerde gebruikers bevatten, is het de verantwoordelijkheid van de app om de gegevens van de beheerde gebruiker te versleutelen. U kunt gegevens versleutelen met de API's `protect` en `unprotect` in `IntuneMAMDataProtectionManager`.

De methode `protect` accepteert een identiteit, die een beheerde of een niet-beheerde gebruiker kan zijn. Als het een beheerde gebruiker is, worden de gegevens versleuteld. Als het een niet-beheerde gebruiker is, wordt een header toegevoegd aan de gegevens waarmee de identiteit wordt gecodeerd, maar worden de gegevens niet versleuteld. U kunt de methode `protectionInfo` gebruiken voor het ophalen van de eigenaar van de gegevens.

### <a name="share-extensions"></a>Share-extensies

Als de app een share-extensie bevat, kan de eigenaar van het item dat wordt gedeeld, worden opgehaald met de methode `protectionInfoForItemProvider` in `IntuneMAMDataProtectionManager`. Als het gedeelde item een bestand is, wordt het instellen van de bestandseigenaar door de SDK afgehandeld. Als het bij het gedeelde item om gegevens gaat, is de app verantwoordelijk voor het instellen van de bestandseigenaar als deze gegevens naar een bestand worden opgeslagen, en voor het aanroepen van de API `setUIPolicyIdentity` voordat de gegevens worden weergegeven in de gebruikersinterface.

### <a name="turn-on-multi-identity"></a>Meerdere identiteiten inschakelen

Alle apps worden standaard beschouwd als apps met één identiteit. De SDK stelt de procesidentiteit in voor de ingeschreven gebruiker. Om ondersteuning voor meerdere identiteiten mogelijk te maken, voegt u een Booleaanse instelling met de naam `MultiIdentity` en de waarde YES toe aan de IntuneMAMSettings-woordenlijst in het bestand Info.plist van de app.

> [!NOTE]
> Wanneer het gebruik van meerdere identiteiten is ingeschakeld, worden de procesidentiteit, de gebruikersinterface-identiteit en de threadidentiteiten op nil ingesteld. De app is verantwoordelijk voor het juist instellen hiervan.

### <a name="switch-identities"></a>Schakelen tussen identiteiten

* **Door app geïnitieerde overschakeling naar een andere identiteit**:

    Bij het starten wordt van apps met meerdere identiteiten verondersteld dat ze worden uitgevoerd onder een onbekend, niet-beheerd account. De voorwaardelijke gebruikersinterface voor opstarten wordt niet uitgevoerd, en er wordt geen beleid afgedwongen op de app. Het is de verantwoordelijkheid van de app om aan de SDK te melden wanneer de identiteit moet worden gewijzigd. Dit gebeurt meestal wanneer de app op het punt staat om gegevens voor een specifiek gebruikersaccount weer te geven.

    Een voorbeeld daarvan is wanneer de gebruiker een document, een postvak of een tabblad in een notitieblok opent. De app moet de SDK op de hoogte stellen voordat het bestand, het postvak of het tabblad wordt geopend. Dit wordt gedaan via de `setUIPolicyIdentity`-API in `IntuneMAMPolicyManager`. Deze API moet worden aangeroepen, ongeacht of het om een beheerde of niet-beheerde gebruiker gaat. Als het een beheerde gebruiker is, voert de SDK de voorwaardelijke startcontroles uit, zoals jailbreakdetectie, pincode en verificatie.

    Het resultaat van de overschakeling naar een andere identiteit wordt asynchroon naar de app geretourneerd via een voltooiingshandler. De app moet het openen van het document, postvak of tabblad uitstellen totdat er een resultaatcode wordt geretourneerd. Als het overschakelen naar een andere identiteit mislukt, moet de app de taak annuleren.

* **Door SDK geïnitieerde overschakeling naar andere identiteit**:

    Soms moet de SDK de app verzoeken om naar een specifieke identiteit over te schakelen. Apps met meerdere identiteiten moeten de `identitySwitchRequired`-methode in `IntuneMAMPolicyDelegate` implementeren om deze aanvraag te verwerken.

    Wanneer deze methode wordt aangeroepen, en indien de app de aanvraag kan afhandelen om naar een opgegeven identiteit over te schakelen, moet de app `IntuneMAMAddIdentityResultSuccess` doorgeven aan de voltooiingshandler. Als de app de aanvraag om naar een andere identiteit over te schakelen niet kan afhandelen, moet de app `IntuneMAMAddIdentityResultFailed` doorgeven aan de voltooiingshandler.

    De app hoeft `setUIPolicyIdentity` niet aan te roepen als reactie op deze aanroep. Als de SDK het nodig acht dat de app moet overschakelen naar een niet-beheerd gebruikersaccount, wordt een lege tekenreeks doorgegeven aan de `identitySwitchRequired`-aanroep.

* **Selectief wissen**:

    Wanneer de app selectief wordt gewist, zal de SDK de `wipeDataForAccount`-methode in `IntuneMAMPolicyDelegate` aanroepen. Het is de verantwoordelijkheid van de app om het opgegeven gebruikersaccount en alle bijbehorende gegevens te verwijderen. De SDK is in staat om alle bestanden te verwijderen waarvan de gebruiker de eigenaar is, en zal dit doen als de app FALSE (onwaar) retourneert als reactie op de aanroep `wipeDataForAccount`.

    Deze methode wordt aangeroepen vanuit een achtergrondthread. De app mag geen waarde retourneren totdat alle gegevens van de gebruiker zijn verwijderd (met uitzondering van bestanden, als de app FALSE retourneert).

## <a name="ios-best-practices"></a>Aanbevolen procedures voor iOS

Hier volgen enkele aanbevolen procedures voor het ontwikkelen voor iOS:

* Het iOS-bestandssysteem is hoofdlettergevoelig. Zorg dat het hoofdlettergebruik juist is voor bestandsnamen zoals `libIntuneMAM.a` en `IntuneMAMResources.bundle`.

* Als Xcode `libIntuneMAM.a` niet kan vinden, kunt u dit probleem oplossen door het pad naar deze bibliotheek toe te voegen in de gekoppelde zoekpaden.

## <a name="faqs"></a>Veelgestelde vragen

### <a name="are-all-of-the-apis-addressable-through-native-swift-or-the-objective-c-and-swift-interoperability"></a>Zijn alle API's adresseerbaar via systeemeigen Swift of via de interoperabiliteit tussen Objective-C en Swift?

De Intune App SDK-API's zijn alleen beschikbaar in Objective-C en bieden geen ondersteuning voor het **systeemeigen** Swift. Swift-interoperabiliteit met Objective-C is vereist.

### <a name="do-all-users-of-my-application-need-to-be-registered-with-the-app-we-service"></a>Moeten alle gebruikers van mijn app worden geregistreerd bij de APP-WE-service?

Nee. In feite hoeven alleen werk- of schoolaccounts te worden geregistreerd bij de Intune App SDK. Apps zijn er verantwoordelijk voor om te bepalen of een account wordt gebruikt in de context van werk of school.

### <a name="what-about-users-that-have-already-signed-in-to-the-application-do-they-need-to-be-enrolled"></a>Wat gebeurt er met gebruikers die zich al bij de app hebben aangemeld? Moeten ze worden ingeschreven?

De toepassing is verantwoordelijk voor het inschrijven van gebruikers nadat ze zijn geverifieerd. De toepassing is ook verantwoordelijk voor het inschrijven van eventuele accounts die aanwezig waren voordat de app MAM-functionaliteit zonder MDM had.

Om dit te bereiken, moet de app gebruikmaken van de `registeredAccounts:`-methode. Deze methode retourneert een NSDictionary met alle accounts die zijn geregistreerd bij de Intune MAM-service. Als bestaande accounts in de app niet op de lijst staan, moet de app deze accounts registreren en inschrijven via `registerAndEnrollAccount:`.

### <a name="how-often-does-the-sdk-retry-enrollments"></a>Hoe vaak probeert de SDK inschrijvingen opnieuw uit te voeren?

De SDK probeert alle eerder mislukte inschrijvingen automatisch opnieuw uit te voeren met een interval van 24 uur. De SDK doet dit om te garanderen dat als de organisatie van een gebruiker MAM heeft ingeschakeld nadat de gebruiker zich heeft aangemeld bij de app, de gebruiker zich kan inschrijven en beleid zal ontvangen.

De SDK stopt met proberen wanneer wordt gedetecteerd dat een gebruiker de app heeft kunnen inschrijven. Dit komt doordat slechts één gebruiker een app op een bepaald moment kan inschrijven. Als de gebruiker wordt uitgeschreven, worden de nieuwe pogingen opnieuw gestart met dezelfde interval van 24 uur.

### <a name="why-does-the-user-need-to-be-deregistered"></a>Waarom moet de registratie van de gebruiker ongedaan worden gemaakt?

De SDK voert regelmatig de volgende acties op de achtergrond uit:

* Als de app nog niet is ingeschreven, probeert deze alle geregistreerde accounts elke 24 uur opnieuw in te schrijven.
* Als de app is ingeschreven, controleert de SDK elke 8 uur of het MAM-beleid is gewijzigd.

Door de registratie van een gebruiker ongedaan te maken, wordt de SDK gewaarschuwd dat de gebruiker de app niet langer gebruikt, en dat de periodiek uitgevoerde gebeurtenissen voor dat gebruikersaccount kunnen worden gestopt. Hierdoor worden indien nodig ook het uitschrijven van de app en een selectieve wisbewerking geactiveerd.

### <a name="should-i-set-the-dowipe-flag-to-true-in-the-deregister-method"></a>Moet ik de doWipe-vlag op true (waar) instellen in de deregister-methode ?

Deze methode moet worden aangeroepen voordat de gebruiker wordt afgemeld bij de app.  Als de gegevens van de gebruiker uit de app worden verwijderd als onderdeel van de afmelding, kan `doWipe` worden ingesteld op false (onwaar). Maar als de app de gegevens van de gebruiker niet daadwerkelijk verwijdert, moet `doWipe` worden ingesteld op true (waar), zodat de SDK de gegevens kan verwijderen.

### <a name="are-there-any-other-ways-that-an-application-can-be-un-enrolled"></a>Zijn er andere manieren om een app uit te schrijven?

Ja, de IT-beheerder kan een opdracht voor selectief wissen verzenden naar de app. Hierdoor wordt de gebruiker uitgeschreven en de registratie ongedaan gemaakt, en worden de gegevens van de gebruiker gewist. De SDK handelt dit scenario automatisch af en verzendt een melding via de gemachtigdenmethode voor uitschrijving.

### <a name="is-there-a-sample-app-that-demonstrates-how-to-integrate-the-sdk"></a>Is er een voorbeeld-app die de integratie van de SDK laat zien?

Ja. Onlangs is het open-source-voorbeeld-app [Wagr voor iOS](https://github.com/Microsoft/Wagr-Sample-Intune-iOS-App) vernieuwd. Wagr is nu ingeschakeld voor app-beveiligingsbeleid met behulp van de Intune App SDK.

## <a name="submit-your-app-to-the-app-store"></a>Uw app naar de App Store verzenden

Zowel de statische bibliotheek als de frameworkbuilds van de Intune App SDK zijn universele binaire bestanden. Dit houdt in dat ze een code hebben voor alle apparaat- en simulatorarchitecturen. Apple weigert apps die naar de App Store worden verzonden als deze simulatorcode bevatten. Bij een compilatie op basis van de statische bibliotheek voor builds die uitsluitend voor apparaten zijn bestemd, wordt de linker automatisch ontdaan van de simulatorcode. Volg de onderstaande stappen om ervoor te zorgen dat alle simulatorcode wordt verwijderd voordat u de app uploadt naar de App Store.

1. Zorg dat `IntuneMAM.framework` zich op uw bureaublad bevindt.

2. Voer deze opdrachten uit:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    De eerste opdracht verwijdert de simulatorarchitecturen uit het bestand DYLIB van het framework. Met de tweede opdracht wordt het bestand DYLIB dat uitsluitend voor apparaten is bestemd, terug gekopieerd naar de frameworkmap.
