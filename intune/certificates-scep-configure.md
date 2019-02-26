---
title: SCEP-certificaten gebruiken met Microsoft Intune - Azure | Microsoft Docs
description: Als u SCEP-certificaten in Microsoft Intune wilt gebruiken, configureert u uw on-premises AD-domein, maakt u een certificeringsinstantie, stelt u de NDES-server in en installeert u de Intune-certificaatconnector. Vervolgens maakt u een SCEP-certificaatprofiel en wijst u dit profiel toe aan groepen. Zie ook de andere gebeurtenis-id's en de bijbehorende beschrijvingen, en de diagnostische codes voor de Intune-connectorservice.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cdc0f02aa09edd05314d0d4a6a2abacc98c94bf2
ms.sourcegitcommit: e5f501b396cb8743a8a9dea33381a16caadc51a9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/23/2019
ms.locfileid: "56742734"
---
# <a name="configure-and-use-scep-certificates-with-intune"></a>SCEP-certificaten configureren en gebruiken met Intune

In dit artikel leest u hoe u uw infrastructuur kunt configureren en vervolgens SCEP-certificaatprofielen (Simple Certificate Enrollment Protocol) kunt maken en toewijzen met Intune.

## <a name="configure-on-premises-infrastructure"></a>Lokale infrastructuur configureren

- **Active Directory-domein**: Alle servers die in dit gedeelte worden genoemd (met uitzondering van de webtoepassingsproxyserver), moeten lid zijn van uw Active Directory-domein.

