---
title: Wissen van door Exchange beheerde mobiele apparaten
description: Met Microsoft Intune kunt u mobiele apparaten wissen of opnieuw instellen die met de Intune Exchange Connector worden beheerd door Exchange ActiveSync (EAS)
keywords: ''
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 753e5e9dac7199dff18d110808524f05aa669036
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wissen van door Exchange beheerde mobiele apparaten

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Met Microsoft Intune kunt u mobiele apparaten wissen of opnieuw instellen die met de Intune Exchange Connector worden beheerd door Exchange ActiveSync (EAS). In de volgende tabel staan de mogelijkheden voor wissen via Exchange ActiveSync:


|      Type wisbewerking       |              Windows 8.1 en Windows RT 8.1              |                            iOS                             |                          Android                          |
|-------------------------|----------------------------------------------------------|------------------------------------------------------------|-----------------------------------------------------------|
|        Volledig wissen        |          Hiermee verwijdert u e-mailaccount en e-mail in de cache.           |                      XFabrieksinstellingen terugzetten.                       |                      Fabrieksinstellingen terugzetten.                       |
|  Selectief wissen/e-mail   |                  Hiermee verwijdert u het e-mailaccount.                  |                       Niet ondersteund.                       |                      Niet ondersteund.                       |
| Selectief wissen/beleid | Afdwinging van het beleid wordt verwijderd, maar de instellingen worden niet gewijzigd | XAfdwinging van het beleid wordt verwijderd, maar de instellingen worden niet gewijzigd. | Afdwinging van het beleid wordt verwijderd, maar de instellingen worden niet gewijzigd. |

