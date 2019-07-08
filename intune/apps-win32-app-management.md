---
title: Win32-apps toevoegen en toewijzen aan Microsoft Intune
titleSuffix: ''
description: Ontdek hoe u Win32-apps toevoegt, toewijst en beheert met Microsoft Intune. Dit onderwerp bevat een overzicht van de Intune-functies voor het leveren en beheren van Win32-apps en biedt informatie over de probleemoplossing voor Win32-apps.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: efdc196b-38f3-4678-ae16-cdec4303f8d2
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3cfe2aef93fb8b7c420ee6513945f11bee5bd0be
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2019
ms.locfileid: "67529722"
---
# <a name="intune-standalone---win32-app-management"></a>Intune (zelfstandig) - Win32-app-beheer

[De zelfstandige versie van Intune](mdm-authority-set.md) heeft nu uitgebreidere beheermogelijkheden voor Win32-apps. Cloudklanten kunnen weliswaar Configuration Manager gebruiken voor het beheer van Win32-apps, maar klanten met alleen Intune hebben uitgebreidere beheermogelijkheden voor hun Win32 LOB-apps (Line-Of-Business). Dit document bevat een overzicht van de Intune-beheerfunctie voor Win32-apps en informatie over de probleemoplossing.

> [!NOTE]
> Deze app-beheermogelijkheid biedt ondersteuning voor zowel 32- als 64-bits besturingssysteemarchitecturen voor Windows-toepassingen.

## <a name="prerequisites"></a>Vereisten

Als u Win32-app-beheer wilt gebruiken, moet u aan de volgende criteria voldoen:

- Windows 10 versie 1607 of hoger (Enterprise, Pro en Education)
- De Windows 10-client moet aan het volgende voldoen: 
    - Apparaten moeten worden gekoppeld aan Azure AD en automatisch worden ingeschreven. De Intune-beheeruitbreiding biedt ondersteuning voor apparaten die via een groepsbeleid zijn ingeschreven, zijn toegevoegd aan Azure AD en aan een hybride domein zijn toegevoegd. 
    > [!NOTE]
    > Voor het scenario met inschrijving via het groepsbeleid: eindgebruikers gebruiken het lokale gebruikersaccount om hun Windows 10-apparaat met AAD samen te voegen. Gebruikers moeten zich op het apparaat aanmelden met hun AAD-gebruikersaccount en zich bij inschrijven bij Intune. Intune installeert de Intune-beheerextensie op het apparaat als een PowerShell-script of een Win32-app op de gebruiker of het apparaat is gericht.
- De grootte van Windows-toepassingen is beperkt tot 8 GB per app.

## <a name="prepare-the-win32-app-content-for-upload"></a>De Win32-app-inhoud voor upload voorbereiden

