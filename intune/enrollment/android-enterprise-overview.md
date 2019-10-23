---
title: Android Enterprise-apparaten met een werkprofiel beheren in Microsoft Intune
titleSuffix: ''
description: Met Microsoft Intune beheert u Android Enterprise-apparaten met een werkprofiel om aanvullende beheermogelijkheden en privacy te leveren wanneer mensen hun persoonlijke Android-apparaten voor hun werk gebruiken.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2cc3c960-1fdd-47ca-a693-420d47b403de
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a5c980b3f9ababaf94aa7b279e533679ed74b0e
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503374"
---
# <a name="manage-android-work-profile-devices-with-intune"></a>Android-apparaten met een werkprofiel beheren met Intune

Android Enterprise biedt een reeks registratie-opties waardoor gebruikers over de meest recente en veilige functies beschikken. Door u bij een Android Enterprise-werkprofiel in te schrijven, is een reeks functies en services beschikbaar waarmee persoonlijke apps en gegevens worden gescheiden van zakelijke apps en gegevens. Het biedt tevens aanvullende beheermogelijkheden en privacy wanneer mensen hun persoonlijke Android-apparaten voor hun werk gebruiken. 

## <a name="supported-devices"></a>Ondersteunde apparaten

De beheermogelijkheden van Android Enterprise zijn afhankelijk van functies die deel uitmaken van recentere Android-besturingssystemen. Voor apparaten die geen ondersteuning bieden voor Android Enterprise, blijft het conventionele Android-beheer beschikbaar. Zie [Android Enterprise-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012) voor meer informatie.

## <a name="onboarding"></a>Onboarding

Voordat u Android Enterprise-apparaten met een werkprofiel registreert, moet u enkele stappen voor onboarding uitvoeren. Met deze stappen wordt uw Intune-tenant verbonden met de Managed Google Play. Zie [Inschrijving van Android Enrollment-apparaten met een werkprofiel inschakelen](android-work-profile-enroll.md) voor meer informatie.

## <a name="work-profile-management"></a>Beheer van werkprofielen

Wanneer u een Android Enterprise-apparaat met een werkprofiel met Intune beheert, beheert u niet het hele apparaat. De beheermogelijkheden hebben alleen betrekking op het werkprofiel dat is gemaakt tijdens de inschrijving van het apparaat. Alle apps die op het apparaat zijn geïmplementeerd met Intune, worden geïnstalleerd in het werkprofiel. App-pictogrammen in het werkprofiel worden onderscheiden van persoonlijke apps op het apparaat. Alle Android-apps en -gegevens buiten het Android Enterprise-gedeelte van het apparaat blijven persoonlijk en onder beheer van de eindgebruiker. Gebruikers kunnen elke gewenste app aan de persoonlijke kant van het apparaat installeren. Beheerders beheren en bewaken apps en acties die bij het werkprofiel horen.

Intune biedt diverse ingebouwde algemene instellingen die u op Android-apparaten met een werkprofiel kunt configureren. Zie [Android work profile device policy settings](../protect/compliance-policy-create-android-for-work.md) (Beleidsinstellingen voor het Android-werkprofiel) voor meer informatie.

## <a name="app-publishing-and-distribution"></a>Apps publiceren en distribueren

Managed Google Play is een integraal onderdeel van de distributie en het beheer van apps via Android Enterprise. Alle apps die op Android Enterprise-apparaten met een werkprofiel in dit werkprofiel worden geïmplementeerd, zijn afkomstig van de beheerde Google Play-service. Als u apps in de Play Store wilt beheren en implementeren, meldt u zich bij de Google Play-website aan met de beheerdersreferenties van uw bedrijf voor Google-beheer. U kunt apps voor de Android Enterprise-implementatie goedkeuren, zodat deze in de werkprofielen van apparaten worden weergegeven. Deze apps worden dan met de Intune-console gesynchroniseerd waar ze vervolgens kunnen worden geïmplementeerd en beheerd met Intune. LOB-apps (Line-Of-Business) die door uw organisatie worden ontwikkeld, moeten worden gepubliceerd naar Beheerde Google Play met behulp van de Android-console voor het publiceren van apps van Google. Line-Of-Business-apps moeten worden geconfigureerd in de Android-console voor het publiceren van apps om de toegang tot uw organisatie te beperken.

Apps kunnen worden geïnstalleerd zonder tussenkomst van de gebruiker en zonder dat de gebruiker **installatie vanuit onbekende bronnen** hoeft toe te staan. Als gebruikers optionele of beschikbare apps willen zoeken en installeren, kunnen ze zoeken in de Play for Work Store op hun apparaat. Zie [Apps toewijzen aan Android Enterprise-apparaten met een werkprofiel met Intune](../apps/apps-add-android-for-work.md) voor meer informatie.

## <a name="app-configuration"></a>App-configuratie

Android Enterprise biedt een infrastructuur voor het implementeren van app-configuratiewaarden naar apps die ze ondersteunen. Als u configuratiewaarden voor zakelijke apps opgeeft, zorgt u ervoor dat ze goed zijn ingesteld wanneer gebruikers de app de eerste keer starten. Ondersteuning voor app-configuratie vereist dat app-ontwikkelaars hun Android-apps specifiek ter ondersteuning van beheerde configuratiewaarden maken. Als dat het geval is, kunt u vervolgens Intune gebruiken en deze configuratie-instellingen toepassen. Zie [App-configuratiebeleidsregels toevoegen voor beheerde Android-apparaten](../apps/app-configuration-policies-use-android.md) voor meer informatie.

