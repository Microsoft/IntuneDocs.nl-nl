---
title: Gebruikersapparaatkoppeling - Intune-datawarehouse
titleSuffix: Microsoft Intune
description: De entiteit UserDeviceAssociation bevat gebruikersapparaatkoppelingen in uw organisatie.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/10/2019
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
ms.openlocfilehash: 9ae5ee7a33ca069853201c553e461d9e36c9bbdb
ms.sourcegitcommit: af2512a1342d8037a96a61c8cc2c63e107913733
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 04/12/2019
ms.locfileid: "59533509"
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
