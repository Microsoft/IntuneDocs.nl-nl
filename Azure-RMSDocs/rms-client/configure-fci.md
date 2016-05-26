---
# required metadata

title: RMS-beveiliging met infrastructuur voor bestandsclassificatie (FCI) voor Windows Server | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 9aa693db-9727-4284-9f64-867681e114c9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# RMS-beveiliging met infrastructuur voor bestandsclassificatie (FCI) voor Windows Server

*Van toepassing op: Azure Rights Management, Windows Server 2012, Windows Server 2012 R2*

Dit artikel bevat instructies en een script om de Rights Management-client (RMS) te gebruiken met het RMS-beveiligingshulpprogramma voor het configureren van Bestandsserverbronbeheer en de infrastructuur voor bestandsclassificatie (FCI).

Met deze oplossingen kunt u automatisch alle bestanden beveiligen die zich in een map op een bestandsserver met Windows Server bevinden, of automatisch bestanden beveiligen die aan een bepaald criterium voldoen. Bijvoorbeeld bestanden die zijn geclassificeerd als vertrouwelijk of die gevoelige gegevens bevatten. Deze oplossing gebruikt Azure Rights Management (Azure RMS) om de bestanden te beveiligen. U moet deze technologie daarom hebben geïmplementeerd in uw organisatie.

