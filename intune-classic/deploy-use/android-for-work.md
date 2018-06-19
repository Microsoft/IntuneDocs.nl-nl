---
title: Over Android for Work
description: Intune beheert Android for Work om aanvullende beheermogelijkheden en privacy te leveren wanneer mensen hun Android-apparaten voor hun werk gebruiken.
keywords: ''
author: nathbarn
manager: dougeby
ms.date: 03/22/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: aa0002d9-f5a0-466e-98ac-3970cb77e3a2
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: ac83eb71b04e034023d008fa4cdbb960f2c4bedb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020959"
---
# <a name="manage-android-for-work-devices-with-intune"></a>Android for Work-apparaten beheren met Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Android for Work omvat een reeks functies en services voor Android-apparaten waarmee persoonlijke apps en gegevens worden gescheiden van een werkprofiel met zakelijke apps en gegevens. Android for Work biedt aanvullende beheermogelijkheden en privacy wanneer mensen hun Android-apparaten voor hun werk gebruiken. Intune kan u helpen apps en bedrijfsbronnen te implementeren op Android for Work-apparaten om ervoor te zorgen dat werk- en privégegevens gescheiden zijn. Bij een succesvolle implementatie blijven apps en de gegevens waartoe ze toegang hebben, exclusief binnen de Android for Work-omgeving op het apparaat.

## <a name="supported-devices"></a>Ondersteunde apparaten

