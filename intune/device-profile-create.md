---
title: Apparaatprofielen maken in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen of configureren in Microsoft Intune, met inbegrip van het selecteren van het platformtype en het configureren van de instellingen in Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6bc6f5d2f32ff060eb2eec568b0048628ad0e09c
ms.sourcegitcommit: 349ab913932547b4a7491181f0aff092f109b87b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/26/2018
ms.locfileid: "52303852"
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
       - **Android Enterprise**
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
       -  [Identiteitsbescherming](identity-protection-configure.md)  
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
[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
