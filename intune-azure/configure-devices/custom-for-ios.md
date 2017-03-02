---
title: Aangepaste Intune-instellingen voor iOS-apparaten
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over de instellingen die u kunt gebruiken in een aangepast iOS-profiel.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: d8e6d0d641dd55c79442f68e7e97d21efcdad7fa
ms.lasthandoff: 02/16/2017


---

# <a name="microsoft-intune-custom-settings-for-ios-devices"></a>Aangepaste Microsoft Intune-instellingen voor iOS-apparaten

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik het aangepaste iOS-profiel van Microsoft Intune om instellingen die u met het [hulpprogramma Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt, op iOS-apparaten te implementeren. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen, en deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Intune iOS-profiel en de instellingen toewijzen aan gebruikers en apparaten in uw organisatie.

Op deze manier kunt u iOS-instellingen implementeren die niet met andere Intune-profieltypen kunnen worden geconfigureerd.


1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](how-to-configure-custom-settings.md) om aan de slag te gaan.
2. Geef de volgende informatie op de blade **Profiel maken** op:

- **Aangepaste configuratieprofielnaam**: geef een naam op voor het beleid, zoals het moet worden weergegeven op het apparaat en in de Intune-status.
- **Configuratieprofielbestand**: blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator.
Controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert compatibel zijn met de versie van iOS op de apparaten, waarop u het aangepaste iOS-beleid implementeert. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).

Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud** van de blade.

