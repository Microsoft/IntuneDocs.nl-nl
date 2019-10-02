---
title: Snelstart - Een groep maken om gebruikers te beheren
titleSuffix: Microsoft Intune
description: In deze snelstart gebruikt u Microsoft Intune om een groep te maken op basis van bestaande gebruikers.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/24/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ccf0f06993ef0edf06ca60ba4de7973ed878441a
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727100"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Quickstart: Een groep maken om gebruikers te beheren

In deze snelstart gebruikt u Intune om een groep te maken op basis van een bestaande gebruiker. Groepen worden gebruikt om uw gebruikers te beheren en de toegang van uw medewerkers tot uw zakelijke resources te regelen. Deze resources kunnen deel uitmaken van het intranet van uw bedrijf, of het kunnen externe resources zijn, zoals SharePoint-sites, SaaS-apps of web-apps.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

>[!NOTE]
>Intune biedt vooraf gemaakte de groepen **Alle gebruikers** en **Alle apparaten** in de console met handige, ingebouwde optimalisaties.

## <a name="prerequisites"></a>Vereisten

- Als u de stappen in deze snelstart wilt uitvoeren, moet u eerst [een gebruiker maken](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u bij de [Intune](https://aka.ms/intuneportal)-portal aan als [globale beheerder of Intune-servicebeheerder](users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-a-group"></a>Een groep maken

U maakt een groep die later in deze snelstartreeks wordt gebruikt. Ga als volgt te werk om een groep te maken:

1. Wanneer u het deelvenster **Microsoft Intune** hebt geopend, selecteert u **Groepen** > **Nieuwe groep**.
2. Selecteer in de vervolgkeuzelijst **Groepstype** de optie **Beveiliging**.
3. Geef in het veld **Groepsnaam** de naam van de nieuwe groep (bijvoorbeeld **Contoso Testers**) op.
4. Voeg een **Beschrijving** aan de groep toe.
5. Stel **Type lidmaatschap** in op **Toegewezen**. 
6. Klik op **Leden** en selecteer uit de lijst een of meer leden voor de groep.

    ![Schermopname van het maken van een groep in Microsoft Intune](./media/quickstart-create-group/quickstart-use-groups-01.png)

7. Klik op **Selecteren** > **maken**.

Als u de groep hebt gemaakt, wordt deze weergegeven in de lijst **Alle groepen**. 

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u Intune gebruikt om een groep te maken op basis van een bestaande gebruiker. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](../groups-add.md) voor meer informatie over het toevoegen van groepen aan Intune.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Automatische inschrijving voor Windows 10-apparaten instellen](../enrollment/quickstart-setup-auto-enrollment.md)
