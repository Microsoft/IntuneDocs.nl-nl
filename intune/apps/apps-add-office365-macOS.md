---
title: Office 365 installeren op macOS-apparaten met Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u Microsoft Intune kunt gebruiken om Office 365-apps op macOS-apparaten te installeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cf4c2abb5506f297af8a4e77145abea5360381b
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755354"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Office 365 toewijzen aan macOS-apparaten met Microsoft Intune

Met dit type app kunt u Office 365 2016-apps eenvoudig toewijzen aan macOS-apparaten. Door dit type app te gebruiken, kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdate (MAU) om ervoor te zorgen dat de apps veiliger worden en up-to-date blijven. De apps die u wilt, worden als één app weergegeven in de lijst met apps in de Intune-console.


## <a name="before-you-start"></a>Voordat u begint

Voordat u Office 365 gaat toevoegen aan macOS-apparaten, moet u de volgende details begrijpen:

- Op de apparaten waarop u deze apps implementeert, moet macOS 10.10 of hoger zijn geïnstalleerd.
- Intune ondersteunt alleen het toevoegen van de Office-apps die in het Office 2016 voor Mac-pakket zijn opgenomen.
- Als er Office-apps zijn geopend wanneer Intune het app-pakket installeert, verliezen gebruikers mogelijk gegevens in niet-opgeslagen bestanden.

## <a name="select-the-office-365-suite-app-type"></a>Het app-type Office 365 Suite selecteren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer **macOS** in het gedeelte **Office 365 Suite** van het deelvenster **Een app-type selecteren**.
4. Klik op **Selecteren**. De stappen voor **Office 365 Suite toevoegen** worden weergegeven.

## <a name="step-1---app-suite-information"></a>Stap 1: Gegevens over de app-suite

In deze stap geeft u informatie op over het app-pakket. Aan de hand van deze informatie kunt u het app-pakket vinden in Intune en kunnen gebruikers het app-pakket vinden in de bedrijfsportal.

1. Op de pagina **Gegevens over de app-suite** kunt u de standaardwaarden bevestigen of wijzigen:
    - **Naam pakket**: voer de naam van het app-pakket in zoals deze wordt weergegeven in de bedrijfsportal. Zorg ervoor dat alle pakketnamen die u gebruikt, uniek zijn. Als dezelfde naam van een app-pakket twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving pakket**: voer een beschrijving in voor het app-pakket. Hier kunt u bijvoorbeeld de apps vermelden die in het pakket zijn opgenomen.
    - **Uitgever**: Microsoft wordt weergegeven als de uitgever.
    - **Categorie**: selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Met deze instellingen kunnen gebruikers het app-pakket gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om het app-pakket prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers naar apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Microsoft wordt weergegeven als de ontwikkelaar.
    - **Eigenaar**: Microsoft wordt weergegeven als de eigenaar.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: het Office 365-logo wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
2. Klik op **Volgende** om de pagina **Bereiktags** weer te geven.

## <a name="step-2---select-scope-tags-optional"></a>Stap 2: Bereiktags selecteren (optioneel)
U kunt bereiktags gebruiken om te bepalen wie er informatie over client-apps mag bekijken in Intune. Zie [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md) (Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT) voor uitgebreide informatie over bereiktags.

1. Klik op **Bereiktags selecteren** om desgewenst bereiktags toe te voegen voor de app-suite. 
2. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.

## <a name="step-3---assignments"></a>Stap 3: Toewijzingen

1. Selecteer de groepstoewijzingen **Vereist** of **Beschikbaar voor ingeschreven apparaten** voor de app-suite. Zie [Groepen toevoegen om gebruikers en apparaten in te delen](~/fundamentals/groups-add.md) en [Apps toewijzen aan groepen met Microsoft Intune](apps-deploy.md) voor meer informatie.

    >[!Note]
    > U kunt de Office 365 voor macOS-app-suite niet via Intune verwijderen.

2. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven. 

## <a name="step-4---review--create"></a>Stap 4: beoordelen en maken

1. Controleer de waarden en instellingen die u hebt ingevoerd voor de app-suite.
2. Klik als u klaar bent op **Maken** om de app toe te voegen aan Intune.

    De blade **Overzicht** van de Office 365 voor Window 10-app-suite die u hebt gemaakt, wordt weergegeven. Het pakket wordt in de lijst met apps als een afzonderlijk item weergegeven.

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps van Office 365 ProPlus 2016 toewijzen aan Windows 10-apparaten met Microsoft Intune](apps-add-office365.md) voor meer informatie over het toevoegen van Office 365-apps aan Windows 10-apparaten.
- Zie voor meer informatie over app-toewijzingen opnemen in of uitsluiten uit groepen gebruikers [App-toewijzingen opnemen en uitsluiten](apps-inc-exl-assignments.md).
