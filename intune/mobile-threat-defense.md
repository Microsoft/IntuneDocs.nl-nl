---
title: Mobile Threat Defense met Microsoft Intune | Microsoft Intune
description: Gebruik Intune Mobile Threat Defense (MTD) met uw Mobile Threat Defense-partner om toegang tot bedrijfsresources te beveiligen op basis van het apparaatrisico.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/28/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 18161e8293ae92420f9437dab18e008e8e57b93a
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816596"
---
# <a name="what-is-mobile-threat-defense-integration-with-intune"></a>Wat is Mobile Threat Defense-integratie met Intune?


Met Intune Mobile Threat Defense-connectors kunt u de door uw gekozen Mobile Threat Defense-leverancier gebruiken als bron van informatie over uw nalevingsbeleid en regels voor voorwaardelijke toegang. Hiermee kunnen IT-beheerders een extra beveiligingslaag toevoegen aan hun bedrijfsresources zoals Exchange en Sharepoint, ter bescherming tegen met name verdachte mobiele apparaten.

## <a name="what-problem-does-this-solve"></a>Welk probleem wordt hiermee opgelost?

Bedrijven moeten gevoelige gegevens tegen nieuwe bedreigingen beschermen. Denk daarbij aan fysieke bedreigingen, apps die een bedreiging vormen, bedreigingen in het netwerk en beveiligingsproblemen van besturingssystemen.

Bedrijven zijn historisch gezien altijd proactief geweest in het beveiligen van pc's tegen aanvallen, maar dat geldt niet voor mobiele apparaten. Mobiele platformen beschikken over geïntegreerde beveiliging, zoals de isolatie van apps en gescreende app-stores, maar ze blijven kwetsbaar voor geavanceerde aanvallen. Tegenwoordig gebruiken meer werknemers apparaten voor het werk en hebben ze toegang tot gevoelige informatie nodig. Apparaten moeten worden beveiligd tegen steeds geavanceerder wordende aanvallen.

## <a name="how-do-the-intune-mobile-threat-defense-connectors-work"></a>Hoe werken de Intune Mobile Threat Defense-connectors?

De connector beschermt bedrijfsresources door een communicatiekanaal te maken tussen Intune en de door uw gekozen Mobile Threat Defense-leverancier. Intune Mobile Threat Defense-partners bieden intuïtieve, eenvoudig te implementeren toepassingen voor mobiele apparaten, die voor rapportage- of afdwingingsdoeleinden informatie over apparaatbedreigingen die u met Intune wilt delen actief scannen en analyseren. 

Als bijvoorbeeld een verbonden Mobile Threat Defense-app aan de Mobile Threat Defense-leverancier rapporteert dat een telefoon in uw netwerk op dat moment is verbonden met een netwerk dat kwetsbaar is voor Man in the Middle-aanvallen, wordt die informatie gedeeld en ingedeeld in een toepasselijke risicocategorie (laag, gemiddeld of hoog). Die wordt vergeleken met het geconfigureerde toegestane risiconiveau in Intune, om te bepalen of de toegangsrechten tot door u gekozen resources moet worden ingetrokken zolang het apparaat verdacht is.

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
