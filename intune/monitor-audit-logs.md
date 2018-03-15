---
title: Auditlogboeken voor Intune-activiteiten
description: Meer informatie over het bekijken van auditlogboeken waarin Intune-activiteiten worden opgenomen
keywords: 
author: dougeby
manager: dougeby
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 9f514e6d2dec268efe99f682bc3ef4e63ec53c02
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/23/2018
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
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Op de blade **Intune** kiest u de werkbelasting waarvoor u auditlogboeken wilt bekijken.
4. In de groep **Bewaking** voor de werkbelasting kiest u **Auditlogboeken**.

## <a name="review-audit-events"></a>Auditgebeurtenissen bekijken
![Auditlogboeken](./media/monitor-audit-logs.png "Auditlogboeken")

Een auditlogboek heeft een standaardlijstweergave waarin de volgende items worden weergegeven:    

- datum en tijd waarop de gebeurtenis is opgetreden
- Gestart door (actor)
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
Elke werkbelasting kent een menu-item dat vooraf de categorie filtert van auditgebeurtenissen die aan deze blade zijn gekoppeld. Met behulp van een afzonderlijke filteroptie kunt u overschakelen naar een andere categorie en naar details over gebeurtenisacties binnen die categorie. U kunt zoeken op UPN (zoals de gebruiker die de actie heeft uitgevoerd). Een filter voor datumbereik biedt opties voor 24 uur, 7 dagen of 30 dagen. Standaard worden de laatste 30 dagen aan auditgebeurtenissen weergegeven.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Graph API gebruiken om auditgebeurtenissen op te halen
Zie [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list) (Auditgebeurtenissen weergeven) voor meer informatie over het gebruik van de Graph API voor het ophalen van één jaar aan auditgebeurtenissen.