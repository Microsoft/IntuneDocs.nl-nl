---
title: Win32-apps aan Microsoft Intune toevoegen
titlesuffix: ''
description: Ontdek hoe u Win32-apps toevoegt, levert en beheert met Microsoft Intune. Dit onderwerp bevat een overzicht van de Intune-functies voor het leveren en beheren van Win32-apps en biedt informatie over de probleemoplossing voor Win32-apps.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0dc1974a57e5a5aa6808936c37e02fd31a7cac7b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187290"
---
# <a name="intune-standalone---win32-app-management-public-preview"></a>Intune (zelfstandig) - Win32-app-beheer (openbare preview)

De zelfstandige versie van Intune heeft uitgebreidere beheermogelijkheden voor Win32-apps. Cloudklanten kunnen weliswaar Configuration Manager gebruiken voor het beheer van Win32-apps, maar klanten met alleen Intune hebben uitgebreidere beheermogelijkheden voor hun Win32 LOB-apps (Line-Of-Business). Dit document bevat een overzicht van de Intune-beheerfunctie voor Win32-apps en informatie over de probleemoplossing.

## <a name="prerequisites-for-public-preview"></a>Vereisten voor de openbare preview

- Windows 10 versie 1607 of hoger (Enterprise)
- De Windows 10-client moet aan het volgende voldoen: 
    - gekoppeld aan Azure Active Directory (AAD) of Hybrid Azure Active Directory, en
    - geregistreerd bij Intune (MDM-beheerd)
- De grootte van Windows-apps wordt in de openbare preview beperkt tot 8 GB per app 

> [!NOTE]
> We testen momenteel Pro- en Education-edities van Windows 10 versie 1607 en horen graag uw feedback.


## <a name="prepare-the-win32-app-content-for-upload"></a>De Win32-app-inhoud voor upload voorbereiden

Gebruik het [hulpprogramma voor uploadvoorbereiding van Microsoft Intune Win32-apps](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool) om Win32-apps alvast te verwerken. Het pakkethulpprogramma converteert de app-installatiebestanden naar de indeling *.intunewin*. Het pakkethulpprogramma detecteert ook enkele kenmerken die Intune vereist om de installatiestatus van de app te bepalen. Nadat u dit hulpprogramma hebt gebruikt in de map van het app-installatieprogramma, kunt u een Win32-app maken in de Intune-console.