- **Certificeringsinstantie** (CA): Moet een Microsoft-certificeringsinstantie (CA) voor ondernemingen zijn die wordt uitgevoerd in een Enterprise-editie van Windows Server 2008 R2 of hoger. Een zelfstandige CA wordt niet ondersteund. Zie [De certificeringsinstantie installeren](http://technet.microsoft.com/library/jj125375.aspx) voor meer informatie.
    Als de certificeringsinstantie werkt met Windows Server 2008 R2, moet u [de hotfix uit KB2483564 installeren](http://support.microsoft.com/kb/2483564/).

- **NDES-server**: Op een apparaat met Windows Server 2012 R2 of hoger moet u de serverrol Registratieservice voor netwerkapparaten (NDES) instellen. Intune biedt geen ondersteuning voor het gebruik van NDES op een server waarop ook de CA voor ondernemingen wordt uitgevoerd. Zie [Richtlijnen voor Registratieservice voor netwerkapparaten](http://technet.microsoft.com/library/hh831498.aspx) voor instructies over hoe u Windows Server 2012 R2 configureert om als host voor NDES te dienen.
De NDES-server moet met een domein in hetzelfde forest als de Enterprise-CA worden gekoppeld. Meer informatie over het implementeren van de NDES-server in een afzonderlijke forest, een geïsoleerd netwerk of een intern domein vindt u in [Een beleidsmodule gebruiken met de registratieservice voor netwerkapparaten](https://technet.microsoft.com/library/dn473016.aspx).

- **Microsoft Intune Certificate Connector**: Download het installatieprogramma voor de **Certificaatconnector** (**NDESConnectorSetup.exe**) via de Intune-beheerportal. Voer dit installatieprogramma uit op de server met de NDES-rol.  

  - De NDES-certificaatconnector ondersteunt ook de Federal Information Processing Standard-modus (FIPS). FIPS is niet vereist, maar wanneer deze modus is ingeschakeld, kunt u certificaten uitgeven en intrekken.

- **Webtoepassingsproxyserver** (optioneel): Gebruik een server die Windows Server 2012 R2 of hoger uitvoert als een webtoepassingsproxyserver (WAP-server). Deze configuratie:
  - Maakt het mogelijk dat apparaten certificaten ontvangen met een internetverbinding.
  - Is een beveiligingsaanbeveling wanneer apparaten via internet verbinding maken om certificaten te ontvangen en te verlengen.
  
- **Azure AD-toepassingsproxy** (optioneel): U kunt de Azure AD-toepassingsproxy gebruiken in plaats van een toegewezen webtoepassingsproxyserver (WAP-server) om de NDES-server op internet te publiceren. Zie voor meer informatie [Beveiligde externe toegang verschaffen voor on-premises toepassingen](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

#### <a name="additional"></a>Aanvullende informatie

- De server die als host voor WAP fungeert, [moet een update installeren](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) waarmee ondersteuning wordt geboden voor de lange URL's die worden gebruikt door de Network Device Enrollment Service. Deze update is opgenomen in het [updatepakket van december 2014](http://support.microsoft.com/kb/3013769)en is afzonderlijk verkrijgbaar in [KB3011135](http://support.microsoft.com/kb/3011135).
- De WAP-server moet een SSL-certificaat hebben dat overeenkomt met de naam zoals die voor externe clients wordt gepubliceerd en het SSL-certificaat vertrouwen dat op de NDES-server wordt gebruikt. De WAP-server kan met deze certificaten de SSL-verbinding van clients beëindigen en een nieuwe SSL-verbinding naar de NDES-server maken.

Zie [Certificaten voor WAP plannen](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) en [algemene informatie over WAP-servers](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)) voor meer informatie.

### <a name="network-requirements"></a>Netwerkvereisten

Als u geen omgekeerde proxy zoals WAP of Azure AD App Proxy gebruikt, moet u TCP-verkeer op poort 443 van alle hosts/IP-adressen op internet naar de NDES-server toestaan.

Sta alle poorten en protocollen toe die nodig zijn tussen de NDES-server en ondersteunende infrastructuur. De NDES-server moet bijvoorbeeld communiceren met de CA, DNS-servers, Configuration Manager-servers, domeincontrollers en mogelijk andere services in uw omgeving.

Het is zeer raadzaam de NDES-server te publiceren via een omgekeerde proxy, zoals de [Azure AD-toepassingsproxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx) of een proxy van een derde partij.

### <a name="certificates-and-templates"></a>Certificaten en sjablonen  

|Object|Details|
|----------|-----------|
|**Certificaatsjabloon**|Configureer deze sjabloon op uw verlenende CA.|
|**Clientverificatiecertificaat**|Dit certificaat wordt aangevraagd bij uw verlenende CA of openbare CA. U installeert dit op de NDES-server.|
|**Serververificatiecertificaat**|Dit SSL-certificaat wordt aangevraagd bij uw verlenende CA of openbare CA. U installeert en verbindt dit in IIS op de NDES-server. Als voor het certificaat het gebruik van client- en serververificatiesleutels is ingesteld (**Uitgebreid sleutelgebruik**), kunt u hetzelfde certificaat gebruiken.|
|**Vertrouwd basis-CA-certificaat**|U kunt het certificaat exporteren als een **.cer**-bestand van de basis-CA of van een apparaat dat de basis-CA vertrouwt. Vervolgens kunt u het toewijzen aan gebruikers, apparaten of beide met het profiel voor vertrouwde CA-certificaten.<br /><b>Opmerking:<b />wanneer een SCEP-certificaatprofiel wordt toegewezen, moet u het profiel voor vertrouwde basis-CA-certificaten waarnaar wordt verwezen in uw SCEP-certificaatprofiel, aan dezelfde gebruiker of apparaatgroep toewijzen.<br /><br />U gebruikt één vertrouwd basis-CA-certificaat per besturingssysteemplatform en koppelt het aan elk vertrouwd basiscertificaatprofiel dat u maakt.<br /><br />U kunt extra vertrouwde basis-CA-certificaten gebruiken als dat nodig is. U kunt dit bijvoorbeeld doen om een vertrouwensrelatie met een CA te leveren die de serververificatiecertificaten voor uw Wi-Fi-toegangspunten ondertekent.|

### <a name="accounts"></a>Accounts

|Naam|Details|
|--------|-----------|
|**NDES-serviceaccount**|Voer een domeingebruikersaccount in dat u als NDES-serviceaccount gaat gebruiken. |

## <a name="configure-your-infrastructure"></a>Uw infrastructuur configureren
Voordat u certificaatprofielen kunt configureren, moet u de volgende stappen uitvoeren. Voor deze stappen is kennis nodig van Windows Server 2012 R2 of hoger en Active Directory Certificate Services (ADCS):

#### <a name="step-1---create-an-ndes-service-account"></a>Stap 1: een NDES-serviceaccount maken

Maak een domeingebruikersaccount dat u als NDES-serviceaccount gaat gebruiken. U voert dit account in wanneer u sjablonen op de verlenende CA configureert voordat u NDES installeert en configureert. Zorg ervoor dat de gebruiker over de standaardrechten **Lokaal aanmelden**, **Aanmelden als service** en **Aanmelden als batchtaak** beschikt. Sommige organisaties voeren een beveiligingsbeleid dat ervoor zorgt dat deze rechten worden uitgeschakeld.

#### <a name="step-2---configure-certificate-templates-on-the-certification-authority"></a>Stap 2: certificaatsjablonen configureren op de certificeringsinstantie
Bij deze stap doet u het volgende:

- Configureert u een certificaatsjabloon voor NDES
- Publiceert u de certificaatsjabloon voor NDES

##### <a name="configure-the-certification-authority"></a>Configureert u de certificeringsinstantie

1. Meld u aan als ondernemingsbeheerder.

2. Gebruik op de verlenende CA de module Certificeringssjabloon om een nieuwe, aangepaste sjabloon te maken. U kunt ook een bestaande sjabloon (bijvoorbeeld de Gebruikerssjabloon) kopiëren en deze bijwerken voor gebruik met NDES.

   >[!NOTE]
   > De NDES-certificaatsjabloon moet zijn gebaseerd op een versie 2 certificaatsjabloon (met Windows 2003-compatibiliteit).

   De sjabloon moet de volgende configuraties hebben:

   - Onder **Algemeen**:
   
       - Controleer of het selectievakje **Certificaat in Active Directory publiceren** **niet** is ingeschakeld.
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
Bij deze stap doet u het volgende:

- Voegt u NDES toe aan een Windows Server en configureert u IIS om NDES te ondersteunen
- Voegt u het NDES-serviceaccount toe aan de groep IIS_IUSR
- De Service Principal Name (SPN) instellen voor het NDES-serviceaccount

1. U meldt zich als **ondernemingsbeheerder** aan op de server die als host voor NDES fungeert en gebruikt vervolgens de [wizard Functies en onderdelen toevoegen](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) om NDES te installeren:

   1. Selecteer in de wizard **Active Directory Certificate Services** om toegang te krijgen tot de AD CS-functieservices. Selecteer de **inschrijvingsservice voor netwerkapparaten**, schakel **Certificeringsinstantie**uit en voer vervolgens de wizard uit.

      > [!TIP]
      > Schakel **Sluiten** niet in tijdens de **installatievoortgang**. Selecteer in plaats daarvan de koppeling **Active Directory Certificate Services op de doelserver configureren**. Hiermee opent u de wizard **AD CS-configuratie** die u voor de volgende stap gebruikt. Nadat AD CS-configuratie is geopend, kunt u de wizard Functies en onderdelen toevoegen sluiten.

   2. Wanneer NDES aan de server wordt toegevoegd, installeert de wizard ook IIS. Controleer of IIS de volgende configuraties heeft:

       - **Webserver** > **Beveiliging** > **Aanvraagfiltering**

       - **Webserver** > **Toepassingsontwikkeling** > **ASP.NET 3.5** 

            Als u ASP.NET 3.5 installeert, installeert u ook .NET Framework 3.5. Als u .NET Framework 3.5 installeert, installeert u zowel het kernonderdeel **.NET Framework 3.5** als **HTTP-activering**.

       - **Webserver** > **Toepassingsontwikkeling** > **ASP.NET 4.5** 

            Als u ASP.NET 4.5 installeert, installeert u ook .NET Framework 4.5. Als u .NET Framework 4.5 installeert, installeer dan het kernonderdeel **.NET Framework 4.5**, **ASP.NET 4.5** en de functie **WCF-services** > **HTTP-activering**.

       - **Beheerhulpprogramma's** > **Compatibiliteit met IIS 6-beheer** > **Compatibiliteit met IIS 6-metabase**

       - **Beheerhulpprogramma's** > **Compatibiliteit met IIS 6-beheer** > **Compatibiliteit met IIS 6 WMI**

       - Voeg op de server het NDES-serviceaccount toe als lid van de lokale groep **IIS_IUSR**.

2. Voer de volgende opdracht uit via een opdrachtprompt met verhoogde bevoegdheid om de SPN van het NDES-serviceaccount in te stellen:

    `setspn -s http/<DNS name of NDES Server> <Domain name>\<NDES Service account name>`

    Bij bijvoorbeeld een NDES-server genaamd **Server01**, een domein genaamd **Contoso.com**en een serviceaccount genaamd **NDESService**gebruikt u:

    `setspn –s http/Server01.contoso.com contoso\NDESService`

#### <a name="step-4---configure-ndes-for-use-with-intune"></a>Stap 4: NDES configureren voor gebruik met Intune
Bij deze stap doet u het volgende:

- Configureert u NDES voor gebruik met de verlenende CA
- Verbindt u het (SSL-)serververificatiecertificaat in IIS
- Configureert u aanvraagfiltering in IIS

1. Open op de NDES-server de wizard AD CS-configuratie en voer de volgende wijzigingen door:

    > [!TIP]
    > Als u op de koppeling in de vorige stap hebt geklikt, is deze wizard al geopend. Anders opent u Serverbeheer voor toegang tot post-implementatieconfiguratie voor Active Directory Certificate Services.

   - Selecteer in **Functieservices** de optie **Registratieservice voor netwerkapparaten**
   - Voer in **Serviceaccount voor NDES** het NDES-serviceaccount in
   - Klik in **Certificeringsinstantie voor Registratieservice voor netwerkapparaten** op **Selecteren** en selecteer vervolgens de verlenende CA waar u de certificaatsjabloon hebt geconfigureerd
   - Stel in **Cryptografie voor NDES** de sleutellengte in om aan de vereisten van uw bedrijf te voldoen.
   - Selecteer in **Bevestiging** **Configureren** om de wizard te voltooien.

2. Nadat de wizard is voltooid, werkt u de volgende registersleutel bij op de NDES-server:

    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

    Voor het bijwerken van deze sleutel gaat u naar de certificaatsjabloon **Doel** (op het tabblad **Afhandeling van aanvragen**). Werk vervolgens de bijbehorende registervermelding bij. Vervang hiervoor de bestaande gegevens door de naam van de certificaatsjabloon (niet de weergavenaam van de sjabloon) die u hebt opgegeven in stap 2. In de volgende tabel wordt het certificaatsjabloondoel gekoppeld aan de waarden in het register:

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

5. Start de server opnieuw op. Gebruik hiervoor niet **iisreset**, omdat deze opdracht de wijzigingen niet opslaat.
6. Blader naar `http://*FQDN*/certsrv/mscep/mscep.dll`. Hier wordt een NDES-pagina weergegeven die vergelijkbaar is met de volgende:

    ![Test NDES](./media/SCEP_NDES_URL.png)

    Als het bericht **503 - Service niet beschikbaar** wordt weergegeven, controleert u de logboeken. De groep van toepassing is waarschijnlijk gestopt vanwege een ontbrekend recht voor de NDES-gebruiker. Deze rechten worden beschreven in stap 1.

##### <a name="install-and-bind-certificates-on-the-ndes-server"></a>Certificaten op de NDES-server installeren en verbinden

1. Vraag op uw NDES-server een **serververificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat. Vervolgens verbindt u dit SSL-certificaat in IIS.

    > [!TIP]
    > Nadat u het SSL-certificaat in IIS hebt verbonden, installeert u een clientverificatiecertificaat. Dit certificaat kan worden verleend door elke CA die wordt vertrouwd door de NDES-server. U kunt hetzelfde certificaat gebruiken als voor het certificaat het gebruik van de client- en serververificatiesleutels is ingesteld (**Uitgebreid sleutelgebruik**). Bekijk de volgende stappen voor informatie over deze verificatiecertificaten.

   1. Nadat u het serververificatiecertificaat hebt ontvangen, opent u **IIS-beheer** en selecteert u de **standaardwebsite**. Selecteer **Bindingen** in het deelvenster **Acties**.

   2. Selecteer **Toevoegen**, stel **Type** in op **https** en controleer vervolgens of de poort **443** is. Als Intune zelfstandig wordt gebruikt, wordt alleen poort 443 ondersteund.

   3. Voer voor het **SSL-certificaat** het serververificatiecertificaat in.

      > [!NOTE]
      > Als de NDES-server een externe en interne naam voor één netwerkadres gebruikt, moet het serververificatiecertificaat het volgende bevatten:
      > - Een **onderwerpnaam** met een externe openbare servernaam
      > - Een **alternatieve onderwerpnaam** die de naam van de interne server bevat

2. Vraag op uw NDES-server een **clientverificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat. Dit kan hetzelfde certificaat zijn als het serververificatiecertificaat indien dat certificaat beide mogelijkheden heeft.

    Het clientverificatiecertificaat moet de volgende eigenschappen hebben:

    - **Uitgebreid sleutelgebruik**: Deze waarde moet **Clientverificatie** bevatten

    - **Onderwerpnaam**: Deze waarde moet gelijk zijn aan de DNS-naam van de server waarop u het certificaat installeert (de NDES-server)

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
Bij deze stap doet u het volgende:

- Schakelt u de ondersteuning voor NDES in Intune in.
- Download, installeer en configureer de certificaatconnector op de server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd/server in uw omgeving. Als u de schaal van de NDES-implementatie in uw organisatie wilt vergroten, kunt u op elke NDES-server meerdere NDES-servers met een certificaatconnector van Microsoft Intune installeren.

##### <a name="download-install-and-configure-the-certificate-connector"></a>De certificaatconnector downloaden, installeren en configureren

> [!IMPORTANT] 
> De Microsoft Intune-certificaatconnector **moet** worden geïnstalleerd op een afzonderlijke Windows-server. Deze kan niet worden geïnstalleerd op de verlenende certificeringsinstantie (CA). De connector **moet** ook worden geïnstalleerd op dezelfde server die de rol van Network Device Enrollment Service (NDES) vervult.

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Certificeringsinstantie** > **Toevoegen**
3. Download het connectorbestand en sla het op. Sla het bestand op op een locatie die toegankelijk is vanaf de server waar u de connector gaat installeren.

    ![ConnectorDownload](./media/certificates-download-connector.png)

4. Nadat het downloaden is voltooid, gaat u naar de server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd. Vervolgens:

    1. Controleer of .NET 4.5 Framework is geïnstalleerd. Dit wordt vereist door de NDES-certificaatconnector. .NET Framework 4.5 wordt automatisch geïnstalleerd met Windows Server 2012 R2 en nieuwere versies.
    2. Voer het installatieprogramma uit (**NDESConnectorSetup.exe**). Het installatieprogramma installeert ook de beleidsmodule voor NDES en de CRP-webservice. De CRP-webservice, CertificateRegistrationSvc, wordt als een toepassing in IIS uitgevoerd.

    > [!NOTE]
    > Wanneer u NDES installeert en Intune zelfstandig wordt gebruikt, wordt de CRP-service automatisch met de certificaatconnector geïnstalleerd. Wanneer u Intune met Configuration Manager gebruikt, installeert u het certificaatregistratiepunt als een afzonderlijke sitesysteemfunctie.

5. Als naar het clientcertificaat voor de certificaatconnector wordt gevraagd, kiest u **Selecteren**en selecteert u het certificaat voor **clientverificatie** dat u in stap 4 op uw NDES-server hebt geïnstalleerd.

    Nadat u het certificaat voor clientverificatie hebt geselecteerd, keert u terug naar het oppervlak **Clientcertificaat voor Microsoft Intune-certificaatconnector** . Hoewel het geselecteerde certificaat niet wordt weergegeven, selecteert u **Volgende** om de eigenschappen van dat certificaat weer te geven. Selecteer **Volgende** en vervolgens **Installeren**.

    > [!IMPORTANT]
    > Internet Explorer Enhanced Security Configuration [moet zijn ingeschakeld op de NDES-server](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) waarop de Intune Certificate Connector wordt gehost.

6. Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

    > [!TIP]
    > Als u de wizard sluit voordat u de gebruikersinterface van de certificaatconnector start, kunt u deze opnieuw openen door de volgende opdracht uit te voeren:
    >
    > <installatiepad>\NDESConnectorUI\NDESConnectorUI.exe

7. In de gebruikersinterface van de **certificaatconnector** :

    Selecteer **Aanmelden** en voer uw Intune-servicebeheerder- of tenantbeheerderreferenties met de machtiging voor algemeen beheer in. Nadat u zich hebt aangemeld, wordt via de Intune Certificate Connector een certificaat van Intune gedownload. Dit certificaat wordt gebruikt voor verificatie tussen de connector en Intune.

    > [!IMPORTANT]
    > Aan het gebruikersaccount moet een geldige Intune-licentie worden toegewezen. Als het gebruikersaccount geen geldige Intune-licentie heeft, mislukt NDESConnectorUI.exe.

    Als uw organisatie een proxyserver gebruikt en de NDES-server de proxy nodig heeft om toegang tot internet te krijgen, selecteert u **Proxyserver gebruiken**. Voer vervolgens de naam van de proxyserver, de poort en de accountreferenties in om verbinding te maken.

    Selecteer het tabblad **Geavanceerd** en voer vervolgens referenties in voor een account met de machtiging **Certificaten verlenen en beheren** op uw verlenende certificeringsinstantie. **Pas** de wijzigingen toe.

    U kunt nu de gebruikersinterface van de certificaatconnector sluiten.

8. Open een opdrachtprompt, voer **services.msc** in en druk vervolgens op **Enter**. Klik met de rechtermuisknop op de **Intune-connectorservice** > **Opnieuw opstarten**.

Controleer of de service wordt uitgevoerd door een browser te openen en de volgende URL in te voeren. Hierop moet een **403**-fout worden geretourneerd:

`http://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> TLS 1.2-ondersteuning wordt geleverd met de NDES-certificaatconnector. Als de server met daarop de NDES-certificaatconnector TLS 1.2 ondersteunt, wordt TLS 1.2 gebruikt. Als de server TLS 1.2 niet ondersteunt, wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

## <a name="create-a-scep-certificate-profile"></a>Een SCEP-certificaatprofiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer een **naam** en een **beschrijving** in voor het SCEP-certificaatprofiel.
4. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit SCEP-certificaat. Op dit moment kunt u een van de volgende platforms selecteren voor apparaatbeperkingsinstellingen:
   - **Android**
   - **Android Enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 en hoger**
   - **Windows 10 en hoger**
5. Selecteer in de vervolgkeuzelijst **Profieltype** de optie **SCEP-certificaat**.
6. Voer de volgende instellingen in:

   - **Certificaattype**: Kies **Gebruiker** voor gebruikerscertificaten. Kies **Apparaat** voor apparaten zonder gebruiker, zoals kiosken. Er zijn **Apparaat**-certificaten beschikbaar voor de volgende platformen:  
     - Android Enterprise
     - iOS
     - macOS
     - Windows 8.1 en hoger
     - Windows 10 en hoger


   - **Indeling van de onderwerpnaam**: Selecteer hoe de onderwerpnaam in de certificaataanvraag automatisch wordt gemaakt met Intune. De beschikbare opties kunnen verschillen, afhankelijk van het gekozen certificaattype: **Gebruiker** of **Apparaat**. 

        **Certificaattype Gebruiker**  

        U kunt e-mailadres van de gebruiker in de onderwerpnaam opnemen. U kunt kiezen uit:

        - **Niet geconfigureerd**
        - **Algemene naam**
        - **Algemene naam en e-mailadres**
        - **Algemene naam als e-mailadres**
        - **IMEI (International Mobile Equipment Identity)**
        - **Serienummer**
        - **Aangepast**: Wanneer u deze optie selecteert, wordt het tekstvak **Aangepast** ook weergegeven. Met dit veld kunt u een onderwerpnaam invoeren in een aangepaste indeling, inclusief variabelen. Aangepaste indeling ondersteunt twee variabelen: **Algemene naam (CN)** en **E-mail (E)**. **Algemene naam (CN)** kan worden ingesteld op een van de volgende variabelen:

            - **CN={{UserName}}**: De principal-naam van de gebruiker, bijvoorbeeld janedoe@contoso.com
            - **CN={{AAD_Device_ID}}**: Een id die wordt toegewezen wanneer u een apparaat in Azure Active Directory (AD) registreert. Deze id wordt doorgaans gebruikt voor verificatie met Azure AD.
            - **CN={{SERIALNUMBER}}**: Het unieke serienummer dat doorgaans wordt gebruikt door de fabrikant om een apparaat te identificeren
            - **CN={{IMEINumber}}**: Het unieke nummer van de International Mobile Equipment Identity (IMEI) dat wordt gebruikt om een mobiele telefoon te identificeren
            - **CN={{OnPrem_Distinguished_Name}}**: Een reeks relatieve namen die door komma's worden gescheiden, bijvoorbeeld `CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com`

                Als u de variabele `{{OnPrem_Distinguished_Name}}` wilt gebruiken, moet u het gebruikerskenmerk `onpremisesdistingishedname` met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD.

            - **CN={{onPremisesSamAccountName}}**: Beheerders kunnen het kenmerk samAccountName van Active Directory synchroniseren naar Azure AD via Azure AD Connect in een kenmerk met de naam `onPremisesSamAccountName`. Deze variabele kan in Intune worden vervangen als onderdeel van een aanvraag voor certificaatuitgifte in het onderwerp van een SCEP-certificaat.  Het kenmerk samAccountName is de aanmeldingsnaam van de gebruiker die wordt gebruikt ter ondersteuning van clients en servers uit een vorige versie van Windows (pre-Windows 2000). De indeling van de gebruikersaanmeldingsnaam is: `DomainName\testUser` of alleen `testUser`.

                Als u de variabele `{{onPremisesSamAccountName}}` wilt gebruiken, moet u het gebruikerskenmerk `onPremisesSamAccountName` met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD.

            Door een combinatie van een of meer van deze variabelen en statische tekenreeksen te gebruiken, kunt u een aangepaste indeling voor de naam van een certificaathouder maken, bijvoorbeeld:  

            **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**

            In dit voorbeeld hebt u een indeling voor de naam van een certificaathouder gemaakt, waarin naast de variabelen voor CN en E gebruik wordt gemaakt van tekenreeksen voor de waarden Organisatie-eenheid, Organisatie, Locatie, Regio en Land. [De functie CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) beschrijft deze functie en de ondersteunde tekenreeksen.

        **Certificaattype Apparaat**  

        Als u het certificaattype **Apparaat** gebruikt, kunt u ook de volgende variabelen van het apparaatcertificaat gebruiken voor de waarde:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Deze variabelen kunnen met statische tekst worden toegevoegd in een tekstvak voor aangepaste waarden. De algemene naam kan bijvoorbeeld worden toegevoegd als `CN = {{DeviceName}}text`.

        > [!IMPORTANT]
        >  - In de statische tekst van het onderwerp leiden accolades **{ }** die geen variabele insluiten, tot een fout. 
        >  - Wanneer u een variabele voor een apparaatcertificaat gebruikt, plaatst u de variabele tussen accolades **{ }**.
        >  - `{{FullyQualifiedDomainName}}` kan alleen worden gebruikt voor Windows-apparaten en apparaten die aan een domein zijn toegevoegd. 
        >  -  Houd er rekening mee dat wanneer u in het onderwerp of de alternatieve naam voor het onderwerp voor een apparaatcertificaat apparaateigenschappen gebruikt, zoals het IMEI-nummer, het serienummer en de Fully Qualified Domain Name, deze eigenschappen kunnen worden vervalst door een persoon met toegang tot het apparaat.
        >  - Het profiel wordt niet geïnstalleerd op het apparaat als de opgegeven apparaatvariabelen niet worden ondersteund. Als bijvoorbeeld {{IMEI}} wordt gebruikt in de onderwerpnaam van een SCEP-profiel dat wordt toegewezen aan een apparaat dat geen IMEI-nummer heeft, mislukt de profielinstallatie. 


   - **Alternatieve naam voor het onderwerp**: Geef op hoe Intune de waarden voor de alternatieve naam van het onderwerp (SAN) automatisch maakt in de certificaataanvraag. De beschikbare opties kunnen verschillen, afhankelijk van het gekozen certificaattype: **Gebruiker** of **Apparaat**. 

        **Certificaattype Gebruiker**  

        De volgende kenmerken zijn beschikbaar:

        - E-mailadres
        - User Principal Name (UPN)

            Als u bijvoorbeeld een gebruikerscertificaattype selecteert, kunt u de User Principal Name (UPN) gebruiken in de alternatieve naam van het onderwerp. Als een clientcertificaat wordt gebruikt om een Network Policy Server te verifiëren, stelt u de alternatieve naam van het onderwerp op de UPN in. 

        **Certificaattype Apparaat**  

        Een aanpasbaar tekstvak in tabelopmaak. De volgende kenmerken zijn beschikbaar:

        - DNS

        Bij het certificaattype **Apparaat** kunt u de volgende variabelen van het apparaatcertificaat gebruiken voor de waarde:  

        ```
        "{{AAD_Device_ID}}",
        "{{Device_Serial}}",
        "{{Device_IMEI}}",
        "{{SerialNumber}}",
        "{{IMEINumber}}",
        "{{AzureADDeviceId}}",
        "{{WiFiMacAddress}}",
        "{{IMEI}}",
        "{{DeviceName}}",
        "{{FullyQualifiedDomainName}}",
        "{{MEID}}",
        ```

        Deze variabelen kunnen met statische tekst worden toegevoegd in het tekstvak voor aangepaste waarden. Het DNS-kenmerk kan bijvoorbeeld worden toegevoegd als `DNS name = {{AzureADDeviceId}}.domain.com`.

        > [!IMPORTANT]
        >  - Accolades **{ }**, pijp-symbolen **|** en puntkomma's **;** kunnen niet worden gebruikt in de statische tekst van de alternatieve naam voor het onderwerp. 
        >  - Wanneer u een variabele voor een apparaatcertificaat gebruikt, plaatst u de variabele tussen accolades **{ }**.
        >  - `{{FullyQualifiedDomainName}}` kan alleen worden gebruikt voor Windows-apparaten en apparaten die aan een domein zijn toegevoegd. 
        >  -  Houd er rekening mee dat wanneer u in het onderwerp of de alternatieve naam voor het onderwerp voor een apparaatcertificaat apparaateigenschappen gebruikt, zoals het IMEI-nummer, het serienummer en de Fully Qualified Domain Name, deze eigenschappen kunnen worden vervalst door een persoon met toegang tot het apparaat.
        >  - Het profiel wordt niet geïnstalleerd op het apparaat als de opgegeven apparaatvariabelen niet worden ondersteund. Als bijvoorbeeld {{IMEI}} wordt gebruikt in de alternatieve onderwerpnaam van een SCEP-profiel dat wordt toegewezen aan een apparaat dat geen IMEI-nummer heeft, mislukt de profielinstallatie.  

   - **Geldigheidsduur van certificaat**: Als u de opdracht `certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE` hebt uitgevoerd op de verlenende CA, waarop een aangepaste geldigheidsperiode mogelijk is, kunt u opgeven hoelang het certificaat geldig blijft.<br>U kunt een waarde invoeren die lager is dan de geldigheidsperiode in de certificaatsjabloon, maar niet hoger. Als de geldigheidsperiode van het certificaat in de certificaatsjabloon bijvoorbeeld twee jaar is, kunt u wel één jaar, maar niet vijf jaar opgeven. De waarde moet ook lager zijn dan de resterende geldigheidsperiode van het certificaat van de verlenende CA. 
   - **Sleutelarchiefprovider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10): Geef op waar de sleutel voor het certificaat wordt bewaard. Kies een van de volgende waarden:
     - **Registeren in de sleutelarchiefprovider voor TPM (Trusted Platform Module) indien TPM aanwezig is, anders registreren in de sleutelarchiefprovider voor software**
     - **Registreren in de sleutelarchiefprovider voor TPM (Trusted Platform Module), anders mislukt**
     - **Registreren bij Passport, anders niet uitvoeren (Windows 10 en hoger)**
     - **Registreren in sleutelarchiefprovider voor software**

   - **Sleutelgebruik**: Voer opties voor sleutelgebruik voor het certificaat in. Uw opties zijn:
     - **Sleutelcodering**: Sta sleuteluitwisseling alleen toe als de sleutel is gecodeerd
     - **Digitale handtekening**: Sta sleuteluitwisseling alleen toe als een digitale handtekening de sleutel helpt beveiligen
   - **Sleutelgrootte (bits)**: Selecteer het aantal bits in de sleutel
   - **Hash-algoritme** (Android, Windows Phone 8.1, Windows 8.1, Windows 10): Selecteer een van de beschikbare typen hash-algoritme om met dit certificaat te gebruiken. Selecteer het sterkste beveiligingsniveau dat door de verbindende apparaten wordt ondersteund.
   - **Basiscertificaat**: Kies een basis-CA-certificaatprofiel dat u eerder hebt geconfigureerd en aan de gebruiker en/of het apparaat hebt toegewezen. Dit CA-certificaat moet het basiscertificaat zijn voor de CA die het certificaat verleent dat u in dit certificaatprofiel gaat configureren. Zorg ervoor dat u dit profiel voor vertrouwde basiscertificaten toewijst aan dezelfde groep die is toegewezen in het SCEP-certificaatprofiel.
   - **Uitgebreide-sleutelgebruik**: **Voeg waarden toe** voor het beoogde gebruik van het certificaat. In de meeste gevallen vereist het certificaat **Clientverificatie** zodat de gebruiker of het apparaat bij een server kan worden geverifieerd. U kunt echter zo nodig andere sleutelgebruiken toevoegen.
   - **Registratie-instellingen**
     - **Drempelwaarde voor verlenging (%)**: Geef het percentage van de levensduur van het certificaat op dat resteert voordat het apparaat verlenging van het certificaat aanvraagt.
     - **URL's van SCEP-server**: Voer een of meer URL's in voor de NDES-servers die certificaten via SCEP verlenen. Voer bijvoorbeeld iets in als `https://ndes.contoso.com/certsrv/mscep/mscep.dll`.
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

## <a name="intune-connector-setup-verification-and-troubleshooting"></a>Configuratie van Intune-connector controleren en problemen oplossen

Zie [Scriptvoorbeelden certificeringsinstantie](https://aka.ms/intuneconnectorverificationscript) om problemen op te lossen en de configuratie van Intune-connector te controleren

## <a name="intune-connector-events-and-diagnostic-codes"></a>Gebeurtenissen en diagnostische codes van de Intune-connector

Vanaf versie 6.1806.x.x legt de Intune-connectorservice gebeurtenissen vast in de **Logboeken** (**Logboeken voor toepassingen en services** > **Microsoft Intune-connector**). Gebruik deze gebeurtenissen om potentiële problemen in de configuratie van de Intune-connector op te lossen. Deze gebeurtenissen leggen de successen en mislukkingen van een bewerking vast, en bevatten ook diagnostische codes met berichten zodat de IT-beheerder problemen kan oplossen.

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
| 20300 | Upload_Success | De aanvraag- of intrekkingsgegevens van het certificaat zijn geüpload. Bekijk de gebeurtenisdetails voor de uploaddetails. | 0x00000000, 0x0FFFFFFF |
| 20302 | Upload_Failure | De aanvraag- of intrekkingsgegevens van het certificaat zijn niet geüpload. Bekijk de gebeurtenisdetails > Uploadstatus om de fout te bepalen.| 0x00000000, 0x0FFFFFFF |
| 20400 | Download_Success | Aanvraag om een certificaat te ondertekenen, een clientcertificaat te downloaden of een certificaat in te trekken, is gedownload. Bekijk de gebeurtenisdetails voor de downloaddetails.  | 0x00000000, 0x0FFFFFFF |
| 20402 | Download_Failure | Aanvraag om een certificaat te ondertekenen, een clientcertificaat te downloaden of een certificaat in te trekken, is niet gedownload. Bekijk de gebeurtenisdetails voor de downloaddetails. | 0x00000000, 0x0FFFFFFF |
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
| 0x00000401 | Symantec_ClientAuthCertNotFound  | Client-Auth Symantec-certificaat is niet gevonden in het lokale certificaatarchief. Zie het artikel [Het Symantec-certificaat voor registratie-autorisatie installeren](https://docs.microsoft.com/intune/certificates-symantec-configure#install-the-symantec-registration-authorization-certificate) voor meer informatie.  |
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

- [PKCS-certificaten gebruiken](certficates-pfx-configure.md) of [PKCS-certificaten uitgeven van een webservice van Symantec PKI-manager](certificates-symantec-configure.md)
- [Een certificeringsinstantie van derden toevoegen om SCEP met Intune te gebruiken](certificate-authority-add-scep-overview.md)
- Gebruik de handleiding [Problemen oplossen met de implementatie van het SCEP-certificaatprofiel in Microsoft Intune](https://support.microsoft.com/help/4457481/troubleshooting-scep-certificate-profile-deployment-in-intune) voor meer hulp.