> [!NOTE]
> Hoewel Azure RMS een [connector](../deploy-use/deploy-rms-connector.md) bevat die infrastructuur voor bestandsclassificatie ondersteunt, ondersteunt die oplossing alleen systeemeigen beveiliging, bijvoorbeeld Office-bestanden.
> 
> Als u alle bestandstypen wilt ondersteunen met infrastructuur voor bestandsclassificatie, moet u de Windows PowerShell-module **RMS-beveiliging** gebruiken, zoals beschreven in dit artikel. De RMS-beveiligingscmdlets ondersteunen net als de RMS-toepassing voor delen, zowel algemene beveiliging als systeemeigen beveiliging, wat betekent dat alle bestanden kunnen worden beveiligd. Zie de sectie [Beveiligingsniveaus: systeemeigen en algemeen](sharing-app-admin-guide-technical.md#levels-of-protection-native-and-generic) in de [Beheerdershandleiding voor de Rights Management-toepassing voor delen](sharing-app-admin-guide.md) voor meer informatie over deze verschillende beveiligingsniveaus.

De volgende instructies zijn van toepassing voor Windows Server 2012 R2 of Windows Server 2012. Als u andere ondersteunde versies van Windows uitvoert, moet u mogelijk enkele van de stappen aanpassen vanwege verschillen tussen uw besturingssysteemversie en de versie die in dit artikel wordt beschreven.

## Vereisten voor Azure RMS-beveiliging met Windows Server FCI
Vereisten voor deze instructies:

-   Op elke bestandsserver waarop Bestandsserverbronbeheer met infrastructuur voor bestandsclassificatie wordt uitgevoerd:

    -   Bestandsserverbronbeheer is geïnstalleerd als een van de functieservices voor de functie Bestandsservices.

    -   U hebt een lokale map geïdentificeerd die bestanden bevat die moeten worden beveiligd met Rights Management. Bijvoorbeeld C:\FileShare.

    -   U hebt het RMS-beveiligingshulpprogramma geïnstalleerd, inclusief de vereisten voor het hulpprogramma (zoals de RMS-client) en voor Azure RMS (zoals het account van de service-principal). Zie [RMS Protection Cmdlets](https://msdn.microsoft.com/library/azure/mt433195.aspx) (RMS-beveiligingscmdlets) voor meer informatie.

    -   Als u het standaardniveau van de RMS-beveiliging (systeemeigen of algemeen) wilt wijzigen voor specifieke bestandsnaamextensies, hebt u het register bewerkt zoals beschreven op de pagina [Configuratie van bestands-API](https://msdn.microsoft.com/library/dn197834%28v=vs.85%29.aspx).

    -   U hebt een internetverbinding met geconfigureerde computerinstellingen voor een proxyserver, indien vereist. Bijvoorbeeld: `netsh winhttp import proxy source=ie`

-   U hebt de aanvullende vereisten geconfigureerd voor de Azure Rights Management-implementatie, zoals beschreven in [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx). U hebt de volgende waarden om verbinding te maken met Azure RMS met een service-principal:

    -   BposTenantId

    -   AppPrincipalId

    -   Symmetrische sleutel

-   U hebt de on-premises Active Directory-gebruikersaccounts gesynchroniseerd met Azure Active Directory of Office 365, met inbegrip van de bijbehorende e-mailadressen. Dit is vereist voor alle gebruikers die mogelijk toegang moeten hebben tot de bestanden nadat deze door FCI en Azure RMS zijn beveiligd. Als u deze stap (bijvoorbeeld in een testomgeving) niet uitvoert, wordt de toegang tot deze bestanden mogelijk geblokkeerd voor gebruikers. Zie [Voorbereiden voor Azure Rights Management](../plan-design/prepare.md) als u meer informatie nodig hebt over deze accountconfiguratie.

-   U hebt vastgesteld welke de Rights Management-sjabloon moet worden gebruikt, waarmee de bestanden worden beveiligd. Zorg ervoor dat u de ID voor deze sjabloon kent door gebruik te maken van de cmdlet [Get-RMSTemplate](https://msdn.microsoft.com/library/azure/mt433197.aspx).

## Instructies voor het configureren van Bestandsserverbronbeheer FCI voor Azure RMS-beveiliging
Volg deze instructies voor het automatisch beveiligen van alle bestanden in een map met een Windows PowerShell-script als aangepaste taak. Voer deze procedures in deze volgorde uit:

1.  Sla het Windows PowerShell-script op

2.  Maak een classificatie-eigenschap voor Rights Management (RMS)

3.  Maak een classificatieregel (classificeren voor RMS)

4.  Configureer het classificatieschema

5.  Maak een aangepaste bestandsbeheertaak (bestanden beveiligen met RMS)

6.  Test de configuratie door de regel en taak handmatig uit te voeren

Nadat u deze instructies hebt uitgevoerd, zijn alle bestanden in de geselecteerde map geclassificeerd met de aangepaste eigenschap van RMS en worden deze bestanden vervolgens beveiligd door Rights Management. Als u een complexere configuratie wilt maken waarbij sommige bestanden wel en andere bestanden niet worden beveiligd, maakt of gebruikt u vervolgens een andere classificatie-eigenschap met een bestandsbeheertaak waarmee alleen die bestanden worden beveiligd.

### Sla het Windows PowerShell-script op

1.  Kopieer de inhoud van het [Windows PowerShell-script](fci-script.md) voor Azure RMS-beveiliging met Bestandsserverbronbeheer. Plak de inhoud van het script in een bestand en sla dit onder de naam **RMS-Protect-FCI.ps1** op uw eigen computer op.

2.  Bekijk het script en breng de volgende wijzigingen aan:

    -   Zoek naar de volgende tekenreeks en vervang deze door uw eigen AppPrincipalId die u gebruikt met de cmdlet [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx) om verbinding te maken met Azure RMS:

        ```
        <enter your AppPrincipalId here>
        ```
        Dit script kan er als volgt uitzien:

        `[Parameter(Mandatory = $false)]`

        `[Parameter(Mandatory = $false)]             [string]$AppPrincipalId = "b5e3f76a-b5c2-4c96-a594-a0807f65bba4",`

    -   Zoeken naar de volgende tekenreeks en vervang deze door uw eigen symmetrische sleutel die u gebruikt met de cmdlet [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx) om verbinding te maken met Azure RMS:

        ```
        <enter your key here>
        ```
        Dit script kan er als volgt uitzien:

        `[Parameter(Mandatory = $false)]`

        `[string]$SymmetricKey = "zIeMu8zNJ6U377CLtppkhkbl4gjodmYSXUVwAO5ycgA="`

    -   Zoek naar de volgende tekenreeks en vervang deze door uw eigen BposTenantId (tenant-id) die u gebruikt met de cmdlet [Set-RMSServerAuthentication](https://msdn.microsoft.com/library/mt433199.aspx) om verbinding te maken met Azure RMS:

        ```
        <enter your BposTenantId here>
        ```
        Dit script kan er als volgt uitzien:

        `[Parameter(Mandatory = $false)]`

        `[string]$BposTenantId = "23976bc6-dcd4-4173-9d96-dad1f48efd42",`

    -   Als op uw server Windows Server 2012 wordt uitgevoerd, moet u aan het begin van het script wellicht de module RMSProtection handmatig laden. Voeg de volgende opdracht toe (of een gelijkwaardige opdracht als de map 'Program Files' zich op een ander station dan het station C bevindt:

        ```
        Import-Module "C:\Program Files\WindowsPowerShell\Modules\RMSProtection\RMSProtection.dll"
        ```

3.  Onderteken het script. Als u het script (veiliger) niet ondertekent, moet u Windows PowerShell configureren op de servers waarop het script wordt uitgevoerd. Voer bijvoorbeeld een Windows PowerShell-sessie uit met de optie **Als beheerder uitvoeren** en typ: **Set-ExecutionPolicy Unrestricted**. Met deze configuratie kunnen echter alle niet-ondertekende scripts worden uitgevoerd (minder veilig).

    Zie [about_Signing](https://technet.microsoft.com/library/hh847874.aspx) in de PowerShell-documentatiebibliotheek voor meer informatie over het ondertekenen van Windows PowerShell-scripts.

4.  Sla het bestand op elke bestandsserver op waarop Bestandsserverbronbeheer met infrastructuur voor bestandsclassificatie wordt uitgevoerd: Sla het bestand bijvoorbeeld op in **C:\RMS-Protection**. Beveilig dit bestand met NTFS-machtigingen zodat niet-geautoriseerde gebruikers het bestand niet kunnen wijzigen.

U bent nu klaar om te beginnen met de configuratie van Bestandsserverbronbeheer.

### Maak een classificatie-eigenschap voor Rights Management (RMS)

-   Maak in Bestandsserverbronbeheer, Classificatiebeheer, een nieuwe lokale eigenschap:

    -   **Naam**: type **RMS**

    -   **Beschrijving**: type **Rights Management-beveiliging**

    -   **Type eigenschap**: selecteer **Ja/Nee**

    -   **Waarde**: selecteer **Ja**

Er kan nu een classificatieregel worden gemaakt die deze eigenschap gebruikt.

### Maak een classificatieregel (classificeren voor RMS)

-   Maak een nieuwe classificatieregel:

    -   Op het tabblad **Algemeen**:

        -   **Naam**: type **Classificeren voor RMS**

        -   **Ingeschakeld**: behoud de standaardwaarde en laat dit selectievakje ingeschakeld.

        -   **Beschrijving**: type **Alle bestanden classificeren in de map &lt;mapnaam&gt; voor Rights Management**.

            Vervang *&lt;mapnaam&gt;* door de door u gekozen mapnaam. Bijvoorbeeld **Alle bestanden classificeren in C:\FileShare-map voor Rights Management**

        -   **Bereik**: voeg uw gekozen map toe. Bijvoorbeeld **C:\FileShare**.

            Schakel de selectievakjes niet in.

    -   Op het tabblad **Classificatie**:

    -   **Classificatiemethode**: selecteer **Classificeerder voor map**

    -   Naam **Eigenschap**: selecteer **RMS**

    -   Waarde **Eigenschap**: selecteer **Ja**

Hoewel u de classificatieregels handmatig kunt uitvoeren, wordt aangeraden voor lopende bewerkingen u deze regel volgens een planning uit te voeren, zodat nieuwe bestanden met de RMS-eigenschap worden geclassificeerd.

### Configureer het classificatieschema

-   Op het tabblad **Automatische classificatie**:

    -   **Vast schema inschakelen**: schakel dit selectievakje in.

    -   Configureer de planning voor het uitvoeren van alle classificatieregels, waaronder de nieuwe regel voor het classificeren van bestanden met de RMS-eigenschap.

    -   **Continue classificatie voor nieuwe bestanden toestaan**: schakel dit selectievakje in zodat nieuwe bestanden wordt geclassificeerd.

    -   Optioneel: breng indien gewenst andere wijzigingen aan, zoals het configureren van opties voor rapporten en meldingen.

Nu de configuratie van de classificatie is voltooid, bent u klaar om een beheertaak te configureren om RMS-beveiliging toe te passen op de bestanden.

### Maak een aangepaste bestandsbeheertaak (bestanden beveiligen met RMS)

-   Maak in **Bestandsbeheertaken** een nieuwe bestandsbeheertaak:

    -   Op het tabblad **Algemeen**:

        -   **Taaknaam**: type **Bestanden beveiligen met RMS**

        -   Houd het selectievakje **Inschakelen** ingeschakeld.

        -   **Beschrijving**: type **Bestanden beveiligen in &lt;mapnaam&gt; met Rights Management en een sjabloon met een Windows PowerShell-script.**

            Vervang *&lt;mapnaam&gt;* door de door u gekozen mapnaam. Bijvoorbeeld **Bestanden beveiligen in C:\FileShare met Rights Management en een sjabloon met een Windows PowerShell-script**

        -   **Bereik**: selecteer de door u gekozen map. Bijvoorbeeld **C:\FileShare**.

            Schakel de selectievakjes niet in.

    -   Op het tabblad **Actie**:

        -   **Type**: selecteer **Aangepast**

        -   **Uitvoerbaar bestand**: geef het volgende op:

            ```
            C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
            ```
            Wijzig dit pad op of blader naar dit bestand als Windows zich niet op station C bevindt.

        -   **Argument**: geef het volgende op en verstrek hierbij uw eigen waarden voor &lt;Pad&gt; en &lt;Sjabloon-id&gt;:

            ```
            -Noprofile -Command "<path>\RMS-Protect-FCI.ps1 -File '[Source File Path]' -TemplateID <template GUID> -OwnerMail [Source File Owner Email]"
            ```
            Als u bijvoorbeeld het script hebt gekopieerd naar C:\RMS-Protection en de sjabloon-id die u hebt geïdentificeerd uit de vereisten is e6ee2481-26b9-45e5-b34a-f744eacd53b0, geeft u het volgende op:

            `-Noprofile -Command "C:\RMS-Protection\RMS-Protect-FCI.ps1 -File '[Source File Path]' -TemplateID e6ee2481-26b9-45e5-b34a-f744eacd53b0 -OwnerMail [Source File Owner Email]"`

            In deze opdracht zijn **[Bronbestandspad]** en **[E-mailadres eigenaar bronbestand]** beide FCI-specifieke variabelen. Typ deze waarden dus exact in zoals ze worden weergegeven in de bovenstaande opdracht. De eerste waarde wordt gebruikt door FCI om automatisch het geïdentificeerde bestand op te geven in de map en met de tweede haalt FCI automatisch het e-mailadres van de benoemde eigenaar van het geïdentificeerde bestand op. Deze opdracht wordt herhaald voor elk bestand in de map. In dit voorbeeld is dit elk bestand in de map C:\FileShare dat bovendien de bestandsclassificatie-eigenschap RMS heeft.

            > [!NOTE]
            > De parameter **- OwnerMail [E-mailadres eigenaar bronbestand]** en de waarde zorgen ervoor dat aan de oorspronkelijke eigenaar van het bestand de status Rights Management-bestandseigenaar wordt verleend nadat het is beveiligd. Dit zorgt ervoor dat de oorspronkelijke bestandseigenaar over alle Rights Management-rechten voor zijn eigen bestanden beschikt. Wanneer bestanden worden gemaakt door een domeingebruiker, wordt het e-mailadres automatisch opgehaald uit Active Directory via de naam van het gebruikersaccount in de eigenschap Eigenaar van het bestand. Hiervoor moet de bestandsserver zich in hetzelfde domein of vertrouwd domein bevinden als de gebruiker.
            > 
            > Wijs indien mogelijk de oorspronkelijke eigenaar aan beveiligde documenten toe, om ervoor te zorgen dat deze gebruikers de volledige controle houden over de bestanden die ze hebben gemaakt. Als u echter de variabele [E-mailadres eigenaar bronbestand] gebruikt, zoals hierboven, en een bestand geen domeingebruiker heeft die is gedefinieerd als de eigenaar (bijvoorbeeld wanneer een lokaal account is gebruikt voor het maken van het bestand, zodat als eigenaar SYSTEM wordt weergegeven), mislukt het script.
            > 
            > Bestanden die geen domeingebruiker als eigenaar hebben, kunt u zelf als domeingebruiker kopiëren en opslaan, zodat u alleen voor deze bestanden de eigenaar wordt. Als u over de benodigde machtigingen beschikt, kunt u de eigenaar handmatig wijzigen.  U kunt ook een specifiek e-mailadres opgeven (zoals uw eigen adres of een groepsadres van de IT-afdeling) in plaats van de variabele [E-mailadres eigenaar bronbestand]. Op die manier gebruiken alle bestanden die u met dit script beveiligt dit e-mailadres voor het definiëren van de nieuwe eigenaar.

    -   **Voer de opdracht uit als**: selecteer **Lokaal systeem**

    -   Op het tabblad **Voorwaarde**:

        -   **Eigenschap**: Selecteer **RMS**

        -   **Operator**: selecteer **Gelijk**

        -   **Waarde**: selecteer **Ja**

    -   Op het tabblad **Planning**:

        -   **Uitvoeren op**: configureer uw voorkeursplanning.

            Zorg voor voldoende tijd om het script te voltooien. Hoewel deze oplossing alle bestanden in de map beveiligt, wordt het script voor elke keer één keer uitgevoerd voor elk bestand. Hoewel dit langer duurt dan het tegelijkertijd beveiligen van alle bestanden, wat door het RMS-beveiligingshulpprogramma wordt ondersteunt, is deze configuratie per bestand voor FCI krachtiger. De beveiligde bestanden kunnen bijvoorbeeld verschillende eigenaars hebben (behoud de oorspronkelijke eigenaar) wanneer u de variabele [E-mailadres eigenaar bronbestand] gebruikt. Deze actie per bestand is vereist als u de configuratie op een later tijdstip wijzigt naar het selectief beveiligen van bestanden in plaats van het beveiligen van alle bestanden in een map.

        -   **Taak continu uitvoeren voor nieuwe bestanden**: schakel dit selectievakje in.

### Test de configuratie door de regel en taak handmatig uit te voeren

1.  Voer de classificatieregel uit:

    1.  Klik op **Classificatieregels** &gt; **Classificatie nu met alle regels uitvoeren**

    2.  Klik op **Wachten totdat de classificatie is voltooid** en klik vervolgens op **OK**..

2.  Wacht totdat het dialoogvenster **Classificatie wordt uitgevoerd** wordt gesloten en bekijk vervolgens de resultaten in het rapport dat automatisch wordt weergegeven. U ziet **1** voor het veld **Eigenschappen** en het aantal bestanden in de map. Bevestig dit met Bestandenverkenner en controleer de eigenschappen van bestanden in de gekozen map. Op het tabblad **Classificatie** ziet u **RMS** als eigenschapsnaam en **Ja** voor de **Waarde**.

3.  Voer de bestandsbeheertaak uit:

    1.  Klik op **Bestandsbeheertaken** &gt; **Bestanden beveiligen met RMS** &gt; **Bestandsbeheertaak nu uitvoeren**

    2.  Klik op **Wachten totdat de taak is voltooid** en klik vervolgens op **OK**..

4.  Wacht totdat het dialoogvenster **Bestandsbeheertaak wordt uitgevoerd** wordt gesloten en bekijk vervolgens de resultaten in het rapport dat automatisch wordt weergegeven. U ziet het aantal bestanden in de door u gekozen map in het veld **Bestanden**. Controleer of de bestanden in de door u gekozen map nu zijn beveiligd door RMS. Als u bijvoorbeeld de map C:\FileShare hebt gekozen, typt u het volgende in een Windows PowerShell-sessie en controleert u of er geen bestanden zijn met de status **UnProtected**:

    ```
    foreach ($file in (Get-ChildItem -Path C:\FileShare -Force | where {!$_.PSIsContainer})) {Get-RMSFileStatus -f $file.PSPath}
    ```
    > [!TIP]
    > Tips voor probleemoplossing:
    > 
    > -   Als u in het rapport **0** ziet, in plaats van het aantal bestanden in de map, geeft dit aan dat het script niet is uitgevoerd. Controleer eerst het script zelf door dit te laden in Windows PowerShell ISE om de inhoud van het script te valideren, en voer het uit om te zien of er fouten worden weergegeven. Als er geen argumenten zijn opgegeven, maakt het script verbinding met Azure RMS voor verificatie.
    > 
    >     -   Als het script rapporteert dat dit geen verbinding kan maken met Azure RMS, controleert u de waarden die worden weergegeven voor het principal-serviceaccount dat u in het script hebt opgegeven.  Zie de tweede voorwaarde in [about_RMSProtection_AzureRMS](https://msdn.microsoft.com/library/mt433202.aspx) voor meer informatie over het maken van dit service-principalaccount
    >     -   Als het script rapporteert dat het verbinding kan maken met Azure RMS, voert u vervolgens [Get-RMSTemplate](https://msdn.microsoft.com/library/mt433197.aspx) rechtstreeks vanuit de Windows PowerShell op de server uit om te controleren of de opgegeven sjabloon kan worden gevonden. De sjabloon die u hebt opgegeven, wordt in de resultaten geretourneerd.
    > -   Als het script zelf foutloos wordt uitgevoerd in Windows PowerShell ISE, voert u het vervolgens uit vanuit een PowerShell-sessie. Geef hierbij de naam op van een bestand dat moet worden beveiligd, zonder de parameter - OwnerEmail:
    > 
    >     ```
    >     powershell.exe -Noprofile -Command "<path>\RMS-Protect-FCI.ps1 -File '<full path and name of a file>' -TemplateID <template GUID>"
    >     ```
    >     -   Als het script in deze Windows PowerShell-sessie correct wordt uitgevoerd, controleert u de invoer voor **Executive** en **Argument** in de actie bestandsbeheertaak.  Als u **- OwnerEmail [E-mailadres eigenaar bronbestand]** hebt opgegeven, verwijdert u deze parameter.
    > 
    >         Als de bestandsbeheertaak correct wordt uitgevoerd zonder **- OwnerEmail [E-mailadres eigenaar bronbestand]**, controleert u of voor de niet-beveiligde bestanden een domeingebruiker is opgegeven als bestandseigenaar, in plaats van **SYSTEM**.  Ga hiervoor naar het tabblad **Beveiliging** voor de bestandseigenschappen en klik vervolgens op **Geavanceerd**. De waarde **Eigenaar** wordt direct na de **Naam** van het bestand weergegeven. Controleer ook of de bestandsserver zich in hetzelfde domein of vertrouwd domein bevindt om het e-mailadres van de gebruiker uit Active Directory Domain Services op te zoeken.
    > -   Als u het juiste aantal bestanden in het rapport ziet, maar de bestanden niet zijn beveiligd, beveiligt u de bestanden handmatig met de cmdlet [Protect-RMSFile](https://msdn.microsoft.com/library/azure/mt433201.aspx) om te zien of er fouten worden weergegeven.

Wanneer u hebt vastgesteld dat deze taken correct worden uitgevoerd, kunt u Bestandsserverbronbeheer sluiten. Nieuwe bestanden worden automatisch beveiligd en alle bestanden worden opnieuw beveiligd wanneer de planning wordt uitgevoerd. Als u de bestanden opnieuw beveiligt, bent u ervan verzekerd dat eventuele wijzigingen in de sjabloon worden toegepast op de bestanden.


## De instructies wijzigen om selectief bestanden te beveiligen
Wanneer de voorgaande instructies werken, kunt u deze zeer eenvoudig wijzigen voor een meer geavanceerde configuratie. U kunt bijvoorbeeld bestanden beveiligen met hetzelfde script, maar dit alleen toepassen op bestanden die persoonlijk gegevens bevatten, en mogelijk een sjabloon selecteren met beperktere rechten.

Hiervoor gebruikt u een van de ingebouwde classificatie-eigenschappen (bijvoorbeeld **Persoonlijke gegevens**), maar u kunt ook uw eigen nieuwe eigenschap maken. Vervolgens maakt u een nieuwe regel waarvoor deze eigenschap wordt gebruikt. U kunt bijvoorbeeld de **Content Classifier** selecteren, de eigenschap **Persoonlijke gegevens ** kiezen met de waarde **Hoog** en de tekenreeks of het expressiepatroon configureren waarmee het bestand wordt geïdentificeerd dat moet worden geconfigureerd voor deze eigenschap (bijvoorbeeld de tekenreeks **Geboortedatum**").

Nu hoeft u alleen nog maar een nieuwe bestandsbeheertaak te maken die hetzelfde script gebruikt (mogelijk met een andere sjabloon) en de voorwaarde te configureren voor de classificatie-eigenschap die u zojuist hebt geconfigureerd. In plaats van de eerder geconfigureerde voorwaarde (eigenschap **RMS** **Gelijk**, **Ja**), kunt u bijvoorbeeld de eigenschap **Persoonlijke gegevens** selecteren en de waarde **Operator** instellen op **Gelijk** en de **Waarde** op **Hoog**.



<!--HONumber=Apr16_HO4-->


