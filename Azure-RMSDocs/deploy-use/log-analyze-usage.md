---
# required metadata

title: Azure Rights Management-gebruik analyseren en vastleggen in een logboek | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 05/13/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a735f3f7-6eb2-4901-9084-8c3cd3a9087e

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure Rights Management-gebruik analyseren en vastleggen in een logboek

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de informatie in dit onderwerp om te zien hoe u logboekregistratie van het gebruik met Azure Rights Management (Azure RMS) kunt gebruiken. De Azure Rights Management-service kan elke aanvraag die voor uw organisatie wordt uitgevoerd, registreren in een logboek, inclusief aanvragen van gebruikers, acties die worden uitgevoerd door Rights Management-beheerders in uw organisatie en acties die ter ondersteuning van uw Azure Rights Management-implementatie worden uitgevoerd door Microsoft-operators.

U kunt deze Azure Rights Management-logboeken gebruiken ter ondersteuning van de volgende bedrijfsscenario's:

-   **Analyseren voor zakelijke inzichten**

    De logboeken die worden gegenereerd door Azure Rights Management, kunnen worden geïmporteerd in een opslagplaats van uw keuze (zoals een database, een OLAP-systeem (Online Analytical Processing) of een MapReduce-systeem) om de informatie te analyseren en rapporten te produceren. U kunt bijvoorbeeld controleren wie de gegevens weergeeft die zijn beveiligd met RMS. U kunt bepalen tot welke met RMS beveiligde gegevens mensen toegang hebben en met welke apparaten en vanaf welke locatie. U kunt achterhalen of mensen de beveiligde gegevens kunnen lezen. U kunt ook zien welke mensen een belangrijk beveiligd document hebben gelezen.

-   **Controleren op misbruik**

    De logboekinformatie voor Azure Rights Management is vrijwel in realtime beschikbaar, zodat u voortdurend het gebruik van Rights Management binnen uw bedrijf in de gaten kunt houden. 99,9% van alle logboeken is binnen vijftien minuten na een RMS-actie beschikbaar.

    Het is bijvoorbeeld mogelijk dat u wilt worden gewaarschuwd bij een toename in het aantal mensen dat met RMS beveiligde gegevens buiten de normale werkuren leest, aangezien dit een indicatie kan zijn dat een kwaadwillende gebruiker informatie verzamelt om aan concurrenten te verkopen. Of als dezelfde gebruiker de gegevens binnen een kort tijdsbestek inziet vanaf twee verschillende IP-adressen. Dit kan erop duiden dat een gebruikersaccount verdacht is.

-   **Forensische analyse uitvoeren**

    Als u een informatielek hebt, wordt u waarschijnlijk gevraagd wie onlangs specifieke documenten heeft geopend en welke informatie een verdacht persoon onlangs heeft weergegeven. U kunt dergelijke vragen beantwoorden wanneer u Azure Rights Management en logboekregistratie gebruikt, aangezien mensen die beveiligde inhoud gebruiken altijd een Rights Management-licentie nodig hebben om documenten en afbeeldingen te kunnen openen die zijn beveiligd met Azure Rights Management, zelfs als deze bestanden worden verplaatst via e-mail of worden gekopieerd naar een USB-station of andere opslagapparaten. Dit betekent dat u Azure Rights Management-logboeken kunt gebruiken als een nauwkeurige bron van informatie voor forensische analyse wanneer u uw gegevens beveiligt met Azure Rights Management.

> [!NOTE]Als u alleen bent geïnteresseerd in de logboekregistratie van beheertaken voor Azure Rights Management en u niet wilt bijhouden hoe gebruikers Rights Management gebruiken, kunt u de Windows PowerShell-cmdlet voor Azure Rights Management [Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx) gebruiken.
> 
> U kunt de klassieke Azure-portal ook gebruiken voor geavanceerde gebruiksrapporten die de volgende informatie bevatten: **RMS-overzicht**, **actieve RMS-gebruiker**, **RMS-apparaatplatformen** en **gebruik van de RMS-toepassing**. Voor toegang tot deze rapporten via de klassieke Azure-portal klikt u op **Active Directory**, selecteert en opent u een map en klikt u vervolgens op **RAPPORTEN**.

