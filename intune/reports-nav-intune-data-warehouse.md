---
title: Intune-datawarehouse-API | Microsoft Docs
description: U kunt de API gebruiken om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6bdb7a8d20d86ca800b61c069dcc380f86747a30
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
#  <a name="intune-data-warehouse-api"></a>Intune-datawarehouse-API

Met de Intune-datawarehouse-API krijgt u toegang tot uw Intune-gegevens in een machineleesbare indeling, voor gebruik in uw favoriete analyseprogramma. U kunt de API gebruiken om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden. De API maakt gebruikt van het OData-protocol, dat standaardpatronen volgt voor:

  -   Aanvraag- en reactieheaders
  -   Statuscodes
  -   HTTP-methoden
  -   URL-conventies
  -   Mediatypen
  -   Nettolading-indelingen
  -   Queryopties

De OData (Open Data-protocol) is een OASIS-standaard (Organization for the Advancement of Structured Information Standards) waarmee de aanbevolen procedure voor het maken en gebruiken van RESTful API's wordt gedefinieerd. Het Intune-datawarehouse maakt gebruik van OData versie 4.0.

Deze naslagsectie biedt een overzicht van eindpunten, ondersteunde HTTP-methoden, retournettolading-indelingen en documentatie van het Intune-datawarehouse-gegevensmodel.

> [!Important]  
> U kunt de meest recente functionaliteit van het datawarehouse met behulp van de bètaversie uitproberen. Voor het gebruik van de bètaversie moet uw URL de queryparameter `api-version=beta` bevatten. De bètaversie biedt functies voordat ze algemeen beschikbaar zijn als een ondersteunde service. Als er nieuwe functies aan Intune worden toegevoegd, kunnen de werking en gegevenscontracten worden gewijzigd. Alle aangepaste code of rapportagemiddelen die afhankelijk zijn van de bètaversie, worden mogelijk onbruikbaar bij nieuwe updates. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

## <a name="odata-custom-client"></a>Aangepaste OData-client

U kunt het Intune-datawarehousegegevensmodel openen via RESTful-eindpunten. Om toegang tot uw gegevens te krijgen, moet uw client zich door middel van OAuth 2.0 autoriseren bij Azure Active Directory (Azure AD). U stelt eerst een webtoepassing en een client-app in Azure in en verleent machtigingen aan de client. Uw lokale client wordt geautoriseerd en kan vervolgens communiceren met de datawarehouse-eindpunten.

Zie [Gegevens ophalen uit de datawarehouse-API met een REST-client](reports-proc-data-rest.md) voor meer informatie

> [!Note]  
> Open de [GitHub Intune-datawarehouseopslagplaats](https://github.com/Microsoft/Intune-Data-Warehouse) op GitHub voor codevoorbeelden.

## <a name="interacting-with-the-api"></a>Interactie met de API

De API vereist autorisatie met Azure AD. Azure AD maakt gebruik van OAuth 2.0. Na autorisatie kunt u gegevens ophalen van de API door een HTTP GET-woord te gebruiken en contact te maken met de beschikbaar gemaakte entiteitverzamelingen. Zie voor meer informatie:

 -  [Autorisatie](reports-api-url.md)
 -  [API-URL-structuur](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Intune-datawarehouse-gegevensmodel

OData definieert een abstract gegevensmodel en een protocol waarmee alle clienttoegangsgegevens beschikbaar zijn voor elke willekeurige gegevensbron. Het onderwerp met documentatie over het gegevensmodel bevat een uitleg van de naamruimten, entiteiten en retourobjecten in het Intune-datawarehouse-gegevensmodel. Zie [Datawarehouse-gegevensmodel](reports-ref-data-model.md) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

Lees de [Verificatiescenario's voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios) voor meer informatie over het werken met Azure AD.

Ga naar [odata.org](http://www.odata.org) voor informatie over OData.
  
U kunt versie 4.0 van de OData-standaard lezen op [OData Version 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
