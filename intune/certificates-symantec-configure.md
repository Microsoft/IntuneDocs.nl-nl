---
title: PKCS-certificaten van Symantec uitgeven met Microsoft Intune
titlesuffix: ''
description: U kunt Intune Certificate Connector installeren en configureren om PKCS-certificaten van een Symantec PKI Manager-webservice uit te geven aan met Intune beheerde apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d9c9027964648ad83c552f7dd7067598cacf560e
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31836522"
---
# <a name="set-up-intune-certificate-connector-for-symantec-pki-manager-web-service"></a>Intune Certificate Connector instellen voor de Symantec PKI Manager-webservice

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel wordt uitgelegd hoe u Intune Certificate Connector installeert en configureert om PKCS-certificaten van een Symantec PKI Manager-webservice uit te geven aan met Intune beheerde apparaten.

In dit artikel wordt naar de Symantec PKI Manager-webservice verwezen als de Symantec-CA. Als u Intune Certificate Connector al hebt geconfigureerd om PKCS-certificaten en SCEP-certificaten van de Microsoft-certificeringsinstantie (CA) uit te geven, kan de dezelfde connector worden gebruikt om PKCS-certificaten van een Symantec-CA te configureren en uit te geven. In dit geval kan Intune Certificate Connector de volgende certificaten uitgeven:

* PKCS-certificaten van een Microsoft-CA
* SCEP-certificaten van een Microsoft-CA
* PKCS-certificaten van een Symantec-CA

Als u Intune Certificate Connector voor Microsoft-CA en Symantec-CA wilt gebruiken, moet u eerst de configuratie van Intune Certificate Connector voor de Microsoft-CA voltooien en vervolgens deze stappen uitvoeren om de connector te configureren voor de Symantec-CA.  Zie [Certificaten configureren in Microsoft Intune](certificates-configure.md) voor meer informatie over het configureren van Intune Certificate Connector voor een Microsoft-CA.

## <a name="prepare-to-install-intune-certificate-connector"></a>De installatie van Microsoft Intune Certificate Connector voorbereiden

Als u Intune Certificate Connector al gebruikt voor een bestaande Microsoft-CA en ondersteuning voor Symantec-CA wilt toevoegen, slaat u deze stap over en gaat u verder met de resterende stappen nadat u de meest recente versie van Intune Certificate Connector hebt geïnstalleerd vanuit de Intune Admin-portal. Deze stap is alleen vereist als u Intune Certificate Connector wilt gebruiken voor een zelfstandige Symantec-CA.

1. Kies een van de versies van het Windows-besturingssysteem in de onderstaande lijst en installeer deze op een computer:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Maak een gebruiker met beheerdersbevoegdheden en gebruik deze om de volgende stappen uit te voeren.

3. Installeer de meest recente Windows-updates.

   > [!IMPORTANT]
   > Start de computer opnieuw op nadat u de Windows-updates hebt geïnstalleerd.

4. Installeer .NET Framework 3.5:

    a. Open **Configuratiescherm** > **Programma's en onderdelen** > **Windows-onderdelen in- of uitschakelen**.

    b. Selecteer **.NET Framework 3.5** en installeer dit.

## <a name="install-the-symantec-registration-authorization-certificate"></a>Het Symantec-certificaat voor registratie-autorisatie installeren

Gebruik de volgende stappen om het RA-certificaat (registratie-autorisatie) van de Symantec-CA op te halen. U moet een actief abonnement op de Symantec-CA hebben om het RA-certificaat te kunnen ophalen.

1. Sla het volgende codefragment op in een bestand genaamd **certreq.ini** en werk dit bij zoals vereist (bijvoorbeeld: *onderwerpnaam in CN-indeling*).

   ```
    [Version] 
    Signature="$Windows NT$" 

    [NewRequest] 
    ;Change to your,country code, company name and common name 
    Subject = "Subject Name in CN format"

    KeySpec = 1 
    KeyLength = 2048 
    Exportable = TRUE 
    MachineKeySet = TRUE 
    SMIME = False 
    PrivateKeyArchive = FALSE 
    UserProtected = FALSE 
    UseExistingKeySet = FALSE 
    ProviderName = "Microsoft RSA SChannel Cryptographic Provider" 
    ProviderType = 12 
    RequestType = PKCS10 
    KeyUsage = 0xa0 

    [EnhancedKeyUsageExtension] 
    OID=1.3.6.1.5.5.7.3.2 ; Client Authentication  // Uncomment if you need a mutual TLS authentication

    ;----------------------------------------------- 
   ```

