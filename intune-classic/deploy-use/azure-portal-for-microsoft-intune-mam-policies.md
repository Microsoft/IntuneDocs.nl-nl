---
title: Azure-portal voor MAM-beleid | Microsoft Docs
description: Beleid maken voor het beheren van mobiele apps in de Azure Portal. De beleidsregels die u hier maakt kunnen worden toegepast op apparaten met of zonder inschrijving bij Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e7fd0a83e21d499da39bd65502d8981bc3b1f61c
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="azure-portal-for-intune-app-protection-policies"></a>Azure-portal voor beveiligingsbeleid voor apps in Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Azure Portal wordt gebruikt om beveiligingsbeleid voor apps te maken en te beheren voor:

- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij en worden beheerd in Intune**.

- Apps die worden uitgevoerd op apparaten die **niet zijn ingeschreven** bij een MDM-oplossing.
- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij een MDM-oplossing van derden**.

>[!IMPORTANT]
> Azure Portal is de nieuwe beheerconsole voor het maken van beveiligingsbeleid voor apps, maar u kunt ook beveiligingsbeleid voor apps maken dat ondersteuning biedt voor apps voor apparaten die zijn ingeschreven bij Intune. Dat doet u met de [Intune-beheerconsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) voor MDM-scenario's.

> Mogelijk ziet u niet alle instellingen van beveiligingsbeleid voor apps die beschikbaar zijn in de Intune-beheerconsole. Als u beveiligingsbeleid voor apps maakt in de Intune-beheerconsole én in Azure Portal, overschrijft het beleid uit Azure Portal het beleid uit de Intune-beheerconsole. In dit scenario wordt het beveiligingsbeleid voor apps uit Azure Portal toegepast op de apps en geïmplementeerd voor gebruikers.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Meld u aan bij de Azure-portal en pas uw startpagina aan

1.  Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw Intune-referenties.

    ![Schermopname van de aanmeldpagina van de Azure-portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Nadat u zich hebt aangemeld, ziet u het **dashboard**. De **Dashboard**-pagina kan worden aangepast.

    ![Schermopname van het dashboard van de Azure-portal](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

    ![Schermopname van het menu Bladeren waarin Intune is gemarkeerd](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  Kies **Intune App Protection** > **Intune mobiel applicatiebeheer** > **Alle instellingen**.

    ![Schermafbeelding van het tabblad Intune Mobile Application Management](../media/AppManagement/MAM-Azure-Portal-2.png)

5. (Optioneel): als u een tabblad op de pagina **Start** wilt vastzetten, gebruikt u de optie **Vastzetten** op de blade. Klik op het punaisepictogram op het tabblad **Intune Mobile Application Management** om het tabblad op de **Start**-pagina vast te zetten.

    ![Schermopname van het tabblad Intune Mobile Application Management waarop het pictogram Vastmaken is gemarkeerd](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Schermopname van het dashboard met de vastgemaakte Intune-tegel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a>Volgende stappen
[Aan de slag met configureren van beveiligingsbeleid voor apps](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

