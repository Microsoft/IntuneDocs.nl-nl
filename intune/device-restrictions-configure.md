---
title: Apparaatbeperkingsinstellingen configureren in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen om functies op Android-, macOS-, iOS-, Windows Phone- en Windows 10-apparaten in Microsoft Intune te beperken
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 56ddf28bb9e81417b4b91bb18baaba14f07fbdd9
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905050"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Apparaatbeperkingsinstellingen configureren in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met apparaatbeperkingen kunt u verschillende instellingen en functies bepalen die u voor diverse categorieën beheert, waaronder:
- Beveiliging
- Browser
- Hardware
- Instellingen voor gegevensdeling

U kunt bijvoorbeeld een apparaatbeperkingsprofiel maken waarmee wordt voorkomen dat gebruikers van iOS-apparaten toegang kunnen krijgen tot de camera van het apparaat.

Lees over de basisprincipes van apparaatbeperkingsprofielen en lees dan meer artikelen voor elk platform voor meer informatie over apparaatspecificaties.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Een apparaatprofiel met apparaatbeperkingsinstellingen maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
4. Geef een **naam** en **beschrijving** op voor het beperkingsprofiel voor het apparaat.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor apparaatbeperkingsinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**
6. Kies **Apparaatbeperkingen** in de vervolgkeuzelijst **Profieltype**. Als u een apparaatbeperkingsprofiel wilt maken voor Windows 10 Team-apparaten, zoals Surface Hub, kiest u **Apparaatbeperkingen (Windows 10 Team)**.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [Android-instellingen](device-restrictions-android.md)
    - [iOS-instellingen](device-restrictions-ios.md)
    - [macOS-instellingen](device-restrictions-macos.md)
    - [Windows Phone 8.1-instellingen](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10-instellingen](device-restrictions-windows-10.md)
    - [Windows 10 Team-instellingen](device-restrictions-windows-10-teams.md)
    - [Instellingen van Windows Holographic for Business](device-restrictions-windows-holographic.md)
    - [Android-werkprofielinstellingen](device-restrictions-android-for-work.md)
8. Als u klaar bent, gaat u terug naar de pagina **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de pagina met de profielenlijst.
Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
