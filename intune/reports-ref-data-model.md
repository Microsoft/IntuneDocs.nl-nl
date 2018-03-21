---
title: Datawarehouse-gegevensmodel
titlesuffix: Microsoft Intune
description: In het Microsoft Intune-datawarehouse worden dagelijks gegevens verzameld om een historisch overzicht te bieden van uw steeds veranderende mobiele omgeving.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7bf893acd5a3d162b767744001fe2257824d86a4
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="data-warehouse-data-model"></a>Datawarehouse-gegevensmodel

In het Intune-datawarehouse worden dagelijks gegevens verzameld om een historisch overzicht te bieden van uw steeds veranderende omgeving van mobiele apparaten. De weergave bestaat uit entiteiten die in de tijd aan elkaar gerelateerd zijn.

## <a name="entities-entity-sets"></a>Entiteiten: entiteitsets

De gegevens in het datawarehouse worden in de volgende algemene gebieden ingedeeld:

  -  Apps met ingeschakelde app-beveiliging en hun gebruik
  -  Ingeschreven apparaten, eigenschappen en inventarisatie
  -  App- en software-inventarisatie
  -  Apparaatconfiguratie en nalevingsbeleid

Deze gebieden omvatten de entiteiten die relevant zijn voor uw Intune-omgeving. Informatie over de entiteitsets kunt u vinden in de volgende onderwerpen:

  -  [App](reports-ref-application.md)
  -  [Datum](reports-ref-date.md)
  -  [Apparaten](reports-ref-devices.md)
  -  [Intune-beheeruitbreiding](reports-ref-intunemanagementextension.md)
  -  [Beleid](reports-ref-policy.md)
  -  [Mobile App Management (MAM)](reports-ref-mobile-app-management.md)
  -  [Gebruiker](reports-ref-user.md)
  -  [Huidige gebruiker](reports-ref-current-user.md)
  -  [Associaties voor gebruikersapparaten](reports-ref-user-device.md)

## <a name="relationships-star-schema-model"></a>Relaties: ster-schema-model

Het datawarehouse groepeert de entiteiten in relaties die relevant zijn voor het type vragen dat u wilt stellen. U kunt bijvoorbeeld het aantal installaties van een intern ontwikkelde Android-toepassing bekijken. De structuur van het datawarehouse stelt u in staat om inzicht te krijgen in uw mobiele omgeving. Bovendien kunt u met behulp van analyseprogramma's, zoals Microsoft Power BI, visualisaties en dynamische dashboards maken op basis van het datawarehouse-gegevensmodel.

De entiteiten en relaties maken gebruik van een ster-schema-model. In een sterschema worden feiten in verband gebracht met de dimensie tijd. Een *feit* in de context van het model is een kwantitatieve meting, zoals het aantal apparaten, het aantal apps of het tijdstip van inschrijving. Feitentabellen bevatten grote hoeveelheden gegevens. Omdat ze bijzonder groot kunnen worden, blijft informatie doorgaans maximaal 30 dagen behouden. Een *dimensie* voorzien de feiten van een context. Het feit meet wat er gebeurd is, terwijl de dimensies aangeven op wie het betrekking heeft. Dimensietabellen, zoals de tabel **Gebruiker**, zijn kleiner en kunnen gegevens langere tijd vasthouden dan feitentabellen. 

Een model met een sterschema is geoptimaliseerd voor flexibiliteit en gegevensanalyse, zodat u de rapporten kunt maken die nodig zijn om een goed beeld te vormen van de steeds veranderende mobiele omgeving.

## <a name="time-daily-snapshots"></a>Tijd: dagelijkse momentopnamen

Het datawarehouse bevindt zich downstream van uw Intune-gegevens. Intune maakt dagelijks een momentopname om middernacht UTC en slaat de momentopname op in het datawarehouse. Hoelang de momentopnamen worden vastgehouden, verschilt per feitentabel. Voor sommige is dat zeven dagen, voor andere 30 dagen en voor weer andere zelfs nog langer.

## <a name="next-steps"></a>Volgende stappen

 - Zie [Levensduur gebruikers weergeven in Intune-datawarehouse](reports-ref-user-timeline.md) voor meer informatie over hoe het datawarehouse de levensduur van een gebruiker in Intune bijhoudt.
 - Zie [Eerste datawarehouse maken](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse) voor meer informatie over het werken met datawarehouses.
 - Zie [Een nieuw Power BI-rapport maken door een gegevensset te importeren](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/) voor meer informatie over het werken met Power BI en een datawarehouse. 
