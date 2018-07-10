---
title: MTD-apps toevoegen en toewijzen aan Microsoft Intune
titleSuffix: ''
description: Gebruik Intune om Mobile Thread Defense (MTD)-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toe te voegen in Azure Portal.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 06/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c7f3229c2cb4c5f3f57d84d348053f25eeeb9c9
ms.sourcegitcommit: f70d6aaea59b52cd0d7bd3008afd243868967fd6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2018
ms.locfileid: "37066212"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>MTD-apps (Mobile Threat Defense) toevoegen en toewijzen met Intune

> [!NOTE] 
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

U kunt Intune gebruiken om MTD-apps toe te voegen en te implementeren. Eindgebruikers kunnen dan meldingen ontvangen wanneer op hun mobiele apparaten een bedreiging wordt vastgesteld en ze kunnen richtlijnen ontvangen om de bedreigingen te verhelpen.


## <a name="before-you-begin"></a>Voordat u begint

De onderstaande stappen moeten worden uitgevoerd in [Azure Portal](https://portal.azure.com/). Zorg ervoor dat u bekend bent met de volgende procedures:

  -   [Een app toevoegen in Intune](apps-add.md).
  -   [Een configuratiebeleid voor iOS-apps toevoegen in Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -   [Een app toewijzen met Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).
  -   [Een configuratiebeleid voor iOS-apps toevoegen](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

> [!TIP]
> De Intune-bedrijfsportal werkt als de broker op Android-apparaten, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD.

## <a name="configure-microsoft-authenticator-for-ios"></a>Microsoft Authenticator voor iOS configureren
Voor iOS-apparaten hebt u de app [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) nodig, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD. Bovendien hebt u het configuratiebeleid voor iOS-apps nodig, dat bepaalt welke MTD iOS-app moet worden gebruikt met Intune.

Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor de App Store voor Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) in **stap 12** in de sectie **App-gegevens configureren**.

## <a name="configure-mtd-applications"></a>MTD-toepassingen configureren

Kies de sectie die overeenkomt met uw MTD-provider:

  - [Lookout for Work](#configure-lookout-for-work-apps)
  - [SEP Mobile (Symantec Endpoint Protection Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
  - [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
  - [Zimperium](#configure-zimperium-apps)
  - [Pradeo](#configure-pradeo-apps)

### <a name="configure-lookout-for-work-apps"></a>Lookout for Work-app configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor Lookout for Work in Google Play](https://play.google.com/store/apps/details?id=com.lookout.enterprise) in **stap 7**.

- **iOS**

  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor de App Store voor Lookout for Work](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) in **stap 12** in de sectie **App-gegevens configureren**.

-   **Lookout for Work-app buiten de Apple Store**
    - U moet de Lookout for Work-app voor iOS opnieuw ondertekenen. De Lookout for Work-app voor iOS wordt gedistribueerd buiten de iOS App Store. Voordat u de app distribueert, moet u de app opnieuw ondertekenen met het iOS Enterprise Developer-certificaat.
    - Zie het [proces voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS](https://personal.support.lookout.com/hc/articles/114094038714) (Engelstalig) op de website van Lookout voor gedetailleerde instructies voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS.

    - **Azure AD-verificatie inschakelen voor gebruikers van de iOS-app Lookout for Work**

        1. Ga naar [Azure Portal](https://portal.azure.com), meld u aan en navigeer naar de toepassingspagina.

        2. Voeg de **Lookout for Work-app voor iOS** toe als een **native clienttoepassing**.

        3. Vervang **com.lookout.enterprise.yourcompanyname** door de klantbundel-id die u hebt geselecteerd bij het ondertekenen van de IPA.

        4.  Voeg de aanvullende omleidings-URI **&lt;companyportal://code/>** toe, gevolgd door een versie met URL-codering van uw oorspronkelijke omleidings-URI.

        5.  Voeg **overgedragen machtigingen** toe aan uw app.

        > [!NOTE] 
        > Zie voor meer informatie de Engelstalige instructies voor het [configureren van een native clienttoepassing met Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

     - **Het IPA-bestand van Lookout for Work toevoegen.**

        - Upload het opnieuw ondertekende IPA-bestand, volgens de instructies in het onderwerp [iOS-Line-Of-Business-apps (LOB) toevoegen aan Microsoft Intune](lob-apps-ios.md). U moet ook de minimale versie van het besturingssysteem instellen op iOS 8.0 of hoger.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Symantec Endpoint Protection Mobile-apps configureren

 - **Android**

    - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik in **stap 7** deze [URL voor de App Store voor SEP Mobile](https://play.google.com/store/apps/details?id=com.skycure.skycure).  Selecteer **Android 4.0 (Ice Cream Sandwich)** voor de **minimale versie van het besturingssysteem**.

 - **iOS**

    - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze **URL voor de App Store voor SEP Mobile** in [stap 12](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) in de sectie **App-gegevens configureren**.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Check Point SandBlast Mobile-apps configureren

 - **Android**

    - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor de App Store voor Check Point SandBlast Mobile](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) in **stap 7**.

 - **iOS**

    - Neem contact op met [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) om de iOS-app te downloaden. Zie de instructies voor het [toevoegen van apps vanuit de iOS Store aan Microsoft Intune](store-apps-ios.md) en gebruik vervolgens de URL voor de Apple Store in **stap 12** in de sectie **App-gegevens configureren**.

### <a name="configure-zimperium-apps"></a>Zimperium-apps configureren

 - **Android**

    - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor Zimperium in Google Play](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) in **stap 7**.

 - **iOS**

    - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor de App Store voor Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) in **stap 12** in de sectie **App-gegevens configureren**.

### <a name="configure-pradeo-apps"></a>Pradeo-apps configureren

 - **Android**

    - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor de App Store voor Pradeo](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) in **stap 7**.

 - **iOS**

    - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor de App Store voor Pradeo](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) in **stap 12** in de sectie **App-gegevens configureren**.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>Uw MTD-apps configureren met een configuratiebeleid voor iOS-apps

### <a name="lookout-for-work-app-configuration-policy"></a>Beleid voor de configuratie van Lookout for Work-apps

- Maak het configuratiebeleid voor iOS-apps volgens de instructies in het onderwerp [How to use Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) (App-configuratiebeleid van Microsoft Intune gebruiken voor iOS).

### <a name="sep-mobile-app-configuration-policy"></a>Beleid voor de configuratie van SEP Mobile-apps

-   Gebruik hetzelfde Azure AD-account dat eerder is geconfigureerd in de [Symantec Endpoint Protection-beheerconsole](https://aad.skycure.com). Dit moet hetzelfde account zijn als het account waarmee u zich hebt aangemeld bij de klassieke Intune-portal.

-   U dient het configuratiebeleid voor de iOS-app te **downloaden**: 
    -   Ga naar de [Symantec Endpoint Protection Mobile-beheerconsole](https://aad.skycure.com) en meld u aan met uw beheerdersreferenties.

    -   Ga naar **Instellingen** en kies onder **Integraties** de optie **Intune**. Kies **EMM Integration Selection**. Kies **Microsoft** en sla uw selectie vervolgens op.

    -   Klik op de koppeling voor de **installatiebestanden voor de integratie** en sla het gegenereerde bestand \*.zip op. Het .zip-bestand bevat het bestand ***.plist** waarmee het configuratiebeleid voor de iOS-app wordt gemaakt in Intune.

    -   Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app SEP Mobile toe te voegen.

    - Gebruik in **stap 8** de optie **XML-gegevens invoeren**, kopieer de inhoud van het bestand ***.plist** en plak de inhoud in de hoofdtekst van het configuratiebeleid.

> [!NOTE]
> Neem contact op met [Symantec Endpoint Protection Mobile Enterprise-ondersteuning](https://support.symantec.com/en_US/contact-support.html) als u de bestanden niet kunt ophalen.

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Configuratiebeleid voor Check Point SandBlast Mobile-apps

- Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Check Point SandBlast Mobile toe te voegen.
    - Gebruik in **stap 8** de optie **XML-gegevens invoeren**, kopieer de onderstaande inhoud en plak deze in de hoofdtekst van het configuratiebeleid.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="zimperium-app-configuration-policy"></a>Configuratiebeleid voor Zimperium-apps

- Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Zimperium toe te voegen.
    - Gebruik in **stap 8** de optie **XML-gegevens invoeren**, kopieer de onderstaande inhoud en plak deze in de hoofdtekst van het configuratiebeleid.

```
<dict>
<key>provider</key><string>Intune</string>
<key>userprincipalname</key><string>{{userprincipalname}}</string>
<key>deviceid</key>
<string>{{deviceid}}</string>
<key>serialnumber</key>
<string>{{serialnumber}}</string>
<key>udidlast4digits</key>
<string>{{udidlast4digits}}</string>
</dict>
```

## <a name="assign-apps-to-groups"></a>Apps aan groepen toewijzen

- Deze stap is van toepassing op alle MTD-partners. Zie de instructies voor het [toewijzen van apps aan groepen met Intune](apps-deploy.md).

## <a name="next-steps"></a>Volgende stappen

- [Het nalevingsbeleid voor MTD-apparaten configureren](mtd-device-compliance-policy-create.md)
