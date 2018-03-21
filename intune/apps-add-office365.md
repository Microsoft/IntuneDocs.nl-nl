---
title: Office 365-apps installeren op apparaten met Microsoft Intune
titlesuffix: 
description: Meer informatie over hoe u Microsoft Intune kunt gebruiken om de installatie van Office 365-apps op Windows 10-apparaten te vereenvoudigen.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 076d228f3b18416e4ecb8fd1b3543a58d037e386
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Office 365-apps toewijzen aan Windows 10-apparaten met Microsoft Intune

Met dit type app kunt u eenvoudig Office 365-apps toewijzen aan de door u beheerde apparaten waarop Windows 10 wordt uitgevoerd. U kunt ook apps installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Pro voor Office 365, mits u daar licenties voor hebt. De gewenste apps worden als één vermelding weergegeven in de lijst met apps in de Intune-console.


## <a name="before-you-start"></a>Voordat u begint

>[!IMPORTANT]
>Deze methode voor het installeren van Office wordt alleen ondersteund als er geen andere Office-versies op het apparaat zijn geïnstalleerd.

- Op de apparaten waarop u deze apps implementeert, moet de Microsoft Windows 10-makersupdate of hoger zijn geïnstalleerd.
- Intune ondersteunt alleen het toevoegen van Office-apps uit Office 365-suite.
- Als er Office-apps zijn geopend wanneer Intune het app-pakket installeert, kan de installatie mogelijk mislukken en kunnen eindgebruikers mogelijk gegevens in niet-opgeslagen bestanden verliezen.
- Deze installatiemethode wordt niet ondersteund op apparaten met Windows 10S, Windows Home, Windows Team, Windows Holographic en Windows Holographic for Business.
- Intune biedt geen ondersteuning voor het installeren van Office 365-desktop-apps vanuit Microsoft Store (die ook wel bekend staan als Office Centennial-apps) op een apparaat waarop u al Office 365-apps met Intune hebt geïmplementeerd. Als u deze configuratie installeert, kan dit leiden tot gegevensverlies of -beschadiging.
- Meerdere vereiste of beschikbare app-toewijzingen tellen niet mee. Een latere app-toewijzing overschrijft reeds bestaande geïnstalleerde app-toewijzingen. Als de eerste set met Office-apps bijvoorbeeld Word bevat maar de laatste set niet, dan wordt Word verwijderd. Dit geldt niet voor Visio- of Project-toepassingen.


## <a name="get-started"></a>Aan de slag

