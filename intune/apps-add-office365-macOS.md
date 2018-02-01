---
title: Office 365 installeren op macOS-apparaten met Intune
titlesuffix: Azure portal
description: Meer informatie over hoe u Intune kunt gebruiken om de installatie van Office 365-apps op macOS-apparaten te vereenvoudigen.
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1573a6a2ca78489df46c9e08ebbfe9a16b0731c7
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Office 365 toewijzen aan macOS-apparaten met Microsoft Intune

Met dit type app kunt u Office 365-apps eenvoudig toewijzen aan macOS-apparaten. Met dit nieuwe type app kunt u Word, Excel, PowerPoint, Outlook en OneNote installeren. Deze apps worden ook geleverd met Microsoft AutoUpdate (MAU) om te zorgen dat de apps veiliger en up-to-date blijven. De gewenste apps worden als één app weergegeven in de lijst met apps in de Intune-console.


## <a name="before-you-start"></a>Voordat u begint

- Op de apparaten waarop u deze apps implementeert, moet macOS 10.10 of hoger zijn geïnstalleerd.
- Intune ondersteunt alleen het toevoegen van Office-apps die in het Office 2016 voor Mac-pakket zijn opgenomen.
- Als er Office-apps zijn geopend wanneer Intune het app-pakket installeert, verliezen eindgebruikers mogelijk gegevens in niet-opgeslagen bestanden.


## <a name="get-started"></a>Aan de slag
Office 365 toevoegen met de blade **Apps**.
1.  Meld u aan bij Azure-portal.
2.  Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3.  Kies **Mobiele apps** op de blade **Intune**.
4.  In de workload **Mobiele apps**kiest u **Apps** in de groep **Beheren**. Kies **Toevoegen**.
5.  Op de blade **App toevoegen** kiest u **Office 365** > **macOS**.
6.  Selecteer **Toevoegen**.

## <a name="configure-the-app-suite"></a>Het app-pakket configureren

Geef informatie op over het app-pakket. Aan de hand van deze informatie kunt u het pakket vinden in Intune en kunnen gebruikers het vinden in de bedrijfsportal-app.

1.  Kies op de blade **App toevoegen** de optie **Gegevens van app-pakket**.
2.  Verstrek de volgende informatie:
    - **Pakketnaam**: voer de naam van het app-pakket in zoals die in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle pakketnamen die u gebruikt uniek zijn. Als dezelfde naam van een app-pakket twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving app-pakket**: voer een beschrijving in voor het app-pakket.
    - **Uitgever**: Microsoft wordt weergegeven als de uitgever.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers het app-pakket gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt het app-pakket prominent weergegeven op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Microsoft wordt weergegeven als de ontwikkelaar.
    - **Eigenaar**: Microsoft wordt weergegeven als de eigenaar.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Pictogram uploaden**: dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3.  Selecteer **OK**. Het pakket wordt in de lijst met apps als een afzonderlijk item weergegeven.

## <a name="configure-app-assignments"></a>App-toewijzingen configureren

In deze stap configureert u de toewijzingen voor het app-pakket. Het daarvoor vereiste type app is binnenkort beschikbaar.

1.  Selecteer het app-pakket in de lijst met apps en selecteer **Toewijzingen**.
2.  Kies **Groepen selecteren**.
3.  Wijs het pakket toe aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](/intune/apps-deploy) voor meer informatie.
4.  Voor elke groep selecteert u **Installatie vereisen**.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Selecteer **Opslaan** om uw toewijzingen door te voeren.

## <a name="next-steps"></a>Volgende stappen

Zie [Apps van Office 365 ProPlus 2016 toewijzen aan Windows 10-apparaten met Microsoft Intune](/intune/apps-add-office365) voor meer informatie over het toevoegen van Office 365-apps aan een Windows 10-apparaat.
