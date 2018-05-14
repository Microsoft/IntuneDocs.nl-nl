---
title: Office 365-apps installeren op apparaten met Microsoft Intune
titlesuffix: ''
description: Meer informatie over hoe u Microsoft Intune kunt gebruiken om de installatie van Office 365-apps op Windows 10-apparaten te vereenvoudigen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da02a71d3801d0e00362617dd5d0cc76ffdd4722
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2018
---
# <a name="assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune

Met dit type app kunt u eenvoudig Office 365-apps toewijzen aan de door u beheerde apparaten waarop Windows 10 wordt uitgevoerd. U kunt ook apps installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Pro voor Office 365, mits u daar licenties voor hebt. De apps die u wilt, worden als één vermelding weergegeven in de lijst met apps in de Intune-console.


## <a name="before-you-start"></a>Voordat u begint

>[!IMPORTANT]
>Deze methode voor het installeren van Office wordt alleen ondersteund als er geen andere Microsoft Office-versies op het apparaat zijn geïnstalleerd.

- Op de apparaten waarop u deze apps implementeert, moet de Microsoft Windows 10-makersupdate of hoger zijn geïnstalleerd.
- Intune biedt alleen ondersteuning voor het toevoegen van Office-apps uit de Office 365-suite.
- Als er Office-apps zijn geopend wanneer het app-pakket wordt geïnstalleerd met Intune, kan de installatie mislukken en kunnen gebruikers gegevens in niet-opgeslagen bestanden verliezen.
- Deze installatiemethode wordt niet ondersteund op apparaten met Windows 10 S, Windows Home, Windows Team, Windows Holographic of Windows Holographic for Business.
- Intune biedt geen ondersteuning voor het installeren van Office 365-desktop-apps vanuit Microsoft Store (die ook wel bekend staan als Office Centennial-apps) op een apparaat waarop u al Office 365-apps met Intune hebt geïmplementeerd. Als u deze configuratie installeert, kan dit leiden tot gegevensverlies of -beschadiging.
- Meerdere vereiste of beschikbare app-toewijzingen tellen niet mee. Een latere app-toewijzing overschrijft reeds bestaande geïnstalleerde app-toewijzingen. Als de eerste set met Office-apps bijvoorbeeld Word bevat maar de laatste set niet, wordt Word verwijderd. Deze voorwaarde geldt niet voor Visio- of Project-toepassingen.


## <a name="get-started"></a>Aan de slag

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Mobiele apps** in het deelvenster **Intune**.
4. Selecteer **Apps** in het werkbelastingvenster **Mobiele apps** onder **Beheren**.
5. Selecteer **Toevoegen**.
6. Selecteer **Windows 10** in het deelvenster **Apps toevoegen**, in de lijst **App-type** onder **Office 365**.

U kunt de app-suite nu configureren.

## <a name="configure-the-app-suite"></a>Het app-pakket configureren

Selecteer de Office-apps die u wilt toewijzen aan apparaten.

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakket configureren**.
2. Kies in het deelvenster **App-pakket configureren** de standaard-apps van Office die u wilt toewijzen aan apparaten.  
    Daarnaast kunt u apps installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Pro voor Office 365, mits u daar licenties voor hebt.
3. Selecteer **OK**.

>[!IMPORTANT]
> Nadat u het app-pakket hebt gemaakt, kunt u de eigenschappen ervan niet meer bewerken. Als u andere eigenschappen wilt configureren, verwijdert u het app-pakket en maakt u een nieuw pakket.

## <a name="configure-app-information"></a>App-gegevens configureren

In deze stap geeft u informatie op over het app-pakket. Aan de hand van deze informatie kunt u het app-pakket vinden in Intune en kunnen gebruikers het app-pakket vinden in de bedrijfsportal.

