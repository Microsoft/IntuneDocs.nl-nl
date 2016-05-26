---
# required metadata

title: De Azure Rights Management-connector installeren en configureren | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 4fed9d4f-e420-4a7f-9667-569690e0d733

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# De Azure Rights Management-connector installeren en configureren

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de volgende informatie om de RMS-connector te installeren en configureren. Deze procedures hebben betrekking op stap 1 tot en met 4 uit [De Azure Rights Management-connector implementeren](deploy-rms-connector.md)..

Voordat u begint, moet u de [vereisten](deploy-rms-connector.md#prerequisites-for-the-rms-connector) voor deze implementatie bekijken en controleren.


## De RMS-connector installeren

1.  Bepaal op welke computers (minstens twee) de RMS-connector wordt uitgevoerd. Ze moeten voldoen aan de minimale specificaties die worden vermeld in de vereisten.

    > [!NOTE]
    > U installeert één RMS-connector (bestaande uit meerdere servers voor een hoge beschikbaarheid) per tenant (Office 365- of Azure AD-tenant). In tegenstelling tot Active Directory RMS hoeft u geen RMS-connector in elke forest te installeren.

2.  Download de bronbestanden voor de RMS-connector via het [Microsoft Downloadcentrum](http://go.microsoft.com/fwlink/?LinkId=314106)..

    Als u de RMS-connector wilt installeren, moet u het bestand RMSConnectorSetup.exe downloaden.

    Daarnaast:

    -   Als u de connector later wilt configureren vanaf een 32 bitscomputer, downloadt u ook RMSConnectorAdminToolSetup_x86.exe.

    -   Als u het hulpprogramma voor de configuratie van de server voor de RMS-connector wilt gebruiken om de configuratie van de registerinstellingen te automatiseren, downloadt u ook GenConnectorConfig.ps1.

3.  Op de computer waarop u de RMS-connector wilt installeren, voert u het bestand **RMSConnectorSetup.exe** uit met beheerdersbevoegdheden.

4.  Selecteer op de welkomstpagina voor de installatie van de Microsoft Rights Management-connector de optie **Install Microsoft Rights Management connector on the computer** (Microsoft Rights Management-connector op de computer installeren) en klik vervolgens op **Next** (Volgende)..

5.  Lees en accepteer de licentievoorwaarden voor de RMS-connector en klik vervolgens op **Next** (Volgende)..

Geef een account en wachtwoord op om door te gaan met het configureren van de RMS-connector.

## Referenties invoeren
Voordat u de RMS-connector kunt configureren, moet u referenties voor een account opgeven dat over voldoende bevoegdheden beschikt om de RMS-connector te configureren. U kunt bijvoorbeeld **admin@contoso.com** typen en het wachtwoord voor dit account opgeven.

Er zijn enkele tekenbeperkingen voor dit wachtwoord. U kunt geen wachtwoord gebruiken dat een van de volgende tekens bevat: ampersand ( **&** ); punthaak links ( **[** ); punthaak rechts ( **]** ); recht aanhalingsteken ( **"** ); en apostrof ( **'** ). Als uw wachtwoord een van deze tekens bevat, mislukt de verificatie voor de RMS-connector en verschijnt het volgende foutbericht: Deze combinatie van gebruikersnaam en wachtwoord is onjuist. Dit foutbericht wordt zelfs weergegeven wanneer u zich wel voor andere scenario's met dit account en wachtwoord kunt aanmelden. Als dit van toepassing is op uw wachtwoord, gebruikt u een ander account met een wachtwoord dat geen van deze speciale tekens bevat. U kunt het wachtwoord ook opnieuw instellen, zodat het geen speciale tekens meer bevat.

Als u daarnaast [besturingselementen voor onboarding](activate-service.md#configuring-onboarding-controls-for-a-phased-deployment) hebt geïmplementeerd, moet u ervoor zorgen dat u de inhoud kunt beveiligen met het account dat u opgeeft. Als u bijvoorbeeld alleen de groep IT-afdeling de mogelijkheid biedt om inhoud te beveiligen, moet het account dat u hier opgeeft, lid zijn van die groep. Als dit niet het geval is, verschijnt het volgende foutbericht: **The attempt to discover the location of the administration service and organization failed. Make sure Microsoft Rights Management service is enabled for your organization.** (Kan de locatie van de beheerservice en organisatie niet detecteren. Zorg ervoor dat de Microsoft Rights Management-service is ingeschakeld voor uw organisatie.)

U kunt een account met een van de volgende bevoegdheden gebruiken:

-   **Office 365 tenant administrator** (Office 365-tenantbeheerder): een account dat een hoofdbeheerder voor uw Office 365-tenant is.

-   **Azure Rights Management global administrator** (Azure Rights Management-hoofdbeheerder): een account met beheerdersbevoegdheden voor de Azure RMS-tenant.

-   **Microsoft RMS connector Administrator** (Microsoft RMS-connectorbeheerder): een account in Azure Active Directory waaraan rechten zijn toegewezen om de RMS-connector voor uw organisatie te installeren en te beheren.

    > [!NOTE]
    > Als u het Administrator-account voor de Microsoft RMS-connector wilt gebruiken, moet u eerst het volgende doen om de rol van RMS-connectorbeheerder toe te wijzen:
    >
    > 1.  Download en installeer op dezelfde computer Windows PowerShell voor Rights Management. Zie [Windows PowerShell voor Azure Rights Management installeren](install-powershell.md) voor meer informatie.
    >
    >     Start Windows PowerShell met de opdracht **Uitvoeren als beheerder** en maak verbinding met de Azure RMS-service via de opdracht [Connect-AadrmService](https://msdn.microsoft.com/library/azure/dn629415.aspx):
    >
    >     ```
    >     Connect-AadrmService                   //provide Office 365 tenant administrator or Azure RMS global administrator credentials
    >     ```
    > 2.  Voer vervolgens de opdracht [Add-AadrmRoleBasedAdministrator](https://msdn.microsoft.com/library/azure/dn629417.aspx) uit met slechts een van de volgende parameters:
    >
    >     ```
    >     Add-AadrmRoleBasedAdministrator -EmailAddress <email address> -Role "ConnectorAdministrator"
    >     ```
    >
    >     ```
    >     Add-AadrmRoleBasedAdministrator -ObjectId <object id> -Role "ConnectorAdministrator"
    >     ```
    >
    >     ```
    >     Add-AadrmRoleBasedAdministrator -SecurityGroupDisplayName <group Name> -Role "ConnectorAdministrator"
    >     ```
    >     Typ bijvoorbeeld: **Add-AadrmRoleBasedAdministrator -EmailAddress melisa@contoso.com -Role " ConnectorAdministrator "**
    >
    >     Hoewel voor deze opdrachten de rol ConnectorAdministrator wordt gebruikt, kunt u hier ook de rol GlobalAdministrator gebruiken.

Tijdens het installatieproces van de RMS-connector wordt alle vereiste software gevalideerd en geïnstalleerd, wordt zo nodig Internet Information Services (IIS) geïnstalleerd en wordt de connectorsoftware geïnstalleerd en geconfigureerd. Bovendien wordt Azure RMS voorbereid voor de configuratie door het volgende te maken:

-   Een lege tabel met servers die zijn geautoriseerd om de connector te gebruiken voor de communicatie met Azure RMS. U voegt later servers toe aan deze tabel.

-   Een set beveiligingstokens voor de connector die bewerkingen met Azure RMS autoriseren. Deze tokens worden gedownload via Azure RMS en geïnstalleerd in het register van de lokale computer. Ze worden beveiligd met de Data Protection Application Programming Interface (DPAPI) en de referenties voor het lokale systeemaccount.

Op de laatste pagina van de wizard, voert u de volgende handeling uit en klikt u vervolgens op **Voltooien**:

-   Als dit de eerste connector is die u hebt geïnstalleerd, moet u nu niet **Launch connector administrator console to authorize servers** (Beheerconsole van de connector starten om servers te autoriseren) selecteren. U selecteert deze optie nadat u de tweede (of laatste) RMS-connector hebt geïnstalleerd. In plaats daarvan moet u de wizard op ten minste één andere computer uitvoeren. U moet minimaal twee connectoren installeren.

-   Als u de tweede (of laatste) connector hebt geïnstalleerd, selecteert u **Launch connector administrator console to authorize servers** (Beheerconsole van de connector starten om servers te autoriseren).

> [!TIP]
> U kunt nu een verificatietest uitvoeren om te controleren of de webservices voor de RMS-connector operationeel zijn:
>
> -   Maak via een webbrowser verbinding met **http://&lt;connectoradres&gt;/_wmcs/certification/servercertification.asmx** en vervang *&lt;connectoradres&gt;* door het adres of de naam van de server waarop de RMS-connector is geïnstalleerd. Als er verbinding is gemaakt, wordt de pagina **ServerCertificationWebService** weergegeven.

Als u de RMS-connector moet verwijderen, voert u de wizard opnieuw uit en selecteert u de optie voor verwijderen.

## Servers autoriseren voor het gebruik van de RMS-connector
Wanneer u de RMS-connector hebt geïnstalleerd op ten minste twee computers, kunt u de servers en services autoriseren waarvoor u de RMS-connector wilt gebruiken. Bijvoorbeeld servers met Exchange Server 2013 of SharePoint Server 2013.

Als u deze servers wilt definiëren, voert u het beheerprogramma voor RMS-connector uit en voegt u items toe aan de lijst met toegestane servers. U kunt dit hulpprogramma uitvoeren door aan het einde van de wizard voor het installeren van de Microsoft Rights Management-connector de optie **Launch connector administration console to authorize servers** (Beheerconsole van de connector starten om servers te autoriseren) te selecteren.

Wanneer u deze servers autoriseert, moet u rekening houden met het volgende:

-   Er worden speciale bevoegdheden verleend voor de servers die u toevoegt. Alle accounts die u in de connectorconfiguratie opgeeft voor de Exchange Server-rol, krijgen de [rol van supergebruiker](configure-super-users.md) toegewezen in Azure RMS, waardoor ze toegang hebben tot alle inhoud voor deze RMS-tenant. Indien nodig wordt nu automatisch de functie voor supergebruikers ingeschakeld. Zorg dat u alleen accounts opgeeft die worden gebruikt door de Exchange-servers van uw account om het beveiligingsrisico met betrekking tot het uitbreiden van de bevoegdheden te voorkomen. Alle servers die zijn geconfigureerd als SharePoint-servers of bestandsservers die gebruikmaken van FCI, krijgen de gebruikelijke gebruikersbevoegdheden toegewezen.

-   U kunt meerdere servers toevoegen als één item door een Active Directory-beveiligingsgroep of -distributiegroep op te geven of door een serviceaccount op te geven dat wordt gebruikt door meerdere servers. Wanneer u deze configuratie gebruikt, deelt de groep servers dezelfde RMS-certificaten en worden de server allemaal beschouwd als eigenaar van de inhoud die ze hebben beveiligd. Als u de administratieve overhead wilt minimaliseren, kunt u het beste deze configuratie met één groep in plaats van individuele servers gebruiken om de Exchange-servers of een SharePoint-serverfarm van uw organisatie te autoriseren.

Klik op de pagina **Servers allowed to utilize the connector** (Servers die de connector mogen gebruiken) op **Add** (Toevoegen)..

> [!NOTE]
> Het autoriseren van servers is de equivalente configuratie in Azure RMS van de AD RMS-configuratie waarbij handmatig NTFS-rechten op ServerCertification.asmx voor de service- of serveraccounts worden toegepast en handmatig superrechten voor de Exchange-accounts worden verleend. Het toepassen van NTFS-rechten op ServerCertification.asmx is niet vereist op de connector.


### Een server toevoegen aan de lijst met toegestane servers
Voer op de pagina the **Allow a server to utilize the connector** (Servers die de connector mogen gebruiken) de naam van het object in of blader om het object te zoeken dat u wilt autoriseren.

Het is belangrijk dat u het juiste object autoriseert. De connector kan alleen door een server worden gebruikt als het account dat de on-premises service (bijvoorbeeld Exchange of SharePoint) uitvoert, wordt geselecteerd voor autorisatie. Als de service bijvoorbeeld wordt uitgevoerd als een geconfigureerd serviceaccount, voegt u de naam van het serviceaccount toe aan de lijst. Als de service wordt uitgevoerd als lokaal systeem, voegt u de naam van het computerobject (bijvoorbeeld SERVERNAME$) toe. U kunt het beste een groep met deze accounts maken en de groep in plaats van afzonderlijke servernamen opgeven.

Meer informatie over de verschillende serverrollen:

-   Voor servers met Exchange: u moet een beveiligingsgroep opgeven en u kunt de standaardgroep (**Exchange-servers**) gebruiken die automatisch door Exchange wordt gemaakt en onderhouden voor alle Exchange-servers in de forest.

-   Voor servers met SharePoint:

    -   Als een SharePoint 2010-server is geconfigureerd om te worden uitgevoerd als lokaal systeem (dat geen gebruikmaakt van een serviceaccount), maakt u handmatig een beveiligingsgroep in Active Directory Domain Services en voegt u de naam van het computerobject voor de server in deze configuratie toe aan deze groep.

    -   Als een SharePoint-server is geconfigureerd voor het gebruik van een serviceaccount (de aanbevolen werkwijze voor SharePoint 2010 en de enige optie voor SharePoint 2016 en SharePoint 2013), doet u het volgende:

        1.  Voeg het serviceaccount toe waarmee de service voor centraal beheerde SharePoint-toepassingen wordt uitgevoerd om ervoor te zorgen dat SharePoint kan worden geconfigureerd via de bijbehorende beheerdersconsole.

        2.  Voeg het account toe dat is geconfigureerd voor de groep van SharePoint-toepassingen.

        > [!TIP]
        > Als deze twee accounts verschillen, kunt u overwegen om één groep te maken die beide accounts bevat om de administratieve overhead te minimaliseren.

-   Voor bestandsservers die gebruikmaken van de infrastructuur voor bestandsclassificatie, worden de gekoppelde services uitgevoerd als het lokale systeemaccount. U moet dus het computeraccount voor de bestandsservers (bijvoorbeeld SERVERNAME$) autoriseren, of een groep die de computeraccounts bevat.

Zodra u klaar ben met het toevoegen van servers, klikt u op **Close** (Sluiten)..

Indien u dit nog niet hebt gedaan, moet u nu de taakverdeling configureren voor de servers waarop de RMS-connector is geïnstalleerd en overwegen of u HTTPS wilt gebruiken voor de verbindingen tussen deze servers en de servers die u zojuist hebt geautoriseerd.

## Taakverdeling en hoge beschikbaarheid configureren
Nadat u het tweede of het laatste exemplaar van de RMS-connector hebt geïnstalleerd, definieert u een URL-servernaam voor de connector en configureert u een taakverdelingssysteem.

De URL-servernaam voor de connector kan elke naam in een door u beheerde naamruimte zijn. U kunt bijvoorbeeld een vermelding in uw DNS-systeem voor **rmsconnector.contoso.com** maken en deze vermelding configureren voor het gebruik van een IP-adres in uw taakverdelingssysteem. Er zijn geen speciale vereisten voor deze naam en de naam hoeft niet te worden geconfigureerd op de connectorservers zelf. Tenzij uw Exchange- en SharePoint-servers via internet met de connector communiceren, hoeft deze naam niet worden omgezet op internet.

> [!IMPORTANT]
> U kunt deze naam beter niet meer wijzigen nadat u Exchange- of SharePoint-servers hebt geconfigureerd voor het gebruik van de connector, omdat u anders alle IRM-configuraties van deze servers moet verwijderen en ze vervolgens opnieuw moet configureren.

Nadat de naam in DNS is gemaakt en is geconfigureerd voor een IP-adres, configureert u de taakverdeling voor dit adres, waarmee verkeer naar de connectorservers wordt omgeleid. Hiervoor kunt u elke IP-load balancer gebruiken, waaronder de functie Network Load Balancing (NLB) in Windows Server. Raadpleeg de [Load Balancing Deployment Guide](http://technet.microsoft.com/library/cc754833%28v=WS.10%29.aspx) (Implementatiegids voor netwerktaakverdeling) voor meer informatie..

Gebruik de volgende instellingen om het NLB-cluster te configureren:

-   Poorten: 80 (voor HTTP) of 443 (voor HTTPS)

    Zie de volgende sectie voor meer informatie over of HTTP of HTTPS moet worden gebruikt.

-   Affiniteit: None

-   Distributiemethode: Equal

De naam die u definieert voor het systeem met gelijke taakverdeling (voor de servers waarop de RMS-connectorservice wordt uitgevoerd), is de naam RMS-connectornaam van uw organisatie. Deze naam gebruikt u later bij het configureren van de on-premises servers voor het gebruik van Azure RMS.

## De RMS-connector configureren voor gebruik van HTTPS
> [!NOTE]
> Deze configuratiestap is optioneel, maar wordt aanbevolen voor extra beveiliging.

Hoewel het gebruik van TLS of SSL optioneel is voor de RMS-connector, wordt u aangeraden deze voor elke beveiligingsgevoelige HTTP-service te gebruiken. Met deze configuratie worden de servers waarop de connector wordt uitgevoerd geverifieerd op uw Exchange- en SharePoint-servers die gebruikmaken van de connector. Daarnaast worden alle gegevens die vanaf deze servers naar de connector worden verzonden, versleuteld.

Als u de RMS-connector wilt inschakelen voor het gebruik van TLS, installeert u op elke server waarop de RMS-connector wordt uitgevoerd, een serververificatiecertificaat dat de naam bevat die u voor de connector wilt gebruiken. Als de naam van de RMS-connector die u in DNS hebt gedefinieerd bijvoorbeeld **rmsconnector.contoso.com** is, implementeert u een serververificatiecertificaat met de algemene naam **rmsconnector.contoso.com** in het certificaatonderwerp. Of geef als DNS-waarde **rmsconnector.contoso.com** op in de alternatieve naam van het certificaat. Het certificaat hoeft niet de naam van de server te bevatten. Vervolgens bindt u dit certificaat in IIS aan de standaardwebsite.

Als u de HTTPS-optie gebruikt, moet u ervoor zorgen dat alle servers waarop de connector wordt uitgevoerd, een geldig serververificatiecertificaat hebben dat is gekoppeld aan de basis-CA die door de Exchange- en SharePoint-servers wordt vertrouwd. Als de certificeringsinstantie (CA) die de certificaten voor de connectorservers heeft uitgeven, een certificaatintrekkingslijst (CRL) publiceert, moeten de Exchange- en SharePoint-servers de CRL bovendien kunnen downloaden.

> [!TIP]
> U kunt de volgende informatie en resources gebruiken om een serververificatiecertificaat aan te vragen en te installeren en dit certificaat vervolgens te binden aan de standaardwebsite in IIS:
>
> -   Als u Active Directory Certificate Services (AD CS) en een certificeringsinstantie (CA) voor ondernemingen gebruikt om de serververificatiecertificaten te implementeren, kunt u de webservercertificaatsjabloon dupliceren en vervolgens gebruiken. Deze certificaatsjabloon maakt gebruik van **Geleverd in de aanvraag** voor de onderwerpnaam van het certificaat. Dit betekent dat u de FQDN of de naam van de RMS-connector kunt opgeven voor de onderwerpnaam of de alternatieve naam voor het onderwerp wanneer u het certificaat aanvraagt.
> -   Zie [ Configuring Internet Server Certificates (IIS 7)](http://technet.microsoft.com/library/cc731977%28v=ws.10%29.aspx) (Internetservercertificaten configureren (IIS 7)) in de documentatiebibliotheek [Web Server (IIS)](http://technet.microsoft.com/library/cc753433%28v=ws.10%29.aspx) op TechNet als u een zelfstandige CA gebruikt of dit certificaat bij een ander bedrijf aanschaft.
> -   Zie [Add a Binding to a Site (IIS 7)](http://technet.microsoft.com/library/cc731692.aspx) (Een binding aan een site toevoegen (IIS 7)) in de documentatiebibliotheek [Web Server (IIS)](http://technet.microsoft.com/library/cc753433%28v=ws.10%29.aspx) op TechNet om ISS te configureren voor het gebruik van het certificaat.

## De RMS-connector voor een webproxyserver configureren
Als uw connectorservers zijn geïnstalleerd in een netwerk dat geen directe verbinding met internet heeft en een webproxyserver voor uitgaande internetverbinding handmatig moet worden geconfigureerd, moet u het register op deze servers voor de RMS-connector configureren.

#### De RMS-connector configureren voor het gebruik van een webproxyserver

1.  Open op elke server met de RMS-connector een registereditor zoals Regedit.

2.  Ga naar **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AADRM\Connector**

3.  Voeg de tekenreekswaarde **ProxyAddress** toe en stel de gegevens voor deze waarde in op **http://&lt;MyProxyDomainOrIPaddress&gt;:&lt;MyProxyPort&gt;**.

    Bijvoorbeeld: **http://proxyserver.contoso.com:8080**

4.  Sluit de Register-editor en start de server opnieuw op of voer een IISReset-opdracht uit om IIS opnieuw te starten.

## Het beheerprogramma voor RMS-connector op beheercomputers installeren
U kunt het beheerprogramma voor RMS-connector uitvoeren vanaf een computer waarop de RMS-connector niet is geïnstalleerd, mits deze computer voldoet aan de volgende vereisten:

-   Een fysieke of virtuele computer met Windows Server 2012 of Windows Server 2012 R2 (alle versies), Windows Server 2008 R2 of Windows Server 2008 R2 Service Pack 1 (alle versies), Windows 8.1, Windows 8 of Windows 7.

-   Ten minste 1 GB aan RAM-geheugen.

-   Minimaal 64 GB aan schijfruimte.

-   Ten minste één netwerkinterface.

-   Toegang tot internet via een firewall (of een webproxy).

Als u het beheerprogramma voor RMS-connector wilt installeren, voert u de volgende bestanden uit:

-   Voor een 32 bitscomputer: RMSConnectorAdminToolSetup_x86.exe

-   Voor een 64 bitscomputer: RMSConnectorSetup.exe

Als u deze bestanden nog niet hebt gedownload, kunt u dit doen via het [Microsoft Downloadcentrum](http://go.microsoft.com/fwlink/?LinkId=314106)..


## Volgende stappen
Nu de RMS-connector is geïnstalleerd en geconfigureerd, kunt u de on-premises servers configureren voor het gebruik van de connector. Ga naar [Servers configureren voor de Azure Rights Management-connector](configure-servers-rms-connector.md)..

<!--HONumber=Apr16_HO4-->