2. Open een opdrachtprompt met verhoogde bevoegdheid en genereer CSR-inhoud met de volgende opdracht:

   `Certreq.exe -new certreq.ini request.csr`

3. Open het bestand request.csr in Kladblok en kopieer de CSR-inhoud in de volgende indeling:

    ```
    -----BEGIN NEW CERTIFICATE REQUEST-----
    MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
    …
    …
    fzpeAWo=
    -----END NEW CERTIFICATE REQUEST-----
    ```

4. Meld u aan bij de Symantec-CA en navigeer naar **Get an RA Cert** via de taken.

   a. Geef de CSR-inhoud uit stap 3 op in het desbetreffende tekstvak.

   b. Geef de beschrijvende naam voor het certificaat op in het desbetreffende tekstvak.

   c. Klik op **Continue**.

      Er wordt een downloadbare koppeling voor het RA-certificaat weergegeven.

   d. Download het RA-certificaat naar de lokale computer.

5. Het RA-certificaat importeren in het Windows-certificaatarchief:

    a. Open een MMC-console.

    b. Klik op **Bestand** > **Modules toevoegen of verwijderen** > **Certificaat** en klik vervolgens op **Toevoegen**.

    c. Selecteer **Computeraccount** en klik daarna op **Volgende**.

    d. Selecteer **Lokale computer** en klik op **Voltooien**.

    e. Klik op **OK** in het venster **Modules toevoegen of verwijderen**. Vouw **Certificaten (lokale computer)** > **Persoonlijk** > **Certificaten** uit.

    f. Klik met de rechtermuisknop op het knooppunt **Certificaten** en selecteer **Alle taken** > **Importeren**.

    g. Selecteer de locatie van het RA-certificaat dat u hebt gedownload van de Symantec-CA en klik op **Volgende**.

    h. Selecteer **Persoonlijk certificaatarchief** en klik op **Volgende**.

    i. Klik op **Voltooien**. Het RA-certificaat wordt geïmporteerd in het persoonlijke archief op de lokale computer, samen met de persoonlijke sleutel.  

6. Het certificaat met persoonlijke sleutel exporteren en importeren:

    a. Vouw **Certificaten (lokale computer)** > **Persoonlijk** > **Certificaten** uit.

    b. Selecteer het certificaat dat is geïmporteerd in de vorige stap.

    c. Klik met de rechtermuisknop op het certificaat en kies **Alle taken** > **Exporteren**.

    d. Klik op **Volgende** en typ het wachtwoord.

    e. Selecteer de locatie waarnaar u wilt exporteren en klik op **Voltooien**.

    f. Volg dezelfde procedure in stap 5 om het certificaat met persoonlijke sleutel te importeren in het persoonlijke archief op de lokale computer.

7. Kopieer de vingerafdruk van het RA-certificaat zonder spaties.  Hier volgt een voorbeeld van een vingerafdruk:

   ```
   RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
   ```


   > [!NOTE]
   > Als er problemen zijn met het ophalen van het RA-certificaat bij de Symantec-CA, neemt u contact op met de klantenondersteuning van Symantec.

## <a name="install-intune-certificate-connector"></a>Microsoft Intune Certificate Connector installeren

Als u de meest recente versie van Intune Certificate Connector al gebruikt voor een bestaande Microsoft-CA en ondersteuning voor de Symantec-CA wilt toevoegen, kunt u deze stap overslaan. Download anders de meest recente versie van Intune Certificate Connector van de Intune-beheerportal en volg deze instructies.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
4. Selecteer in het deelvenster **Apparaatconfiguratie** de optie **Certificeringsinstantie**.
5. Klik op **Toevoegen** en selecteer **Connectorbestand downloaden**. Sla het bestand op in een locatie waar u het kunt openen vanaf de server waarop u de connector gaat installeren. 
3. Voer NDESConnectorSetup.exe uit met verhoogde bevoegdheden.

    a. Selecteer in het scherm **Installatieopties** de optie **PFX-distributie** zoals weergegeven in de volgende schermopname.  Voltooi de overige instellingen met de standaardselecties.

   > [!IMPORTANT]
   > Als u wilt dat Intune Certificate Connector certificaten uitgeeft van een Microsoft-CA en een Symantec-CA, selecteert u **SCEP- en PFX-profieldistributie**. Voltooi de overige instellingen met de standaardselecties.

   ![InstallConnector][InstallConnector]
 
