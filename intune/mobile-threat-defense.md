---
title: Mobile Threat Defense met Intune
titleSuffix: Azure portal
description: De toegang tot bedrijfsresources beveiligen op basis van apparaatrisico
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f9c28bbd06fbee620466d4f269fbb08d98bbcde2
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a>Integratie van Mobile Threat Defense met Intune


Met Intune Mobile Threat Defense-connectors kunt u de door uw gekozen Mobile Threat Defense-leverancier gebruiken als bron van informatie over uw nalevingsbeleid en regels voor voorwaardelijke toegang. Hiermee kunnen IT-beheerders een extra beveiligingslaag toevoegen aan hun bedrijfsresources zoals Exchange en Sharepoint, ter bescherming tegen met name verdachte mobiele apparaten.

## <a name="what-problem-does-this-solve"></a>Welk probleem wordt hiermee opgelost?

Bedrijven moeten gevoelige gegevens tegen nieuwe bedreigingen beschermen. Denk daarbij aan fysieke bedreigingen, apps die een bedreiging vormen, bedreigingen in het netwerk en beveiligingsproblemen van besturingssystemen.
Bedrijven zijn historisch gezien altijd proactief geweest in het beveiligen van pc's tegen aanvallen, maar dat geldt niet voor mobiele apparaten. Mobiele platformen beschikken over geïntegreerde beveiliging, zoals de isolatie van apps en gescreende app-stores, maar ze blijven kwetsbaar voor geavanceerde aanvallen. Tegenwoordig gebruiken meer werknemers apparaten voor het werk en hebben ze toegang tot gevoelige informatie nodig. Apparaten moeten worden beveiligd tegen steeds geavanceerder wordende aanvallen.

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a>Hoe werken Intune Mobile Threat Defense-connectors?

De connector beschermt bedrijfsresources door een communicatiekanaal te maken tussen Intune en de door uw gekozen Mobile Threat Defense-leverancier. Intune Mobile Threat Defense-partners bieden intuïtieve, eenvoudig te implementeren toepassingen voor mobiele apparaten, die informatie over apparaatbedreigingen actief scannen, analyseren en met Intune delen, voor rapportage- of afdwingingsdoeleinden. Als bijvoorbeeld een verbonden Mobile Threat Defense-app aan de Mobile Threat Defense-leverancier rapporteert dat een telefoon in uw netwerk op dat moment is verbonden met een netwerk dat kwetsbaar is voor Man in the Middle-aanvallen, wordt die informatie gedeeld en ingedeeld in een toepasselijke risicocategorie (laag, gemiddeld of hoog). Die wordt vergeleken met het geconfigureerde toegestane risiconiveau in Intune, om te bepalen of de toegangsrechten tot door u gekozen resources moet worden ingetrokken zolang het apparaat verdacht is.

## <a name="sample-scenarios"></a>Voorbeeldscenario's

Wanneer een apparaat wordt beschouwd als geïnfecteerd door de Mobile Threat Defense-oplossing:

![Geïnfecteerd apparaat volgens Mobile Threat Defense](./media/MTD-image-1.png)

Toegang wordt geboden wanneer het apparaat is hersteld:

![Toegang verleend door Mobile Threat Defense](./media/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a>Mobile Threat Defense-partners

Meer informatie over het beveiligen van de toegang tot bedrijfsresources op basis van apparaat, netwerk en toepassingsrisico met:

- [Lookout](lookout-mobile-threat-defense-connector.md)
- [Skycure](skycure-mobile-threat-defense-connector.md)
- [Check Point SandBlast Mobile](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)