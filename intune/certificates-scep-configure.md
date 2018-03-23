---
title: SCEP-certificaten configureren en beheren met Microsoft Intune
description: Meer informatie over hoe u uw infrastructuur kunt configureren en vervolgens een SCEP-certificaatprofiel (Simple Certificate Enrollment Protocol) kunt maken en toewijzen in Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88109f1dc4543a5c71f36378fddb110c03afa08f
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2018
---
# <a name="configure-and-manage-scep-certificates-with-microsoft-intune"></a>SCEP-certificaten configureren en beheren met Microsoft Intune
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In dit onderwerp leest u hoe u uw infrastructuur kunt configureren en vervolgens SCEP-certificaatprofielen (Simple Certificate Enrollment Protocol) kunt maken en toewijzen met Intune.

## <a name="configure-on-premises-infrastructure"></a>Lokale infrastructuur configureren

-    **Active Directory-domein**: alle servers die in dit gedeelte worden genoemd (met uitzondering van de webtoepassingsproxyserver), moeten lid zijn van uw Active Directory-domein.

-  **Certificeringsinstantie** (CA): een certificeringsinstantie (CA) voor ondernemingen (CA) die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. Zie [De certificeringsinstantie installeren](http://technet.microsoft.com/library/jj125375.aspx) voor meer informatie.
    Als de certificeringsinstantie werkt met Windows Server 2008 R2, moet u [de hotfix uit KB2483564 installeren](http://support.microsoft.com/kb/2483564/).

-  **NDES-Server**: op een server waarop Windows Server 2012 R2 of hoger wordt uitgevoerd, moet u de Registratieservice voor netwerkapparaten (NDES) instellen. Intune biedt geen ondersteuning voor het gebruik van NDES wanneer dit wordt uitgevoerd op een server waarop ook de CA voor ondernemingen wordt uitgevoerd. Zie [Richtlijnen voor Registratieservice voor netwerkapparaten](http://technet.microsoft.com/library/hh831498.aspx) voor instructies over hoe u Windows Server 2012 R2 configureert om als host voor de Registratieservice voor netwerkapparaten te dienen.
De NDES-server moet worden toegevoegd aan het domein dat de CA host en mag zich niet op dezelfde server als de CA bevinden. Meer informatie over het implementeren van de NDES-server in een afzonderlijke forest, een geïsoleerd netwerk of een intern domein vindt u in [Een beleidsmodule gebruiken met de registratieservice voor netwerkapparaten](https://technet.microsoft.com/library/dn473016.aspx).

-  **Microsoft Intune-certificaatconnector**: u kunt de Azure-portal gebruiken om het installatieprogramma voor de **Certificaatconnector** (**ndesconnectorssetup.exe**) te downloaden. Vervolgens kunt u **ndesconnectorssetup.exe** uitvoeren op de server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd waar u de certificaatconnector wilt installeren. 
-  **Webtoepassingsproxyserver** (optioneel): u kunt een server met Windows Server 2012 R2 of hoger gebruiken als webtoepassingsproxyserver (WAP-server). Deze configuratie:
    -  Maakt het mogelijk dat apparaten certificaten ontvangen met een internetverbinding.
    -  Is een beveiligingsaanbeveling wanneer apparaten via internet verbinding maken om certificaten te ontvangen en te verlengen.

 > [!NOTE]           
> -    De server die als host voor WAP fungeert, [moet een update installeren](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) waarmee ondersteuning wordt geboden voor de lange URL's die worden gebruikt door de Network Device Enrollment Service. Deze update is opgenomen in het [updatepakket van december 2014](http://support.microsoft.com/kb/3013769)en is afzonderlijk verkrijgbaar in [KB3011135](http://support.microsoft.com/kb/3011135).
>-  Daarnaast moet de server waarop WAP als host optreedt, een SSL-certificaat hebben dat overeenkomt met de naam zoals die voor externe clients wordt gepubliceerd. Bovendien moet de server het SSL-certificaat vertrouwen dat op de NDES-server wordt gebruikt. De WAP-server kan met deze certificaten de SSL-verbinding van clients beëindigen en een nieuwe SSL-verbinding naar de NDES-server maken.
    Zie het gedeelte **Certificaten plannen** van [Publicatie van toepassingen met Web Application Proxy plannen](https://technet.microsoft.com/library/dn383650.aspx) voor meer informatie over certificaten voor WAP. Zie [Werken met Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) voor algemene informatie over WAP-servers.|

### <a name="network-requirements"></a>Netwerkvereisten

Van internet naar het perimeternetwerk, poort 443 toestaan van alle hosts/IP-adressen op internet naar de NDES-server.

Van het perimeternetwerk naar het vertrouwde netwerk, alle poorten en protocollen toestaan die nodig zijn voor domeintoegang tot de NDES-server die lid is van het domein. De NDES-server moet toegang hebben tot de certificaatservers, DNS-servers, Configuration Manager-servers en domeincontrollers.

Het is raadzaam de NDES-server te publiceren via een proxy, zoals de [Azure AD-toepassingsproxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx) of een proxy van een derde partij.


### <a name="certificates-and-templates"></a>Certificaten en sjablonen

|Object|Details|
|----------|-----------|
|**Certificaatsjabloon**|Configureer deze sjabloon op uw verlenende CA.|
|**Clientverificatiecertificaat**|Dit certificaat wordt aangevraagd bij uw verlenende CA of openbare CA. U installeert dit op de NDES-server.|
|**Serververificatiecertificaat**|Dit SSL-certificaat wordt aangevraagd bij uw verlenende CA of openbare CA. U installeert en verbindt dit in IIS op de NDES-server.|
|**Vertrouwd basis-CA-certificaat**|U exporteert dit certificaat als een **CER-bestand** van de basis-CA of een ander apparaat dat de basis-CA vertrouwt, en wijst het toe aan apparaten met het profiel voor een vertrouwd CA-certificaat.<br /><br />U gebruikt één vertrouwd basis-CA-certificaat per besturingssysteemplatform en koppelt het aan elk vertrouwd basiscertificaatprofiel dat u maakt.<br /><br />U kunt extra vertrouwde basis-CA-certificaten gebruiken als dat nodig is. U kunt dit bijvoorbeeld doen om een vertrouwensrelatie met een CA te leveren die de serververificatiecertificaten voor uw Wi-Fi-toegangspunten ondertekent.|

### <a name="accounts"></a>Accounts

|Naam|Details|
|--------|-----------|
|**NDES-serviceaccount**|Geef een domeingebruikersaccount op die u wilt gebruiken als het NDES-serviceaccount.|

## <a name="configure-your-infrastructure"></a>Uw infrastructuur configureren
Voordat u certificaatprofielen kunt configureren, moet u de volgende taken uitvoeren waarvoor kennis van Windows Server 2012 R2 en Active Directory Certificate Services (ADCS) nodig is:

**Stap 1**: een NDES-serviceaccount maken

**Stap 2**: certificaatsjablonen configureren op de certificeringsinstantie

**Stap 3**: vereisten configureren op de NDES-server

**Stap 4**: NDES configureren voor gebruik met Intune

**Stap 5**: de Intune-certificaatconnector inschakelen, installeren en configureren

#### <a name="step-1---create-an-ndes-service-account"></a>Stap 1: een NDES-serviceaccount maken

Maak een domeingebruikersaccount dat u als NDES-serviceaccount gaat gebruiken. U geeft dit account op wanneer u sjablonen op de verlenende CA configureert voordat u NDES installeert en configureert. Zorg ervoor dat de gebruiker over de standaardrechten **Lokaal aanmelden**, **Aanmelden als service** en **Aanmelden als batchtaak** beschikt. Sommige organisaties voeren een beveiligingsbeleid dat ervoor zorgt dat deze rechten worden uitgeschakeld.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Stap 2: certificaatsjablonen configureren op de certificeringsinstantie
In deze taak:

-   Configureert u een certificaatsjabloon voor NDES

-   Publiceert u de certificaatsjabloon voor NDES

##### <a name="to-configure-the-certification-authority"></a>De certificeringsinstantie configureren

1.  Meld u aan als ondernemingsbeheerder.

2.  Gebruik op de verlenende CA de module Certificaatsjablonen om een nieuwe aangepaste sjabloon te maken of een bestaande sjabloon te kopiëren en vervolgens een bestaande sjabloon te bewerken (zoals de gebruikerssjabloon) voor gebruik met NDES.

    >[!NOTE]
    > De NDES-certificaatsjabloon moet zijn gebaseerd op een versie 2 certificaatsjabloon (met Windows 2003-compatibiliteit).

    De sjabloon moet de volgende configuraties hebben:

    -   Geef een gebruiksvriendelijke **weergavenaam voor de sjabloon** op.

    -   Selecteer op het tabblad **Onderwerpnaam** de optie **Met de aanvraag meeleveren**. (Beveiliging wordt afgedwongen door de Intune-beleidsmodule voor NDES.)

    -   Zorg ervoor dat op het tabblad **Extensies** de **beschrijving van toepassingsbeleid** de optie **Clientverificatie**bevat.

        > [!IMPORTANT]
        > Bewerk voor iOS- en macOS-certificaatsjablonen op het tabblad **Extensies** het **sleutelgebruik** en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

    -   Selecteer op het tabblad **Beveiliging** het NDES-serviceaccount en wijs hieraan de machtiging **Registreren** toe voor de sjabloon. Intune-beheerders die SCEP-profielen maken, vereisen **leesrechten** om naar de sjabloon te kunnen bladeren tijdens het maken van SCEP-profielen.

    > [!NOTE]
    > Voor het intrekken van certificaten moet het NDES-serviceaccount voor elk certificaatsjabloon die door een certificaatprofiel wordt gebruikt, beschikken over rechten voor het *verlenen en beheren van certificaten*.

3.  Controleer de **geldigheidsperiode** op het tabblad **Algemeen** van de sjabloon. Standaard gebruikt Intune de waarde die is geconfigureerd in de sjabloon. U kunt de CA echter zodanig configureren dat de aanvrager een andere waarde kan opgeven, die u vervolgens vanuit de Intune-beheerconsole kunt instellen. Als u altijd de waarde in de sjabloon wilt gebruiken, slaat u de rest van deze stap over.

    > [!IMPORTANT]
    > iOS en macOS gebruiken altijd de waarde die in de sjabloon is ingesteld, ongeacht andere configuraties die u instelt.

Hier volgen schermafbeeldingen van de configuratie van een voorbeeldsjabloon.

![Sjabloon, tabblad Afhandeling van aanvragen](.\media\scep_ndes_request_handling.png)

![Sjabloon, tabblad Onderwerpnaam](.\media\scep_ndes_subject_name.jpg)

![Sjabloon, tabblad Beveiliging](.\media\scep_ndes_security.jpg)

![Sjabloon, tabblad Extensies](.\media\scep_ndes_extensions.jpg)

![Sjabloon, tabblad Uitgiftevereisten](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Voor Toepassingsbeleid voegt u alleen het benodigde toepassingsbeleid toe. Leg uw keuzes voor aan de beveiligingsbeheerder.



De CA zodanig configureren dat de aanvrager de geldigheidsperiode kan opgeven:

1. Voer de volgende opdracht voor de CA uit:
    - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
    - **net stop certsvc**
    - **net start certsvc**
2. Gebruik op de verlenende CA de module Certificeringsinstantie om de certificaatsjabloon te publiceren.
    Selecteer het knooppunt **Certificaatsjablonen**, klik op **Actie**-&gt; **Nieuw** &gt; **Te verlenen certificaatsjablonen** en selecteer vervolgens de sjabloon die u in stap 2 hebt gemaakt.
3. Controleer in de map **Certificaatsjablonen** of de sjabloon is gepubliceerd.


#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Stap 3: vereisten configureren op de NDES-server
In deze taak:

-   Voegt u NDES toe aan een Windows Server en configureert u IIS om NDES te ondersteunen

-   Voegt u het NDES-serviceaccount toe aan de groep IIS_IUSR

-   Stelt u de SPN voor het NDES-serviceaccount in




   1.  U meldt zich als **ondernemingsbeheerder** aan op de server die als host voor NDES fungeert, en gebruikt vervolgens de [wizard Functies en onderdelen toevoegen](https://technet.microsoft.com/library/hh831809.aspx) om NDES te installeren:

    1.  Selecteer in de wizard **Active Directory Certificate Services** om toegang te krijgen tot de AD CS-functieservices. Selecteer de **inschrijvingsservice voor netwerkapparaten**, schakel **Certificeringsinstantie**uit en voer vervolgens de wizard uit.

        > [!TIP]
        > Klik op de pagina **Voortgang van de installatie** van de wizard niet op **Sluiten**. Klik in plaats daarvan op de koppeling voor **Active Directory Certificate Services op de doelserver configureren**. Hiermee opent u de wizard **AD CS-configuratie** die u voor de volgende taak gebruikt. Nadat AD CS-configuratie is geopend, kunt u de wizard Functies en onderdelen toevoegen sluiten.

    2.  Wanneer NDES aan de server wordt toegevoegd, installeert de wizard ook IIS. Controleer of IIS de volgende configuraties heeft:

        -   **Webserver** &gt; **Beveiliging** &gt; **Filtering aanvragen**

        -   **Webserver** &gt; **Toepassingsontwikkeling** &gt; **ASP.NET 3.5**. Als u ASP.NET 3.5 installeert, installeert u ook .NET Framework 3.5. Als u .NET Framework 3.5 installeert, installeert u zowel het kernonderdeel **.NET Framework 3.5** als **HTTP-activering**.

        -   **Webserver** &gt; **Toepassingsontwikkeling** &gt; **ASP.NET 4.5**. Als u ASP.NET 4.5 installeert, installeert u ook .NET Framework 4.5. Als u .NET Framework 4.5 installeert, installeert u het kernonderdeel **.NET Framework 4.5**, **ASP.NET 4.5** en **WCF-services** &gt; **HTTP-activering**.

        -   **Beheerhulpprogramma's** &gt; **Compatibiliteit met IIS 6-beheer** &gt; **Compatibiliteit met IIS 6-metabase**

        -   **Beheerhulpprogramma's** &gt; **Compatibiliteit met IIS 6-beheer** &gt; **Compatibiliteit met IIS 6 WMI**

  2.  Voeg op de server het NDES-serviceaccount toe als lid van de groep **IIS_IUSR**.

   3.  Voer de volgende opdracht uit via een opdrachtprompt met verhoogde bevoegdheid om de SPN van het NDES-serviceaccount in te stellen:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Bij bijvoorbeeld een NDES-server genaamd **Server01**, een domein genaamd **Contoso.com**en een serviceaccount genaamd **NDESService**gebruikt u:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Stap 4: NDES configureren voor gebruik met Intune
In deze taak:

-   Configureert u NDES voor gebruik met de verlenende CA

-   Verbindt u het (SSL-)serververificatiecertificaat in IIS

-   Configureert u aanvraagfiltering in IIS


1.  Open op de NDES-server de wizard AD CS-configuratie en voer de volgende configuraties door:

    > [!TIP]
    > Als u op de koppeling in de vorige taak hebt geklikt, is deze wizard al geopend. Anders opent u Serverbeheer voor toegang tot post-implementatieconfiguratie voor Active Directory Certificate Services.

    -   Selecteer op de pagina **Functieservices** de optie **Registratieservice voor netwerkapparaten**.

    -   Geef op de pagina **Serviceaccount voor NDES** het NDES-serviceaccount op.

    -   Klik op de pagina **Certificeringsinstantie voor Registratieservice voor netwerkapparaten** op **Selecteren**en selecteer vervolgens de verlenende CA waar u de certificaatsjabloon hebt geconfigureerd.

    -   Stel op de pagina **Cryptografie voor NDES** de sleutellengte in om aan de vereisten van uw bedrijf te voldoen.

    Klik op de pagina **Bevestiging** op **Configureren** om de wizard te voltooien.

2.  Nadat de wizard is voltooid, bewerkt u de volgende registersleutel op de NDES-server:

    -   **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**

    Als u deze sleutel wilt bewerken, stelt u het **doel** van de certificaatsjabloon vast (dit kunt u vinden op het bijbehorende tabblad **Afhandeling van aanvragen**) en bewerkt u vervolgens de bijbehorende vermelding in het register. U doet dit door de bestaande gegevens te vervangen door de naam van de certificaatsjabloon (niet de weergavenaam van de sjabloon) die u hebt opgegeven in Taak 1. In de volgende tabel wordt het certificaatsjabloondoel gekoppeld aan de waarden in het register:

    |Certificaatsjabloondoel (op het tabblad Afhandeling van aanvragen)|Te bewerken registerwaarde|Waarde die in de Intune-beheerconsole wordt weergegeven voor het SCEP-profiel|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |Handtekening|SignatureTemplate|Digitale handtekening|
    |Versleuteling|EncryptionTemplate|Sleutelcodering|
    |Handtekening en versleuteling|GeneralPurposeTemplate|Sleutelcodering<br /><br />Digitale handtekening|
    Als het doel van uw certificaatsjabloon bijvoorbeeld **Versleuteling**is, bewerkt u de waarde **EncryptionTemplate** zo dat deze de naam van uw certificaatsjabloon is.

3. De NDES-server ontvangt lange URL's (query's) waarvoor u twee registervermeldingen moet toevoegen:

    |Locatie|Waarde|Type|Gegevens|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (decimaal)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (decimaal)|


4. Selecteer in IIS Manager achtereenvolgens **Standaardwebsite** -> **Filteren aanvragen** -> **Functie-instellingen bewerken** en wijzig de **Maximale URL-lengte** en **Maximale querytekenreeks** in *65534*, zoals wordt weergegeven.

    ![Maximale lengte van de URL's en query's van IIS](.\media\SCEP_IIS_max_URL.png)

5.  Start de server opnieuw op. U kunt de wijzigingen niet voltooien door **iisreset** uit te voeren op de server.
6. Blader naar http://*FQDN*/certsrv/mscep/mscep.dll. Hier wordt een NDES-pagina weergegeven die vergelijkbaar is met de volgende:

    ![Test NDES](.\media\SCEP_NDES_URL.png)

    Als het bericht **503 - Service niet beschikbaar** wordt weergegeven, controleert u de logboeken. De groep van toepassing is waarschijnlijk gestopt vanwege een ontbrekend recht voor de NDES-gebruiker. Deze rechten worden beschreven in Taak 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Certificaten op de NDES-server installeren en verbinden

1.  Vraag op uw NDES-server een **serververificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat. Vervolgens verbindt u dit SSL-certificaat in IIS.

    > [!TIP]
    > Nadat u het SSL-certificaat in IIS hebt verbonden, installeert u een clientverificatiecertificaat. Dit certificaat kan worden verleend door elke CA die wordt vertrouwd door de NDES-server. Hoewel dit niet wordt aanbevolen, kunt u hetzelfde certificaat voor zowel server- als clientverificatie gebruiken zolang het certificaat beide EKU's (Enhance Key Usages) heeft. Bekijk de volgende stappen voor informatie over deze verificatiecertificaten.

    1.  Nadat u het serververificatiecertificaat hebt verkregen, opent u **IIS-beheer**, selecteert u de **standaardwebsite** in het deelvenster **Verbindingen** en klikt u vervolgens op **Bindingen** in het deelvenster **Acties** .

    2.  Klik op **Toevoegen**, stel **Type** in op **https**en controleer vervolgens of de poort **443**is. (Als Intune zelfstandig wordt gebruikt, wordt alleen poort 443 ondersteund.

    3.  Geef voor het **SSL-certificaat**het serververificatiecertificaat op.

        > [!NOTE]
        > Als de NDES-server zowel een externe als interne naam voor één netwerkadres gebruikt, moet het serververificatiecertificaat een **onderwerpnaam** met een externe openbare servernaam en een **alternatieve naam voor het onderwerp** met de interne servernaam hebben.

2.  Vraag op uw NDES-server een **clientverificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat. Dit kan hetzelfde certificaat zijn als het serververificatiecertificaat als dat certificaat beide mogelijkheden heeft.

    Het clientverificatiecertificaat moet de volgende eigenschappen hebben:

    **Uitgebreid sleutelgebruik**: dit moet **Clientverificatie** omvatten.

    **Onderwerpnaam**: deze moet gelijk zijn aan de DNS-naam van de server waarop u het certificaat installeert (de NDES-server).

##### <a name="to-configure-iis-request-filtering"></a>IIS-aanvraagfiltering configureren

1.  Open op de NDES-server **IIS-beheer**, selecteer de **standaardwebsite** in het deelvenster **Verbindingen** en open vervolgens **Aanvraagfiltering**.

2.  Klik op **Functie-instellingen bewerken**en stel de waarden in:

    **querytekenreeks (bytes)** = **65534**

    **Maximale URL-lengte (bytes)** = **65534**

3.  Controleer de volgende registersleutel:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Zorg ervoor dat de volgende waarden zijn ingesteld als DWORD-gegevens:

    Naam: **MaxFieldLength**, met een decimale waarde van **65534**

    Naam: **MaxRequestBytes**, met een decimale waarde van **65534**

4. Start de NDES-server opnieuw op. De server is nu klaar om de certificaatconnector te ondersteunen.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Stap 5: de Intune-certificaatconnector inschakelen, installeren en configureren
In deze taak:

- Schakelt u de ondersteuning voor NDES in Intune in.
- Download, installeer en configureer de certificaatconnector op de server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd/server in uw omgeving. Als u de schaalbaarheid van de NDES-implementatie in uw organisatie wilt vergroten, kunt u op elke NDES-server meerdere NDES-servers met een certificaatconnector van Microsoft Intune installeren.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>De certificaatconnector downloaden, installeren en configureren
![ConnectorDownload](./media/certificates-download-connector.png)   
 
1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
4. Selecteer in het deelvenster **Apparaatconfiguratie** de optie **Certificeringsinstantie**.
5. Klik op **Toevoegen** en selecteer **Connectorbestand downloaden**. Sla het bestand op in een locatie waar u het kunt openen vanaf de server waarop u de connector gaat installeren. 
6.  Nadat het downloaden is voltooid, voert u het gedownloade installatieprogramma (**ndesconnectorssetup.exe**) uit op server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd. Het installatieprogramma installeert ook de beleidsmodule voor NDES en de CRP-webservice. (De CRP-webservice, CertificateRegistrationSvc, wordt als een toepassing in IIS uitgevoerd.)

    > [!NOTE]
    > Wanneer u NDES installeert en Intune zelfstandig wordt gebruikt, wordt de CRP-service automatisch met de certificaatconnector geïnstalleerd. Wanneer u Intune met Configuration Manager gebruikt, installeert u het certificaatregistratiepunt als een afzonderlijke sitesysteemfunctie.

3.  Als naar het clientcertificaat voor de certificaatconnector wordt gevraagd, kiest u **Selecteren**en selecteert u het certificaat voor **clientverificatie** dat u in Taak 3 op uw NDES-server hebt geïnstalleerd.

    Nadat u het certificaat voor clientverificatie hebt geselecteerd, keert u terug naar het oppervlak **Clientcertificaat voor Microsoft Intune-certificaatconnector** . Hoewel het geselecteerde certificaat niet wordt weergegeven, klikt u op **Volgende** om de eigenschappen van dat certificaat weer te geven. Klik vervolgens op **Volgende**en **Installeren**.

4.  Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

    > [!TIP]
    > Als u de wizard sluit voordat u de gebruikersinterface van de certificaatconnector start, kunt u deze opnieuw openen door de volgende opdracht uit te voeren:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In de gebruikersinterface van de **certificaatconnector** :

    Klik op **Aanmelden** en voer uw Intune-servicebeheerder- of tenantbeheerderreferenties met de machtiging voor algemeen beheer in.

    > [!IMPORTANT]
    > Aan het gebruikersaccount moet een geldige Intune-licentie worden toegewezen. Als het gebruikersaccount geen geldige Intune-licentie heeft, mislukt NDESConnectorUI.exe.

    Als uw organisatie een proxyserver gebruikt en de NDES-server de proxy nodig heeft om toegang tot internet te krijgen, klikt u op **Proxyserver gebruiken** en geeft u de naam van de proxyserver, de poort en de accountreferenties op om verbinding te maken.

    Selecteer het tabblad **Geavanceerd** en geef vervolgens referenties op voor een account met de machtiging **Certificaten verlenen en beheren** op uw verlenende certificeringsinstantie. Klik vervolgens op **Toepassen**.

    U kunt nu de gebruikersinterface van de certificaatconnector sluiten.

6.  Open een opdrachtprompt en typ **services.msc**. Druk vervolgens op **Enter**, klik met de rechtermuisknop op **Intune-connectorservice** en klik vervolgens op **Opnieuw opstarten**.

Controleer of de service wordt uitgevoerd door een browser te openen en de volgende URL in te voeren. Hierop moet een **403** -fout worden geretourneerd:

**http:// &lt;FQDN_van_uw_NDES-server&gt;/certsrv/mscep/mscep.dll**

## <a name="how-to-create-a-scep-certificate-profile"></a>Een SCEP-certificaatprofiel maken

1. Selecteer in Azure Portal de workload **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** in het deelvenster **Apparaatconfiguratie**.
3. Selecteer **Profiel maken** in het deelvenster Profielen.
4. Voer in het deelvenster **Profiel maken** een **naam** en een **beschrijving** in voor het SCEP-certificaatprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit SCEP-certificaat. Op dit moment kunt u een van de volgende platforms selecteren voor apparaatbeperkingsinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**
6. Selecteer in de vervolgkeuzelijst **Profieltype** de optie **SCEP-certificaat**.
7. Configureer in het deelvenster **SCEP-certificaat** de volgende instellingen:
    - **Geldigheidsduur van certificaat**: als u de opdracht **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** hebt uitgevoerd voor de verlenende CA, waarmee een aangepaste geldigheidsperiode mogelijk is, kunt u opgeven hoe lang het certificaat geldig blijft.<br>U kunt een waarde opgeven die lager is dan de geldigheidsperiode in het opgegeven certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in het certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA. 
    - **Sleutelarchiefprovider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): geef op waar de sleutel voor het certificaat wordt opgeslagen. Kies een van de volgende waarden:
        - **Registeren in de sleutelarchiefprovider voor TPM (Trusted Platform Module) indien TPM aanwezig is, anders registreren in de sleutelarchiefprovider voor software**
        - **Registreren in de sleutelarchiefprovider voor TPM (Trusted Platform Module), anders mislukt**
        - **Registreren bij Passport, anders niet uitvoeren (Windows 10 en hoger)**
        - **Registreren in sleutelarchiefprovider voor software**
    - **Indeling van de onderwerpnaam**: selecteer in de lijst hoe de onderwerpnaam in de certificaataanvraag automatisch wordt gemaakt met Intune. Als het certificaat voor een gebruiker is, kunt u ook het e-mailadres van de gebruiker in de onderwerpnaam opnemen. U kunt kiezen uit:
        - **Niet geconfigureerd**
        - **Algemene naam**
        - **Algemene naam en e-mailadres**
        - **Algemene naam als e-mailadres**
        - **IMEI (International Mobile Equipment Identity)**
        - **Serienummer**
        - **Aangepast:** als u deze optie selecteert, wordt een ander veld van de vervolgkeuzelijst weergegeven. Met dit veld kunt u een indeling van de aangepaste onderwerpnaam invoeren. De twee variabelen die worden ondersteund voor de aangepaste indeling zijn **Algemene naam (CN)** en **E-mail (E)**. Met behulp van een combinatie van een of meerdere van deze variabelen en statische tekenreeksen kunt u een aangepaste indeling voor de onderwerpnaam maken, zoals: **CN={{UserName}},E={{EmailAddress}},OU=Mobiel,O=Financiële groep,L=Redmond,ST=Washington,C=VS** In dit voorbeeld hebt u een indeling voor een onderwerpnaam gemaakt die naast de CN- en E-variabelen tekenreeksen voor de waarden van de organisatie-eenheid, de organisatie, de locatie, de staat en het land gebruikt. [In dit onderwerp](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) worden de functie **CertStrToName** en de ondersteunde tekenreeksen gedemonstreerd.
        
    - **Alternatieve onderwerpnaam**: geef op hoe de waarden voor de alternatieve naam van het onderwerp (SAN) in de certificaataanvraag automatisch worden gemaakt met Intune. Als u bijvoorbeeld een gebruikerscertificaattype selecteerde, kunt u de User Principal Name (UPN) gebruiken in de alternatieve naam van het onderwerp. Als het clientcertificaat wordt gebruikt om een Network Policy Server te verifiëren, dient u de alternatieve naam van het onderwerp op de UPN in te stellen. 
    - **Sleutelgebruik**: geef opties voor sleutelgebruik voor het certificaat op. U kunt kiezen uit de volgende opties: 
        - **Sleutelcodering**: sta alleen sleuteluitwisseling toe als de sleutel is gecodeerd. 
        - **Digitale handtekening**: sta alleen sleuteluitwisseling toe als een digitale handtekening de sleutel helpt beveiligen. 
    - **Sleutelgrootte (bits)**: selecteer het aantal bits in de sleutel. 
    - **Hash-algoritme** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): selecteer een van de beschikbare typen hash-algoritme om met dit certificaat te gebruiken. Selecteer het sterkste beveiligingsniveau dat door de verbindende apparaten wordt ondersteund. 
    - **Basiscertificaat**: kies een basis-CA-certificaatprofiel dat u eerder hebt geconfigureerd en aan de gebruiker of het apparaat hebt toegewezen. Dit CA-certificaat moet het basiscertificaat zijn voor de CA die het certificaat verleent dat u in dit certificaatprofiel gaat configureren. 
    - **Uitgebreide-sleutelgebruik**: selecteer **Toevoegen** om waarden voor het beoogde gebruik van het certificaat toe te voegen. In de meeste gevallen vereist het certificaat **Clientverificatie** zodat de gebruiker of het apparaat bij een server kan worden geverifieerd. U kunt echter zo nodig andere sleutelgebruiken toevoegen. 
    - **Registratie-instellingen**
        - **Drempelwaarde voor verlenging (%)**: geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
        - **URL's van SCEP-server**: geef een of meer URL's op voor de NDES-servers die certificaten via SCEP verlenen. 
8. Selecteer **OK** en ga vervolgens terug naar het deelvenster **Profiel maken** en selecteer **Maken**.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

## <a name="how-to-assign-the-certificate-profile"></a>Het certificaatprofiel toewijzen

Overweeg het volgende voordat u certificaatprofielen aan groepen toewijst:

- Wanneer u certificaatprofielen aan groepen toewijst, wordt het certificaatbestand van het vertrouwde CA-certificaatprofiel op het apparaat geïnstalleerd. Het apparaat gebruikt het SCEP-certificaatprofiel om een certificaataanvraag te maken.
- Certificaatprofielen worden alleen geïnstalleerd op apparaten met het platform dat u gebruikt wanneer u het profiel maakt.
- U kunt certificaatprofielen toewijzen aan gebruikersverzamelingen of apparaatverzamelingen.
- Als u een certificaat snel naar een apparaat wilt publiceren nadat het apparaat is geregistreerd, wijst u het certificaatprofiel toe aan een gebruikersgroep en niet aan een apparaatgroep. Als u het toewijst aan een apparaatgroep, is een volledige apparaatregistratie vereist voordat het apparaat beleid kan ontvangen.
- Hoewel u elk profiel afzonderlijk toewijst, moet u ook het vertrouwde basis-CA- en het SCEP- of PKCS-profiel toewijzen. Anders mislukt het SCEP- of PKCS-certificaatbeleid.

Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor informatie over het toewijzen van apparaatprofielen.