## <a name="configure-intune-certificate-connector"></a>Intune Certificate Connector configureren

Intune Certificate Connector wordt standaard geïnstalleerd op `%ProgramFiles%\Microsoft Intune`.

1. Open het bestand %ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config in Kladblok.

    a. Werk de waarde van de sleutel RACertThumbprint bij met de waarde van de vingerafdruk van het certificaat die u in het vorige gedeelte hebt gekopieerd.  Hier volgt een voorbeeld:

   ```
   <add key="RACertThumbprint"
   value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   ```

    b. Sla het bestand op en sluit het.

2. Open services.msc.

    a. Selecteer **Intune-connectorservice**.

    b. Stop de service en start de service weer.

    c. Sluit het venster Services.

## <a name="setup-the-intune-administrator-account"></a>Het Intune-beheerdersaccount instellen

Als u Intune Certificate Connector al gebruikt voor een bestaande Microsoft-CA en ondersteuning voor de Symantec-CA wilt toevoegen, slaat u deze stap over en gaat u verder met de overige stappen. 

1. De interface van NDES Connector starten vanuit ` %ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe `

    a. Klik op het tabblad **Inschrijving** en klik vervolgens op **Aanmelden**.

    b. Geef uw beheerdersreferenties voor de Intune-tenant op in de desbetreffende tekstvakken.

    c. Klik op **Aanmelden**.  Er verschijnt een bevestigingsvenster met het bericht **Ingeschreven** zoals in de volgende schermopname.
2. Sluit de gebruikersinterface van NDES Connector.

![ConfigureConnector][ConfigureConnector]
 
## <a name="create-a-trusted-certificate-profile"></a>Een vertrouwd certificaatprofiel maken

De PKCS-certificaten die worden geïmplementeerd voor met Intune beheerde apparaten, moeten worden gekoppeld met een vertrouwd basiscertificaat. Hiervoor moet u een vertrouwd certificaatprofiel voor Intune maken met het basiscertificaat dat is verkregen van de Symantec-CA.

1. Een vertrouwd basiscertificaat ophalen van de Symantec-CA:

    a. Meld u aan bij de beheerportal van de Symantec CA.

    b. Klik op Manage CAs bij Tasks:

    c. Selecteer de juiste CA in de lijst met CA's.

    d. Klik op Download root certificate om het vertrouwde basiscertificaat te downloaden.

