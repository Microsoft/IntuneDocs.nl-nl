---
title: Helpdesk voor portal voor probleemoplossing
titleSuffix: Intune on Azure
description: Medewerkers van de helpdesk gebruiken de Portal voor problemen oplossen voor het oplossen van technische problemen van gebruikers
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 08/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 32d3d014abc48eb2c3d0e10a71dc7f4616c49db8
ms.sourcegitcommit: af013af8d9a63c9aa16e5e9eddf38ad9c5a77898
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2017
---
# <a name="use-the-troubleshooting-portal-to-help-users"></a>Gebruikers helpen met behulp van de portal voor probleemoplossing

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De portal voor probleemoplossing biedt helpdeskmedewerkers en Intune-beheerders toegang tot gebruikersgegevens om te reageren op hulpaanvragen van gebruikers. Organisaties met helpdeskmedewerkers kunnen de rol **Helpdeskmedewerker** toewijzen aan een groep gebruikers, die vervolgens via de blade Probleem oplossen gebruikers kunnen helpen.

Als een gebruiker bijvoorbeeld contact opneemt met de ondersteuning vanwege een technisch probleem met Intune, voert de helpdeskmedewerker eerst de naam van de gebruiker in. Intune toont nuttige gegevens waarmee veel laag-1-problemen kunnen worden opgelost, waaronder:
- Gebruikersstatus
- Toewijzingen
- Fout bij installeren van app
- Problemen met naleving
- Apparaat reageert niet
-   Ophalen van VPN- of Wi-Fi-instellingen lukt niet apparaat
-   Fout tijdens installatie van app

## <a name="add-help-desk-operators"></a>Helpdeskmedewerkers toevoegen
Als Intune-beheerder kunt u de rol Helpdeskmedewerker toewijzen aan een gebruikersgroep. leden van die groep kunnen op de beheerportal problemen van gebruikers oplossen. Elke helpdeskmedewerker moet een licentie voor Intune hebben om toegang te krijgen tot de Intune-portal. Lees hier meer over het [toewijzen van Intune-licenties](licenses-assign.md).

Ga als volgt te werk als u helpdeskgebruikers wilt toevoegen:
1. [Voeg indien nodig gebruikers aan Intune toe](users-add.md).
2. [Maak een helpdeskgroep](groups-add.md) en voeg gebruikers aan de groep toe.
3. [Wijs de RBAC-rol Helpdeskmedewerker toe](role-based-access-control.md#built-in-roles).

  ![Schermafbeelding van de Intune-portal met de Intune-rollen gemarkeerd en een lijst van ingebouwde rollen, inclusief de rol Helpdeskmedewerker](./media/help-desk-user-add.png) U kunt ook een [aangepaste rol maken](role-based-access-control.md#custom-roles) die u verder kunt aanpassen om helpdeskmedewerkers toegang te geven.  Helpdeskmedewerkers moeten over de volgende machtigingen beschikken om gebruikers te ondersteunen bij probleemoplossing:
    - MobileApps: Lezen
    - ManagedApps: lezen
    - ManagedDevices: Lezen
    - Organisatie: Lezen
    - DeviceCompliancePolices: lezen
    - DeviceConfigurations: lezen

4. Als u helpdeskmedewerkers toestemming wilt geven de servicestatus te bekijken en ondersteuningstickets te openen voor Intune, [verleent u gebruikers beheerdersmachtigingen](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) op het niveau van een **servicebeheerder**. Verleen geen machtiging op het niveau van **Intune-servicebeheerder**, omdat deze directory-rol meer rechten heeft dan nodig is voor helpdeskmedewerkers.

## <a name="access-the-troubleshooting-portal"></a>Toegang tot de Portal voor problemen oplossen

Medewerkers van de helpdesk en Intune-beheerders hebben op twee manieren toegang tot de Portal voor problemen oplossen:
- Open [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in een webbrowser als u alleen de portal voor het oplossen van problemen wilt zien.
  ![Schermafbeelding van de console voor probleemoplossing](./media/help-desk-console.png)
- Meld u aan bij Azure Portal, kies **Meer services** > **Bewaking en beheer** > **Intune** en ga vervolgens naar **Help en ondersteuning** > **Problemen oplossen**.

Klik op **Gebruiker selecteren** om een gebruiker en de gegevens van die gebruiker te bekijken.

## <a name="use-the-troubleshooting-portal"></a>Toegang tot de Portal voor problemen oplossen

In de Portal voor problemen oplossen kunt u **Gebruiker selecteren** kiezen om gebruikersgegevens weer te geven. Met gebruikersgegevens kunt u inzicht krijgen in de huidige status van gebruikers en hun apparaten. In de portal voor probleemoplossing worden de volgende gegevens over het oplossen van problemen weergegeven:
- **Accountstatus**
- **Gebruikersstatus**
- **Apparaten** met apparaatacties
- **Groepslidmaatschap**
- **Beveiligingsstatus van de app**
