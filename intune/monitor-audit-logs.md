---
title: Auditlogboeken voor Microsoft Intune-activiteiten
description: Meer informatie over het bekijken van auditlogboeken waarin Microsoft Intune-activiteiten worden opgenomen.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: c7c8b860be9722138f8bd804a66131328b592022
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2018
ms.locfileid: "29962443"
---
# <a name="audit-logs-for-intune-activities"></a>Auditlogboeken voor Intune-activiteiten
Auditlogboeken bevatten een lijst met activiteiten die een wijziging in Microsoft Intune genereren. U kunt acties of externe taken maken, bijwerken (bewerken), verwijderen en toewijzen en controlegebeurtenissen genereren die u kunt bekijken. U kunt auditlogboeken voor de meeste werkbelastingen van Intune bekijken. Controles worden standaard ingeschakeld voor alle klanten. Dit kan niet worden uitgeschakeld. Controlegebeurtenissen worden vastgelegd sinds de versie die in december 2017 beschikbaar is gemaakt; eerdere gebeurtenissen zijn niet beschikbaar.

## <a name="who-can-access-the-data"></a>Wie hebben er toegang tot de gegevens?
Gebruikers met de volgende machtigingen kunnen auditlogboeken bekijken:
- Hoofdbeheerder
- Intune-servicebeheerder
- Beheerders die zijn toegewezen aan een Intune-rol met **Auditgegevens** - **Lezen**-machtigingen

## <a name="audit-logs-for-intune-workloads"></a>Auditlogboeken voor Intune-werkbelastingen
U kunt auditlogboeken in de controlegroep voor elke werkbelasting van Intune bekijken.  
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. In het deelvenster **Intune** kiest u de werkbelasting waarvoor u auditlogboeken wilt bekijken. Dit kan bijvoorbeeld **Apparaten** zijn.
4. In de groep **Bewaking** voor de werkbelasting kiest u **Auditlogboeken**.

## <a name="review-audit-events"></a>Auditgebeurtenissen bekijken
![Auditlogboeken](./media/monitor-audit-logs.png "Auditlogboeken")

Een auditlogboek heeft een standaardlijstweergave waarin de volgende items worden weergegeven:    

- datum en tijd waarop de gebeurtenis is opgetreden
- Gestart door (actor)
- Toepassingsnaam
- Activiteit
- Doel(en)
- Categorie
- Status

Door te klikken op een item in de lijstweergave, krijgt u alle beschikbare details van het item te zien.

![Auditlogboeken](./media/monitor-audit-log-detail.png "Auditlogboeken")

> [!Note]    
> De sectie **Gestart door (actor)** in de details van het auditlogboek bevat informatie over wie de activiteit heeft uitgevoerd en waarvandaan dit gebeurde. Als u de activiteit bijvoorbeeld in Intune in Azure Portal uitvoert, vermeldt **Toepassing** altijd **Uitbreiding voor Microsoft Intune-portal** en maakt de **Toepassings-id** altijd gebruik van dezelfde GUID. 
>    
> In de sectie **Doel(en)** kunnen meerdere doelen worden vermeld, samen met de eigenschappen die zijn gewijzigd.  


## <a name="filter-audit-events"></a>Auditgebeurtenissen filteren
Elke workload kent een menu-item dat vooraf op de categorie van auditgebeurtenissen filtert die aan het deelvenster is gekoppeld. Met behulp van een afzonderlijke filteroptie kunt u overschakelen naar een andere categorie en naar details over gebeurtenisacties binnen die categorie. U kunt zoeken op UPN (zoals de gebruiker die de actie heeft uitgevoerd). Een filter voor datumbereik biedt opties voor 24 uur, 7 dagen of 30 dagen. Standaard worden de laatste 30 dagen aan auditgebeurtenissen weergegeven.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Graph API gebruiken om auditgebeurtenissen op te halen
Zie [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list) (Auditgebeurtenissen weergeven) voor meer informatie over het gebruik van de Graph API voor het ophalen van één jaar aan auditgebeurtenissen.