2. Een vertrouwd certificaatprofiel maken in de Intune-beheerportal:

    a. Meld u met uw beheerdersreferenties voor de Intune-tenant aan bij [Azure Portal](https://portal.azure.com) en zoek naar Intune-resources.

    b. Maak van een vertrouwd certificaatprofiel via **Microsoft Intune** > **Apparaatconfiguratie** > **Profielen**  >   **Profiel maken**.

    c. Geef de vereiste gegevens op in de velden **Naam** en **Beschrijving** en selecteer vervolgens het doelplatform. 

    d. Kies het vertrouwde basiscertificaat in de vervolgkeuzelijst Profieltype.

    e. Upload het vertrouwde basiscertificaat dat u in de vorige stap van de Symantec-CA hebt gekregen.

    f. Voltooi de resterende stappen om het profiel te maken. 

    g. Klik op **Toewijzingen** en selecteer de gewenste groep.  Ten minste één gebruiker of apparaat moet deel uitmaken van de toegewezen groep.

## <a name="get-the-certificate-profile-oid"></a>De certificaatprofiel-OID ophalen

De OID van het certificaatprofiel is gekoppeld aan een certificaatprofielsjabloon in de Symantec-CA.  Als u een PKCS-certificaatprofiel wilt maken in de Intune-beheerportal, moet u de naam van de certificaatsjabloon opgeven in de vorm van een certificaatprofiel-OID die gekoppeld aan een certificaatsjabloon in de Symantec-CA.

1. Meld u aan bij de beheerportal van de Symantec-CA.
2. Klik op Certificaatprofielen beheren.
3. Selecteer het certificaatprofiel dat u wilt gebruiken.
4. Kopieer de OID van het certificaatprofiel. Deze ziet er ongeveer uit zoals in het volgende voorbeeld:

   ```
   Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
   ```

   > [!NOTE]
   > Als er problemen zijn met het verkrijgen van de OID van het certificaatprofiel, neemt u contact op met de klantenondersteuning van Symantec.

## <a name="create-a-pkcs-certificate-profile"></a>Een PKCS-certificaatprofiel maken

1. Meld u met uw beheerdersreferenties voor de Intune-tenant aan bij [Azure Portal](https://portal.azure.com) en zoek naar Intune-resources.
2. Maak van een PKCS-certificaatprofiel via **Microsoft Intune** > **Apparaatconfiguratie > Profielen** > **Profiel maken**.

    a. Geef de vereiste gegevens op in de velden **Naam** en **Beschrijving** en selecteer vervolgens het doelplatform.

    b. Selecteer **PKCS-certificaatprofiel** in de vervolgkeuzelijst **Profieltype**.  

    c. Voltooi de resterende stappen om het profiel te maken.

   ![ConfigureProfile][ConfigureProfile]

   > [!IMPORTANT]
   > De volgende parameters van het PKCS-certificaatprofiel moeten worden geconfigureerd met de opgegeven waarden in de volgende tabel, zoals weergegeven in de schermafbeelding, om PKCS-certificaten van de Symantec-CA te kunnen uitgeven via Intune Certificate Connector. 

    |Parameter van PKCS-certificaat | Waarde | Description |
    | --- | --- | --- |
    | Certificeringsinstantie | pki-ws.symauth.com | Deze waarde moet de FQDN van de basisservice van de Symantec-CA zijn, zonder afsluitende schuine strepen.  Als u niet zeker weet of dit is de juiste FQDN voor de basisservice voor uw Symantec-CA-abonnement is, neemt u contact op met de klantenondersteuning van Symantec. <br><br> Als deze FQDN onjuist is, geeft Intune Certificate Connector geen PKCS-certificaten van de Symantec-CA uit.| 
    | Naam van certificeringsinstantie | Symantec | Deze waarde moet de tekenreeks **Symantec** zijn. <br><br> Als deze waarde afwijkt, geeft Intune Certificate Connector geen PKCS-certificaten van de Symantec-CA uit.|
    | Naam van certificaatsjabloon | Certificaatsjabloon-OID van de Symantec-CA. <br><br> Bijvoorbeeld: `2.16.840.1.113733.1.16.1.2.3.1.1.61904612`| Deze waarde moet de certificaatprofiel-OID zijn die in het vorige gedeelte is verkregen van de certificaatprofielsjabloon van de Symantec-CA. <br><br> Als Intune Certificate Connector geen certificaatsjabloon kan vinden die is gekoppeld aan deze certificaatprofiel-OID in de Symantec-CA, worden geen PKCS-certificaten van de Symantec-CA uitgegeven.|

   > [!NOTE]
   > De PKCS-certificaatprofielen voor Windows-platforms hoeven niet te zijn gekoppeld aan een vertrouwd certificaatprofiel. Dit is echter wel vereist voor profielen voor andere platforms dan Windows, zoals Android.

3. Klik op **Toewijzingen** en selecteer de gewenste groep.  Ten minste één gebruiker of apparaat moet deel uitmaken van de toegewezen groep.
 
Nadat u de vorige stappen hebt voltooid, geeft Intune Certificate Connector PKCS-certificaten van de Symantec-CA uit voor met Intune beheerde apparaten in de toegewezen groep. Deze certificaten zijn beschikbaar in het persoonlijke archief van het certificaatarchief van de huidige gebruiker op het met Intune beheerde apparaat.

### <a name="pkcs-certificate-profile-supported-attributes"></a>Ondersteunde kenmerken van het PKCS-certificaatprofiel

|Kenmerk | Door Intune ondersteunde indelingen | Door Symantec Cloud-CA ondersteunde indelingen | Resultaat |
| --- | --- | --- | --- |
| Onderwerpnaam |Intune ondersteunt de onderwerpnaam in de volgende drie indelingen: <br><br> 1. Algemene naam <br> 2. Algemene naam en e-mailadres <br> 3. Algemene naam als e-mailadres <br><br> Hier volgt een voorbeeld: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | De Symantec-CA ondersteunt aanvullende kenmerken.  Als u aanvullende kenmerken wilt selecteren, moeten ze worden gedefinieerd met vaste waarden in de sjabloon voor het Symantec-certificaatprofiel.| We gebruiken Algemene naam of e-mailadres uit de PKCS-certificaataanvraag. <br><br> Als de geselecteerde kenmerken voor het Intune-certificaatprofiel en de sjabloon voor het Symantic-certificaatprofiel niet overeenkomen, worden er geen certificaten uitgegeven door de Symantec-CA.|
| SAN | Intune ondersteunt alleen de volgende waarden voor SAN-velden: <br><br> AltNameTypeEmail <br><br> AltNameTypeUpn <br><br> AltNameTypeOtherName (gecodeerde waarde) | De Symantec Cloud-CA ondersteunt deze parameters ook. Als u aanvullende kenmerken wilt selecteren, moeten ze worden gedefinieerd met vaste waarden in de sjabloon voor het Symantec-certificaatprofiel. <br><br> AltNameTypeEmail: als dit type niet wordt gevonden in het SAN, wordt de waarde van AltNameTypeUpn gebruikt.  Als AltNameTypeUpn ook niet wordt gevonden in het SAN, wordt de waarde van de onderwerpnaam gebruikt als deze de indeling van een e-mailadres heeft.  Als deze nog steeds niet wordt gevonden, kan Intune Certificate Connector de certificaten niet uitgeven. <br><br> Bijvoorbeeld: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> AltNameTypeUpn: als dit type niet wordt gevonden in het SAN, wordt de waarde van AltNameTypeEmail gebruikt. Als AltNameTypeEmail ook niet in het SAN wordt gevonden, wordt de waarde van de onderwerpnaam gebruikt als deze de indeling van een e-mailadres heeft.  Als deze nog steeds niet wordt gevonden, kan Intune Certificate Connector de certificaten niet uitgeven.  <br><br> Bijvoorbeeld: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> AltNameTypeOtherName: als dit type niet in het SAN wordt gevonden, kan Intune Certificate Connector de certificaten niet uitgeven. <br><br> Bijvoorbeeld: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  **Belangrijke opmerking:** De waarde van dit veld wordt alleen ondersteund in de gecodeerde indeling (hexadecimale waarde) door de Symantec-CA. Elke waarde in dit veld wordt door Intune Certificate Connector daarom geconverteerd naar base-64 codering voordat de certificaataanvraag wordt verzonden. **Intune Certificate Connector valideert niet of deze waarde al is gecodeerd.** | Geen |

## <a name="troubleshooting"></a>Probleemoplossing

De logboeken van de Intune Certificate Connector-service zijn beschikbaar in `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs` op de computer met NDES Connector. Open de logboeken in [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) en zoek naar uitzonderingen of foutmeldingen.

| Probleem/foutbericht | Stappen voor het oplossen |
| --- | --- |
| Kan niet aanmelden met beheerdersaccount van Intune-tenant in de interface van NDES Connector | Dit kan gebeuren wanneer de on-premises certificaatconnector niet is ingeschakeld in de Intune-beheerportal. Voer de volgende stappen uit om dit probleem op te lossen: <br><br> Vanuit de Silverlight-interface: <br> 1. Meld u aan bij de [Intune-beheerportal](https://admin.manage.microsoft.com) <br> 2. Klik op BEHEER <br> 3. Selecteer Beheer van mobiele apparaten > Certificaatconnector <br> 4. Klik op **On-premises certificaatconnector configureren** <br> 5. Schakel het selectievakje **Certificaatconnector inschakelen** in <br> 6. Klik op **OK**. <br><br>of <br><br> Vanuit Azure Portal: <br> 1. Meld u aan bij [Azure Portal](https://portal.azure.com) <br> 2. Ga naar Microsoft Intune <br> 3. Selecteer **Apparaatconfiguratie** > **Certificeringsinstantie** <br> 4. Klik op **Inschakelen**. <br><br> Nadat u de vorige stappen hebt voltooid vanuit de Silverlight-interface of de Azure-portal, probeert u zich aan te melden met hetzelfde Intune-beheerdersaccount in de interface van NDES Connector. |
| NDES Connector-certificaat kan niet worden gevonden. <br><br> System.ArgumentNullException: waarde kan niet null zijn. | Intune Certificate Connector toont deze fout als het beheerdersaccount van de Intune-tenant zich nooit heeft aangemeld bij de interface van NDES Connector. <br><br> Als deze fout zich blijft voordoen, start u de Intune-serviceconnector opnieuw. <br><br> 1. Open services.msc. <br> 2. Selecteer **Intune-connectorservice**. <br> 3. Klik met de rechtermuisknop en selecteer **Opnieuw starten**.|
| NDES Connector: IssuePfx - Algemene uitzondering: <br> System.NullReferenceException: Objectverwijzing niet ingesteld op een exemplaar van een object. | Deze fout is tijdelijk. Start de Intune-serviceconnector opnieuw. <br><br> 1. Open services.msc. <br> 2. Selecteer **Intune-connectorservice**. <br> 3. Klik met de rechtermuisknop en selecteer **Opnieuw starten**. |
| Symantec-provider: Kan Symantec-beleid niet ophalen. 'Er is een time-out opgetreden voor de bewerking'. | Intune Certificate Connector kreeg een foutbericht over een time-out met een bewerking tijdens de communicatie met de Symantec-CA. Als deze fout zich blijft voordoen, verhoogt u de time-outwaarde voor de verbinding en probeert u het opnieuw. <br><br> De time-out voor de verbinding verhogen: <br> 1. Ga naar de computer met NDES Connector. <br>2. Open het bestand `%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config` in Kladblok. <br> 3. Verhoog de time-outwaarde voor de volgende parameter: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Start de Intune-connectorservice opnieuw. <br><br> Als het probleem zich blijft voordoen, neemt u contact op met de klantenondersteuning van Symantec. |
| Symantec-provider: Kan clientcertificaat niet ophalen | Intune Certificate Connector kan het certificatie voor bronautorisatie niet ophalen uit het persoonlijke certificaatarchief op de lokale computer. U lost dit probleem op door het certificaat voor bronautorisatie, samen met de persoonlijke sleutel, te installeren in het persoonlijke certificaatarchief van de lokale computer. <br><br> **Opmerking:** Het certificaat voor bronautorisatie moet worden opgehaald bij de Symantec-CA. Neem voor meer informatie contact op met de klantenondersteuning van Symantec. | 
| Symantec-provider: Kan Symantec-beleid niet ophalen. 'De aanvraag is afgebroken: kan het beveiligde SSL/TLS-kanaal niet maken.' | Deze fout treedt op in de volgende scenario's: <br><br> 1. De Intune Certificate Connector-service beschikt over onvoldoende machtigingen om het certificaat voor bronautorisatie, samen met de persoonlijke sleutel, te lezen in het persoonlijke certificaatarchief van de lokale computer. U kunt dit probleem oplossen door het account in de actieve context van de connectorservice in services.msc te controleren. De connectorservice moet worden uitgevoerd in de context NT AUTHORITY\SYSTEM. <br><br> 2. Het PKCS-certificaatprofiel in de Intune-beheerportal is mogelijk geconfigureerd met een ongeldige FQDN van de Symantec CA-basisservice. De FQDN moet lijken op `pki-ws.symauth.com`. U lost dit probleem door contact op te nemen met de klantenondersteuning van Symantec en te vragen of de URL juist is voor uw abonnement. <br><br> 3. Intune Certificate Connector kan niet worden geverifieerd bij de Symantec-CA met het certificaat voor bronautorisatie omdat de persoonlijke sleutel niet kan worden opgehaald. U lost dit probleem op door het certificaat voor bronautorisatie, samen met de persoonlijke sleutel, te installeren in het persoonlijke certificaatarchief van de lokale computer. <br><br> Als het probleem zich blijft voordoen, neemt u contact op met de klantenondersteuning van Symantec. |
| Symantec-provider: Kan Symantec-beleid niet ophalen. 'Een aanvraagelement is niet begrepen.' | Intune Certificate Connector kan de sjabloon voor het Symantec-certificaatprofiel niet ophalen omdat de clientprofiel-OID niet overeenkomt met het Intune-certificaatprofiel. Het is ook mogelijk dat Intune Certificate Connector de certificaatprofielsjabloon die is gekoppeld aan de opgegeven clientprofiel-OID in de Symantec-CA, niet kan vinden. <br><br> U lost dit probleem op door de juiste clientprofiel-OID te verkrijgen via de Symantec-certificaatsjabloon in de Symantec-CA. Werk vervolgens het PKCS-certificaatprofiel in de Intune-beheerportal bij. <br><br> De clientprofiel-OID ophalen van de Symantec-CA: <br> 1. Meld u aan bij de beheerportal van de Symantec-CA. <br> 2. Klik op Manage Certificate Profiles. <br> 3. Selecteer het certificaatprofiel dat u wilt gebruiken. <br> 4. Vraag de certificaatprofiel-OID op. Deze ziet er ongeveer uit zoals in het volgende voorbeeld: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Het PKCS-certificaatprofiel bijwerken met de juiste certificaatprofiel-OID: <br>1. Meld u aan bij de Intune-beheerportal. <br> 2. Ga naar het PKCS-certificaatprofiel en klik op **Bewerken**. <br> 3. Werk de certificaatprofiel-OID bij in het veld met de naam van de certificaatsjabloon. <br> 4. Sla het PKCS-certificaatprofiel op. |
| Symantec-provider: Verificatie van beleid is mislukt. <br><br> Kenmerk staat niet op de lijst met door Symantec ondersteunde kenmerken voor certificaatsjablonen | De Symantec-CA toont dit bericht wanneer er een discrepantie is tussen de sjabloon voor het Symantec-certificaatprofiel en het Intune-certificaatprofiel. Dit probleem ontstaat waarschijnlijk doordat kenmerken in SubjectName of SubjectAltName niet overeenkomen. <br><br> U lost dit probleem op door voor SubjectName en SubjectAltName in de sjabloon voor het Symantec-certificaatprofiel door Intune ondersteunde kenmerken te selecteren. Raadpleeg de door Intune ondersteunde kenmerken in het gedeelte Certificaatparameters voor meer informatie. |
| Sommige gebruikersapparaten ontvangen geen PKCS-certificaten van de Symantec-CA. | Dit probleem treedt op als de UPN van de gebruiker speciale tekens bevat, zoals een onderstrepingsteken (bijvoorbeeld: `global_admin@intune.onmicrosoft.com`). <br><br> De Symantec-CA ondersteunt geen speciale tekens in mail_firstname en mail_lastname. <br><br> Voer de volgende stappen uit om dit probleem op te lossen: <br><br> 1.   Meld u aan bij de beheerportal van de Symantec-CA. <br> 2. Ga naar Manage Certificate Profiles. <br> 3.   Klik op het certificaatprofiel dat wordt gebruikt voor Intune. <br> 4.  Klik op de koppeling Customize options. <br> 5.   Klik op de knop Advanced options. <br> 6.  Voeg onder certificaatvelden – Subject DN het veld Common Name (CN) toe en verwijder het bestaande veld Common Name (CN). Toevoegen en verwijderen moeten tegelijk worden uitgevoerd. <br> 7.    Klik op Save. <br><br> Na de voorgaande wijziging vraagt het Symantec-certificaatprofiel om 'CN =<upn>' in plaats van mail_firstname en mail_lastname. |
| De gebruiker heeft een reeds geïmplementeerd certificaat van het apparaat verwijderd. | Intune implementeert hetzelfde certificaat opnieuw wanneer opnieuw wordt ingecheckt of het beleid wordt afgedwongen. In dit geval ontvangt NDES Connector geen PKCS-certificaataanvraag. |

## <a name="next-steps"></a>Volgende stappen

- Gebruik de informatie in dit artikel naast de informatie in [Wat zijn Microsoft Intune-apparaatprofielen?](device-profiles.md) om de apparaten van uw organisatie en de certificaten erop te beheren.

[InstallConnector]:  ./media/certificates-symantec-connector-install.png "Intune Certificate Connector installeren en PFX-distributie selecteren"
[ConfigureConnector]: ./media/certificates-symantec-configure-connector-configure.png "Intune Certificate Connector configureren"
[ConfigureProfile]: ./media/certificates-symantec-pkcs-example.png "PKCS-certificaatprofiel maken in Azure Portal"
