---
title: Ingebouwde apps toevoegen op mobiele apparaten met Microsoft Intune
titlesuffix: ''
description: Meer informatie over hoe u Intune kunt gebruiken om de installatie van ingebouwde apps op mobiele apparaten te vereenvoudigen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5b67b50a5bd372541cf0842696e5012ca991d8b8
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Ingebouwde apps toevoegen aan Microsoft Intune

Met het *ingebouwde* app-type kunt u eenvoudig gecureerde beheerde apps zoals Office 365-apps toewijzen aan iOS- en Android-apparaten. U kunt specifieke apps voor dit app-type, zoals Excel, OneDrive, Outlook, Skype en andere, toewijzen. Nadat u een app hebt toegevoegd, wordt het app-type weergegeven als *ingebouwde iOS-app* of *ingebouwde Android-app*. Met behulp van het ingebouwde app-type kunt u kiezen welke van deze apps u wilt publiceren naar gebruikers van apparaten.

In eerdere versies van de Intune-console heeft Intune verschillende standaard beheerde Office 365-apps opgegeven, zoals Outlook en OneDrive. De app-typen voor deze beheerde apps waren gelabeld als *Beheerde iOS Store-app* of *Beheerde Android-app*. In plaats van dat u deze app-typen gebruikt, raden we u aan dat u het ingebouwde app-type gebruikt. Door het ingebouwde app-type te gebruiken, hebt u meer flexibiliteit om Office 365-apps te bewerken en te verwijderen.

>[!NOTE]
>Office 365-standaardapps die als *Beheerde iOS Store-app* of *Beheerde Android-app* zijn gelabeld worden uit de app-lijst verwijderd zodra alle toewijzingen zijn verwijderd.

## <a name="add-a-built-in-app"></a>Ingebouwde app toevoegen

Voer de volgende stappen uit om een ingebouwde app toe te voegen aan uw beschikbare apps in Microsoft Intune:
1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Controle en beheer** > **Intune** om het deelvenster Microsoft Intune weer te geven.
3. Selecteer **Mobiele apps** in het deelvenster **Intune**.
4. In het venster **Mobiele apps**, onder **Beheren**, selecteert u **Apps**.
5. Selecteer **Toevoegen**.
6. In het app-venster **Toevoegen** in de lijst **App-type** selecteert u **Ingebouwde app**.
7. Selecteer **App selecteren**.
8. In het deelvenster **Ingebouwde app** selecteert u de apps die u wilt opnemen.
9. Selecteer **Toevoegen** in het deelvenster **App toevoegen**.


## <a name="configure-app-information"></a>App-gegevens configureren

U kunt informatie over de ingebouwde app aanpassen. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal.
1. Kies in het venster **Mobiele apps - Apps** de ingebouwde app die u wilt aanpassen.  
    Er wordt een deelvenster voor de ingebouwde app weergegeven.
2. Selecteer de optie **Eigenschappen** onder **Beheren**.
3. Selecteer de optie **Configureren** om de informatie over de ingebouwde app aan te passen.
4. In het venster **App-gegevens** kunt u de volgende informatie aanpassen:
    - **Naam**: voer de naam van de ingebouwde app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving in voor de app. 
    - **Uitgever**: voer de naam van de uitgever van de app in.
    - **Categorie**: (optioneel) selecteer een of meer van de ingebouwde app-categorieën. Als u deze optie instelt, kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld *HR-afdeling* (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Pictogram uploaden**: dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
4. Selecteer **OK**.
5. In het venster **Eigenschappen** selecteert u **Opslaan**.

## <a name="next-steps"></a>Volgende stappen

- U kunt de apps nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie.
