---
title: IntuneManagementExtension-entiteit
titleSuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie IntuneManagementExtension van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ebece46bac8ebee5cb3c6a573f0b09c4b308abe3
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040991"
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
| ExtensionState |De status van een IntuneManagementExtension. | In orde |

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

