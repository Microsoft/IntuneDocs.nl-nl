---
title: Azure-portal voor MAM-beleid | Microsoft Intune
description: Beleid maken voor het beheren van mobiele apps in de Azure Portal. De beleidsregels die u hier maakt kunnen worden toegepast op apparaten met of zonder inschrijving bij Intune.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9eb7e79bee2bc36dffab97ffdb6f665218bc739e
ms.openlocfilehash: 0acef421f179ebf922ec8af71ba336e3e5f96bd2


---

# Azure-portal voor Microsoft Intune MAM-beleid
## De Azure-portal gebruiken
In de Azure-portal kunt u beleid voor het beheer van mobiele apps (MAM) maken en beheren.

De Azure-portal biedt ondersteuning voor het maken van MAM-beleid voor:
- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij en worden beheerd in Intune**.
- Apps die worden uitgevoerd op apparaten die **niet zijn ingeschreven** bij een MDM-oplossing.
- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij een MDM-oplossing van derden**.

>[!IMPORTANT]

> Als u de Intune-beheerconsole gebruikt om uw apparaten te beheren, kunt u met de [Intune-beheerconsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) MAM-beleid maken dat apps ondersteunt voor apparaten die zijn geregistreerd bij Intune.

> Mogelijk ziet u niet alle MAM-beleidsinstellingen in de Intune-beheerconsole. De Azure-portal is de nieuwe beheerconsole voor het maken van MAM-beleid. Als u een MAM-beleid in zowel de Intune-beheerconsole als de Azure Portal maakt, wordt het beleid in de Azure Portal toegepast op de apps en geïmplementeerd op gebruikers.

## Meld u aan bij de Azure-portal en pas uw startpagina aan

1.  Ga naar de [Azure-portal](https://portal.azure.com) en meld u aan met uw [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-referenties.

    ![Schermopname van de aanmeldpagina van de Azure-portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Nadat u zich hebt aangemeld, wordt de pagina **Dashboard** weergegeven. De **Dashboard**-pagina kan worden aangepast.

    ![Schermopname van het dashboard van de Azure-portal](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Ga in het menu **Bladeren** naar **Intune**.![Schermopname van het menu Bladeren waarin Intune is gemarkeerd](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Kies **Intune** > **Intune Mobile Application Management** > **Instellingen**.

    ![Schermafbeelding van het tabblad Intune Mobile Application Management](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Als u een blade wilt vastzetten op de pagina **Start**, klikt u op het punaisepictogram op de blade **Intune Mobile Application Management**.

    ![Schermopname van het tabblad Intune Mobile Application Management waarop het pictogram Vastmaken is gemarkeerd](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Schermopname van het dashboard met de vastgemaakte Intune-tegel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Volgende stappen
[Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management)](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


