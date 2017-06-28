---
title: De certificaatinfrastructuur voor SCEP configureren
description: Infrastructuur voor het maken en implementeren van SCEP-certificaatprofielen.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 9b62e03d88055c19a04c3968a1f060e20ae4fc65
ms.contentlocale: nl-nl
ms.lasthandoff: 06/08/2017

---
# <a name="configure-certificate-infrastructure-for-scep"></a>De certificaatinfrastructuur voor SCEP configureren

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt beschreven welke infrastructuur u nodig hebt om SCEP-certificaatprofielen te maken en implementeren.

### <a name="on-premises-infrastructure"></a>Lokale infrastructuur

-    **Active Directory-domein**: alle servers die in dit gedeelte worden genoemd (met uitzondering van de webtoepassingsproxyserver), moeten lid zijn van uw Active Directory-domein.

-  **Certificeringsinstantie** (CA): een certificeringsinstantie (CA) voor ondernemingen (CA) die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. Zie [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx)(De certificeringsinstantie installeren) voor instructies over het instellen van een certificeringsinstantie.
    Als de certificeringsinstantie werkt met Windows Server 2008 R2, moet u [de hotfix uit KB2483564 installeren](http://support.microsoft.com/kb/2483564/).
I
-  **NDES-Server**: op een server waarop Windows Server 2012 R2 of hoger wordt uitgevoerd, moet u de Registratieservice voor netwerkapparaten (NDES) instellen. Intune biedt geen ondersteuning voor het gebruik van NDES wanneer dit wordt uitgevoerd op een server waarop ook de CA voor ondernemingen wordt uitgevoerd. Zie [Richtlijnen voor Registratieservice voor netwerkapparaten](http://technet.microsoft.com/library/hh831498.aspx) voor instructies over hoe u Windows Server 2012 R2 configureert om als host voor de Registratieservice voor netwerkapparaten te dienen. De NDES-server moet worden toegevoegd aan het domein dat de CA host en mag zich niet op dezelfde server als de CA bevinden. Meer informatie over het implementeren van de NDES-server in een afzonderlijke forest, een geïsoleerd netwerk of een intern domein vindt u in [Een beleidsmodule gebruiken met de registratieservice voor netwerkapparaten](https://technet.microsoft.com/library/dn473016.aspx).

-  **Microsoft Intune-certificaatconnector**: u kunt de Intune-beheerconsole gebruiken om het installatieprogramma voor de **Certificaatconnector** (**ndesconnectorssetup.exe**) te downloaden. Vervolgens kunt u **ndesconnectorssetup.exe** uitvoeren op de computer waarop u de certificaatconnector wilt installeren.
-  **Webtoepassingsproxyserver** (optioneel): u kunt een server met Windows Server 2012 R2 of hoger als webtoepassingsproxyserver (WAP-server) gebruiken. Deze configuratie:
    -  Maakt het mogelijk dat apparaten certificaten ontvangen met een internetverbinding.
    -  Is een beveiligingsaanbeveling wanneer apparaten via internet verbinding maken om certificaten te ontvangen en te verlengen.

 > [!NOTE]           
> -    De server die als host voor WAP fungeert, [moet een update installeren](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) waarmee ondersteuning wordt geboden voor de lange URL's die worden gebruikt door de Network Device Enrollment Service. Deze update is opgenomen in het [updatepakket van december 2014](https://support.microsoft.com/kb/3013769)en is afzonderlijk verkrijgbaar in [KB3011135](https://support.microsoft.com/kb/3011135).
>-  Daarnaast moet de server waarop WAP als host optreedt, een SSL-certificaat hebben dat overeenkomt met de naam zoals die voor externe clients wordt gepubliceerd. Bovendien moet de server het SSL-certificaat vertrouwen dat op de NDES-server wordt gebruikt. De WAP-server kan met deze certificaten de SSL-verbinding van clients beëindigen en een nieuwe SSL-verbinding naar de NDES-server maken.
    Zie het gedeelte **Certificaten plannen** van [Publicatie van toepassingen met Web Application Proxy plannen](https://technet.microsoft.com/library/dn383650.aspx) voor meer informatie over certificaten voor WAP. Zie [Werken met Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) voor algemene informatie over WAP-servers.|

### <a name="network-requirements"></a>Netwerkvereisten

Van internet naar het perimeternetwerk, poort 443 toestaan van alle hosts/IP-adressen op internet naar de NDES-server.

Van het perimeternetwerk naar het vertrouwde netwerk, alle poorten en protocollen toestaan die nodig zijn voor domeintoegang tot de NDES-server die lid is van het domein. De NDES-server moet toegang hebben tot de certificaatservers, DNS-servers, Configuration Manager-servers en domeincontrollers.

Het is raadzaam de NDES-server te publiceren via een proxy, zoals de [Azure AD-toepassingsproxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx) of een proxy van een derde partij.


### <a name="BKMK_CertsAndTemplates"></a>Certificaten en sjablonen

|Object|Details|
|----------|-----------|
|**Certificaatsjabloon**|U configureert deze sjabloon op uw verlenende CA.|
|**Clientverificatiecertificaat**|Dit certificaat, dat wordt aangevraagd bij uw verlenende CA of openbare CA, installeert u op de NDES-server.|
|**Serververificatiecertificaat**|Dit SSL-certificaat, dat wordt aangevraagd bij uw verlenende CA of openbare CA, installeert en verbindt u in IIS op de NDES-server.|
|**Vertrouwde basis-CA-certificaat**|U exporteert dit als een **CER-bestand** van de basis-CA of een ander apparaat dat de basis-CA vertrouwt, en implementeert het naar apparaten met het profiel voor een vertrouwd CA-certificaat.<br /><br />U gebruikt één vertrouwd basis-CA-certificaat per besturingssysteemplatform en koppelt het aan elk vertrouwd basiscertificaatprofiel dat u maakt.<br /><br />U kunt extra vertrouwde basis-CA-certificaten gebruiken als dat nodig is. U kunt dit bijvoorbeeld doen om een vertrouwensrelatie met een CA te leveren die de serververificatiecertificaten voor uw Wi-Fi-toegangspunten ondertekent.|

### <a name="BKMK_Accounts"></a>Accounts

|Naam|Details|
|--------|-----------|
|**NDES-serviceaccount**|U geeft een domeingebruikersaccount op om als het NDES-serviceaccount te gebruiken.|

## <a name="BKMK_ConfigureInfrastructure"></a>Uw infrastructuur configureren
Voordat u certificaatprofielen kunt configureren, moet u de volgende taken uitvoeren waarvoor kennis van Windows Server 2012 R2 en Active Directory Certificate Services (ADCS) nodig is:

**Taak 1**: een NDES-serviceaccount maken

**Taak 2**: certificaatsjablonen configureren op de certificeringsinstantie

**Taak 3**: vereisten configureren op de NDES-server

**Taak 4**: NDES configureren voor gebruik met Intune

**Taak 5**: de Intune-certificaatconnector inschakelen, installeren en configureren

### <a name="task-1---create-an-ndes-service-account"></a>Taak 1: een NDES-serviceaccount maken

Maak een domeingebruikersaccount dat u als NDES-serviceaccount gaat gebruiken. U geeft dit account op wanneer u sjablonen op de verlenende CA configureert voordat u NDES installeert en configureert. Zorg ervoor dat de gebruiker over de standaardrechten **Lokaal aanmelden**, **Aanmelden als service** en **Aanmelden als batchtaak** beschikt. Sommige organisaties voeren een beveiligingsbeleid dat ervoor zorgt dat deze rechten worden uitgeschakeld.




### <a name="task-2---configure-certificate-templates-on-the-certification-authority"></a>Taak 2: certificaatsjablonen configureren op de certificeringsinstantie
In deze taak:

-   Configureert u een certificaatsjabloon voor NDES

-   Publiceert u de certificaatsjabloon voor NDES

##### <a name="to-configure-the-certification-authority"></a>De certificeringsinstantie configureren

1.  Meld u aan als ondernemingsbeheerder.

2.  Gebruik op de verlenende CA de module Certificaatsjablonen om een nieuwe aangepaste sjabloon te maken of een bestaande sjabloon te kopiëren en vervolgens een bestaande sjabloon te bewerken (zoals de gebruikerssjabloon) voor gebruik met NDES.

    De sjabloon moet de volgende configuraties hebben:

    -   Geef een gebruiksvriendelijke **weergavenaam voor de sjabloon** op.

    -   Selecteer op het tabblad **Onderwerpnaam** de optie **Met de aanvraag meeleveren**. (Beveiliging wordt afgedwongen door de Intune-beleidsmodule voor NDES.)

    -   Zorg ervoor dat op het tabblad **Extensies** de **beschrijving van toepassingsbeleid** de optie **Clientverificatie**bevat.

        > [!IMPORTANT]
        > Bewerk voor iOS- en Mac OS X-certificaatsjablonen op het tabblad **Extensies** het **sleutelgebruik** en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

    -   Selecteer op het tabblad **Beveiliging** het NDES-serviceaccount en wijs hieraan de machtiging **Registreren** toe voor de sjabloon. Intune-beheerders die SCEP-profielen maken, vereisen **leesrechten** om naar de sjabloon te kunnen bladeren tijdens het maken van SCEP-profielen.

    > [!NOTE]
    > Voor het intrekken van certificaten moet het NDES-serviceaccount voor elk certificaatsjabloon die door een certificaatprofiel wordt gebruikt, beschikken over rechten voor het *verlenen en beheren van certificaten*.

3.  Controleer de **geldigheidsperiode** op het tabblad **Algemeen** van de sjabloon. Standaard gebruikt Intune de waarde die is geconfigureerd in de sjabloon. U kunt de CA echter zodanig configureren dat de aanvrager een andere waarde kan opgeven, die u vervolgens vanuit de Intune-beheerconsole kunt instellen. Als u altijd de waarde in de sjabloon wilt gebruiken, slaat u de rest van deze stap over.

    > [!IMPORTANT]
    > Het iOS-platform en het Mac OS X-platform gebruiken altijd de waarde die in de sjabloon is ingesteld, ongeacht andere configuraties die u instelt.

Hier volgen schermafbeeldingen van de configuratie van een voorbeeldsjabloon.

![Sjabloon, tabblad Afhandeling van aanvragen](..\media\scep_ndes_request_handling.png)

![Sjabloon, tabblad Onderwerpnaam](..\media\scep_ndes_subject_name.jpg)

![Sjabloon, tabblad Beveiliging](..\media\scep_ndes_security.jpg)

![Sjabloon, tabblad Extensies](..\media\scep_ndes_extensions.jpg)

![Sjabloon, tabblad Uitgiftevereisten](..\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > Voor Toepassingsbeleid (in de vierde schermafbeelding) voegt u alleen het benodigde toepassingsbeleid toe. Leg uw keuzes voor aan de beveiligingsbeheerder.



Als u de CA zo wilt configureren dat de aanvrager de geldigheidsperiode kan opgeven, voert u op de CA de volgende opdrachten uit:

   1.  **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   2.  **net stop certsvc**

   3.  **net start certsvc**

4.  Gebruik op de verlenende CA de module Certificeringsinstantie om de certificaatsjabloon te publiceren.

    1.  Selecteer het knooppunt **Certificaatsjablonen**, klik op **Actie**-&gt; **Nieuw** &gt; **Te verlenen certificaatsjablonen** en selecteer vervolgens de sjabloon die u in stap 2 hebt gemaakt.

    2.  Controleer in de map **Certificaatsjablonen** of de sjabloon is gepubliceerd.


### <a name="task-3---configure-prerequisites-on-the-ndes-server"></a>Taak 3: vereisten configureren op de NDES-server
In deze taak:

-   Voegt u NDES toe aan een Windows Server en configureert u IIS om NDES te ondersteunen

-   Voegt u het NDES-serviceaccount toe aan de groep IIS_IUSR

-   Stelt u de SPN voor het NDES-serviceaccount in




   1.  U meldt zich als **ondernemingsbeheerder**aan op de server die als host voor NDES fungeert, en gebruikt vervolgens de [wizard Functies en onderdelen toevoegen](https://technet.microsoft.com/library/hh831809.aspx) om NDES te installeren:

    1.  Selecteer in de wizard **Active Directory Certificate Services** om toegang te krijgen tot de AD CS-functieservices. Selecteer de **inschrijvingsservice voor netwerkapparaten**, schakel **Certificeringsinstantie**uit en voer vervolgens de wizard uit.

        > [!TIP]
        > Klik op de pagina **Voortgang van de installatie** van de wizard niet op **Sluiten**. Klik in plaats daarvan op de koppeling voor **Active Directory Certificate Services op de doelserver configureren**. Hiermee opent u de wizard **AD CS-configuratie** die u voor de volgende taak gebruikt. Nadat AD CS-configuratie is geopend, kunt u de wizard Functies en onderdelen toevoegen sluiten.

    2.  Wanneer NDES aan de server wordt toegevoegd, installeert de wizard ook IIS. Controleer of IIS de volgende configuraties heeft:

        -   **Webserver** &gt; **Beveiliging** &gt; **Filtering aanvragen**

        -   **Webserver** &gt; **Toepassingsontwikkeling** &gt; **ASP.NET 3.5**. Als ASP.NET 3.5 wordt geïnstalleerd, wordt ook .NET Framework 3.5 geïnstalleerd. Als u .NET Framework 3.5 installeert, installeert u zowel het kernonderdeel **.NET Framework 3.5** als **HTTP-activering**.

        -   **Webserver** &gt; **Toepassingsontwikkeling** &gt; **ASP.NET 4.5**. Als ASP.NET 4.5 wordt geïnstalleerd, wordt ook .NET Framework 4.5 geïnstalleerd. Als u .NET Framework 4.5 installeert, installeert u het kernonderdeel **.NET Framework 4.5**, **ASP.NET 4.5** en **WCF-services** &gt; **HTTP-activering**.

        -   **Beheerhulpprogramma's** &gt; **Compatibiliteit met IIS 6-beheer** &gt; **Compatibiliteit met IIS 6-metabase**

        -   **Beheerhulpprogramma's** &gt; **Compatibiliteit met IIS 6-beheer** &gt; **Compatibiliteit met IIS 6 WMI**

  2.  Voeg op de server het NDES-serviceaccount toe als lid van de groep **IIS_IUSR**.

   3.  Voer de volgende opdracht uit via een opdrachtprompt met verhoogde bevoegdheid om de SPN van het NDES-serviceaccount in te stellen:

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   Bij bijvoorbeeld een NDES-server genaamd **Server01**, een domein genaamd **Contoso.com**en een serviceaccount genaamd **NDESService**gebruikt u:

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

### <a name="task-4---configure-ndes-for-use-with-intune"></a>Taak 4: NDES configureren voor gebruik met Intune
In deze taak:

-   Configureert u NDES voor gebruik met de verlenende CA

-   Verbindt u het (SSL-)serververificatiecertificaat in IIS

-   Configureert u aanvraagfiltering in IIS

##### <a name="to-configure-ndes-for-use-with-intune"></a>NDES configureren voor gebruik met Intune

1.  Open op de NDES-server de wizard AD CS-configuratie en voer de volgende configuraties door.

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

3. De NDES-server ontvangt zeer lange URL's (query's) waarvoor u twee registervermeldingen moet toevoegen:

    |Locatie|Waarde|Type|Gegevens|
    |-------|-----|----|----|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxFieldLength|DWORD|65534 (decimaal)|
    |HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters|MaxRequestBytes|DWORD|65534 (decimaal)|


4. Kies in IIS-manager achtereenvolgens **Standaardwebsite** -> **Filtering aanvragen** -> **Functie-instellingen bewerken** en wijzig de **Maximale URL-lengte** en **Maximale querytekenreeks** in *65534*, zoals wordt weergegeven.

    ![Maximale lengte van de URL's en query’s van IIS](..\media\SCEP_IIS_max_URL.png)

5.  Start de server opnieuw op. U kunt de wijzigingen niet voltooien door **iisreset** uit te voeren op de server.
6. Blader naar http://*FQDN*/certsrv/mscep/mscep.dll. Hier wordt een NDES-pagina weergegeven die vergelijkbaar is met de volgende:

    ![Test NDES](..\media\SCEP_NDES_URL.png)

    Als het bericht **503 - Service niet beschikbaar** wordt weergegeven, controleert u de logboeken. De groep van toepassing is waarschijnlijk gestopt vanwege een ontbrekend recht voor de NDES-gebruiker. Deze rechten worden beschreven in Taak 1.

##### <a name="to-install-and-bind-certificates-on-the-ndes-server"></a>Certificaten op de NDES-server installeren en verbinden

1.  Vraag op uw NDES-server een **serververificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat. Vervolgens verbindt u dit SSL-certificaat in IIS.

    > [!TIP]
    > Nadat u het SSL-certificaat in IIS hebt verbonden, installeert u ook een clientverificatiecertificaat. Dit certificaat kan worden verleend door elke CA die wordt vertrouwd door de NDES-server. Hoewel dit niet wordt aanbevolen, kunt u hetzelfde certificaat voor zowel server- als clientverificatie gebruiken zolang het certificaat beide EKU's (Enhance Key Usages) heeft. Bekijk de volgende stappen voor informatie over deze verificatiecertificaten.

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

2.  Klik op **Functie-instellingen bewerken**en stel het volgende in:

    **querytekenreeks (bytes)** = **65534**

    **Maximale URL-lengte (bytes)** = **65534**

3.  Controleer de volgende registersleutel:

    **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**

    Zorg ervoor dat de volgende waarden zijn ingesteld als DWORD-gegevens:

    Naam: **MaxFieldLength**, met een decimale waarde van **65534**

    Naam: **MaxRequestBytes**, met een decimale waarde van **65534**

4.  Start de NDES-server opnieuw op. De server is nu klaar om de certificaatconnector te ondersteunen.

### <a name="task-5---enable-install-and-configure-the-intune-certificate-connector"></a>Taak 5: de Intune-certificaatconnector inschakelen, installeren en configureren
In deze taak:

Schakelt u de ondersteuning voor NDES in Intune in.

Downloadt, installeert en configureert u de certificaatconnector op de NDES-server.

##### <a name="to-enable-support-for-the-certificate-connector"></a>Ondersteuning voor de certificaatconnector inschakelen

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com), klik op **Beheer** &gt; **Certificaatconnector**.

2.  Klik op **On-premises certificaatconnector configureren**.

3.  Selecteer **Certificaatconnector inschakelen**en klik vervolgens op **OK**.

##### <a name="to-download-install-and-configure-the-certificate-connector"></a>De certificaatconnector downloaden, installeren en configureren

1.  Open de [Intune-beheerconsole](https://manage.microsoft.com) en klik vervolgens op **Beheer** &gt; **Mobile Device Management** &gt; **Certificaatconnector** &gt; **Certificaatconnector downloaden**.

2.  Nadat het downloaden is voltooid, voert u het gedownloade installatieprogramma (**ndesconnectorssetup.exe**) uit op Windows Server 2012 R2-server: Het installatieprogramma installeert ook de beleidsmodule voor NDES en de CRP-webservice. (De CRP-webservice, CertificateRegistrationSvc, wordt als een toepassing in IIS uitgevoerd.)

    > [!NOTE]
    > Wanneer u NDES installeert en Intune zelfstandig wordt gebruikt, wordt de CRP-service automatisch met de certificaatconnector geïnstalleerd. Wanneer u Intune met Configuration Manager gebruikt, installeert u het certificaatregistratiepunt als een afzonderlijke sitesysteemfunctie.

3.  Als naar het clientcertificaat voor de certificaatconnector wordt gevraagd, klikt u op **Selecteren**en selecteert u het certificaat voor **clientverificatie** dat u in Taak 3 op uw NDES-server hebt geïnstalleerd.

    Nadat u het certificaat voor clientverificatie hebt geselecteerd, keert u terug naar het oppervlak **Clientcertificaat voor Microsoft Intune-certificaatconnector** . Hoewel het geselecteerde certificaat niet wordt weergegeven, klikt u op **Volgende** om de eigenschappen van dat certificaat weer te geven. Klik vervolgens op **Volgende**en **Installeren**.

4.  Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

    > [!TIP]
    > Als u de wizard sluit voordat u de gebruikersinterface van de certificaatconnector start, kunt u deze opnieuw openen door de volgende opdracht uit te voeren:
    >
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  In de gebruikersinterface van de **certificaatconnector** :

    Klik op **Aanmelden** en voer uw Intune-servicebeheerder- of tenantbeheerderreferenties met de machtiging voor algemeen beheer in.

    Als uw organisatie een proxyserver gebruikt en de NDES-server de proxy nodig heeft om toegang tot internet te krijgen, klikt u op **Proxyserver gebruiken** en geeft u de naam van de proxyserver, de poort en de accountreferenties op om verbinding te maken.

    Selecteer het tabblad **Geavanceerd** en geef vervolgens referenties op voor een account met de machtiging **Certificaten verlenen en beheren** op uw verlenende certificeringsinstantie. Klik vervolgens op **Toepassen**.

    U kunt nu de gebruikersinterface van de certificaatconnector sluiten.

6.  Open een opdrachtprompt en typ **services.msc**. Druk vervolgens op **Enter**, klik met de rechtermuisknop op **Intune-connectorservice** en klik vervolgens op **Opnieuw opstarten**.

Controleer of de service wordt uitgevoerd door een browser te openen en de volgende URL in te voeren. Hierop moet een **403** -fout worden geretourneerd:

**https:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**

## <a name="next-steps"></a>Volgende stappen
U bent nu klaar om certificaatprofielen te configureren, zoals beschreven in [Certificaatprofielen configureren](Configure-Intune-certificate-profiles.md).

