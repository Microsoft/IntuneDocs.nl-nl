---
title: Snelstart - Een groep maken om gebruikers te beheren
titlesuffix: Microsoft Intune
description: In deze snelstart gebruikt u Microsoft Intune om een groep te maken op basis van bestaande gebruikers.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/09/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d6c51a2823e95526b76e5e71e35420d1744b70f6
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52178375"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Snelstart: een groep maken om gebruikers te beheren

In deze snelstart gebruikt u Intune om een groep te maken op basis van een bestaande gebruiker. Groepen worden gebruikt om uw gebruikers te beheren en de toegang van uw medewerkers tot uw zakelijke resources te regelen. Deze resources kunnen deel uitmaken van het intranet van uw bedrijf, of het kunnen externe resources zijn, zoals SharePoint-sites, SaaS-apps of web-apps.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

>[!NOTE]
>Intune biedt vooraf gemaakte de groepen **Alle gebruikers** en **Alle apparaten** in de console met handige, ingebouwde optimalisaties.

## <a name="prerequisites"></a>Vereisten

- Als u de stappen in deze snelstart wilt uitvoeren, moet u eerst [een gebruiker maken](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als [globale beheerder of Intune-servicebeheerder](users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-a-group"></a>Een groep maken

U maakt een groep die later in deze snelstartreeks wordt gebruikt.

1. Wanneer u het deelvenster **Microsoft Intune** hebt geopend, selecteert u **Groepen** > **Nieuwe groep**.
2. Selecteer in de vervolgkeuzelijst **Groepstype** de optie **Beveiliging**.
3. Stel de **naam** in op Contoso Testers en voeg een **beschrijving** toe aan de groep.
4. Stel **Type lidmaatschap** in op **Toegewezen**. 
5. Klik op **Leden** en selecteer uit de bestaande lijst een of meer leden voor de groep.

    ![Schermopname van het maken van een groep in Microsoft Intune](./media/quickstart-use-groups-01.png)

6. Klik op **Selecteren** > **maken**.

Als u de groep hebt gemaakt, wordt deze weergegeven in de lijst **Alle groepen**. 

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u Intune gebruikt om een groep te maken op basis van een bestaande gebruiker. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](groups-add.md) voor meer informatie over het toevoegen van groepen aan Intune.

Als u deze reeks Intune-snelstartgidsen wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Snelstart: Automatische inschrijving voor Windows 10-apparaten instellen](quickstart-setup-auto-enrollment.md)
