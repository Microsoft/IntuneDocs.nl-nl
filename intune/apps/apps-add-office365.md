---
title: Office 365-apps toevoegen aan Windows 10-apparaten met behulp van Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u Microsoft Intune kunt gebruiken om Office 365-apps op Windows 10-apparaten te installeren.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: craigma
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seoapril2019
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2cb247ec25b134fa9810a426be88b7fc90999394
ms.sourcegitcommit: 2c8a41ee95a3fde150667a377770e51b621ead65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2019
ms.locfileid: "73635409"
---
# <a name="add-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Office 365-apps toevoegen aan Windows 10-apparaten met Microsoft Intune

Voordat u apps kunt toewijzen, controleren, configureren of beveiligen, moet u ze aan Intune toevoegen. Een van de beschikbare [apptypen](apps-add.md#app-types-in-microsoft-intune) is Office 365-apps voor Windows 10-apparaten. Door dit apptype in Intune te selecteren, kunt u Office 365-apps toewijzen aan en installeren op door u beheerde apparaten waarop Windows 10 wordt uitgevoerd. U kunt ook apps toewijzen en installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Online Plan 2, mits u daar licenties voor hebt. De beschikbare Office 365-apps worden als één vermelding weergegeven in de lijst met apps in de Intune-console in Azure.

> [!NOTE]
> U moet Office 365 ProPlus-licenties gebruiken om Office 365 ProPlus-apps te activeren die via Microsoft Intune zijn geïmplementeerd. Momenteel wordt Office 365 Business-editie niet ondersteund door Intune.

## <a name="before-you-start"></a>Voordat u begint

> [!IMPORTANT]
> Als zich op het apparaat van eindgebruiker MSI-Office-apps bevinden, moet u de functie **MSI verwijderen** gebruiken om deze apps veilig te verwijderen. Anders mislukt de installatie van de door Intune geleverd Office 365-apps.

- Op de apparaten waarop u deze apps implementeert, moet de Microsoft Windows 10-makersupdate of hoger zijn geïnstalleerd.
- Intune biedt alleen ondersteuning voor het toevoegen van Office-apps uit de Office 365-suite.
- Als er Office-apps zijn geopend wanneer het app-pakket wordt geïnstalleerd met Intune, kan de installatie mislukken en kunnen gebruikers gegevens in niet-opgeslagen bestanden verliezen.
- Deze installatiemethode wordt niet ondersteund op apparaten met Windows Home, Windows Team, Windows Holographic of Windows Holographic for Business.
- Intune biedt geen ondersteuning voor het installeren van Office 365-desktop-apps vanuit Microsoft Store (die ook wel bekend staan als Office Centennial-apps) op een apparaat waarop u al Office 365-apps met Intune hebt geïmplementeerd. Als u deze configuratie installeert, kan dit leiden tot gegevensverlies of -beschadiging.
- Meerdere vereiste of beschikbare app-toewijzingen tellen niet mee. Een latere app-toewijzing overschrijft reeds bestaande geïnstalleerde app-toewijzingen. Als de eerste set met Office-apps bijvoorbeeld Word bevat maar de laatste set niet, wordt Word verwijderd. Deze voorwaarde geldt niet voor Visio- of Project-toepassingen.
- Meerdere Office 365-implementaties worden momenteel niet ondersteund. Er wordt slechts één implementatie geleverd op het apparaat
- **Office-versie**: kies of u de 32-bits of 64-bits versie van Office wilt toewijzen. U kunt de 32-bits versie op zowel 32-bits als 64-bits apparaten installeren, maar de 64-bits versie kan alleen worden geïnstalleerd op 64-bits apparaten.
- **MSI verwijderen van de apparaten van eindgebruikers**: kies of u bestaande Office MSI-apps wilt verwijderen van apparaten van eindgebruikers. De installatie mislukt als er zich bestaande MSI-apps op apparaten van eindgebruikers bevinden. De te verwijderen apps zijn niet beperkt tot de apps die zijn geselecteerd voor de installatie in **App-suite configureren**, omdat hierdoor alle Office-apps (MSI) van het apparaat van de eindgebruiker worden verwijderd. Zie [Bestaande MSI-versies van Office verwijderen bij een upgrade naar Office 365 ProPlus](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version) voor meer informatie. Wanneer u Intune Office opnieuw op de computers van uw eindgebruikers installeert, krijgen eindgebruikers automatisch dezelfde taalpakketten als bij eerdere .MSI Office installaties.

## <a name="get-started"></a>Aan de slag

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloaddeelvenster **Client-apps** onder **Beheren** de optie **Apps**.
5. Selecteer **Toevoegen**.
6. Selecteer **Windows 10** in het deelvenster **Apps toevoegen**, in de lijst **App-type** onder **Office 365 Suite**.

## <a name="select-settings-format"></a>Indeling van instellingen selecteren

Selecteer een **Indeling voor instellingen** om een configuratiemethode voor appinstellingen te kiezen. De volgende indelingsopties voor instellingen zijn beschikbaar:
- Configuration Designer
- XML-gegevens invoeren

Wanneer u **Configuration Designer** kiest, worden op de blade **App toevoegen** twee extra instellingsopties weergegeven:
- De app-suite configureren
- Instellingen voor app-suite

<img alt="Add Office 365 - Configuration designer" src="./media/apps-add-office365/apps-add-office365-02.png" width="700">

Als u **XML-gegevens invoeren** kiest, wordt op de blade **App toevoegen** de optie **XML-gegevens invoeren** weergegeven. Selecteer deze optie om de blade **Configuratiebestand** weer te geven. 

![Office 365 Configuration Designer toevoegen](./media/apps-add-office365/apps-add-office365-01.png)
    
Zie [XML-gegevens invoeren](apps-add-office365.md#enter-xml-format) hieronder voor meer informatie over de optie **XML-gegevens invoeren**.

## <a name="configure-app-suite-information"></a>Gegevens over app-suite configureren

In deze stap geeft u informatie op over het app-pakket. Aan de hand van deze informatie kunt u het app-pakket vinden in Intune en kunnen gebruikers het app-pakket vinden in de bedrijfsportal.

1. Selecteer **App-pakketgegevens** in het deelvenster **App toevoegen**.
2. Voer in het deelvenster **App-pakketgegevens** het volgende uit:
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
3. Selecteer **OK**.

## <a name="configure-app-suite"></a>De app-suite configureren

Als u de optie **Configuration Designer** in de vervolgkeuzelijst **Instellingsindeling**, ziet u de optie **App-suite configureren** in de blade **App toevoegen**. Selecteer de Office-apps die u wilt toewijzen aan apparaten.

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakket configureren**.
2. Kies in het deelvenster **App-pakket configureren** de standaard-apps van Office die u wilt toewijzen aan apparaten.  
    Daarnaast kunt u apps installeren voor de Microsoft Project Online-bureaubladclient en Microsoft Visio Online Plan 2, mits u daar licenties voor hebt.
3. Selecteer **OK**.

## <a name="configure-app-suite-settings"></a>Instellingen voor app-suite configureren

Als u de optie **Configuration Designer** in de vervolgkeuzelijst **Instellingsindeling**, ziet u de optie **Instellingen app-suite** in de blade **App toevoegen**. In deze stap configureert u de installatieopties voor het app-pakket. De instellingen gelden voor alle apps die u aan het pakket hebt toegevoegd.

1. Selecteer in het deelvenster **App toevoegen** de optie **Instellingen voor app-pakket**.
2. Voer in het deelvenster **Instellingen voor app-pakket** het volgende uit:
    - **Office-versie**: kies of u de 32-bits of 64-bits versie van Office wilt toewijzen. U kunt de 32-bits versie op zowel 32-bits als 64-bits apparaten installeren, maar de 64-bits versie kan alleen worden geïnstalleerd op 64-bits apparaten.
    - **Updatekanaal**: kies hoe Office moet worden bijgewerkt op apparaten. Zie [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) (Overzicht van updatekanalen voor Office 365 ProPlus) voor meer informatie over de verschillende updatekanalen. U kunt kiezen uit:
        - **Maandelijks**
        - **Maandelijks (gericht)**
        - **Halfjaarlijks**
        - **Halfjaarlijks (gericht)**

        Wanneer u een kanaal hebt gekozen, kunt u eventueel **Specifiek** selecteren om voor het geselecteerde kanaal een specifieke versie van Office te installeren op apparaten van eindgebruikers. Selecteer daarna welke **specifieke versie** van Office u wilt gebruiken.
        
        Welke versies er beschikbaar zijn, verandert in de loop van de tijd. Daarom is het mogelijk dat er bij het maken van een nieuwe implementatie nieuwere versies beschikbaar zijn en dat bepaalde oudere versies niet meer beschikbaar zijn. Huidige implementaties blijven de oudere versie implementeren, maar de versielijst wordt voortdurend per kanaal bijgewerkt.
        
        Voor apparaten waarop de vastgemaakte versie wordt bijgewerkt (of andere eigenschappen worden bijgewerkt) en die worden geïmplementeerd als beschikbaar, wordt de rapportagestatus weergegeven als Geïnstalleerd als ze de vorige versie hebben geïnstalleerd, totdat het apparaat wordt ingecheckt. Als het apparaat wordt ingecheckt, wordt tijdelijk de status gewijzigd in Onbekend, maar dit wordt niet aan de gebruiker weergegeven. Wanneer de gebruiker met de installatie van de later beschikbaar gekomen versie begint, ziet de gebruiker dat de status wordt gewijzigd in Geïnstalleerd.
        
        Zie [Overzicht van updatekanalen voor Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) voor meer informatie.

    - **MSI verwijderen van de apparaten van eindgebruikers**: kies of u bestaande Office MSI-apps wilt verwijderen van apparaten van eindgebruikers. De installatie mislukt als er zich bestaande MSI-apps op apparaten van eindgebruikers bevinden. De te verwijderen apps zijn niet beperkt tot de apps die zijn geselecteerd voor de installatie in **App-suite configureren**, omdat hierdoor alle Office-apps (MSI) van het apparaat van de eindgebruiker worden verwijderd. Zie [Bestaande MSI-versies van Office verwijderen bij een upgrade naar Office 365 ProPlus](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version) voor meer informatie. Wanneer u Intune Office opnieuw op de computers van uw eindgebruikers installeert, krijgen eindgebruikers automatisch dezelfde taalpakketten als bij eerdere .MSI Office installaties. 
    - **Gebruiksrechtovereenkomst voor eindgebruikers van de app automatisch accepteren**: selecteer deze optie als het voor eindgebruikers niet vereist is om de gebruiksrechtovereenkomst te accepteren. Intune accepteert de overeenkomst automatisch.
    - **Activering van gedeelde computers gebruiken**: selecteer deze optie wanneer meerdere gebruikers een computer delen. Zie [Overzicht van activering van gedeelde computers voor Office 365](https://docs.microsoft.com/DeployOffice/overview-of-shared-computer-activation-for-office-365-proplus) voor meer informatie.
    - **Talen**: Office wordt automatisch geïnstalleerd in de ondersteunde talen die met Windows zijn geïnstalleerd op het apparaat van de eindgebruiker. Selecteer deze opties als u aanvullende talen wilt installeren met het app-pakket. <p></p>
    U kunt aanvullende talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in Azure Portal **Microsoft Intune** > **Client-apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**. Zie voor meer informatie het [overzicht van de implementatie van talen in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-deploying-languages-in-office-365-proplus).

## <a name="select-scope-tags-optional"></a>Bereiktags selecteren (optioneel)
U kunt bereiktags gebruiken om te bepalen wie er informatie over client-apps mag bekijken in Intune. Zie [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md) (Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT) voor uitgebreide informatie over bereiktags.

1. Selecteer **Bereik (tags)**  > **Toevoegen**.
2. Gebruik het vak onder **Selecteren** om bereiktags te zoeken.
3. Schakel het selectievakje in naast de bereiktags die u aan deze app wilt toewijzen.
4. Kies **Selecteren** > **OK**.

## <a name="enter-xml-format"></a>XML-indeling invoeren

Als u de optie **XML-gegevens invoeren** in de vervolgkeuzelijst **Instellingsindeling**, ziet u de optie **XML-gegevens invoeren** in de blade **App toevoegen**. Raadpleeg [Configuratie-opties voor het Office-implementatieprogramma](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool) voor meer informatie.

## <a name="finish-up"></a>Voltooien

Als u klaar bent, selecteert u **Toevoegen** in het deelvenster **App toevoegen**. De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. De volgende stap is het toewijzen van de apps aan de groepen van uw keuze. Zie [Apps aan groepen toewijzen](~/apps/apps-deploy.md) voor meer informatie.

## <a name="deployment-details"></a>Implementatiedetails

Nadat het implementatiebeleid van Intune is toegewezen aan de doelmachines via de [Office-configuratieserviceprovider (CSP)](https://docs.microsoft.com/windows/client-management/mdm/office-csp), downloadt het eindapparaat automatisch het installatiepakket van de locatie *officecdn.microsoft.com*. U ziet twee nieuwe mappen in de map *Program Files*:

![Office-installatiepakketten in de map Program Files](./media/apps-add-office365/office-folder.png)

Onder de map *Microsoft Office* wordt een nieuwe map gemaakt waarin de installatiebestanden worden opgeslagen:

![Nieuwe map gemaakt onder Microsoft Office-directory](./media/apps-add-office365/created-folder.png)

Onder de map *Microsoft Office 15* worden de Klik-en-Klaar-opstartbestanden voor het installeren van Office opgeslagen. De installatie wordt automatisch gestart als het toewijzingstype vereist is:

![Klik-en-Klaar-opstartbestanden voor installatie](./media/apps-add-office365/clicktorun-files.png)

De installatie wordt uitgevoerd in de stille modus als de toewijzing van het O365-pakket is geconfigureerd als vereist. De gedownloade installatiebestanden worden verwijderd zodra de installatie is voltooid. Als de toewijzing is geconfigureerd als **Beschikbaar**, worden de Office-toepassingen weergegeven in de Bedrijfsportal-toepassing, zodat eindgebruikers de installatie handmatig kunnen starten.

## <a name="troubleshooting"></a>Probleemoplossing
Intune gebruikt het [Office-implementatiehulpprogramma](https://docs.microsoft.com/DeployOffice/overview-of-the-office-2016-deployment-tool) om Office 365 ProPlus te downloaden en op uw clientcomputers te implementeren met de [Office 365 CDN](https://docs.microsoft.com/office365/enterprise/content-delivery-networks). Bekijk de best practices die worden vermeld in [Office 365-eindpunten beheren](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints), om ervoor te zorgen dat uw netwerkconfiguratie toestaat dat clients rechtstreeks toegang hebben tot CDN, in plaats van dat CDN-verkeer door centrale proxy's wordt geleid. Zo voorkomt u onnodige latentie.

Voer de [Microsoft Ondersteunings- en herstelassistent voor Office 365](https://diagnostics.office.com) uit op een doelapparaat als u tijdens de installatie of uitvoering problemen ondervindt.

### <a name="additional-troubleshooting-details"></a>Aanvullende gegeven voor het oplossen van problemen

Als u de O365-apps niet op een apparaat kunt installeren, moet u vaststellen of het probleem verband houdt met Intune of met het besturingssysteem of Office. Als de twee mappen *Microsoft Office* en *Microsoft Office 15* worden weergegeven in de map *Program Files* map van het apparaat, kunt u bevestigen dat Intune de implementatie met succes heeft gestart. Als u de twee mappen niet ziet verschijnen onder *Program Files*, moet u de onderstaande gevallen bevestigen:

- Het apparaat is goed ingeschreven bij Microsoft Intune. 
- Er is een actieve netwerkverbinding met het apparaat. Als het apparaat zich in de vliegtuigmodus bevindt, is uitgeschakeld of zich op een locatie zonder service bevindt, wordt het beleid pas toegepast nadat de netwerkverbinding tot stand is gebracht.
- Aan de netwerkvereisten voor zowel Intune als Office 365 is voldaan en de bijbehorende IP-bereiken zijn toegankelijk op basis van de volgende artikelen:

  - [Netwerkconfiguratievereisten en bandbreedte voor Intune](https://docs.microsoft.com/intune/network-bandwidth-use)
  - [Office 365-URL's en IP-adresbereiken](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)

- Het O365-app-pakket is toegewezen aan de juiste groepen. 

Controleer bovendien de grootte van de directory *C:\Program Files\Microsoft Office\Updates\Download*. Het van de Intune-cloud gedownloade installatiepakket wordt opgeslagen op deze locatie. Als de grootte niet of erg langzaam toeneemt, is het raadzaam om de netwerkverbinding en bandbreedte te controleren.

Wanneer u kunt concluderen dat zowel Intune als de netwerkinfrastructuur naar verwachting werken, moet u het probleem verder analyseren vanuit besturingssysteemperspectief. Houd rekening met de volgende voorwaarden:

- Het doelapparaat moet werken met Windows 10-makersupdate of hoger.
- Er zijn geen bestaande Office-apps geopend terwijl Intune de toepassingen implementeert.
- Bestaande MSI-versies van Office zijn op de juiste wijze verwijderd van het apparaat. Intune maakt gebruik van Office Klik-en-klaar, dat niet compatibel is met Office MSI. Dit gedrag wordt verder beschreven in dit document:<br>
  [Office op dezelfde computer geïnstalleerd met Klik-en-Klaar en met Windows Installer wordt niet ondersteund](https://support.office.com/article/office-installed-with-click-to-run-and-windows-installer-on-same-computer-isn-t-supported-30775ef4-fa77-4f47-98fb-c5826a6926cd)
- De aanmeldingsgebruiker moet gemachtigd zijn om toepassingen op het apparaat te installeren.
- Bevestig dat er geen problemen zijn op basis van de Windows-Logboeken **Windows-logboeken** -> **Toepassingen**.
- Leg tijdens de installatie uitgebreide Office-installatielogboeken vast. Volg hiervoor de volgende stappen:<br>
    1. Schakel uitgebreide logboekregistratie voor Office-installatie in op de doelcomputers. Hiervoor voert u de volgende opdracht uit om het register te wijzigen:<br>
        `reg add HKLM\SOFTWARE\Microsoft\ClickToRun\OverRide /v LogLevel /t REG_DWORD /d 3`<br>
    2. Implementeer het Office 365-pakket opnieuw op de doelapparaten.<br>
    3. Wacht ongeveer 15 tot 20 minuten en ga naar de map **%temp%** en de map **%windir%\temp**, sorteer op **Gewijzigd op** en kies de *{machinenaam}-{tijdstempel}.log*-bestanden die zijn gewijzigd op basis van uw reproductietijdstip.<br>
    4. Schakel de uitgebreide logboekregistratie weer uit met de volgende opdracht:<br>
        `reg delete HKLM\SOFTWARE\Microsoft\ClickToRun\OverRide /v LogLevel /f`<br>
        De uitgebreide logboeken kunnen meer gedetailleerde informatie bieden over het installatieproces.

## <a name="errors-during-installation-of-the-app-suite"></a>Fouten tijdens de installatie van het app-pakket

Raadpleeg [ULS-logboekregistratie in Office 365 ProPlus inschakelen](https://blogs.technet.microsoft.com/odsupport/2018/06/18/how-to-enable-office-365-proplus-uls-logging) voor informatie over hoe u uitgebreide installatielogboeken bekijkt.

In de volgende tabellen worden algemene foutcodes en hun betekenis weergegeven.

### <a name="status-for-office-csp"></a>Status voor Office CSP

| Status | Fase | Beschrijving |
|--------------------------------------------------|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1460 (ERROR_TIMEOUT) | Download | Het downloaden van de Office Deployment Tool is mislukt |
| 13 (ERROR_INVALID_DATA) | - | De handtekening van de gedownloade Office Deployment Tool kan niet worden geverifieerd |
| Foutcode van CertVerifyCertificateChainPolicy | - | De certificeringscontrole van de gedownloade Office Deployment Tool is mislukt |
| 997 | WIP | Wordt geïnstalleerd |
| 0 | Na de installatie | Installatie voltooid |
| 1603 (ERROR_INSTALL_FAILURE) | - | Controle van vereisten is mislukt, zoals SxS (Er is geprobeerd te installeren terwijl 2016 MSI is geïnstalleerd)Versie komt niet overeenOverige |
| 0x8000ffff (E_UNEXPECTED) | - | Er is geprobeerd te verwijderen zonder Office Klik-en-Klaar op de machine |
| 17002 | - | Het scenario (installatie) kan niet worden voltooid. Mogelijke redenen:Installatie geannuleerd door gebruikerInstallatie geannuleerd door een andere installatieOnvoldoende schijfruimte tijdens installatieOnbekende taal-ID |
| 17004 | - | Onbekende SKU’s |


### <a name="office-deployment-tool-error-codes"></a>Office Deployment Tool-foutcodes

| Scenario | Retourcode | Gebruikersinterface | Opmerking |
|------------------------------------------------------------------------------------------------------------------|---------------------------------------|----------------------------------------------------|------------------------------------|
| Er is geprobeerd de installatie te verwijderen zonder actieve Klik-en-Klaar-installatie | -2147418113, 0x8000ffff of 2147549183 | Foutcode: 30088-1008Foutcode: 30125-1011 (404) | Office Deployment Tool |
| Installeren terwijl de MSI-versie is geïnstalleerd | 1603 | - | Office Deployment Tool |
| De installatie is geannuleerd door de gebruiker of door een andere installatie | 17002 | - | Klik-en-Klaar |
| Er is geprobeerd een 64-bits versie te installeren op een apparaat waarop de 32-bits versie is geïnstalleerd. | 1603 | - | Retourcodes Office Deployment Tool |
| Er is geprobeerd een onbekende SKU te installeren (dit is geen geldige use case voor Office CSP omdat er alleen geldige SKU’s mogen worden doorgegeven) | 17004 | - | Klik-en-Klaar |
| Gebrek aan ruimte | 17002 | - | Klik-en-Klaar |
| Kan de Klik-en-Klaar-client niet starten (onverwacht) | 17000 | - | Klik-en-Klaar |
| De Klik-en-Klaar-client kan het scenario niet in de wachtrij zetten (onverwacht) | 17001 | - | Klik-en-Klaar |

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps toewijzen aan groepen](/intune-azure/manage-apps/deploy-apps) om de apps toe te wijzen aan de groepen van uw keuze.
