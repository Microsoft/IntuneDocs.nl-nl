---
title: Office 365 installeren op macOS-apparaten met Microsoft Intune
titlesuffix: 
description: Meer informatie over hoe u Microsoft Intune kunt gebruiken om Office 365-apps op macOS-apparaten te installeren.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8de14184c4d23adc79d5b519fdcf272f0d7f6804
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Office 365 toewijzen aan macOS-apparaten met Microsoft Intune

Met het type **Store app** kunt u Office 365-apps eenvoudig toewijzen aan macOS-apparaten. Met dit type app kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdate (MAU) om te zorgen dat de apps veiliger en up-to-date blijven. De gewenste apps worden als één app weergegeven in de lijst met apps in de Intune-console.


## <a name="before-you-start"></a>Voordat u begint

Voordat u Office 365 gaat toevoegen aan macOS-apparaten, moet u de volgende details begrijpen:

- Op de apparaten waarop u deze apps implementeert, moet macOS 10.10 of hoger zijn geïnstalleerd.
- Intune ondersteunt alleen het toevoegen van Office-apps die in het Office 2016 voor Mac-pakket zijn opgenomen.
- Als er Office-apps zijn geopend wanneer Intune het app-pakket installeert, verliezen eindgebruikers mogelijk gegevens in niet-opgeslagen bestanden.

## <a name="create-and-configure-the-app-suite"></a>Het app-pakket maken en configureren

Office 365 toevoegen met de blade **Apps**.
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Bewaking en beheer** > **Intune**.
3. Kies **Mobiele apps** in het deelvenster **Intune**.
4. In de workload **Mobiele apps**kiest u **Apps** in de sectie **Beheren**. 
5. Kies **Toevoegen** om het deelvenster **App toevoegen** weer te geven.
6. In de lijst **App-type** selecteert u **macOS** in de groep **Office 365-pakket**.
7. Selecteer **Informatie over app-pakket** om informatie over het app-pakket op te geven. Aan de hand van deze informatie kunt u het app-pakket vinden in Intune en kunnen gebruikers het vinden in de bedrijfsportal-app.
8.  Verstrek de volgende informatie:
    - **Pakketnaam**: voer de naam van het app-pakket in zoals die in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle pakketnamen die u gebruikt uniek zijn. Als dezelfde naam van een app-pakket twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving app-pakket**: voer een beschrijving in voor het app-pakket.
    - **Uitgever**: Microsoft wordt weergegeven als de uitgever.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met deze instellingen kunnen gebruikers het app-pakket gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: met deze instelling wordt het app-pakket prominent weergegeven op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL** (optioneel): voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL** (optioneel): voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Microsoft wordt weergegeven als de ontwikkelaar.
    - **Eigenaar**: Microsoft wordt weergegeven als de eigenaar.
    - **Opmerkingen** (optioneel): voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: het Office 365-logo wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
9.  Klik op **OK** in het deelvenster **App-gegevens**.
10. Klik op **Toevoegen** op de blade **App toevoegen**.
    Het pakket wordt in de lijst met apps als een afzonderlijk item weergegeven.

## <a name="configure-app-assignments"></a>App-toewijzingen configureren

In deze stap configureert u de toewijzingen voor het app-pakket. 

1. Selecteer het app-pakket **Office 365** in de lijst met apps om de overzichtsblade **Office 365** weer te geven.
2. Klik op **Toewijzingen** in de blade **Office 365**.
3. Klik op **Groep toevoegen** om een groep toe te voegen om het app-pakket te gebruiken. De blade **Groep toevoegen** wordt weergegeven.
3. Stel het **Toewijzingstype** in op **Vereist**.
4. Wijs het pakket toe aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor meer informatie.

    >[!Note]
    > Voor groepen waarvoor u het Office 365-app-pakket nodig hebt, kunt u het niet verwijderen via Microsoft Intune.

5. Selecteer **OK** op de blade **Toewijzen**.
6. Selecteer **OK** op de blade **Groep toevoegen**.
7. Selecteer **Opslaan** om uw toewijzingen door te voeren.

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps van Office 365 ProPlus 2016 toewijzen aan Windows 10-apparaten met Microsoft Intune](apps-add-office365.md) voor meer informatie over het toevoegen van Office 365-apps aan een Windows 10-apparaat.
- Zie voor meer informatie over het opnemen en uitsluiten van app-toewijzingen aan groepen gebruikers [App-toewijzingen opnemen en uitsluiten](apps-inc-exl-assignments.md).