1. Selecteer **App-pakketgegevens** in het deelvenster **App toevoegen**.
2. Voer in het deelvenster **App-pakketgegevens** het volgende uit:
    - **Pakketnaam**: voer de naam van het app-pakket in zoals deze wordt weergegeven in de bedrijfsportal. Zorg ervoor dat alle pakketnamen die u gebruikt, uniek zijn. Als dezelfde naam van een app-pakket twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving app-pakket**: voer een beschrijving in voor het app-pakket. Hier kunt u bijvoorbeeld de apps vermelden die in het pakket zijn opgenomen.
    - **Uitgever**: voer de naam van de uitgever van de app in.
    - **Categorie**: selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Met deze instellingen kunnen gebruikers het app-pakket gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: selecteer deze instelling om het app-pakket prominent weer te geven op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld *HR-afdeling* (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Selecteer **OK**.

## <a name="configure-app-settings"></a>App-instellingen configureren

In deze stap configureert u de installatieopties voor het app-pakket. De instellingen gelden voor alle apps die u aan het pakket hebt toegevoegd.

1. Selecteer in het deelvenster **App toevoegen** de optie **Instellingen voor app-pakket**.
2. Voer in het deelvenster **Instellingen voor app-pakket** het volgende uit:
    - **Office-versie**: kies of u de 32-bits of 64-bits versie van Office wilt toewijzen. U kunt de 32-bits versie op zowel 32-bits als 64-bits apparaten installeren, maar de 64-bits versie kan alleen worden geïnstalleerd op 64-bits apparaten.
    - **Updatekanaal**: kies hoe Office moet worden bijgewerkt op apparaten. Zie [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) (Overzicht van updatekanalen voor Office 365 ProPlus) voor meer informatie over de verschillende updatekanalen. U kunt kiezen uit:
        - **Maandelijks**
        - **Maandelijks (gericht)**
        - **Halfjaarlijks**
        - **Halfjaarlijks (gericht)**
    - **Gebruiksrechtovereenkomst van de app automatisch accepteren**: selecteer deze optie als eindgebruikers de gebruiksrechtovereenkomst niet hoeven te accepteren. Intune accepteert de overeenkomst automatisch.
    - **Activering van gedeelde computers gebruiken**: selecteer deze optie wanneer meerdere gebruikers een computer delen. Zie Activering van gedeelde computers voor Office 365 voor meer informatie.
    - **Talen**: Office wordt automatisch geïnstalleerd in de ondersteunde talen die met Windows zijn geïnstalleerd op het apparaat van de eindgebruiker. Selecteer deze opties als u aanvullende talen wilt installeren met het app-pakket.

>[!IMPORTANT]
> Nadat u het app-pakket hebt gemaakt, kunt u de eigenschappen ervan niet meer bewerken. Als u andere eigenschappen wilt configureren, verwijdert u het app-pakket en maakt u een nieuw pakket.

## <a name="finish-up"></a>Voltooien

Als u klaar bent, selecteert u **Toevoegen** in het deelvenster **App toevoegen**. De app die u hebt gemaakt, wordt weergegeven in de lijst met apps.

## <a name="errors-during-installation-of-the-app-suite"></a>Fouten tijdens de installatie van het app-pakket

In de volgende tabellen worden algemene foutcodes en hun betekenis weergegeven.

### <a name="status-for-office-csp"></a>Status voor Office CSP

||||
|-|-|-|
|Status|Fase|Description|
|1460 (ERROR_TIMEOUT)|Download|Het downloaden van de Office Deployment Tool is mislukt|    
|13 (ERROR_INVALID_DATA)|-|De handtekening van de gedownloade Office Deployment Tool kan niet worden geverifieerd|
|Foutcode van CertVerifyCertificateChainPolicy|-|De certificeringscontrole van de gedownloade Office Deployment Tool is mislukt|    
|997|WIP|Wordt geïnstalleerd|
|0|Na de installatie|Installatie voltooid|    
|1603 (ERROR_INSTALL_FAILURE)|-|Een controle op vereisten is mislukt, zoals:<ul><li>SxS (Er is geprobeerd te installeren terwijl 2016 MSI is geïnstalleerd)</li><li>Versie komt niet overeen</li><li>Overige</li></ul>|  
|0x8000ffff (E_UNEXPECTED)|-|Er is geprobeerd te verwijderen zonder Office Klik-en-Klaar op de machine|     
|17002|-|Het scenario (installatie) kan niet worden voltooid. Mogelijke oorzaken:<ul><li>Installatie is geannuleerd door gebruiker</li><li>Installatie is geannuleerd vanwege een andere installatie</li><li>Geen schijfruimte meer tijdens installatie</li><li>Onbekende taal-id</li></ul>|
|17004|-|Onbekende SKU's|   


### <a name="office-deployment-tool-error-codes"></a>Office Deployment Tool-foutcodes

|||||
|-|-|-|-|
|Scenario|Retourcode|Gebruikersinterface|Opmerking|
|Er is geprobeerd de installatie te verwijderen zonder actieve Klik-en-Klaar-installatie|-2147418113, 0x8000ffff of 2147549183|Foutcode: 30088-1008<br>Foutcode: 30125-1011 (404)|Office Deployment Tool|
|Installeren terwijl de MSI-versie is geïnstalleerd|1603|-|Office Deployment Tool|
|De installatie is geannuleerd door de gebruiker of door een andere installatie|17002|-|Klik-en-Klaar|
|Er is geprobeerd een 64-bits versie te installeren op een apparaat waarop de 32-bits versie is geïnstalleerd.|1603|-|Retourcodes Office Deployment Tool|
|Er is geprobeerd een onbekende SKU te installeren (dit is geen geldige use case voor Office CSP omdat er alleen geldige SKU’s mogen worden doorgegeven)|17004|-|Klik-en-Klaar|
|Gebrek aan ruimte|17002|-|Klik-en-Klaar|
|De Klik-en-Klaar-client kan niet worden gestart (onverwacht)|17000|-|Klik-en-Klaar|
|De Klik-en-Klaar-client kan het scenario niet in de wachtrij zetten (onverwacht)|17001|-|Klik-en-Klaar|

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps toewijzen aan groepen](/intune-azure/manage-apps/deploy-apps) om de apps toe te wijzen aan de groepen van uw keuze.
