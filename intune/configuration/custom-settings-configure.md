---
title: Aangepaste apparaatinstellingen gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Een profiel toevoegen of maken om aangepaste instellingen te gebruiken voor apparaten met Windows 10 en hoger en Windows Phone-, Windows 8.1-, Android-, Android Enterprise-, macOS- en iOS-apparaten met Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 18e0edc4a99b8974e6408a7c8776b0c042404210
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724253"
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Een profiel maken met aangepaste instellingen in Intune

## <a name="what-are-custom-profiles"></a>Wat zijn aangepaste profielen?

Microsoft Intune bevat veel ingebouwde instellingen om verschillende functies op een apparaat te beheren. U kunt ook aangepaste profielen maken. Aangepaste profielen zijn ideaal wanneer u apparaatinstellingen en -functies wilt gebruiken die niet in Intune zijn ingebouwd. Deze profielen bevatten functies en instellingen die u op apparaten in uw organisatie kunt beheren. U kunt bijvoorbeeld een aangepast profiel maken waarmee u dezelfde functie voor elk iOS-apparaat instelt.

Zie [Wat zijn Microsoft Intune-apparaatprofielen?](device-profiles.md) voor meer informatie over configuratieprofielen. 

Dit artikel bevat koppelingen voor het maken van aangepaste profielen voor Android, Android Enterprise, iOS, macOS en Windows.

## <a name="available-platforms"></a>Beschikbare platformen

Aangepaste instellingen worden voor elk platform anders geconfigureerd. Om bijvoorbeeld functies op Android- en Windows-apparaten te beheren, kunt u OMA-URI-waarden (Open Mobile Alliance Uniform Resource Identifier) opgeven. Voor Apple-apparaten kunt u een bestand importeren dat u met [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) of [Apple Profile Manager](https://support.apple.com/profile-manager) hebt gemaakt.

Aangepaste profielen worden op een zelfde manier gemaakt als ingebouwde profielen en zijn beschikbaar op de volgende platformen:

- [Android](../custom-settings-android.md)
- [Android Enterprise](../custom-settings-android-for-work.md)
- [iOS/iPadOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)

## <a name="next-steps"></a>Volgende stappen

Kies uw platform en ga aan de slag:

- [Android](../custom-settings-android.md)
- [Android Enterprise](../custom-settings-android-for-work.md)
- [iOS/iPadOS](custom-settings-ios.md)
- [macOS](custom-settings-macos.md)
- [Windows 10](custom-settings-windows-10.md)
- [Windows Holographic for Business](custom-settings-windows-holographic.md)
- [Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
