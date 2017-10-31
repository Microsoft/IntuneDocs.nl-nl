---
title: Gebruikersapparaatkoppelingen | Microsoft Docs
description: Naslagonderwerp voor de categorie Gebruikersapparaatkoppelingen van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Naslaginformatie voor entiteit gebruikersapparaatkoppelingen

De categorie **Gebruikersapparaatkoppelingen** bevat de entiteit **Gebruikersapparaatkoppelingen** die wordt gebruikt voor het definiëren van apparaatkoppelingen binnen de organisatie.

**Gebruikersapparaatkoppelingen**

De entiteit **Gebruikersapparaatkoppelingen** vertegenwoordigt de gedefinieerde apparaatkoppelingen binnen de organisatie.

| Naam               | Beschrijving                                                                                      | Voorbeeld                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | De unieke id van de gebruiker in het datawarehouse - surrogaatsleutel.                             | 123                    |
| DeviceKey          | Een unieke id van het apparaat in het datawarehouse.                                           | 123                    |
| CreatedDateTimeUTC | De datum en tijd in UTC wanneer de gebruikersapparaatkoppeling is gemaakt.                               | 11/23/2016 12:00:00 AM |
| IsDeleted          | Geeft aan dat de gebruiker het apparaat heeft uitgeschreven en dat de koppeling niet meer actueel is. | True                   |
| EndedDateTimeUTC   | De datum en tijd in UTC waarop IsDeleted is gewijzigd in **Waar**.                                         | 23-06-2017 12.00.00 |