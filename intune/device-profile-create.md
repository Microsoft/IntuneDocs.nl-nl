---
title: Intune-apparaatconfiguratieprofielen maken
titlesuffix: Azure portal
description: Meer informatie over het maken van configuratieprofielen voor Intune-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5c23d33bde16ada61b6164bb560a30b81cab0020
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Apparaatconfiguratieprofielen maken in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
2. Kies op de blade met de profielenlijst **Profiel maken**.
3. Geef op de blade **Profiel maken** de volgende informatie op:
    - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: voer een beschrijving in voor het profiel (optioneel).
    - **Platform**: selecteer het platformtype voor het profiel dat u wilt maken.
    - **Profieltype**: selecteer het type profiel dat u wilt maken. Welke typen beschikbaar zijn, is afhankelijk van het platform dat u hebt gekozen.
    - **Instellingen**: in de volgende onderwerpen vindt u meer informatie over de instellingen voor elk profieltype:
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

    ![Apparaatprofiel maken](./media/create-device-profile.png)
4. Als u klaar bent met het configureren van de instellingen, kiest u **Maken** op de blade **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.


### <a name="next-steps"></a>Volgende stappen
Zie [How to assign device profiles with Microsoft Intune](device-profile-assign.md) (Apparaatprofielen toewijzen met Microsoft Intune) voor meer informatie over het toewijzen van apparaatprofielen.
