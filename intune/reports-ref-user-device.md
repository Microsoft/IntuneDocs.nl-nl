---
title: Gebruikersapparaatkoppeling - Intune-datawarehouse
titleSuffix: Microsoft Intune
description: De entiteit UserDeviceAssociation bevat gebruikersapparaatkoppelingen in uw organisatie.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 466066faf03cbdf560697a04310eac844d4f1b87
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798257"
---
# <a name="reference-for-user-device-association-entity"></a>Naslaginformatie voor entiteit gebruikersapparaatkoppelingen

De entiteit **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie.

## <a name="userdeviceassociation"></a>UserDeviceAssociation


|        Naam        |                                           Beschrijving                                            |        Voorbeeld         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Een unieke id van gebruiker in het datawarehouse. (surrogaatsleutel).               |          123           |
|     DeviceKey      |                      Een unieke id van het apparaat in het datawarehouse.                      |          123           |
| CreatedDateTimeUTC |           De datum en tijd wanneer de gebruikersapparaatkoppeling is gemaakt. Hiervoor wordt de UTC-notatie gebruikt.           | 11/23/2016 12:00:00 AM |
|     IsDeleted      | Geeft aan dat de gebruiker het apparaat heeft uitgeschreven en dat de koppeling niet meer actueel is. |       Waar/onwaar       |
|  EndedDateTimeUTC  |              De datum en tijd in UTC waarop IsDeleted is gewijzigd in <strong>Waar</strong>.               | 23-06-2017 12.00.00 |

## <a name="next-steps"></a>Volgende stappen

- Meer informatie over het [Intune-datawarehouse](reports-nav-create-intune-reports.md).