1.  Meld u aan bij de [Azure-portal](https://portal.azure.com).
2.  Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3.  Kies **Mobiele apps** op de blade **Intune**.
4.  In de workload **Mobiele apps** kiest u **Apps** in het gedeelte **Beheren**.
5.  Kies **Toevoegen** boven de lijst met apps.
6.  Op de lijst **App-type** op de blade **Apps toevoegen** selecteert u **Windows 10** bij **Office 365-suite**.
    U kunt de app-suite nu configureren.

## <a name="configure-the-app-suite"></a>Het app-pakket configureren

In deze stap kiest u de Office-apps die u wilt toewijzen aan apparaten.

1.  Kies op de blade **App toevoegen** de optie **App-pakket configureren**.
2.  Kies op de blade **App-pakket configureren** de standaard Office-apps die u wilt toewijzen aan apparaten. Daarnaast kunt u apps installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Pro voor Office 365, mits u daar licenties voor hebt.
3.  Wanneer u klaar bent, klikt u op **OK**.

>[!IMPORTANT]
> Nadat u het app-pakket hebt gemaakt, kunt u de eigenschappen ervan niet meer bewerken. Als u andere eigenschappen wilt configureren, verwijdert u het app-pakket en maakt u een nieuw pakket.

## <a name="configure-app-information"></a>App-gegevens configureren

In deze stap moet u informatie opgeven over de app-suite. Aan de hand van deze informatie kunt u de app-suite vinden in Intune en kunnen gebruikers deze vinden in de bedrijfsportal-app.

1.  Kies op de blade **App toevoegen** de optie **Gegevens van app-pakket**.
2.  Voer de volgende gegevens in op de blade **Gegevens van app-pakket**:
    - **Pakketnaam**: voer de naam van het app-pakket in zoals die in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle pakketnamen die u gebruikt uniek zijn. Als dezelfde naam van een app-pakket twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving app-pakket**: voer een beschrijving in voor het app-pakket. Hier kunt u bijvoorbeeld de apps vermelden die in het pakket zijn opgenomen.
    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers het app-pakket gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt het app-pakket duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3.  Wanneer u klaar bent, klikt u op **OK**.

## <a name="configure-app-settings"></a>App-instellingen configureren

In deze stap configureert u de installatieopties voor het app-pakket. De instellingen gelden voor alle apps die u aan het pakket hebt toegevoegd.

1.  Kies op de blade **App toevoegen** de optie **Instellingen van app-pakket**.
2.  Voer de volgende gegevens in op de blade **Instellingen van app-pakket**:
    - **Office-versie**: kies of u de 32-bits of 64-bits versie van Office wilt toewijzen. U kunt de 32-bits versie op zowel 32-bits als 64-bits apparaten installeren, maar de 64-bits versie kan alleen worden geïnstalleerd op 64-bits apparaten.
    - **Updatekanaal**: kies hoe Office moet worden bijgewerkt op apparaten. Zie [Overzicht van updatekanalen voor Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) voor meer informatie over de verschillende updatekanalen. U kunt kiezen uit:
        - **Maandelijks**
        - **Maandelijks (gericht)**
        - **Halfjaarlijks**
        - **Halfjaarlijks (gericht)**
    - **Gebruiksrechtovereenkomst van de app automatisch accepteren**: selecteer deze optie als uw eindgebruikers de gebruiksrechtovereenkomst niet hoeven te accepteren. Intune accepteert de overeenkomst automatisch.
    - **Activering van gedeelde computers gebruiken**: activering van gedeelde computers wordt gebruikt wanneer meerdere gebruikers een computer delen. Zie Activering van gedeelde computers voor Office 365 voor meer informatie.
    - **Talen**: Office wordt automatisch geïnstalleerd in de ondersteunde talen die zijn geïnstalleerd met Windows op het apparaat van de eindgebruiker. Selecteer deze opties als u aanvullende talen wilt installeren met het app-pakket.

>[!IMPORTANT]
> Nadat u het app-pakket hebt gemaakt, kunt u de eigenschappen ervan niet meer bewerken. Als u andere eigenschappen wilt configureren, verwijdert u het app-pakket en maakt u een nieuw pakket.

## <a name="finish-up"></a>Voltooien

Wanneer u klaar bent, kiest u op de blade **Toevoegen** de optie **Toevoegen**. De app die u hebt gemaakt, wordt weergegeven in de lijst met apps.

## <a name="error-codes-when-installing-the-app-suite"></a>Foutcodes bij de installatie van het app-pakket

In de volgende tabel staan algemene foutcodes en de betekenis daarvan.

### <a name="status-for-office-csp"></a>Status voor Office CSP:

||||
|-|-|-|
|Status|Fase|Description|
|1460 (ERROR_TIMEOUT)|Download|Het downloaden van de Office Deployment Tool is mislukt|    
|13 (ERROR_INVALID_DATA)|-|De handtekening van de gedownloade Office Deployment Tool kan niet worden geverifieerd|
|Foutcode van CertVerifyCertificateChainPolicy|-|De certificeringscontrole van de gedownloade Office Deployment Tool is mislukt|    
|997|WIP|Wordt geïnstalleerd|
|0|Na de installatie|Installatie voltooid|    
|1603 (ERROR_INSTALL_FAILURE)|-|Een controle op vereisten is mislukt, zoals:<br>- SxS (Er is geprobeerd te installeren terwijl 2016 MSI is geïnstalleerd)<br>- versie komt niet overeen<br>- enzovoort.|     
|0x8000ffff (E_UNEXPECTED)|-|Er is geprobeerd te installeren zonder Office Klik-en-Klaar op de machine.|    
|17002|-|Het scenario (installatie) kan niet worden voltooid. Mogelijke oorzaken:<br>- Installatie geannuleerd door gebruiker<br>- Installatie geannuleerd door een andere installatie<br>- Geen schijfruimte meer tijdens installatie<br>- Onbekende taal-ID|
|17004|-|Onbekende SKU’s|   


### <a name="office-deployment-tool-error-codes"></a>Foutcodes Office Deployment Tool

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

- U kunt de apps nu toewijzen aan de groepen die u kiest. Zie [Apps toewijzen aan groepen](/intune-azure/manage-apps/deploy-apps).