Gebruik het [hulpprogramma voor voorbereiding van Microsoft Win32-inhoud](https://go.microsoft.com/fwlink/?linkid=2065730) om klassieke Windows-apps (Win32) alvast te verwerken. Met het hulpprogramma converteert u de app-installatiebestanden naar de indeling *.intunewin*. Het hulpprogramma detecteert ook enkele kenmerken die voor Intune zijn vereist om de installatiestatus van de app te bepalen. Nadat u dit hulpprogramma hebt gebruikt in de map van het app-installatieprogramma, kunt u een Win32-app maken in de Intune-console.

> [!IMPORTANT]
> Alle bestanden en submappen worden met het [hulpprogramma voor de voorbereiding van Microsoft Win32-inhoud](https://go.microsoft.com/fwlink/?linkid=2065730) ingepakt wanneer het *.intunewin*-bestand wordt gemaakt. Zorg ervoor dat u het hulpprogramma voor de voorbereiding van Microsoft Win32-inhoud gescheiden houdt van de bestanden en mappen van het installatieprogramma, zodat u het hulpprogramma of andere onnodige bestanden en mappen niet in uw *.intunewin*-bestand insluit.

U kunt het [hulpprogramma voor voorbereiding van Microsoft Win32-inhoud](https://go.microsoft.com/fwlink/?linkid=2065730) als zip-bestand downloaden via GitHub. Het ingepakte bestand bevat de map **Microsoft-Win32-Content-Prep-Tool-master**. In de map vindt u het voorbereidingsprogramma, de licentie, een readme-bestand en de release-opmerkingen. 

### <a name="process-flow-to-create-intunewin-file"></a>Processtroom voor het maken van het .intunewin-bestand

   ![Processtroom voor het maken van een .intunewin-bestand](./media/prepare-win32-app.svg)

### <a name="run-the-microsoft-win32-content-prep-tool"></a>Het hulpprogramma voor de voorbereiding van Microsoft Win32-inhoud uitvoeren

Als u `IntuneWinAppUtil.exe` uitvoert zonder parameters vanuit het opdrachtvenster, krijgt u in het hulpprogramma stapsgewijze instructies voor het invoeren van de vereiste parameters. Of u kunt de parameters aan de opdracht toevoegen op basis van de volgende beschikbare opdrachtregelparameters.

### <a name="available-command-line-parameters"></a>Beschikbare opdrachtregelparameters 

|    **Opdrachtregelparameter**    |    **Beschrijving**    |
|:------------------------------:|:----------------------------------------------------------:|
|    `-h`     |    Help    |
|    `-c <setup_folder>`     |    De map voor alle installatiebestanden. Alle bestanden in deze map worden gecomprimeerd in een *.intunewin*-bestand.    |
|    `-s <setup_file>`     |    Installatiebestand (zoals *setup.exe* of *setup.msi*).    |
|    `-o <output_folder>`     |    Uitvoermap voor het gegenereerde *.intunewin*-bestand.    |
|    `-q`       |    Stille modus    |

### <a name="example-commands"></a>Voorbeeldopdrachten

|    **Voorbeeldopdracht**    |    **Beschrijving**    |
|:-----------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
|    `IntuneWinAppUtil -h`    |    Met deze opdracht worden de gebruiksgegevens voor het hulpprogramma weergegeven.    |
|    `IntuneWinAppUtil -c c:\testapp\v1.0 -s c:\testapp\v1.0\setup.exe -o c:\testappoutput\v1.0 -q`    |    Met deze opdracht genereert u het `.intunewin`-bestand van de opgegeven bronmap en het installatiebestand. Dit hulpprogramma haalt vereiste informatie voor Intune op voor het MSI-installatiebestand. Als `-q` is opgegeven, wordt de opdracht uitgevoerd in de stille modus. Als het uitvoerbestand al bestaat, wordt het overschreven. Als de uitvoermap niet bestaat, wordt deze automatisch gemaakt.    |

Wanneer u het bestand *.intunewin* genereert, plaatst u eventuele referentiebestanden in een submap van de map van het installatieprogramma. Vervolgens gebruikt u een relatief pad om te verwijzen naar het specifieke bestand dat u nodig hebt. Bijvoorbeeld:

**Bronmap voor installatieprogramma:** *c:\testapp\v1.0*<br>
**Licentiebestand:** *c:\testapp\v1.0\licenses\license.txt*

Verwijs naar het bestand *license.txt* door het relatieve pad *licenses\license.txt* te gebruiken.

## <a name="create-assign-and-monitor-a-win32-app"></a>Een Win32-app maken, toewijzen en bewaken

Net als bij een LOB-app (Line-Of-Business) kunt u een Win32-app aan Microsoft Intune toevoegen. Dit type app wordt doorgaans intern of door een externe partij geschreven. 

### <a name="process-flow-to-add-a-win32-app-to-intune"></a>Processtroom om een Win32-app aan Intune toe te voegen

   ![Processtroom om een Win32-app aan Intune toe te voegen](./media/add-win32-app.svg)

### <a name="add-a-win32-app-to-intune"></a>Een Win32-app toevoegen aan Intune

De volgende stappen bevatten instructies waarmee u een Windows-app kunt toevoegen aan Intune.

### <a name="step-1-specify-the-software-setup-file"></a>Stap 1: locatie van het software-installatiebestand opgeven

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer in het deelvenster **Intune** de optie **Client-apps** > **Apps** > **Toevoegen**.
4. Selecteer in het app-deelvenster **Toevoegen** **Windows-app (Win32)** uit de opgegeven vervolgkeuzelijst.

    ![Schermafbeelding van de blade App toevoegen - vervolgkeuzelijst Type toevoegen](./media/apps-win32-app-01.png)

### <a name="step-2-upload-the-app-package-file"></a>Stap 2: het app-pakketbestand uploaden

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakketbestand** om een bestand te selecteren. Het deelvenster App-pakketbestand wordt weergegeven.

    ![Schermafbeelding van de blade App-pakketbestand](./media/apps-win32-app-02.png)

2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Windows-installatiebestand met de extensie *.intunewin*.

    > [!IMPORTANT]
    > Gebruik de nieuwste versie van het hulpprogramma voor voorbereiding van Microsoft Win32-inhoud. Als u de nieuwste versie niet gebruikt, ziet u een waarschuwing om aan te geven dat de app met een oudere versie van het hulpprogramma voor voorbereiding van Microsoft Win32-inhoud is ingepakt. 

3. Klik op **OK** wanneer u klaar bent.

### <a name="step-3-configure-app-information"></a>Stap 3: App-gegevens configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **App-gegevens** om de app te configureren.
2. Configureer de volgende gegevens in het deelvenster **App-gegevens**. Sommige van de waarden in dit deelvenster worden mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Als dezelfde app-naam twee keer voorkomt, wordt elke app in de bedrijfsportal weergegeven.
    - **Beschrijving**: Voer een beschrijving in voor de app. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Geef de app prominent weer op de hoofdpagina van de bedrijfsportal wanneer gebruikers door apps bladeren.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat u aan de app wilt koppelen. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Klik op **OK** wanneer u klaar bent.

### <a name="step-4-configure-app-installation-details"></a>Stap 4: app-installatiegegevens configureren
1. Selecteer in het deelvenster **App toevoegen** de optie **Programma** om de installatie- en verwijderopdrachten voor de app te configureren.
2. Voeg de volledige installatieopdrachtregel toe om de app te installeren. 

    Als de bestandsnaam van uw app bijvoorbeeld **MyApp123** is, voegt u het volgende toe:<br>
    `msiexec /p “MyApp123.msp”`<p>
    En als de toepassing `ApplicationName.exe` is, bestaat de opdracht uit de naam van de toepassing, gevolgd door de opdrachtargumenten (schakelaars) die door het pakket worden ondersteund. <br>Bijvoorbeeld:<br>
    `ApplicationName.exe /quiet`<br>
    In de bovenstaande opdracht biedt het `ApplicationName.exe`-pakket ondersteuning voor het opdrachtargument `/quiet`.<p> 
    Neem voor de specifieke argumenten die door het toepassingspakket worden ondersteund contact op met uw toepassingsleverancier.

3. Voeg de volledige opdrachtregel voor verwijdering toe om de app te verwijderen op basis van de unieke id van de app. 

    Bijvoorbeeld: `msiexec /x “{12345A67-89B0-1234-5678-000001000000}”`

    > [!NOTE]
    > U kunt een Win32-app configureren voor installatie in een **gebruikers**- of **systeem**context. Een **gebruiker**scontext verwijst naar alleen een bepaalde gebruiker. Een **systeem**context verwijst naar alle gebruikers van een Windows 10-apparaat.
    >
    > Eindgebruikers hoeven niet te zijn aangemeld bij het apparaat om Win32-apps te installeren.
    > 
    > Het installeren en verwijderen van de Win32-app wordt uitgevoerd met de beheerdersbevoegdheden (standaard) wanneer voor de app is ingesteld dat deze in de gebruikerscontext moet worden geïnstalleerd en de eindgebruiker op het apparaat beheerdersbevoegdheden heeft.

4. Klik op **OK** wanneer u klaar bent.

### <a name="step-5-configure-app-requirements"></a>Stap 5: de app-vereisten configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **Vereisten** om de vereisten waaraan apparaten moeten voldoen voordat de app wordt geïnstalleerd te configureren.
2. Configureer de volgende gegevens in het deelvenster **Een regel voor vereisten toevoegen**. Sommige van de waarden in dit deelvenster worden mogelijk automatisch ingevuld.
    - **Architectuur van besturingssysteem**: kies de architecturen die nodig zijn om de app te installeren.
    - **Minimumversie van het besturingssysteem**: selecteer de minimumversie van het besturingssysteem die nodig is om de app te installeren.
    - **Vereiste schijfruimte (MB)**: voeg optioneel de vrije schijfruimte op het systeemstation toe die nodig is om de app te installeren.
    - **Vereiste fysieke geheugen (MB)**: voeg optioneel het fysieke geheugen (RAM) toe dat nodig is om de app te installeren.
    - **Minimumaantal vereiste logische processors**: voeg optioneel het minimumaantal logische processors toe dat nodig is om de app te installeren.
    - **Minimale vereiste processorsnelheid (MHz)**: voeg optioneel de minimale processorsnelheid toe die nodig is om de app te installeren.

3. Klik op **Toevoegen** om de blade **Een vereisteregel toevoegen** weer te geven en aanvullende vereisteregels te configureren. Selecteer het **Vereistetype** om het regeltype te kiezen dat u wilt gebruiken om te bepalen hoe een vereiste moet worden gevalideerd. Vereisteregels kunnen op informatie over het bestandssysteem, registerwaarden of PowerShell-scripts worden gebaseerd. 
    - **Bestand**: Als u **Bestand** als **Vereistetype** kiest, moet de vereisteregel een bestand of map, datum, versie of grootte selecteren. 
        - **Pad**: het volledige pad van de map met het bestand of de map dat/die u wilt detecteren.
        - **Bestand of map**: het bestand of de map dat/die u wilt detecteren.
        - **Eigenschap**: selecteer het type regel dat moet worden gebruikt om de aanwezigheid van de app te valideren.
        - **Gekoppeld aan een 32-bits app op 64-bits clients**: selecteer **Ja** om padomgevingsvariabelen in een 32-bits context op 64-bits clients uit te breiden. Selecteer **Nee** (standaard) om padvariabelen in een 64-bits context op 64-bits clients uit te breiden. 32-bits clients gebruiken altijd de 32-bits context.
    - **Register**: Als u **Register** als **Vereistetype** kiest, moet de vereisteregel een registerinstelling op basis van een waarde, tekenreeks, geheel getal of versie selecteren.
        - **Sleutelpad**: het volledige pad van de registervermelding met de waarde die moet worden gedetecteerd.
        - **Waardenaam**: de naam van de registerwaarde die moet worden gedetecteerd. Als deze waarde leeg is, wordt de detectie op de sleutel uitgevoerd. De (standaard)waarde van een sleutel wordt als detectiewaarde gebruikt als de detectiemethode anders is dan het bestaan van het bestand of de map.
        - **Registersleutelvereiste**: selecteer het vergelijkingstype voor registersleutels dat u gebruikt om te bepalen hoe de vereisteregel moet worden gevalideerd.
        - **Gekoppeld aan een 32-bits app op 64-bits clients**: selecteer **Ja** om het 32-bits register te doorzoeken op 64-bits clients. Selecteer **Nee** (standaard) om het 64-bits register op 64-bits clients te doorzoeken. Voor 32-bits clients wordt altijd het 32-bits register doorzocht.
    - **Script**: Kies **Script** als **Vereistetype** als u geen vereisteregel kunt maken op basis van een bestand, register of een andere methode die voor u in de Intune-console beschikbaar is.
        - **Scriptbestand**: als de bestaanscode 0 is, detecteren we de STDOUT met meer details voor vereisteregels op basis van PowerShell-script. We kunnen STDOUT bijvoorbeeld als geheel getal met de waarde 1 detecteren.
        - **Script uitvoeren als 32-bits proces op 64-bits clients** - selecteer **Ja** om het script uit te voeren in een 32-bits proces op 64-bits clients. Selecteer **Nee** (standaard) om het script in een 64-bits proces op 64-bits clients uit te voeren. 32-bits clients voeren het script uit in een 32-bits proces.
        - **U kunt dit script als volgt uitvoeren met behulp van de aanmeldingsgegevens**: Selecteer **Ja** om het script uit te voeren met behulp van de referenties waarmee op het apparaat is aangemeld**.
        - **Controle van scripthandtekening afdwingen**: selecteer **Ja** om te verifiëren dat het script is ondertekend door een vertrouwde uitgever, zodat het script zonder waarschuwingen of prompts kan worden uitgevoerd. Het script wordt niet geblokkeerd terwijl het wordt uitgevoerd. Selecteer **Nee** (standaard) om het script met bevestiging van de eindgebruiker uit te voeren zonder handtekeningverificatie.
        - **Gegevenstype uitvoer selecteren**: Selecteer het gegevenstype dat is gebruikt voor het bepalen van de overeenkomst met een vereisteregel.
4. Klik op **OK** wanneer u klaar bent.

### <a name="step-6-configure-app-detection-rules"></a>Stap 6: app-detectieregels configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **Detectieregels** om de regels voor het detecteren van de aanwezigheid van de app te configureren.
2. Selecteer in het veld **Regelnotatie** hoe de aanwezigheid van de app moet worden gedetecteerd. U kunt de detectieregels handmatig configureren of een aangepast script gebruiken om de aanwezigheid van de app te detecteren. U moet minstens één detectieregel kiezen. 

    > [!NOTE]
    > U kunt in het deelvenster **Detectieregels** meerdere regels toevoegen. Er moet aan de voorwaarden van **alle** regels worden voldaan om de app te detecteren.

    - **Detectieregels handmatig configureren**: u kunt een van de volgende regeltypen selecteren:
        1. **MSI**: verifiëren op basis van een controle van de MSI-versie. Deze optie kan slechts eenmaal worden toegevoegd. Als u dit regeltype kiest, hebt u twee instellingen:
            - **MSI-productcode**: voeg een geldige MSI-productcode voor de app toe.
            - **Versiecontrole van MSI-product**: selecteer **Ja** om naast de MSI-productcode de productversie van MSI te controleren.
        2. **Bestand**: verifieer op basis van bestand- of mapdetectie, datum, versie of grootte.
            - **Pad**: het volledige pad van de map met het bestand of de map dat/die u wilt detecteren.
            - **Bestand of map**: het bestand of de map dat/die u wilt detecteren.
            - **Detectiemethode**: selecteer het type detectiemethode dat moet worden gebruikt om de aanwezigheid van de app te valideren.
            - **Gekoppeld aan een 32-bits app op 64-bits clients**: selecteer **Ja** om padomgevingsvariabelen in een 32-bits context op 64-bits clients uit te breiden. Selecteer **Nee** (standaard) om padvariabelen in een 64-bits context op 64-bits clients uit te breiden. 32-bits clients gebruiken altijd de 32-bits context.
            
            **Voorbeelden van detectie op basis van bestanden**
            1. Controleer op het bestaan van het bestand.
         
                ![Schermopname van het deelvenster Detectieregels: bestaan van bestand](./media/apps-win32-app-03.png)
        
            2. Controleer op het bestaan van de map.
         
                ![Schermopname van het deelvenster Detectieregels: bestaan van map](./media/apps-win32-app-04.png)
        
        3. **Register**: verifieer op basis van waarde, tekenreeks, geheel getal of versie.
            - **Sleutelpad**: het volledige pad van de registervermelding met de waarde die moet worden gedetecteerd.
            - **Waardenaam**: de naam van de registerwaarde die moet worden gedetecteerd. Als deze waarde leeg is, wordt de detectie op de sleutel uitgevoerd. De (standaard)waarde van een sleutel wordt als detectiewaarde gebruikt als de detectiemethode anders is dan het bestaan van het bestand of de map.
            - **Detectiemethode**: selecteer het type detectiemethode dat moet worden gebruikt om de aanwezigheid van de app te valideren.
            - **Gekoppeld aan een 32-bits app op 64-bits clients**: selecteer **Ja** om het 32-bits register te doorzoeken op 64-bits clients. Selecteer **Nee** (standaard) om het 64-bits register op 64-bits clients te doorzoeken. Voor 32-bits clients wordt altijd het 32-bits register doorzocht.
            
            **Voorbeelden voor detectie op basis van een register**
            1. Controleer of er een registersleutel bestaat.
            
                ![Schermopname van het deelvenster Detectieregels: registersleutel bestaat](./media/apps-win32-app-05.png)    
            
            2. Controleer of er registerwaarden bestaan.
        
                ![Schermopname van het deelvenster Detectieregels: registerwaarde bestaat](./media/apps-win32-app-06.png)    
        
            3. Controleer op gelijke tekenreeksen aan die van de registerwaarde.
        
                ![Schermopname van het deelvenster Detectieregels: gelijke tekenreeks registerwaarde](./media/apps-win32-app-07.png)    
     
    - **Een aangepast detectiescript gebruiken**: geef het PowerShell-script op dat wordt gebruikt voor het detecteren van deze app. 
    
        1. **Scriptbestand**: selecteer een PowerShell-script waarmee de aanwezigheid van de app op de client wordt gedetecteerd. De app worden gedetecteerd wanneer het script zowel een afsluitcode met waarde 0 retourneert als een tekenreekswaarde naar STDOUT schrijft.

        2. **Script uitvoeren als 32-bits proces op 64-bits clients** - selecteer **Ja** om het script uit te voeren in een 32-bits proces op 64-bits clients. Selecteer **Nee** (standaard) om het script in een 64-bits proces op 64-bits clients uit te voeren. 32-bits clients voeren het script uit in een 32-bits proces.

        3. **Controle van scripthandtekening afdwingen**: selecteer **Ja** om te verifiëren dat het script is ondertekend door een vertrouwde uitgever, zodat het script zonder waarschuwingen of prompts kan worden uitgevoerd. Het script wordt niet geblokkeerd terwijl het wordt uitgevoerd. Selecteer **Nee** (standaard) om het script met bevestiging van de eindgebruiker uit te voeren zonder handtekeningverificatie.
    
            Intune-agent controleert de resultaten vanuit het script. Het leest de waarden die door het script zijn geschreven naar de standaard uitvoerstroom (STDOUT), de standaardfoutstroom (STDERR) en de afsluitcode. Als het script wordt afgesloten met een andere waarde dan nul, mislukt het script en is de app-detectiestatus Niet geïnstalleerd. Als de afsluitcode nul is en STDOUT gegevens heeft, is de toepassingsdetectiestatus Geïnstalleerd. 

            > [!NOTE]
            > Microsoft adviseert om uw script te coderen als UTF-8. Als het script wordt afgesloten met de waarde 0, is de uitvoering van het script gelukt. Het tweede uitvoerkanaal geeft aan dat de app is gedetecteerd: STDOUT-gegevens geven aan dat de app is gevonden op de client. We zoeken niet naar een bepaalde tekenreeks van STDOUT.

        4. Nadat u uw regel(s) hebt toegevoegd, selecteert u **Toevoegen** > **OK**.

### <a name="step-7-configure-app-return-codes"></a>Stap 7: app-retourcodes configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **Retourcodes** om de retourcodes toe te voegen om het gedrag voor opnieuw proberen van de installatie of het gedrag na installatie voor de app op te geven. De retourcodevermeldingen worden tijdens het maken van een app standaard toegevoegd. U kunt echter aanvullende retourcodes toevoegen of bestaande retourcodes wijzigen. 
2. Voeg in he deelvenster **Retourcodes** extra retourcodes toe of wijzig bestaande retourcodes.
    - **Mislukt**: de retourwaarde die wijst op een app-installatiefout.
    - **Hard opstarten**: de retourcode voor hard opstarten staat niet toe dat de volgende Win32-apps worden geïnstalleerd op de client zonder opnieuw op te starten. 
    - **Zacht opstarten**: de retourcode voor zacht opstarten staat toe dat de volgende Win32-app wordt geïnstalleerd zonder dat de client opnieuw moet worden opgestart. Opnieuw opstarten is nodig om de installatie van de huidige app te voltooien.
    - **Opnieuw**: de retourcode-agent Opnieuw probeert de app drie keer te installeren. Er wordt tussen elke poging 5 minuten gewacht. 
    - **Gelukt**: de retourwaarde die aangeeft dat de app is geïnstalleerd.
3. Selecteer **OK** nadat u iets hebt toegevoegd aan de lijst met retourcodes of deze hebt aangepast.

### <a name="step-8-add-the-app"></a>Stap 8: De app toevoegen

1. Controleer in het deelvenster **App toevoegen** of de app-gegevens die u hebt geconfigureerd correct zijn.
2. Selecteer **Toevoegen** om de app te uploaden naar Intune.

### <a name="step-9-assign-the-app"></a>Stap 9: de app toewijzen

1. Selecteer in het deelvenster van de app de optie **Toewijzingen**.
2. Selecteer **Groep toevoegen** om het deelvenster **Groep toevoegen** te openen dat is gerelateerd aan de app.
3. Selecteer een **toewijzingstype** voor de specifieke app:
    - **Beschikbaar voor ingeschreven apparaten**: gebruikers installeren de app vanuit de bedrijfsportal-app of -website.
    - **Vereist**: de app wordt geïnstalleerd op apparaten in de geselecteerde groepen.
    - **Verwijderen**: de app wordt verwijderd van apparaten in de geselecteerde groepen.
4. Selecteer **Opgenomen groepen** en wijs de groepen toe die deze app gaan gebruiken.
5. Selecteer **OK** op het deelvenster **Toewijzen** de selectie te voltooien van de groepen die moeten worden opgenomen.
6. Selecteer **Groepen uitsluiten** als u gebruikersgroepen wilt uitsluiten zodat ze niet worden beïnvloed door deze app-toewijzing.
7. Selecteer **OK** in het deelvenster **Groep toevoegen**.
8. Selecteer **Opslaan** in het deelvenster **Toewijzingen**.

U hebt nu de stappen voor het toevoegen van een Win32-app aan Intune voltooid. Zie [Apps toewijzen aan groepen met Microsoft Intune](https://docs.microsoft.com/intune/apps-deploy) en [App-gegevens en -toewijzingen controleren met Microsoft Intune](https://docs.microsoft.com/intune/apps-monitor) voor meer informatie over app-toewijzing en -controle.

## <a name="app-dependencies"></a>App-afhankelijkheden

App-afhankelijkheden zijn toepassingen die moeten worden geïnstalleerd voordat u uw Win32-app kunt installeren. U kunt vereisen dat andere apps als afhankelijkheden worden geïnstalleerd. Specifiek moeten de afhankelijke apps op het apparaat worden geïnstalleerd vóór u de Win32-app installeert. Er is een maximum van 100 afhankelijkheden. Dit is inclusief de afhankelijkheden van eventueel opgenomen afhankelijkheden en de app zelf. U kunt alleen Win32-afhankelijkheden toevoegen nadat uw Win32-app is toegevoegd en naar Intune is geüpload. Zodra uw Win32-app is toegevoegd, ziet u de optie **Afhankelijkheden** op de blade voor uw Win32-app. 

Wanneer u een app-afhankelijkheid toevoegt, kunt u een zoekopdracht uitvoeren op basis van de naam en uitgever van de app. Daarnaast kunt u de toegevoegde afhankelijkheden sorteren op basis van de naam en uitgever van de app. Eerder toegevoegde app-afhankelijkheden kunnen niet worden geselecteerd in de lijst met toegevoegde app-afhankelijkheden. 

U kunt kiezen of elke afhankelijke app automatisch moet worden geïnstalleerd. Standaard is de optie **Automatisch installeren** voor elke afhankelijkheid ingesteld op **Ja**. Door automatisch een afhankelijke app te installeren, zelfs als de afhankelijke app niet op de gebruiker of het apparaat is gericht, installeert Intune de app op het apparaat om aan de afhankelijkheid te voldoen voordat u uw Win32-app installeert. Let op: een afhankelijkheid kan over recursieve onderliggende afhankelijkheden beschikken en elke onderliggende afhankelijkheid wordt geïnstalleerd vóór de hoofdafhankelijkheid wordt geïnstalleerd. Daarnaast worden afhankelijkheden niet volgens een bepaalde installatievolgorde bij een gegeven afhankelijkheidsniveau geïnstalleerd.

U kunt met de volgende stappen een app-afhankelijkheid aan uw Win32-app toevoegen:

1. Selecteer **Client-apps** > **Apps** in Intune om uw lijst met toegevoegde client-apps weer te geven. 
2. Selecteer een toegevoegde **Windows-app (Win32-app)**. 
3. Selecteer **Afhankelijkheden** om de afhankelijke apps toe te voegen die moeten worden geïnstalleerd voordat de Win32-app kan worden geïnstalleerd. 
4. Klik op **Toevoegen** om een app-afhankelijkheid toe te voegen.
5. Zodra u de afhankelijke app(s) hebt toegevoegd, klikt u op **Selecteren**.
6. Selecteer **Ja** of **Nee** onder **Automatisch installeren** om te kiezen of de afhankelijke app automatisch moet worden geïnstalleerd.
7. Klik op **Opslaan**.

Eindgebruikers zien pop-upmeldingen van Windows die aangeven dat er afhankelijke apps worden gedownload en geïnstalleerd als onderdeel van het installatieproces van de Win32-app. Daarnaast zien eindgebruikers over het algemeen een van de volgende meldingen als een afhankelijke app niet is geïnstalleerd:
- Een of meer afhankelijke apps kunnen niet worden geïnstalleerd
- Er is niet voldaan aan een of meer vereisten voor afhankelijke apps
- Een of meer afhankelijke apps zijn in afwachting van het opnieuw opstarten van het apparaat

Als u een afhankelijkheid niet **automatisch wilt installeren**, wordt de installatie van de Win32-app niet gestart. Daarnaast wordt in een app-rapport aangegeven dat de afhankelijkheid als `failed` is gemarkeerd. Ook wordt een reden opgegeven waarom de installatie niet is gelukt. Klik op een fout (of waarschuwing) in de [installatiedetails](troubleshoot-app-install.md#win32-app-installation-troubleshooting) van de Win32-app om de installatiefout van de afhankelijkheid weer te geven. 

Op elke afhankelijkheid wordt de Intune Win32-app-logica voor opnieuw proberen (drie keer opnieuw proberen te installeren na 5 minuten wachten) en de algemene planning voor opnieuw beoordelen toegepast. Daarnaast zijn afhankelijkheden alleen van toepassing tijdens de installatie van de Win32-app op het apparaat. Afhankelijkheden zijn niet van toepassing bij het verwijderen van een Win32-app. Als u een afhankelijkheid wilt verwijderen, klikt u op het weglatingsteken (drie puntjes) links naast de afhankelijke app, aan het einde van de rij van de lijst met afhankelijkheden. 

## <a name="delivery-optimization"></a>Delivery optimization

Clients van Windows 10 1709 en hoger downloaden Intune Win32-app-inhoud via een delivery optimization-onderdeel in de Windows 10-client. Delivery optimization biedt peer-to-peer-functionaliteit die standaard is ingeschakeld. Delivery Optimization kan worden geconfigureerd via groepsbeleid en via de Intune-apparaatconfiguratie. Raadpleeg [Delivery Optimization voor Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) voor meer informatie. 

## <a name="install-required-and-available-apps-on-devices"></a>Vereiste installatie en beschikbare apps op apparaten

De eindgebruiker ziet de pop-upmeldingen van Windows voor de vereiste en beschikbare app-installaties. De volgende afbeelding toont een voorbeeld van de pop-upmelding wanneer de app-installatie pas wordt voltooid wanneer het apparaat opnieuw wordt opgestart. 

![Schermafbeelding van pop-upmeldingen van Windows voor een app-installatie](./media/apps-win32-app-08.png)    

De volgende afbeelding informeert de eindgebruiker dat er app-wijzigingen worden aangebracht aan het apparaat.

![Schermafbeelding die aan de gebruiker meldt dat er wijzigingen aan de app worden uitgevoerd](./media/apps-win32-app-09.png)    

## <a name="toast-notifications-for-win32-apps"></a>Toast-meldingen voor Win32-apps 
Indien nodig, kunt u per app-toewijzing onderdrukken dat toast-meldingen voor eindgebruikers worden weergegeven. Selecteer vanuit Intune de optie **Client-apps** > **Apps** > selecteer de app > **Toewijzingen** > **Groepen opnemen**. 

> [!NOTE]
> Win32-apps waarvoor de Intune-beheerextensie is geïnstalleerd, worden niet verwijderd van apparaten die niet meer ingeschreven zijn. Beheerders kunnen gebruikmaken van uitsluiting van opdrachten, zodat Win32-apps niet worden aangeboden op BYOD-apparaten.

## <a name="troubleshoot-win32-app-issues"></a>Problemen met Win32-apps oplossen
Agentlogboeken op de clientcomputer staan doorgaans in `C:\ProgramData\Microsoft\IntuneManagementExtension\Logs`. U kunt `CMTrace.exe` gebruiken om deze logboekbestanden weer te geven. *CMTrace.exe* kan worden gedownload via [Configuration Manager-clienthulpprogramma's](https://docs.microsoft.com/sccm/core/support/tools). 

![Schermafbeelding van de agentlogboeken op de clientcomputer](./media/apps-win32-app-10.png)    

> [!IMPORTANT]
> Als u wilt toestaan dat LOB Win32-apps goed worden geïnstalleerd en uitgevoerd, moeten via de antimalware-instellingen worden ingesteld dat de volgende mappen niet worden gescand:<p>
> **Voor X64-clientcomputers**:<br>
> *C:\Program Files (x86)\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*
>  
> **Voor X86-clientcomputers**:<br>
> *C:\Program Files\Microsoft Intune Management Extension\Content*<br>
> *C:\windows\IMECache*

### <a name="detecting-the-win32-app-file-version-using-powershell"></a>De bestandsversie van de Win32-app detecteren met behulp van PowerShell

Als u problemen ondervindt bij het detecteren van de bestandsversie van de Win32-app, kunt u de volgende PowerShell-opdracht gebruiken of aanpassen:

``` PowerShell

$FileVersion = [System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion
#The below line trims the spaces before and after the version name
$FileVersion = $FileVersion.Trim();
if ("<file version of successfully detected file>" -eq $FileVersion)
{
#Write the version to STDOUT by default
$FileVersion
exit 0
}
else
{
#Exit with non-zero failure code
exit 1
}

```
Vervang in de bovenstaande PowerShell-opdracht de tekenreeks `<path to binary file>` door het pad naar uw Win32-appbestand. Een voorbeeld van een pad ziet er als volgt uit:<br>
`C:\Program Files (x86)\Microsoft SQL Server Management Studio 18\Common7\IDE\ssms.exe`

Vervang ook de tekenreeks `<file version of successfully detected file>` door de bestandsversie die u moet detecteren. Een voorbeeld van een tekenreeks voor een bestandsversie ziet er als volgt uit:<br>
`2019.0150.18118.00 ((SSMS_Rel).190420-0019)`

Als u de versiegegevens van uw Win32-app moet ophalen, kunt u de volgende PowerShell-opdracht gebruiken:

``` PowerShell

[System.Diagnostics.FileVersionInfo]::GetVersionInfo("<path to binary file>").FileVersion

```

Vervang in de bovenstaande PowerShell-opdracht `<path to binary file>` door het bestandspad.

### <a name="additional-troubleshooting-areas-to-consider"></a>Aanvullende gebieden voor probleemoplossing die u kunt overwegen
- Controleer de targeting om ervoor te zorgen dat de agent op het apparaat is geïnstalleerd: een Win32-app gericht op een groep of een PowerShell-Script gericht op een groep maken een agentinstallatiebeleid voor de beveiligingsgroep.
- Controleer de versie van het besturingssysteem: Windows 10 1607 en hoger.  
- Controleer de Windows 10-SKU; Windows 10 S en Windows-versies met de S-modus ingeschakeld bieden geen ondersteuning voor MSI-installatie.

Zie [Problemen met de installatie van Win32-apps oplossen](troubleshoot-app-install.md#win32-app-installation-troubleshooting) voor meer informatie over het oplossen van problemen met Win32-apps.

## <a name="next-steps"></a>Volgende stappen

- Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over apps toevoegen aan Intune.