## <a name="email-configuration"></a>E-mailconfiguratie

Android Enterprise biedt geen standaardapp voor e-mail of systeemeigen e-mailprofielobjecten zoals wordt geleverd door iOS. In plaats daarvan kunnen e-mailconfiguraties worden ingesteld door app-configuratie-instellingen toe te passen op e-mail-apps die hiervoor ondersteuning bieden. Gmail en Nine Work zijn twee EAS-clientapps (Exchange ActiveSync) in de Play Store die ondersteuning bieden voor configuratie met Android Enterprise-app-configuratie.

Intune biedt configuratiesjablonen voor Gmail- en Nine Work-apps wanneer deze als zakelijke apps worden beheerd. Andere e-mailapps die ondersteuning bieden voor app-configuratieprofielen, kunnen worden geconfigureerd met beleid voor de configuratie van mobiele apps.

Als u werkt met voorwaardelijke toegang via Exchange ActiveSync voor een Android Enterprise-apparaat met een werkprofiel, moet u een Gmail- of Nine Work-app voor e-mail gebruiken. De Microsoft Outlook voor Android-app of een andere e-mail-app die gebruikmaakt van moderne verificatie via ADAL, wordt ook ondersteund. Zie [E-mailinstellingen configureren in Microsoft Intune](../configuration/email-settings-configure.md) voor meer informatie.

## <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Appbeveiligingsbeleid dat wordt toegepast, wordt volledig ondersteund in het werkprofiel en in het persoonlijk profiel. U kunt Line-Of-Business-apps in de Android-console voor het publiceren van apps publiceren op https://play.google.com/apps/publish. Deze console bevat een optie om apps privé voor uw organisatie te maken. Zie [Een nalevingsbeleid voor Android Enterprise-apparaten met een werkprofiel in Intune toevoegen](../protect/compliance-policy-create-android-for-work.md) voor meer informatie. Zie [Wat is een app-beveiligingsbeleid?](../apps/app-protection-policy.md) voor algemene informatie over app-beveiligingsbeleid.

## <a name="vpn-profiles"></a>VPN-profielen

VPN-ondersteuning is vergelijkbaar met Android VPN-profielen. Dezelfde VPN-providers en algemene configuratieopties zijn beschikbaar voor Android Enterprise-beheer, met twee verschillen:

- **VPN voor het werkprofiel**: VPN-verbindingen zijn beperkt tot de apps die zijn geïmplementeerd voor het werkprofiel. Alleen apps die met Android Enterprise worden beheerd, kunnen de VPN-verbinding gebruiken. Persoonlijke apps op het apparaat kunnen geen beheerde VPN-verbinding gebruiken. Zie [VPN-instellingen voor Android Enterprise](../configuration/vpn-settings-android-enterprise.md) voor meer informatie.

- **App-specifiek VPN**: app-specifiek VPN kan in Intune worden geconfigureerd als de VPN-provider het volgende ondersteunt:
  - configuratie voor app-specifiek VPN
  - de mogelijkheid om VPN per app te configureren via het app-configuratieprofiel voor Android Enterprise.
  Zie [Een aangepast Microsoft Intune-profiel gebruiken voor het maken van een VPN-profiel per app voor Android-apparaten](../configuration/android-pulse-secure-per-app-vpn.md) voor meer informatie.

## <a name="certificate-profiles"></a>Certificaatprofielen

Dezelfde certificaatprofielconfiguratieopties die beschikbaar zijn voor Android-beheer, zijn beschikbaar op Android Enterprise-apparaten met een werkprofiel. Android Enterprise biedt verbeterde certificaatbeheer-API's. Het verbeterde certificaatbeheer biedt de volgende functionaliteit:

- Zorgt ervoor dat de implementatie van het certificaat naadloos op de achtergrond voor de gebruiker plaatsvindt.
- Zorgt ervoor dat geïmplementeerde certificaten worden verwijderd wanneer een apparaat uit Intune wordt teruggetrokken en het werkprofiel wordt verwijderd.
- Biedt verbeterde berichtverzending waarbij gebruikers door hun IT-afdeling via hun beheerservice worden geïnformeerd dat het certificaat is geïmplementeerd en geconfigureerd.

Zie [Een certificaatprofiel configureren voor uw apparaten in Microsoft Intune](../protect/certificates-configure.md) voor meer informatie.

## <a name="wi-fi-profiles"></a>Wi-Fi-profielen

Wi-Fi-profielen die worden beheerd door Android Enterprise, worden verwijderd wanneer het apparaat buiten gebruik wordt gesteld (uit Intune wordt teruggetrokken) en het werkprofiel wordt verwijderd. Zie [Wi-Fi-instellingen configureren in Microsoft Intune](../configuration/wi-fi-settings-configure.md) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen
- [Android-apparaten inschrijven](android-enroll.md)
- [Apps toewijzen aan Android Enterprise-apparaten met een werkprofiel met Intune](../apps/apps-add-android-for-work.md)
