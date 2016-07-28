---
title: Apps implementeren | Microsoft Intune
description: In dit onderwerp worden enkele concepten uitgelegd die u moet begrijpen voordat u apps met Intune gaat implementeren.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 84f19cd198a2367abb0267071bd73ce8ac6d7d05


---

# Apps implementeren met Microsoft Intune

In dit onderwerp worden enkele concepten uitgelegd die u moet begrijpen voordat u apps met Microsoft Intune gaat implementeren.


## Acties voor de implementatie van apps
Wanneer u apps implementeert, kunt u kiezen uit een van de volgende implementatieacties:

-   **Vereiste installatie**: de app wordt op het apparaat geïnstalleerd zonder dat tussenkomst van de eindgebruiker is vereist.

    > [!TIP]
    > Voor iOS-apparaten die zich niet in de modus Supervisie bevinden, en voor alle Android-apparaten, moet de gebruiker de aangeboden app accepteren voordat deze wordt geïnstalleerd.
    > 
    >  Als een eindgebruiker een app verwijdert die u hebt geïmplementeerd als een vereiste installatie, wordt de app automatisch opnieuw geïnstalleerd door Intune na de volgende inventarisatiecyclus die meestal elke 7 dagen plaatsvindt.

-   **Beschikbare installatie**: de app wordt weergegeven in de bedrijfsportal en eindgebruikers kunnen de app op aanvraag installeren.

-   **Verwijderen** : de app wordt van het apparaat verwijderd.

-   **Niet van toepassing**: de app wordt niet weergegeven in de bedrijfsportal en wordt op geen enkel apparaat geïnstalleerd.

#### Inzicht in welke implementatieacties beschikbaar zijn voor elk type installatieprogramma

|Type installatieprogramma|Vereiste installatie|Beschikbare installatie|Verwijderen|Niet van toepassing|
|------------------|--------------------|---------------------|-------------|------------------|
|App-pakket voor Windows (geïmplementeerd op een gebruikersgroep)|Ja|Ja|Ja|Ja|
|App-pakket voor Windows (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
|App-pakket voor mobiele apparaten (geïmplementeerd op een gebruikersgroep)|Ja|Ja|Ja|Ja|
|App-pakket voor mobiele apparaten (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
|Windows Installer (geïmplementeerd op een gebruikersgroep)|Nee|Ja|Nee|Ja|
|Windows Installer (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
|Externe koppeling (geïmplementeerd op een gebruikersgroep)|Nee|Ja|Nee|Ja|
|Externe koppeling (geïmplementeerd op een apparaatgroep)|Nee|Nee|Nee|Nee|
|Beheerde iOS-app uit de App Store (geïmplementeerd op een gebruikersgroep)|Ja|Ja|Ja|Ja|
|Beheerde iOS-app uit de App Store (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
> [!TIP]
> Wanneer u een app implementeert en zowel gebruikers- als apparaatgroepen selecteert, kunt u de app alleen als **Beschikbare installatie** implementeren.

## Implementatieconflicten
Wanneer twee implementaties met dezelfde implementatieactie worden ontvangen door een apparaat, gelden de volgende regels:

-   Implementaties op een apparaatgroep hebben prioriteit boven implementaties op een gebruikersgroep. Als een app echter op een gebruikersgroep wordt geïmplementeerd met de implementatieactie **Beschikbaar** en dezelfde app wordt ook op een apparaatgroep geïmplementeerd met de implementatieactie **Niet van toepassing**, wordt de app beschikbaar gesteld in de bedrijfsportal zodat gebruikers deze kunnen installeren.

-   Een installatieactie heeft prioriteit ten opzichte van een verwijderingsactie.

-   Als zowel een vereiste als een beschikbare installatie worden ontvangen door een apparaat, worden de acties gecombineerd (de app is zowel vereist als beschikbaar, dus de eindgebruiker kan deze installeren vanaf de bedrijfsportal voordat er wordt gestart met de vereiste installatie).


## Volgende stappen

Lees hoe u [apps in Microsoft Intune implementeert](deploy-apps-in-microsoft-intune.md).



<!--HONumber=Jul16_HO3-->


