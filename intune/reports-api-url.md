---
title: Intune-datawarehouse-API-eindpunt
titlesuffix: Microsoft Intune
description: Naslagonderwerp waarin de Intune-datawarehouse-API-URL-structuur wordt beschreven.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2b25140cb5c3c8c70ff42186352362c57dcf6ee7
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune-datawarehouse-API-eindpunt

U kunt de Intune-datawarehouse-API gebruiken met een account met specifiek op rollen gebaseerd toegangsbeheer en Azure AD-referenties. Vervolgens autoriseert u uw REST client met Azure AD met behulp van OAuth 2.0. En ten slotte vormt u een zinvolle URL voor het aanroepen van een datawarehouseresource.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autorisatie

Azure Active Directory (Azure AD) maakt gebruik van OAuth 2.0 om het mogelijk te maken dat u toegang tot webtoepassingen en web-API's in uw Azure AD-tenant kunt autoriseren. In deze taalonafhankelijke handleiding wordt beschreven hoe u HTTP-berichten verzendt en ontvangt zonder onze open source-bibliotheken te gebruiken. De OAuth 2.0-autorisatiecodestroom wordt beschreven in [sectie 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) van de OAuth 2.0-specificatie.

Zie [Toegang tot webtoepassingen die gebruikmaken van OAuth 2.0 en Azure Active Directory autoriseren](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code) voor meer informatie.

## <a name="api-url-structure"></a>API URL-structuur

De datawarehouse-API-eindpunten lezen de entiteiten voor elke set. De API ondersteunt een **GET** HTTP-woord en een subset queryopties.

Voor de URL voor Intune wordt de volgende notatie gebruikt:  
https://fef.{<strong><em>locatie</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}

De URL bevat de volgende elementen:

| Element | Voorbeeld | Description |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | De basis-URL kan worden gevonden door de blade Datawarehouse-API in Azure Portal te bekijken. |
| entiteitverzameling | dates | De naam van de OData-entiteitverzameling. Zie [Gegevensmodel](reports-ref-data-model.md) voor meer informatie over verzamelingen en entiteiten in het gegevensmodel. |
| api-versie | beta | Version is de versie van de API waartoe toegang moet worden verkregen. Zie [Versie](#API-version-information) voor meer informatie. |


## <a name="api-version-information"></a>API-versiegegevens

De huidige versie van de API is `beta`. 

## <a name="odata-query-options"></a>OData-queryopties

De huidige versie ondersteunt de volgende OData-queryparameters: `$filter, $orderby, $select, $skip,` en `$top`.