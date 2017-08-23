---
title: Office 365 ProPlus-app installeren op Windows 10-apparaten met Intune
titleSuffix: Intune on Azure
description: Meer informatie over hoe u Intune kunt gebruiken om de installatie van Office 365-apps op Windows 10-apparaten te vereenvoudigen.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 471b4dd524cea553af89acc3e158fd2a05cebe3d
ms.sourcegitcommit: c8fb42fcb8735af432c7e07c380d956171012bd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2017
---
# <a name="how-to-assign-office-365-proplus-2016-apps-to-windows-10-devices-with-microsoft-intune"></a>Office 365 ProPlus 2016-apps toewijzen aan Windows 10-apparaten met Microsoft Intune

Met dit type app kunt u eenvoudig Office 365 ProPlus 2016-apps toewijzen aan de door u beheerde apparaten waarop Windows 10 wordt uitgevoerd. U kunt ook apps installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Pro voor Office 365, mits u daar licenties voor hebt. De gewenste apps worden als één app weergegeven in de lijst met apps in de Intune-console.


## <a name="before-you-start"></a>Voordat u begint

>[!IMPORTANT]
>Deze methode voor het installeren van Office wordt alleen ondersteund als er geen andere Office-versies op het apparaat zijn geïnstalleerd.

- Op de apparaten waarop u deze apps implementeert, moet de Microsoft Windows 10-makersupdate of hoger zijn geïnstalleerd.
- Intune ondersteunt alleen het toevoegen van Office-apps uit Office 365 ProPlus 2016.
- Als er Office-apps zijn geopend wanneer Intune het app-pakket installeert, verliezen eindgebruikers mogelijk gegevens in niet-opgeslagen bestanden.
- Deze installatiemethode wordt niet in Windows 10S-apparaten ondersteund.
- Intune biedt geen ondersteuning voor het installeren van Office 365-bureaublad-apps vanuit Windows Store (bekend als Centennial Office-apps) op een apparaat waarop u al Office 365-apps met Intune hebt geïmplementeerd. Als u deze configuratie installeert, kan dit leiden tot gegevensverlies of -beschadiging.


## <a name="get-started"></a>Aan de slag

1.  Meld u aan bij Azure Portal.
2.  Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3.  Kies **Mobiele apps** op de blade **Intune**.
4.  Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
5.  Kies **Toevoegen** boven de lijst met apps.
6.  Kies op de blade **App toevoegen** de optie **Office 365 ProPlus-pakket (Windows 10)**.

## <a name="configure-the-app-suite"></a>Het app-pakket configureren

In deze stap kiest u de Office-apps die u wilt toewijzen aan apparaten.

1.  Kies op de blade **App toevoegen** de optie **App-pakket configureren**.
2.  Kies op de blade **App-pakket configureren** de standaard Office-apps die u wilt toewijzen aan apparaten. Daarnaast kunt u apps installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Pro voor Office 365, mits u daar licenties voor hebt.
3.  Wanneer u klaar bent, klikt u op **OK**.

>[!IMPORTANT]
> Nadat u het app-pakket hebt gemaakt, kunt u de eigenschappen ervan niet meer bewerken. Als u andere eigenschappen wilt configureren, verwijdert u het app-pakket en maakt u een nieuw pakket.

## <a name="configure-app-information"></a>App-gegevens configureren

In deze stap geeft u informatie op over het app-pakket. Aan de hand van deze informatie kunt u het pakket vinden in de Intune-console en kunnen eindgebruikers het vinden in de bedrijfsportal-app.

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
    - **Pictogram uploaden**: dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3.  Wanneer u klaar bent, klikt u op **OK**.

## <a name="configure-app-settings"></a>App-instellingen configureren

In deze stap configureert u de installatieopties voor het app-pakket. De instellingen gelden voor alle apps die u aan het pakket hebt toegevoegd.

1.  Kies op de blade **App toevoegen** de optie **Instellingen van app-pakket**.
2.  Voer de volgende gegevens in op de blade **Instellingen van app-pakket**: 
    - **Office-versie**: kies of u de 32-bits of 64-bits versie van Office wilt toewijzen. U kunt de 32-bits versie op zowel 32-bits als 64-bits apparaten installeren, maar de 64-bits versie kan alleen worden geïnstalleerd op 64-bits apparaten.
    - **Updatekanaal**: kies hoe Office moet worden bijgewerkt op apparaten. Zie Overzicht van updatekanalen voor Office 365 ProPlus voor meer informatie over de verschillende updatekanalen. U kunt kiezen uit: 
        - **Current**
        - **Deferred**
        - **Eerste versie van Current**
        - **Eerste versie van Deferred**
    - **Gebruiksrechtovereenkomst van de app automatisch accepteren**: selecteer deze optie als uw eindgebruikers de gebruiksrechtovereenkomst niet hoeven te accepteren. Intune accepteert de overeenkomst automatisch.
    - **Activering van gedeelde computers gebruiken**: activering van gedeelde computers wordt gebruikt wanneer meerdere gebruikers een computer delen. Zie Activering van gedeelde computers voor Office 365 ProPlus voor meer informatie.
    - **Talen**: Office wordt automatisch geïnstalleerd in de ondersteunde talen die zijn geïnstalleerd met Windows op het apparaat van de eindgebruiker. Selecteer deze opties als u aanvullende talen wilt installeren met het app-pakket.

>[!IMPORTANT]
> Nadat u het app-pakket hebt gemaakt, kunt u de eigenschappen ervan niet meer bewerken. Als u andere eigenschappen wilt configureren, verwijdert u het app-pakket en maakt u een nieuw pakket.

## <a name="finish-up"></a>Voltooien

Wanneer u klaar bent, kiest u **Opslaan** op de blade **App toevoegen**. De app die u hebt gemaakt, wordt weergegeven in de lijst met apps.

## <a name="error-codes-when-installing-the-app-suite"></a>Foutcodes bij de installatie van het app-pakket

In de volgende tabel staan algemene foutcodes en de betekenis daarvan.

### <a name="status-for-office-csp"></a>Status voor Office CSP: 

||||
|-|-|-|
|Status|Fase|Beschrijving|
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

U kunt de apps nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](/intune-azure/manage-apps/deploy-apps) voor hulp.

             


