---
title: Apps implementeren
description: In dit onderwerp worden enkele concepten uitgelegd die u moet begrijpen voordat u apps met Intune gaat implementeren.
keywords: ''
author: mattbriggs
ms.author: mabrigg
manager: dougeby
ms.date: 12/27/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: dc2a8cb8fc07f87dd0a4e9d8f3935c04a73fe8fd
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="deploy-apps-with-microsoft-intune"></a>Apps implementeren met Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

In dit onderwerp worden enkele concepten uitgelegd die u moet begrijpen voordat u apps met Microsoft Intune gaat implementeren.


## <a name="app-deployment-actions"></a>Acties voor de implementatie van apps
Wanneer u apps implementeert, kunt u kiezen uit een van de volgende implementatieacties:

-   **Vereiste installatie**: de app wordt op het apparaat geïnstalleerd zonder dat tussenkomst van de gebruiker is vereist.

    > [!TIP]
    > Voor iOS-apparaten die zich niet in de modus Supervisie bevinden, en voor alle Android-apparaten, moet de gebruiker de aangeboden app accepteren voordat deze wordt geïnstalleerd.
    >
    >  Als een gebruiker een app verwijdert die u hebt geïmplementeerd als een vereiste installatie, wordt de app automatisch opnieuw geïnstalleerd door Intune na de volgende inventarisatiecyclus die meestal elke zeven dagen plaatsvindt.

-   **Beschikbare installatie**: de app wordt weergegeven in de bedrijfsportal en gebruikers kunnen de app op aanvraag installeren.

-   **Verwijderen** : de app wordt van het apparaat verwijderd.

-   **Niet van toepassing**: de app wordt niet weergegeven in de bedrijfsportal en wordt op geen enkel apparaat geïnstalleerd.

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a>Inzicht in welke implementatieacties beschikbaar zijn voor elk type installatieprogramma

|                         Type installatieprogramma                          | Vereiste installatie | Beschikbare installatie | Verwijderen | Niet van toepassing |
|-----------------------------------------------------------------|------------------|-------------------|-----------|----------------|
|         App-pakket voor Windows (geïmplementeerd op een gebruikersgroep)          |       Ja        |        Ja        |    Ja    |      Ja       |
|        App-pakket voor Windows (geïmplementeerd op een apparaatgroep)         |       Ja        |        Nee         |    Ja    |      Ja       |
|    App-pakket voor mobiele apparaten (geïmplementeerd op een gebruikersgroep)    |       Ja        |        Ja        |    Ja    |      Ja       |
|   App-pakket voor mobiele apparaten (geïmplementeerd op een apparaatgroep)   |       Ja        |        Nee         |    Ja    |      Ja       |
|          Windows Installer (geïmplementeerd op een gebruikersgroep)           |        Nee        |        Ja        |    Nee     |      Ja       |
|         Windows Installer (geïmplementeerd op een apparaatgroep)          |       Ja        |        Nee         |    Ja    |      Ja       |
|            Externe koppeling (geïmplementeerd op een gebruikersgroep)             |        Nee        |        Ja        |    Nee     |      Ja       |
|           Externe koppeling (geïmplementeerd op een apparaatgroep)            |        Nee        |        Nee         |    Nee     |       Nee       |
|  Beheerde iOS-app uit de App Store (geïmplementeerd op een gebruikersgroep)  |       Ja        |        Ja        |    Ja    |      Ja       |
| Beheerde iOS-app uit de App Store (geïmplementeerd op een apparaatgroep) |       Ja        |        Nee         |    Ja    |      Ja       |

> [!TIP]
> Wanneer u een app implementeert en zowel gebruikers- als apparaatgroepen selecteert, kunt u de app alleen als **Beschikbare installatie** implementeren.

## <a name="deployment-conflicts"></a>Implementatieconflicten
Wanneer twee implementaties met dezelfde implementatieactie worden ontvangen door een apparaat, gelden de volgende regels:

-   Implementaties op een apparaatgroep hebben prioriteit boven implementaties op een gebruikersgroep. Als een app echter op een gebruikersgroep wordt geïmplementeerd met de implementatieactie **Beschikbaar** en dezelfde app wordt ook op een apparaatgroep geïmplementeerd met de implementatieactie **Niet van toepassing**, wordt de app beschikbaar gesteld in de bedrijfsportal zodat gebruikers deze kunnen installeren.

-   Een installatieactie heeft prioriteit ten opzichte van een verwijderingsactie.

-   Als een apparaat zowel een vereiste installatie als een beschikbare installatie ontvangt, worden de acties gecombineerd. De gebruiker kan met andere woorden de beschikbare app via de bedrijfsportal installeren voordat de vereiste installatie begint.


## <a name="next-steps"></a>Volgende stappen

Lees hoe u [apps in Microsoft Intune implementeert](deploy-apps-in-microsoft-intune.md).
