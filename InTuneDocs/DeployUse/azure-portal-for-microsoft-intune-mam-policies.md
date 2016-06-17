---
# required metadata

title: Azure Portal voor MAM-beleid | Microsoft Intune
description:
keywords:
author: karthikaraman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure Portal voor Microsoft Intune MAM-beleid
## Toegang tot de Azure-portal
In **Azure Portal** kunt u beleid voor het beheer van mobiele apps maken en beheren.

Azure Portal biedt ondersteuning voor het maken van MAM-beleid voor:
- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij en worden beheerd door Intune**.
- Apps die worden uitgevoerd op apparaten die **niet zijn geregistreerd** bij een MDM-oplossing.
- Apps die worden uitgevoerd op apparaten die zijn **geregistreerd bij een MDM-oplossing van derden**.

Als u momenteel de **Intune-beheerconsole** gebruikt om uw apparaten te beheren, kunt u met de [Intune-beheerconsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) MAM-beleid maken dat apps ondersteunt voor apparaten die zijn geregistreerd bij Intune.
>[!IMPORTANT]
> Mogelijk ziet u in de Intune-beheerconsole niet alle MAM-beleidsinstellingen. Azure Portal is de nieuwe beheerconsole voor het maken van MAM-beleid. Als u MAM-beleid in zowel de Intune-beheerconsole als Azure Portal maakt, wordt het beleid in Azure Portal toegepast op de apps en geïmplementeerd bij gebruikers.

## Meld u aan bij Azure Portal en pas uw startpagina aan

1.  Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-referenties.

    ![Schermopname van de aanmeldingspagina van Azure Portal](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  Wanneer u zich hebt aangemeld, ziet u het **dashboard**. De pagina **Dashboard** bevat een reeks standaardtegels die u kunt verwijderen. U kunt ook nieuwe tegels toevoegen om de pagina aan uw eigen voorkeuren aan te passen.

    ![Schermopname van het dashboard van Azure Portal](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  Ga in het menu **Bladeren** naar **Intune**.![Schermopname van het menu Bladeren waarin Intune is gemarkeerd](../media/AppManagement/AzurePortal_MAM_Browse_Intune.png)

4.  Klik op **Intune > Intune Mobile Application Management > Instellingen**.

    ![Schermopname van de blade Intune Mobile Application Management](../media/AppManagement/AzurePortal_MAM_Mainblade.png)

    > [!TIP]
    > Als u een blade op de **Start** -pagina wilt vastzetten, gebruikt u de optie **Vastzetten** op de blade.  Klik op het punaisepictogram op de blade **Intune Mobile Application Management**om de blade op de **Start** -pagina vast te zetten.

    ![Schermopname van de blade Intune Mobile Application Management waarop het pictogram Vastmaken is gemarkeerd](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Schermopname van het dashboard met de vastgemaakte Intune-tegel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)
## Volgende stappen
[Bereid u voor op het configureren van beleid voor het beheer van mobiele apps](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)


<!--HONumber=May16_HO3-->


