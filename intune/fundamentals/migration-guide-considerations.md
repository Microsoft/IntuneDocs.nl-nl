---
title: Speciale overwegingen bij migratie
titleSuffix: Microsoft Intune
description: Dit artikel bevat speciale migratieoverwegingen voordat u een Microsoft Intune-migratiecampagne start.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 45e2985bcf01d635e964ee8785938c0d5df4e4af
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727607"
---
# <a name="special-migration-considerations"></a>Speciale overwegingen bij migratie

Er zijn mogelijk speciale overwegingen bij migraties van toepassing, afhankelijk van uw bestaande MDM-provideromgeving.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Wissen voor het Device Enrollment Program (DEP) van Apple

Met het Device Enrollment Program (DEP) van Apple worden apparaatconfiguraties ingesteld die niet door de eindgebruiker kunnen worden verwijderd. Als u de geavanceerde beheerfuncties van DEP wilt behouden, moet het apparaat in de oorspronkelijke staat worden hersteld door dit te wissen, zodat het apparaat bij Intune kan worden ingeschreven.

Als u met DEP de apparaten in Intune wilt blijven beheren, moet u [de inschrijving van iOS-apparaten met het Device Enrollment Program instellen](../enrollment/device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Volgende stappen

[Fase 2: migratiecampagne](../migration-guide-campaign.md)
