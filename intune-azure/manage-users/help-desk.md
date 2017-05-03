---
title: Portal voor problemen oplossen van helpdesk | Microsoft-documenten
titleSuffix: Intune Azure preview
description: Medewerkers van de helpdesk gebruiken de Portal voor problemen oplossen voor het oplossen van technische problemen van gebruikers
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e0ecc775f70703574c4e1adf0f0aa204f2745b72
ms.openlocfilehash: 723830f686991fe13de13f75c6a5d1bc84e6920b
ms.lasthandoff: 04/20/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Gebruikers helpen met de Portal voor problemen oplossen in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met de Portal voor problemen oplossen kunnen helpdeskmedewerkers en Intune-beheerders de gebruikers en hun apparaten weergeven en taken uitvoeren voor het oplossen van technische problemen met Intune.

## <a name="add-help-desk-operators"></a>Helpdeskmedewerkers toevoegen
Een Intune-beheerder kan machtigingen voor helpdeskmedewerkers toewijzen aan gebruikers. Helpdeskgebruikers kunnen vervolgens de Intune-portal weergeven, maar kunnen geen beheertaken buiten de werkbelasting voor probleemoplossing bekijken of uitvoeren.

1. Meld u aan bij [Azure Portal](https:portal.azure.com) als Intune-beheerder, selecteer **Meer services** > **Bewaking en Beheer** > **Intune**.
2. Selecteer **Intune-rollen** in de linkernavigatieblade.
3. Selecteer op de werkbelasting **Intune-rollen** het item **Helpdeskmedewerker** en selecteer vervolgens **Toewijzen**.
4. Type een **Toewijzingsnaam** (vereist), een **Beschrijving van toewijzing** (optioneel) en wijs **Leden (groepen)** en **Bereik (groepen)** toe.
5. Leden van de rol Helpdeskmedewerker kunnen nu gebruikmaken van de Portal voor problemen oplossen.

Zie [Intune-rollen (RBAC)](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) voor meer informatie over Intune-rollen.

## <a name="access-the-troubleshooting-portal"></a>Toegang tot de Portal voor problemen oplossen

Medewerkers van de helpdesk en Intune-beheerders hebben op twee manieren toegang tot de Portal voor problemen oplossen:
- Selecteer in [Azure Portal](https:portal.azure.com) het item **Meer Services** > **Bewaking en beheer** > **Intune** en selecteer vervolgens **Problemen oplossen** in de linkernavigatieblade. Andere werkbelastingen zijn zichtbaar in de linkernavigatieblade, maar zijn niet beschikbaar.
![Schermafbeelding van de werkbelasting Problemen oplossen van Intune, met de koppeling Gebruiker selecteren](media/help-desk-user.png)
- Open [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) in een webbrowser. Alleen de Portal voor problemen oplossen is zichtbaar.

## <a name="use-the-troubleshooting-portal"></a>Toegang tot de Portal voor problemen oplossen

In de Portal voor problemen oplossen kunt u **Gebruiker selecteren** kiezen om gebruikersgegevens weer te geven. Met gebruikersgegevens kunt u inzicht krijgen in de huidige status van gebruikers en hun apparaten. In de Portal voor problemen oplossen worden de volgende Intune-gegevens over gebruikers en apparaten weergegeven:
- Gegevens van gebruikersaccount
- Lidmaatschap gebruikersgroep
- Apparaatgegevens

Helpdeskgebruikers kunnen ook externe taken uitvoeren op apparaten zoals **Extern vergrendelen**.

