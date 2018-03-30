---
title: Apparaatprofielen maken in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen of configureren in Microsoft Intune, met inbegrip van het selecteren van het platformtype en het configureren van de instellingen in Azure Portal.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e5070052c0d4cce3cfd81a7bae259bc7dfb22e7f
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/20/2018
---
# <a name="create-a-device-profile-in-microsoft-intune"></a>Een apparaatprofiel maken in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

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

    ![Schermopname van Profiel maken](./media/create-device-profile.png)

4. Selecteer **Maken** na voltooiing.

Het profiel wordt gemaakt en wordt weergegeven in de lijst.


## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen toewijzen met Microsoft Intune](device-profile-assign.md) om apparaatprofielen toe te wijzen.
