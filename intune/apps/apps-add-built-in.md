---
title: Ingebouwde apps toevoegen op mobiele apparaten met Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u Intune kunt gebruiken om de installatie van ingebouwde apps op mobiele apparaten te vereenvoudigen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
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
ms.openlocfilehash: 96cd4997029c15396db91e9866bbb387c20f1044
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414448"
---
# <a name="add-built-in-apps-to-microsoft-intune"></a>Ingebouwde apps toevoegen aan Microsoft Intune

Met het *ingebouwde* app-type kunt u eenvoudig gecureerde beheerde apps zoals Office 365-apps toewijzen aan iOS-/iPadOS- en Android-apparaten. U kunt specifieke apps voor dit app-type, zoals Excel, OneDrive, Outlook, Skype en andere, toewijzen. Nadat u een app hebt toegevoegd, wordt het app-type weergegeven als *ingebouwde iOS-app* of *ingebouwde Android-app*. Met behulp van het ingebouwde app-type kunt u kiezen welke van deze apps u wilt publiceren naar gebruikers van apparaten.

In eerdere versies van de Intune-console heeft Intune verschillende standaard beheerde Office 365-apps opgegeven, zoals Outlook en OneDrive. De app-typen voor deze beheerde apps waren gelabeld als *Beheerde iOS Store-app* of *Beheerde Android-app*. In plaats van dat u deze app-typen gebruikt, raden we u aan dat u het ingebouwde app-type gebruikt. Door het ingebouwde app-type te gebruiken, hebt u meer flexibiliteit om Office 365-apps te bewerken en te verwijderen.

>[!NOTE]
>Office 365-standaardapps die als *Beheerde iOS Store-app* of *Beheerde Android-app* zijn gelabeld worden uit de app-lijst verwijderd zodra alle toewijzingen zijn verwijderd.

## <a name="add-a-built-in-app"></a>Ingebouwde app toevoegen

Voer de volgende stappen uit om een ingebouwde app toe te voegen aan uw beschikbare apps in Microsoft Intune:
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder de beschikbare typen **Store-app** de optie **Ingebouwde app**.
4. Klik op **Selecteren**. De stappen **App toevoegen** worden weergegeven.
5. Klik op de pagina **Ingebouwde apps selecteren** op **App selecteren** om de apps te selecteren die u wilt opnemen.
6. Selecteer de ingebouwde apps die u wilt opnemen. 
7. Nadat u de apps hebt geselecteerd, klikt u op **Selecteren** in het deelvenster **Ingebouwde apps selecteren**.
8. Klik op **Volgende** om de pagina **Bereiktags** weer te geven.
9. Klik op **Bereiktags selecteren** om desgewenst bereiktags toe te voegen voor de app. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT](~/fundamentals/scope-tags.md) voor meer informatie.
10. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.
11. Selecteer de groepstoewijzingen voor de app. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](~/fundamentals/groups-add.md) voor meer informatie. 
12. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven. Controleer de waarden en instellingen die u hebt ingevoerd voor de app.
13. Klik als u klaar bent op **Maken** om de app toe te voegen aan Intune.

    De blade **Overzicht** van de app die u hebt gemaakt, wordt weergegeven.

## <a name="configure-app-information"></a>App-gegevens configureren

U kunt informatie over de ingebouwde app aanpassen. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal.
1. Selecteer **Apps** > **Alle apps** en selecteer de ingebouwde app die u wilt aanpassen.  
   Er wordt een deelvenster voor de ingebouwde app weergegeven.
2. Selecteer **Eigenschappen**.
3. Selecteer **Bewerken** naast **App-gegevens**.
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
5. Klik op **Beoordelen en opslaan** om de pagina **Beoordelen en maken** weer te geven. Controleer de waarden en instellingen die u hebt ingevoerd voor de app.
13. Klik wanneer u klaar bent op **Opslaan** om de app in Intune bij te werken.

    De blade **Overzicht** van de app die u hebt gemaakt, wordt weergegeven.

## <a name="next-steps"></a>Volgende stappen

- U kunt de apps nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie.
