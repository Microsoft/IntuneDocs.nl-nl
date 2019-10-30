---
title: Mobile Threat Defense-apps toevoegen aan niet-ingeschreven apparaten
titleSuffix: Microsoft Intune
description: Mobile Threat Defense-apps toevoegen aan niet-ingeschreven apparaten door apparaatgebruikers.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: f8dd7127594a0e23c85b9f8141ce6d398d9a447a
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72794456"
---
# <a name="add-mobile-threat-defense-apps-to-unenrolled-devices"></a>Mobile Threat Defense-apps toevoegen aan niet-ingeschreven apparaten

Wanneer u het beveiligingsbeleid van de Intune-app met Mobile Threat Defense gebruikt, worden eindgebruikers door Intune op hun apparaat begeleid tijdens de installatie van en aanmelding bij alle apps die zijn vereist om de verbindingen met alle relevante services in te schakelen.

Eindgebruikers hebben Microsoft Authenticator (iOS) nodig om hun apparaat te registreren en Mobile Threat Defense (zowel voor Android als iOS) om meldingen te kunnen ontvangen als een bedreiging wordt geïdentificeerd op hun mobiele apparaten, en om hulp te krijgen bij het oplossen van de bedreigingen.

Desgewenst kunt u Intune gebruiken om de apps Microsoft Authenticator en MTD (Mobile Threat Defense) ook toe te voegen en te implementeren.

> [!NOTE] 
> Dit artikel is van toepassing op alle Mobile Threat Defense-partners die ondersteuning bieden aan beleid voor app-beveiliging: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).
> 
> Voor apparaten die niet zijn ingeschreven, hebt u **geen configuratiebeleid voor iOS-apps nodig** om de app Mobile Threat Defense voor iOS die u met Intune gebruikt, in te stellen. Dit is een belangrijk verschil ten opzichte van apparaten die bij Intune zijn Ingeschreven. 

## <a name="configure-microsoft-authenticator-for-ios-via-intune-optional"></a>Microsoft Authenticator voor iOS via Intune configureren (optioneel)
Wanneer het beveiligingsbeleid van de Intune-app met Mobile Threat Defense wordt gebruikt, worden eindgebruikers door Intune op hun apparaat begeleid bij de installatie op, de aanmelding bij en inschrijving van hun apparaat bij Microsoft Authenticator (iOS).

Als u de app echter beschikbaar wilt maken voor eindgebruikers via de Intune-bedrijfsportal, raadpleegt u de instructies voor het [toevoegen van iOS Store-apps aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de iOS App Store voor Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) bij het invullen van de sectie **App-gegevens configureren**. Vergeet niet om als laatste stap [de app met behulp van Intune toe te wijzen aan groepen](../apps/apps-deploy.md).

> [!NOTE] 
> Voor iOS-apparaten hebt u de app [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) nodig, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD. De Intune-bedrijfsportal werkt als de broker op Android-apparaten, zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD.

## <a name="making-mobile-threat-defense-apps-available-via-intune-optional"></a>Mobile Threat Defense-apps beschikbaar maken via Intune (optioneel)
Wanneer het beveiligingsbeleid van de Intune-app met Mobile Threat Defense wordt gebruikt, worden eindgebruikers door Intune begeleid bij de installatie op en aanmelding bij de Mobile Threat-Defense-client-app. 

Als u de app echter via de Intune-bedrijfsportal beschikbaar wilt maken voor eindgebruikers, kunt u de onderstaande stappen volgen in [Azure Portal](https://portal.azure.com/). Zorg ervoor dat u bekend bent met de volgende procedures:

- [Een app toevoegen in Intune](../apps/apps-add.md).
- [Een app toewijzen met Intune](../apps/apps-deploy.md).

### <a name="making-lookout-for-work-available-to-end-users"></a>Lookout for Work beschikbaar maken voor eindgebruikers
- **Android**  
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de Play Store voor Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) als u de sectie **App-gegevens configureren** invult.

- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de iOS App Store voor Lookout for Work](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) als u de sectie **App-gegevens configureren** invult.

<!-- ### Making Symantec Endpoint Protection Mobile available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). When completing the **Configure app information** section, use this [SEP Mobile app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure). For **Minimum operating system**, select **Android 4.0 (Ice Cream Sandwich)**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [SEP Mobile - App Store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) when completing the **Configure app information** section.

### Making Check Point SandBlast Mobile available to end users
- **Android**  
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Check Point SandBlast Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) when completing the **Configure app information** section. 

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Check Point SandBlast Mobile - App Store URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) when completing the **Configure app information** section. -->

### <a name="making-zimperium-available-to-end-users"></a>Zimperium beschikbaar maken voor eindgebruikers
<!-- - **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Zimperium - Play Store URL](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) when completing the **Configure app information** section. -->
- **iOS**
  - Zie de instructies in het artikel [iOS Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-ios.md). Gebruik deze [URL voor de App Store voor Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) in de sectie **App-gegevens configureren**.
 
<!-- ### Making Pradeo available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Pradeo - Play Store URL](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Pradeo - App Store URL](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) when completing the **Configure app information** section. -->

### <a name="making-better-mobile-available-to-end-users"></a>Better Mobile beschikbaar maken voor eindgebruikers 
- **Android**
  - Zie de instructies in het artikel [Android Store-apps toevoegen aan Microsoft Intune](../apps/store-apps-android.md). Gebruik deze [URL voor de Play Store voor Active Shield](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) als u de sectie **App-gegevens configureren** invult.
<!-- - **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) when completing the **Configure app information** section. -->

<!-- ### Making Sophos available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Sophos - Play Store URL](https://play.google.com/store/apps/details?id=com.sophos.smsec) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) when completing the **Configure app information** section.

### Making Wandera available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Wandera Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.wandera.android) when completing the **Configure app information** section. For **Minimum operating system**, select **Android 5.0**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Wandera Mobile - - App Store URL](https://itunes.apple.com/app/wandera/id605469330) when completing the **Configure app information** section. -->

## <a name="next-steps"></a>Volgende stappen  

- [De Mobile Threat Defense-connector in Intune inschakelen voor niet-ingeschreven apparaten](~/protect/mtd-enable-unenrolled-devices.md)

