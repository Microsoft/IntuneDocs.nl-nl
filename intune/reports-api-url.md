---
title: Intune-datawarehouse-API-eindpunt
titlesuffix: Microsoft Intune
description: Dit naslagonderwerp beschrijft de URL-structuur van de Microsoft Intune-datawarehouse-API. Er worden filtervoorbeelden gegeven.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: caf4401a2274a74050ec0eb404363cfc15b23e76
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851437"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune-datawarehouse-API-eindpunt

U kunt de Intune-datawarehouse-API gebruiken met een account met specifiek op rollen gebaseerd toegangsbeheer en Azure AD-referenties. Vervolgens autoriseert u uw REST client met Azure AD met behulp van OAuth 2.0. En ten slotte vormt u een zinvolle URL voor het aanroepen van een datawarehouseresource.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autorisatie

Azure Active Directory (Azure AD) maakt gebruik van OAuth 2.0 om het mogelijk te maken dat u toegang tot webtoepassingen en web-API's in uw Azure AD-tenant kunt autoriseren. In deze taalonafhankelijke handleiding wordt beschreven hoe u HTTP-berichten verzendt en ontvangt zonder open source-bibliotheken te gebruiken. De OAuth 2.0-autorisatiecodestroom wordt beschreven in [sectie 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) van de OAuth 2.0-specificatie.

Zie [Toegang tot webtoepassingen die gebruikmaken van OAuth 2.0 en Azure Active Directory autoriseren](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code) voor meer informatie.

## <a name="api-url-structure"></a>API URL-structuur

De datawarehouse-API-eindpunten lezen de entiteiten voor elke set. De API ondersteunt een **GET** HTTP-woord en een subset queryopties.

Voor de URL voor Intune wordt de volgende notatie gebruikt:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> Vervang in de bovenstaande URL `{location}`, `{entity-collection}`en `{api-version}` op basis van de informatie in de onderstaande tabel.

De URL bevat de volgende elementen:

| Element | Voorbeeld | Beschrijving |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | De basis-URL kan worden gevonden door de blade Datawarehouse-API in Azure Portal te bekijken. |
| entiteitverzameling | dates | De naam van de OData-entiteitverzameling. Zie [Gegevensmodel](reports-ref-data-model.md) voor meer informatie over verzamelingen en entiteiten in het gegevensmodel. |
| api-versie | beta | Version is de versie van de API waartoe toegang moet worden verkregen. Zie [Versie](#API-version-information) voor meer informatie. |
| maxhistorydays | 7 | (Optioneel) Het maximum aantal dagen waarin de geschiedenis kan worden opgehaald. Deze parameter kan worden geleverd aan een verzameling, maar wordt pas van kracht voor verzamelingen met `dateKey` als onderdeel van de sleuteleigenschap ervan. Zie [Bereikfilters DateKey](reports-api-url.md#datekey-range-filters) voor meer informatie. |

## <a name="api-version-information"></a>API-versiegegevens

De huidige versie van de API is `beta`. 

## <a name="odata-query-options"></a>OData-queryopties

De huidige versie ondersteunt de volgende OData-queryparameters: `$filter, $orderby, $select, $skip,` en `$top`.

## <a name="datekey-range-filters"></a>Bereikfilters DateKey

`DateKey`-bereikfilters kunnen worden gebruikt voor het beperken van de hoeveelheid te downloaden gegevens voor enkele verzamelingen met `dateKey` als een sleuteleigenschap. Het `DateKey`-filter kan worden gebruikt voor het optimaliseren van serviceprestaties door de volgende `$filter`-queryparameter op te geven:

1.  `DateKey` alleen in de `$filter`, waarbij de `lt/le/eq/ge/gt`-operators worden ondersteund en worden gekoppeld aan de logische operator `and`, waar ze kunnen worden toegewezen aan een begindatum en/of einddatum.
2.  `maxhistorydays` wordt opgegeven als aangepaste query.<br>

## <a name="filter-examples"></a>Voorbeelden van filters

> [!NOTE]
> Bij de filtervoorbeelden wordt ervan uitgegaan dat het vandaag 21-2-2018 is.

|                             Filter                             |           Prestatieoptimalisatie           |                                          Beschrijving                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Volledig                                      |    Gegevens retourneren met `DateKey` tussen 20180214 en 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Volledig                                      |    Gegevens retourneren met `DateKey` gelijk aan 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Volledig                                      |    Gegevens retourneren met `DateKey` tussen 20180214 en 20180220.                                     |
|    `maxhistorydays=7&$filter=Id gt 1`                            |    Gedeeltelijk, id-prt 1 wordt niet geoptimaliseerd    |    Gegevens retourneren met `DateKey` tussen 20180214 20180221 en id groter dan 1.             |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Volledig                                      |    Gegevens retourneren met `DateKey` gelijk aan 20180214. `maxhistorydays` wordt genegeerd.                            |
|    `$filter=DateKey eq 20180214 and Id gt 1`                     |    Geen                                      |    Niet behandeld als `DateKey`-bereikfilter, waardoor er dus geen prestatieverhoging is.                              |
|    `$filter=DateKey ne 20180214`                                 |    Geen                                      |    Niet behandeld als `DateKey`-bereikfilter, waardoor er dus geen prestatieverhoging is.                              |
|    `maxhistorydays=7&$filter=DateKey eq 20180214 and Id gt 1`    |    Geen                                      |    Niet behandeld als `DateKey`-bereikfilter, waardoor er dus geen prestatieverhoging is. `maxhistorydays` genegeerd.    |
