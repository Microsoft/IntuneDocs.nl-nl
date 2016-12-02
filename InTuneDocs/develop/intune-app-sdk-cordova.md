---
title: Intune App SDK Cordova-invoegtoepassing | Microsoft Intune
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: karthikaraman
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: af7df3fcf50c3508d495522341bb287c638f40a3
ms.openlocfilehash: 2af369cc44c710789ab65eb25f10602882772019


---
# ﻿<a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune App SDK Cordova-invoegtoepassing

> [!NOTE]
> U kunt desgewenst eerst het artikel [Aan de slag met Intune App SDK](intune-app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.


## <a name="overview"></a>Overzicht

Met de [Intune App SDK Cordova-invoegtoepassing](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam) kunt u de [beheerfuncties voor Intune Mobile App](/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) inschakelen in iOS- en Android-apps die zijn gebouwd met Cordova. De invoegtoepassing biedt ontwikkelaars de mogelijkheid om beveiligingsfuncties voor de Intune-app en -gegevens te integreren in hun op Cordova gebaseerde app.

U zult merken dat u SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. Als u de invoegtoepassing hebt gemaakt in uw mobiele iOS- of Android-app, kan de IT-beheerder via Mobile Application Management (MAM) in Microsoft Intune beleid implementeren dat verschillende functies voor gegevensbescherming biedt. We hebben de invoegtoepassing zodanig ontwikkeld dat de meeste stappen automatisch worden uitgevoerd in het bouwproces voor Cordova. Dat zou het mogelijk moeten maken om uw app snel in te schakelen voor beheer. Volg de onderstaande stappen op basis van uw doelplatform om aan de slag te gaan.




## <a name="whats-supported"></a>Wat wordt ondersteund

### <a name="developer-machines"></a>Machines van ontwikkelaars
* Windows
* Mac OS


### <a name="mobile-app-platforms"></a>Mobiele app-platformen
* Android 4.0+
* iOS

### <a name="intune-mobile-application-management-scenarios"></a>Scenario’s voor Intune Mobile Application Management

* Apparaten die zijn ingeschreven bij Intune MDM
* Apparaten die zijn ingeschreven bij EMM van derden
* Onbeheerde apparaten (niet ingeschreven bij een MDM)

Cordova-apps die zijn gemaakt met de Intune App SDK Cordova-invoegtoepassing kunnen nu Mobile Application Management-beleid (MAM) van Intune ontvangen op apparaten die wel en apparaten die niet zijn ingeschreven in Mobile Device Management (MDM) van Intune.



## <a name="prerequisites"></a>Vereisten

### <a name="technical-prerequisites"></a>Technische vereisten

* **[Alleen android]** Op het apparaat moet altijd de meest recente Microsoft Intune-bedrijfsportal-app zijn geïnstalleerd.


* Versie 0.8.0 of hoger van de [Azure Active Directory Authentication Libraries-invoegtoepassing (ADAL) voor Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) is vereist.
  * **Belangrijk:** Vanwege een [hier](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) opgeslagen Cordova Apache-fout worden apps die al afhankelijk zijn van de invoegtoepassing, niet automatisch bijgewerkt naar de vereiste versie.


### <a name="before-you-install-and-use-microsoft-intune-app-sdk-cordova-plugin-you-must"></a>Voordat u de Microsoft Intune App SDK Cordova-invoegtoepassing installeert en gebruikt, **moet** u:

* De [licentievoorwaarden voor de Intune App SDK Cordova-invoegtoepassing](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam/blob/master/Intune_App_SDK_Cordova_plugin_RTM_license.pdf) doorlezen.

* Een exemplaar van de licentievoorwaarden voor uw administratie afdrukken en bewaren. Door de Intune App SDK Cordova-invoegtoepassing te downloaden en gebruiken, gaat u akkoord met deze licentievoorwaarden.  Als u deze niet accepteert, moet u de software niet gebruiken.


## <a name="quick-start"></a>Snel starten

1. Uw versie van ADAL bijwerken:

    ```
    cordova plugin remove cordova-plugin-ms-adal
    cordova plugin add cordova-plugin-ms-adal@0.8.x
    ```

2. De Intune App SDK Cordova-invoegtoepassing toevoegen:

    ```
    cordova plugin add cordova-plugin-ms-intune-mam
    ```

## <a name="how-to-build-the-plugin-into-your-ios-app"></a>De invoegtoepassing inbouwen in uw iOS-app

U moet een aantal stappen uitvoeren om uw app gereed te maken voor Intune MAM. Voor het gemak worden deze stappen automatisch vooraf uitgevoerd in het bouwproces van Cordova. De geautomatiseerde stappen brengen hierdoor wijzigingen aan in uw `*.pbxproj`- , `*-Info.plist`- en `*.entitlements`-bestanden die zijn gekoppeld aan een projectconfiguratie. Als uw project geen rechtenbestand bevat, maakt de invoegtoepassing dit automatisch.

Deze configuratie wordt slechts op één doel ondersteund en indien er meerdere doelen zijn, wordt de configuratie uitgevoerd op het eerste doel dat wordt gevonden. Als het proces mislukt, controleert u of:

1. Het Xcode-project van uw app `[name].xcodeproj` is, waarbij `[name]` staat voor de waarde die is gedefinieerd in `config.xml`.
2. Uw project de [standaardmappenstructuur van Cordova voor apps](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure) gebruikt.

## <a name="how-to-build-the-plugin-into-your-android-app"></a>De invoegtoepassing inbouwen in uw Android-app

1. Importeer deze invoegtoepassing met de meest recente Cordova-hulpprogramma's. De invoegtoepassing wordt automatisch aangeroepen als een `after_compile`-stap.

2. De invoegtoepassing maakt een voor MAM geschikte versie van een ingebouwde APK (Android API 14+) aan het einde van het bouwproces. De uitvoer van de build bevat een `[Project]-intunewrapped-[Build_Configuration].apk` (bijvoorbeeld `helloWorld-intunewrapped-debug.apk`).

De invoegtoepassing ondersteunt alleen Gradle-builds.

Vanwege een [hier](https://issues.apache.org/jira/browse/CB-9434) opgeslagen Cordova-fout waardoor bepaalde Cordova-hooks worden genegeerd in `cordova run`, moet u als volgt te werk gaan om de verpakte app uit te voeren vanaf de opdrachtregel:

```
$ cordova build
$ cordova run --nobuild
```


### <a name="signing-your-android-app"></a>Uw Android-app ondertekenen
Als u handtekeninginformatie aan de verpakte APK wilt toevoegen, wijzigt u `build.json` zoals u gewend bent om handtekeninginformatie toe te voegen. Bijvoorbeeld:
```json
{
  "android": {
    "release": {
      "keystore": "your.keystore",
      "storePassword": "yourpassword",
      "alias": "youralias",
      "password" : "yourpassword",
      "keystoreType": ""
    }
  }
}
```

### <a name="build-for-android-test-only"></a>Build alleen voor Android-test

1. Voeg `android:testOnly="true"` toe aan het toepassingsknooppunt van het `AndroidManifest.xml`-bestand.


2. **Cordova 6.x.x:** In `[PROJECT_ROOT]/platforms/android/cordova/lib/Adb.js`, wijzig regel 60 van

    ```javascript
    var args = ['-s', target, 'install'];
    ```
    in op
    ```javascript
    var args = ['-s', target, 'install', '-t'];
    ```

Hierdoor wordt `adb install` uitgevoerd met de markering '-t', omdat `testOnly`-apps niet zonder deze markering kunnen worden geïnstalleerd.

### <a name="debugging-from-visual-studio"></a>Foutopsporing via Visual Studio
Nadat u de app de eerste keer hebt gestart, verschijnt een dialoogvenster met de melding dat de app wordt beheerd door Intune. Klik op Niet opnieuw weergeven en klik opnieuw op de knop foutopsporing/uitvoeren in Visual Studio voor onderbrekingspunten die moeten worden uitgevoerd.

## <a name="known-limitations"></a>Bekende beperkingen
### <a name="android"></a>Android
* Ondersteuning voor MultiDex is onvolledig.
* App moet gericht zijn op Android 4.0 (Android API 14) of hoger.

### <a name="ios"></a>iOS
* Wanneer u de lijst met UTI’s wijzigt onder het knooppunt **CFBundleDocumentTypes** van het bestand **Info.plist**, moet u de Intune UTI’s wissen uit de sectie Geïmporteerde UTI van hetzelfde PLIST-bestand (knooppunt **UTImportedTypeDeclarations**) voordat u opnieuw opbouwt. Alle Intune UTI’s beginnen met het voorvoegsel `com.microsoft.intune.mam`.

* Als u de Intune-invoegtoepassing wilt verwijderen uit uw Cordova-project, moet u ook het iOS-platform verwijderen en opnieuw toevoegen om bepaalde onderdelen van de Intune-configuratie in de .xcodeproj- en .plist-bestanden ongedaan te maken.



<!--HONumber=Nov16_HO4-->


