---
title: Apparaatprofielen maken in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen of configureren in Microsoft Intune, met inbegrip van het platformtype selecteren en de instellingen configureren in de Azure Portal
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4e1febb5f12de038d2ddd543be883f71ef79005
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Een apparaatprofiel maken in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="create-the-profile"></a>Het profiel maken
1. In de [Azure-portal](https://portal.azure.com) selecteert u **Alle services** en zoekt u naar **Microsoft Intune**.

2. In **Microsoft Intune** selecteert u **Apparaatconfiguratie**,dan **Profielen** en vervolgens selecteert u  **Profiel maken**.

3. Voer de volgende eigenschappen in:

    - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: optioneel, maar aanbevolen. Geef een beschrijving voor het profiel op.
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

        -  [Instellingen voor apparaatfuncties](device-features-configure.md)
        -  [Apparaatbeperkingsinstellingen](device-restrictions-configure.md)
        -  [E-mailinstellingen](email-settings-configure.md)
        -  [VPN-instellingen](vpn-settings-configure.md)
        -  [Wi-Fi-instellingen](wi-fi-settings-configure.md)
        -  [Upgrade-instellingen voor Windows 10-editie](edition-upgrade-configure-windows-10.md)
        -  [Certificaatinstellingen](certificates-configure.md)
        -  [Instellingen voor Windows Information Protection](windows-information-protection-configure.md)
        -  [Onderwijsinstellingen](education-settings-configure.md)
        -  [Aangepaste instellingen](custom-settings-configure.md)

    ![De instellingen opgeven om een apparaatprofiel te maken](./media/create-device-profile.png)

4. Selecteer **Maken** na voltooiing.

Het profiel wordt gemaakt en wordt weergegeven in de lijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) als u dit profiel wilt toewijzen aan groepen.


## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen toewijzen met Microsoft Intune](device-profile-assign.md) om apparaatprofielen toe te wijzen.
