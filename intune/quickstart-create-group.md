---
title: Snelstart - Een groep maken om gebruikers te beheren
titlesuffix: Microsoft Intune
description: In deze snelstart gebruikt u Microsoft Intune om een groep te maken op basis van bestaande gebruikers.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a4468f2e6919349095d934790740afc8c347282
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581585"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Snelstart: een groep maken om gebruikers te beheren

In deze snelstart gebruikt u Intune om een groep te maken op basis van een bestaande gebruiker. Groepen worden gebruikt om uw gebruikers te beheren en de toegang van uw medewerkers tot uw zakelijke resources te regelen. Deze resources kunnen deel uitmaken van het intranet van uw bedrijf, of het kunnen externe resources zijn, zoals SharePoint-sites, SaaS-apps of web-apps.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

>[!NOTE]
>Intune biedt vooraf gemaakte de groepen **Alle gebruikers** en **Alle apparaten** in de console met handige, ingebouwde optimalisaties.

## <a name="prerequisites"></a>Vereisten

- Als u de stappen in deze snelstart wilt uitvoeren, moet u eerst [een gebruiker maken](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service. U gaat in Azure Portal naar Intune door **Alle services** > **Intune** te kiezen. Intune bevindt zich in de sectie **Controle en beheer**.

## <a name="create-a-group"></a>Een groep maken
1. Wanneer u het deelvenster **Microsoft Intune** hebt geopend, selecteert u **Groepen** > **Nieuwe groep**.
2. In het deelvenster **Groep** selecteert u **Groepstype** > **Beveiliging**.
3. Stel de **naam** in op Contoso Testers en voeg een **beschrijving** toe aan de groep.
4. Stel **Type lidmaatschap** in op **Toegewezen**. 
5. Klik op **Leden** en selecteer **leden** voor de groep uit de bestaande lijst.

    ![Schermopname van het maken van een groep in Microsoft Intune](./media/quickstart-use-groups-01.png)

6. Klik op **Selecteren**.
7. Klik op **Maken**.

Als u de groep hebt gemaakt, wordt deze weergegeven in de lijst **Alle groepen**. 

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u Intune gebruikt om een groep te maken op basis van een bestaande gebruiker.

> [!div class="nextstepaction"]
> [Een nalevingsbeleid voor apparaten maken](quickstart-create-policy.md)
