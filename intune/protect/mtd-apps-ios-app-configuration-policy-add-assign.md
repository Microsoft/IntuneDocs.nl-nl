---
title: MTD-apps toevoegen en toewijzen aan Microsoft Intune
titleSuffix: Microsoft Intune
description: Gebruik Intune om Mobile Thread Defense (MTD)-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toe te voegen in Azure Portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04a18befe73ce63f5619c3efc6def4189db9c8df
ms.sourcegitcommit: 13fa1a4a478cb0e03c7f751958bc17d9dc70010d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188485"
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>MTD-apps (Mobile Threat Defense) toevoegen en toewijzen met Intune

U kunt Intune gebruiken om MTD-apps (Mobile Threat Defense) toe te voegen en te implementeren. Eindgebruikers kunnen dan meldingen ontvangen wanneer op hun mobiele apparaten een bedreiging wordt vastgesteld en ze kunnen richtlijnen ontvangen om de bedreigingen te verhelpen.

> [!NOTE]
> Dit artikel is van toepassing op alle Mobile Threat Defense-partners.

## <a name="before-you-begin"></a>Voordat u begint

Voer de volgende stappen in Intune uit: Zorg ervoor dat u bekend bent met de volgende procedures:

- [Een app toevoegen in Intune](../apps/apps-add.md).
- [Een configuratiebeleid voor iOS-apps toevoegen in Intune](../apps/app-configuration-policies-use-ios.md).
- [Een app toewijzen met Intune](../apps/apps-deploy.md).

> [!TIP]
> De Intune-bedrijfsportal werkt als de broker op Android-apparaten, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD.

## <a name="configure-microsoft-authenticator-for-ios"></a>Microsoft Authenticator voor iOS configureren

Voor iOS-apparaten hebt u de app [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) nodig, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD. Bovendien hebt u een configuratiebeleid voor iOS-apps nodig, waarmee wordt bepaald welke MTD iOS-app moet worden gebruikt met Intune.

Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) wanneer u **App-gegevens** configureert.

## <a name="configure-mtd-applications"></a>MTD-toepassingen configureren

Kies de sectie die overeenkomt met uw MTD-provider:

