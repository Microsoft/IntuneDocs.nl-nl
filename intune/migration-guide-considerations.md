---
title: Speciale overwegingen bij migratie
titlesuffix: Microsoft Intune
description: Dit artikel bevat speciale migratieoverwegingen voordat u een Microsoft Intune-migratiecampagne start.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.openlocfilehash: 039b3dc4d45b340a7d7f8ed0314661a2505a779b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179813"
---
# <a name="special-migration-considerations"></a>Speciale overwegingen bij migratie

Er zijn mogelijk speciale overwegingen bij migraties van toepassing, afhankelijk van uw bestaande MDM-provideromgeving.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Wissen voor het Device Enrollment Program (DEP) van Apple

Met het Device Enrollment Program (DEP) van Apple worden apparaatconfiguraties ingesteld die niet door de eindgebruiker kunnen worden verwijderd. Als u de geavanceerde beheerfuncties van DEP wilt behouden, moet het apparaat in de oorspronkelijke staat worden hersteld door dit te wissen, zodat het apparaat bij Intune kan worden ingeschreven.

Als u met DEP de apparaten in Intune wilt blijven beheren, moet u [de inschrijving van iOS-apparaten met het Device Enrollment Program instellen](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Volgende stappen

[Fase 2: Migratiecampagne](migration-guide-campaign.md)
