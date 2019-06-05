---
title: Apparaatbeperkingsinstellingen configureren in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen om functies op Android-, macOS-, iOS-, Windows Phone- en Windows 10-apparaten in Microsoft Intune te beperken
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4cae90723c7ff92a8042f068fb49c1709506c7ff
ms.sourcegitcommit: 063177c6c365fef3642edd7c455790958469aad9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/30/2019
ms.locfileid: "66412431"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Apparaatbeperkingsinstellingen configureren in Microsoft Intune

Met apparaatbeperkingen kunt u verschillende instellingen en functies bepalen die u voor diverse categorieën beheert, waaronder:
- Beveiliging
- Browser
- Hardware
- Instellingen voor gegevensdeling

U kunt bijvoorbeeld een apparaatbeperkingsprofiel maken waarmee wordt voorkomen dat gebruikers van iOS-apparaten toegang kunnen krijgen tot de camera van het apparaat.

Lees over de basisprincipes van apparaatbeperkingsprofielen en lees dan meer artikelen voor elk platform voor meer informatie over apparaatspecificaties.

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Geef een **naam** en **beschrijving** op voor het beperkingsprofiel voor het apparaat.
4. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor apparaatbeperkingsinstellingen:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**

5. Kies **Apparaatbeperkingen** in de vervolgkeuzelijst **Profieltype**. Als u een apparaatbeperkingsprofiel wilt maken voor Windows 10 Team-apparaten, zoals Surface Hub, kiest u **Apparaatbeperkingen (Windows 10 Team)** .
6. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Kies uw platform voor gedetailleerde instellingen:

    - [Android-instellingen](device-restrictions-android.md)
    - [Instellingen voor Android Enterprise](device-restrictions-android-for-work.md)
    - [iOS-instellingen](device-restrictions-ios.md)
    - [macOS-instellingen](device-restrictions-macos.md)
    - [Windows Phone 8.1-instellingen](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10-instellingen](device-restrictions-windows-10.md)
    - [Windows 10 Team-instellingen](device-restrictions-windows-10-teams.md)
    - [Instellingen van Windows Holographic for Business](device-restrictions-windows-holographic.md)

7. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Nadat het profiel is gemaakt, is het klaar om te worden toegewezen. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
