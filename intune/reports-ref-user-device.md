---
title: Gebruikersapparaatkoppeling - Intune-datawarehouse
titlesuffix: Microsoft Intune
description: Een lijst met wijzigingen in de API van Intune-datawarehouse.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bd06c4d42de0c4f64ec0c0cfa61d8aa44af7ab95
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
---
# <a name="user-device-association"></a>Gebruikersapparaatkoppeling

De entiteit **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie.


|        Naam        |                                           Description                                            |        Voorbeeld         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Een unieke id van gebruiker in het datawarehouse. (surrogaatsleutel).               |          123           |
|     DeviceKey      |                      Een unieke id van het apparaat in het datawarehouse.                      |          123           |
| CreatedDateTimeUTC |           De datum en tijd wanneer de gebruikersapparaatkoppeling is gemaakt. Hiervoor wordt de UTC-notatie gebruikt.           | 11/23/2016 12:00:00 AM |
|     IsDeleted      | Geeft aan dat de gebruiker het apparaat heeft uitgeschreven en dat de koppeling niet meer actueel is. |       Waar/onwaar       |
|  EndedDateTimeUTC  |              De datum en tijd in UTC waarop IsDeleted is gewijzigd in <strong>Waar</strong>.               | 23-06-2017 12.00.00 |

