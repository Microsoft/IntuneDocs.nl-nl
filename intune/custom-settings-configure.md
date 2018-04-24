---
title: Aangepaste apparaatinstellingen gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Een profiel toevoegen of maken om aangepaste instellingen te gebruiken voor Windows-, Android en iOS-apparaten met Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce7c263435f92a041b93dc5d34ffa912c6fa87fb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Een profiel maken met aangepaste instellingen in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune heeft mogelijk niet alle ingebouwde instellingen die u nodig hebt of wilt hebben. Of u wilt wellicht een instelling gebruiken die beschikbaar is in andere apparaatprofielen. Om deze instellingen toe te voegen, maakt u een apparaatprofiel en configureert u het profiel met aangepaste apparaatinstellingen.

In dit artikel worden de basisstappen beschreven om een profiel met aangepaste instellingen te maken. Het bevat ook koppelingen om u te verdiepen in het maken van aangepaste instellingen met de verschillende platforms.

## <a name="custom-settings-on-different-platforms"></a>Aangepaste instellingen op verschillende platforms
Aangepaste instellingen worden voor elk platform anders geconfigureerd. Om bijvoorbeeld functies op Android- en Windows-apparaten te beheren, kunt u OMA-URI-waarden (Open Mobile Alliance Uniform Resource Identifier) opgeven. Voor Apple-apparaten kunt u een bestand importeren dat u met [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt.

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie**, selecteer dan **Profielen** en kies **Profiel maken**.
4. Voer een **Naam** en **Beschrijving** in voor het aangepaste profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. U kunt kiezen uit de volgende platforms:

    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**

6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u kiest. De volgende koppelingen geven meer informatie over de aangepaste instellingen voor elk platform:

    - [Android-instellingen](custom-settings-android.md)
    - [iOS-instellingen](custom-settings-ios.md)
    - [macOS-instellingen](custom-settings-macos.md)
    - [Windows Phone 8.1-instellingen](custom-settings-windows-phone-8-1.md)
    - [Windows 10-instellingen](custom-settings-windows-10.md)
    - [Instellingen van Windows Holographic for Business](custom-settings-windows-holographic.md)
    - [Android for Work-instellingen](custom-settings-android-for-work.md)

8. Wanneer u bent klaar, selecteert u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven in de profielenlijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u dit profiel wilt toewijzen aan groepen.
