---
title: De werking van een normale Intune-migratiecyclus | Microsoft Docs
description: In dit artikel wordt uitgelegd hoe een Intune-migratiecyclus werkt en worden voorbeelden gegeven van de wijze waarop klanten de migratiecycli uitvoeren.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: aa8fb215772b6e8d3a913d929c030d68e363970b
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-typical-migration-cycle"></a>Fase 2: normale migratiecyclus

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Het is gebruikelijk voor een organisatie om de Intune-migratie te starten met een korte testfase onder een aantal gebruikers op de IT-afdeling. Bovendien moet uw organisatie mogelijk thema’s bespreken als de welwillendheid van medewerkers ten aanzien van de wijziging, het aantal gebruikers, de complexiteit, de vereisten, de locatie en het bedrijfsrisico zodat u het tijdskader voor de migratie kunt bepalen.

Hier volgt een voorbeeld van de wijze waarop u uw doelgroepen kunt plannen:

  | **Doelgroepen van de migratie** | **Periode 1** | **Periode 2** | **Periode 3** | **Periode 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Beperkte testfase voor de IT-organisatie (50 gebruikers) | Plan aankondigen | Opdracht geven tot deelname | Opgeven van de deadline | De voorwaardelijke toegang toepassen |  |                                                        
| Uitgebreide testfase voor de IT-organisatie (200 gebruikers) |  | Plan aankondigen | Opdracht geven tot deelname | Opgeven van de deadline | De voorwaardelijke toegang toepassen | 
| Fase 1 van de migratie met technisch onderlegde gebruikers (2000) |  |  | Plan aankondigen | Opdracht geven tot deelname | Opgeven van de deadline | 
| Fase 2 van de migratie (oostelijk deel van de V.S.) |  |  |  | Plan aankondigen | Opdracht geven tot deelname | 
| Alle regio 's |  |  |  |  | Plan aankondigen | 

## <a name="customer-migration-case-study"></a>Casestudy van de klantmigratie

### <a name="adatum-corporation"></a>Adatum Corporation

- Bekijk [hoe Adatum Corporation een migratie heeft doorgevoerd van een externe MDM-provider naar Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Migratiebewaking

Microsoft Intune biedt verschillende methoden om de migratie te bewaken:

1.  Groepsweergaven van Intune-gebruikers

2.  Een reeks ingebouwde rapporten en

3.  Waarschuwingen in de Intune-beheerconsole.

U moet bijhouden hoeveel gebruikers apparaten hebben ingeschreven na elke fase zodat u het volgende kunt doen:

-   De effectiviteit van uw communicatieplan beoordelen.

-   De gevolgen van het doorvoeren van de voorwaardelijke toegang beoordelen.

Meer informatie over [het bewaken van de Intune-migratie](https://docs.microsoft.com/intune/deploy-use/understand-microsoft-intune-operations-by-using-reports).

## <a name="post-migration"></a>Na migratie

U moet de voorgaande MDM-provider buiten gebruik stellen en/of u afmelden voor de service nadat de migratie naar Intune is uitgevoerd. Daarnaast moet u eventuele overbodige infrastructuurvereisten verwijderen door de instructies van de MDM-provider te volgen.

