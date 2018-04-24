---
title: MTD-apps toevoegen en toewijzen aan Microsoft Intune
titleSuffix: ''
description: Gebruik Intune om Mobile Thread Defense (MTD)-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toe te voegen in Azure Portal.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 08cebf84443e65ded5f7884218fbe17d722bddf2
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>MTD-apps (Mobile Threat Defense) toevoegen en toewijzen met Intune

> [!NOTE] 
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

U kunt Intune gebruiken om MTD-apps toe te voegen en te implementeren. Eindgebruikers kunnen dan meldingen ontvangen wanneer op hun mobiele apparaten een bedreiging wordt vastgesteld en ze kunnen richtlijnen ontvangen om de bedreigingen te verhelpen.

Voor iOS-apparaten hebt u de app [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) nodig, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD. Bovendien hebt u het configuratiebeleid voor iOS-apps nodig, dat bepaalt welke MTD iOS-app moet worden gebruikt met Intune.

> [!TIP]
> De Intune-bedrijfsportal werkt als de broker op Android-apparaten, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD.

## <a name="before-you-begin"></a>Voordat u begint

-   De onderstaande stappen moeten worden uitgevoerd in [Azure Portal](https://portal.azure.com/).

-   Zorg ervoor dat u bekend bent met de volgende procedures:

    -   [Een app toevoegen in Intune](apps-add.md).

    -   [Een configuratiebeleid voor iOS-apps toevoegen in Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Een app toewijzen met Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Een configuratiebeleid voor iOS-apps toevoegen](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-apps"></a>Apps toevoegen

### <a name="all-mtd-partners"></a>All MTD-partners

#### <a name="microsoft-authenticator-app-for-ios"></a>Microsoft Authenticator-app voor iOS

- Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor Microsoft Authenticator in de iTunes Store](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) in **stap 5**, onder de sectie **App-gegevens configureren**.

### <a name="lookout"></a>Lookout

#### <a name="android"></a>Android
- Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor Lookout for Work in Google Play](https://play.google.com/store/apps/details?id=com.lookout.enterprise) in **stap 7**.

#### <a name="ios"></a>iOS

- Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor Lookout for Work in de iTunes Store](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) in **stap 5**, onder de sectie **App-gegevens configureren**.

#### <a name="lookout-for-work-app-outside-the-apple-store"></a>Lookout for Work-app buiten de iOS App Store

U moet de Lookout for Work-app voor iOS opnieuw ondertekenen. De Lookout for Work-app voor iOS wordt gedistribueerd buiten de iOS App Store. Voordat u de app distribueert, moet u de app opnieuw ondertekenen met het iOS Enterprise Developer-certificaat.

Zie het [proces voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS](https://personal.support.lookout.com/hc/articles/114094038714) (Engelstalig) op de website van Lookout voor gedetailleerde instructies voor het opnieuw ondertekenen van Lookout for Work-apps voor iOS.

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Azure AD-verificatie inschakelen voor Lookout for Work-app voor iOS

Schakel Azure Active Directory-verificatie voor de iOS-gebruikers als volgt in:

1. Ga naar [Azure Portal](https://portal.azure.com), meld u aan en navigeer naar de toepassingspagina.

2. Voeg de **Lookout for Work-app voor iOS** toe als een **native clienttoepassing**.

3. Vervang **com.lookout.enterprise.yourcompanyname** door de klantbundel-id die u hebt geselecteerd bij het ondertekenen van de IPA.

4.  Voeg de aanvullende omleidings-URI **&lt;companyportal://code/>** toe, gevolgd door een versie met URL-codering van uw oorspronkelijke omleidings-URI.

5.  Voeg **overgedragen machtigingen** toe aan uw app.

    > [!NOTE] 
    > Zie voor meer informatie de Engelstalige instructies voor het [configureren van een native clienttoepassing met Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).

##### <a name="add-the-lookout-for-work-ipa-file"></a>Het IPA-bestand van Lookout for Work toevoegen

- Upload het opnieuw ondertekende IPA-bestand, volgens de instructies in het onderwerp [iOS-Line-Of-Business-apps (LOB) toevoegen aan Microsoft Intune](lob-apps-ios.md). U moet ook de minimale versie van het besturingssysteem instellen op iOS 8.0 of hoger.

### <a name="skycure"></a>Skycure

#### <a name="android"></a>Android

- Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor Skycure in Google Play](https://play.google.com/store/apps/details?id=com.skycure.skycure) in **stap 7**.

#### <a name="ios"></a>iOS

- Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor Skycure in de iTunes Store](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) in **stap 5**, onder de sectie **App-gegevens configureren**.

### <a name="check-point-sandblast-mobile"></a>Check Point SandBlast Mobile

#### <a name="android"></a>Android

- Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor de App Store voor Check Point SandBlast Mobile](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) in **stap 7**.

