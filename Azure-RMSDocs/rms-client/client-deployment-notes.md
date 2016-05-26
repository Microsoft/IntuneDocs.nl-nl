---
# required metadata

title: Notities bij de implementatie van de RMS-client | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 03cc8c6f-3b63-4794-8d92-a5df4cdf598f

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Notities bij de implementatie van de RMS-client

*Van toepassing op: Active Directory Rights Management Services, Azure Rights Management, Windows 7 met SP1, Windows 8, Windows 8.1, Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, Windows Vista*

Versie 2 van de Rights Management Service-client (RMS-client) is ook bekend als de MSIPC-client. Deze software voor Windows-computers communiceert met Microsoft Rights Management-services on-premises of in de cloud voor beveiliging van de toegang tot en het gebruik van informatie wanneer deze informatie wordt gebruikt door toepassingen en apparaten binnen de grenzen van uw organisatie, of buiten deze beheerde grenzen. De RMS-client wordt geleverd bij de [Rights Management-toepassing voor delen voor Windows](sharing-app-windows.md), maar is ook beschikbaar [als optionele download](http://www.microsoft.com/download/details.aspx?id=38396) die, met bevestiging en instemming van de gebruiksrechtovereenkomst, vrijelijk kan worden gedistribueerd bij software van derden zodat clients inhoud kunnen beveiligen en verbruiken die wordt beveiligd door Rights Management-services.


## De RMS-client opnieuw distribueren
De RMS-client kan vrijelijk opnieuw worden gedistribueerd en gebundeld met andere toepassingen en IT-oplossingen. Als u ontwikkelaar van toepassingen of oplossingsprovider bent en de RMS client opnieuw wilt distribueren, hebt u twee mogelijkheden:

-   Aanbevolen: sluit het installatieprogramma van de RMS-client in de installatie van de toepassing in en voer deze in stille modus uit (de schakelaar **/quiet**, zoals omschreven in de volgende sectie).

-   Maak de RMS-client een vereiste voor de toepassing. Met deze optie moet u gebruikers mogelijk aanvullende instructies bieden waarmee ze de client kunnen verkrijgen en installeren en hun computers met de client kunnen bijwerken voordat ze uw toepassingen kunnen gebruiken.

## De RMS-client installeren
De RMS-client is opgenomen in een uitvoerbaar installatiebestand met de naam **setup_msipc_***<arch>***.exe**, waarbij het *<arch>* bestand **x86** (voor 32 bitsclientcomputers) of **x64** (voor 64 bitsclientcomputers) is. Met het 64 bitsinstallatiepakket (x64) wordt zowel een uitvoerbaar bestand voor de 32 bitsruntime geïnstalleerd voor compatibiliteit met 32 bitstoepassingen die op een 64 bitsbesturingssysteem worden uitgevoerd als een uitvoerbaar bestand voor de 64 bitsruntime voor ondersteuning van systeemeigen 64 bitstoepassingen. Het 32-bits (x86) installatieprogramma kan niet worden uitgevoerd op een 64-bits Windows-installatie.

> [!NOTE]
> U moet verhoogde bevoegdheden hebben voor het installeren van de RMS-client, bijvoorbeeld zoals een lid van de groep Administrators op de lokale computer.

U kunt de RMS-client installeren via een van de volgende installatiemethoden:

-   **Stille modus.** Met de schakelaar **/quiet** als onderdeel van de opdrachtregelmogelijkheden kunt u de RMS-client op de achtergrond op computers installeren. Het volgende voorbeeld toont een installatie in stille modus voor de RMS-client op een 64 bitsclientcomputer:

    ```
    setup_msipc_x64.exe /quiet
    ```

-   **Interactieve modus.** U kunt de RMS-client ook installeren met het installatieprogramma op basis van een GUI die wordt geleverd door de installatiewizard van de RMS-client. Hiervoor dubbelklikt u op het installatiepakket van de RMS-client (**setup_msipc_***<arch>***.exe**) in de map waarnaar deze is gekopieerd of gedownload op uw lokale computer.

## Vragen en antwoorden over de RMS-client
De volgende sectie bevat veelgestelde vragen en de antwoorden over de RMS-client

### Welke besturingssystemen ondersteunen de RMS-client?
De RMS-client wordt ondersteund op de volgende besturingssystemen:

|Windows Server-besturingssysteem|Windows Client-besturingssysteem|
|-----------------------------------|-----------------------------------|
|Windows Server 2012 R2|Windows 8.1|
|Windows Server 2012|Windows 8|
|Windows Server 2008 R2|Windows 7 met ten minste SP1|
|Windows Server 2008 (alleen AD RMS)|Windows Vista met ten minste SP2 (alleen AD RMS)|

### Welke processoren of platformen ondersteunen de RMS-client?
De RMS-client wordt ondersteund op x86- en x64-platformen.

### Waar wordt de RMS-client geïnstalleerd?
De RMS-client wordt standaard geïnstalleerd in %ProgramFiles%\Active Directory Rights Management Services Client 2.<minor version number>.

### Welke bestanden zijn gekoppeld aan de RMS-clientsoftware?
De volgende bestanden worden geïnstalleerd als onderdeel van de RMS-clientsoftware:

-   Msipc.dll

-   Ipcsecproc.dll

-   Ipcsecproc_ssp.dll

-   MSIPCEvents.man

Naast deze bestanden installeert de RMS-client ook ondersteuningsbestanden met een meertalige gebruikersinterface (MUI) in 44 talen. Als u de ondersteunde talen wilt controleren, voert u de RMS-clientinstallatie uit en bekijkt u de inhoud van de meertalige ondersteuningsmappen onder het standaardpad nadat de installatie is voltooid.

### Is de RMS-clientsoftware opgenomen in de standaardinstelling wanneer ik een ondersteund besturingssysteem installeer?
Nee. Nee. Deze versie van de RMS-client wordt als een optionele download verzonden die apart kan worden geïnstalleerd op computers waarop ondersteunde versies van het Microsoft Windows-besturingssysteem worden uitgevoerd.

### Wordt de RMS-client automatisch bijgewerkt met Microsoft Update?
Als u deze RMS-client hebt geïnstalleerd met de optie voor installatie op de achtergrond, neemt de RMS-client de huidige instellingen voor Microsoft Update over. Als u de RMS-client hebt geïnstalleerd met het installatieprogramma op basis van een GUI, wordt u door de installatiewizard van de RMS-client gevraagd of u Microsoft Update wilt inschakelen.

## RMS-clientinstellingen
De volgende sectie bevat informatie over RMS-clientinstellingen: Deze informatie kan nuttig zijn als zich problemen voordoen met toepassingen of services die de RMS-client gebruiken.

> [!NOTE]
> Voor sommige instellingen is het van belang of de toepassing met RMS-functionaliteit wordt uitgevoerd als clientmodustoepassing (zoals Microsoft Word en Outlook of de RMS-toepassing voor delen) of als servermodustoepassing (zoals SharePoint en Exchange).  In de volgende tabellen zijn deze instellingen respectievelijk geïdentificeerd als **clientmodus** en **servermodus**.

### Waar de RMS-client licenties opslaat op clientcomputers
Met de RMS-client worden licenties opgeslagen op de lokale schijf en bepaalde gegevens worden ook opgeslagen in het Windows-register.

|Beschrijving|Clientmoduspaden|Servermoduspaden|
|---------------|---------------------|---------------------|
|Licentieopslaglocatie|%localappdata%\Microsoft\MSIPC|%allusersprofile%\Microsoft\MSIPC\Server\*<SID>*\|
|Archieflocatie sjabloon|%localappdata%\Microsoft\MSIPC\Templates|%allusersprofile%\Microsoft\MSIPC\Server\Templates\*<SID>*\|
|Registerlocatie|HKEY_CURRENT_USER<br /> \Software<br /> \Classes<br /> \Local Settings<br /> \Software<br /> \Microsoft<br /> \MSIPC|HKEY_CURRENT_USER<br /> \Software<br /> \Microsoft<br /> \MSIPC<br /> \Server<br /> \*<SID>*|
> [!NOTE]
> *<SID>* is de beveiligings-id (SID) van het account waarmee de servertoepassing wordt uitgevoerd. Als de toepassing bijvoorbeeld wordt uitgevoerd onder het ingebouwde netwerkserviceaccount, vervangt u *<SID>* door de waarde van de bekende SID voor dat account (S-1-5-20).

### Windows-registerinstellingen voor de RMS-client
U kunt de Windows-registersleutels gebruiken om enkele RMS-client-configuraties in te stellen of wijzigen. Als beheerder van toepassingen met RMS-functionaliteit die communiceren met AD RMS-servers, wilt u mogelijk de locatie van de enterpriseservice bijwerken (de geselecteerde AD RMS-server overschrijven die momenteel is geselecteerd voor publiceren), afhankelijk van de huidige locatie van de clientcomputer binnen uw Active Directory-topologie. Of mogelijk wilt u AD RMS-tracering inschakelen op de clientcomputer om een probleem met een toepassing met RMS-functionaliteit op te lossen. Gebruik de volgende tabel om de registerinstellingen te identificeren die u voor de RMS-client kunt wijzigen.

|Taak|Instellingen|
|--------|------------|
|Alleen voor AD RMS:de servicelocatie van de onderneming voor een clientcomputer bijwerken|Update de volgende registersleutels:<br /><br />HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterpriseCertification<br />REG_SZ: default<br /><br />**Waarde:**<http or https>:// *RMS_Cluster_Name*/_wmcs/Certification<br /><br />HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation\EnterprisePublishing<br />REG_SZ: default<br /><br />**Waarde:** <http or https>:// *RMS_Cluster_Name*/_wmcs/Licensing|
|Tracering in- en uitschakelen|Werk de volgende registersleutel bij:<br /><br />HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC<br />REG_DWORD: traceren<br /><br />**Waarden:** 1 tracering inschakelen, 0 tracering uitschakelen (standaard)|
|De frequentie in dagen voor het vernieuwen van sjablonen wijzigen|De volgende registerwaarden geven aan hoe vaak sjablonen worden vernieuwd op de computer van de gebruiker als de waarde TemplateUpdateFrequencyInSeconds niet is ingesteld.  Als geen van deze waarden is ingesteld, is het standaardvernieuwingsinterval voor het downloaden van sjablonen door toepassingen die de RMS-client (versie 1.0.1784.0) gebruiken, 1 dag. Eerdere versies hebben een standaardwaarde van elke 7 dagen.<br /><br />**Clientmodus:**<br /><br />HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />REG_DWORD: TemplateUpdateFrequency<br /><br />**Waarde:** een geheel getal dat het aantal dagen (minimaal 1) tussen downloads specificeert.<br /><br />**Servermodus:**<br /><br />HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*<SID>*<br />REG_DWORD: TemplateUpdateFrequency<br /><br />**Waarde:** een geheel getal dat het aantal dagen (minimaal 1) tussen downloads specificeert.|
|De frequentie in seconden voor het vernieuwen van sjablonen wijzigen<br /><br />Belangrijk: als deze waarde is opgegeven, wordt de waarde voor het vernieuwen van sjablonen in dagen genegeerd. Geef een van beide op, niet beide.|De volgende registerwaarden geven aan hoe vaak de sjablonen op de computer van de gebruiker worden bijgewerkt. Als deze waarde of de waarde voor het wijzigen van de frequentie in dagen (TemplateUpdateFrequency) niet is ingesteld, is het standaardvernieuwingsinterval voor het downloaden van sjablonen door toepassingen die de RMS-client (versie 1.0.1784.0) gebruiken, 1 dag. Eerdere versies hebben een standaardwaarde van elke 7 dagen.<br /><br />**Clientmodus:**<br /><br />HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />REG_DWORD: TemplateUpdateFrequencyInSeconds<br /><br />**Waarde:** een geheel getal dat het aantal seconden (minimaal 1) tussen downloads specificeert.<br /><br />**Servermodus:**<br /><br />HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\Server\*<SID>*<br />REG_DWORD: TemplateUpdateFrequencyInSeconds<br /><br />**Waarde:** een geheel getal dat het aantal dagen (minimaal 1) tussen downloads specificeert.|
|Alleen voor AD RMS: sjablonen direct downloaden na het volgende publicatieverzoek|Tijdens het testen en evalueren, wilt u de RMS-client mogelijk zo snel mogelijk sjablonen laten downloaden. Verwijder hiervoor de volgende registersleutel, zodat de RMS-client sjablonen direct downloadt na het volgende publicatieverzoek in plaats van te wachten op de tijd die door de registerinstelling TemplateUpdateFrequency is opgegeven.<br /><br />HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC\<Server Name>\Template<br /><br />**Opmerking**: <Server Name> kan zowel externe (corprights.contoso.com) als interne (corprights) URL's, en dus twee verschillende vermeldingen hebben.|
|Alleen voor AD RMS: ondersteuning voor Federated Authentication inschakelen|Als de RMS-clientcomputer verbinding maakt met een AD RMS-cluster met een federatieve vertrouwensrelatie, moet u het federatieve thuisdomein configureren.<br /><br />HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />REG_SZ: FederationHomeRealm<br /><br />**Waarde:** de waarde van deze registervermelding is de uniform resource identifier (URI) voor de Federation Service (bijvoorbeeld 'https://fs-01.contoso.com').|
|Alleen voor AD RMS: federatieve servers van partners ondersteunen waarvoor verificatie op basis van formulieren is vereist voor de gebruikersinvoer|De RMS-client wordt standaard in stille modus uitgevoerd en gebruikersinvoer is niet vereist. Federatieve servers van partners kunnen echter zijn geconfigureerd om gebruikersinvoer te vereisen zoals verificatie op basis van formulieren. In dat geval moet u de RMS-client configureren om de stille modus te negeren, zodat het Federated Authentication-formulier in een browservenster wordt weergegeven en de gebruiker om verificatie wordt gevraagd.<br /><br />HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\Federation<br />REG_DWORD: EnableBrowser<br /><br />**Opmerking**: als de federatieve server is geconfigureerd om verificatie op basis van formulieren te gebruiken, is deze sleutel vereist. Als de federatieve server is geconfigureerd om geïntegreerde verificatie van Windows te gebruiken dan is deze sleutel niet vereist.|
|Alleen voor AD RMS: ILS-servicegebruik blokkeren|Het gebruik van inhoud die wordt beveiligd door de ILS-service wordt standaard ingeschakeld door de RMS-client. U kunt de client kan echter zo configureren dat deze service wordt geblokkeerd door de volgende registersleutel in te stellen. Als deze registersleutel is ingesteld om ILS-service te blokkeren, wordt elke poging om inhoud die is beveiligd door de ILS-service te openen en te verbruiken, geretourneerd met de volgende fout:<br />HRESULT_FROM_WIN32(ERROR_ACCESS_DISABLED_BY_POLICY)<br /><br />HKEY_CURRENT_USER\Software\Classes\Local Settings\Software\Microsoft\MSIPC<br />REG_DWORD: **DisablePassportCertification**<br /><br />**Waarde:** 1 ILS-verbruik blokkeren, 0 ILS-verbruik toestaan (standaard)|

### Sjabloondistributie voor de RMS-client beheren
Met sjablonen kunnen gebruikers en beheerders eenvoudig en snel Rights Management-beveiliging toepassen. De RMS-client downloadt automatisch sjablonen van de RMS-servers of -service. Als u de sjablonen op de volgende maplocatie opslaat, downloadt de RMS-client geen sjablonen van de standaardlocatie, maar worden in plaats daarvan de sjablonen gedownload die in deze map hebt geplaatst. De RMS-client blijft mogelijk sjablonen van andere beschikbare RMS-servers downloaden.

**Clientmodus:** %localappdata%\Microsoft\MSIPC\UnmanagedTemplates

**Servermodus:** %allusersprofile%\Microsoft\MSIPC\Server\UnmanagedTemplates\*<SID>*

Wanneer u deze map gebruikt, is er geen speciale naamconventie vereist, behalve dat de sjablonen moeten worden uitgegeven door de RMS-server of -service en de bestandsextensie .xml moeten hebben. Geldige namen zijn bijvoorbeeld Contoso-Confidential.xml of Contoso-ReadOnly.xml.

## Alleen voor AD RMS: de RMS-client beperken tot het gebruik van vertrouwde AD RMS-servers
De RMS-client kan worden beperkt tot het gebruik van alleen specifieke vertrouwde AD RMS-servers door de volgende wijzigingen aan te brengen in het Windows-register.

**De RMS-client beperken tot het gebruik van alleen vertrouwde AD RMS-servers**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_DWORD: AllowTrustedServersOnly

    **Waarde:** als een andere waarde dan nul is opgegeven, vertrouwt de RMS-client alleen de opgegeven servers die zijn geconfigureerd in de lijst TrustedServers en de Azure Rights Management-service.

**Leden toevoegen aan de lijst met vertrouwde AD RMS-servers**

-   HKEY_LOCAL_MACHINE\Software\Microsoft\MSIPC\TrustedServers\
    REG_SZ: *<URL_or_HostName>*

    **Waarde:** de tekenreekswaarden in deze registersleutellocatie kunnen de naamindeling van een DNS-domein hebben (bijvoorbeeld **adrms.contoso.com**) of volledige URL's naar vertrouwde AD RMS-servers hebben (bijvoorbeeld **https://adrms.contoso.com**). Als een opgegeven URL begint met **https://**, gebruikt de RMS-client SSL of TLS om contact op te nemen met de opgegeven AD RMS-server.

## Detectie van RMS-services
Met RMS-servicedetectie kan de RMS-client controleren welke RMS-server of -service moet communiceren voordat inhoud wordt beveiligd. Servicedetectie kan ook optreden als de RMS-client beveiligde inhoud verbruikt, maar dit is minder waarschijnlijk, omdat het beleid dat is gekoppeld aan de inhoud de voorkeur RMS-server of -service bevat. Alleen als dat niet werkt, voert de client servicedetectie uit.

Servicedetectie zoekt eerst naar een on-premises versie van Rights Management (AD RMS). Als dat niet werkt, zoekt servicedetectie automatisch naar de cloudversie van Rights Management (Azure RMS).

De RMS-client controleert het volgende om servicedetectie voor een on-premises implementatie uit te voeren:

1.  Het Windows-register op de lokale computer: als servicedetectie-instellingen zijn geconfigureerd in het register, worden deze instellingen eerst geprobeerd.  Deze instellingen zijn standaard niet geconfigureerd in het register.

2.  Active Directory Domain Services: een computer in het domein zoekt in Active Directory naar een serviceaansluitpunt (SCP). Als een SCP is geregistreerd, wordt de URL van de RMS-server voor gebruik naar de RMS-client geretourneerd.

### Alleen voor AD RMS: servicedetectie op de server inschakelen met Active Directory
Als het account over voldoende bevoegdheden beschikt (Ondernemingsadministrators en lokale beheerder voor de AD RMS-server), kunt u automatisch een serviceaansluitpunt (SCP) registreren tijdens de installatie van de AD RMS-basisclusterserver. Als in het forest al een SCP bestaat, moet u eerst het bestaande SCP verwijderen voordat u een nieuw SCP kunt registreren.

U kunt een SCP registreren en verwijderen na de installatie van AD RMS met de volgende procedure. Voordat u begint, controleert u of uw account de vereiste bevoegdheden (Ondernemingsadministrators en lokale beheerder voor de AD RMS-server) beschikt.

#### AD RMS-servicedetectie kan worden ingeschakeld door een SCP in Active Directory te registreren

1.  Open de console Active Directory Management Services op de AD RMS-server:

    -   Doe het volgende als u Windows Server 2008 R2 of Windows Server 2008 gebruikt: klik op **Start**, klik op **Systeembeheer** en klik vervolgens op **Active Directory Rights Management Services**.

    -   Doe het volgende als u Windows Server 2012 R2 of Windows Server 2012 gebruikt: klik in Serverbeheer op **Extra** en klik vervolgens op **Active Directory Rights Management Services**.

2.  Klik met de rechtermuisknop in het AD RMS-cluster en klik vervolgens op **Eigenschappen**.

3.  Klik op het tabblad **SCP**.

4.  Selecteer het selectievakje **SCP wijzigen**.

5.  Selecteer de optie **SCP instellen op huidig certificeringscluster** en klik vervolgens op **OK**.

### Servicedetectie aan de clientzijde inschakelen met het Windows-register
Als alternatief voor het gebruik van een SCP of wanneer er geen SCP bestaat, kunt u het register op de clientcomputer configureren zodat de RMS-client de AD RMS-server kan vinden.

#### AD RMS-servicedetectie aan clientzijde inschakelen met het Windows-register

1.  Open de Register-editor van Windows, Regedit.exe.

    -   Typ op de clientcomputer in het venster Uitvoeren **regedit** en druk vervolgens op Enter om de Register-editor te openen.

2.  In de Register-editor gaat u naar **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC**.

    > [!IMPORTANT]
    > Als u een 32 bitstoepassing op een 64 bitscomputer uitvoert, is het pad als volgt: 
    > **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC**

3.  Als u de ServiceLocation-subsleutel wilt maken, klikt u met de rechtermuisknop op **MSIPC**, wijst u **Nieuw** aan, klikt u op **Sleutel** en typt u vervolgens **ServiceLocation**.

4.  Als u de EnterpriseCertification-subsleutel wilt maken, klikt u met de rechtermuisknop op **ServiceLocation**, wijst u **Nieuw** aan, klikt u op **Sleutel** en typt u vervolgens **EnterpriseCertification**.

5.  Doe het volgende als u de URL voor ondernemingscertificering wilt instellen: dubbelklik op de waarde **(Standaard)** onder de subsleutel **EnterpriseCertification**. Als het dialoogvenster **Tekenreeks bewerken** wordt weergegeven, typt u voor **Waardegegevens** <http or https>://*AD RMS_cluster_name*/_wmcs/Certification en klikt u vervolgens op **OK**.

6.  Als u de EnterprisePublishing-subsleutel wilt maken, klikt u met de rechtermuisknop op **ServiceLocation**, wijst u **Nieuw** aan, klikt u op **Sleutel** en typt u vervolgens EnterprisePublishing.

7.  Doe het volgende als u de URL voor ondernemingspublicatie wilt instellen: dubbelklik op **(Standaard)** onder de subsleutel **EnterprisePublishing**. Als het dialoogvenster **Tekenreeks bewerken** wordt weergegeven, typt u voor **Waardegegevens** <http or https>://*AD RMS_cluster_name*/_wmcs/Licensing en klikt u vervolgens op **OK**.

8.  Sluit de Register-editor af.

Als de RMS-client geen SCP kan vinden in Active Directory en deze niet is opgegeven in het register, mislukken servicedetectieaanroepen voor AD RMS.

### Licentieserververkeer omleiden
In sommige gevallen moet u mogelijk verkeer omleiden tijdens servicedetectie, bijvoorbeeld wanneer twee organisaties worden samengevoegd en de oude licentieserver in een organisatie buiten gebruik wordt gesteld en de clients moeten worden omgeleid naar een nieuwe licentieserver. Of u migreert van AD RMS naar Azure RMS. Gebruik de volgende procedure om licentie-omleiding in te schakelen.

#### Omleiden van RMS-licentieverlening inschakelen met het Windows-register

1.  Open de Register-editor van Windows, Regedit.exe.

    -   Typ op de clientcomputer in het venster Uitvoeren **regedit** en druk vervolgens op Enter om Register-editor te openen.

2.  Navigeer in de Register-editor naar een van de volgende locaties:

    -   Voor een 64 bitsversie van Office op een x64-platform: HKLM\SOFTWARE\Microsoft\MSIPC\Servicelocation

    -   Voor een 32 bitsversie van Office op een x64-platform: HKLM\SOFTWARE\Wow6432Node\Microsoft\MSIPC\Servicelocation

3.  Maak een subsleutel LicensingRedirection door met de rechtermuisknop te klikken op **ServiceLocation**, wijs **Nieuw** aan, klik op **Sleutel** en typ vervolgens **LicensingRedirection**.

4.  Stel de licentie-omleiding in door met de rechtermuisknop te klikken op de subsleutel **LicensingRedirection**, selecteer **Nieuw** en selecteer vervolgens **Waarde tekenreeks**.  Geef voor **Naam** de URL van de vorige serverlicentie op en geef voor **Waarde** de URL van de nieuwe serverlicentie op.

    Als u bijvoorbeeld licenties wilt omleiden van een server op Contoso.com naar een server op Fabrikam.com, kunt u de volgende waarden invoeren:

    **Naam:** https://contoso.com/_wmcs/licensing

    **Waarde:** https://fabrikam.com/_wmcs/licensing

    > [!NOTE]
    > Als voor de oude licentieserver URL's voor intranet en extranet zijn opgegeven dan moet een nieuwe naam- en waardetoewijzing worden ingesteld voor beide URL's onder de LicensingRedirection-sleutel.

5.  Herhaal de vorige stap voor alle servers die moeten worden omgeleid.

6.  Sluit de Register-editor af.



<!--HONumber=May16_HO1-->


