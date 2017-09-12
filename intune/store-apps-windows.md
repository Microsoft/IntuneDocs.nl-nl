---
title: Windows Store-apps toevoegen aan Intune
titleSuffix: Azure portal
description: Meer informatie over het toevoegen van Windows Store-apps aan Intune.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f10da996f8587e63320e31ae57e88a5f14f3f9c2
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Windows Store-apps toevoegen aan Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
4. Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies **App-gegevens** op de blade **App toevoegen**.
7. Configureer de volgende gegevens op de blade **App bewerken**. Klik wanneer u klaar bent op **Toevoegen**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden op deze blade mogelijk automatisch ingevuld:
    - **App-naam**: voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **App-beschrijving**: voer een beschrijving in voor de app. Deze wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **App Store URL** (URL van App Store): voer voor de app die u wilt maken de URL naar de App Store in.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie** (optioneel): selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Hierdoor kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Pictogram uploaden**: upload het pictogram dat aan de app wordt gekoppeld. Dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
8. Wanneer u klaar bent, kiest u **Opslaan** op de blade **App toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

## <a name="manually-assign-windows-10-company-portal-app"></a>De Windows 10-bedrijfsportal-app handmatig toewijzen
Eindgebruikers kunnen de bedrijfsportal-app installeren vanuit Microsoft Store voor het beheren van apparaten en installeren van apps. Als uw bedrijf echter vereist dat u de bedrijfsportal-app toewijst, kunt u de Windows 10-bedrijfsportal-app handmatig rechtstreeks toewijzen vanuit Intune, ook als u Intune niet hebt geïntegreerd met Microsoft Store voor Bedrijven.

 > [!NOTE]
 > Voor deze optie is handmatige toewijzing van updates vereist voor elke app-update.

1. Meld u aan bij uw account in [Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) en schaf de versie met de **offlinelicentie** van de bedrijfsportal-app aan.  
2. Zodra de app is aangeschaft, selecteert u de app op de pagina **Inventaris**.  
3. Selecteer **Windows 10 alle apparaten** als **Platform**. Klik vervolgens op de betreffende **Architectuur** en download. Een app-licentiebestand is niet nodig voor deze app.
![Afbeelding van Windows 10 alle apparaten en architectuur X86-pakketdetails voor downloaden](./media/Win10CP-all-devices.png)
4. Download alle pakketten onder "Vereiste frameworks". Dit moet worden uitgevoerd voor x86-, x64- en ARM-architecturen. Totaal zijn dit 9 pakketten, zoals hieronder weergegeven.

