---
title: Apparaten beheren met Intune
titlesuffix: Azure portal
description: Meer informatie over het weergeven van apparaten die u met Intune beheert en de verschillende bewerkingen die u op deze apparaten kunt uitvoeren.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca40eee8a53fa3e8b2610ce414f0037180d4beaf
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Wat is Microsoft Intune-apparaatbeheer?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De workload **Apparaten** biedt inzicht in de apparaten die u beheert en geeft u de mogelijkheid om taken op afstand voor deze apparaten uit te voeren. Toegang krijgen tot de workload:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. U kunt informatie over apparaten weergeven en de vermelde acties voor externe apparaten uitvoeren.

## <a name="available-device-actions"></a>Beschikbare apparaatbedreigingen
De beschikbaarheid van de acties is afhankelijk van het apparaatplatform en de configuratie van het apparaat.

- [Inventaris van apparaten weergeven](device-inventory.md)
- Externe apparaatacties uitvoeren:
    - [Bedrijfsgegevens verwijderen](devices-wipe.md#remove-company-data)
    - [Fabrieksinstellingen terugzetten](devices-wipe.md#factory-reset)
    - [Vergrendelen op afstand](device-remote-lock.md)
    - [Wachtwoordcode opnieuw instellen](device-passcode-reset.md)
    - [Activeringsvergrendeling overslaan](device-activation-lock-bypass.md) (alleen iOS)
    - [Nieuwe start](device-fresh-start.md) (alleen Windows)
    - [Modus Apparaat verloren](device-lost-mode.md) (alleen iOS)
    - [Apparaat zoeken](device-locate.md) (alleen iOS)
    - [Opnieuw starten](device-restart.md) (alleen Windows)
    - [Windows 10-pincode opnieuw instellen](device-windows-pin-reset.md)
    - [Beheer op afstand voor Android](device-profile-android-teamviewer.md)
    - [Apparaat synchroniseren](device-sync.md)


## <a name="next-steps"></a>Volgende stappen

- Kies **Apparaatacties** om de status te zien van acties die zijn uitgevoerd op apparaten die u beheert.
![Apparaatbedreigingen bewaken](./media/monitor-device-actions.png)
