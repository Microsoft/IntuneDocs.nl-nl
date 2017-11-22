---
title: Wijzigingenlogboek Intune-datawarehouse | Microsoft Docs
description: Een lijst met wijzigingen in de API van Intune-datawarehouse.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d675a36cd5ea4c11d755174bf2b0bbc5d4b18ec
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/08/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Wijzigingenlogboek voor de API van Intune-datawarehouse

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Houd updates voor Intune-datawarehouse bij.

## <a name="1710"></a>1710
_Uitgebracht: november 2017_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>De gebruikersentiteit bevat de meest recente gebruikersgegevens in het datawarehouse-gegevensmodel <!-- 1544273 -->

De eerste versie van het gegevensmodel Intune-datawarehouse bevat alleen recente, historische Intune-gegevens. Rapportopstellers kunnen de huidige status van een gebruiker niet vastleggen. In deze update wordt [ **Gebruikersentiteit** ](reports-ref-user.md) ingevuld met de meest recente gebruikersgegevens.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nieuwe entiteiten in het datawarehouse-gegevensmodel <!-- 1479526 --><!-- -->

 - De entiteit [ **UserDeviceAssociation**](reports-ref-user-device.md) is toegevoegd. **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie.
 - De entiteit [ **IntuneManagementExtension**](reports-ref-intunemanagementextension.md) is toegevoegd. **IntuneManagementExtension** bevat entiteiten voor mobiele apparaten die informatie bijhouden, zoals de versie en de status van de installatie.

## <a name="next-steps"></a>Volgende stappen
 - Ontdek [wat er elke week nieuw is in Intune](whats-new.md). U vindt hier ook informatie over toekomstige wijzigingen, belangrijke kennisgevingen betreffende de service en informatie over oudere releases. 
 - Lees het [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882).