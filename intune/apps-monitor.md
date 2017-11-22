---
title: App-gegevens en -toewijzingen controleren
titlesuffix: Azure portal
description: Nadat u een app hebt toegewezen aan gebruikers of apparaten, gebruikt u deze informatie om de status van de toewijzing te controleren.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3736b6d43f5cd3b6c75097a2ceabebffd75f0caa
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>App-gegevens en -toewijzingen controleren met Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune biedt een aantal manieren om de eigenschappen en toewijzingsstatus te controleren van apps die u beheert.

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** + **Intune**.
3. Kies in de workload **Mobiele apps** **Apps** in de groep **Beheren**.
     
    ![Blade Installatiestatus van de app.](./media/monitor-apps.png)
5. Kies de gewenste app in de lijst van app-blades. U ziet dan de blade <*app-naam*> **Installatiestatus apparaat**.

Het rapport Installatiestatus apparaat bevat de volgende kolommen:

1.  **Apparaatnaam** De naam van het apparaattype.
2.  **Gebruikersnaam** De naam van de gebruiker.
3.   **Platform** Het op het apparaat geïnstalleerde besturingssysteem.
4.  **Versie** Het versienummer van de app.
5.   **Status** De mogelijke statussen van de apps zijn: **Geïnstalleerd**, **Niet geïnstalleerd**, **Wacht op installatie** en **Fout**.
6. **Statusdetails** Een leesbare beschrijving van de status van de app op het apparaat.
7. **Laatste check-in** Wanneer het apparaat voor het laatst heeft ingecheckt bij Intune.

Neem vervolgens een van de volgende acties om meer over uw apps en hun toewijzingen te leren.

## <a name="general"></a>Algemeen

- **Overzicht**: biedt een eenvoudig overzicht van de app en informatie over de status van alle toewijzingen voor die app. U kunt een van de grafieken kiezen om de blade **Installatiestatus van het apparaat** of **Installatiestatus van de gebruiker** te openen voor gedetailleerde informatie.

## <a name="manage"></a>Manage

- **Eigenschappen**: hiermee kunt u de informatie over de geselecteerde app weergeven en wijzigen. Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over app-eigenschappen.
- **Toewijzingen**: bevat informatie over toewijzingen voor deze app. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie.

## <a name="monitor"></a>Monitor

- **Installatiestatus van het apparaat**: bevat gedetailleerde informatie voor elk apparaat waaraan u de geselecteerde app hebt toegewezen, inclusief de apparaatnaam, het besturingssysteem, wanneer het apparaat voor het laatst is ingecheckt bij Intune en de status van de app-installatie.
- **Installatiestatus van de gebruiker**: bevat gedetailleerde informatie over de gebruiker waaraan u de geselecteerde app hebt toegewezen, waaronder het aantal installaties van de app die de gebruiker op alle apparaten heeft geïnstalleerd en informatie over eventuele installatiefouten.