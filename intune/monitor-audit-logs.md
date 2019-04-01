---
title: Controle van wijzigingen en gebeurtenissen in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over het bekijken van auditlogboeken waarin Microsoft Intune-activiteiten worden opgenomen.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93072ba4730de0252f54d93fa1169062d496ce38
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394898"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Gebruik auditlogboeken volgen en controleren van gebeurtenissen in Microsoft Intune

Auditlogboeken bevatten een lijst met activiteiten die een wijziging in Microsoft Intune genereren. Maken, bijwerken (bewerken), verwijderen, toewijzen en externe acties maken controlegebeurtenissen die beheerders voor de meeste werkbelastingen van Intune kunnen bekijken. Standaard is controle ingeschakeld voor alle klanten. Het kan niet worden uitgeschakeld.

> [!NOTE]
> Gebeurtenissen voor beveiligingscontrole gestart opname in de functie-release van December 2017. Eerdere gebeurtenissen zijn niet beschikbaar.

## <a name="who-can-access-the-data"></a>Wie hebben er toegang tot de gegevens?

Gebruikers met de volgende machtigingen kunnen auditlogboeken bekijken:

- Hoofdbeheerder
- Intune-servicebeheerder
- Beheerders die zijn toegewezen aan een Intune-rol met **Auditgegevens** - **Lezen**-machtigingen

## <a name="audit-logs-for-intune-workloads"></a>Auditlogboeken voor Intune-werkbelastingen

U kunt auditlogboeken in de controlegroep voor elke Intune-workload bekijken:

1. Selecteer in [Azure Portal](https://portal.azure.com/) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Kiest u de werkbelasting die u wilt bekijken van auditlogboeken. Selecteer bijvoorbeeld **apparaten**.
3. Onder **bewaking**, kiest u **auditlogboeken**.

## <a name="route-logs-to-azure-monitor"></a>Logboeken routeren naar Azure Monitor

Operationele logboeken en auditlogboeken kunnen ook worden gerouteerd naar Azure Monitor. In **auditlogboeken**, selecteer **gegevensinstellingen exporteren**:

![Logboekgegevens exporteren naar Azure monitor door het selecteren van instellingen voor exporteren van gegevens in Intune](./media/audit-logs-export-data-settings.png)

Voor meer informatie over deze functie raadpleegt u [Logboekgegevens verzenden naar Storage, Event Hubs of Log Analytics in Intune](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Auditgebeurtenissen bekijken

![Kies auditlogboeken in Intune om te zien van acties en datums wanneer gebeurtenissen zich hebben voorgedaan](./media/monitor-audit-logs.png "auditlogboeken")

Een auditlogboek heeft een standaardlijstweergave waarin de volgende items worden weergegeven:

- Datum en tijd waarop de gebeurtenis is opgetreden
- Gestart door (actor)
- Toepassingsnaam
- Activiteit
- Doel(en)
- Categorie
- Status

Meer informatie over een gebeurtenis, selecteer een item in de lijst:

![Meer gedetailleerde informatie over wie deed wat in audit registreert in Intune](./media/monitor-audit-log-detail.png "details van het auditlogboek")

> [!NOTE]
> **Gestart door (actor)** bevat informatie over wie de taak is uitgevoerd en wanneer deze is uitgevoerd. Als u de activiteit bijvoorbeeld in Intune in de Azure-portal uitvoert, vermeldt **Toepassing** altijd **Uitbreiding voor Microsoft Intune-portal** en maakt de **Toepassings-id** altijd gebruik van dezelfde GUID.
> 
> In de sectie **Doel(en)** worden mogelijk meerdere doelen vermeld, samen met de eigenschappen die zijn gewijzigd.  

## <a name="filter-audit-events"></a>Auditgebeurtenissen filteren

Elke workload kent een menu-item dat vooraf op de categorie van auditgebeurtenissen filtert die aan het deelvenster is gekoppeld. Met behulp van een afzonderlijke filteroptie kunt u overschakelen naar een andere categorie en naar details over gebeurtenisacties binnen die categorie. U kunt zoeken op UPN, zoals de gebruiker die de actie heeft uitgevoerd. Een filter voor datumbereik biedt opties voor 24 uur, 7 dagen of 30 dagen. Standaard worden de laatste 30 dagen aan auditgebeurtenissen weergegeven.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Graph API gebruiken om auditgebeurtenissen op te halen

Zie voor meer informatie over het gebruik van de graph API om op te halen van één jaar aan auditgebeurtenissen [auditEvents lijst](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Volgende stappen

[Logboekgegevens verzenden naar eventhubs-opslag of meld u analytics](review-logs-using-azure-monitor.md).

[Logboeken voor beveiliging van de client-app controleren](app-protection-policy-settings-log.md).
