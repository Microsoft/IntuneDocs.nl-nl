---
title: Mobile Threat Defense met Microsoft Intune
titleSuffix: Microsoft Intune
description: Gebruik Intune Mobile Threat Defense (MTD) met uw Mobile Threat Defense-partner om toegang tot bedrijfsresources te beveiligen op basis van het apparaatrisico.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b67e3b14fd94376fb6dacad88fa58ddc460a6bc5
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73057583"
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integratie van Mobile Threat Defense met Intune

Intune kan gegevens van een Mobile Threat Defense-leverancier (MTD) integreren als een gegevensbron voor apparaatnalevingsbeleid en regels voor voorwaardelijke toegang tot apparaten. U kunt deze gegevens gebruiken voor de beveiliging van bedrijfsresources zoals Exchange en SharePoint door de toegang te blokkeren voor mobiele apparaten die zijn gecompromitteerd.

Intune kan dezelfde gegevens gebruiken als een bron voor niet-ingeschreven apparaten met behulp van het Intune-beveiligingsbeleid voor apps. Beheerders kunnen daarom deze informatie gebruiken om bedrijfsgegevens te beschermen binnen een [met Microsoft Intune beveiligde app](~/apps/apps-supported-intune-apps.md) en een blok uitgeven of selectief wissen.

## <a name="protect-corporate-resources"></a>Bedrijfsresources beveiligen

Door gegevens van MTD-leveranciers te integreren, kunt u uw bedrijfsresources beschermen tegen bedreigingen die invloed hebben op mobiele platforms.  

Bedrijven zijn meestal proactief bij het beveiligen van pc's tegen aanvallen, maar dat geldt niet voor mobiele apparaten die vaak niet worden bewaakt en beveiligd. Mobiele platforms beschikken weliswaar over geïntegreerde beveiliging (bijvoorbeeld de isolatie van apps en gescreende app-stores), maar ze blijven kwetsbaar voor geavanceerde aanvallen. Het gebruik van diverse apparaten voor werk en toegang tot gevoelige informatie neemt steeds meer toe. De gegevens van MTD-leveranciers kunnen helpen om apparaten en uw resources tegen steeds geavanceerder wordende aanvallen te beschermen.

## <a name="intune-mobile-threat-defense-connectors"></a>Intune Mobile Threat Defense-connectors

Intune gebruikt een Mobile Threat Defense-connector om een communicatiekanaal te maken tussen Intune en de door u gekozen MTD-leverancier. Intune MTD-partners bieden intuïtieve en eenvoudig te implementeren toepassingen voor mobiele apparaten. Met deze toepassingen wordt bedreigingsinformatie actief gescand en geanalyseerd om met Intune te delen. Intune kan de gegevens voor rapportage- of afdwingingsdoeleinden gebruiken.

Bijvoorbeeld: Een verbonden MTD-app meldt aan de MTD-leverancier dat een telefoon in uw netwerk op dat moment is verbonden met een netwerk dat kwetsbaar is voor man-in-the-middle-aanvallen. Voor deze informatie wordt bepaald of het risiconiveau laag, middelhoog of hoog is. Het risiconiveau wordt vervolgens vergeleken met de toegestane risico's die u in Intune hebt ingesteld. Op basis van deze vergelijking kan toegang tot bepaalde resources van uw keuze worden ingetrokken wanneer het apparaat is gecompromitteerd.

## <a name="data-that-intune-collects-for-mobile-threat-defense"></a>Gegevens die door Intune worden verzameld voor Mobile Threat Defense

Als deze optie is ingeschakeld, verzamelt Intune informatie over de app-inventaris van apparaten in zowel privé- als bedrijfseigendom en maakt Intune deze informatie beschikbaar voor MTD-providers om op te halen, zoals Lookout for Work. U kunt de app-inventaris verzamelen van gebruikers van iOS-apparaten.

Deze service is opt-in; er wordt standaard geen informatie over app-inventaris gedeeld. Een Intune-beheerder moet **synchronisatie van apps voor iOS-apparaten** inschakelen in de instellingen van de Mobile Threat Defense-connector voordat informatie over app-inventaris wordt gedeeld.

**App-inventaris**  
Als u App Sync voor iOS-apparaten inschakelt, worden inventarissen van iOS-apparaten in zowel bedrijfs- en privé-eigendom verzonden naar uw MTD-serviceprovider. Gegevens in de app-inventarisatie bestaan onder andere uit:

- App-id
- App-versie
- Verkorte App-versie
- App-naam
- Grootte van de App-bundel
- Dynamische grootte van de App
- Of de app wel of niet is gevalideerd
- Of de app wel of niet wordt beheerd

## <a name="sample-scenarios-for-enrolled-devices-using-device-compliance-policies"></a>Voorbeeldscenario's voor geregistreerde apparaten met behulp van het nalevingsbeleid voor apparaten

Wanneer een apparaat wordt beschouwd als geïnfecteerd door de Mobile Threat Defense-oplossing:

![Afbeelding met een apparaat dat volgens Mobile Threat Defense is geïnfecteerd](./media/mobile-threat-defense/MTD-image-1.png)

Toegang wordt geboden wanneer het apparaat is hersteld:

![Afbeelding met een apparaat waartoe middels Mobile Threat Defense toegang is verleend](./media/mobile-threat-defense/MTD-image-2.png)

## <a name="sample-scenarios-for-unenrolled-devices-using-intune-app-protection-policies"></a>Voorbeeldscenario's voor niet-geregistreerde apparaten met behulp van het app-beveiligingsbeleid van Intune

Wanneer een apparaat wordt beschouwd als geïnfecteerd door de Mobile Threat Defense-oplossing:<br>
![Afbeelding van een apparaat dat volgens Mobile Threat Defense is geïnfecteerd](./media/mobile-threat-defense/MTD-image-3.png)

Toegang wordt geboden wanneer het apparaat is hersteld:<br>
![Afbeelding van een apparaat waartoe middels Mobile Threat Defense toegang is verleend](./media/mobile-threat-defense/MTD-image-4.png)

> [!NOTE]
> U kunt meerdere Mobile Threat Defense-leveranciers gebruiken met één Intune-tenant. Wanneer echter twee of meer leveranciers zijn geconfigureerd voor hetzelfde platform, moet op alle apparaten die dat platform uitvoeren, elke MTD-app worden geïnstalleerd en moet er op bedreigingen worden gescand. Als er geen scan kan worden verzonden vanuit een geconfigureerde app, heeft dit als gevolg dat het apparaat als niet-compatibel wordt gemarkeerd. 

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense-partners

Meer informatie over het beveiligen van de toegang tot bedrijfsresources op basis van apparaat, netwerk en toepassingsrisico met:

- [Lookout for Work](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Wandera Mobile Threat Defense](wandera-mtd-connector.md)
