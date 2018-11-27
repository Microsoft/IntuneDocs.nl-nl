---
title: Het Intune-datawarehouse gebruiken
titlesuffix: Microsoft Intune
description: Gebruik het Intune-datawarehouse om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 13054bcaf885173e768fefb585cb71f266e9ca9e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184655"
---
# <a name="use-the-intune-data-warehouse"></a>Het Intune-datawarehouse gebruiken

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik het Intune-datawarehouse om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden. Rapporten kunnen bijvoorbeeld het volgende bevatten:
-   Trend van gebruikers die zich registreren bij Intune, zodat u uw licentieaankopen kunt optimaliseren
-   Uitsplitsing van app- en besturingssysteemversies zodat u de status van mobiele apparaten kunt controleren
-   Registratie- en apparaatnalevingstrends zodat u de implementatie van beleidsupdates soepel kunt laten verlopen

Het datawarehouse biedt u toegang tot meer informatie over uw mobiele omgeving dan Azure Portal. U hebt met het Intune-datawarehouse toegang tot:

  -  Historische Intune-gegevens
  -  Gegevens die dagelijks worden vernieuwd
  -  Een gegevensmodel waarbij de OData-standaard wordt gebruikt

> [!Note]
> Als u een hybride beheer van mobiele apparaten (MDM) met System Center Configuration Manager en Microsoft Intune gebruikt, wilt u uw gegevens ophalen uit SCCM. Het Intune-datawarehouse bevat alleen Intune-gegevens. U kunt een SCCM Power BI-dashboard gebruiken voor uw aangepaste rapporten. Zie [Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template) (Introductie van de Power BI-oplossingssjabloon voor System Center Configuration Manager) en [Power BI content for Dynamics 365](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/power-bi-home-page) (Power BI-inhoud voor Dynamics 365) voor meer informatie.

> [!Important]  
> U kunt nu versie v1.0 van een Intune-datawarehouse gebruiken door de queryparameter  `api-version=v1.0` in te stellen. Updates voor verzamelingen in het datawarehouse zijn additief van aard en veroorzaken geen problemen voor bestaande scenario's.<br><br>
> U kunt de meest recente functionaliteit van het datawarehouse met behulp van de bètaversie uitproberen. Voor het gebruik van de bètaversie moet uw URL de queryparameter  `api-version=beta` bevatten. De bètaversie biedt functies voordat ze algemeen beschikbaar zijn als een ondersteunde service. Als er nieuwe functies aan Intune worden toegevoegd, kunnen de werking en gegevenscontracten worden gewijzigd. Alle aangepaste code of rapportagemiddelen die afhankelijk zijn van de bètaversie, worden mogelijk onbruikbaar bij nieuwe updates.

**Volgende stappen**

- Haal een koppeling op en gebruik Power BI om inzicht te krijgen. Zie [Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md) (Verbinding maken met het Intune-datawarehouse met Power BI) voor instructies.
- Maak met de koppeling een aangepast rapport met Power BI. Zie [Een rapport maken van de OData-feed met Power BI](reports-proc-create-with-odata.md) voor instructies.
- Verkrijg meer informatie over de Intune-datawarehouse-API, het gegevensmodel en relaties tussen entiteiten<!-- , and an example of creating a custom client to retrieve data,--> (zie [Intune-datawarehouse-API](reports-nav-intune-data-warehouse.md)).