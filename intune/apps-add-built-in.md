---
title: Ingebouwde apps toevoegen op mobiele apparaten met Microsoft Intune
titlesuffix: 
description: Meer informatie over hoe u Intune kunt gebruiken om de installatie van ingebouwde apps op mobiele apparaten te vereenvoudigen.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ec8de66-5a0f-4c8d-afbf-c2becc7d6eec
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7d90f86babc2f73acd5ccd1b454c636c6d4f79b2
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-built-in-apps-to-microsoft-intune"></a>Ingebouwde apps toevoegen aan Microsoft Intune

Met het **ingebouwde** app-type kunt u eenvoudig gecureerde beheerde apps zoals Office 365-apps toewijzen aan iOS- en Android-apparaten. U kunt specifieke apps voor dit app-type, zoals Excel, OneDrive, Outlook, Skype en andere, toewijzen. Nadat u een app hebt toegevoegd, ziet u het app-type als **ingebouwde iOS-app** of **ingebouwde Android-app**. Met behulp van het ingebouwde app-type kunt u kiezen welke van deze specifieke apps u wilt publiceren naar gebruikers van apparaten.

 In eerdere versies van de Intune-console heeft Intune verschillende standaard beheerde Office 365-apps opgegeven, zoals Outlook en OneDrive. Het app-type voor deze beheerde apps was gelabeld als Beheerde iOS Store-app of Beheerde Android-app. We raden u aan om gebruik te maken van het ingebouwde app-type in plaats van Beheerde iOS Store-app of Beheerde Android-app. Het ingebouwde app-type biedt meer flexibiliteit om office 365-apps te bewerken en te verwijderen.

>[!NOTE]
>Office 365-standaardapps die als Beheerde iOS Store-app of Beheerde Android-app zijn gelabeld worden uit de app-lijst verwijderd zodra alle toewijzingen zijn verwijderd.

## <a name="add-built-in-app"></a>Ingebouwde app toevoegen

Als u de volgende stappen uitvoert, kunt u een ingebouwde app toevoegen aan uw beschikbare apps in Microsoft Intune.
1.  Meld u aan bij Azure-portal.
2.  Kies **Meer services** > **Controle en beheer** > **Intune** om de Microsoft Intune-blade weer te geven.
3.  Kies **Mobiele apps** op de blade **Intune**.
4.  Ga naar de blade **Mobiele apps** en kies **Apps** in de groep **Beheren**.
5.  Kies **Toevoegen** om een nieuwe app toe te voegen.
6.  Kies op de blade **App toevoegen** de optie **Ingebouwde app** in de lijst **App-type**.
7.  Klik op **App selecteren** om de ingebouwde apps te kiezen die u wilt opnemen.
8.  Selecteer op de blade Ingebouwde app de apps die u wilt opnemen.
9.  Klik op de blade **App toevoegen** op **Toevoegen** om de apps op te nemen.


## <a name="configure-app-information"></a>App-gegevens configureren

U kunt informatie over de ingebouwde app aanpassen. Aan de hand van deze informatie kunt u de app vinden in Intune en kunnen gebruikers de app vinden in de bedrijfsportal-app.
1.  Kies op de blade **Mobiele apps - Apps** de ingebouwde app die u wilt aanpassen. Er wordt een blade voor de ingebouwde app weergegeven.
2.  Selecteer de optie **Eigenschappen** van de groep **Beheren**.
3.  Selecteer de optie **Configureren** om de informatie over de ingebouwde app aan te passen.
4.  Op de blade **App-gegevens** kunt u de volgende informatie aanpassen:
    -   **Naam**: voer de naam van de ingebouwde app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    -   **Beschrijving**: voer een beschrijving in voor de app. 
    -   **Uitgever**: voer de naam van de uitgever of de app in.
    -   **Categorie**: (optioneel) selecteer een of meer van de ingebouwde app-categorieën. Als u deze optie instelt, kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    -   **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    -   **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    -   **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    -   **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    -   **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld HR-afdeling (optioneel).
    -   **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    -   **Pictogram uploaden**: dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3.  Wanneer u klaar bent, klikt u op **OK** op de blade **App-gegevens**.
4.  Klik op **Opslaan** op de blade **Eigenschappen**.

## <a name="next-steps"></a>Volgende stappen

- U kunt de apps nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.
