---
title: Apparaatprofielen maken in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen of configureren in Microsoft Intune, met inbegrip van het selecteren van het platformtype en het configureren van de instellingen in Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3f62e306574606ffa1eb1e6f242c3cb30b1a9c1b
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34744649"
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Een apparaatprofiel maken in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Het profiel maken
1. In [Azure Portal](https://portal.azure.com) selecteert u **Alle services** en zoekt u naar **Microsoft Intune**.

2. In **Microsoft Intune** selecteert u **Apparaatconfiguratie** en vervolgens **Profielen**. Selecteer vervolgens **Profiel maken**.

3. Voer de volgende eigenschappen in:

   - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
   - **Beschrijving:** voer een beschrijving in voor het profiel. (Een beschrijving is optioneel, maar wordt aanbevolen.)
   - **Platform**: selecteer het platformtype:  

       - **Android**
       - **Android for Work**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 en hoger**
       - **Windows 10 en hoger**

   - **Profieltype**: selecteer het type dat u wilt maken. De lijst is afhankelijk van het platform dat u kiest.
   - **Instellingen**: in de volgende onderwerpen worden de instellingen voor elk profieltype beschreven:

       -  [Apparaatfuncties](device-features-configure.md)
       -  [Apparaatbeperkingen](device-restrictions-configure.md)
       -  [Endpoint Protection](endpoint-protection-configure.md)
       -  [Kiosk](kiosk-settings.md)
       -  [E-mail](email-settings-configure.md)
       -  [VPN](vpn-settings-configure.md)
       -  [Wi-Fi](wi-fi-settings-configure.md)
       -  Education voor [Windows 10](education-settings-configure.md) en [iOS](wi-fi-settings-ios.md)
       -  [Upgrade Windows 10-editie](edition-upgrade-configure-windows-10.md)
       -  [Updatebeleid voor iOS](software-updates-ios.md)
       -  [Certificaten](certificates-configure.md)
       -  [Windows Information Protection](windows-information-protection-configure.md)
       -  [Aangepast](custom-settings-configure.md)

     ![Schermopname van Profiel maken](./media/create-device-profile.png)

4. Selecteer **Maken** na voltooiing.

Het profiel wordt gemaakt en wordt weergegeven in de lijst.

## <a name="next-steps"></a>Volgende stappen
[Wijs het profiel toe](device-profile-assign.md) en [controleer de status](device-profile-monitor.md).
