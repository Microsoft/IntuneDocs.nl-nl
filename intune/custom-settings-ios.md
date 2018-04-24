---
title: Aangepaste Microsoft Intune-instellingen voor apparaten met iOS
titleSuffix: ''
description: Meer informatie over de instellingen die u in Microsoft Intune kunt gebruiken in een aangepast iOS-profiel.
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
ms.openlocfilehash: ada36b11489adbbcaf67db9192c7dd66caadb525
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-ios"></a>Aangepaste Microsoft Intune-apparaatinstellingen voor apparaten met iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Gebruik het aangepaste iOS-profiel van Microsoft Intune om instellingen die u met het [hulpprogramma Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt toe te wijzen aan iOS-apparaten. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen, en deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Intune iOS-profiel en de instellingen toewijzen aan gebruikers en apparaten in uw organisatie.

Op deze manier kunt u iOS-instellingen toewijzen die u niet kunt configureren met andere Intune-profieltypen.


1. Volg de instructies in [Aangepaste apparaatinstellingen configureren in Microsoft Intune](custom-settings-configure.md) om aan de slag te gaan.
2. In het deelvenster **Aangepast configuratieprofiel** kunt u elk van de volgende instellingen configureren:

- **Aangepaste configuratieprofielnaam**: geef een naam op voor het beleid, zoals het wordt weergegeven op het apparaat en in de Intune-status.
- **Configuratieprofielbestand**: blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator.
Controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert compatibel zijn met de iOS-versie op de apparaten waaraan u het aangepaste iOS-beleid toewijst. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).

Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud** van het deelvenster.