De beheermogelijkheden van Android for Work zijn afhankelijk van functies die deel uitmaken van een nieuwer Android-besturingssysteem. Android for Work wordt momenteel ondersteund op apparaten met Android 5.0 Lollipop en hoger die ondersteuning voor werkprofielen bieden. Voor apparaten die geen ondersteuning voor Android for Work bieden, blijft het conventionele Android-beheer beschikbaar. Meer informatie over [Android for Work-vereisten](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="onboarding"></a>Onboarding

Voordat u Android for Work-apparaten registreert, moet u enkele stappen voor onboarding uitvoeren. Met deze stappen wordt uw Intune-tenant verbonden met de Play for Work-service van Google die een integraal onderdeel van het Android for Work-app-distributie en -beheerproces vormt. Meer informatie over [Android for Work-registratie inschakelen](/intune-classic/deploy-use/set-up-android-for-work).

## <a name="work-profile-management"></a>Beheer van werkprofielen

Wanneer u een Android for Work-apparaat met Intune beheert, beheert u niet het hele apparaat. De beheermogelijkheden hebben alleen betrekking op het werkprofiel dat is gemaakt tijdens de inschrijving van het apparaat. Alle apps die op het apparaat zijn geïmplementeerd met Intune, worden geïnstalleerd in het werkprofiel. Apps in het werkprofiel worden aangegeven met een oranje werkmap om zakelijke apps te onderscheiden van persoonlijke apps op het apparaat. Alle Android-apps en -gegevens buiten het Android for Work-gedeelte van het apparaat blijven persoonlijk en onder beheer van de eindgebruiker. Gebruikers kunnen elke gewenste app aan de persoonlijke kant van het apparaat installeren, terwijl beheerders apps en acties behorend bij het werkprofiel kunnen beheren en bewaken.

Intune biedt diverse ingebouwde algemene instellingen die u op Android for Work-apparaten kunt configureren. Meer informatie over [Android for Work-beleidsinstellingen](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="app-publishing-and-distribution"></a>Apps publiceren en distribueren

De Google Play for Work-service vormt een integraal onderdeel van de distributie en het beheer van apps via Android for Work. Alle apps die op Android for Work-apparaten worden geïmplementeerd in het werkprofiel, zijn afkomstig van de Play for Work-service. Als u apps in de Play Store wilt beheren en implementeren, meldt u zich bij de Google Play-website aan met de beheerdersreferenties van uw bedrijf voor Google-beheer. U kunt apps voor de Android for Work-implementatie goedkeuren zodat deze in de werkprofielen van apparaten worden weergegeven. Deze apps worden dan met de Intune-console gesynchroniseerd waar ze vervolgens kunnen worden geïmplementeerd en beheerd met Intune. LOB-apps (Line-Of-Business) die door uw organisatie worden ontwikkeld, moeten worden gepubliceerd naar Play for Work met behulp van de Android-console voor het publiceren van apps van Google. Line-Of-Business-apps moeten worden geconfigureerd in de Android-console voor het publiceren van apps om de toegang tot uw organisatie te beperken.

Apps kunnen worden geïnstalleerd zonder tussenkomst van de gebruiker en zonder dat de gebruiker **installatie vanuit onbekende bronnen** hoeft toe te staan. Als gebruikers optionele of beschikbare apps willen zoeken en installeren, kunnen ze zoeken in de Play for Work Store op hun apparaat. Meer informatie over [Apps implementeren voor Android for Work](/intune-classic/deploy-use/android-for-work-apps).

## <a name="app-configuration"></a>App-configuratie

Android for Work biedt een infrastructuur voor het implementeren van appconfiguratiewaarden naar apps die ze ondersteunen. Als u configuratiewaarden voor zakelijke apps opgeeft, zorgt u ervoor dat ze goed zijn ingesteld wanneer gebruikers de app de eerste keer starten. Ondersteuning voor app-configuratie vereist dat app-ontwikkelaars hun Android-apps specifiek ter ondersteuning van beheerde configuratiewaarden maken. Als dat het geval is, kunt u vervolgens Intune gebruiken en deze configuratie-instellingen toepassen. Meer informatie over [configuratie-instellingen voor Android for Work-apps](afw-app-configuration-policy.md).

## <a name="email-configuration"></a>E-mailconfiguratie

Android for Work biedt geen standaardapp voor e-mail of een eigen e-mailprofielobject zoals door iOS wordt geboden. In plaats daarvan kunnen e-mailconfiguraties worden ingesteld door app-configuratie-instellingen toe te passen op e-mail-apps die hiervoor ondersteuning bieden. Gmail en Nine Work zijn twee EAS-clientapps (Exchange ActiveSync) in de Play Store die ondersteuning bieden voor configuratie met Android for Work-appconfiguratie.

Intune biedt configuratiesjablonen voor Gmail- en Nine Work-apps wanneer deze als zakelijke apps worden beheerd. Andere e-mail-apps die ondersteuning bieden voor app-configuratieprofielen, kunnen worden geconfigureerd met beleid voor de configuratie van mobiele apps.

Als u werkt met voorwaardelijke toegang via Exchange ActiveSync voor Android for Work-apparaten, moet u een Gmail- of Nine Work-app voor e-mail gebruiken. De Microsoft Outlook voor Android-app of een andere e-mail-app die gebruikmaakt van moderne verificatie via ADAL, wordt ook ondersteund. Meer informatie over [E-mailprofielen voor bedrijfse-mail](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).

## <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Appbeveiligingsbeleid dat wordt toegepast, wordt volledig ondersteund in het werkprofiel en in het persoonlijk profiel. U kunt Line-Of-Business-apps in de Android-console voor het publiceren van apps publiceren op https://play.google.com/apps/publish. Deze console bevat een optie om apps privé voor uw organisatie te maken. Meer informatie over [Instellingen voor nalevingsbeleid voor Android for Work](afw-compliance-policy-settings-in-microsoft-intune.md). Raadpleeg [Appbeleid](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md) voor algemene informatie over het beleid met betrekking tot de beveiliging van apps.

## <a name="vpn-profiles"></a>VPN-profielen

VPN-ondersteuning is vergelijkbaar met Android VPN-profielen. Dezelfde VPN-providers en algemene configuratieopties zijn beschikbaar voor Android for Work-beheer, met twee verschillen:

-  **VPN voor het werkprofiel**: VPN-verbindingen zijn beperkt tot de apps die zijn geïmplementeerd voor het werkprofiel. Alleen apps die met Android for Work worden beheerd, kunnen de VPN-verbinding gebruiken. Persoonlijke apps op het apparaat kunnen geen beheerde VPN-verbinding gebruiken.

-  **App-specifiek VPN**: als een VPN-provider configuratie voor een app-specifiek VPN ondersteunt en de mogelijkheid biedt om VPN per app te configureren via het configuratieprofiel voor Android for Work-apps, kan een app-specifieke VPN in Intune worden geconfigureerd. Neem contact op met de VPN-provider om te controleren of deze mogelijkheid wordt ondersteund. Meer informatie over [VPN-verbindingsprofielen](vpn-connections-in-microsoft-intune.md).

## <a name="certificate-profiles"></a>Certificaatprofielen

Dezelfde certificaatprofielconfiguratieopties die beschikbaar zijn voor Android-beheer, zijn beschikbaar op Android for Work-apparaten. Android for Work biedt verbeterde certificaatbeheer-API's. Het verbeterde certificaatbeheer biedt de volgende functionaliteit:

- Zorgt ervoor dat de implementatie van het certificaat naadloos op de achtergrond voor de gebruiker plaatsvindt.
-  Zorgt ervoor dat geïmplementeerde certificaten volledig worden verwijderd wanneer een apparaat uit Intune wordt teruggetrokken en het werkprofiel wordt verwijderd.
-  Biedt verbeterde berichtverzending waarbij gebruikers door hun IT-afdeling via hun beheerservice worden geïnformeerd dat het certificaat is geïmplementeerd en geconfigureerd.

Meer informatie over [Certificaatprofielen](secure-resource-access-with-certificate-profiles.md).

## <a name="wi-fi-profiles"></a>Wi-Fi-profielen

Wi-Fi-profielen die worden beheerd door Android for Work, worden verwijderd wanneer het apparaat uit Intune wordt teruggetrokken en het werkprofiel wordt verwijderd. Meer informatie over [Wi-Fi-profielen](wi-fi-connections-in-microsoft-intune.md).

## <a name="next-steps"></a>Volgende stappen
[Android for Work-registratie inschakelen](/intune-classic/deploy-use/set-up-android-for-work)

[Apps implementeren voor Android for Work](/intune-classic/deploy-use/android-for-work-apps)
