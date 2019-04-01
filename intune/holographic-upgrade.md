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
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1c6a2f4fc3e3cae171cea96520d075a659d4d1ca
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566332"
---
# <a name="upgrade-devices-running-windows-holographic-to-windows-holographic-for-business"></a>Apparaten met Windows Holographic upgraden naar Windows Holographic for Business

Microsoft Intune bevat veel instellingen waarmee u uw apparaten kunt beheren en beveiligen. In dit artikel worden de instellingen beschreven waarmee u Windows Holographic-apparaten kunt upgraden naar Windows Holographic for Business. Deze instellingen worden gedefinieerd in een upgradeconfiguratieprofiel in Intune dat wordt gepusht naar of geïmplementeerd op apparaten.

Gebruik deze instellingen voor het upgraden van uw Windows Holographic-apparaten als onderdeel van uw MDM-oplossing (Mobile Device Management). Voor Microsoft HoloLens kunt u de Commercial Suite aanschaffen om de vereiste licentie voor de upgrade op te halen. Zie [Windows Holographic for Business-functies ontgrendelen](https://docs.microsoft.com/hololens/hololens-upgrade-enterprise) voor meer informatie.

Zie [Upgrade Windows 10 editions or enable S mode](edition-upgrade-configure-windows-10.md) (Windows 10-edities upgraden of S-modus inschakelen) voor meer informatie over deze functie.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](edition-upgrade-configure-windows-10.md#create-the-profile).

## <a name="edition-upgrade"></a>Editie-upgrade

- **Editie bijwerken naar**: Selecteer **Windows 10 Holographic voor bedrijven**.
- **Licentiebestand**: blader naar het XML-licentiebestand dat voor u is opgegeven en selecteer dit bestand.

  ![Voer de naam van het XML-bestand in dat de gegevens over de licentie voor Holographic for Business bevat](media/Holographic-edition-upgrade.png)
 
## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt mogelijk nog niets. Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](device-profile-monitor.md).

U kunt ook editie-upgradeprofielen maken voor apparaten met [Windows 10 en hoger](edition-upgrade-windows-settings.md).
