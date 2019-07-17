---
title: Mobile Threat Defense met Microsoft Intune
titleSuffix: Microsoft Intune
description: Gebruik Intune Mobile Threat Defense (MTD) met uw Mobile Threat Defense-partner om toegang tot bedrijfsresources te beveiligen op basis van het apparaatrisico.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73c8167c91129d79a98674a92e7ccc5487a6b283
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885088"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Wat is Mobile Threat Defense-integratie met Intune?
Intune kan gegevens van een Mobile Threat Defense-leverancier als gegevensbron voor nalevingsbeleid en regels voor voorwaardelijke toegang integreren. U kunt deze gegevens gebruiken voor de beveiliging van bedrijfsresources zoals Exchange en SharePoint door de toegang te blokkeren voor mobiele apparaten die zijn gecompromitteerd.  

## <a name="what-problem-does-this-solve"></a>Welk probleem wordt hiermee opgelost?
Integratiegegevens van een Mobile Threat Defense-leverancier kunnen helpen uw bedrijfsresources te beschermen tegen bedreigingen die invloed hebben op mobiele platforms.  

Bedrijven zijn meestal proactief bij het beveiligen van pc's tegen aanvallen, maar dat geldt niet voor mobiele apparaten die vaak niet worden bewaakt en beveiligd. Mobiele platforms beschikken weliswaar over geïntegreerde beveiliging (bijvoorbeeld de isolatie van apps en gescreende app-stores), maar ze blijven kwetsbaar voor geavanceerde aanvallen. Het gebruik van diverse apparaten voor werk en de toegang tot gevoelige informatie neemt steeds meer toe. De gegevens van de Mobile Threat Defense-leverancier kunnen helpen apparaten en uw resources tegen steeds geavanceerder wordende aanvallen te beschermen.  

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Hoe werken de Intune Mobile Threat Defense-connectors?

Intune gebruikt een Mobile Threat Defense-connector om een communicatiekanaal te maken tussen Intune en de door u gekozen Mobile Threat Defense-leverancier. Intune Mobile Threat Defense-partners bieden intuïtieve, eenvoudig te implementeren toepassingen voor mobiele apparaten. Met deze toepassingen wordt bedreigingsinformatie actief gescand en geanalyseerd om met Intune te delen. Intune kan de gegevens voor rapportage- of afdwingingsdoeleinden gebruiken.  

Bijvoorbeeld: Een verbonden Mobile Threat Defense-app meldt aan de Mobile Threat Defense-leverancier dat een telefoon in uw netwerk op het moment is verbonden met een netwerk dat kwetsbaar is voor man-in-the-middle-aanvallen. Voor deze informatie wordt bepaald of het risiconiveau laag, middelhoog of hoog is. Het risiconiveau wordt vervolgens vergeleken met de toegestane risico's die u in Intune hebt ingesteld. Op basis van deze vergelijking kan toegang tot bepaalde resources van uw keuze worden ingetrokken wanneer het apparaat is gecompromitteerd.

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a>Welke gegevens worden door Intune verzameld voor Mobile Threat Defense?

Als deze optie is ingeschakeld, verzamelt Intune informatie over de app-inventaris van apparaten in zowel privé- als bedrijfseigendom en maakt Intune deze informatie beschikbaar voor MTD-providers om op te halen, zoals Lookout for Work. U kunt de app-inventaris verzamelen van gebruikers van iOS-apparaten.

Deze service is opt-in; er wordt standaard geen informatie over app-inventaris gedeeld. Een Intune-beheerder moet App Sync voor iOS-apparaten inschakelen in de service-instellingen voordat informatie over app-inventaris wordt gedeeld.

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

## <a name="sample-scenarios"></a>Voorbeeldscenario's

Wanneer een apparaat wordt beschouwd als geïnfecteerd door de Mobile Threat Defense-oplossing:

![Afbeelding met een apparaat dat volgens Mobile Threat Defense is geïnfecteerd](./media/MTD-image-1.png)

Toegang wordt geboden wanneer het apparaat is hersteld:

![Afbeelding met een apparaat waartoe middels Mobile Threat Defense toegang is verleend](./media/MTD-image-2.png)

> [!NOTE] 
> Het gebruik van meerdere Mobile Threat Defense-leveranciers met Intune wordt niet ondersteund. Als u meerdere MTD-programma's hebt ingeschakeld, worden alle MTD-apps geïnstalleerd en wordt er op alle apparaten gescand op bedreigingen.

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense-partners

Meer informatie over het beveiligen van de toegang tot bedrijfsresources op basis van apparaat, netwerk en toepassingsrisico met:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Symantec Endpoint Protection Mobile](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [Zimperium](zimperium-mobile-threat-defense-connector.md)
- [Pradeo](pradeo-mobile-threat-defense-connector.md)
- [Better Mobile](better-mobile-threat-defense-connector.md)
- [Sophos Mobile](sophos-mtd-connector.md)
- [Wandera Mobile Threat Defense](wandera-mtd-connector.md)
