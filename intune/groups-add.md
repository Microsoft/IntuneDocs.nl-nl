---
title: Groepen toevoegen om gebruikers en apparaten in te delen
titlesuffix: Microsoft Intune
description: Voeg groepen toe om gebruikers en apparaten in te delen op basis van geografie, afdeling of hardwarespecificaties.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7d2b551832d8d0e467d079df673954318623e4c
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="add-groups-to-organize-users-and-devices"></a>Groepen toevoegen om gebruikers en apparaten in te delen
Intune maakt gebruik van Azure AD-groepen (Active Directory) voor het beheren van apparaten en gebruikers. Als beheerder van Intune kunt u groepen instellen die aansluiten bij de behoeften van uw organisatie. Maak groepen om gebruikers of apparaten in te delen op geografische locatie, afdeling of hardwarekenmerken. Gebruik groepen voor het beheren van taken op schaal. U kunt zo bijvoorbeeld beleidsregels instellen voor een groot aantal gebruikers tegelijk of apps implementeren op een reeks apparaten.

In dit onderwerp wordt uitgelegd hoe u groepen toevoegt voor gebruik in Intune.

U kunt de volgende typen groepen toevoegen:
- **Toegewezen groepen**: voeg handmatig gebruikers of apparaten toe aan een statische groep
- **Dynamische groepen**: (met Azure Active Directory Premium) hiermee kunt u dynamisch gebruikers- of apparaatgroepen maken aan de hand van eenvoudige of geavanceerde regels

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Volg de onderstaande stappen om een nieuwe groep te maken.
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. In het deelvenster **Intune** kiest u **Groepen**. Kies vervolgens **Nieuwe groep** in het deelvenster **Alle groepen**.
  ![Schermafbeelding van de Azure-portal met de optie Nieuwe groep geselecteerd](./media/groups-add-new.png)
2. Geef een **groepstype**, **naam** en **beschrijving** op voor de nieuwe groep. Deze eigenschappen worden alleen weergegeven in de beheerportal en zijn niet zichtbaar voor gebruikers.

3. Kies een waarde voor **Type lidmaatschap**:
  - **Toegewezen**: om een groep te maken met handmatig toegewezen leden. Lees hier meer over [toegewezen groepen van Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Dynamische gebruiker**: om een gebruikersgroep te maken op basis van een **dynamische query**.
  - **Dynamisch apparaat**: om een apparaatgroep te maken op basis van een **dynamische query**.

  ![Schermafbeelding van Intune-groepseigenschappen](./media/groups-add-properties.png)

  In Azure AD kunt u dynamische groepen maken op basis van regels die het lidmaatschap definiëren. Lees hier meer over het [maken van dynamische groepen op basis van kenmerken](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Selecteer **Office-functies inschakelen** om leden van de gebruikersgroep toegang te geven tot gedeelde Office 365-apps. Meer informatie over [Office 365 Groepen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Kies **Maken** om de nieuwe groep toe te voegen.

## <a name="see-also"></a>Zie ook
- [Toegang tot resources beheren met Azure Active Directory-groepen](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klassieke Intune-groepen in Azure Portal](groups-get-started.md)
