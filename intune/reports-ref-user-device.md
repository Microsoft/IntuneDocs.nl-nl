---
title: Gebruikersapparaatkoppeling - Intune-datawarehouse
titlesuffix: Microsoft Intune
description: De entiteit UserDeviceAssociation bevat gebruikersapparaatkoppelingen in uw organisatie.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: bff8e67a3c6df4364491ba1407aeaee43ff976c4
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236616"
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
