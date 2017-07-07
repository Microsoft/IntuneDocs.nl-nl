---
title: Wissen van door Exchange beheerde mobiele apparaten
description: Met Microsoft Intune kunt u mobiele apparaten wissen of opnieuw instellen die met de Intune Exchange Connector worden beheerd door Exchange ActiveSync (EAS)
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 665f57a4cdb25c1e9f2bef7f1c25f284589df16f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wissen van door Exchange beheerde mobiele apparaten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met Microsoft Intune kunt u mobiele apparaten wissen of opnieuw instellen die met de Intune Exchange Connector worden beheerd door Exchange ActiveSync (EAS). In de volgende tabel staan de mogelijkheden voor wissen via Exchange ActiveSync:

|Type wisbewerking|Windows 8.1 en Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Volledig wissen|Hiermee verwijdert u e-mailaccount en e-mail in de cache.|XFabrieksinstellingen terugzetten.|Fabrieksinstellingen terugzetten.|
|Selectief wissen/e-mail|Hiermee verwijdert u het e-mailaccount.|Niet ondersteund.|Niet ondersteund.|
|Selectief wissen/beleid|Afdwinging van het beleid wordt verwijderd, maar de instellingen worden niet gewijzigd|XAfdwinging van het beleid wordt verwijderd, maar de instellingen worden niet gewijzigd.|Afdwinging van het beleid wordt verwijderd, maar de instellingen worden niet gewijzigd.|
