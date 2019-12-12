---
title: Het Intune-datawarehouse gebruiken
titleSuffix: Microsoft Intune
description: Gebruik het Intune-datawarehouse om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f382ce35d1d13a59f1aa5ca6a904c0c9babff8c1
ms.sourcegitcommit: 7cc45ef52dda08479bc6bdff7d11d2f6c0e7b93b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2019
ms.locfileid: "74899344"
---
# <a name="use-the-microsoft-intune-data-warehouse"></a>Het Intune-datawarehouse gebruiken

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gebruik het Intune-datawarehouse om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden. Rapporten kunnen bijvoorbeeld het volgende bevatten:
- Trend van gebruikers die zich registreren bij Intune, zodat u uw licentieaankopen kunt optimaliseren
- Uitsplitsing van app- en besturingssysteemversies zodat u de status van mobiele apparaten kunt controleren
- Registratie- en apparaatnalevingstrends zodat u de implementatie van beleidsupdates soepel kunt laten verlopen

## <a name="data-warehouse-benefits"></a>Voordelen van het datawarehouse

Het datawarehouse biedt u toegang tot meer informatie over uw mobiele omgeving dan Azure Portal. U hebt met het Intune-datawarehouse toegang tot:

- Historische Intune-gegevens
- Gegevens die dagelijks worden vernieuwd
- Een gegevensmodel waarbij de OData-standaard wordt gebruikt

> [!Note]
> Als u gebruikmaakt van gezamenlijk beheerd Mobile Device Management (MDM) met System Center Configuration Manager en Microsoft Intune, moet u uw gegevens ophalen uit Configuration Manager. Het Intune-datawarehouse bevat alleen Intune-gegevens. U kunt een Configuration Manager Power BI-dashboard gebruiken voor uw aangepaste rapporten. Zie [Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template) (Introductie van de Power BI-oplossingssjabloon voor System Center Configuration Manager) en [Power BI content for Dynamics 365](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/power-bi-home-page) (Power BI-inhoud voor Dynamics 365) voor meer informatie.

> [!Important]  
> U kunt nu versie v1.0 van een Intune-datawarehouse gebruiken door de queryparameter  `api-version=v1.0` in te stellen. Updates voor verzamelingen in het datawarehouse zijn additief van aard en veroorzaken geen problemen voor bestaande scenario's.<br><br>
> U kunt de meest recente functionaliteit van het datawarehouse met behulp van de bètaversie uitproberen. Voor het gebruik van de bètaversie moet uw URL de queryparameter  `api-version=beta` bevatten. De bètaversie biedt functies voordat ze algemeen beschikbaar zijn als een ondersteunde service. Als er nieuwe functies aan Intune worden toegevoegd, kunnen de werking en gegevenscontracten worden gewijzigd. Alle aangepaste code of rapportagemiddelen die afhankelijk zijn van de bètaversie, worden mogelijk onbruikbaar bij nieuwe updates.

## <a name="next-steps"></a>Volgende stappen

- Haal een koppeling op en gebruik Power BI om inzicht te krijgen. Zie [Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md) (Verbinding maken met het Intune-datawarehouse met Power BI) voor instructies.
- Maak met de koppeling een aangepast rapport met Power BI. Zie [Een rapport maken van de OData-feed met Power BI](reports-proc-create-with-odata.md) voor instructies.
- Voor meer informatie over de Intune Data Warehouse-API, het gegevensmodel en relaties tussen entiteiten,<!-- , and an example of creating a custom client to retrieve data,--> zie [Intune Data Warehouse-API](reports-nav-intune-data-warehouse.md).
