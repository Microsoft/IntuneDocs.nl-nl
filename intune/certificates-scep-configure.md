---
title: SCEP-certificaten gebruiken met Microsoft Intune - Azure | Microsoft Docs
description: Als u SCEP-certificaten in Microsoft Intune wilt gebruiken, configureert u uw on-premises AD-domein, maakt u een certificeringsinstantie, stelt u de NDES-server in en installeert u de Intune-certificaatconnector. Vervolgens maakt u een SCEP-certificaatprofiel en wijst u dit profiel toe aan groepen. Zie ook de andere gebeurtenis-id's en de bijbehorende beschrijvingen, en de diagnostische codes voor de Intune-connectorservice.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5441bb15d6906257432afbfe51fffc6c11a6324
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745023"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>SCEP-certificaten configureren en gebruiken met Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u hoe u uw infrastructuur kunt configureren en vervolgens SCEP-certificaatprofielen (Simple Certificate Enrollment Protocol) kunt maken en toewijzen met Intune.

## <a name="configure-on-premises-infrastructure"></a>Lokale infrastructuur configureren

- **Active Directory-domein**: alle servers die in dit gedeelte worden genoemd (met uitzondering van de webtoepassingsproxyserver), moeten lid zijn van uw Active Directory-domein.

- **Certificeringsinstantie** (CA): een certificeringsinstantie (CA) voor ondernemingen (CA) die wordt uitgevoerd op een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. Zie [De certificeringsinstantie installeren](http://technet.microsoft.com/library/jj125375.aspx) voor meer informatie.
    Als de certificeringsinstantie werkt met Windows Server 2008 R2, moet u [de hotfix uit KB2483564 installeren](http://support.microsoft.com/kb/2483564/).

- **NDES-Server**: op een server waarop Windows Server 2012 R2 of hoger wordt uitgevoerd, moet u de Registratieservice voor netwerkapparaten (NDES) instellen. Intune biedt geen ondersteuning voor het gebruik van NDES wanneer dit wordt uitgevoerd op een server waarop ook de CA voor ondernemingen wordt uitgevoerd. Zie [Richtlijnen voor Registratieservice voor netwerkapparaten](http://technet.microsoft.com/library/hh831498.aspx) voor instructies over hoe u Windows Server 2012 R2 configureert om als host voor de Registratieservice voor netwerkapparaten te dienen.
De NDES-server moet worden toegevoegd aan het domein dat de CA host en mag zich niet op dezelfde server als de CA bevinden. Meer informatie over het implementeren van de NDES-server in een afzonderlijke forest, een geïsoleerd netwerk of een intern domein vindt u in [Een beleidsmodule gebruiken met de registratieservice voor netwerkapparaten](https://technet.microsoft.com/library/dn473016.aspx).

- **Microsoft Intune-certificaatconnector**: u kunt de Azure-portal gebruiken om het installatieprogramma voor de **Certificaatconnector** (**ndesconnectorssetup.exe**) te downloaden. Vervolgens kunt u **ndesconnectorssetup.exe** uitvoeren op de server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd waar u de certificaatconnector wilt installeren. 
- **Webtoepassingsproxyserver** (optioneel): u kunt een server met Windows Server 2012 R2 of hoger gebruiken als webtoepassingsproxyserver (WAP-server). Deze configuratie:
  -  Maakt het mogelijk dat apparaten certificaten ontvangen met een internetverbinding.
  -  Is een beveiligingsaanbeveling wanneer apparaten via internet verbinding maken om certificaten te ontvangen en te verlengen.

#### <a name="additional"></a>Aanvullende informatie
- De server die als host voor WAP fungeert, [moet een update installeren](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) waarmee ondersteuning wordt geboden voor de lange URL's die worden gebruikt door de Network Device Enrollment Service. Deze update is opgenomen in het [updatepakket van december 2014](http://support.microsoft.com/kb/3013769)en is afzonderlijk verkrijgbaar in [KB3011135](http://support.microsoft.com/kb/3011135).
- De WAP-server moet een SSL-certificaat hebben dat overeenkomt met de naam zoals die voor externe clients wordt gepubliceerd en het SSL-certificaat vertrouwen dat op de NDES-server wordt gebruikt. De WAP-server kan met deze certificaten de SSL-verbinding van clients beëindigen en een nieuwe SSL-verbinding naar de NDES-server maken.

Zie [Certificaten voor WAP plannen](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) en [algemene informatie over WAP-servers](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)) voor meer informatie.

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
|**NDES-serviceaccount**|Voer een domeingebruikersaccount in dat u als NDES-serviceaccount gaat gebruiken.|

## <a name="configure-your-infrastructure"></a>Uw infrastructuur configureren
Voordat u certificaatprofielen kunt configureren, moet u de volgende taken uitvoeren. Voor deze taken is kennis nodig van Windows Server 2012 R2 en Active Directory Certificate Services (ADCS):

**Stap 1**: een NDES-serviceaccount maken

**Stap 2**: certificaatsjablonen configureren op de certificeringsinstantie

**Stap 3**: vereisten configureren op de NDES-server

**Stap 4**: NDES configureren voor gebruik met Intune

**Stap 5**: de Intune-certificaatconnector inschakelen, installeren en configureren

#### <a name="step-1---create-an-ndes-service-account"></a>Stap 1: een NDES-serviceaccount maken

Maak een domeingebruikersaccount dat u als NDES-serviceaccount gaat gebruiken. U voert dit account in wanneer u sjablonen op de verlenende CA configureert voordat u NDES installeert en configureert. Zorg ervoor dat de gebruiker over de standaardrechten **Lokaal aanmelden**, **Aanmelden als service** en **Aanmelden als batchtaak** beschikt. Sommige organisaties voeren een beveiligingsbeleid dat ervoor zorgt dat deze rechten worden uitgeschakeld.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Stap 2: certificaatsjablonen configureren op de certificeringsinstantie
In deze taak:

- Configureert u een certificaatsjabloon voor NDES
- Publiceert u de certificaatsjabloon voor NDES

##### <a name="configure-the-certification-authority"></a>Configureert u de certificeringsinstantie

1. Meld u aan als ondernemingsbeheerder.

2. Gebruik op de verlenende CA de module Certificeringssjabloon om een nieuwe, aangepaste sjabloon te maken. U kunt ook een bestaande sjabloon (bijvoorbeeld de Gebruikerssjabloon) kopiëren en deze bijwerken voor gebruik met NDES.

   >[!NOTE]
   > De NDES-certificaatsjabloon moet zijn gebaseerd op een versie 2 certificaatsjabloon (met Windows 2003-compatibiliteit).

   De sjabloon moet de volgende configuraties hebben:

   - Voer een gebruiksvriendelijke **weergavenaam voor de sjabloon** in.

   - Selecteer **Leveren met het verzoek** in **Onderwerpnaam**. (Beveiliging wordt afgedwongen door de Intune-beleidsmodule voor NDES.)

   - Controleer in **Extensies** of de **beschrijving van toepassingsbeleid** de optie **Clientverificatie** bevat.

     > [!IMPORTANT]
     > Bewerk voor iOS- en macOS-certificaatsjablonen op het tabblad **Extensies** het **sleutelgebruik** en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

   - Selecteer in **Beveiliging** het NDES-serviceaccount en wijs hieraan de machtiging **Registreren** toe voor de sjabloon. Intune-beheerders die SCEP-profielen maken, vereisen **leesrechten** om naar de sjabloon te kunnen bladeren tijdens het maken van SCEP-profielen.

     > [!NOTE]
     > Voor het intrekken van certificaten moet het NDES-serviceaccount voor elke certificaatsjabloon dat door een certificaatprofiel wordt gebruikt, beschikken over rechten voor het *verlenen en beheren van certificaten*.

3. Controleer de **geldigheidsperiode** op het tabblad **Algemeen** van de sjabloon. Standaard gebruikt Intune de waarde die is geconfigureerd in de sjabloon. U kunt de CA echter zodanig configureren dat de aanvrager een andere waarde kan invoeren, die u vervolgens vanuit de Intune-beheerconsole kunt instellen. Als u altijd de waarde in de sjabloon wilt gebruiken, slaat u de rest van deze stap over.

   > [!IMPORTANT]
   > iOS en macOS gebruiken altijd de waarde die in de sjabloon is ingesteld, ongeacht andere configuraties die u instelt.

Voorbeeld van de sjabloonconfiguratie:

![Sjabloon, tabblad Afhandeling van aanvragen](./media/scep_ndes_request_handling.png)

![Sjabloon, tabblad Onderwerpnaam](./media/scep_ndes_subject_name.jpg)

![Sjabloon, tabblad Beveiliging](./media/scep_ndes_security.jpg)

![Sjabloon, tabblad Extensies](./media/scep_ndes_extensions.jpg)

![Sjabloon, tabblad Uitgiftevereisten](./media/scep_ndes_issuance_reqs.jpg)

> [!IMPORTANT]
> Voor Toepassingsbeleid voegt u alleen het benodigde toepassingsbeleid toe. Leg uw keuzes voor aan de beveiligingsbeheerder.

Configureer de CA zodanig dat de aanvrager de geldigheidsperiode kan invoeren:

1. Voer de volgende opdracht voor de CA uit:
   - **certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   - **net stop certsvc**
   - **net start certsvc**

2. Gebruik op de verlenende CA de module Certificeringsinstantie om de certificaatsjabloon te publiceren.
   Selecteer het knooppunt **Certificaatsjablonen**, klik op **Actie** > **Nieuw** > **Te verlenen certificaatsjablonen** en selecteer vervolgens de sjabloon die u in stap 2 hebt gemaakt.

3. Controleer in de map **Certificaatsjablonen** of de sjabloon is gepubliceerd.

#### <a name="step-3---configure-prerequisites-on-the-ndes-server"></a>Stap 3: vereisten configureren op de NDES-server
In deze taak:

- Voegt u NDES toe aan een Windows Server en configureert u IIS om NDES te ondersteunen
- Voegt u het NDES-serviceaccount toe aan de groep IIS_IUSR
- Stelt u de SPN voor het NDES-serviceaccount in

1. U meldt zich als **ondernemingsbeheerder** aan op de server die als host voor NDES fungeert en gebruikt vervolgens de [wizard Functies en onderdelen toevoegen](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) om NDES te installeren:

   1. Selecteer in de wizard **Active Directory Certificate Services** om toegang te krijgen tot de AD CS-functieservices. Selecteer de **inschrijvingsservice voor netwerkapparaten**, schakel **Certificeringsinstantie**uit en voer vervolgens de wizard uit.

      > [!TIP]
      > Schakel **Sluiten** in **installatievoortgang** niet in. Selecteer in plaats daarvan de koppeling **Active Directory Certificate Services op de doelserver configureren**. Hiermee opent u de wizard **AD CS-configuratie** die u voor de volgende taak gebruikt. Nadat AD CS-configuratie is geopend, kunt u de wizard Functies en onderdelen toevoegen sluiten.

   2. Wanneer NDES aan de server wordt toegevoegd, installeert de wizard ook IIS. Controleer of IIS de volgende configuraties heeft:

   3. **Webserver** > **Beveiliging** > **Aanvraagfiltering**

   4. **Webserver** > **Toepassingsontwikkeling** > **ASP.NET 3.5**. Als u ASP.NET 3.5 installeert, installeert u ook .NET Framework 3.5. Als u .NET Framework 3.5 installeert, installeert u zowel het kernonderdeel **.NET Framework 3.5** als **HTTP-activering**.

   5. **Webserver** > **Toepassingsontwikkeling** > **ASP.NET 4.5**. Als u ASP.NET 4.5 installeert, installeert u ook .NET Framework 4.5. Als u .NET Framework 4.5 installeert, installeer dan het kernonderdeel **.NET Framework 4.5**, **ASP.NET 4.5** en de functie **WCF-services** > **HTTP-activering**.

   6. **Beheerhulpprogramma's** > **Compatibiliteit met IIS 6-beheer** > **Compatibiliteit met IIS 6-metabase**

   7. **Beheerhulpprogramma's** > **Compatibiliteit met IIS 6-beheer** > **Compatibiliteit met IIS 6 WMI**

   8. Voeg op de server het NDES-serviceaccount toe als lid van de groep **IIS_IUSR**.

2. Voer de volgende opdracht uit via een opdrachtprompt met verhoogde bevoegdheid om de SPN van het NDES-serviceaccount in te stellen:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Bij bijvoorbeeld een NDES-server genaamd **Server01**, een domein genaamd **Contoso.com**en een serviceaccount genaamd **NDESService**gebruikt u:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Stap 4: NDES configureren voor gebruik met Intune
In deze taak:

- Configureert u NDES voor gebruik met de verlenende CA
- Verbindt u het (SSL-)serververificatiecertificaat in IIS
- Configureert u aanvraagfiltering in IIS

1. Open op de NDES-server de wizard AD CS-configuratie en voer de volgende wijzigingen door:

    > [!TIP]
    > Als u op de koppeling in de vorige taak hebt geklikt, is deze wizard al geopend. Anders opent u Serverbeheer voor toegang tot post-implementatieconfiguratie voor Active Directory Certificate Services.

   - Selecteer in **Functieservices** de optie **Registratieservice voor netwerkapparaten**
   - Voer in **Serviceaccount voor NDES** het NDES-serviceaccount in
   - Klik in **Certificeringsinstantie voor Registratieservice voor netwerkapparaten** op **Selecteren** en selecteer vervolgens de verlenende CA waar u de certificaatsjabloon hebt geconfigureerd
   - Stel in **Cryptografie voor NDES** de sleutellengte in om aan de vereisten van uw bedrijf te voldoen.
   - Selecteer in **Bevestiging** **Configureren** om de wizard te voltooien.

2. Nadat de wizard is voltooid, werkt u de volgende registersleutel bij op de NDES-server:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Voor het bijwerken van deze sleutel gaat u naar de certificaatsjabloon **Doel** (op het tabblad **Afhandeling van aanvragen**). Werk vervolgens de bijbehorende registervermelding bij door de bestaande gegevens te vervangen door de naam van de certificaatsjabloon (niet de weergavenaam van de sjabloon) die u hebt opgegeven in taak 1. In de volgende tabel wordt het certificaatsjabloondoel gekoppeld aan de waarden in het register:

    |Certificaatsjabloondoel (op het tabblad Afhandeling van aanvragen)|Te bewerken registerwaarde|Waarde die in de Intune-beheerconsole wordt weergegeven voor het SCEP-profiel|
    |---|---|---|
    |Handtekening|SignatureTemplate|Digitale handtekening|
    |Versleuteling|EncryptionTemplate|Sleutelcodering|
    |Handtekening en versleuteling|GeneralPurposeTemplate|Sleutelcodering<br/>Digitale handtekening|

    Als het doel van uw certificaatsjabloon bijvoorbeeld **Versleuteling**is, bewerkt u de waarde **EncryptionTemplate** zo dat deze de naam van uw certificaatsjabloon is.

3. De NDES-server ontvangt lange URL's (query's) waarvoor u twee registervermeldingen moet toevoegen:


   |                        Locatie                        |      Waarde      | Type  |      Gegevens       |
   |--------------------------------------------------------|-----------------|-------|-----------------|
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxFieldLength  | DWORD | 65534 (decimaal) |
   | HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters | MaxRequestBytes | DWORD | 65534 (decimaal) |


4. Selecteer in IIS-beheer **Standaardwebsite** > **Aanvraagfiltering** > **Functie-instelling bewerken**. Vervang de **maximale URL-lengte** en **maximale queryreeks** door *65534*, zoals weergegeven:

    ![Maximale lengte van de URL's en query's van IIS](./media/SCEP_IIS_max_URL.png)

5. Start de server opnieuw op. U kunt de wijzigingen niet voltooien door **iisreset** uit te voeren op de server.
6. Blader naar `http://*FQDN*/certsrv/mscep/mscep.dll`. Hier wordt een NDES-pagina weergegeven die vergelijkbaar is met de volgende:

    ![Test NDES](./media/SCEP_NDES_URL.png)

    Als het bericht **503 - Service niet beschikbaar** wordt weergegeven, controleert u de logboeken. De groep van toepassing is waarschijnlijk gestopt vanwege een ontbrekend recht voor de NDES-gebruiker. Deze rechten worden beschreven in Taak 1.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Certificaten op de NDES-server installeren en verbinden

1. Vraag op uw NDES-server een **serververificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat. Vervolgens verbindt u dit SSL-certificaat in IIS.

    > [!TIP]
    > Nadat u het SSL-certificaat in IIS hebt verbonden, installeert u een clientverificatiecertificaat. Dit certificaat kan worden verleend door elke CA die wordt vertrouwd door de NDES-server. Hoewel dit niet wordt aanbevolen, kunt u hetzelfde certificaat voor zowel server- als clientverificatie gebruiken zolang het certificaat beide EKU's (Enhance Key Usages) heeft. Bekijk de volgende stappen voor informatie over deze verificatiecertificaten.

   1. Nadat u het serververificatiecertificaat hebt ontvangen, opent u **IIS-beheer** en selecteert u de **standaardwebsite**. Selecteer **Bindingen** in het deelvenster **Acties**.

   2. Selecteer **Toevoegen**, stel **Type** in op **https** en controleer vervolgens of de poort **443** is. Als Intune zelfstandig wordt gebruikt, wordt alleen poort 443 ondersteund.

   3. Voer voor het **SSL-certificaat** het serververificatiecertificaat in.

      > [!NOTE]
      > Als de NDES-server een externe en interne naam voor één netwerkadres gebruikt, moet het serververificatiecertificaat het volgende bevatten:
      > - Een **onderwerpnaam** met een externe openbare servernaam
      > - Een **alternatieve onderwerpnaam** die de naam van de interne server bevat

2. Vraag op uw NDES-server een **clientverificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat. Dit kan hetzelfde certificaat zijn als het serververificatiecertificaat als dat certificaat beide mogelijkheden heeft.

    Het clientverificatiecertificaat moet de volgende eigenschappen hebben:

    - **Uitgebreid sleutelgebruik**: deze waarde moet **Clientverificatie** omvatten

    - **Onderwerpnaam**: deze waarde moet gelijk zijn aan de DNS-naam van de server waarop u het certificaat installeert (de NDES-server)

##### <a name="configure-iis-request-filtering"></a>IIS-aanvraagfiltering configureren

1. Open op de NDES-server **IIS-beheer**, selecteer de **standaardwebsite** in het deelvenster **Verbindingen** en open vervolgens **Aanvraagfiltering**.

2. Selecteer **Functie-instellingen bewerken** en stel de waarden in:

    - **querytekenreeks (bytes)** = **65534**
    - **Maximale URL-lengte (bytes)** = **65534**

3. Controleer de volgende registersleutel:

    `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

    Zorg ervoor dat de volgende waarden zijn ingesteld als DWORD-gegevens:

    - Naam: **MaxFieldLength**, met een decimale waarde van **65534**
    - Naam: **MaxRequestBytes**, met een decimale waarde van **65534**

4. Start de NDES-server opnieuw op. De server is nu klaar om de certificaatconnector te ondersteunen.

#### <a name="step-5---enable-install-and-configure-the-intune-certificate-connector"></a>Stap 5: de Intune-certificaatconnector inschakelen, installeren en configureren
In deze taak:

- Schakelt u de ondersteuning voor NDES in Intune in.
- Download, installeer en configureer de certificaatconnector op de server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd/server in uw omgeving. Als u de schaal van de NDES-implementatie in uw organisatie wilt vergroten, kunt u op elke NDES-server meerdere NDES-servers met een certificaatconnector van Microsoft Intune installeren.

##### <a name="download-install-and-configure-the-certificate-connector"></a>De certificaatconnector downloaden, installeren en configureren
![ConnectorDownload](./media/certificates-download-connector.png)

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** en vervolgens **Certificeringsinstantie**.
4. Selecteer **Toevoegen** en **Connectorbestand downloaden**. Sla het bestand op in een locatie waar u het kunt openen vanaf de server waarop u de connector gaat installeren.
5. Nadat het downloaden is voltooid, voert u het gedownloade installatieprogramma (**ndesconnectorssetup.exe**) uit op server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd. Het installatieprogramma installeert ook de beleidsmodule voor NDES en de CRP-webservice. (De CRP-webservice, CertificateRegistrationSvc, wordt als een toepassing in IIS uitgevoerd.)

    > [!NOTE]
    > Wanneer u NDES installeert en Intune zelfstandig wordt gebruikt, wordt de CRP-service automatisch met de certificaatconnector geïnstalleerd. Wanneer u Intune met Configuration Manager gebruikt, installeert u het certificaatregistratiepunt als een afzonderlijke sitesysteemfunctie.

6. Als naar het clientcertificaat voor de certificaatconnector wordt gevraagd, kiest u **Selecteren**en selecteert u het certificaat voor **clientverificatie** dat u in Taak 3 op uw NDES-server hebt geïnstalleerd.

    Nadat u het certificaat voor clientverificatie hebt geselecteerd, keert u terug naar het oppervlak **Clientcertificaat voor Microsoft Intune-certificaatconnector** . Hoewel het geselecteerde certificaat niet wordt weergegeven, selecteert u **Volgende** om de eigenschappen van dat certificaat weer te geven. Selecteer **Volgende** en vervolgens **Installeren**.
    
    > [!IMPORTANT]
    > De Intune Certificate Connector kan niet worden geregistreerd op een apparaat waarop Verbeterde beveiliging van Internet Explorer is ingeschakeld. [Schakel Verbeterde beveiliging van Internet Explorer uit](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) als u de Intune Certificate Connector wilt gebruiken.

7. Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

    > [!TIP]
    > Als u de wizard sluit voordat u de gebruikersinterface van de certificaatconnector start, kunt u deze opnieuw openen door de volgende opdracht uit te voeren:
    >
    > <installatiepad>\NDESConnectorUI\NDESConnectorUI.exe

8. In de gebruikersinterface van de **certificaatconnector** :

    Selecteer **Aanmelden** en voer uw Intune-servicebeheerder- of tenantbeheerderreferenties met de machtiging voor algemeen beheer in.

    > [!IMPORTANT]
    > Aan het gebruikersaccount moet een geldige Intune-licentie worden toegewezen. Als het gebruikersaccount geen geldige Intune-licentie heeft, mislukt NDESConnectorUI.exe.

    Als uw organisatie een proxyserver gebruikt en de NDES-server de proxy nodig heeft om toegang tot internet te krijgen, selecteert u **Proxyserver gebruiken** en voert u de naam van de proxyserver, de poort en de accountreferenties in om verbinding te maken.

    Selecteer het tabblad **Geavanceerd** en voer vervolgens referenties in voor een account met de machtiging **Certificaten verlenen en beheren** op uw verlenende certificeringsinstantie. **Pas** de wijzigingen toe.

    U kunt nu de gebruikersinterface van de certificaatconnector sluiten.

9. Open een opdrachtprompt, voer **services.msc** in en druk vervolgens op **Enter**. Klik met de rechtermuisknop op de **Intune-connectorservice** en kies **Opnieuw opstarten**.

Controleer of de service wordt uitgevoerd door een browser te openen en de volgende URL in te voeren. Hierop moet een **403**-fout worden geretourneerd:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

## <a name="create-a-scep-certificate-profile"></a>Een SCEP-certificaatprofiel maken

1. Open Microsoft Intune in Azure Portal.
2. Selecteer **Apparaatconfiguratie**, selecteer **Profielen** en selecteer vervolgens **Profiel maken**.
3. Voer een **naam** en een **beschrijving** in voor het SCEP-certificaatprofiel.
4. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit SCEP-certificaat. Op dit moment kunt u een van de volgende platforms selecteren voor apparaatbeperkingsinstellingen:
   - **Android**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 en hoger**
   - **Windows 10 en hoger**
5. Selecteer in de vervolgkeuzelijst **Profieltype** de optie **SCEP-certificaat**.
6. Configureer in het deelvenster **SCEP-certificaat** de volgende instellingen:

   - **Geldigheidsduur van certificaat**: als u de opdracht `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE` hebt uitgevoerd op de verlenende CA waarop een aangepaste geldigheidsperiode mogelijk is, kunt u opgeven hoelang het certificaat geldig blijft.<br>U kunt een waarde invoeren die lager is dan de geldigheidsperiode in de certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in de certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA. 
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
     - **Aangepast**: als u deze optie selecteert, wordt een ander veld van de vervolgkeuzelijst weergegeven. Met dit veld kunt u een indeling van de aangepaste onderwerpnaam invoeren. De aangepaste indeling ondersteunt twee variabelen: **Algemene naam (CN)** en **E-mail (E)**. **Algemene naam (CN)** kan worden ingesteld op een van de volgende variabelen:
       - **CN = {{UserName}}**: de Principle-naam van de gebruiker, zoals janedoe@contoso.com
       - **CN = {{AAD_Device_ID}}**: een id die wordt toegewezen wanneer u een apparaat in Azure Active Directory (AD) registreert. Deze id wordt doorgaans gebruikt voor verificatie met Azure AD.
       - **CN={{SERIALNUMBER}}**: het unieke serienummer dat doorgaans wordt gebruikt door de fabrikant om een apparaat te identificeren
       - **CN = {{IMEINumber}}**: het unieke nummer van de International Mobile Equipment Identity (IMEI) dat wordt gebruikt om een mobiele telefoon te identificeren
       - **CN = {{OnPrem_Distinguished_Name}}**: een reeks relatieve DN-namen die door komma's worden gescheiden, bijvoorbeeld `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

          Als u de variabele `{{OnPrem_Distinguished_Name}}` wilt gebruiken, moet u het gebruikerskenmerk `onpremisesdistingishedname` met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD.

       - **CN={{onPremisesSamAccountName}}**: beheerders kunnen het kenmerk samAccountName van Active Directory synchroniseren naar Azure AD via Azure AD Connect in een kenmerk genaamd `onPremisesSamAccountName`. Deze variabele kan in Intune worden vervangen als onderdeel van een aanvraag voor certificaatuitgifte in het onderwerp van een SCEP-certificaat.  Het kenmerk samAccountName is de aanmeldingsnaam van de gebruiker die wordt gebruikt ter ondersteuning van clients en servers uit een vorige versie van Windows (pre-Windows 2000). De indeling van de gebruikersaanmeldingsnaam is: `DomainName\testUser` of alleen `testUser`.

          Als u de variabele `{{onPremisesSamAccountName}}` wilt gebruiken, moet u het gebruikerskenmerk `onPremisesSamAccountName` met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD.

       Door een combinatie van deze twee variabelen met statische tekenreeksen te gebruiken, kunt u een aangepaste indeling voor de naam van een certificaathouder maken, bijvoorbeeld: **CN = {{UserName}}, E = {{EmailAddress}}, OU = Mobile, O groep Finance, L = Redmond, ST = Washington, C = = US**. <br/> In dit voorbeeld hebt u een indeling voor de naam van een certificaathouder gemaakt, waarin naast de variabelen voor CN en E gebruik wordt gemaakt van tekenreeksen voor de waarden Organisatie-eenheid, Organisatie, Locatie, Regio en Land. [De functie CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) beschrijft deze functie en de ondersteunde tekenreeksen.

- **Alternatieve onderwerpnaam**: voer in hoe de waarden voor de alternatieve naam van het onderwerp (SAN) in de certificaataanvraag automatisch worden gemaakt met Intune. Als u bijvoorbeeld een gebruikerscertificaattype selecteert, kunt u de User Principal Name (UPN) gebruiken in de alternatieve naam van het onderwerp. Als het clientcertificaat wordt gebruikt om een Network Policy Server te verifiëren, dient u de alternatieve naam van het onderwerp op de UPN in te stellen.
- **Sleutelgebruik**: voer opties voor sleutelgebruik voor het certificaat in. Uw opties zijn:
  - **Sleutelcodering**: sta alleen sleuteluitwisseling toe als de sleutel is gecodeerd
  - **Digitale handtekening**: sta alleen sleuteluitwisseling toe als een digitale handtekening de sleutel helpt beveiligen
- **Sleutelgrootte (bits)**: selecteer het aantal bits in de sleutel
- **Hash-algoritme** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): selecteer een van de beschikbare typen hash-algoritme om met dit certificaat te gebruiken. Selecteer het sterkste beveiligingsniveau dat door de verbindende apparaten wordt ondersteund.
- **Basiscertificaat**: kies een basis-CA-certificaatprofiel dat u eerder hebt geconfigureerd en aan de gebruiker of het apparaat hebt toegewezen. Dit CA-certificaat moet het basiscertificaat zijn voor de CA die het certificaat verleent dat u in dit certificaatprofiel gaat configureren.
- **Uitgebreide-sleutelgebruik**: waarden **Toevoegen** voor het beoogde gebruik van het certificaat. In de meeste gevallen vereist het certificaat **Clientverificatie** zodat de gebruiker of het apparaat bij een server kan worden geverifieerd. U kunt echter zo nodig andere sleutelgebruiken toevoegen.
- **Registratie-instellingen**
  - **Drempelwaarde voor verlenging (%)**: voer het percentage van de levensduur van het certificaat in dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
  - **URL's van SCEP-server**: voer een of meer URL's in voor de NDES-servers die certificaten via SCEP verlenen.
  - Selecteer **OK** en **maak** uw profiel.

Het profiel wordt gemaakt en wordt weergegeven in het deelvenster met de profielenlijst.

## <a name="assign-the-certificate-profile"></a>Het certificaatprofiel toewijzen

Overweeg het volgende voordat u certificaatprofielen aan groepen toewijst:

- Wanneer u certificaatprofielen aan groepen toewijst, wordt het certificaatbestand van het vertrouwde CA-certificaatprofiel op het apparaat geïnstalleerd. Het apparaat gebruikt het SCEP-certificaatprofiel om een certificaataanvraag te maken.
- Certificaatprofielen worden alleen geïnstalleerd op apparaten met het platform dat u gebruikt wanneer u het profiel maakt.
- U kunt certificaatprofielen toewijzen aan gebruikersverzamelingen of apparaatverzamelingen.
- Als u een certificaat snel naar een apparaat wilt publiceren nadat het apparaat is geregistreerd, wijst u het certificaatprofiel toe aan een gebruikersgroep en niet aan een apparaatgroep. Als u het toewijst aan een apparaatgroep, is een volledige apparaatregistratie vereist voordat het apparaat beleid kan ontvangen.
- Hoewel u elk profiel afzonderlijk toewijst, moet u ook het vertrouwde basis-CA- en het SCEP- of PKCS-profiel toewijzen. Anders mislukt het SCEP- of PKCS-certificaatbeleid.

    > [!NOTE]
    > In iOS worden als het goed is meerdere exemplaren van het certificaat weergegeven in het beheerprofiel als u meerdere resourceprofielen hebt geïmplementeerd die hetzelfde certificaatprofiel gebruiken.
    
Zie [Apparaatprofielen toewijzen](device-profile-assign.md) voor informatie over het toewijzen van apparaatprofielen.

## <a name="intune-connector-events-and-diagnostic-codes"></a>Gebeurtenissen en diagnostische codes van de Intune-connector

Vanaf versie 6.1803.x.x legt de Intune-connectorservice gebeurtenissen vast in de **Logboeken** (**Logboeken voor toepassingen en services** > **Microsoft Intune-connector**). Gebruik deze gebeurtenissen om potentiële problemen in de configuratie van de Intune-connector op te lossen. Deze gebeurtenissen leggen de successen en mislukkingen van een bewerking vast, en bevatten ook diagnostische codes met berichten zodat de IT-beheerder problemen kan oplossen.

### <a name="event-ids-and-descriptions"></a>Gebeurtenis-id's en beschrijvingen

> [!NOTE]
> Voor informatie over de verwante diagnostische codes voor elke gebeurtenis gebruikt u de tabel **Diagnostische codes** (in dit artikel).

| Gebeurtenis-id      | Gebeurtenisnaam    | Gebeurtenisbeschrijving | Verwante diagnostische codes |
| ------------- | ------------- | -------------     | -------------            |
| 10010 | StartedConnectorService  | Connectorservice gestart | 0x00000000, 0x0FFFFFFF |
| 10020 | StoppedConnectorService  | Connectorservice gestopt | 0x00000000, 0x0FFFFFFF |
| 10100 | CertificateRenewal_Success  | Connector-inschrijvingscertificaat vernieuwd | 0x00000000, 0x0FFFFFFF |
| 10102 | CertificateRenewal_Failure  | Connector-inschrijvingscertificaat niet vernieuwd. Installeer de connector opnieuw. | 0x00000000, 0x00000405, 0x0FFFFFFF |
| 10302 | RetrieveCertificate_Error  | Ophalen van het connector-inschrijvingscertificaat uit het register is mislukt. Bekijk de gebeurtenisdetails voor de vingerafdruk van het certificaat die betrekking heeft op deze gebeurtenis. | 0x00000000, 0x00000404, 0x0FFFFFFF |
| 10301 | RetrieveCertificate_Warning  | Controleer de diagnostische gegevens in de details van gebeurtenis. | 0x00000000, 0x00000403, 0x0FFFFFFF |
| 20100 | PkcsCertIssue_Success  | Een PKCS-certificaat is uitgegeven. Bekijk de gebeurtenisdetails voor de apparaat-id, de gebruikers-id, CA-naam, certificaatsjabloonnaam en certificaatvingerafdruk die betrekking hebben op deze gebeurtenis. | 0x00000000, 0x0FFFFFFF |
| 20102 | PkcsCertIssue_Failure  | Uitgifte van een PKCS-certificaat is mislukt. Bekijk de gebeurtenisdetails voor de apparaat-id, gebruikers-id, CA-naam, certificaatsjabloonnaam en certificaatvingerafdruk die betrekking hebben op deze gebeurtenis. | 0x00000000, 0x00000400, 0x00000401, 0x0FFFFFFF |
| 20200 | RevokeCert_Success  | Het certificaat is ingetrokken. Bekijk de gebeurtenisdetails voor de apparaat-id, gebruikers-id, CA-naam en certificaatserienummer die betrekking hebben op deze gebeurtenis. | 0x00000000, 0x0FFFFFFF |
| 20202 | RevokeCert_Failure | Kan het certificaat niet verwijderen. Bekijk de gebeurtenisdetails voor de apparaat-id, gebruikers-id, CA-naam en certificaatserienummer die betrekking hebben op deze gebeurtenis. Zie de NDES SVC-logboeken voor meer informatie.   | 0x00000000, 0x00000402, 0x0FFFFFFF |
| 20300 | Download_Success | Aanvraag om een certificaat te ondertekenen, een clientcertificaat te downloaden of een certificaat in te trekken, is gedownload. Bekijk de gebeurtenisdetails voor de downloaddetails.  | 0x00000000, 0x0FFFFFFF |
| 20302 | Download_Failure | Aanvraag om een certificaat te ondertekenen, een clientcertificaat te downloaden of een certificaat in te trekken, is niet gedownload. Bekijk de gebeurtenisdetails voor de downloaddetails. | 0x00000000, 0x0FFFFFFF |
| 20400 | Upload_Success | De aanvraag- of intrekkingsgegevens van het certificaat zijn geüpload. Bekijk de gebeurtenisdetails voor de uploaddetails. | 0x00000000, 0x0FFFFFFF |
| 20402 | Upload_Failure | De aanvraag- of intrekkingsgegevens van het certificaat zijn niet geüpload. Bekijk de gebeurtenisdetails > Uploadstatus om de fout te bepalen.| 0x00000000, 0x0FFFFFFF |
| 20500 | CRPVerifyMetric_Success  | Certificaatregistratiepunt heeft een clientverificatievraag geverifieerd | 0x00000000, 0x0FFFFFFF |
| 20501 | CRPVerifyMetric_Warning  | Certificaatregistratiepunt heeft de aanvraag voltooid maar geweigerd. Zie de diagnostische code en het bericht voor meer informatie. | 0x00000000, 0x00000411, 0x0FFFFFFF |
| 20502 | CRPVerifyMetric_Failure  | Certificaatregistratiepunt heeft een clientverificatievraag niet geverifieerd. Zie de diagnostische code en het bericht voor meer informatie. Zie de details van het gebeurtenisbericht voor de apparaat-id die overeenkomt met de verificatievraag. | 0x00000000, 0x00000408, 0x00000409, 0x00000410, 0x0FFFFFFF |
| 20600 | CRPNotifyMetric_Success  | Certificaatregistratiepunt heeft de procesmelding voltooid en heeft het certificaat verzonden naar het clientapparaat. | 0x00000000, 0x0FFFFFFF |
| 20602 | CRPNotifyMetric_Failure  | Certificaatregistratiepunt heeft de procesmelding niet voltooid. Zie de details van het gebeurtenisbericht voor meer informatie over de aanvraag. Controleer de verbinding tussen de NDES-server en de CA. | 0x00000000, 0x0FFFFFFF |

### <a name="diagnostic-codes"></a>Diagnostische codes

| Diagnostische code | Naam diagnostische test | Diagnostisch bericht |
| -------------   | -------------   | -------------      |
| 0x00000000 | Geslaagd  | Geslaagd |
| 0x00000400 | PKCS_Issue_CA_Unavailable  | Certificeringsinstantie is niet geldig of is niet bereikbaar. Controleer of de certificeringsinstantie beschikbaar is en of uw server ermee kan communiceren. |
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Client-Auth Symantec-certificaat is niet gevonden in het lokale certificaatarchief. Zie het artikel [Het Symantec-certificaat voor registratie-autorisatie installeren](https://docs.microsoft.com/en-us/intune/certificates-symantec-configure#install-the-symantec-registration-authorization-certificate) voor meer informatie.  |
| 0x00000402 | RevokeCert_AccessDenied  | Het opgegeven account heeft geen machtigingen om een certificaat van CA in te trekken. Zie het veld CA-naam in de berichtdetails van de gebeurtenis om de verlenende CA te bepalen.  |
| 0x00000403 | CertThumbprint_NotFound  | Kan geen certificaat vinden dat overeenkomt met uw invoer. Registreer de certificaatconnector en probeer het opnieuw. |
| 0x00000404 | Certificate_NotFound  | Kan geen certificaat vinden dat overeenkomt met de opgegeven invoer. Registreer de certificaatconnector nogmaals en probeer het opnieuw. |
| 0x00000405 | Certificate_Expired  | Een certificaat is verlopen. Registreer de certificaatconnector nogmaals om het certificaat te vernieuwen en probeer het opnieuw. |
| 0x00000408 | CRPSCEPCert_NotFound  | CRP-versleutelingscertificaat kan niet worden gevonden. Controleer of NDES en de Intune-connector correct zijn ingesteld. |
| 0x00000409 | CRPSCEPSigningCert_NotFound  | Handtekeningcertificaat kan niet worden opgehaald. Controleer of de Intune-connectorservice correct is geconfigureerd en of de Intune-connectorservice wordt uitgevoerd. Controleer ook of de downloadgebeurtenissen voor het certificaat zijn gelukt. |
| 0x00000410 | CRPSCEPDeserialize_Failed  | Het deserialiseren van de SCEP-verificatie-aanvraag is mislukt. Controleer of NDES en de Intune-connector correct zijn ingesteld. |
| 0x00000411 | CRPSCEPChallenge_Expired  | De aanvraag is geweigerd vanwege een verlopen certificaatverificatievraag. Het clientapparaat kan het opnieuw proberen nadat een nieuwe verificatievraag van de beheerserver is verkregen. |
| 0x0FFFFFFFF | Unknown_Error  | Uw aanvraag kan niet worden voltooid omdat aan serverzijde een fout is opgetreden. Probeer het opnieuw. |

## <a name="next-steps"></a>Volgende stappen
[Gebruik PKCS-certificaten](certficates-pfx-configure.md) of [geef PKCS-certificaten uit van een webservice van Symantec PKI-manager](certificates-symantec-configure.md).
