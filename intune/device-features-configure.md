---
title: Instellingen van apparaatfuncties voor Microsoft Intune configureren
titleSuffix: 
description: Meer informatie over hoe u met Microsoft Intune functies kunt configureren op de apparaten die u beheert.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6cd646976deb1599c4cbc9154b6f2a487029dd79
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
#<a name="configure-device-feature-settings-in-microsoft-intune"></a>Instellingen voor apparaatfuncties configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met apparaatfuncties kunt u functies op iOS- en macOS-apparaten beheren, zoals AirPrint, meldingen en configuraties voor gedeelde apparaten.

Lees in dit artikel wat de basisbeginselen zijn voor het configureren van de profielen voor apparaatfuncties en lees vervolgens aanvullende artikelen voor elk platform voor apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-device-feature-settings"></a>Een apparaatprofiel met instellingen voor apparaatfuncties maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies op de pagina **Intune** de optie **Apparaatconfiguratie**.
2. Kies op de pagina **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
3. Kies **Profiel maken** op de pagina Profielen.
4. Voer op de pagina **Profiel maken** een **naam** en **beschrijving** in voor het profiel van de apparaatfuncties.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen voor apparaatfuncties kiezen:
    - **iOS**
    - **macOS**
6. Kies in de vervolgkeuzelijst **Profieltype** de optie **Apparaatfuncties**. 
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende artikelen voor gedetailleerde instellingen voor elk platform:
    - [AirPrint-instellingen voor iOS en MacOS](air-print-settings-ios-macos.md)
    - [AirPlay-instellingen voor iOS](airplay-settings-ios.md)
    - [Indelingsinstellingen voor het iOS-startscherm](home-screen-settings-ios.md)
    - [App-meldingsinstellingen voor iOS opgeven](app-notification-settings-ios.md)
    - [Configuratie-instellingen voor gedeelde apparaten voor iOS](shared-device-settings-ios.md)
    - [Intune configureren voor eenmalige aanmelding vanaf iOS-apparaten](sso-ios.md)
    - [Filterinstellingen voor webinhoud in iOS](web-content-filter-settings-ios.md)

8. Als u klaar bent, selecteert u **OK**, gaat u terug naar de pagina **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de pagina met de profielenlijst.
## <a name="next-steps"></a>Volgende stappen

Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u dit profiel wilt toewijzen aan groepen.



