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
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 15a3130263e19f8d6bef55427bf9a53f8e8b42ef
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508375"
---
# <a name="special-migration-considerations"></a>Speciale overwegingen bij migratie

Er zijn mogelijk speciale overwegingen bij migraties van toepassing, afhankelijk van uw bestaande MDM-provideromgeving.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Wissen voor het Device Enrollment Program (DEP) van Apple

Met het Device Enrollment Program (DEP) van Apple worden apparaatconfiguraties ingesteld die niet door de eindgebruiker kunnen worden verwijderd. Als u de geavanceerde beheerfuncties van DEP wilt behouden, moet het apparaat in de oorspronkelijke staat worden hersteld door dit te wissen, zodat het apparaat bij Intune kan worden ingeschreven.

Als u met DEP de apparaten in Intune wilt blijven beheren, moet u [de inschrijving van iOS-apparaten met het Device Enrollment Program instellen](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Volgende stappen

[Fase 2: migratiecampagne](migration-guide-campaign.md)
