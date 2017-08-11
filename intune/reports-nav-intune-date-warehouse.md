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
ms.openlocfilehash: 5f03fd3a1557ef5d013fe695016ed0e3b119ee62
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2017
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

<!-- ## OData custom client

You can access the Intune Data Warehouse data model through RESTful endpoints. To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0. You first set up a web app and a client app in Azure, grant permissions to the client. Your local client will get authorization, can then communicate with the Data Warehouse endpoints.

For more information, see [Get data from the Data Warehouse API with a REST client](Get-data-REST.md) -->

## <a name="interacting-with-the-api"></a>Interactie met de API

De API vereist autorisatie met Azure AD. Azure AD maakt gebruik van OAuth 2.0. Na autorisatie kunt u gegevens ophalen van de API door een HTTP GET-woord te gebruiken en contact te maken met de beschikbaar gemaakte entiteitverzamelingen. Zie voor meer informatie:

 -  [Autorisatie](reports-api-url.md)
 -  [API-URL-structuur](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Intune-datawarehouse-gegevensmodel

OData definieert een abstract gegevensmodel en een protocol waarmee alle clienttoegangsgegevens beschikbaar zijn voor elke willekeurige gegevensbron. Het onderwerp met documentatie over het gegevensmodel bevat een uitleg van de naamruimten, entiteiten en retourobjecten in het Intune-datawarehouse-gegevensmodel. Zie [Datawarehouse-gegevensmodel](reports-ref-data-model.md) voor meer informatie.

## <a name="for-more-information"></a>Voor meer informatie

[Verificatiescenario's voor Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)  
[odata.org](http://www.odata.org)  
[OData versie 4.0](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
