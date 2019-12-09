---
title: Ingebouwde apps toevoegen op mobiele apparaten met Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u Intune kunt gebruiken om de installatie van ingebouwde apps op mobiele apparaten te vereenvoudigen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a92699ccce4f0b2590e526b3442cd45bfda6407c
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563607"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Ingebouwde apps toevoegen aan Microsoft Intune

Met het *ingebouwde* app-type kunt u eenvoudig gecureerde beheerde apps zoals Office 365-apps toewijzen aan iOS- en Android-apparaten. U kunt specifieke apps voor dit app-type, zoals Excel, OneDrive, Outlook, Skype en andere, toewijzen. Nadat u een app hebt toegevoegd, wordt het app-type weergegeven als *ingebouwde iOS-app* of *ingebouwde Android-app*. Met behulp van het ingebouwde app-type kunt u kiezen welke van deze apps u wilt publiceren naar gebruikers van apparaten.

In eerdere versies van de Intune-console heeft Intune verschillende standaard beheerde Office 365-apps opgegeven, zoals Outlook en OneDrive. De app-typen voor deze beheerde apps waren gelabeld als *Beheerde iOS Store-app* of *Beheerde Android-app*. In plaats van dat u deze app-typen gebruikt, raden we u aan dat u het ingebouwde app-type gebruikt. Door het ingebouwde app-type te gebruiken, hebt u meer flexibiliteit om Office 365-apps te bewerken en te verwijderen.

>[!NOTE]
>Office 365-standaardapps die als *Beheerde iOS Store-app* of *Beheerde Android-app* zijn gelabeld worden uit de app-lijst verwijderd zodra alle toewijzingen zijn verwijderd.

## <a name="add-a-built-in-app"></a>Ingebouwde app toevoegen

Voer de volgende stappen uit om een ingebouwde app toe te voegen aan uw beschikbare apps in Microsoft Intune:
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. In het app-venster **Toevoegen** in de lijst **App-type** selecteert u **Ingebouwde app**.
4. Selecteer **App selecteren**.
5. In het deelvenster **Ingebouwde app** selecteert u de apps die u wilt opnemen.
6. Selecteer **Toevoegen** in het deelvenster **App toevoegen**.


## <a name="configure-app-information"></a>App-gegevens configureren

U kunt informatie over de ingebouwde app aanpassen. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal.
1. Selecteer **Apps** > **Alle apps** en selecteer de ingebouwde app die u wilt aanpassen.  
   Er wordt een deelvenster voor de ingebouwde app weergegeven.
2. Selecteer **Eigenschappen** > **Configureren**.
4. In het venster **App-gegevens** kunt u de volgende informatie aanpassen:
    - **Naam**: Voer de naam van de ingebouwde app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: Voer een beschrijving in voor de app. 
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **Categorie**: (optioneel) Selecteer een of meer van de ingebouwde app-categorieën. Als u deze optie instelt, kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Geef de app prominent weer op de hoofdpagina van de bedrijfsportal wanneer gebruikers door apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: Voer een naam in voor de eigenaar van deze app (bijvoorbeeld *HR-afdeling*) (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Het pictogram Uploaden**: Upload een pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
4. Selecteer **OK**.
5. In het venster **Eigenschappen** selecteert u **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

- U kunt de apps nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie.
