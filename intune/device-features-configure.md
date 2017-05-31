---
title: Instellingen voor apparaatfuncties configureren in Intune
titleSuffix: Intune Azure preview
description: 'Preview-versie van Intune Azure: lees hoe u met Intune functies kunt configureren op de apparaten die u beheert.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f584d76a498264f8ab1cf883f5ee95d52d3446d3
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Instellingen voor apparaatfuncties configureren in Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Met apparaatbeperkingen kunt u functies op iOS- en macOS-apparaten beheren, zoals AirPrint, meldingen en configuraties voor gedeelde apparaten.

Lees in dit onderwerp wat de basisbeginselen zijn voor het configureren van de profielen voor apparaatfuncties en lees vervolgens de aanvullende onderwerpen voor elk platform voor apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Een apparaatprofiel met apparaatbeperkingsinstellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en **beschrijving** in voor het profiel voor de apparaatfuncties.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen voor apparaatfuncties kiezen:
    - **iOS**
    - **macOS**
6. Kies **Apparaatfuncties** in de vervolgkeuzelijst **Profieltype**. 
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [AirPrint-instellingen voor iOS en MacOS](air-print-settings-ios-macos.md)
     - [AirPlay-instellingen voor iOS](airplay-settings-ios.md)
    - [Indelingsinstellingen voor het iOS-startscherm](home-screen-settings-ios.md)
    - [App-meldingsinstellingen voor iOS opgeven](app-notification-settings-ios.md)
    - [Configuratie-instellingen voor gedeelde apparaten voor iOS](shared-device-settings-ios.md)

8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.




