---
title: Speciale overwegingen bij migratie
description: "In dit artikel worden klanten geïnformeerd over de speciale overwegingen bij migraties die ze moeten maken voordat ze aan een migratiecampagne beginnen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Speciale overwegingen bij migratie

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Er zijn speciale overwegingen bij migraties die mogelijk van toepassing zijn, afhankelijk van uw bestaande MDM-provideromgeving.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Fabrieksinstellingen terugzetten voor het Device Enrollment Program (DEP) van Apple

Met het Device Enrollment Program (DEP) van Apple worden apparaatconfiguraties ingesteld die niet door de eindgebruiker kunnen worden verwijderd. Als u de geavanceerde beheerfuncties van DEP wilt behouden, moet het apparaat in de oorspronkelijke staat worden hersteld via het terugzetten van de fabrieksinstellingen zodat het apparaat bij Intune kan worden ingeschreven.

Als u met DEP de apparaten in Intune wilt blijven beheren, moet u [de inschrijving van iOS-apparaten met het Device Enrollment Program instellen](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>Volgende stappen 

[Fase 2: migratiecampagne](migration-guide-campaign.md)
