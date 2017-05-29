---
title: Aangepaste Intune-instellingen voor iOS-apparaten
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over de instellingen die u kunt gebruiken in een aangepast iOS-profiel.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3d1ccae3c36e13b4074c442b48943077041a8b52
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>Aangepaste Microsoft Intune-instellingen voor iOS-apparaten

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Gebruik het aangepaste iOS-profiel van Microsoft Intune om instellingen die u met het [hulpprogramma Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt toe te wijzen aan iOS-apparaten. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen, en deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Intune iOS-profiel en de instellingen toewijzen aan gebruikers en apparaten in uw organisatie.

Op deze manier kunt u iOS-instellingen toewijzen die u niet kunt configureren met andere Intune-profieltypen.


1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. Geef de volgende informatie op de blade **Profiel maken** op:

- **Aangepaste configuratieprofielnaam**: geef een naam op voor het beleid, zoals het moet worden weergegeven op het apparaat en in de Intune-status.
- **Configuratieprofielbestand**: blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator.
Controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert compatibel zijn met de iOS-versie op de apparaten waaraan u het aangepaste iOS-beleid toewijst. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).

Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud** van de blade.

