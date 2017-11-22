---
title: De entiteit IntuneManagementExtension | Microsoft Docs
description: Naslagonderwerp voor de categorie IntuneManagementExtension van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 30908e4dbb55e16db0e253330175f65fb127d523
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/08/2017
---
# <a name="reference-for-intune-management-extension"></a>Naslag voor Intune-beheeruitbreiding

De categorie **IntuneManagementExtension** bevat entiteiten voor mobiele apparaten waarmee gegevens worden bijgehouden, zoals:

  -  Versies van een IntuneManagementExtension
  -  Installatiestatus van een IntuneManagementExtension

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

De entiteit **IntuneManagementExtensionVersion** bevat een lijst van alle versies die worden gebruikt door IntuneManagementExtension.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| ExtensionVersionKey |De unieke id van de IntuneManagementExtension-versie. | 1 |
| ExtensionVersion |Het versienummer, bestaande uit vier cijfers. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

De **IntuneManagementExtensionHealthState** bevat een lijst van alle mogelijke statussen van de IntuneManagementExtension.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| ExtensionStateKey |Unieke id van de status. | 2 |
| ExtensionState |De status van een IntuneManagementExtension. | Goed |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

De **IntuneManagementExtension** bevat een lijst dagelijkse IntuneManagementExtension-statussen op elk apparaat met Windows 10.
De gegevens voor de afgelopen 60 dagen worden bewaard. 

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| DateKey |De unieke id van de datum. | 123 |
| TenantKey |De unieke id van de tenant. | 456 |
| DeviceKey |Unieke id van het apparaat. | 789 |
| ExtensionVersionKey |De unieke id van de IntuneManagementExtension-versie. | 1 |
| ExtensionStateKey|Unieke id van de status. | 2 |