Gebruik de volgende secties voor meer informatie over de logboekregistratie van het Azure Rights Management-gebruik.

## Azure Rights Management-gebruik registreren in een logboek
Vanaf februari 2016 wordt voor alle klanten standaard de functie voor logboekregistratie van het Azure Rights Management-gebruik ingeschakeld. Dit is van toepassing op klanten die hun Azure RMS-service vóór februari 2016 hebben geactiveerd en op klanten die de service na februari 2016 activeren. 

> [!NOTE] Er zijn geen extra kosten verbonden aan de opslag van de logboeken of de functie voor logboekregistratie.
> 
> Als u vóór februari 2016 ook al gebruikmaakte van logboekregistratie van het Azure RMS-gebruik, had u een abonnement op Azure en voldoende opslag in Azure nodig. Dit is nu niet meer nodig.



## Uw gebruikslogboekbestanden voor Azure Rights Management openen en gebruiken
Azure Rights Management schrijft de logboeken als een reeks blobs naar uw Azure-opslagaccount. Elke blob bevat een of meer logboekrecords met een uitgebreide W3C-logboekindeling. De blob-namen zijn getallen, in de volgorde waarin ze zijn gemaakt. De sectie [Hoe u de gebruikslogboeken van Azure Rights Management moet interpreteren](#how-to-interpret-your-azure-rights-management-usage-logs) verderop in dit document bevat meer informatie over de inhoud en het maken van de logboeken.

Het kan even duren voordat logboeken na een Azure Rights Management-actie worden weergegeven in uw opslagaccount. De meeste logboeken worden binnen vijftien minuten weergegeven. U kunt de logboeken het beste downloaden naar een lokale opslag, zoals een lokale map, een database of een opslagplaats met MapReduce.

Als u de gebruikslogboeken wilt downloaden, gebruikt u de Azure RMS-beheermodule voor Windows PowerShell. Zie [Windows PowerShell voor Azure Rights Management installeren](install-powershell.md) voor de installatie-instructies. Als u deze Windows PowerShell-module eerder hebt gedownload, voert u de volgende opdracht uit om te controleren of u minimaal over versienummer **2.4.0.0** beschikt: `(Get-Module aadrm -ListAvailable).Version` 

### Uw gebruikslogboeken downloaden met PowerShell

1.  Start Windows PowerShell met de optie **Uitvoeren als beheerder** en gebruik de cmdlet [Connect-AadrmService](https://msdn.microsoft.com/library/azure/dn629415.aspx) om verbinding te maken met de Azure Rights Management-service:

    ```
    Connect-AadrmService
    ```
    
2.  Voer de volgende opdracht uit om de logboeken voor een specifieke datum te downloaden: 

    ```
    Get-AadrmUserLog -Path <location> -fordate <date>
    ```

    Bijvoorbeeld nadat u de map met de naam Logboeken op de station E: hebt gemaakt:
    
    * Als u de logboeken voor een specifiek datum wilt downloaden (zoals 01-02-2016), voert u de volgende opdracht uit: `Get-AadrmUserLog -Path E:\Logs -fordate 2/1/2016`
    
    * Als u logboeken voor een bepaald datumbereik wilt downloaden (bijvoorbeeld van 01-02-2016 tot en met 14-02-2016), voert u de volgende opdracht uit: `Get-AadrmUserLog -Path E:\Logs -fromdate 2/1/2016 –todate 2/14/2016` 

Wanneer u, zoals in het voorbeeld, alleen de dag opgeeft, wordt verondersteld dat de lokale tijd 00:00:00 is. Vervolgens wordt deze tijd geconverteerd naar UTC. Wanneer u de parameter -fromdate of -todate gebruikt om een tijd op te geven (bijvoorbeeld -fordate "2/1/2016 15:00:00"), worden deze datum en tijd geconverteerd naar UTC. Vervolgens worden de logboeken voor die UTC-tijdsperiode opgehaald met de opdracht Get-AadrmUserLog.

U moet minimaal een volledige dag opgeven om te downloaden.

Deze cmdlet gebruikt standaard drie threads om de logboeken te downloaden. Als u over voldoende netwerkbrandbreedte beschikt en de logboeken sneller wilt downloaden, gebruikt u de parameter -NumberOfThreads. Deze ondersteunt een waarde van 1 tot en met 32. Als u bijvoorbeeld de volgende opdracht uitvoert, worden met de cmdlet 10 threads gestart om de logboeken te downloaden: `Get-AadrmUserLog -Path E:\Logs -fromdate 2/1/2016 –todate 2/14/2016 -numberofthreads 10`


> [!TIP]
> U kunt alle gedownloade logboekbestanden samenvoegen in CSV-indeling met behulp van de [Log Parser van Microsoft](https://www.microsoft.com/download/details.aspx?id=24659). Dit is een hulpprogramma waarmee u kunt converteren tussen verschillende bekende logboekindelingen. U kunt ook dit hulpprogramma gebruiken om gegevens te converteren naar de SYSLOG-indeling of om gegevens te importeren in een database. Nadat u het hulpprogramma hebt geïnstalleerd, voert u `LogParser.exe /?` uit voor hulp bij en informatie over het gebruik van dit hulpprogramma. 
>
> U kunt bijvoorbeeld de volgende opdracht uitvoeren om alle gegevens te importeren in een logboekbestand met de extensie .log: `logparser –i:w3c –o:csv "SELECT * INTO AllLogs.csv FROM *.log"`

#### Als u de logboekregistratie van het gebruik van Azure RMS handmatig hebt ingeschakeld vóór de logboekregistratiewijziging van 22 februari 2016


Als u ook voor de wijziging in de logboekregistratie al gebruikmaakte van logboekregistratie, staan er gebruikslogboeken in uw geconfigureerde Azure-opslagaccount. Deze logboeken worden niet als onderdeel van de logboekregistratiewijziging door Microsoft gekopieerd van uw opslagaccount naar de nieuwe opslagaccount die wordt beheerd met Azure RMS. U bent zelf verantwoordelijk voor het beheren van de levenscyclus van eerder gegenereerde logboeken. U kunt de cmdlet [Get-AadrmUsageLog](https://msdn.microsoft.com/library/dn629401.aspx) gebruiken om uw oude logboeken te downloaden. Bijvoorbeeld:

- Alle beschikbare logboeken downloaden naar de map E:\logs: `Get-AadrmUsageLog -Path "E:\Logs"`
    
- Een specifiek bereik blobs downloaden: `Get-AadrmUsageLog –Path "E:\Logs" –FromCounter 1024 –ToCounter 2047`

U hoeft de logboeken niet te downloaden met de cmdlet Get-AadrmUsageLog als een van de volgende zaken van toepassing is:

-  U hebt Azure Rights Management geactiveerd op of vóór 22 februari 2016 maar de functie voor de logboekregistratie van het gebruik niet ingeschakeld.

- U hebt Azure Rights Management geactiveerd na 22 februari 2016.

## Hoe u de gebruikslogboeken van Azure Rights Management moet interpreteren
Gebruik de volgende informatie om de gebruikslogboeken voor Azure Rights Management te interpreteren.

### De logboekvolgorde
Azure Rights Management schrijft de logboeken als een reeks blobs. 

Elk item in het logboek heeft een UTC-timestamp. Omdat Azure Rights Management wordt uitgevoerd op meerdere servers in meerdere datacentrums, lijkt het soms alsof de logboeken de verkeerde volgorde hebben, zelfs wanneer ze worden gesorteerd op hun timestamp. Het verschil is echter klein en meestal niet meer dan een minuut. In de meeste gevallen levert dit geen problemen op voor de logboekanalyse.

### De blob-indeling
Elke blob heeft een uitgebreide W3C-logboekbestandsindeling. Deze begint met de volgende twee regels:

**#Software: RMS**

**#Versie: 1.1**

De eerste regel geeft aan dat het Azure Rights Management-logboeken zijn. De tweede regel geeft aan dat de rest van de blob de specificatie van versie 1.1 volgt. Het is raadzaam dat alle toepassingen die deze logboeken parseren, deze twee regels controleren voordat de rest van de blob wordt geparseerd.

De derde regel inventariseert een lijst met veldnamen die worden gescheiden door tabs:

**#Velden: date            time            row-id        request-type           user-id       result          correlation-id          content-id                owner-email           issuer                     template-id             file-name                  date-published      c-info         c-ip**

Elk van de volgende regels is een logboekrecord. De waarden van de velden staan in dezelfde volgorde als de voorafgaande regel en worden gescheiden door tabs. Gebruik de volgende tabel om de velden te interpreteren.

|Veldnaam|W3C-gegevenstype|Beschrijving|Voorbeeldwaarde|
|--------------|-----------------|---------------|-----------------|
|date|Datum|De UTC-datum wanneer de aanvraag is uitgevoerd.<br /><br />De bron is de lokale klok op de server waarmee de aanvraag wordt uitgevoerd.|25-06-2013|
|time|Tijd|De UTC-tijd met een 24-uursnotatie wanneer de aanvraag is uitgevoerd.<br /><br />De bron is de lokale klok op de server waarmee de aanvraag wordt uitgevoerd.|21:59:28|
|row-id|Tekst|De unieke GUID voor deze logboekrecord.<br /><br />Deze waarde is handig wanneer u de logboeken samenvoegt of logboeken naar een andere indeling kopieert.|1c3fe7a9-d9e0-4654-97b7-14fafa72ea63|
|request-type|Naam|De naam van de RMS-API die is aangevraagd.|AcquireLicense|
|user-id|Tekenreeks|De gebruiker die het verzoek heeft ingediend.<br /><br />De waarde wordt tussen enkele aanhalingstekens geplaatst. Bepaalde aanvraagtypen zijn anoniem. In dat geval is de waarde ".|'joe@contoso.com'|
|result|Tekenreeks|'Voltooid' als de aanvraag is uitgevoerd.<br /><br />Het fouttype tussen enkele aanhalingstekens als de aanvraag is mislukt.|'Voltooid'|
|correlation-id|Tekst|De GUID die door het RMS-clientlogboek en het logboekbestand van de server voor een bepaalde aanvraag wordt gedeeld.<br /><br />Deze waarde kan nuttig zijn bij het oplossen van clientproblemen.|cab52088-8925-4371-be34-4b71a3112356|
|content-id|Tekst|De GUID tussen accolades waarmee de beveiligde inhoud (bijvoorbeeld een document) wordt aangeduid.<br /><br />Dit veld bevat alleen een waarde wanneer het aanvraagtype AcquireLicense is en is leeg voor alle andere aanvraagtypen.|{bb4af47b-cfed-4719-831d-71b98191a4f2}|
|owner-email|Tekenreeks|Het e-mailadres van de eigenaar van het document.|alice@contoso.com|
|uitgever|Tekenreeks|Het e-mailadres van de verstrekker van het document.|alice@contoso.com (or) FederatedEmail.4c1f4d-93bf-00a95fa1e042@contoso.onmicrosoft.com'|
|Sjabloon-id|Tekenreeks|De id van de sjabloon die wordt gebruikt om het document te beveiligen.|{6d9371a6-4e2d-4e97-9a38-202233fed26e}|
|File-name|Tekenreeks|De bestandsnaam van het document dat is beveiligd. <br /><br />Op dit moment kunnen worden een aantal bestanden (zoals Office-documenten) als GUID's weergegeven in plaats van met de werkelijke bestandsnaam.|TopSecretDocument.docx|
|Date-published|Datum|De datum waarop het document is beveiligd.|15-10-2015T21:37:00|
|c-info|Tekenreeks|De informatie over het clientplatform waarmee de aanvraag wordt ingediend.<br /><br />De specifieke tekenreeks varieert, afhankelijk van de toepassing (bijvoorbeeld het besturingssysteem of de browser).|'MSIPC;version=1.0.623.47;AppName=WINWORD.EXE;AppVersion=15.0.4753.1000;AppArch=x86;OSName=Windows;OSVersion=6.1.7601;OSArch=amd64'|
|c-ip|Adres|Het IP-adres van de client waarmee de aanvraag is ingediend.|64.51.202.144|

#### Uitzonderingen voor het veld user-id
Hoewel het veld user-id meestal aangeeft welke gebruiker de aanvraag heeft uitgevoerd, zijn er twee uitzonderingen waarbij de waarde niet aan een echte gebruiker is gekoppeld:

-   De waarde **microsoftrmsonline@&lt;YourTenantID&gt;.rms.&lt;region&gt;.aadrm.com**.

    Dit duidt erop dat de aanvraag wordt uitgevoerd door een Office 365-service, zoals Exchange Online of SharePoint Online. In de tekenreeks is *&lt;YourTenantID&gt;* de GUID voor uw tenant en is *&lt;region&gt;* de regio waar uw tenant is geregistreerd. **na** staat bijvoorbeeld voor Noord-Amerika, **eu** voor Europa en **ap** voor Azië.

-   Als u de RMS-connector gebruikt.

    Aanvragen vanaf deze connector worden geregistreerd met de Service Principal Name die automatisch door RMS wordt gegenereerd wanneer u de RMS-connector installeert.

#### Standaardaanvraagtypen
Er zijn tal van aanvraagtypen voor Azure Rights Management, maar de volgende tabel bevat enkele veelgebruikte aanvraagtypen.

|Aanvraagtype|Beschrijving|
|----------------|---------------|
|AcquireLicense|Er wordt met een client van een Windows-machine een licentie aangevraagd voor inhoud die is beveiligd met RMS.|
|AcquirePreLicense|Er wordt met een client namens de gebruiker een licentie aangevraagd voor inhoud die is beveiligd met RMS.|
|AcquireTemplates|Er is een aanroep uitgevoerd om sjablonen op te halen op basis van sjabloon-id 's.|
|AcquireTemplateInformation|Er is een aanroep uitgevoerd om de id's van de sjabloon bij de service op te halen.|
|AddTemplate|Er wordt een aanroep uitgevoerd via de klassieke Azure-portal om een sjabloon toe te voegen.|
|BECreateEndUserLicenseV1|Er wordt een aanroep uitgevoerd vanaf een mobiel apparaat om een gebruiksrechtovereenkomst te maken.|
|BEGetAllTemplatesV1|Er wordt een aanroep uitgevoerd vanaf een mobiel apparaat (back-end) om alle sjablonen op te halen.|
|Certify|De inhoud wordt voor beveiliging gecertificeerd door de client.|
|Ontsleutelen|De client probeert de inhoud te ontsleutelen die is beveiligd met RMS.|
|DeleteTemplateById|Er is een aanroep vanuit de klassieke Azure-portal uitgevoerd om een sjabloon te verwijderen op basis van de sjabloon-id.|
|ExportTemplateById|Er wordt een aanroep vanuit de klassieke Azure-portal uitgevoerd om een sjabloon te verwijderen op basis van de sjabloon-id.|
|FECreateEndUserLicenseV1|Vergelijkbaar met de AcquireLicense-aanvraag, maar afkomstig van mobiele apparaten.|
|FECreatePublishingLicenseV1|Hetzelfde als Certify en GetClientLicensorCert gecombineerd, afkomstig van mobiele clients.|
|FEGetAllTemplates|Er wordt een aanroep vanaf een mobiel apparaat (front-end) uitgevoerd om de sjablonen te verkrijgen.|
|GetAllTemplates|Er wordt een aanroep vanuit de klassieke Azure-portal uitgevoerd om alle sjablonen te verkrijgen.|
|GetClientLicensorCert|Er wordt met de client een publicatiecertificaat aangevraagd (dat later wordt gebruikt om inhoud te beveiligen) bij een Windows-computer.|
|GetConfiguration|Er wordt een Azure PowerShell-cmdlet aangeroepen om de configuratie van de Azure RMS-tenant op te halen.|
|GetConnectorAuthorizations|Er wordt een aanroep uitgevoerd met de RMS-connectoren om hun configuratie op te halen uit de cloud.|
|GetTenantFunctionalState|De klassieke Azure-portal of Azure RMS is geactiveerd.|
|GetTemplateById|Er wordt een aanroep uitgevoerd vanuit de klassieke Azure-portal om een sjabloon op te halen door een sjabloon-id op te geven.|
|ExportTemplateById|Er wordt een aanroep uitgevoerd vanuit de klassieke Azure-portal om een sjabloon te exporteren door een sjabloon-id op te geven.|
|FindServiceLocationsForUser|Er wordt een aanroep uitgevoerd om URL's te zoeken, die worden gebruik om Certify of AcquireLicense aan te roepen.|
|ImportTemplate|Er wordt een aanroep uitgevoerd vanuit de klassieke Azure-portal om een sjabloon te importeren.|
|ServerCertify|Een wordt een aanroep vanaf een RMS-clients(zoals SharePoint) uitgevoerd om de server te certificeren.|
|SetUsageLogFeatureState|Er wordt een aanroep uitgevoerd om logboekregistratie van het gebruik in te schakelen.|
|SetUsageLogStorageAccount|Er wordt een aanroep uitgevoerd om de locatie van Azure RMS-logboeken op te geven.|
|SignDigest|Er wordt een aanroep uitgevoerd wanneer een sleutel wordt gebruikt voor ondertekeningsdoeleinden. Doorgaans wordt er één aanroep per AcquireLicence (of FECreateEndUserLicenseV1), Certify en GetClientLicensorCert (of FECreatePublishingLicenseV1) verzonden.|
|UpdateTemplate|Er wordt een aanroep uitgevoerd vanuit de klassieke Azure-portal om een bestaande sjabloon bij te werken.|

## Windows PowerShell reference
Vanaf februari 2016 hebt u voor de logboekregistratie van het Azure RMS-gebruik alleen de Windows PowerShell-cmdlet [Get-AadrmUserLog](https://msdn.microsoft.com/library/azure/mt653941.aspx) nodig. 

Voorheen had u de volgende, nu afgeschafte cmdlets nodig voor Azure RMS-gebruikslogboeken:  

-   [Disable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629404.aspx)

-   [Enable-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629421.aspx)

-   [Get-AadrmUsageLog](https://msdn.microsoft.com/library/azure/dn629401.aspx)

-   [Get-AadrmUsageLogFeature](https://msdn.microsoft.com/library/azure/dn629425.aspx)

-   [Get-AadrmUsageLogLastCounterValue](https://msdn.microsoft.com/library/azure/dn629423.aspx)

-   [Get-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629419.aspx)

-   [Set-AadrmUsageLogStorageAccount](https://msdn.microsoft.com/library/azure/dn629426.aspx)

Als uw eigen Azure-opslag logboeken bevat die zijn gemaakt vóór de wijziging in de Azure RMS-logboekregistratie, kunt u ze downloaden met deze oudere cmdlets en net als voorheen gebruikmaken van Get-AadrmUsageLog en Get-AadrmUsageLogLastCounterValue. Maar alle nieuwe gebruikslogboeken worden naar de nieuwe Azure RMS-opslag geschreven en moeten worden gedownload met Get-AadrmUserLog.

Zie [Administering Azure Rights Management by Using Windows PowerShell](administer-powershell.md) (Beheer van Azure Rights Management met Windows PowerShell) voor meer informatie over het gebruik van Windows PowerShell voor Azure Rights Management.





<!--HONumber=May16_HO3-->


