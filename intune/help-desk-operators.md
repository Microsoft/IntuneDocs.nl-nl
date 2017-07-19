---
title: Helpdesk voor portal voor probleemoplossing
titleSuffix: Intune on Azure
description: Medewerkers van de helpdesk gebruiken de Portal voor problemen oplossen voor het oplossen van technische problemen van gebruikers
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Gebruikers helpen met de Portal voor problemen oplossen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De Portal voor problemen oplossen biedt helpdeskmedewerkers en Intune-beheerders toegang tot gebruikersgegevens die van pas komen bij het oplossen van problemen van gebruikers. Organisaties met helpdeskmedewerkers kunnen de rol **Helpdeskmedewerker** toewijzen aan een groep gebruikers, die vervolgens via de blade Probleem oplossen gebruikers kunnen helpen.

Als een gebruiker bijvoorbeeld contact opneemt met de ondersteuning vanwege een technisch probleem met Intune, voert de helpdeskmedewerker eerst de naam van de gebruiker in. Vervolgens wordt er in Intune relevante informatie weergegeven die kan helpen bij veel eerstelijnsproblemen, zoals problemen met de gebruikersstatus, de installatie van apps of nalevingsproblemen. Voorbeelden van problemen die hier kunnen worden opgelost:
- Apparaat reageert niet
-   Ophalen van VPN- of Wi-Fi-instellingen lukt niet apparaat
-   Fout tijdens installatie van app


## <a name="add-help-desk-operators"></a>Helpdeskmedewerkers toevoegen
Een Intune-beheerder kan op twee manieren machtigingen voor helpdeskmedewerkers toewijzen aan gebruikers:
- De ingebouwde rol **Helpdeskmedewerker** toewijzen
- Een aangepaste rol maken en toewijzen

## <a name="assign-help-desk-operator-role"></a>De rol Helpdeskmedewerker toewijzen
Als Intune-beheerder kunt u de rol Helpdeskmedewerker toewijzen aan een gebruikersgroep. Leden van die groep kunnen de beheerportal gebruiken. Elke helpdeskmedewerker moet een licentie voor Intune hebben om toegang te krijgen tot de Intune-portal. Lees hier meer over het [toewijzen van Intune-licenties](licenses-assign.md).

1. Meld u als Intune-beheerder aan bij de Intune-portal en selecteer **Intune-rollen**.
2. Selecteer **Helpdeskmedewerker** > **Toewijzingen** op de blade **Intune-rollen** en selecteer vervolgens **Toewijzen**.
  ![Schermafbeelding van de Intune-portal met de optie Intune-rollen gemarkeerd en een lijst met ingebouwde rollen, waaronder Helpdeskmedewerker, met Toewijzingen gemarkeerd en een rood kader rond Toewijzen](./media/help-desk-user-assign.png)
3. Type een **Toewijzingsnaam** (vereist), een **Beschrijving van toewijzing** (optioneel) en wijs **Leden (groepen)** en **Bereik (groepen)** toe.
4. Leden van de rol Helpdeskmedewerker kunnen nu gebruikmaken van de Portal voor problemen oplossen.

Zie [Intune-rollen (RBAC)](role-based-access-control.md) voor meer informatie over Intune-rollen.

## <a name="create-a-custom-role-for-troubleshooting"></a>Een aangepaste rol maken voor het oplossen van problemen
Als Intune-beheerder kunt u een aangepaste rol maken waarmee gebruikers de Portal voor problemen oplossen kunnen gebruiken met machtigingen die aansluiten bij de behoeften van uw organisatie. Zie [Intune-rollen (RBAC)](role-based-access-control.md) voor meer informatie over Intune-rollen.

![Schermafbeelding van de Intune-portal met de optie Intune-rollen gemarkeerd en een lijst met ingebouwde rollen, waaronder Helpdeskmedewerker](./media/help-desk-user-add.png)

Om de Intune-console te gebruiken voor een helpdeskweergave, moet een aangepaste rol voor de helpdesk de volgende machtigingen hebben:
- MobileApps: Lezen
- ManagedApps: lezen
- ManagedDevices: Lezen
- Organisatie: Lezen

## <a name="access-the-troubleshooting-portal"></a>Toegang tot de Portal voor problemen oplossen

Medewerkers van de helpdesk en Intune-beheerders hebben op twee manieren toegang tot de Portal voor problemen oplossen:
- Open [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in een webbrowser.
- Ga in de Intune-portal naar **Help en ondersteuning** > **Probleemoplossing**.

![Schermafbeelding van de werkbelasting Problemen oplossen van Intune, met de koppeling Gebruiker selecteren](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Toegang tot de Portal voor problemen oplossen

In de Portal voor problemen oplossen kunt u **Gebruiker selecteren** kiezen om gebruikersgegevens weer te geven. Met gebruikersgegevens kunt u inzicht krijgen in de huidige status van gebruikers en hun apparaten. In de portal voor probleemoplossing worden de volgende gegevens over het oplossen van problemen weergegeven:
- **Tenantstatus**
- **Gebruikersstatus**
- **Apparaten** en apparaatacties
- **Groepslidmaatschap**
- **Beveiligingsstatus van de app**