#### <a name="ios"></a>iOS

- Neem contact op met [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) om de iOS-app te downloaden. Zie de instructies voor het [toevoegen van apps vanuit de iOS Store aan Microsoft Intune](store-apps-ios.md) en gebruik vervolgens de URL voor de Apple Store in **stap 5** in de sectie **App-gegevens configureren**.

### <a name="zimperium"></a>Zimperium

#### <a name="android"></a>Android

- Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](store-apps-android.md). Gebruik deze [URL voor Zimperium in Google Play](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) in **stap 7**.

#### <a name="ios"></a>iOS

- Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](store-apps-ios.md). Gebruik deze [URL voor Zimperium in de iTunes Store](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) in **stap 5**, onder de sectie **App-gegevens configureren**.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>De MTD-app koppelen aan een configuratiebeleid voor iOS-apps

### <a name="for-lookout"></a>Voor Lookout

- Maak het configuratiebeleid voor iOS-apps volgens de instructies in het onderwerp [How to use Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) (App-configuratiebeleid van Microsoft Intune gebruiken voor iOS).

### <a name="for-skycure"></a>Voor Skycure

-   Gebruik hetzelfde Azure AD-account dat eerder is geconfigureerd in de [Skycure-beheerconsole](https://aad.skycure.com). Dit moet hetzelfde account zijn als het account waarmee is aangemeld bij de klassieke Intune-portal.

-   U dient het configuratiebeleid voor de iOS-app te **downloaden**: 
    -   Ga naar [Beheerconsole van Skycure](https://aad.skycure.com) en meld u aan met uw beheerdersreferenties.

    -   Ga naar **Instellingen** &gt; **Integraties voor apparaatbeheer**  &gt; **Selectie van EMM-integraties**, kies **Microsoft Intune** en sla vervolgens de selectie op.

    -   Klik op de koppeling voor de **installatiebestanden voor de integratie** en sla het gegenereerde bestand \*.zip op. Het ZIP-bestand bevat het bestand **skycure\_configuration.plist**, waarmee het configuratiebeleid voor de iOS-app wordt gemaakt in Intune.

    -   Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Skycure toe te voegen.

    - Gebruik in **stap 8** de optie **XML-gegevens invoeren**, kopieer de inhoud van het bestand **skycure_configuration.plist** en plak de inhoud in de hoofdtekst van het configuratiebeleid.

U kunt de inhoud van **skycure_configuration.plist** ook hier kopiëren:

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>
```
### <a name="for-check-point-sandblast-mobile"></a>Voor Check Point SandBlast Mobile

- Zie de Engelstalige instructies voor het [gebruiken van app-configuratiebeleid voor iOS van Microsoft Intune](app-configuration-policies-use-ios.md) om het configuratiebeleid voor de iOS-app Check Point SandBlast Mobile toe te voegen.
    - Gebruik in **stap 8** de optie **XML-gegevens invoeren**, kopieer de onderstaande inhoud en plak deze in de hoofdtekst van het configuratiebeleid.

```
<dict><key>MDM</key><string>INTUNE</string></dict>
```

### <a name="for-zimperium"></a>Voor Zimperium

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

## <a name="to-assign-apps-all-mtd-partners"></a>Apps toewijzen (alle MTD-partners)

- Zie de instructies voor het [toewijzen van apps aan groepen met Intune](apps-deploy.md).

## <a name="next-steps"></a>Volgende stappen

- [Nalevingsbeleid voor MTD-apparaten toevoegen](mtd-device-compliance-policy-create.md)
