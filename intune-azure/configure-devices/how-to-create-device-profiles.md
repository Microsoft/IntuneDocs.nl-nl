---
title: Apparaatconfiguratieprofielen in Intune maken | Intune Azure Preview
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u apparaatconfiguratieprofielen in Intune kunt maken.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: cc9ef6777f06aca5ef93154c38e12520ab9ed348
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a>Apparaatconfiguratieprofielen maken in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
2. Kies op de blade met de profielenlijst **Profiel maken**.
3. Geef de volgende informatie op de blade **Profiel maken** op:
    - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: voer een beschrijving in voor het profiel (optioneel).
    - **Platform**: selecteer het platformtype voor het profiel dat u wilt maken.
    - **Profieltype**: selecteer het type profiel dat u wilt maken. Welke typen beschikbaar zijn, is afhankelijk van het platform dat u hebt gekozen.
    - **Instellingen**: in de volgende onderwerpen vindt u meer informatie over de instellingen voor elk profieltype:
        -  [Apparaatbeperkingsinstellingen](/intune-azure/configure-devices/how-to-configure-device-restrictions)
        -  [E-mailinstellingen](/intune-azure/configure-devices/how-to-configure-email-settings)
        -  [VPN-instellingen](/intune-azure/configure-devices/how-to-configure-vpn-settings)
        -  [Wi-Fi-instellingen](/intune-azure/configure-devices/how-to-configure-wi-fi-settings)
        -  [Upgrade-instellingen voor Windows 10-editie](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade)
        -  [Certificaatinstellingen](/intune-azure/configure-devices/how-to-configure-certificates)
        -  [Instellingen voor Windows Information Protection](/intune-azure/configure-devices/how-to-configure-windows-information-protection)
        -  [Onderwijsinstellingen](/intune-azure/configure-devices/education-settings-for-ios.md)
        -  [Aangepaste instellingen](/intune-azure/configure-devices/how-to-configure-custom-settings)

    ![Apparaatprofiel maken](./media/create-device-profile.png)
4. Als u klaar bent met het configureren van de instellingen, kiest u **Maken** op de blade **Profiel maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.


### <a name="next-steps"></a>Volgende stappen
Zie [How to assign device profiles with Microsoft Intune](/intune-azure/configure-devices/how-to-assign-device-profiles) (Apparaatprofielen toewijzen met Microsoft Intune) voor meer informatie over het toewijzen van apparaatprofielen.

