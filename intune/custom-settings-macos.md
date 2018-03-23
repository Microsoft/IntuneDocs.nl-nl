---
title: Aangepaste Microsoft Intune-instellingen voor apparaten met macOS
titleSuffix: ''
description: Meer informatie over de instellingen die u in Microsoft Intune kunt gebruiken in een aangepast macOS-profiel.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e8dc2042d7f88cf626d7420d4760255e1e9a3469
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-macos"></a>Aangepaste Microsoft Intune-apparaatinstellingen voor apparaten met macOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik het aangepaste macOS-profiel van Microsoft Intune om instellingen die u met het hulpprogramma [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt, toe te wijzen aan macOS-apparaten. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen, en deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Intune macOS-profiel en de instellingen toewijzen aan gebruikers en apparaten in uw organisatie.

Op deze manier kunt u macOS-instellingen toewijzen die u niet kunt configureren met andere Intune-profieltypen.


1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. In het deelvenster **Aangepast configuratieprofiel** kunt u elk van de volgende instellingen configureren:

- **Aangepaste configuratieprofielnaam**: geef een naam op voor het beleid, zoals het wordt weergegeven op het apparaat en in de Intune-status.
- **Configuratieprofielbestand**: blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator.
Controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert compatibel zijn met de macOS-versie op de apparaten waarop u het aangepaste macOS-beleid toewijst. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).

Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud** van het deelvenster.
