---
title: Aangepaste apparaatinstellingen configureren in Intune
titleSuffix: Azure portal
description: Meer informatie over hoe u Intune kunt gebruiken voor het configureren van aangepaste instellingen op de apparaten die u beheert.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e3821f40cdf1c36f020bf807eed5c6fbd83a9aa
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Aangepaste apparaatinstellingen configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Wanneer u aangepaste instellingen moet gebruiken

Het kan handig zijn aangepaste apparaatinstellingen te gebruiken wanneer de instellingen die u wilt configureren, niet in Intune zijn ingebouwd, en beschikbaar zijn via andere apparaatprofielen.
Aangepaste instellingen worden voor elk platform anders geconfigureerd. Voor Android- en Windows-apparaten kunt u bijvoorbeeld OMA-URI-waarden (Open Mobile Alliance Uniform Resource Identifier) opgeven voor het beheren van functies op apparaten. Voor Apple-apparaten kunt u een bestand importeren dat u met [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) hebt gemaakt.

Gebruik de informatie in dit onderwerp voor meer informatie over de basisbeginselen voor het configureren van profielen met aangepaste instellingen en lees vervolgens de aanvullende onderwerpen voor elk platform voor meer apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-custom-settings"></a>Een apparaatprofiel met aangepaste instellingen maken

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het aangepaste profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor aangepaste apparaatinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 en hoger**
6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [Android-instellingen](custom-settings-android.md)
    - [iOS-instellingen](custom-settings-ios.md)
    - [macOS-instellingen](custom-settings-macos.md)
    - [Windows Phone 8.1-instellingen](custom-settings-windows-phone-8-1.md)
    - [Windows 10-instellingen](custom-settings-windows-10.md)
    - [Android for Work-instellingen](custom-settings-android-for-work.md)
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.
