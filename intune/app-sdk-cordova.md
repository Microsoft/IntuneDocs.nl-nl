---
title: Microsoft Intune App SDK Cordova-invoegtoepassing
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 0329720b6f02c718ef27a59e6efc5f3a76eed1c5
ms.contentlocale: nl-nl
ms.lasthandoff: 06/08/2017


---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a>Microsoft Intune App SDK Cordova-invoegtoepassing

> [!NOTE]
> U kunt desgewenst eerst het artikel [Aan de slag met Intune App SDK](app-sdk-get-started.md) lezen, waarin wordt uitgelegd hoe u de integratie voor elk ondersteund platform kunt voorbereiden.

## <a name="overview"></a>Overzicht

De [Intune App SDK Cordova-invoegtoepassing](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS en Android-apps, gebouwd met Cordova. De invoegtoepassing biedt ontwikkelaars de mogelijkheid om beveiligingsfuncties voor de Intune-app en -gegevens te integreren in hun op Cordova gebaseerde app.

U zult merken dat u SDK-functies kunt inschakelen zonder het gedrag van uw app te wijzigen. Als u de invoegtoepassing in uw iOS- of Android-app hebt gemaakt, kan de Microsoft Intune-beheerder beveiligingsbeleid voor Intune-apps implementeren dat bestaat uit een diverse functies voor gegevensbeveiliging. De invoegtoepassing is zo ontwikkeld dat de meeste stappen automatisch worden uitgevoerd in het bouwproces voor Cordova. Dat zou het mogelijk moeten maken om uw app snel in te schakelen voor app-beveiliging van Intune. Volg de onderstaande stappen op basis van uw doelplatform om aan de slag te gaan.

## <a name="supported-platforms"></a>Ondersteunde platformen

* De invoegtoepassing kan worden gebruikt bij Windows, Mac en Linux OS
* De invoegtoepassing kan worden gebruikt bij Android-apps met `minSdkVersion` >= 14 en `targetSdkVersion` <= 24
* De invoegtoepassing kan worden gebruikt bij iOS-apps voor iOS 9.0 en hoger.

## <a name="intune-mobile-application-management-scenarios"></a>Scenario’s voor Intune Mobile Application Management

* Apparaten die zijn ingeschreven bij Intune MDM
* Apparaten die zijn ingeschreven bij EMM van derden
* Onbeheerde apparaten (niet ingeschreven bij een MDM)

Cordova-apps die zijn gemaakt met de Intune App SDK Cordova-invoegtoepassing kunnen nu app-beveiligingsbeleid van Intune ontvangen op apparaten die wel en apparaten die niet zijn ingeschreven in Mobile Device Management (MDM) van Intune.

## <a name="prerequisites"></a>Vereisten

### <a name="android"></a>Android

* Op het apparaat moet altijd de meest recente Microsoft Intune-bedrijfsportal-app zijn geïnstalleerd.
* Op het pad waar u de Cordova-build uitvoert wanneer u de invoegtoepassing gebruikt, moet zich ten minste Java 7 bevinden.

### <a name="ios"></a>iOS

* Voor MDM-functies moet op het apparaat de meest recente Microsoft Intune-bedrijfsportal-app zijn geïnstalleerd. Deze app is *niet* nodig voor het app-beveiligingsbeleid van Intune zonder apparaatinschrijvingsfuncties.

### <a name="both-platforms"></a>Beide platforms

* Versie 0.8.0 of hoger van de [Azure Active Directory Authentication Libraries-invoegtoepassing (ADAL) voor Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) is vereist.

> [!NOTE]
> Vanwege een [hier](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) geregistreerde Cordova Apache-fout worden apps die al afhankelijk zijn van de invoegtoepassing, niet automatisch bijgewerkt naar de vereiste versie.



## <a name="quick-start"></a>Snel starten

1. Uw versie van ADAL bijwerken:

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. De Intune App SDK Cordova-invoegtoepassing toevoegen:

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a>De invoegtoepassing inbouwen in uw iOS-app

U moet een aantal stappen uitvoeren om uw app gereed te maken voor app-beveiligingsbeleid van Intune. Voor het gemak worden deze stappen automatisch vooraf uitgevoerd in het bouwproces van Cordova. De geautomatiseerde stappen brengen hierdoor wijzigingen aan in uw `*.pbxproj`- , `*-Info.plist`- en `*.entitlements`-bestanden die zijn gekoppeld aan een projectconfiguratie. Als uw project geen rechtenbestand bevat, maakt de invoegtoepassing dit automatisch.

Deze configuratie wordt slechts op één doel ondersteund en indien er meerdere doelen zijn, wordt de configuratie uitgevoerd op het eerste doel dat wordt gevonden. Als het proces mislukt, controleert u of:

1. Het Xcode-project van uw app `[name].xcodeproj` is, waarbij `[name]` staat voor de waarde die is gedefinieerd in `config.xml`.
2. Uw project de [standaardmappenstructuur van Cordova voor apps](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure) gebruikt.

## <a name="build-the-plugin-into-your-android-app"></a>De invoegtoepassing inbouwen in uw Android-app

1. Importeer deze invoegtoepassing met de meest recente Cordova-hulpprogramma's. De invoegtoepassing wordt automatisch aangeroepen als een `after_compile`-stap.

2. De invoegtoepassing maakt een voor Intune geschikte versie van een ingebouwde APK (Android API 14+) aan het einde van het bouwproces. De uitvoer van de build bevat een `[Project]-intunewrapped-[Build_Configuration].apk` (bijvoorbeeld `helloWorld-intunewrapped-debug.apk`).

> [!NOTE]
> De invoegtoepassing ondersteunt alleen Gradle-builds.

Vanwege een [hier](https://issues.apache.org/jira/browse/CB-9434) opgeslagen Cordova-fout waardoor bepaalde Cordova-hooks worden genegeerd in `cordova run`, moet u als volgt te werk gaan om de verpakte app uit te voeren vanaf de opdrachtregel:

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a>Uw Android-app ondertekenen

De invoegtoepassing herkent automatisch ondertekeningsgegevens die u op de volgende locaties hebt opgegeven voor Cordova:

* platforms/android/debug-signing.properties
* platforms/android/release-signing.properties
* res/native/android/ant.properties

Zie [de Cordova Gradle-ondertekeningsgegevens](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) voor meer informatie over de verwachte indeling.

Er wordt momenteel geen ondersteuning geboden voor de mogelijkheid om ondertekeningsgegevens te bieden in `build.json` of op willekeurige locaties die via parameters aan de Cordova-build zijn geleverd.

## <a name="debugging-from-visual-studio"></a>Foutopsporing via Visual Studio

Nadat u de app de eerste keer hebt gestart, verschijnt een dialoogvenster met de melding dat de app wordt beheerd door Intune. Klik op Niet opnieuw weergeven en klik opnieuw op de knop foutopsporing/uitvoeren in Visual Studio voor onderbrekingspunten die moeten worden uitgevoerd.

## <a name="known-limitations"></a>Bekende beperkingen

### <a name="android"></a>Android

* Ondersteuning voor MultiDex is onvolledig.
* De app moet een `minSdkVersion` van 14 en een `targetSdkVersion` van 24 of lager hebben. Apps die bedoeld zijn voor API 25, worden momenteel niet ondersteund
* Apps die zijn ondertekend met het V2-handtekeningschema, kunnen niet opnieuw worden ondertekend. Als met V2 ondertekende apps zijn ingepakt door de invoegtoepassing, is de ingepakte .apk van de uitvoer niet ondertekend.
*
  * U kunt de standaard-V2-ondertekening van Cordova uitschakelen door het volgende aan het bestand `build-extras.gradle` toe te voegen:

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a>iOS

* Wanneer u de lijst met UTI's wijzigt onder het knooppunt **CFBundleDocumentTypes** van het bestand **Info.plist**, moet u de Intune UTI's wissen uit de sectie Geïmporteerde UTI's van hetzelfde PLIST-bestand (knooppunt **UTImportedTypeDeclarations**) voordat u opnieuw opbouwt. Alle Intune UTI's beginnen met het voorvoegsel `com.microsoft.intune.mam`.

* Als u de Intune App SDK voor Cordova-invoegtoepassing wilt verwijderen uit uw Cordova-project, moet u ook het iOS-platform verwijderen en opnieuw toevoegen om bepaalde onderdelen van de Intune-configuratie in de .xcodeproj- en .plist-bestanden ongedaan te maken.

