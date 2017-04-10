---
title: Speciale overwegingen bij migraties | Microsoft Docs
description: "In dit artikel worden klanten geïnformeerd over de speciale overwegingen bij migraties die ze moeten maken voordat ze aan een migratiecampagne beginnen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 634e84312fa1a93eb85bf70e1593ca11359b72ff
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-special-migration-considerations"></a>Fase 1: speciale overwegingen bij migraties

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Er zijn speciale overwegingen bij migraties die mogelijk van toepassing zijn, afhankelijk van uw bestaande MDM-provideromgeving.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Fabrieksinstellingen terugzetten voor het Device Enrollment Program (DEP) van Apple

Met het Device Enrollment Program (DEP) van Apple worden apparaatconfiguraties ingesteld die niet door de eindgebruiker kunnen worden verwijderd. Als u de geavanceerde beheerfuncties van DEP wilt behouden, moet het apparaat in de oorspronkelijke staat worden hersteld via het terugzetten van de fabrieksinstellingen zodat het apparaat bij Intune kan worden ingeschreven.

Als u met DEP de apparaten in Intune wilt blijven beheren, doet u het volgende:

1.  Integreer [DEP in Intune](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune).

2.  Ga naar uw Apple DEP-account en [wijs de serienummers van de DEP-apparaten opnieuw toe](https://help.apple.com/deployment/business/#/tesf9562af26), van uw bestaande MDM-provider naar Intune.

3.  [Synchroniseer](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) uw DEP-account met Intune.

4.  Vervolgens moet u de betreffende DEP-inschrijvingsprofielen [maken en toewijzen](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) aan de serienummers in Intune.

5.  Zet de fabrieksinstellingen terug op de apparaten (op afstand via uw huidige MDM-provider of handmatig op elk apparaat).

6.  Verdeel de apparaten over de eindgebruikers.

## <a name="next-steps"></a>Volgende stappen 

[Fase 2: migratiecampagne](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

