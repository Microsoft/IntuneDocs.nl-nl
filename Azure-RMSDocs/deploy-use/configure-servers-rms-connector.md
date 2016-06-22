---
# required metadata

title: Servers configureren voor de Azure Rights Management-connector | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 06/08/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 75846ee1-2370-4360-81ad-e2b6afe3ebc9

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Servers configureren voor de Azure Rights Management-connector

*Van toepassing op: Azure Rights Management, Windows Server 2012, Windows Server 2012 R2*


Gebruik de volgende informatie om uw on-premises servers te configureren waarop de Azure Rights Management-connector (RMS) wordt gebruikt. Deze procedures hebben betrekking op stap 5 in [Deploying the Azure Rights Management connector](deploy-rms-connector.md) (De Azure Rights Management-connector implementeren).

Zorg er voordat u begint voor dat u de RMS-connector hebt geïnstalleerd en geconfigureerd en dat u eventuele [vereisten](deploy-rms-connector.md#prerequisites-for-the-rms-connector) hebt gecontroleerd die van toepassing zijn voor de servers waarop de connector wordt gebruikt.


## Servers configureren voor het gebruik van de RMS-connector
Nadat u de RMS-connector hebt geïnstalleerd en geconfigureerd, bent u klaar om uw on-premises servers te configureren waarop Rights Management wordt gebruikt en via de connector verbinding te maken met Azure RMS. Dit betekent dat u de volgende servers moet configureren:

-   **Voor Exchange 2016 en Exchange 2013**: servers voor clienttoegang en postvakservers

-   **Voor Exchange 2010**: servers voor clienttoegang en Hub Transport-servers

-   **Voor SharePoint**: SharePoint front-endwebservers, waaronder die servers waarop de server voor centraal beheer wordt gehost

-   **Voor infrastructuur voor bestandsclassificering**: Windows Server-computers waarop bestandsbronbeheer is geïnstalleerd

Voor deze configuratie zijn registerinstellingen vereist. Hiervoor hebt u twee mogelijkheden: automatisch met het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector of handmatig door het register te bewerken.

---

**Automatisch met het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector:**

- Voordelen:

    - Het register hoeft niet direct te worden bewerkt. Dit wordt automatisch uitgevoerd via een script.

    - Er hoeft geen Windows PowerShell-cmdlet te worden uitgevoerd voor het verkrijgen van de Microsoft RMS-URL.

    - De vereisten worden automatisch gecontroleerd (maar niet automatisch hersteld) als u het hulpprogramma lokaal uitvoert.

Nadelen:

- Wanneer u het hulpprogramma uitvoert, moet u verbinding maken met een server waarop de RMS-connector al wordt uitgevoerd.

---

**Handmatig door het register te bewerken:**

- Voordelen:

    - Er is geen verbinding vereist met een server waarop de RMS-connector wordt uitgevoerd.

- Nadelen:

    - Meer foutgevoelige administratieve overhead.

    - U moet uw Microsoft RMS-URL verkrijgen, waarvoor u een Windows PowerShell-opdracht moet uitvoeren.

    - U moet altijd zelf alle vereisten controleren.


---

> [!IMPORTANT] In beide gevallen moet u handmatig eventuele vereiste software installeren en Exchange, SharePoint en de infrastructuur voor bestandsclassificatie configureren voor het gebruik van Rights Management.

Voor de meeste organisaties is automatische configuratie met het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector een de betere optie, omdat deze methode efficiënter en betrouwbaarheid is dan handmatige configuratie.

Na het wijzigingen van de configuratie op deze servers, moet u deze opnieuw opstarten als er Exchange of SharePoint op wordt uitgevoerd en eerder zijn geconfigureerd voor het gebruik van AD RMS. U hoeft deze servers niet opnieuw op te starten als u deze voor het eerst configureert voor Rights Management. De bestandsserver die is geconfigureerd voor het gebruik van de infrastructuur voor bestandsclassificatie moet u altijd opnieuw opstarten nadat u de configuratie hebt gewijzigd.

### Het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector gebruiken

1.  Als u het script voor het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector (GenConnectorConfig.ps1) nog niet hebt gedownload, downloadt u dit via het [Microsoft Downloadcentrum](http://go.microsoft.com/fwlink/?LinkId=314106).

2.  Sla het bestand GenConnectorConfig.ps1 op de computer op waarop u het hulpprogramma wilt uitvoeren. Als u het hulpprogramma lokaal uitvoeren wilt, moet dit de server zijn die u wilt configureren voor communicatie met de RMS-connector. Anders kunt u het op een willekeurige computer opslaan.

3.  Bepaal hoe u het hulpprogramma uitvoert:

    -   **Lokaal**: u kunt het hulpprogramma interactief uitvoeren vanaf de server die wordt geconfigureerd voor communicatie met de RMS-connector. Dit is handig voor een eenmalige configuratie, bijvoorbeeld in een testomgeving.

    -   **Software-implementatie**: u kunt het hulpprogramma uitvoeren om registerbestanden te maken die u vervolgens implementeert op een of meer relevante servers met een beheertoepassing voor systemen dat ondersteuning biedt voor software-implementatie, zoals System Center Configuration Manager.

    -   **Groepsbeleid**: u kunt het hulpprogramma uitvoeren om een script te maken dat u aan een beheerder geeft die groepsbeleidsobjecten kan maken voor de servers die worden geconfigureerd. Met dit script wordt een groepsbeleidsobject gemaakt voor elk servertype dat moet worden geconfigureerd en dat de beheerder vervolgens kan toewijzen aan de relevante servers.

    > [!NOTE]
    > Met dit hulpprogramma configureert u de servers die communiceren met de RMS-connector en die aan het begin van deze sectie worden weergegeven. Voer dit hulpprogramma niet uit op de servers waarop de RMS-connector wordt uitgevoerd.

4.  Start Windows PowerShell met de optie **Als beheerder uitvoeren** en gebruik de opdracht Get-help voor instructies hoe u het hulpprogramma moet gebruiken voor uw gekozen configuratiemethode:

    ```
    Get-help .\GenConnectorConfig.ps1 -detailed
    ```

Als u het script wilt uitvoeren, moet u de URL invoeren van de RMS-connector voor uw organisatie. Voer het protocolvoorvoegsel (HTTP:// of HTTPS://) en de naam van de connector in die u in DNS hebt gedefinieerd voor het adres met gelijke taakverdeling van de connector. Bijvoorbeeld https://connector.contoso.com. Het hulpprogramma gebruikt vervolgens die URL om verbinding te maken met de servers waarop de RMS-connector wordt uitgevoerd en om andere parameters te verkrijgen die worden gebruikt voor het maken van de vereiste configuraties.

> [!IMPORTANT] Wanneer u dit hulpprogramma uitvoert, moet u ervoor zorgen dat u de naam opgeeft van de RMS-connector met gelijke taakverdeling voor uw organisatie en niet de naam van één server waarop de RMS-connectorservice wordt uitgevoerd.

Gebruik de volgende secties voor specifieke informatie over elk servicetype:

-   [Een Exchange-server configureren voor het gebruik van de connector](#configuring-an-exchange-server-to-use-the-connector)

-   [Een SharePoint-server configureren voor het gebruik van de connector](#configuring-a-sharepoint-server-to-use-the-connector)

-   [Een bestandsserver configureren voor infrastructuur voor bestandsclassificatie voor het gebruik van de connector](#configuring-a-file-server-for-file-classification-infrastructure-to-use-the-connector)

> [!NOTE]
> Wanneer deze servers zijn geconfigureerd voor het gebruik van de connector, werken clienttoepassingen die lokaal op deze servers zijn geïnstalleerd mogelijk niet met RMS. Wanneer dit gebeurt, is dit omdat de toepassingen proberen de connector te gebruiken in plaats van de RMS rechtstreeks te gebruiken, wat niet wordt ondersteund.
>
> Als Office 2010 daarnaast lokaal is geïnstalleerd op een Exchange-server, werken de IRM-functies van de clientapp mogelijk vanaf die computer nadat de server is geconfigureerd voor het gebruik van de connector. Dit wordt echter niet ondersteund.
>
> In beide gevallen moet u de clienttoepassingen installeren op afzonderlijke computers die niet zijn geconfigureerd voor het gebruik van de connector. Vervolgens gebruiken ze de RMS rechtstreeks.

## Een Exchange-server configureren voor het gebruik van de connector
De volgende Exchange-rollen communiceren met de RMS-connector:

-   Voor Exchange 2016 en Exchange 2013: server voor clienttoegang en postvakserver

-   Voor Exchange 2010: server voor clienttoegang en Hub Transport-server

Voor het gebruik van de RMS-connector moet op deze servers waarop Exchange wordt uitgevoerd een van de volgende softwareversies worden uitgevoerd:

-   Exchange Server 2016

-   Exchange Server 2013 met Exchange 2013 cumulatieve update 3

-   Exchange Server 2010 met Exchange 2010 Service Pack 3 Rollup update 6

U moet op deze servers ook een versie installeren van de RMS-client met ondersteuning voor cryptografische modus 2 voor RMS. De minimumversie die wordt ondersteund in Windows Server 2008 is opgenomen in de hotfix die kunt downloaden via [RSA key length is increased to 2048 bits for AD RMS in Windows Server 2008 R2 and in Windows Server 2008](http://support.microsoft.com/kb/2627272) (RSA-sleutellengte wordt verhoogd tot 2048 bits voor AD RMS in Windows Server 2008 R2 en Windows Server 2008). De minimumversie voor Windows Server 2008 R2 kan worden gedownload via [RSA key length is increased to 2048 bits for AD RMS in Windows 7 or in Windows Server 2008 R2](http://support.microsoft.com/kb/2627273) (RSA-sleutellengte wordt verhoogd tot 2048 bits voor AD RMS in Windows 7 en Windows Server 2008 R2). Windows Server 2012 en Windows Server 2012 R2 bieden systeemeigen ondersteuning voor cryptografische modus 2.

> [!IMPORTANT]
> Als deze versies of latere versies van Exchange en de RMS-client niet zijn geïnstalleerd, kunt u Exchange niet configureren voor het gebruik van de connector. Controleer of deze versies zijn geïnstalleerd voordat u doorgaat.

### Exchange-servers configureren voor het gebruik van de connector

1. Zorg ervoor dat de Exchange-servers zijn gemachtigd om de RMS-connector te gebruiken, met het beheerprogramma voor de RMS-connector en de informatie uit de sectie [Authorizing servers to use the RMS connector](install-configure-rms-connector.md#authorizing-servers-to-use-the-rms-connector) (Servers machtigen om de RMS-connector te gebruiken). Deze configuratie is vereist, zodat Exchange de RMS-connector kan gebruiken.

2.  Voer een van de volgende handelingen uit op de Exchange-serverfuncties die met de RMS-connector communiceren:

    -   Voer het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector uit. Zie [Het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector gebruiken](#how-to-use-the-server-configuration-tool-for-microsoft-rms-connector) in dit artikel voor meer informatie.

        Als u het hulpprogramma bijvoorbeeld lokaal wilt uitvoeren om een server met Exchange 2016 of Exchange 2013 te configureren:

        ```
        .\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetExchange2013
        ```

    -   Bewerk het register handmatig met de informatie in [Registry settings for the RMS connector](rms-connector-registry-settings.md) (Registerinstellingen voor de RMS-connector) om handmatig registerinstellingen toe te voegen op de servers. 

3.  Schakel in Exchange de IRM-functionaliteit in. Zie [Information Rights Management Procedures](https://technet.microsoft.com/library/dd351212%28v=exchg.150%29.aspx) (Information Rights Management-procedures) in de Exchange-bibliotheek voor meer informatie.

    > [!NOTE]
    > Nadat u **Set-IRMConfiguration -InternalLicensingEnabled $true** hebt uitgevoerd, wordt IRM standaard automatisch ingeschakeld voor Outlook Web App en mobiele apparaten, en wordt IRM tevens ingeschakeld voor postvakken. Beheerders kunnen IRM echter op verschillende niveaus uitschakelen, bijvoorbeeld voor een server voor clienttoegang, voor de virtuele map of het postvakbeleid van Outlook Web App en voor het postvakbeleid van een mobiel apparaat. Als gebruikers (na een dag wachten) geen van de Azure RMS-sjablonen kunnen zien in Outlook Web App of op mobiele apparaten, terwijl ze de sjablonen in de Outlook-client wel kunnen zien, controleert u de betreffende instelling om er zeker van te zijn dat IRM niet is uitgeschakeld. Zie [Enable or Disable Information Rights Management on Client Access Servers](https://technet.microsoft.com/library/dd876938(v=exchg.150).aspx) (Information Rights Management in- of uitschakelen op servers voor clienttoegang) in de Exchange-documentatie voor meer informatie. 


## Een SharePoint-server configureren voor het gebruik van de connector
De volgende SharePoint-rollen communiceren met de RMS-connector:

-   SharePoint front-endwebservers, waaronder die servers waarop de server voor centraal beheer wordt gehost

Voor het gebruik van de RMS-connector moet op deze servers waarop SharePoint wordt uitgevoerd een van de volgende softwareversies worden uitgevoerd:

-   SharePoint Server 2016

-   SharePoint Server 2013

-   SharePoint Server 2010

Op een server waarop SharePoint 2016 of SharePoint 2013 wordt uitgevoerd, moet ook een versie van de client MSIPC 2.1 worden uitgevoerd, die wordt ondersteund met de RMS-connector. Download de nieuwste client via het [Microsoft Downloadcentrum](http://www.microsoft.com/download/details.aspx?id=38396) om ervoor te zorgen dat u over een ondersteunde versie beschikt.

> [!WARNING] Er zijn meerdere versies van de client MSIPC 2.1. Zorg dus ervoor dat u versie 1.0.2004.0 of hoger hebt.
>
> U kunt de clientversie controleren aan de hand van het versienummer van MSIPC.dll, dat zich bevindt in **\Program Files\Active Directory Rights Management Services Client 2.1**. In het dialoogvenster eigenschappen wordt het versienummer van de client MSIPC 2.1 weergegeven.

Op servers met SharePoint 2010 moet een versie van de MSDRM-client zijn geïnstalleerd die ondersteuning biedt voor cryptografische modus 2 voor RMS. De minimumversie die wordt ondersteund in Windows Server 2008 is opgenomen in de hotfix die u kunt downloaden via [RSA key length is increased to 2048 bits for AD RMS in Windows Server 2008 R2 and in Windows Server 2008](http://support.microsoft.com/kb/2627272) (RSA-sleutellengte wordt verhoogd tot 2048 bits voor AD RMS in Windows Server 2008 R2 en Windows Server 2008). De minimumversie voor Windows Server 2008 R2 kunt u downloaden via [RSA key length is increased to 2048 bits for AD RMS in Windows 7 or in Windows Server 2008 R2](http://support.microsoft.com/kb/2627273) (RSA-sleutellengte wordt verhoogd tot 2048 bits voor AD RMS in Windows 7 en Windows Server 2008 R2). Windows Server 2012 en Windows Server 2012 R2 bieden systeemeigen ondersteuning voor cryptografische modus 2.

### SharePoint-servers configureren voor het gebruik van de connector

1. Zorg ervoor dat de SharePoint-servers zijn gemachtigd om de RMS-connector te gebruiken, met het beheerprogramma voor de RMS-connector en de informatie uit de sectie [Authorizing servers to use the RMS connector](install-configure-rms-connector.md#authorizing-servers-to-use-the-rms-connector) (Servers machtigen om de RMS-connector te gebruiken). Deze configuratie is vereist, zodat Exchange de RMS-connector kan gebruiken.

2.  Voer een van de volgende handelingen uit op de SharePoint-servers die met de RMS-connector communiceren:

    -   Voer het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector uit. Zie [Het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector gebruiken](#how-to-use-the-server-configuration-tool-for-microsoft-rms-connector) in dit artikel voor meer informatie.

        Als u het hulpprogramma bijvoorbeeld lokaal wilt uitvoeren om een server met SharePoint 2016 of SharePoint 2013 te configureren:

        ```
        .\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetSharePoint2013
        ```

    -   Als u SharePoint 2016 of SharePoint 2013 gebruikt, bewerkt u het register handmatig met de informatie in [Registry settings for the RMS connector](rms-connector-registry-settings.md) (Registerinstellingen voor de RMS-connector) om handmatig registerinstellingen toe te voegen op de servers. 

3.  Schakel IRM in SharePoint in. Zie [Configure Information Rights Management (SharePoint Server 2010)](https://technet.microsoft.com/library/hh545607%28v=office.14%29.aspx) (Information Rights Management configureren (SharePoint Server 2010)) in de SharePoint-bibliotheek voor meer informatie.

    Wanneer u deze instructies volgt, moet u SharePoint configureren voor het gebruik van de connector door **Deze RMS-server gebruiken** te specificeren vervolgens de URL voor de taakverdelingsconnector in te voeren die u hebt geconfigureerd. Voer het protocolvoorvoegsel (HTTP:// of HTTPS://) en de naam van de connector in die u in DNS hebt gedefinieerd voor het adres met gelijke taakverdeling van de connector. Als uw connectornaam bijvoorbeeld https://connector.contoso.com is, vertoont uw configuratie gelijkenis met de volgende afbeelding:

    ![SharePoint-Server configureren voor de RMS-connector](../media/AzRMS_SharePointConnector.png)

    Nadat IRM is ingeschakeld op een SharePoint-farm, schakelt u IRM in op afzonderlijke bibliotheken met de optie **Information Rights Management** op de pagina **Bibliotheekinstellingen** voor elk van de bibliotheken.


## Een bestandsserver configureren voor infrastructuur voor bestandsclassificatie voor het gebruik van de connector
Als u de RMS-connector en de infrastructuur voor bestandsclassificatie wilt gebruiken om Office-documenten te beveiligen, moet op de bestandsserver een van de volgende besturingssystemen worden uitgevoerd:

-   Windows Server 2012 R2

-   Windows Server 2012

### Bestandsservers configureren voor het gebruik van de connector

1.  Zorg ervoor dat de bestandsservers zijn gemachtigd om de RMS-connector te gebruiken, met het beheerprogramma voor de RMS-connector en de informatie uit de sectie [Authorizing servers to use the RMS connector](install-configure-rms-connector.md#authorizing-servers-to-use-the-rms-connector) (Servers machtigen om de RMS-connector te gebruiken). Deze configuratie is vereist, zodat Exchange de RMS-connector kan gebruiken.

2.  Voer een van de volgende bewerkingen uit op de bestandsservers die zijn geconfigureerd voor infrastructuur voor bestandsclassificatie en die met de RMS-connector communiceren:

    -   Voer het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector uit. Zie [Het hulpprogramma voor serverconfiguratie voor de Microsoft RMS-connector gebruiken](#how-to-use-the-server-configuration-tool-for-microsoft-rms-connector) in dit artikel voor meer informatie.

        Als u het hulpprogramma bijvoorbeeld lokaal wilt uitvoeren om een bestandsserver te configureren:

        ```
        .\GenConnectorConfig.ps1 -ConnectorUri https://rmsconnector.contoso.com -SetFCI2012
        ```

    - Bewerk het register handmatig met de informatie in [Registry settings for the RMS connector](rms-connector-registry-settings.md) (Registerinstellingen voor de RMS-connector) om handmatig registerinstellingen toe te voegen op de servers. 

3.  Maak classificatieregels en bestandsbeheertaken om documenten te beveiligen met RMS-versleuteling en specificeer vervolgens een RMS-sjabloon om automatisch RMS-beleid toe te passen. Zie [Overzicht van Bestandsserverbronbeheer](http://technet.microsoft.com/library/hh831701.aspx) in de documentatiebibliotheek van Windows Server voor meer informatie.

## Volgende stappen
Nu de RMS-connector is geïnstalleerd en geconfigureerd en de servers zijn geconfigureerd om de connector te gebruiken, kunnen IT-beheerders en gebruikers e-mailberichten en documenten beveiligen en verbruiken met Azure RMS. Als u dit gemakkelijk wilt maken voor gebruikers, implementeert u de RMS-toepassing voor delen, waarna invoegtoepassing voor Office worden geïnstalleerd en nieuwe opties voor klikken met de rechtermuisknop worden toegevoegd aan Bestandenverkenner. Zie [Beheerdershandleiding voor de Rights Management-toepassing voor delen](../rms-client/sharing-app-admin-guide.md) voor meer informatie.

U kunt het [Azure Rights Management-implementatieschema](../plan-design/deployment-roadmap.md) gebruiken om te controleren of er andere configuratiestappen zijn die wilt uitvoeren voordat u [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] implementeert voor gebruikers en beheerders.

Zie [De Azure Rights Management-connector controleren](monitor-rms-connector.md) om de RMS-connector te controleren. 


<!--HONumber=Jun16_HO2-->


