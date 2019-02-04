---
title: Apparaatbeperkingsinstellingen configureren in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen om functies op Android-, macOS-, iOS-, Windows Phone- en Windows 10-apparaten in Microsoft Intune te beperken
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7ab60e64927db5537a106c1257a5624670771f86
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831408"
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

1. Selecteer in de [Azure-portal](https://portal.azure.com) **Alle services** > filter op **Intune** > selecteer **Intune**.
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

5. Kies **Apparaatbeperkingen** in de vervolgkeuzelijst **Profieltype**. Als u een apparaatbeperkingsprofiel wilt maken voor Windows 10 Team-apparaten, zoals Surface Hub, kiest u **Apparaatbeperkingen (Windows 10 Team)**.
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
