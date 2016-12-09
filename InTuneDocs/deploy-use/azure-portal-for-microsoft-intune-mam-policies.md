---
title: Azure-portal voor MAM-beleid | Microsoft Intune
description: Beleid maken voor het beheren van mobiele apps in de Azure Portal. De beleidsregels die u hier maakt kunnen worden toegepast op apparaten met of zonder inschrijving bij Intune.
keywords: 
author: NathBarn
ms.author: nathbarn
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
ms.sourcegitcommit: 87e37cd8334ddb9331c0662b691545cd0ab0553a
ms.openlocfilehash: b377d527621693f4c231f6f8b16cab277853cdf7


---

# <a name="azure-portal-for-microsoft-intune-mam-policies"></a>Azure-portal voor Microsoft Intune MAM-beleid

## <a name="use-the-azure-portal"></a>De Azure-portal gebruiken
In de Azure-portal kunt u beleid voor het beheer van mobiele apps (MAM) maken en beheren.

De Azure-portal biedt ondersteuning voor het maken van MAM-beleid voor:
- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij en worden beheerd in Intune**.

- Apps die worden uitgevoerd op apparaten die **niet zijn ingeschreven** bij een MDM-oplossing.
- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij een MDM-oplossing van derden**.

>[!IMPORTANT]


> Als u de Intune-beheerconsole gebruikt om uw apparaten te beheren, kunt u met de [Intune-beheerconsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) MAM-beleid maken dat apps ondersteunt voor apparaten die zijn geregistreerd bij Intune.

> Mogelijk ziet u niet alle MAM-beleidsinstellingen in de Intune-beheerconsole. De Azure-portal is de nieuwe beheerconsole voor het maken van MAM-beleid. Als u een MAM-beleid in zowel de Intune-beheerconsole als de Azure Portal maakt, wordt het beleid in de Azure Portal toegepast op de apps en geïmplementeerd op gebruikers.


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a>Meld u aan bij de Azure-portal en pas uw startpagina aan

1.  Ga naar de [Azure-portal](https://portal.azure.com) en meld u aan met uw [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-referenties.

    ![Schermopname van de aanmeldpagina van de Azure-portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Nadat u zich hebt aangemeld, ziet u het **dashboard**. De **Dashboard**-pagina kan worden aangepast.

    ![Schermopname van het dashboard van de Azure-portal](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Ga in het menu **Bladeren** naar **Intune**.![Schermopname van het menu Bladeren waarin Intune is gemarkeerd](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Kies **Intune** > **Intune Mobile Application Management** > **Instellingen**.

    ![Schermafbeelding van het tabblad Intune Mobile Application Management](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]

    > Als u een tabblad op de **Start** -pagina wilt vastzetten, gebruikt u de optie **Vastzetten** op het tabblad. Klik op het punaisepictogram op het tabblad **Intune Mobile Application Management** om het tabblad op de **Start**-pagina vast te zetten.

    ![Schermopname van het tabblad Intune Mobile Application Management waarop het pictogram Vastmaken is gemarkeerd](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Schermopname van het dashboard met de vastgemaakte Intune-tegel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## <a name="next-steps"></a>Volgende stappen
[Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


