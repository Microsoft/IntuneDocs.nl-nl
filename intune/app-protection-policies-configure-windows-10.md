---
title: Aan de slag met de configuratie van beveiligingsbeleid voor apps in Windows 10
titlesuffix: Azure portal
description: MAM-provider (mobile application management) instellen in Azure AD
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d18ef2119ed0f8adc63f6675024c8e694235ee35
ms.sourcegitcommit: 128770ecc820f6ff3c99b15752bce7a58257f1d5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Aan de slag met de configuratie van beveiligingsbeleid voor apps in Windows 10

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Voordat u een beveiligingsbeleid voor apps in Windows 10 maakt, moet u MAM (mobile application management) voor Windows 10 inschakelen door de MAM-provider in Azure AD in te stellen. Op deze manier kunt u de status van de inschrijving definiëren bij het maken van een nieuw WIP-beleid (Windows Information Protection) met Intune.

> [!NOTE]
> De status van inschrijving mag MAM of MDM (Mobile Device Management) zijn.

## <a name="to-configure-the-mam-provider"></a>De MAM-provider configureren

1.  Ga naar [Azure Portal](https://portal.azure.com/) en meld u aan met uw Intune-referenties.

2.  Kies in het menu links **Azure Active Directory**.

    ![MAM-providerconfiguratie](./media/mam-provider-sc-1.png)

3.  De blade **Azure AD** wordt geopend. Kies **Mobiliteit (MDM en MAM)** en klik vervolgens op **Microsoft Intune**.

    ![Mobiliteit (MDM en MAM)](./media/mam-provider-sc-1.png)

4.  De blade voor het configureren wordt geopend. Kies eerst **Standaard MAM-URL's herstellen** en configureer vervolgens het volgende:

    a.  Gebruikersbereik van MAM: u kunt MAM gebruiken om bedrijfsgegevens van een specifieke groep gebruikers te beveiligen die gebruikmaken van Windows 10-apparaten, of van alle gebruikers.

    b.  URL voor de voorwaarden van MAM: De URL van de voorwaarden voor het gebruik van eindpunten van de MAM-service. Deze wordt gebruikt om de voorwaarden van de MAM-service voor eindgebruikers weer te geven.

    c.  Detectie-URL van MAM: via deze URL kunnen apparaten zoeken als ze beveiligingsbeleidsregels voor apps nodig hebben.

    d.  URL van MAM-naleving:

5.  zodra u deze instellingen hebt geconfigureerd, kiest u **Opslaan**.

> [!NOTE]
> Apparaten met een MAM-inschrijvingsstatus moeten aan Azure AD zijn toegevoegd.

## <a name="next-steps"></a>Volgende stappen

[WIP-beveiligingsbeleid voor apps maken](windows-information-protection-policy-create.md)
