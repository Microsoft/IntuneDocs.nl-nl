---
title: Office 365 installeren op macOS-apparaten met Microsoft Intune
titlesuffix: ''
description: Meer informatie over hoe u Microsoft Intune kunt gebruiken om Office 365-apps op macOS-apparaten te installeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f8b76de6e9b3a584be7ad324391c1c071140488e
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329441"
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
1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Controle en beheer** > **Intune**.
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloaddeelvenster **Client-apps** onder **Beheren** de optie **Apps**. 
5. Selecteer **Toevoegen**.
6. In de lijst **App-type** in de groep **Office 365-pakket** selecteert u **macOS**.
7. Selecteer **Informatie over app-pakket** voor informatie over het app-pakket.  
    Aan de hand van deze informatie kunt u het app-pakket vinden in Intune en kunnen gebruikers dit vinden in de bedrijfsportal.
8. Voer de volgende informatie in:
    - **Pakketnaam**: voer de naam van het app-pakket in zoals die in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle pakketnamen die u gebruikt, uniek zijn. Als dezelfde naam van een app-pakket twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving app-pakket**: voer een beschrijving in voor het app-pakket.
    - **Uitgever**: Microsoft wordt weergegeven als de uitgever.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met deze instellingen kunnen gebruikers het app-pakket gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: selecteer deze instelling om het app-pakket prominent weer te geven op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Microsoft wordt weergegeven als de ontwikkelaar.
    - **Eigenaar**: Microsoft wordt weergegeven als de eigenaar.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
    - **Logo**: het Office 365-logo wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
9. Selecteer **OK**.
10. Selecteer **Toevoegen** in het deelvenster **App toevoegen**.  
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