- [Lookout for Work](#configure-lookout-for-work-apps)
- [SEP Mobile (Symantec Endpoint Protection Mobile)](#configure-symantec-endpoint-protection-mobile-apps)
- [Check Point SandBlast Mobile](#configure-check-point-sandblast-mobile-apps)
- [Zimperium](#configure-zimperium-apps)
- [Pradeo](#configure-pradeo-apps)
- [Better Mobile](#configure-better-mobile-apps)
- [Sophos Mobile](#configure-sophos-apps)
- [Wandera](#configure-wandera-apps)

### <a name="configure-lookout-for-work-apps"></a>Lookout for Work-app configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor Lookout for Work in Google Play](https://play.google.com/store/apps/details?id=com.lookout.enterprise) voor de **URL App Store**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de iTunes Store voor Lookout for Work](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) voor de **URL App Store**.

- **Lookout for Work-app buiten de Apple Store**
  - U moet de Lookout for Work-app voor iOS opnieuw ondertekenen. De Lookout for Work-app voor iOS wordt gedistribueerd buiten de iOS App Store. Voordat u de app distribueert, moet u de app opnieuw ondertekenen met het iOS Enterprise Developer-certificaat.  
  - Zie het [proces voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS](https://personal.support.lookout.com/hc/articles/114094038714) (Engelstalig) op de website van Lookout voor gedetailleerde instructies voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS.

  - **Azure AD-verificatie inschakelen voor gebruikers van de iOS-app Lookout for Work**

    1. Ga naar [Azure Portal](https://portal.azure.com), meld u aan en navigeer naar de toepassingspagina.

    2. Voeg de **Lookout for Work-app voor iOS** toe als een **native clienttoepassing**.

    3. Vervang **com.lookout.enterprise.yourcompanyname** door de klantbundel-id die u hebt geselecteerd bij het ondertekenen van de IPA.

    4. Voeg de aanvullende omleidings-URI **&lt;companyportal://code/>** toe, gevolgd door een versie met URL-codering van uw oorspronkelijke omleidings-URI.

    5. Voeg **overgedragen machtigingen** toe aan uw app.

    > [!NOTE]
    > Zie voor meer informatie de Engelstalige instructies voor het [configureren van een native clienttoepassing met Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

  - **Het IPA-bestand van Lookout for Work toevoegen.**

    - Upload het opnieuw ondertekende IPA-bestand, volgens de instructies in het artikel [iOS-Line-Of-Business-apps (LOB) toevoegen aan Microsoft Intune](../apps/lob-apps-ios.md). U moet ook de minimale versie van het besturingssysteem instellen op iOS 8.0 of hoger.

### <a name="configure-symantec-endpoint-protection-mobile-apps"></a>Symantec Endpoint Protection Mobile-apps configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de App Store voor SEP Mobile](https://play.google.com/store/apps/details?id=com.skycure.skycure) voor de **URL App Store**.  Selecteer **Android 4.0 (Ice Cream Sandwich)** voor de **minimale versie van het besturingssysteem**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor SEP Mobile](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) voor de **URL App Store**.

### <a name="configure-check-point-sandblast-mobile-apps"></a>Check Point SandBlast Mobile-apps configureren

- **Android**  
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de App Store voor Check Point SandBlast](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) voor de **URL App Store**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor Check Point SandBlast](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) voor de **URL App Store**.  

### <a name="configure-zimperium-apps"></a>Zimperium-apps configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de App Store voor Zimperium](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) voor de **URL App Store**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) voor de **URL App Store**.  
 
### <a name="configure-pradeo-apps"></a>Pradeo-apps configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de App Store voor Pradeo](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) voor de **URL App Store**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor Pradeo](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) voor de **URL App Store**.

### <a name="configure-better-mobile-apps"></a>Better Mobile-apps configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de App Store voor Active Shield](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) voor de **URL App Store**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor Active Shield](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) voor de **URL App Store**.

### <a name="configure-sophos-apps"></a>Sophos-apps configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de App Store voor Sophos](https://play.google.com/store/apps/details?id=com.sophos.smsec) voor de **URL App Store**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor Active Shield](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) voor de **URL App Store**.

### <a name="configure-wandera-apps"></a>Wandera-apps configureren

- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de mobiele app-store van Wandera](https://play.google.com/store/apps/details?id=com.wandera.android) voor de **URL App Store**. Selecteer **Android 5.0**  voor de **minimale versie van het besturingssysteem**.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de mobiele app-store van Wandera](https://itunes.apple.com/app/wandera/id605469330) voor de **URL App Store**.

## <a name="configure-your-mtd-apps-with-an-ios-app-configuration-policy"></a>Uw MTD-apps configureren met een configuratiebeleid voor iOS-apps

### <a name="lookout-for-work-app-configuration-policy"></a>Beleid voor de configuratie van Lookout for Work-apps

Maak het configuratiebeleid voor iOS-apps volgens de instructies in het artikel [using iOS app configuration policy](../apps/app-configuration-policies-use-ios.md) (App-configuratiebeleid voor iOS gebruiken).

### <a name="sep-mobile-app-configuration-policy"></a>Beleid voor de configuratie van SEP Mobile-apps

Gebruik hetzelfde Azure AD-account dat eerder is geconfigureerd in de [Symantec Endpoint Protection-beheerconsole](https://aad.skycure.com). Dit moet hetzelfde account zijn als het account waarmee u zich hebt aangemeld bij Intune.

- **Download** het configuratiebeleidsbestand voor de iOS-app:
  - Ga naar de [Symantec Endpoint Protection Mobile-beheerconsole](https://aad.skycure.com) en meld u aan met uw beheerdersreferenties.

  - Ga naar **Instellingen** en kies onder **Integraties** de optie **Intune**. Kies **EMM Integration Selection**. Kies **Microsoft** en sla uw selectie vervolgens op.

  - Klik op de koppeling voor de **installatiebestanden voor de integratie** en sla het gegenereerde bestand \*.zip op. Het .zip-bestand bevat het bestand * **.plist** waarmee het configuratiebeleid voor de iOS-app wordt gemaakt in Intune.

  - Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](../apps/app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app SEP Mobile toe te voegen.

    - Selecteer voor **Indeling van de configuratie-instellingen** de optie **XML-gegevens invoeren**, kopieer de inhoud van het bestand * **.plist** en plak de inhoud in de hoofdtekst van het configuratiebeleid.

> [!NOTE]
> Neem contact op met [Symantec Endpoint Protection Mobile Enterprise-ondersteuning](https://support.symantec.com/en_US/contact-support.html) als u de bestanden niet kunt ophalen.

### <a name="check-point-sandblast-mobile-app-configuration-policy"></a>Configuratiebeleid voor Check Point SandBlast Mobile-apps

Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](../apps/app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Check Point SandBlast Mobile toe te voegen.

- Selecteer voor **Indeling van de configuratie-instellingen** de optie **XML-gegevens invoeren**, kopieer de volgende inhoud en plak de inhoud in de hoofdtekst van het configuratiebeleid.

  `<dict><key>MDM</key><string>INTUNE</string></dict>`


### <a name="zimperium-app-configuration-policy"></a>Configuratiebeleid voor Zimperium-apps

Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](../apps/app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Zimperium toe te voegen.

- Selecteer voor **Indeling van de configuratie-instellingen** de optie **XML-gegevens invoeren**, kopieer de volgende inhoud en plak de inhoud in de hoofdtekst van het configuratiebeleid.

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

### <a name="pradeo-app-configuration-policy"></a>Configuratiebeleid voor Pradeo-apps

Pradeo biedt geen ondersteuning voor toepassingsconfiguratiebeleid in iOS.  Als u een geconfigureerde app wilt krijgen, moet u in plaats daarvan Pradeo gebruiken om aangepaste IPA- of APK-bestanden te implementeren die al vooraf zijn geconfigureerd met de gewenste instellingen.

### <a name="better-mobile-app-configuration-policy"></a>Configuratiebeleid voor Better Mobile-apps

Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](../apps/app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Better Mobile toe te voegen.

- Selecteer voor **Indeling van de configuratie-instellingen** de optie **XML-gegevens invoeren**, kopieer de volgende inhoud en plak de inhoud in de hoofdtekst van het configuratiebeleid. Vervang de `https://client.bmobi.net` URL dor de juiste console-URL.

   ```
    <dict>
   <key>better_server_url</key>
   <string>https://client.bmobi.net</string>
   <key>better_udid</key>
   <string>{{aaddeviceid}}</string>
   <key>better_user</key>
   <string>{{userprincipalname}}</string>
   </dict>
   ```

### <a name="sophos-mobile-app-configuration-policy"></a>Configuratiebeleid voor Sophos Mobile-apps

Maak het configuratiebeleid voor iOS-apps volgens de instructies in het artikel [using iOS app configuration policy](../apps/app-configuration-policies-use-ios.md) (App-configuratiebeleid voor iOS gebruiken).

### <a name="wandera-app-configuration-policy"></a>Configuratiebeleid voor Wandera-app

Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](../apps/app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Wandera toe te voegen.

- Voor **Indeling configuratie-instellingen** selecteert u **XML-gegevens invoeren**.

Meld u aan bij uw RADAR Wandera-portal en ga naar **Instellingen** > **EMM-integratie** > **App-push**. Selecteer **Intune** en kopieer en plak de onderstaande inhoud vervolgens in de hoofdtekst van het configuratiebeleid.  

  ```
  <dict><key>secretKey</key>
  <string>SeeRADAR</string>
  <key>apiKey</key>
  <string> SeeRADAR </string>
  <key>customerId</key>
  <string> SeeRADAR </string>
  <key>email</key>
  <string>{{mail}}</string>
  <key>firstName</key>
  <string>{{username}}</string>
  <key>lastName</key>
  <string></string>
  <key>activationType</key>
  <string>PROVISION_THEN_AWP</string></dict>
  ```

## <a name="assign-apps-to-groups"></a>Apps aan groepen toewijzen

Deze stap is van toepassing op alle MTD-partners. Zie de instructies voor het [toewijzen van apps aan groepen met Intune](../apps/apps-deploy.md).

## <a name="next-steps"></a>Volgende stappen

- [Het nalevingsbeleid voor MTD-apparaten configureren](mtd-device-compliance-policy-create.md)
