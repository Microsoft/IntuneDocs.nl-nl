---
title: IntuneManagementExtension-entiteit
titlesuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie IntuneManagementExtension van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 48e08b93468fb177fd3a724e5bcc6758cf262e99
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189364"
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


|      Eigenschap       |                         Beschrijving                         | Voorbeeld |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               De unieke id van de datum.                |   123   |
|      TenantKey      |              De unieke id van de tenant.               |   456   |
|      DeviceKey      |              Unieke id van het apparaat.               |   789   |
| ExtensionVersionKey | De unieke id van de IntuneManagementExtension-versie. |    1    |
|  ExtensionStateKey  |             Unieke id van de status.              |    2    |

