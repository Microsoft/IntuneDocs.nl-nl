---
title: Upgraden naar Windows Holographic for Business
titleSuffix: Microsoft Intune
description: Lees hoe u apparaten met Windows Holographic kunt upgraden naar Windows Holographic for Business
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6342ed23f67c37c2f5084e58594294d826a28e40
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506710"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Apparaten met Windows Holographic upgraden naar Windows Holographic for Business

Microsoft Intune bevat veel instellingen waarmee u uw apparaten kunt beheren en beveiligen. In dit artikel worden de instellingen beschreven waarmee u Windows Holographic-apparaten kunt upgraden naar Windows Holographic for Business. Deze instellingen worden gedefinieerd in een upgradeconfiguratieprofiel in Intune dat wordt gepusht naar of geïmplementeerd op apparaten.

Gebruik deze instellingen voor het upgraden van uw Windows Holographic-apparaten als onderdeel van uw MDM-oplossing (Mobile Device Management). Voor Microsoft HoloLens kunt u de Commercial Suite aanschaffen om de vereiste licentie voor de upgrade op te halen. Zie [Windows Holographic for Business-functies ontgrendelen](https://docs.microsoft.com/hololens/hololens1-upgrade-enterprise) voor meer informatie.

Zie [Upgrade Windows 10 editions or enable S mode](../edition-upgrade-configure-windows-10.md) (Windows 10-edities upgraden of S-modus inschakelen) voor meer informatie over deze functie.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Editie-upgrade

- **Editie bijwerken naar**: selecteer bij **Windows 10 Holographic for Business**.
- **Licentiebestand**: blader naar het XML-licentiebestand dat voor u is opgegeven en selecteer dit bestand.

  ![Voer de naam van het XML-bestand in dat de gegevens over de licentie voor Holographic for Business bevat](./media/holographic-upgrade/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt mogelijk nog niets. Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](../device-profile-monitor.md).

U kunt ook editie-upgradeprofielen maken voor apparaten met [Windows 10 en hoger](edition-upgrade-windows-settings.md).
