---
title: Infrastructuur configureren om SCEP-certificaatprofielen te ondersteunen in Microsoft Intune - Azure | Microsoft Docs
description: Als u SCEP in Microsoft Intune wilt gebruiken, configureert u uw on-premises AD-domein, maakt u een certificeringsinstantie, stelt u de NDES-server in en installeert u de Microsoft Intune Certificate Connector.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c454ae6184f4d2a7c3c31f3c61d2cf4331ac187c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514095"
---
# <a name="configure-infrastructure-to-support-scep-with-intune"></a>Infrastructuur configureren om SCEP te ondersteunen in Intune

Intune ondersteunt het gebruik van Simple Certificate Enrollment Protocol (SCEP) om [verbindingen met uw apps en bedrijfsresources te verifiëren](certificates-configure.md). SCEP maakt gebruik van het certificaat van de certificeringsinstantie (CA) om de uitwisseling van berichten te beveiligen voor de Certificate Signing Request (CSR). Wanneer uw infrastructuur SCEP ondersteunt, kunt u gebruikmaken van *SCEP-certificaatprofielen* van Intune (een apparaatprofieltype in Intune) om de certificaten op uw apparaten te implementeren. De Microsoft Intune Certificate Connector is vereist voor het gebruik van SCEP-certificaatprofielen in Intune wanneer u een Active Directory Certificate Services-certificeringsinstantie gebruikt. De connector is niet vereist wanneer u [externe certificeringsinstanties](certificate-authority-add-scep-overview.md#set-up-third-party-ca-integration) gebruikt. 

De informatie in dit artikel kan u helpen bij het configureren van uw infrastructuur voor de ondersteuning van SCEP wanneer u Active Directory Certificate Services gebruikt. Nadat de infrastructuur is geconfigureerd, kunt u [SCEP-certificaatprofielen maken en implementeren](certificates-profile-scep.md) in Intune.

> [!TIP]
> Intune biedt ook ondersteuning voor het gebruik van [Public Key Cryptography Standards #12-certificaten](certficates-pfx-configure.md).

## <a name="prerequisites-for-using-scep-for-certificates"></a>Vereisten voor het gebruik van SCEP voor certificaten

Voordat u verdergaat, moet u ervoor zorgen dat u [een *vertrouwd certificaatprofiel* hebt gemaakt en geïmplementeerd](certificates-configure.md#export-the-trusted-root-ca-certificate) op apparaten waarop SCEP-certificaatprofielen zullen worden gebruikt. SCEP-certificaatprofielen verwijzen rechtstreeks naar het vertrouwde certificaatprofiel dat u gebruikt om een certificaat van een vertrouwde basis-CA in te richten op apparaten.

### <a name="servers-and-server-roles"></a>Servers en serverfuncties

De volgende on-premises infrastructuur moet worden uitgevoerd op servers die deel uitmaken van uw Active Directory-domein, met uitzondering van de webtoepassingsproxyserver.

- **Certificeringsinstantie**: gebruik een Microsoft Active Directory Certificate Services-certificeringsinstantie (CA) voor ondernemingen die wordt uitgevoerd in een Enterprise-editie van Windows Server 2008 R2 met servicepack 1 of later. De versie van Windows Server die u gebruikt, moet ondersteund blijven door Microsoft. Een zelfstandige CA wordt niet ondersteund. Zie [De certificeringsinstantie installeren](https://technet.microsoft.com/library/jj125375.aspx) voor meer informatie. Als uw certificeringsinstantie werkt met Windows Server 2008 R2 SP1, moet u [de hotfix van KB2483564 installeren](https://support.microsoft.com/kb/2483564/).

- **NDES-serverfunctie**: u moet een NDES-serverfunctie (Registratieservice voor netwerkapparaten) configureren in Windows Server 2012 R2 of later. In een volgende sectie van dit artikel wordt u begeleid bij [het installeren van NDES](#set-up-ndes).

  - De server die als host fungeert voor NDES moet deel uitmaken van het domein en zich in hetzelfde forest bevinden als uw ondernemings-CA.
  - U kunt niet gebruikmaken van NDES die is geïnstalleerd op de server waarop de ondernemings-CA wordt gehost.
  - U gaat de Microsoft Intune Certificate-connector op dezelfde server installeren die als host fungeert voor NDES.

  Zie [Hulp bij Registratieservice voor netwerkapparaten](https://technet.microsoft.com/library/hh831498.aspx) in de Windows Server-documentatie en [Een beleidsmodule gebruiken met de Registratieservice voor netwerkapparaten](https://technet.microsoft.com/library/dn473016.aspx) voor meer informatie over NDES.

- **Microsoft Intune Certificate Connector**: de Microsoft Intune Certificate Connector is vereist voor het gebruik van SCEP-certificaatprofielen in Intune. In dit artikel vindt u instructies voor het [ installeren van deze connector](#install-the-intune-certificate-connector).

  De connector ondersteunt ook de Federal Information Processing Standard-modus (FIPS). FIPS is niet vereist, maar wanneer deze modus is ingeschakeld, kunt u certificaten verlenen en intrekken.
  - De connector moet worden uitgevoerd op dezelfde server als de NDES-serverfunctie, een server met Windows Server 2012 R2 of later.
  - .NET Framework 4.5 is vereist voor de connector en wordt automatisch geïnstalleerd met Windows Server 2012 R2.
  - Verbeterde beveiliging van Internet Explorer [moet zijn ingeschakeld op de server die als host fungeert voor NDES](https://technet.microsoft.com/library/cc775800(v=WS.10).aspx) en de Microsoft Intune Certificate Connector.

De volgende on-premises infrastructuur is optioneel:

Als u wilt dat apparaten op internet certificaten ontvangen, moet u uw NDES-URL extern publiceren in uw bedrijfsnetwerk. U kunt de Azure AD-toepassingsproxy, de webtoepassingsproxyserver of een andere omgekeerde proxy gebruiken.

- **Azure AD-toepassingsproxy** (optioneel): u kunt de Azure AD-toepassingsproxy gebruiken in plaats van een toegewezen webtoepassingsproxyserver (WAP-server) om de NDES-URL op internet te publiceren. Op die manier kunnen er certificaten worden verkregen voor zowel intranet- als internetgerichte apparaten. Zie voor meer informatie [Beveiligde externe toegang verschaffen voor on-premises toepassingen](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- **Webtoepassingsproxyserver** (optioneel): gebruik een server met Windows Server 2012 R2 of later als webtoepassingsproxyserver (WAP-server) om uw NDES-URL op internet te publiceren.  Op die manier kunnen er certificaten worden verkregen voor zowel intranet- als internetgerichte apparaten.

  De server die als host voor WAP fungeert, [moet een update installeren](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) waarmee ondersteuning wordt geboden voor de lange URL's die worden gebruikt door de Network Device Enrollment Service. Deze update is opgenomen in het [updatepakket van december 2014](https://support.microsoft.com/kb/3013769)en is afzonderlijk verkrijgbaar in [KB3011135](https://support.microsoft.com/kb/3011135).

  De WAP-server moet een SSL-certificaat hebben dat overeenkomt met de naam die op externe clients is gepubliceerd en het SSL-certificaat vertrouwen dat wordt gebruikt op de computer waarop de NDES-service wordt gehost. De WAP-server kan met deze certificaten de SSL-verbinding van clients beëindigen en een nieuwe SSL-verbinding naar de NDES-service maken.

  Zie [Certificaten voor WAP plannen](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn383650(v=ws.11)#plan-certificates) en [algemene informatie over WAP-servers](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn584113(v=ws.11)) voor meer informatie.

### <a name="accounts"></a>Accounts

- **NDES-serviceaccount**: identificeer een domeingebruikersaccount om als NDES-serviceaccount te gebruiken voordat u NDES instelt. U geeft dit account op wanneer u sjablonen op uw verlenende CA configureert voordat u NDES configureert.

  Dit account moet de volgende rechten hebben op de server die als host fungeert voor NDES:

  - **Lokaal aanmelden**
  - **Aanmelden als service**
  - **Aanmelden als batchtaak**

  Zie [Een domeingebruikersaccount maken om te fungeren als NDES-serviceaccount](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v=ws.11)#to-create-a-domain-user-account-to-act-as-the-ndes-service-account) voor meer informatie.

- **Toegang tot de computer die als host fungeert voor de NDES-service**: u hebt een domeingebruikersaccount nodig met machtigingen voor het installeren en configureren van Windows-serverfuncties op de server waarop u NDES installeert.

- **Toegang tot de certificeringsinstantie**: u hebt een domeingebruikersaccount nodig dat beschikt over de rechten voor het beheren van uw certificeringsinstantie.

### <a name="network-requirements"></a>Netwerkvereisten

Het is raadzaam de NDES-service te publiceren via een omgekeerde proxy, zoals de [Azure AD-toepassingsproxy, Web Access Proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/) of een externe proxy. Als u geen omgekeerde proxy gebruikt, moet u TCP-verkeer toestaan van alle hosts en IP-adressen op internet naar de NDES-service via poort 443.

Sta alle poorten en protocollen toe die nodig zijn voor communicatie tussen de NDES-service en ondersteunende infrastructuur in uw omgeving. De computer waarop de NDES-service wordt gehost, moet bijvoorbeeld communiceren met de CA, DNS-servers, domeincontrollers en mogelijk andere services of servers in uw omgeving, zoals Configuration Manager.

### <a name="certificates-and-templates"></a>Certificaten en sjablonen

De volgende certificaten en sjablonen worden gebruikt wanneer u SCEP gebruikt.

|Object    |Details    |
|----------|-----------|
|**SCEP-certificaatsjabloon**         |De sjabloon die u gaat configureren op uw verlenende CA, die wordt gebruikt om de SCEP-aanvragen van apparaten uit te voeren. |
|**Clientverificatiecertificaat** |Aangevraagd door uw verlenende CA of openbare CA.<br /> U installeert dit certificaat op de computer die als host fungeert voor de NDES-service en wordt gebruikt door de Microsoft Intune Certificate Connector.<br /> Als voor het certificaat het gebruik van *client-* en *serververificatiesleutels* is ingesteld (**Uitgebreid sleutelgebruik**) voor de CA-sjabloon die u gebruikt om dit certificaat te verlenen, dan kunt u hetzelfde certificaat gebruiken voor zowel server- als clientverificatie. |
|**Serververificatiecertificaat** |Webservercertificaat aangevraagd door uw verlenende CA of openbare CA.<br /> U installeert en verbindt dit SSL-certificaat in IIS op de computer die als host fungeert voor NDES.<br />Als voor het certificaat het gebruik van *client-* en *serververificatiesleutels* is ingesteld (**Uitgebreid sleutelgebruik**) voor de CA-sjabloon die u gebruikt om dit certificaat te verlenen, dan kunt u hetzelfde certificaat gebruiken voor zowel server- als clientverificatie. |
|**Vertrouwd basis-CA-certificaat**       |Als u een SCEP-certificaatprofiel wilt gebruiken, moeten de apparaten uw vertrouwde basiscertificeringsinstantie (CA) vertrouwen. Gebruik een *vertrouwd certificaatprofiel* in Intune om het vertrouwde basis-CA-certificaat in te richten voor gebruikers en apparaten. <br/><br/> **-** Gebruik één vertrouwd basis-CA-certificaat per besturingssysteemplatform en koppel dat certificaat aan elk vertrouwde certificaatprofiel dat u maakt. <br /><br /> **-** U kunt extra vertrouwde basis-CA-certificaten gebruiken als dat nodig is. U kunt bijvoorbeeld extra certificaten gebruiken om een vertrouwensrelatie met een CA te leveren die de serververificatiecertificaten voor uw Wi-Fi-toegangspunten ondertekent. Maak extra vertrouwde basis-CA-certificaten voor verlenende CA's.  In het SCEP-certificaatprofiel dat u in Intune maakt, moet u het vertrouwde basis-CA-profiel voor de verlenende CA opgeven.<br/><br/> Zie [Het vertrouwde basis-CA-certificaat exporteren](certificates-configure.md#export-the-trusted-root-ca-certificate) en [Profielen voor vertrouwde certificaten maken](certificates-configure.md#create-trusted-certificate-profiles) in *Certificaten voor verificatie gebruiken in Intune* voor meer informatie over het vertrouwde certificaatprofiel. |

## <a name="configure-the-certification-authority"></a>Configureert u de certificeringsinstantie

In de volgende secties gaat u het volgende doen:

- De vereiste sjabloon voor NDES configureren en publiceren
- De vereiste machtigingen voor het intrekken van certificaten instellen.

Voor de volgende secties is kennis nodig van Windows Server 2012 R2 of later en van Active Directory Certificate Services (AD CS).

### <a name="access-your-issuing-ca"></a>Toegang tot uw verlenende CA

1. Meld u aan bij uw verlenende CA met een domeinaccount met voldoende rechten om de CA te beheren.

2. Open de Microsoft Management Console (MMC) van de certificeringsinstantie. Vervolgens kunt u 'certsrv.msc' **Uitvoeren** of in **Serverbeheer** klikken op **Extra** en vervolgens op **Certificeringsinstantie**.

3. Selecteer het knooppunt **Certificaatsjablonen** en klik op **Actie** > **Beheren**.

### <a name="create-the-scep-certificate-template"></a>De SCEP-certificaatsjabloon maken

1. Maak een v2-certificaatsjabloon (met Windows 2003-compatibiliteit) om te gebruiken als de SCEP-certificaatsjabloon. U kunt het volgende doen:

   - Gebruik de module *Certificeringssjablonen* om een nieuwe aangepaste sjabloon te maken.
   - Kopieer een bestaande sjabloon (bijvoorbeeld de Gebruikerssjabloon) en werk de kopie vervolgens bij voor gebruik als NDES-sjabloon.

2. Configureer de volgende instellingen op de opgegeven tabbladen van de sjabloon:

   - **Algemeen**:

     - Schakel **Certificaat in Active Directory publiceren** uit.
     - Geef een beschrijvende **Weergavenaam van sjabloon** op, zodat u deze sjabloon later kunt identificeren.

   - **Onderwerpnaam**:

     - Selecteer **Met de aanvraag meeleveren**. Beveiliging wordt afgedwongen door de Intune-beleidsmodule voor NDES.

       ![Sjabloon, tabblad Onderwerpnaam](./media/certificates-scep-configure/scep-ndes-subject-name.jpg)

   - **Extensies**:

     - Zorg ervoor dat de **Beschrijving van toepassingsbeleid** de optie **Clientverificatie** bevat.

       > [!IMPORTANT]
       > Voeg alleen het toepassingsbeleid toe dat u nodig hebt. Leg uw keuzes voor aan de beveiligingsbeheerder.

     - Bewerk voor iOS-/iPadOS- en macOS-certificaatsjablonen ook **Sleutelgebruik** en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

     ![Sjabloon, tabblad Extensies](./media/certificates-scep-configure/scep-ndes-extensions.jpg)  

   - **Beveiliging**:

     - Voeg het **NDES-serviceaccount** toe. Voor dit account zijn de machtigingen **Lezen** en **Registreren** voor deze sjabloon vereist.

     - Voeg aanvullende accounts toe voor Intune-beheerders die SCEP-profielen gaan maken. Voor deze accounts is de machtiging **Lezen** voor de sjabloon vereist zodat deze beheerders naar deze sjabloon kunnen bladeren tijdens het maken van SCEP-profielen.

     ![Sjabloon, tabblad Beveiliging](./media/certificates-scep-configure/scep-ndes-security.jpg)

   - **Afhandeling van aanvragen**:

     De volgende afbeelding is een voorbeeld. Uw configuratie kan anders zijn.  

     ![Sjabloon, tabblad Afhandeling van aanvragen](./media/certificates-scep-configure/scep-ndes-request-handling.png)

   - **Uitgiftevereisten**:

     De volgende afbeelding is een voorbeeld. Uw configuratie kan anders zijn.

     ![Sjabloon, tabblad Uitgiftevereisten](./media/certificates-scep-configure/scep-ndes-issuance-reqs.jpg)

3. Sla de certificaatsjabloon op.

### <a name="create-the-client-certificate-template"></a>De clientcertificaatsjabloon maken

Voor de Intune Certificate Connector is een certificaat vereist met het uitgebreide sleutelgebruik *Clientverificatie* en een Onderwerpnaam die gelijk is aan de FQDN van de computer waarop de connector is geïnstalleerd. Er is een sjabloon met de volgende eigenschappen vereist:

- **Extensies** > **Toepassingsbeleid** moet **Clientverificatie** bevatten
- **Onderwerpnaam** > **Met de aanvraag meeleveren**.

Als u al een sjabloon hebt waarin deze eigenschappen zijn opgenomen, kunt u deze opnieuw gebruiken. Anders maakt u een nieuwe sjabloon door een bestaande te dupliceren of een aangepaste sjabloon te maken.

### <a name="create-the-server-certificate-template"></a>De servercertificaatsjabloon maken

Voor de communicatie tussen beheerde apparaten en IIS op de NDES-server wordt HTTPS gebruikt, waarvoor het gebruik van een certificaat is vereist. U kunt het certificaat **Webserver** gebruiken om dit certificaat te verlenen. Als u liever een speciale sjabloon hebt, zijn de volgende eigenschappen vereist:

- **Extensies** > **Toepassingsbeleid** moet **Serververificatie** bevatten
- **Onderwerpnaam** > **Met de aanvraag meeleveren**.

> [!NOTE]
> Als u een certificaat hebt dat voldoet aan de vereisten van zowel de client- als servercertificaatsjabloon, kunt u één certificaat voor zowel IIS als de Intune Certificate Connector gebruiken.

### <a name="grant-permissions-for-certificate-revocation"></a>Machtigingen verlenen voor het intrekken van certificaten

Als u wilt dat certificaten die niet meer nodig zijn door Intune worden ingetrokken, moet u daartoe machtigingen verlenen in de certificeringsinstantie.

In de Intune Certificate Connector kunt u het **systeemaccount** van de NDES-server gebruiken of een specifiek account, zoals het **NDES-serviceaccount**.

1. Klik in de console van de certificeringsinstantie met de rechtermuisknop op de CA-naam en selecteer **Eigenschappen**.

2. Klik op het tabblad **Beveiliging** op **Toevoegen**.

3. Verleen de machtiging **Certificaten verlenen en beheren**:

   - Als u ervoor kiest het **systeemaccount** van de NDES-server te gebruiken, geeft u de machtigingen op voor de NDES-server.
   - Als u ervoor kiest om het **NDES-serviceaccount** te gebruiken, geeft u in plaats daarvan machtigingen voor dat account op.

### <a name="modify-the-validity-period-of-the-certificate-template"></a>De geldigheidsduur van de certificaatsjabloon wijzigen

U kunt optioneel de geldigheidsduur van de certificaatsjabloon wijzigen.  

Na het [maken van de SCEP-certificaatsjabloon](#create-the-scep-certificate-template) kunt u de sjabloon bewerken om de **Geldigheidsduur** op het tabblad **Algemeen** te controleren.

Standaard gebruikt Intune de waarde die is geconfigureerd in de sjabloon. U kunt de CA echter zodanig configureren dat de aanvrager een andere waarde kan invoeren, en die waarde kan worden ingesteld in de Intune-beheerconsole.

> [!IMPORTANT]
> Gebruik voor iOS/iPadOS en macOS altijd een waarde die in de sjabloon is ingesteld.

#### <a name="to-configure-a-value-that-can-be-set-from-within-the-intune-console"></a>Een waarde configureren die in de Intune-console kan worden ingesteld

1. Voer de volgende opdracht voor de CA uit:

   -**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**
   -**net stop certsvc**
   -**net start certsvc**

2. Gebruik op de verlenende CA de module Certificeringsinstantie om de certificaatsjabloon te publiceren. Selecteer het knooppunt **Certificaatsjablonen**, selecteer **Actie** > **Nieuw** > **Te verlenen certificaatsjablonen** en selecteer vervolgens de certificaatsjabloon die u in de vorige sectie hebt gemaakt.

3. Controleer of de sjabloon is gepubliceerd door deze te bekijken in de map **Certificaatsjablonen**.

## <a name="set-up-ndes"></a>NDES instellen

Met de volgende procedures kunt u de Registratieservice voor netwerkapparaten (NDES) configureren voor gebruik in Intune. Zie [Hulp bij Registratieservice voor netwerkapparaten](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831498(v%3dws.11)) voor meer informatie.

### <a name="install-the-ndes-service"></a>De NDES-service installeren

1. Meld u als **Ondernemingsbeheerder** aan op de server die als host voor NDES fungeert en gebruik vervolgens de [wizard Functies en onderdelen toevoegen](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) om NDES te installeren:

   1. Selecteer in de wizard **Active Directory Certificate Services** om toegang te krijgen tot de AD CS-functieservices. Selecteer **Registratieservice voor netwerkapparaten**, schakel **Certificeringsinstantie** uit en voltooi vervolgens de wizard.

      > [!TIP]
      > Selecteer **Sluiten** niet tijdens **Voortgang van de installatie**. Selecteer in plaats daarvan de koppeling **Active Directory Certificate Services op de doelserver configureren**. De wizard **AD CS-configuratie** wordt geopend, die u gebruikt voor de volgende procedure in dit artikel: *de NDES-service configureren*. Nadat AD CS-configuratie is geopend, kunt u de wizard Functies en onderdelen toevoegen sluiten.

   2. Wanneer NDES aan de server wordt toegevoegd, installeert de wizard ook IIS. Controleer of IIS de volgende configuraties heeft:

      - **Webserver** > **Beveiliging** > **Aanvraagfiltering**
      - **Webserver** > **Toepassingsontwikkeling** > **ASP.NET 3.5**

        Als u ASP.NET 3.5 installeert, installeert u ook .NET Framework 3.5. Als u .NET Framework 3.5 installeert, installeert u zowel het kernonderdeel **.NET Framework 3.5** als **HTTP-activering**.

      - **Webserver** > **Toepassingsontwikkeling** > **ASP.NET 4.5**

        Als u ASP.NET 4.5 installeert, installeert u ook .NET Framework 4.5. Als u .NET Framework 4.5 installeert, installeer dan het kernonderdeel **.NET Framework 4.5**, **ASP.NET 4.5** en de functie **WCF-services** > **HTTP-activering**.

      - **Beheerhulpprogramma's** > **Compatibiliteit met IIS 6-beheer** > **Compatibiliteit met IIS 6-metabase**
      - **Beheerhulpprogramma's** > **Compatibiliteit met IIS 6-beheer** > **Compatibiliteit met IIS 6 WMI**
      - Voeg op de server het NDES-serviceaccount toe als lid van de lokale groep **IIS_IUSR**.

2. Voer de volgende opdracht uit via een opdrachtprompt met verhoogde bevoegdheid op de computer waarop de NDES-service wordt gehost. Met de volgende opdracht stelt u de SPN van het NDES-serviceaccount in:

   `setspn -s http/<DNS name of the computer that hosts the NDES service> <Domain name>\<NDES Service account name>`

   Als de computer waarop de NDES-service wordt gehost bijvoorbeeld **Server01** heet, uw domein **Contoso.com** is en het serviceaccount **NDESService** is, gebruikt u:

   `setspn –s http/Server01.contoso.com contoso\NDESService`  

### <a name="configure-the-ndes-service"></a>De NDES-service configureren

1. Open op de computer waarop de NDES-service wordt gehost de wizard **AD CS-configuratie** en breng de volgende wijzigingen aan:

   > [!TIP]
   > Als u verdergaat vanuit de vorige procedure en op de koppeling **Active Directory Certificate Services op de doelserver configureren** hebt geklikt, is deze wizard al geopend. Anders opent u Serverbeheer voor toegang tot post-implementatieconfiguratie voor Active Directory Certificate Services.

   - Selecteer in **Functieservices** de optie **Registratieservice voor netwerkapparaten**.
   - Geef in **Serviceaccount voor NDES** het NDES-serviceaccount op.
   - Klik in **CA voor NDES** op **Selecteren** en selecteer vervolgens de verlenende CA waar u de certificaatsjabloon hebt geconfigureerd.
   - Stel in **Cryptografie voor NDES** de sleutellengte in om aan de vereisten van uw bedrijf te voldoen.
   - Selecteer in **Bevestiging** **Configureren** om de wizard te voltooien.

2. Na voltooiing van de wizard, werkt u de volgende registersleutel bij op de computer waarop de NDES-service wordt gehost:

   `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\`

   Voor het bijwerken van deze sleutel gaat u naar het **Doel** (op het tabblad **Afhandeling van aanvragen**) van de certificaatsjablonen. Werk vervolgens de bijbehorende registervermelding bij. Vervang hiervoor de bestaande gegevens door de naam van de certificaatsjabloon (niet de weergavenaam van de sjabloon) die u hebt opgegeven bij het [maken van het certificaatsjabloon](#create-the-scep-certificate-template).

   In de volgende tabel wordt het certificaatsjabloondoel gekoppeld aan de waarden in het register:

   |Certificaatsjabloondoel (op het tabblad Afhandeling van aanvragen)|Te bewerken registerwaarde|Waarde die in de Intune-beheerconsole wordt weergegeven voor het SCEP-profiel|
   |------------------------|-------------------------|---|
   |Handtekening               |SignatureTemplate        |Digitale handtekening |
   |Versleuteling              |EncryptionTemplate       |Sleutelcodering  |
   |Handtekening en versleuteling|GeneralPurposeTemplate   |Sleutelcodering <br/> Digitale handtekening |

   Als het doel van uw certificaatsjabloon bijvoorbeeld **Versleuteling**is, bewerkt u de waarde **EncryptionTemplate** zo dat deze de naam van uw certificaatsjabloon is.

3. Configureer IIS-aanvraagfiltering om in IIS ondersteuning toe te voegen voor de lange URL's (query's) die de NDES-service ontvangt.

   1. Selecteer in IIS-beheer **Standaardwebsite** > **Aanvraagfiltering** > **Functie-instelling bewerken** om de pagina **Instellingen voor aanvraagfiltering bewerken** te openen.

   2. Configureer de volgende instellingen:

      - **Maximale URL-lengte (in bytes)** = 65534
      - **Maximale queryreeks (in bytes)** = 65534

   3. Selecteer **OK** om deze configuratie op te slaan en IIS-beheer te sluiten.

   4. Valideer deze configuratie door de volgende registersleutel te bekijken om te bevestigen dat deze de aangegeven waarden bevat:

      `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters`

      De volgende waarden zijn ingesteld als DWORD-vermeldingen:

      - Naam: **MaxFieldLength**, met een decimale waarde van **65534**
      - Naam: **MaxRequestBytes**, met een decimale waarde van **65534**

4. Start de server die als host fungeert voor de NDES-service opnieuw op. Gebruik **iisreset** niet, want daarmee worden de benodigde wijzigingen niet voltooid.

5. Blader naar *http://* Server_FQDN */certsrv/mscep/mscep.dll*. Hier wordt een NDES-pagina weergegeven die vergelijkbaar is met de volgende afbeelding:

   ![Test NDES](./media/certificates-scep-configure/scep-ndes-url.png)

   Als vanuit het webadres wordt geretourneerd dat een **503-service niet beschikbaar is**, controleert u de computerlogboeken. Deze fout treedt doorgaans op wanneer de groep van toepassingen is gestopt vanwege een ontbrekende [machtiging voor het NDES-serviceaccount](#accounts).
  
### <a name="install-and-bind-certificates-on-the-server-that-hosts-ndes"></a>Certificaten installeren en verbinden op de server waarop NDES wordt gehost

> [!TIP]
> In de volgende procedure kunt u één certificaat gebruiken voor zowel *serververificatie* als *clientverificatie* als de configuratie van dat certificaat voldoet aan de criteria van beide gebruikswijzen. De criteria voor beide gebruikswijzen worden beschreven in stap 1 en 3 van de volgende procedure.

1. Vraag een **serververificatiecertificaat** aan bij uw interne CA of een openbare CA en installeer het certificaat.

   Als de server een externe en interne naam voor één netwerkadres gebruikt, moet het serververificatiecertificaat het volgende bevatten:

   - Een **Onderwerpnaam** met een externe openbare servernaam.
   - Een **Alternatieve naam voor onderwerp** die de interne servernaam bevat.

2. Verbind het serververificatiecertificaat in IIS:

   1. Nadat u het serververificatiecertificaat hebt geïnstalleerd, opent u **IIS-beheer** en selecteert u de **Standaardwebsite**. Selecteer **Bindingen** in het deelvenster **Acties**.

   1. Selecteer **Toevoegen**, stel **Type** in op **https** en controleer vervolgens of de poort **443** is.
   
   1. Geef voor het **SSL-certificaat**het serververificatiecertificaat op.

3. Vraag op uw NDES-server een **clientverificatie** certificaat van uw interne CA of een openbare CA aan en installeer het certificaat.

   Het clientverificatiecertificaat moet de volgende eigenschappen hebben:

   - **Uitgebreid sleutelgebruik**: Deze waarde moet **Clientverificatie** bevatten.
   - **Onderwerpnaam**: Deze waarde moet gelijk zijn aan de DNS-naam van de server waarop u het certificaat installeert (de NDES-server).

4. De server die als host fungeert voor de NDES-service is nu gereed om de Intune Certificate Connector te ondersteunen.

## <a name="install-the-intune-certificate-connector"></a>De Microsoft Intune Certificate Connector installeren

De Microsoft Intune Certificate Connector wordt geïnstalleerd op server waarop uw NDES-service wordt uitgevoerd. Het gebruik van NDES of de Intune Certificate Connector op dezelfde server als uw verlenende certificeringsinstantie (CA) wordt niet ondersteund.

### <a name="to-install-the-certificate-connector"></a>Certificate Connector installeren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Certificaatconnectors** > **Toevoegen**.

3. Download de connector voor het SCEP-bestand en sla deze op. Sla het bestand op op een locatie die toegankelijk is vanaf de server waar u de connector gaat installeren.

   ![ConnectorDownload](./media/certificates-scep-configure/download-certificates-connector.png)

4. Nadat het downloaden is voltooid, gaat u naar de server waarop de NDES-rol (Registratieservice voor netwerkapparaten) wordt uitgevoerd. Vervolgens:

   1. Controleer of .NET 4.5 Framework is geïnstalleerd. Dit wordt vereist door de Intune Certificate Connector. .NET Framework 4.5 wordt automatisch geïnstalleerd met Windows Server 2012 R2 en nieuwere versies.

   2. Voer het installatieprogramma uit (**NDESConnectorSetup.exe**). Via het installatieprogramma wordt ook de beleidsmodule voor NDES en de webservice Certificaatregistratiepunt (CRP) van IIS geïnstalleerd. De webservice CRP, *CertificateRegistrationSvc*, wordt als een toepassing in IIS uitgevoerd.

      Wanneer u NDES installeert en Intune zelfstandig wordt gebruikt, wordt de CRP-service automatisch met de certificaatconnector geïnstalleerd.

5. Wanneer om het clientcertificaat voor de Certificate Connector wordt gevraagd, kiest u **Selecteren** en selecteert u het **clientverificatiecertificaat** dat u op uw NDES-server hebt geïnstalleerd tijdens stap 3 van de procedure [Certificaten installeren en verbinden op de server waarop NDES wordt gehost](#install-and-bind-certificates-on-the-server-that-hosts-ndes) die eerder in dit artikel is beschreven.

   Nadat u het clientverificatiecertificaat hebt geselecteerd, wordt u teruggevoerd naar het gebied **Clientcertificaat voor Microsoft Intune Certificate Connector**. Hoewel het certificaat dat u hebt geselecteerd niet wordt weergegeven, selecteert u **Volgende** om de eigenschappen van dat certificaat weer te geven. Selecteer **Volgende** en vervolgens **Installeren**.

> [!NOTE]
> De volgende wijzigingen moeten worden aangebracht voor GCC High-tenants voordat de Intune Certificate Connector wordt gestart.
> 
> Breng wijzigingen aan in de twee onderstaande configuratiebestanden, waarmee de service-eindpunten voor de GCC High-omgeving worden bijgewerkt. U ziet dat door deze updates de URI van het achtervoegsel **.com** in het achtervoegsel **.us** wordt gewijzigd. Er zijn in totaal drie URI-updates, twee updates in het configuratiebestand NDESConnectorUI.exe. config en één update in het bestand NDESConnector.exe.config.
> 
> - Bestandsnaam: <install_Path>\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.config
> 
>   Voorbeeld: (%programfiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.config)
>   ```
>    <appSettings>
>        <add key="SignInURL" value="https://portal.manage.microsoft.us/Home/ClientLogon"/>
>        <add key="LocationServiceEndpoint" value="RestUserAuthLocationService/RestUserAuthLocationService/ServiceAddresses"/>
>        <add key="AccountPortalURL" value="https://manage.microsoft.us"/>
>    </appSettings>
>   ```
> 
> - Bestandsnaam: <install_Path>\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config
>
>   Voorbeeld: (%programfiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config)
>    ```
>    <appSettings>
>        <add key="BaseServiceAddress" value="https://manage.microsoft.us/" />
>    ```
>
> Als deze bewerkingen niet worden voltooid, krijgt GCC High-tenants de volgende fout: "Toegang geweigerd" "U bent niet gemachtigd om deze pagina weer te geven"

6. Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

   Als u de wizard sluit voordat u de gebruikersinterface van Certificate Connector start, kunt u deze opnieuw openen door de volgende opdracht uit te voeren:

   *<install_Path>\NDESConnectorUI\NDESConnectorUI.exe*

7. In de gebruikersinterface van de **certificaatconnector** :

   1. Selecteer **Aanmelden** en voer uw Intune-servicebeheerder- of tenantbeheerderreferenties met de machtiging voor algemeen beheer in.

   2. Aan het account dat u gebruikt moet een geldige Intune-licentie zijn toegewezen.

   3. Nadat u zich hebt aangemeld, wordt door de Intune Certificate Connector een certificaat van Intune gedownload. Dit certificaat wordt gebruikt voor verificatie tussen de connector en Intune. Als het account dat u hebt gebruikt geen Intune-licentie heeft, kan het certificaat niet uit Intune worden opgehaald door de connector (NDESConnectorUI. exe).  

      Als uw organisatie een proxyserver gebruikt en de NDES-server de proxy nodig heeft om toegang tot internet te krijgen, selecteert u **Proxyserver gebruiken**. Voer vervolgens de naam van de proxyserver, de poort en de accountreferenties in om verbinding te maken.

   4. Selecteer het tabblad **Geavanceerd** en voer vervolgens referenties in voor een account met de machtiging **Certificaten verlenen en beheren** op uw verlenende certificeringsinstantie. **Pas** de wijzigingen toe.  

    5. U kunt nu de gebruikersinterface van de certificaatconnector sluiten.

8. Open een opdrachtprompt, voer **services.msc** in en druk vervolgens op **Enter**. Klik met de rechtermuisknop op de **Intune-connectorservice** > **Opnieuw opstarten**.

Controleer of de service wordt uitgevoerd door een browser te openen en de volgende URL in te voeren. Dan wordt er een **403**-fout geretourneerd: `https://<FQDN_of_your_NDES_server>/certsrv/mscep/mscep.dll`

> [!NOTE]
> De Intune Certificate Connector ondersteunt TLS 1.2. Als de server waarop de connector wordt gehost TLS 1.2 ondersteunt, wordt TLS 1.2 gebruikt. Als de server TLS 1.2 niet ondersteunt, wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

## <a name="next-steps"></a>Volgende stappen

[Een SCEP-certificaatprofiel maken](certificates-profile-scep.md)  
[Problemen met de Intune Certificate Connector oplossen](troubleshoot-certificate-connector-events.md)
