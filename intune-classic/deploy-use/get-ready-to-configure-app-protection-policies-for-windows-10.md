---
title: Aan de slag met de configuratie van beveiligingsbeleid voor apps in Windows 10
description: MAM-provider (mobile application management) instellen in Azure AD
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 04/18/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9b91d3740ead5815974d7ffee67c15b7769b0210
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31025549"
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Aan de slag met de configuratie van beveiligingsbeleid voor apps in Windows 10

[!INCLUDE [note for both-portals](../includes/note-for-both-portals.md)]

Voordat u een beveiligingsbeleid voor apps in Windows 10 maakt, moet u MAM (mobile application management) voor Windows 10 inschakelen door de MAM-provider in Azure AD in te stellen. Op deze manier kunt u de status van de inschrijving definiëren bij het maken van een nieuw WIP-beleid (Windows Information Protection) met Intune.

> [!NOTE]
> De status van inschrijving mag MAM of MDM (Mobile Device Management) zijn.

## <a name="to-configure-the-mam-provider"></a>De MAM-provider configureren

1.  Ga naar [Azure Portal](https://portal.azure.com/) en meld u aan met uw Intune-referenties.

2.  Kies in het menu links **Azure Active Directory**.

    ![MAM-providerconfiguratie](../media/AppManagement/mam-provider-sc-1.png)

3.  De blade **Azure AD** wordt geopend. Kies **Mobiliteit (MDM en MAM)** en klik vervolgens op **Microsoft Intune**.

    ![Mobiliteit (MDM en MAM)](../media/AppManagement/mam-provider-sc-2.png)

4.  De blade voor het configureren wordt geopend. Kies eerst **Standaard MAM-URL's herstellen** en configureer vervolgens het volgende:

    a.  Gebruikersbereik van MAM: u kunt MAM gebruiken om bedrijfsgegevens van een specifieke groep gebruikers te beveiligen die gebruikmaken van Windows 10-apparaten, of van alle gebruikers.

    b.  URL voor de voorwaarden van MAM: De URL van de voorwaarden voor het gebruik van eindpunten van de MAM-service. Deze wordt gebruikt om de voorwaarden van de MAM-service voor eindgebruikers weer te geven.

    c.  Detectie-URL van MAM: via deze URL kunnen apparaten zoeken als ze beveiligingsbeleidsregels voor apps nodig hebben.

    d.  URL van MAM-naleving:

5.  zodra u deze instellingen hebt geconfigureerd, kiest u **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

[WIP-beveiligingsbeleid voor apps maken](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)
