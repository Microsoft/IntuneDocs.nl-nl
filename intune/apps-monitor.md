---
title: App-gegevens en -toewijzingen controleren
titleSuffix: Intune on Azure
description: Nadat u een app hebt toegewezen aan gebruikers of apparaten, gebruikt u deze informatie om de status van de toewijzing te controleren.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a558c7d7c804b62535b2223cde9c409c56f22f6
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/15/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>App-gegevens en -toewijzingen controleren met Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune biedt een aantal manieren om de eigenschappen en toewijzingsstatus te controleren van apps die u beheert.

1. Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
2. Kies op de blade met de lijst van apps de app waarvoor u informatie wilt weergegeven. Vervolgens ziet u de blade <*app-naam*> **Installatiestatus van het apparaat**: ![Blade Installatiestatus van de app.](./media/monitor-apps.png)

Neem vervolgens een van de volgende acties om meer over uw apps en hun toewijzingen te leren.

## <a name="general"></a>Algemeen

- **Overzicht**: biedt een eenvoudig overzicht van de app en informatie over de status van alle toewijzingen voor die app. U kunt een van de grafieken kiezen om de blade **Installatiestatus van het apparaat** of **Installatiestatus van de gebruiker** te openen voor gedetailleerde informatie.

## <a name="manage"></a>Manage

- **Eigenschappen**: hiermee kunt u de informatie over de geselecteerde app weergeven en wijzigen. Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over app-eigenschappen.
- **Toewijzingen**: bevat informatie over toewijzingen voor deze app. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie.

## <a name="monitor"></a>Monitor

- **Installatiestatus van het apparaat**: bevat gedetailleerde informatie voor elk apparaat waaraan u de geselecteerde app hebt toegewezen, inclusief de apparaatnaam, het besturingssysteem, wanneer het apparaat voor het laatst is ingecheckt bij Intune en de status van de app-installatie.
- **Installatiestatus van de gebruiker**: bevat gedetailleerde informatie over de gebruiker waaraan u de geselecteerde app hebt toegewezen, waaronder het aantal installaties van de apps die de gebruiker op alle apparaten heeft geïnstalleerd en informatie over eventuele installatiefouten.