![Afbeelding van afhankelijkheidsbestanden voor downloaden ](./media/Win10CP-dependent-files.png)
5. Voordat u de bedrijfsportal-app uploadt naar Intune, maakt u een map (bijvoorbeeld C:&#92;Company Portal) waarin de pakketten als volgt zijn gestructureerd:
  1. Plaats het bedrijfsportalpakket in C:\Bedrijfsportal. Maak op deze locatie tevens een submap Afhankelijkheden.  
  ![Afbeelding van de map Afhankelijkheden waarin het APPXBUN-bestand is opgeslagen](./media/Win10CP-Dependencies-save.png)
  2. Plaats de negen afhankelijkheidspakketten in de map Afhankelijkheden.  
  Als de afhankelijkheden niet in deze indeling worden geplaatst, worden ze niet herkend door Intune en kunnen ze niet worden geüpload tijdens de pakket-upload. Het uploaden mislukt met de volgende fout.  
  ![De Windows-app-afhankelijkheid voor dit software-installatieprogramma is niet gevonden in de toepassingsmap. U kunt doorgaan met het maken en toewijzen van deze toepassing, maar deze kan pas worden uitgevoerd als de ontbrekende Windows-app-afhankelijkheid beschikbaar is.](./media/Win10CP-error-message.png)
6. Ga terug naar Intune en upload the Bedrijfsportal-app als nieuwe app. Wijs deze als vereiste app toe aan de gewenste set doelgebruikers.  

Zie [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Een appxbundle met afhankelijkheden implementeren via Microsoft Intune MDM) voor meer informatie over hoe Intune afhankelijkheden voor universele apps verwerkt.  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Hoe kan ik de Bedrijfsportal op de apparaten van mijn gebruikers bijwerken als hierop al de oudere apps uit de Store zijn geïnstalleerd?
Als uw gebruikers de Windows 8.1- of Windows Phone 8.1-bedrijfsportal-apps al hebben geïnstalleerd vanuit de Store, moeten deze automatisch worden bijgewerkt naar de nieuwe versie, zonder dat hiervoor actie door u of uw gebruikers is vereist. Als de update niet wordt uitgevoerd, vraagt u uw gebruikers om te controleren of automatische updates voor Store-apps op hun apparaten is ingeschakeld.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe ik een upgrade uitvoeren van mijn gesideloade Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de toewijzing voor de Windows 8.1-bedrijfsportal-app te verwijderen door de toewijzingsactie in te stellen op Installatie ongedaan maken. Zodra deze actie is uitgevoerd, kan de Windows 10-bedrijfsportal-app worden toegewezen via een van de bovenstaande opties.  

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal hebt toegewezen zonder deze te ondertekenen met het Symantec-certificaat, volgt u de stappen in de bovenstaande sectie Assign directly via Intune (Rechtstreeks toewijzen via Intune) om de upgrade te voltooien.

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal hebt ondertekend en toegewezen met het Symantec-certificaat voor ondertekening van programmacode, volgt u de stappen in de onderstaande sectie.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe kan ik een upgrade uitvoeren van mijn ondertekende en gesideloade Windows Phone 8.1-bedrijfsportal-app of Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de bestaande toewijzing voor de Windows Phone 8.1-bedrijfsportal-app of de Windows 8.1-bedrijfsportal-app te verwijderen door de toewijzingsactie in te stellen op Installatie ongedaan maken. Zodra deze actie is uitgevoerd, kan de Windows 10-bedrijfsportal-app normaal worden toegewezen.  

Anders moet de Windows 10-bedrijfsportal-app op de juiste manier worden bijgewerkt en ondertekend om ervoor te zorgen dat het upgradepad in acht wordt genomen.  

Als de Windows 10-bedrijfsportal-app op deze manier is ondertekend en toegewezen, moet u dit proces herhalen voor elke nieuwe app-update wanneer deze beschikbaar is in de Store. De app wordt niet automatisch bijgewerkt wanneer de Store wordt bijgewerkt.  

Het ondertekenen en toewijzen van de app gaat als volgt:

1. Download het ondertekeningsscript voor de Microsoft Intune Windows 10-bedrijfsportal-app van [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Voor dit script moet de Windows SDK voor Windows 10 moet zijn geïnstalleerd op de hostcomputer. Ga naar [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) om de Windows SDK voor Windows 10 te downloaden.
2. Download de Windows 10-bedrijfsportal-app vanuit Microsoft Store voor Bedrijven, zoals hierboven beschreven.  
3. Voer het script uit met de invoerparameters die zijn opgegeven in de koptekst van het script om de Windows-10-bedrijfsportal-app (hieronder uitgepakt) te ondertekenen. Afhankelijkheden hoeven niet in het script te worden doorgegeven. Deze zijn alleen vereist wanneer de app wordt geüpload naar de Intune-beheerconsole.

|Parameter | Beschrijving|
| ------------- | ------------- |
|InputWin10AppxBundle |Het pad naar het bron-appxbundle-bestand |
|OutputWin10AppxBundle |Het uitvoerpad voor het ondertekende appxbundle-bestand.  Win81Appx Het pad naar het Windows 8.1- of Windows Phone 8.1-bedrijfsportalbestand (het APPX-bestand).|
|PfxFilePath |Het pad naar het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec (het PFX-bestand). |
|PfxPassword| Het wachtwoord voor het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec. |
|PublisherId |De uitgevers-id van de onderneming. Als deze niet is opgegeven, wordt het veld Onderwerp van Symantec Enterprise-certificaat voor ondertekening van mobiele code gebruikt.|
|SdkPath | Het pad naar de hoofdmap van de Windows-SDK voor Windows 10. Dit argument is optioneel en wordt standaard ingesteld op ${env:ProgramFiles(x86)} \Windows Kits\10|
Via het script wordt de ondertekende versie van de Windows 10-bedrijfsportal-app uitgevoerd wanneer het uitvoeren van de app is voltooid. Vervolgens kunt u de ondertekende versie van de app toewijzen als een LOB-app via Intune. De huidige toegewezen versies worden bijgewerkt naar deze nieuwe app.  
