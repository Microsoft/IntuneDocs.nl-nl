---
title: Registratiebeperkingen instellen in Intune
titlesuffix: Azure portal
description: Beperk het registreren per platform en geef een registratielimiet voor apparaten op in Intune. "
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e55a96ee1bee5b1f25a4ddf3366f3e7dc94122a
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="add-groups-in-intune"></a>Groepen toevoegen in Intune
Intune maakt gebruik van Azure AD-groepen (Active Directory) voor het beheren van apparaten en gebruikers. Als beheerder van Intune kunt u groepen instellen die aansluiten bij de behoeften van uw organisatie. Maak groepen om gebruikers of apparaten in te delen op geografische locatie, afdeling of hardwarekenmerken. Gebruik groepen voor het beheren van taken op schaal. U kunt zo bijvoorbeeld beleidsregels instellen voor een groot aantal gebruikers tegelijk of apps implementeren op een reeks apparaten.

In dit onderwerp wordt uitgelegd hoe u groepen toevoegt voor gebruik in Intune.

U kunt de volgende typen groepen toevoegen:
- **Toegewezen groepen**: voeg handmatig gebruikers of apparaten toe aan een statische groep
- **Dynamische groepen**: (met Azure Active Directory Premium) hiermee kunt u dynamisch gebruikers- of apparaatgroepen maken aan de hand van eenvoudige of geavanceerde regels

## <a name="add-a-new-group"></a>Een nieuwe groep toevoegen

Volg de onderstaande stappen om een nieuwe groep te maken.
1. Ga in de Azure-portal naar **Groepen** en kies vervolgens **Nieuwe groep** op de blade **Alle groepen**.
  ![Schermafbeelding van de Azure-portal met de optie Nieuwe groep geselecteerd](./media/groups-add-new.png)
2. Geef waarden op voor **Naam** en **Beschrijving** voor de nieuwe groep. Deze eigenschappen worden alleen weergegeven in de beheerportal en zijn niet zichtbaar voor gebruikers.

3. Kies een waarde voor **Type lidmaatschap**:
  - **Toegewezen**: om een groep te maken met handmatig toegewezen leden. Lees hier meer over [toegewezen groepen van Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Dynamische gebruiker**: om een gebruikersgroep te maken op basis van een **dynamische query**.
  - **Dynamisch apparaat**: om een apparaatgroep te maken op basis van een **dynamische query**.

  ![Schermafbeelding van eigenschappen van een Intune-groep met de instellingen Naam, Beschrijving, Type lidmaatschap, Office-functies inschakelen en Leden](./media/groups-add-properties.png)

  In Azure AD kunt u dynamische groepen maken op basis van regels die het lidmaatschap definiëren. Lees hier meer over het [maken van dynamische groepen op basis van kenmerken](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Selecteer **Office-functies inschakelen** om leden van de gebruikersgroep toegang te geven tot gedeelde Office 365-apps. Meer informatie over [Office 365 Groepen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).
5. Kies **Maken** om de nieuwe groep toe te voegen.

## <a name="see-also"></a>Zie ook
- [Toegang tot resources beheren met Azure Active Directory-groepen](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Klassieke Intune-groepen in Azure Portal](groups-get-started.md)
