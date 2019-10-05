---
title: Intune-datawarehouse-API-eindpunt
titleSuffix: Microsoft Intune
description: Dit naslagonderwerp beschrijft de URL-structuur van de Microsoft Intune-datawarehouse-API. Er worden filtervoorbeelden gegeven.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f73e80fed5de74bc074e26502270467b7d846e5c
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940146"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune-datawarehouse-API-eindpunt

U kunt de Intune-datawarehouse-API gebruiken met een account met specifiek op rollen gebaseerd toegangsbeheer en Azure AD-referenties. Vervolgens autoriseert u uw REST client met Azure AD met behulp van OAuth 2.0. En ten slotte vormt u een zinvolle URL voor het aanroepen van een datawarehouseresource.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

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
| entiteitverzameling | devicePropertyHistories | De naam van de OData-entiteitverzameling. Zie [Gegevensmodel](reports-ref-data-model.md) voor meer informatie over verzamelingen en entiteiten in het gegevensmodel. |
| api-versie | beta | Version is de versie van de API waartoe toegang moet worden verkregen. Zie [Versie](reports-api-url.md#api-version-information) voor meer informatie. |
| maxhistorydays | 7 | (Optioneel) Het maximum aantal dagen waarin de geschiedenis kan worden opgehaald. Deze parameter kan worden geleverd aan een verzameling, maar wordt pas van kracht voor verzamelingen met `dateKey` als onderdeel van de sleuteleigenschap ervan. Zie [Bereikfilters DateKey](reports-api-url.md#datekey-range-filters) voor meer informatie. |

## <a name="api-version-information"></a>API-versiegegevens

U kunt nu versie v1.0 van een Intune-datawarehouse gebruiken door de queryparameter  `api-version=v1.0` in te stellen. Updates voor verzamelingen in het datawarehouse zijn additief van aard en veroorzaken geen problemen voor bestaande scenario's.

U kunt de meest recente functionaliteit van het datawarehouse met behulp van de bètaversie uitproberen. Voor het gebruik van de bètaversie moet uw URL de queryparameter  `api-version=beta` bevatten. De bètaversie biedt functies voordat ze algemeen beschikbaar zijn als een ondersteunde service. Als er nieuwe functies aan Intune worden toegevoegd, kunnen de werking en gegevenscontracten worden gewijzigd. Alle aangepaste code of rapportagemiddelen die afhankelijk zijn van de bètaversie, worden mogelijk onbruikbaar bij nieuwe updates.

## <a name="odata-query-options"></a>OData-queryopties

De huidige versie ondersteunt de volgende OData-queryparameters: `$filter`, `$select`, `$skip,` en `$top`. In `$filter` worden mogelijk alleen `DateKey` of `RowLastModifiedDateTimeUTC` ondersteund wanneer de kolommen van toepassing zijn, en andere eigenschappen zouden een ongeldige aanvraag activeren.

## <a name="datekey-range-filters"></a>Bereikfilters DateKey

`DateKey`-bereikfilters kunnen worden gebruikt voor het beperken van de hoeveelheid te downloaden gegevens voor enkele verzamelingen met `dateKey` als een sleuteleigenschap. Het `DateKey`-filter kan worden gebruikt voor het optimaliseren van serviceprestaties door de volgende `$filter`-queryparameter op te geven:

1. `DateKey` alleen in de `$filter`, waarbij de `lt/le/eq/ge/gt`-operators worden ondersteund en worden gekoppeld aan de logische operator `and`, waar ze kunnen worden toegewezen aan een begindatum en/of einddatum.
2. `maxhistorydays` wordt opgegeven als aangepaste query.<br>

## <a name="filter-examples"></a>Voorbeelden van filters

> [!NOTE]
> Bij de filtervoorbeelden wordt ervan uitgegaan dat het vandaag 21-2-2019 is.

|                             Filter                             |           Prestatieoptimalisatie           |                                          Beschrijving                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Volledig                                      |    Gegevens retourneren met `DateKey` tussen 20180214 en 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Volledig                                      |    Gegevens retourneren met `DateKey` gelijk aan 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Volledig                                      |    Gegevens retourneren met `DateKey` tussen 20180214 en 20180220.                                     |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Volledig                                      |    Gegevens retourneren met `DateKey` gelijk aan 20180214. `maxhistorydays` wordt genegeerd.                            |
|    `$filter=RowLastModifiedDateTimeUTC ge 2018-02-21T23:18:51.3277273Z`                                |    Volledig                                       |    Retourgegevens met `RowLastModifiedDateTimeUTC` zijn groter dan of gelijk aan `2018-02-21T23:18:51.3277273Z`                             |
