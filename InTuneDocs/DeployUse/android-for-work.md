---
title: Over Android for Work | Microsoft Intune
description: Intune beheert Android for Work om aanvullende beheermogelijkheden en privacy te leveren wanneer mensen hun Android-apparaten voor hun werk gebruiken.
keywords: 
author: nathbarn
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
translationtype: Human Translation
ms.sourcegitcommit: 83914246bde673b188ca3f7d9cf50b4d0de2edd4
ms.openlocfilehash: 127db326fc96625c719b8136964bae014a904b3d


---

# <a name="manage-android-for-work-devices-with-intune"></a>Android for Work-apparaten beheren met Intune

Android for Work is een set Android-apparaatfuncties en -services. Deze functies en services bieden aanvullende beheermogelijkheden en privacy wanneer mensen hun Android-apparaten voor hun werk gebruiken. Intune kan u helpen apps en bedrijfsbronnen te implementeren op Android for Work-apparaten om ervoor te zorgen dat werk- en privégegevens gescheiden zijn. Bij een succesvolle implementatie blijven apps en de gegevens waartoe ze toegang hebben, exclusief binnen de Android for Work-omgeving op het apparaat.

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

## <a name="supported-devices"></a>Ondersteunde apparaten

Android for Work vereist nieuwere Android-hardware omdat veel beheermogelijkheden afhankelijk zijn van functies die deel uitmaken van een nieuwer Android-besturingssysteem. Android for Work wordt momenteel ondersteund op apparaten met Android 5.0 Lollipop en hoger die ondersteuning voor werkprofielen bieden. Voor apparaten die geen systeemeigen ondersteuning voor Android for Work bieden, blijft het conventionele Android-beheer beschikbaar. Meer informatie over [Android for Work-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Onboarding

Voordat u Android for Work-apparaten registreert, moet u enkele stappen voor onboarding uitvoeren. Met deze stappen wordt uw Intune-tenant verbonden met de Play for Work-service van Google die een integraal onderdeel van het Android for Work-app-distributie en -beheerproces vormt. Meer informatie over [Android for Work-registratie inschakelen](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Beheer van werkprofielen

Wanneer u een Android for Work-apparaat met Intune beheert, beheert u niet het hele apparaat. De beheermogelijkheden hebben alleen betrekking op een werkprofiel dat is gemaakt tijdens de inschrijving. Alle apps die op het apparaat zijn geïmplementeerd met Intune, maken deel uit van het werkprofiel. Op de pictogrammen voor apps in het werkprofiel wordt een oranje werkmap weergegeven. Met deze markering wordt onderscheid gemaakt tussen bedrijfs-apps en persoonlijke apps op het apparaat. Alle Android-apps en -gegevens buiten het Android for Work-gedeelte van het apparaat blijven persoonlijk en onder beheer van de eindgebruiker. Gebruikers kunnen elke gewenste app aan de persoonlijke kant van het apparaat installeren, terwijl beheerders acties behorend bij het werkprofiel kunnen beheren en bewaken.

## <a name="app-publishing-and-distribution"></a>Apps publiceren en distribueren

De Google Play for Work-service vormt een integraal onderdeel van de distributie en het beheer van apps. Alle apps die op Android for Work-apparaten worden geïmplementeerd in het werkprofiel, zijn afkomstig van Play for Work. Als u apps in de Play Store wilt beheren en implementeren, meldt u zich als Intune-beheerder aan bij de Play for Work-website en zorgt u voor de goedkeuting van apps voor uw Intune-tenant. Deze apps worden met de Intune-console gesynchroniseerd waar ze vervolgens kunnen worden geïmplementeerd en beheerd met Intune. LOB-apps (Line-Of-Business) die door uw organisatie worden ontwikkeld, moeten worden gepubliceerd naar Play for Work met behulp van de Android-console voor het publiceren van apps van Google. Line-Of-Business-apps moeten worden geconfigureerd in de Android-console voor het publiceren van apps om de toegang tot uw organisatie te beperken.

Apps installeren zonder tussenkomst van de gebruiker en zonder dat de gebruiker **installatie vanuit onbekende bronnen** hoeft toe te staan. Als de gebruiker optionele of beschikbare apps wil zoeken en installeren, moet de gebruiker de met een badge voor zakelijke apps gemarkeerde Play Store-app op zijn apparaat hebben. Meer informatie over [Apps implementeren voor Android for Work](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>App-configuratie

Android for Work biedt een infrastructuur voor het implementeren van appconfiguratiewaarden naar apps die ze ondersteunen. Als u configuratiewaarden voor zakelijke apps opgeeft, zorgt u ervoor dat ze goed zijn ingesteld wanneer gebruikers de app de eerste keer starten. Ondersteuning voor app-configuratie vereist dat app-ontwikkelaars hun Android-apps specifiek ter ondersteuning van beheerde configuratiewaarden maken. Als dat het geval is, kunt u vervolgens Intune gebruiken en deze configuratie-instellingen toepassen. Meer informatie over [configuratie-instellingen voor Android for Work-apps](afw-app-configuration-policy.md).

## <a name="email-configuration"></a>E-mailconfiguratie

Android for Work biedt geen standaardapp voor e-mail of systeemeigen e-mailprofielobject zoals wordt geleverd door iOS. In plaats daarvan kunnen e-mailconfiguraties worden ingesteld door app-configuratie-instellingen toe te passen op e-mail-apps die hiervoor ondersteuning bieden. Gmail en Nine Work zijn twee EAS-clientapps (Exchange ActiveSync) in de Play Store die ondersteuning bieden voor configuratie met Android for Work-appconfiguratie.

Intune biedt configuratiesjablonen voor Gmail- en Nine Work-apps. Andere e-mailapps die ondersteuning bieden voor app-configuratieprofielen, kunnen worden geconfigureerd met beleid voor de configuratie van mobiele apps.

Als u werkt met voorwaardelijke EAS-toegang voor Android for Work-apparaten, moet u een Gmail- of Nine Work-app voor e-mail gebruiken. De Microsoft Outlook voor Android-app of een andere e-mail-app die gebruikmaakt van moderne verificatie via ADAL, wordt ook ondersteund. Meer informatie over [E-mailprofielen voor bedrijfse-mail](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="mobile-app-management-policies"></a>Mobile App Management-beleid

Beleid voor beperkingen dat wordt toegepast op apps die zijn ingeschakeld voor MAM (Mobile Application Management), wordt volledig ondersteund in het werkprofiel en in het persoonlijke profiel. U kunt Line-Of-Business-apps in de Android-console voor het publiceren van apps publiceren op https://play.google.com/apps/publish. Deze console bevat een optie om apps privé voor uw organisatie te maken. Meer informatie over [Instellingen voor nalevingsbeleid](afw-compliance-policy-settings-in-microsoft-intune.md). Zie [Mobile App Management-beleid](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) voor meer informatie.

## <a name="vpn-profiles"></a>VPN-profielen

VPN-ondersteuning is vergelijkbaar met Android VPN-profielen. Dezelfde VPN-providers en algemene configuratieopties zijn beschikbaar. Er zijn twee belangrijke verschillen:

1.  **VPN voor het werkprofiel**: VPN-verbindingen zijn alleen bedoeld voor de apps die zijn geïmplementeerd voor het werkprofiel. Alleen apps die met Android for Work worden beheerd, kunnen de VPN-verbinding gebruiken. Persoonlijke apps op het apparaat kunnen geen beheerde VPN-verbinding gebruiken.

2.  **App-specifiek VPN**: als een VPN-provider configuratie voor een app-specifiek VPN ondersteunt en de mogelijkheid biedt om per app VPN via het Android for Work-app configuratieprofiel te configureren, kan het app-specifieke VPN in Intune worden geconfigureerd. Neem contact op met de VPN-provider om te controleren of deze mogelijkheid wordt ondersteund. Meer informatie over [VPN-verbindingsprofielen](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Certificaatprofielen

Dezelfde certificaatprofielconfiguratieopties die beschikbaar zijn voor traditioneel Android-beheer, zijn beschikbaar op Android for Work-apparaten. Android for Work biedt verbeterde certificaatbeheer-API's. Het verbeterde certificaatbeheer biedt de volgende functionaliteit:

1.  Zorgt ervoor dat de implementatie van het certificaat naadloos op de achtergrond voor de gebruiker plaatsvindt.

2.  Zorgt ervoor dat geïmplementeerde certificaten volledig worden verwijderd wanneer een apparaat uit Intune wordt teruggetrokken en het werkprofiel wordt verwijderd.

3.  Biedt verbeterde berichtverzending waarbij gebruikers door hun IT-afdeling via hun beheerservice worden geïnformeerd dat het certificaat is geïmplementeerd en geconfigureerd.

Meer informatie over [Certificaatprofielen](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>Wi-Fi-profielen

Wi-Fi-profielen die worden beheerd door Android for Work, worden gegarandeerd verwijderd wanneer het apparaat uit Intune wordt teruggetrokken en het werkprofiel wordt verwijderd. Meer informatie over [Wi-Fi-profielen](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Volgende stappen
[Android for Work-registratie inschakelen](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-android-for-work)
[Apps voor Android for Work implementeren](https://docs.microsoft.com/en-us/intune/deploy-use/android-for-work-apps)



<!--HONumber=Nov16_HO5-->


