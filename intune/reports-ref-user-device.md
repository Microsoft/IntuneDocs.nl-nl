---
title: Gebruikersapparaatkoppeling - Intune-datawarehouse | Microsoft Docs
description: Een lijst met wijzigingen in de API van Intune-datawarehouse.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095395be4c86780ad65ba1e24b856f6eef8d41ae
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
# <a name="user-device-association"></a>Gebruikersapparaatkoppeling

De entiteit **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie.

| Naam               | Description                                                                                      | Voorbeeld                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Een unieke id van gebruiker in het datawarehouse. (surrogaatsleutel).                              | 123                    |
| DeviceKey          | Een unieke id van het apparaat in het datawarehouse.                                            | 123                    |
| CreatedDateTimeUTC | De datum en tijd wanneer de gebruikersapparaatkoppeling is gemaakt. Hiervoor wordt de UTC-notatie gebruikt.                                | 11/23/2016 12:00:00 AM |
| IsDeleted          | Geeft aan dat de gebruiker het apparaat heeft uitgeschreven en dat de koppeling niet meer actueel is. | Waar/onwaar             |
| EndedDateTimeUTC   | De datum en tijd in UTC waarop IsDeleted is gewijzigd in **Waar**.                                              | 23-06-2017 12.00.00 |
