---
title: Intune-datawarehouse-API-eindpunt | Microsoft Docs
description: Naslagonderwerp waarin de API URL-structuur wordt beschreven.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7723bb42eedcd97142f039ca52b60911fa91838b
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Intune-datawarehouse-API-eindpunt

U kunt de Intune-datawarehouse-API gebruiken met een account met specifiek op rollen gebaseerd toegangsbeheer en Azure AD-referenties. Vervolgens autoriseert u uw REST client met Azure AD met behulp van OAuth 2.0. En ten slotte vormt u een zinvolle URL voor het aanroepen van een datawarehouseresource.

## <a name="azure-ad-and-intune-credential-requirements"></a>Azure AD en Intune-referentievereisten

Verificatie en autorisatie zijn gebaseerd op Azure AD-referenties en Intune RBAC (Role-Based Access Control, op rollen gebaseerd toegangsbeheer). Alle globale beheerders en Intune-servicebeheerders voor uw tenant hebben standaard toegang tot de API. Gebruik Intune-rollen om toegang te bieden voor meer gebruikers door hen toegang tot de **rapportageresource** te verlenen.

Vereisten voor toegang tot de API zijn:

  -  Er moet een Intune-licentie zijn toegewezen aan de gebruiker
  -  Gebruiker moet een van de volgende zijn:
      -  Globale Azure AD-beheerder
      -  Een Intune-servicebeheerder
      -  Gebruiker met op rollen gebaseerde toegang tot de **rapporten**resource

## <a name="authorization"></a>Autorisatie

Azure Active Directory (Azure AD) maakt gebruik van OAuth 2.0 om het mogelijk te maken dat u toegang tot webtoepassingen en web-API's in uw Azure AD-tenant kunt autoriseren. In deze taalonafhankelijke handleiding wordt beschreven hoe u HTTP-berichten verzendt en ontvangt zonder onze open source-bibliotheken te gebruiken. De OAuth 2.0-autorisatiecodestroom wordt beschreven in [sectie 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) van de OAuth 2.0-specificatie.

Zie [Toegang tot webtoepassingen die gebruikmaken van OAuth 2.0 en Azure Active Directory autoriseren](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code) voor meer informatie.

## <a name="api-url-structure"></a>API URL-structuur

De datawarehouse-API-eindpunten lezen de entiteiten voor elke set. De API ondersteunt een **GET** HTTP-woord en een subset queryopties.

Voor de URL voor Intune wordt de volgende notatie gebruikt:  
https://fef.{***locatie***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***entiteitverzameling***}?api-version={***api-versie***}

De URL bevat de volgende elementen:

| Element | Voorbeeld | Beschrijving |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | De basis-URL kan worden gevonden door de blade Datawarehouse-API in Azure Portal te bekijken. |
| entiteitverzameling | dates | De naam van de OData-entiteitverzameling. Zie [Gegevensmodel](reports-ref-data-model.md) voor meer informatie over verzamelingen en entiteiten in het gegevensmodel. |
| api-versie | beta | Version is de versie van de API waartoe toegang moet worden verkregen. Zie [Versie](#API-version-information) voor meer informatie. |


## <a name="api-version-information"></a>API-versiegegevens

De huidige versie van de API is `beta`. 

## <a name="odata-query-options"></a>OData-queryopties

De huidige versie ondersteunt de volgende OData-queryparameters: `$skip, $top, $filter, $orderby`.