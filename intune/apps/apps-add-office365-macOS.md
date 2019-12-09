---
title: Office 365 installeren op macOS-apparaten met Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u Microsoft Intune kunt gebruiken om Office 365-apps op macOS-apparaten te installeren.
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
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 01ca17c9f8e3fd86e12f225621e6dc0e07bb4acb
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74564080"
---
# <a name="assign-office-365-to-macos-devices-with-microsoft-intune"></a>Office 365 toewijzen aan macOS-apparaten met Microsoft Intune

Met dit type app kunt u Office 365 2016-apps eenvoudig toewijzen aan macOS-apparaten. Door dit type app te gebruiken, kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdate (MAU) om ervoor te zorgen dat de apps veiliger worden en up-to-date blijven. De apps die u wilt, worden als één app weergegeven in de lijst met apps in de Intune-console.


## <a name="before-you-start"></a>Voordat u begint

Voordat u Office 365 gaat toevoegen aan macOS-apparaten, moet u de volgende details begrijpen:

- Op de apparaten waarop u deze apps implementeert, moet macOS 10.10 of hoger zijn geïnstalleerd.
- Intune ondersteunt alleen het toevoegen van de Office-apps die in het Office 2016 voor Mac-pakket zijn opgenomen.
- Als er Office-apps zijn geopend wanneer Intune het app-pakket installeert, verliezen gebruikers mogelijk gegevens in niet-opgeslagen bestanden.

## <a name="create-and-configure-the-app-suite"></a>Het app-pakket maken en configureren

Voeg Office 365 toe vanuit het deelvenster **Apps**.
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. In de lijst **App-type** in de groep **Office 365-pakket** selecteert u **macOS**.
4. Selecteer **Informatie over app-pakket** voor informatie over het app-pakket.  
    Aan de hand van deze informatie kunt u het app-pakket vinden in Intune en kunnen gebruikers dit vinden in de bedrijfsportal.
5. Voer de volgende informatie in:
    - **Naam pakket**: voer de naam van het app-pakket in zoals deze wordt weergegeven in de bedrijfsportal. Zorg ervoor dat alle pakketnamen die u gebruikt, uniek zijn. Als dezelfde naam van een app-pakket twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving pakket**: voer een beschrijving in voor het app-pakket.
    - **Uitgever**: Microsoft wordt weergegeven als de uitgever.
    - **Categorie**: Selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met deze instellingen kunnen gebruikers het app-pakket gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om het app-pakket prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers naar apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Microsoft wordt weergegeven als de ontwikkelaar.
    - **Eigenaar**: Microsoft wordt weergegeven als de eigenaar.
    - **Opmerkingen**: Voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
    - **Logo**: het Office 365-logo wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
6. Selecteer **OK**.
7. Selecteer **Toevoegen** in het deelvenster **App toevoegen**.  
    Het pakket wordt in de lijst met apps als een afzonderlijk item weergegeven.

## <a name="configure-app-assignments"></a>App-toewijzingen configureren

In deze stap configureert u de toewijzingen voor het app-pakket. 

1. Selecteer het app-pakket **Office 365** in de lijst met apps om het overzichtsdeelvenster **Office 365** weer te geven.
2. Selecteer in het deelvenster **Office 365** de optie **Toewijzingen**.
3. Selecteer **Groep toevoegen** om een groep toe te voegen die het app-pakket kan bekijken.  
    Het deelvenster **Groep toevoegen** wordt weergegeven.
4. Stel het **toewijzingstype** in op **Vereist** of **Beschikbaar**.
5. Wijs het pakket toe aan de groepen die u hebt geselecteerd. Zie [Apps aan groepen toewijzen met Microsoft Intune](apps-deploy.md) voor meer informatie.

    >[!Note]
    > U kunt het app-pakket Office 365 niet via Intune verwijderen.

5. Selecteer in het deelvenster **Toewijzen** **OK**.
6. Selecteer in het deelvenster **Groep toevoegen** **OK**.
7. Selecteer **Opslaan** om uw toewijzingen definitief te maken.

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps van Office 365 ProPlus 2016 toewijzen aan Windows 10-apparaten met Microsoft Intune](apps-add-office365.md) voor meer informatie over het toevoegen van Office 365-apps aan Windows 10-apparaten.
- Zie voor meer informatie over app-toewijzingen opnemen in of uitsluiten uit groepen gebruikers [App-toewijzingen opnemen en uitsluiten](apps-inc-exl-assignments.md).