U kunt het [hulpprogramma voor uploadvoorbereiding van Microsoft Intune Win32-apps](https://github.com/Microsoft/Intune-Win32-App-Packaging-Tool) downloaden uit GitHub.

### <a name="available-command-line-parameters"></a>Beschikbare opdrachtregelparameters 

|    **Opdrachtregelparameter**    |    **Beschrijving**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Help    |
|    `-c <setup_folder>`     |    De installatiemap voor alle installatiebestanden.    |
|   ` -s <setup_file>`     |    Installatiebestand (zoals *setup.exe* of *setup.msi*).    |
|    `-o <output_folder>`     |    Uitvoermap voor het gegenereerde *.intunewin*-bestand.    |
|    `-q`       |    Stille modus    |

### <a name="example-commands"></a>Voorbeeldopdrachten

|    **Voorbeeldopdracht**    |    **Beschrijving**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Met deze opdracht worden de gebruiksgegevens voor het hulpprogramma weergegeven.    |
|    `IntuneWinAppUtil -c <setup_folder> -s <source_setup_file> -o <output_folder> <-q>`    |    Met deze opdracht genereert u het `.intunewin`-bestand van de opgegeven bronmap en het installatiebestand. Dit hulpprogramma haalt vereiste informatie voor Intune op voor het MSI-installatiebestand. Als `-q` is opgegeven, wordt de opdracht uitgevoerd in de stille modus. Als het uitvoerbestand al bestaat, wordt het overschreven. Als de uitvoermap niet bestaat, wordt deze automatisch gemaakt.    |

Wanneer u het bestand *.intunewin* genereert, plaatst u eventuele referentiebestanden in een submap van de map van het installatieprogramma. Vervolgens gebruikt u een relatief pad om te verwijzen naar het specifieke bestand dat u nodig hebt. Bijvoorbeeld:

**Bronmap voor installatieprogramma:** *c:\testapp\v1.0*<br>
**Licentiebestand:** *c:\testapp\v1.0\licenses\license.txt*

Verwijs naar het bestand *license.txt* door het relatieve pad *licenses\license.txt* te gebruiken.

## <a name="create-assign-and-monitor-a-win32-app"></a>Een Win32-app maken, toewijzen en bewaken

Net als bij een LOB-app (Line-Of-Business) kunt u een Win32-app aan Microsoft Intune toevoegen. Dit type app wordt doorgaans intern of door een externe partij geschreven. De volgende stappen bevatten instructies waarmee u een Windows-app kunt toevoegen aan Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Stap 1: de locatie van het software-installatiebestand opgeven

1.  Meld u aan bij [Azure Portal](https://portal.azure.com/).
2.  Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3.  Selecteer in het deelvenster **Intune** de optie **Client-apps** > **Apps** > **Toevoegen**.
4.  Selecteer in het app-deelvenster **Toevoegen** **Windows-app (Win32) - preview** uit de opgegeven vervolgkeuzelijst.

    ![Schermopname van App toevoegen: vervolgkeuzelijst voor soort toevoegen](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Stap 2: het app-pakketbestand uploaden

1.  Selecteer in het deelvenster **App toevoegen** de optie **App-pakketbestand** om een bestand te selecteren. Het deelvenster App-pakketbestand wordt weergegeven.

    ![Schermopname van App-pakketbestand](./media/apps-win32-app-02.png)

2.  Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Windows-installatiebestand met de extensie *.intunewin*.
3.  Klik op **OK** wanneer u klaar bent.

### <a name="step-3-configure-app-information"></a>Stap 3: de app-gegevens configureren

1.  Selecteer in het deelvenster **App toevoegen** de optie **App-gegevens** om de app te configureren.
2.  Configureer de volgende gegevens in het deelvenster **App-gegevens**. Sommige van de waarden in dit deelvenster worden mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Als dezelfde app-naam twee keer voorkomt, wordt elke app in de bedrijfsportal weergegeven.
    - **Beschrijving**: voer een beschrijving in voor de app. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever van de app in.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer desgewenst de URL in van een website die informatie over de app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over de app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat aan de app is gekoppeld. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3.  Klik op **OK** wanneer u klaar bent.

### <a name="step-4-configure-app-installation-details"></a>Stap 4: app-installatiegegevens configureren
1.  Selecteer in het deelvenster **App toevoegen** de optie **Programma** om de installatie- en verwijderopdrachten voor de app te configureren.
2.  Voeg de volledige installatieopdrachtregel toe om de app te installeren. 

    Als de bestandsnaam van uw app bijvoorbeeld **MyApp123** is, voegt u het volgende toe: `msiexec /i “MyApp123.msi”`

3.  Voeg de volledige opdrachtregel voor verwijdering toe om de app te verwijderen op basis van de unieke id van de app. 

    Bijvoorbeeld: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > U kunt een Win32-app configureren voor installatie in een **gebruikers**- of **systeem**context. Een **gebruiker**scontext verwijst naar alleen een bepaalde gebruiker. Een **systeem**context verwijst naar alle gebruikers van een Windows 10-apparaat.
    >
    > Eindgebruikers hoeven niet te zijn aangemeld bij het apparaat om Win32-apps te installeren.

4.  Klik op **OK** wanneer u klaar bent.

### <a name="step-5-configure-app-requirements"></a>Stap 5: de app-vereisten configureren

1.  Selecteer in het deelvenster **App toevoegen** de optie **Vereisten** om de vereisten waaraan apparaten moeten voldoen voordat de app wordt geïnstalleerd te configureren.
2.  Configureer de volgende gegevens in het deelvenster **Vereisten**. Sommige van de waarden in dit deelvenster worden mogelijk automatisch ingevuld.
    - **Architectuur van besturingssysteem**: kies de architecturen die nodig zijn om de app te installeren.
    - **Minimumversie van het besturingssysteem**: selecteer de minimumversie van het besturingssysteem die nodig is om de app te installeren.
    - **Vereiste schijfruimte (MB)**: voeg desgewenst de vrije schijfruimte op het systeemstation toe die nodig is om de app te installeren.
    - **Vereiste fysieke geheugen (MB)**: voeg desgewenst het fysieke geheugen (RAM) toe dat nodig is om de app te installeren.
    - **Minimumaantal vereiste logische processors**: voeg desgewenst het minimumaantal logische processors toe dat nodig is om de app te installeren.
    - **Minimale vereiste processorsnelheid (MHz)**: voeg desgewenst de minimale processorsnelheid toe die nodig is om de app te installeren.
3.  Klik op **OK** wanneer u klaar bent.

### <a name="step-6-configure-app-detection-rules"></a>Stap 6: app-detectieregels configureren

1.  Selecteer in het deelvenster **App toevoegen** de optie **Detectieregels** om de regels voor het detecteren van de aanwezigheid van de app te configureren.
2.  Selecteer in het veld **Regelnotatie** hoe de aanwezigheid van de app moet worden gedetecteerd. U kunt de detectieregels handmatig configureren of een aangepast script gebruiken om de aanwezigheid van de app te detecteren. U moet minstens één detectieregel kiezen. 

    > [!NOTE]
    > U kunt in het deelvenster **Detectieregels** meerdere regels toevoegen. Er moet aan de voorwaarden van **alle** regels worden voldaan om de app te detecteren.

    - **Detectieregels handmatig configureren**: u kunt een van de volgende regeltypen selecteren:
        1.  **MSI**: verifiëren op basis van een controle van de MSI-versie. Deze optie kan slechts eenmaal worden toegevoegd. Als u dit regeltype kiest, hebt u twee instellingen:
            - **MSI-productcode**: voeg een geldige MSI-productcode voor de app toe.
            - **Versiecontrole van MSI-product**: selecteer **Ja** om naast de MSI-productcode de productversie van MSI te controleren.
        2.  **Bestand**: verifieer op basis van bestand- of mapdetectie, datum, versie of grootte.
            - **Pad**: het volledige pad van de map met het bestand of de map dat/die u wilt detecteren.
            - **Bestand of map**: het bestand of de map dat/die u wilt detecteren.
            - **Detectiemethode**: selecteer het type detectiemethode dat moet worden gebruikt om de aanwezigheid van de app te valideren.
            - **Gekoppeld aan een 32-bits app op 64-bits clients**: selecteer **Ja** om padomgevingsvariabelen in een 32-bits context op 64-bits clients uit te breiden. Selecteer **Nee** (standaard) om padvariabelen in een 64-bits context op 64-bits clients uit te breiden. 32-bits clients gebruiken altijd de 32-bits context.
            
            **Voorbeelden van detectie op basis van bestanden**
            1.  Controleer op het bestaan van het bestand.
         
                ![Schermopname van het deelvenster Detectieregels: bestaan van bestand](./media/apps-win32-app-03.png)
        
            2.  Controleer op het bestaan van de map.
         
                ![Schermopname van het deelvenster Detectieregels: bestaan van map](./media/apps-win32-app-04.png)
        
        3. **Register**: verifieer op basis van waarde, tekenreeks, geheel getal of versie.
            - **Sleutelpad**: het volledige pad van de registervermelding met de waarde die moet worden gedetecteerd.
            - **Waardenaam**: de naam van de registerwaarde die moet worden gedetecteerd. Als deze waarde leeg is, wordt de detectie op de sleutel uitgevoerd. De (standaard)waarde van een sleutel wordt als detectiewaarde gebruikt als de detectiemethode anders is dan het bestaan van het bestand of de map.
            - **Detectiemethode**: selecteer het type detectiemethode dat moet worden gebruikt om de aanwezigheid van de app te valideren.
            - **Gekoppeld aan een 32-bits app op 64-bits clients**: selecteer **Ja** om het 32-bits register te doorzoeken op 64-bits clients. Selecteer **Nee** (standaard) om het 64-bits register op 64-bits clients te doorzoeken. Voor 32-bits clients wordt altijd het 32-bits register doorzocht.
            
            **Voorbeelden voor detectie op basis van een register**
            1.  Controleer of er een registersleutel bestaat.
            
                ![Schermopname van het deelvenster Detectieregels: registersleutel bestaat](./media/apps-win32-app-05.png)    
            
            2.  Controleren of registerwaarde bestaat (**niet beschikbaar in preview**).
        
                ![Schermopname van het deelvenster Detectieregels: registerwaarde bestaat](./media/apps-win32-app-06.png)    
        
            3.  Controleer op gelijke tekenreeksen aan die van de registerwaarde.
        
                ![Schermopname van het deelvenster Detectieregels: gelijke tekenreeks registerwaarde](./media/apps-win32-app-07.png)    
     
    - **Een aangepast detectiescript gebruiken**: geef het PowerShell-script op dat wordt gebruikt voor het detecteren van deze app. 
    
        1.  **Scriptbestand**: selecteer een PowerShell-script waarmee de aanwezigheid van de app op de client wordt gedetecteerd. De app worden gedetecteerd wanneer het script zowel een afsluitcode met waarde 0 retourneert als een tekenreekswaarde naar STDOUT schrijft.
        2.  **Script uitvoeren als 32-bits proces op 64-bits clients**: selecteer **Ja** om het script uit te voeren van met de referenties van de aangemelde eindgebruiker. Selecteer **Nee** (standaard) om het script in de systeemcontext uit te voeren.
        3.  **Controle van scripthandtekening afdwingen**: selecteer **Ja** om te verifiëren dat het script is ondertekend door een vertrouwde uitgever, zodat het script zonder waarschuwingen of prompts kan worden uitgevoerd. Het script wordt niet geblokkeerd terwijl het wordt uitgevoerd. Selecteer **Nee** (standaard) om het script met bevestiging van de eindgebruiker uit te voeren zonder handtekeningverificatie.
    
        Intune sidecar controleert de resultaten van het script. Het leest de waarden die door het script zijn geschreven naar de standaard uitvoerstroom (STDOUT), de standaardfoutstroom (STDERR) en de afsluitcode. Als het script wordt afgesloten met een andere waarde dan nul, mislukt het script en is de app-detectiestatus Niet geïnstalleerd. Als de afsluitcode nul is en STDOUT gegevens heeft, is de toepassingsdetectiestatus Geïnstalleerd. 
    
        > [!NOTE]
        > Als het script wordt afgesloten met de waarde 0, is de uitvoering van het script gelukt. Het tweede uitvoerkanaal geeft aan dat de app is gedetecteerd: STDOUT-gegevens geven aan dat de app is gevonden op de client. We zoeken niet naar een bepaalde tekenreeks van STDOUT.
    
3.  Nadat u uw regel(s) hebt toegevoegd, selecteert u **Toevoegen** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Stap 7: app-retourcodes configureren

1.  Selecteer in het deelvenster **App toevoegen** de optie **Retourcodes** om de retourcodes toe te voegen om het gedrag voor opnieuw proberen van de installatie of het gedrag na installatie voor de app op te geven. De retourcodevermeldingen worden tijdens het maken van een app standaard toegevoegd. U kunt echter aanvullende retourcodes toevoegen of bestaande retourcodes wijzigen. 
2.  Voeg in he deelvenster **Retourcodes** extra retourcodes toe of wijzig bestaande retourcodes.
    - **Mislukt**: de retourwaarde die wijst op een app-installatiefout.
    - **Hard opstarten**: de retourcode voor hard opstarten staat niet toe dat de volgende Win32-apps worden geïnstalleerd op de client zonder opnieuw op te starten. 
    - **Zacht opstarten**: de retourcode voor zacht opstarten staat toe dat de volgende Win32-app wordt geïnstalleerd zonder dat de client opnieuw moet worden opgestart. Opnieuw opstarten is nodig om de installatie van de huidige app te voltooien.
    - **Opnieuw**: de retourcode-agent Opnieuw probeert de app drie keer te installeren. Er wordt tussen elke poging 5 minuten gewacht. 
    - **Gelukt**: de retourwaarde die aangeeft dat de app is geïnstalleerd.
3.  Selecteer **OK** nadat u iets hebt toegevoegd aan de lijst met retourcodes of deze hebt aangepast.

### <a name="step-8-add-the-app"></a>Stap 8: de app toevoegen

1.  Controleer in het deelvenster **App toevoegen** of de app-gegevens die u hebt geconfigureerd correct zijn.
2.  Selecteer **Toevoegen** om de app te uploaden naar Intune.

### <a name="step-9-assign-the-app"></a>Stap 9: de app toewijzen

1.  Selecteer in het deelvenster van de app de optie **Toewijzingen**.
2.  Selecteer **Groep toevoegen** om het deelvenster **Groep toevoegen** te openen dat is gerelateerd aan de app.
3.  Selecteer een **toewijzingstype** voor de specifieke app:
    - **Beschikbaar voor ingeschreven apparaten**: gebruikers installeren de app vanuit de bedrijfsportal-app of vanaf de bedrijfsportal-website.
    - **Vereist**: de app wordt geïnstalleerd op apparaten in de geselecteerde groepen.
    - **Verwijderen**: de app wordt verwijderd van apparaten in de geselecteerde groepen.
4.  Selecteer **Opgenomen groepen** en wijs de groepen toe die deze app gaan gebruiken.
5.  Selecteer **OK** op het deelvenster **Toewijzen** de selectie te voltooien van de groepen die moeten worden opgenomen.
6.  Selecteer **Groepen uitsluiten** als u gebruikersgroepen wilt uitsluiten zodat ze niet worden beïnvloed door deze app-toewijzing.
7.  Selecteer **OK** in het deelvenster **Groep toevoegen**.
8.  Selecteer **Opslaan** in het deelvenster **Toewijzingen**.

U hebt nu de stappen voor het toevoegen van een Win32-app aan Intune voltooid. Zie [Apps toewijzen aan groepen met Microsoft Intune](https://docs.microsoft.com/intune/apps-deploy) en [App-gegevens en -toewijzingen controleren met Microsoft Intune](https://docs.microsoft.com/intune/apps-monitor) voor meer informatie over app-toewijzing en -controle.

## <a name="install-required-and-available-apps-on-devices"></a>Vereiste installatie en beschikbare apps op apparaten

De eindgebruiker ziet de pop-upmeldingen van Windows voor de vereiste en beschikbare app-installaties. De volgende afbeelding toont een voorbeeld van de pop-upmelding wanneer de app-installatie pas wordt voltooid wanneer het apparaat opnieuw wordt opgestart. 

![Voorbeeldschermopname van pop-upmeldingen van Windows voor een app-installatie](./media/apps-win32-app-08.png)    

De volgende afbeelding informeert de eindgebruiker dat er app-wijzigingen worden aangebracht aan het apparaat.

![Voorbeeldschermopname van de melding aan de eindgebruiker dat er app-wijzigingen worden aangebracht aan het apparaat](./media/apps-win32-app-09.png)    

## <a name="troubleshoot-win32-app-issues"></a>Problemen met Win32-apps oplossen
Agentlogboeken op de clientcomputer staan doorgaans in `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. U kunt `CMTrace.exe` gebruiken om deze logboekbestanden weer te geven. *CMTrace.exe* kan worden gedownload via [SCCM-clienthulpprogramma's](https://docs.microsoft.com/sccm/core/support/tools). 

![Schermopname van de agentlogboeken](./media/apps-win32-app-10.png)    

### <a name="troubleshooting-areas-to-consider"></a>Gebieden voor probleemoplossing om te overwegen
- Controleer de targeting om ervoor te zorgen dat de agent op het apparaat is geïnstalleerd: een Win32-app gericht op een groep of een PowerShell-Script gericht op een groep maken een agentinstallatiebeleid voor de beveiligingsgroep.
- Controleer de versie van het besturingssysteem: Windows 10 1607 en hoger.  
- Controleer de Windows 10-SKU; Windows 10 S en Windows-versies met de S-modus ingeschakeld bieden geen ondersteuning voor MSI-installatie.

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over apps toevoegen aan Intune.
