---
title: Wijzigingen en gebeurtenissen in Microsoft Intune controleren - Azure | Microsoft Docs
description: Meer informatie over het bekijken van auditlogboeken waarin Microsoft Intune-activiteiten worden opgenomen.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d999603abc539fda4d152d15dd1ab965c465f39e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736296"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Gebruik auditlogboeken om gebeurtenissen in Microsoft Intune te volgen en te controleren

Auditlogboeken bevatten een lijst met activiteiten die een wijziging in Microsoft Intune genereren. De acties maken, bijwerken (bewerken), verwijderen, toewijzen en externe acties zorgen voor controlegebeurtenissen die beheerders voor de meeste werkbelastingen van Intune kunnen bekijken. Standaard is controle ingeschakeld voor alle klanten. De functie kan niet worden uitgeschakeld.

> [!NOTE]
> Het vastleggen van controlegebeurtenissen is gestart bij de functierelease van december 2017. Eerdere gebeurtenissen zijn niet beschikbaar.

## <a name="who-can-access-the-data"></a>Wie hebben er toegang tot de gegevens?

Gebruikers met de volgende machtigingen kunnen auditlogboeken bekijken:

- Hoofdbeheerder
- Intune-servicebeheerder
- Beheerders die zijn toegewezen aan een Intune-rol met **Auditgegevens** - **Lezen**-machtigingen

## <a name="audit-logs-for-intune-workloads"></a>Auditlogboeken voor Intune-werkbelastingen

U kunt auditlogboeken in de controlegroep voor elke Intune-workload bekijken:

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Kies de gewenste werkbelasting voor het bekijken van auditlogboeken. Selecteer bijvoorbeeld **Apparaten**.
3. Kies onder **Bewaking** **Auditlogboeken**.

## <a name="route-logs-to-azure-monitor"></a>Logboeken routeren naar Azure Monitor

Auditlogboeken en operationele logboeken kunnen ook naar Azure Monitor worden gerouteerd. Selecteer in **Auditlogboeken** **Gegevensinstellingen exporteren**:

![Logboekgegevens exporteren naar Azure Monitor door Gegevensinstellingen exporteren in Intune te selecteren](./media/monitor-audit-logs/audit-logs-export-data-settings.png)

Voor meer informatie over deze functie raadpleegt u [Logboekgegevens verzenden naar Storage, Event Hubs of Log Analytics in Intune](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Auditgebeurtenissen bekijken

![Kies auditlogboeken in Intune om acties en datums te zien bij het optreden van gebeurtenissen](./media/monitor-audit-logs/monitor-audit-logs.png "Auditlogboeken")

Een auditlogboek heeft een standaardlijstweergave waarin de volgende items worden weergegeven:

- Datum en tijd waarop de gebeurtenis is opgetreden
- Gestart door (actor)
- Toepassingsnaam
- Activiteit
- Doel(en)
- Categorie
- Status

Selecteer een item in de lijst als u meer informatie over een gebeurtenis wilt bekijken:

![Meer gedetailleerde informatie krijgen over wie wat deed in auditlogboeken in Intune](./media/monitor-audit-logs/monitor-audit-log-detail.png "Details van auditlogboeken")

> [!NOTE]
> **Gestart door (actor)** bevat informatie over wie de taak heeft uitgevoerd en waar deze is uitgevoerd. Als u de activiteit bijvoorbeeld in Intune in de Azure-portal uitvoert, vermeldt **Toepassing** altijd **Uitbreiding voor Microsoft Intune-portal** en maakt de **Toepassings-id** altijd gebruik van dezelfde GUID.
> 
> In de sectie **Doel(en)** worden mogelijk meerdere doelen vermeld, samen met de eigenschappen die zijn gewijzigd.  

## <a name="filter-audit-events"></a>Auditgebeurtenissen filteren

Elke workload kent een menu-item dat vooraf op de categorie van auditgebeurtenissen filtert die aan het deelvenster is gekoppeld. Met behulp van een afzonderlijke filteroptie kunt u overschakelen naar een andere categorie en naar details over gebeurtenisacties binnen die categorie. U kunt zoeken op UPN, zoals de gebruiker die de actie heeft uitgevoerd. Een filter voor datumbereik biedt opties voor 24 uur, 7 dagen of 30 dagen. Standaard worden de laatste 30 dagen aan auditgebeurtenissen weergegeven.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Graph API gebruiken om auditgebeurtenissen op te halen

Zie [List auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0) (Auditgebeurtenissen weergeven) voor meer informatie over het gebruik van de Graph API voor het ophalen van één jaar aan auditgebeurtenissen.

## <a name="next-steps"></a>Volgende stappen

[Logboekgegevens verzenden naar opslag, Event Hubs of Log Analytics](review-logs-using-azure-monitor.md).

[Logboeken voor beveiliging van de client-app controleren](../apps/app-protection-policy-settings-log.md).
