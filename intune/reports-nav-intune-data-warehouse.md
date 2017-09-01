---
title: Intune-datawarehouse-API | Microsoft Docs
description: U kunt de API gebruiken om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 52b498beb024b86282c93be7aa5a248800db6609
ms.sourcegitcommit: 294de4d4058de2c625abb8143e90880d27da9284
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/15/2017
---
#  <a name="intune-data-warehouse-api"></a>Intune-datawarehouse-API

U krijgt met de Intune-datawarehouse-API toegang tot uw Intune-gegevens in een machineleesbare indeling voor gebruik in uw favoriete analyseprogramma. U kunt de API gebruiken om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden. De API maakt gebruikt van het OData-protocol, dat standaardpatronen volgt voor:

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

U kunt het Intune-datawarehousegegevensmodel openen via RESTful-eindpunten. Om toegang tot uw gegevens te krijgen, moet uw client zich door middel van OAuth 2.0 autoriseren met Microsoft Azure Active Directory (Azure AD). U stelt eerst een webtoepassing en een client-app in Azure in en verleent machtigingen aan de client. Uw lokale client ontvangt autorisatie en kan vervolgens communiceren met de datawarehouse-eindpunten.

Zie [Gegevens ophalen uit de datawarehouse-API met een REST-client](reports-proc-data-rest.md) voor meer informatie

## <a name="interacting-with-the-api"></a>Interactie met de API

De API vereist autorisatie met Azure AD. Azure AD maakt gebruik van OAuth 2.0. Na autorisatie kunt u gegevens ophalen van de API door een HTTP GET-woord te gebruiken en contact te maken met de beschikbaar gemaakte entiteitverzamelingen. Zie voor meer informatie:

 -  [Autorisatie](reports-api-url.md)
 -  [API-URL-structuur](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Intune-datawarehouse-gegevensmodel

OData definieert een abstract gegevensmodel en een protocol waarmee alle clienttoegangsgegevens beschikbaar zijn voor elke willekeurige gegevensbron. Het onderwerp met documentatie over het gegevensmodel bevat een uitleg van de naamruimten, entiteiten en retourobjecten in het Intune-datawarehouse-gegevensmodel. Zie [Datawarehouse-gegevensmodel](reports-ref-data-model.md) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

[Verificatiescenario's voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)  
[odata.org](http://www.odata.org)  
[OData versie 4.0](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
