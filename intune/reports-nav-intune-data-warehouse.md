---
title: Intune-datawarehouse-API
titlesuffix: Microsoft Intune
description: U kunt de Intune-datawarehouse-API gebruiken om rapporten te genereren die inzicht in de mobiele omgeving van uw bedrijf bieden.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2d9dda7381aa7d3033dec0618843522339335c0b
ms.sourcegitcommit: bea4a81d262607c6e9dd1e26f5cd1a2faf7d051b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2018
ms.locfileid: "45602092"
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
  
Controleer de OData-versie 4.0 standaard op [OData-versie 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
