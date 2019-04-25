---
title: Opslag en verwerking van gegevens in Intune
description: Informatie over de opslag en verwerking van persoonlijke gegevens in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: edb07842-6a16-482e-8c1d-541a29e169a8
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3b499f3171910f28a2d190d28e8ab6e945fa463a
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511265"
---
# <a name="data-storage-and-processing-in-intune"></a>Opslag en verwerking van gegevens in Intune

Nadat Intune [de gegevens heeft verzameld](privacy-data-collect.md), verloopt de opslag en verwerking van die gegevens zoals hieronder wordt beschreven.

## <a name="storing-personal-data"></a>Persoonlijke gegevens opslaan

Alle niet-telemetrische gegevens die zijn verzameld, worden verwerkt via de Intune-service en opgeslagen op een of meer van de volgende locaties: 

- SQLAzure 
- Betrouwbare verzamelingen (Service Fabric)  
- Azure Storage 

Telemetrische gegevens (servicelogboeken, prestatielogboeken, fouten enzovoort) die essentieel zijn voor de bewaking en het bieden van een stabiele service, worden verzonden naar de gegevensopslag van telemetrie van Microsoft.

### <a name="storage-locations"></a>Opslaglocaties

Microsoft biedt in veel regio's wereldwijd Intune-services aan. Intune respecteert de opslaglocaties die zijn gekozen door de beheerder voor klantgegevens.

Zie [Microsoft Intune Waar zijn mijn klantgegevens?](For more information, see Microsoft Intune Where is my customer data?) voor meer informatie.

### <a name="personal-data-retention"></a>Persoonlijke gegevens bewaren

Over het algemeen worden persoonlijke gegevens door Intune bewaard tot dertig dagen nadat de gebruiker is verwijderd uit Intune-beheer.

Telemetrische gegevens die zijn verzameld als onderdeel van het gebruik van Intune, worden maximaal 30 dagen bewaard.

Auditlogboeken worden maximaal één jaar bewaard.

## <a name="processing-personal-data"></a>Persoonlijke gegevens verwerken

Intune verwerkt persoonlijke gegevens conform ISO-gecertificeerde systemen. Zie [Service Trust Portal](https://www.microsoft.com/en-us/TrustCenter/stp) voor meer informatie.

### <a name="profiling-and-marketing"></a>Profilering en marketing

Microsoft Intune gebruikt geen persoonlijke gegevens die zijn verzameld als onderdeel van de service voor profilerings- of marketingdoeleinden. 

### <a name="restrict-processing-of-personal-data"></a>Verwerking van persoonlijke gegevens beperken

Als u de verwerking van persoonlijke gegevens van een gebruiker wilt beperken, kunt u het gebruikersaccount verwijderen door:
1. Een elektronisch exemplaar van de persoonlijke gegevens van de gebruiker te verwijderen, met inbegrip van
    - accounts
    - servicegegevens
    - gekoppelde logboeken
2. Het account van de gebruiker en de bijbehorende gegevens te verwijderen uit Intune.

## <a name="next-steps"></a>Volgende stappen

Meer informatie over hoe Intune persoonlijke gegevens [beveiligt en deelt](privacy-data-secure-share.md). 
