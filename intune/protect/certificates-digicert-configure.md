---
title: PKCS-certificaten van DigiCert uitgeven met Microsoft Intune
titleSuffix: Microsoft Intune
description: U kunt Intune Certificate Connector installeren en configureren om PKCS-certificaten van het DigiCert PKI-platform uit te geven voor met Intune beheerde apparaten.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1679eb656e04296e53d8994dcd47144621c99d0c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71721770"
---
# <a name="set-up-intune-certificate-connector-for-digicert-pki-platform"></a>Intune Certificate Connector instellen voor het DigiCert PKI-platform  

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U kunt Intune Certificate Connector gebruiken om PKCS-certificaten van het DigiCert PKI-platform uit te geven voor met Intune beheerde apparaten. U kunt de connector gebruiken met alleen een DigiCert-CA (certificeringsinstantie) of met zowel een DigiCert-CA als een Microsoft-CA.  
> [!TIP]  
> DigiCert heeft de websitebeveiliging van Symantec en verwante zakelijke PKI-oplossingen verkregen. Raadpleeg het [artikel over technische ondersteuning van Symantec](https://support.symantec.com/en_US/article.INFO4722.html) voor meer informatie over deze wijziging.

Als u de Intune Certificate Connector al gebruikt om certificaten van een Microsoft-CA uit te geven met behulp van PKCS of System Center Endpoint Protection, kunt u dezelfde connector gebruiken om PKCS-certificaten van een DigiCert-CA te configureren en uit te geven. Nadat u de configuratie ter ondersteuning van de DigiCert-CA hebt voltooid, kan de Intune Certificate Connector de volgende certificaten uitgeven:

* PKCS-certificaten van een Microsoft-CA
* PKCS-certificaten van een DigiCert-CA
* Endpoint Protection-certificaten van een Microsoft-CA

Als u de connector niet hebt geïnstalleerd maar deze wilt gebruiken voor zowel een Microsoft-CA als een DigiCert-CA, voltooit u eerst de connectorconfiguratie voor de Microsoft-CA. Ga vervolgens terug naar dit artikel om de connector te configureren om ook DigiCert te ondersteunen. Zie [Een certificaatprofiel configureren voor uw apparaten in Microsoft Intune](certificates-configure.md) voor meer informatie over certificaatprofielen en de connector.  

Als u de connector gebruikt met alleen de DigiCert-CA, kunt u de instructies in dit artikel gebruiken om de connector te installeren en vervolgens te configureren. 

## <a name="prerequisites"></a>Vereisten  
- **Een actief abonnement op de DigiCert-CA**: Het abonnement is vereist om een RA-certificaat (registratie-instantie) te verkrijgen van de DigiCert-CA.

## <a name="install-the-digicert-ra-certificate"></a>Het DigiCert RA-certificaat installeren  
 
1. Sla het volgende codefragment op in een bestand genaamd **certreq.ini** en werk dit bij zoals vereist (bijvoorbeeld: *onderwerpnaam in CN-indeling*).
 
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

2. Open een opdrachtprompt met verhoogde bevoegdheid en genereer een CSR (certificaatondertekeningsaanvraag) met behulp van de volgende opdracht:

   `Certreq.exe -new certreq.ini request.csr`

3. Open het bestand request.csr in Kladblok en kopieer de CSR-inhoud in de volgende indeling:


        -----BEGIN NEW CERTIFICATE REQUEST-----
        MIID8TCCAtkCAQAwbTEMMAoGA1UEBhMDVVNBMQswCQYDVQQIDAJXQTEQMA4GA1UE
        …
        …
        fzpeAWo=
        -----END NEW CERTIFICATE REQUEST-----


4. Meld u aan bij de DigiCert-CA en blader in de taken naar **RA-certificaat verkrijgen**.

   a. Geef in het tekstvak de CSR-inhoud op uit stap 3. 

   b. Geef een beschrijvende naam op voor het certificaat.

   c. Selecteer **Doorgaan**. 

   d. Gebruik de opgegeven koppeling om het RA-certificaat te downloaden op de lokale computer.

5. Importeer het RA-certificaat in het Windows-certificaatarchief:

   a. Open een MMC-console.

   b. Klik op **Bestand** > **Modules toevoegen of verwijderen** > **Certificaat** > **Toevoegen**. 

   c. Selecteer **Computeraccount** > **Volgende**.

   d. Selecteer **Lokale computer** > **Voltooien**. 

   e. Selecteer **OK** in het venster **Modules toevoegen of verwijderen**. Vouw **Certificaten (lokale computer)**  > **Persoonlijk** > **Certificaten** uit.

   f. Klik met de rechtermuisknop op het knooppunt **Certificaten** en selecteer **Alle taken** > **Importeren**.  

   g. Selecteer de locatie van het RA-certificaat dat u hebt gedownload van de DigiCert-CA, en klik vervolgens op **Volgende**.

   h. Selecteer **Persoonlijke certificaatarchief** > **Volgende**. 

   i. Selecteer **Voltooien** om het RA-certificaat en de bijbehorende persoonlijke sleutel te importeren in het **persoonlijke certificaatarchief van de lokale computer**.  

6. Het certificaat met persoonlijke sleutel exporteren en importeren: 

   a. Vouw **Certificaten (lokale computer)**  > **Persoonlijk** > **Certificaten** uit.

   b. Selecteer het certificaat dat is geïmporteerd in de vorige stap.

   c. Klik met de rechtermuisknop op het certificaat en selecteer **Alle taken** > **Exporteren**.

   d. Selecteer **Volgende** en voer het wachtwoord in.

   e. Selecteer de locatie waarnaar u wilt exporteren, en selecteer vervolgens **Voltooien**.

   f. Gebruik de procedure in stap 5 om het certificaat met persoonlijke sleutel te importeren in het **persoonlijke archief op de lokale computer**.

   g. Leg een kopie van de vingerafdruk van het RA-certificaat vast, zonder spaties. Dit is een voorbeeld van de vingerafdruk: 

        RA Cert Thumbprint: “EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5”
    
    > [!NOTE]
    > Voor hulp bij het ophalen van het RA-certificaat van de DigiCert-CA, neemt u contact op met de [klantenondersteuning van DigiCert](mailto:enterprise-pkisupport@digicert.com).  

## <a name="prepare-to-install-intune-certificate-connector"></a>De installatie van Microsoft Intune Certificate Connector voorbereiden
> [!TIP]  
> Deze sectie is van toepassing als u Intune Certificate Connector gebruikt met alleen een DigiCert-CA. Als u Intune Certificate Connector gebruikt met een Microsoft-CA en ondersteuning voor DigiCert-CA wilt toevoegen, gaat u verder naar [De connector configureren om DigiCert te ondersteunen](#configure-the-connector-to-support-digicert).  

1. Kies een van de versies van het Windows-besturingssysteem in de onderstaande lijst en installeer deze op een computer:
   * Windows Server 2012 R2 Datacenter
   * Windows Server 2012 R2 Standard
   * Windows Server 2016 Datacenter
   * Windows Server 2016 Standard

2. Maak een gebruiker met beheerdersbevoegdheden en gebruik deze om de volgende stappen uit te voeren.

3. Zoek naar de meest recente Windows-updates en installeer deze, indien beschikbaar. Start de computer opnieuw op nadat u de Windows-updates hebt geïnstalleerd.

4. Installeer .NET Framework 3.5:

   a. Open **Configuratiescherm** > **Programma's en onderdelen** > **Windows-onderdelen in- of uitschakelen**.

   b. Selecteer **.NET Framework 3.5** en installeer dit.  

## <a name="install-intune-certificate-connector-for-use-with-digicert"></a>Intune Certificate Connector installeren voor gebruik met DigiCert  

> [!TIP]  
> Als u de Intune Certificate Connector gebruikt met een Microsoft-CA en ondersteuning voor DigiCert-CA wilt toevoegen, gaat u verder naar [De connector configureren om DigiCert te ondersteunen](#configure-the-connector-to-support-digicert).  

Download de meest recente versie van Intune Certificate Connector van de Intune-beheerportal en volg deze instructies.

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Selecteer **Apparaatconfiguratie** > **Certificaatconnectors** >  **+ Toevoegen**.  

3. Selecteer **De certificaatconnectorsoftware downloaden**. Sla de software op in een locatie waar u toegang toe hebt vanaf de server waarop u deze gaat installeren.  

   ![De connectorsoftware downloaden](./media/certificates-digicert-configure/connector-download.png)
   
4. Voer op de server waar u de connector wilt installeren **NDESConnectorSetup.exe** uit met verhoogde bevoegdheid. 

5. Selecteer op de pagina **Installatieopties** **PFX-distributie**.  
   
   ![PFX-distributie selecteren](./media/certificates-digicert-configure/digicert-ca-connector-install.png)

   > [!IMPORTANT]
   > Als u de Intune Certificate Connector gaat gebruiken om certificaten van een Microsoft-CA en een DigiCert-CA uit te geven, selecteert u **SCEP- en PFX-profieldistributie**. 

6. Gebruik de standaardselecties om het instellen van de connector te voltooien.

## <a name="configure-the-connector-to-support-digicert"></a>De connector configureren voor de ondersteuning van DigiCert

Standaard wordt Intune Certificate Connector geïnstalleerd in **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc**.

1. Open in de map **NDESConnectorSvc** het bestand **NDESConnector.exe.config** in Kladblok.

   a. Werk de waarde van de sleutel `RACertThumbprint` bij met de waarde van de certificaatvingerafdruk die u in het vorige gedeelte hebt gekopieerd. Bijvoorbeeld:

        <add key="RACertThumbprint"
        value="EA7A4E0CD1A4F81CF0740527C31A57F6020C17C5"/>
   
   b. Sla het bestand op en sluit het.

2. Open **services.msc**:

   a. Selecteer **Intune-connectorservice**.

   b. Stop de service en start de service weer.

   c. Sluit het venster van de service.

## <a name="set-up-the-intune-administrator-account"></a>Het Intune-beheerdersaccount instellen  

> [!TIP]  
> Als u Intune Certificate Connector gebruikt met een Microsoft-CA en ondersteuning voor DigiCert-CA wilt toevoegen, gaat u verder naar [Een vertrouwd certificaatprofiel maken](#create-a-trusted-certificate-profile).   
 
1. Open de gebruikersinterface van NDES Connector vanuit **%ProgramFiles%\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe**.  

2. Selecteer **Aanmelden** op het tabblad **Inschrijving**.

3. Geef uw beheerdersreferenties voor de Intune-tenant op.

4. Selecteer **Aanmelden** en vervolgens **OK** om een geslaagde inschrijving te bevestigen. Vervolgens kunt u de gebruikersinterface van NDES Connector sluiten.
   
   ![NDES Connector-interface met bericht 'Inschrijven is geslaagd'](./media/certificates-digicert-configure/certificates-digicert-configure-connector-configure.png)



## <a name="create-a-trusted-certificate-profile"></a>Een vertrouwd certificaatprofiel maken

De PKCS-certificaten die u wilt implementeren voor met Intune beheerde apparaten, moeten worden gekoppeld met een vertrouwd basiscertificaat. Als u deze keten tot stand wilt brengen, maakt u een vertrouwd certificaatprofiel voor Intune maken met het basiscertificaat van de DigiCert-CA.

1. Een vertrouwd basiscertificaat ophalen van de DigiCert-CA:

    a. Meld u aan bij de beheerportal van DigiCert-CA.

    b. Selecteer **CA's beheren** in **Taken**. 

    c. Selecteer de juiste CA in de lijst.  

    d. Selecteer **Basiscertificaat downloaden** om het vertrouwde basiscertificaat te downloaden.

2. Maak een vertrouwd certificaatprofiel in de Intune-beheerportal:

   a. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

   b. Selecteer **Apparaatconfiguratie** > **Beheren** > **Profielen** > **Profiel maken**.

   c. Voer een **Naam** en **Beschrijving** in voor het vertrouwde certificaatprofiel.

   d. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform voor dit vertrouwde certificaat.

   e. Selecteer in de vervolgkeuzelijst **Profieltype** de optie **Vertrouwd certificaat**.

   f. Blader naar het vertrouwde bestand voor de basis-CA die u in de vorige stap hebt verkregen van de DigiCert-CA, en selecteer vervolgens **OK**.

   g. Voor Windows 8.1- en Windows 10-apparaten selecteert u het doelarchief voor het vertrouwde certificaat vanuit:    
      - **Certificaatarchief van de computer – basis**  
      - **Certificaatarchief van de computer – tijdelijk**  
      - **Certificaatarchief van de gebruiker – tijdelijk** 

   h. Als u klaar bent, kiest u **OK**, gaat u terug naar het deelvenster **Profiel maken** en kiest u **Maken**.  
 
Het profiel wordt weergegeven in de lijst met profielen in het deelvenster **Apparaatconfiguratie – Profielen** met het profieltype **Vertrouwd certificaat**.  Zorg ervoor dat u dit profiel toewijst aan apparaten die certificaten gaan gebruiken. Zie [Apparaatprofielen toewijzen](../configuration/device-profile-assign.md) om dit profiel toe te wijzen aan groepen.


## <a name="get-the-certificate-profile-oid"></a>De certificaatprofiel-OID ophalen  

De OID van het certificaatprofiel is gekoppeld aan een certificaatprofielsjabloon in de DigiCert-CA. Als u een PKCS-certificaatprofiel wilt maken in Intune, moet u de naam van de certificaatsjabloon opgeven in de vorm van een certificaatprofiel-OID die is gekoppeld aan een certificaatsjabloon in de DigiCert-CA.

1. Meld u aan bij de beheerportal van DigiCert-CA.
2. Selecteer **Certificaatprofielen beheren**.
3. Selecteer het certificaatprofiel dat u wilt gebruiken.
4. Kopieer de OID van het certificaatprofiel. Deze ziet er ongeveer uit zoals in het volgende voorbeeld:

 
       Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109 
 

> [!NOTE]
> Als u hulp nodig hebt bij het ophalen van de certificaat profiel-OID, neemt u contact op met [DigiCert-klantondersteuning](mailto:enterprise-pkisupport@digicert.com).

## <a name="create-a-pkcs-certificate-profile"></a>Een PKCS-certificaatprofiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).  

2. Ga naar **Apparaatconfiguratie** >  **Profielen**, en selecteer **Profiel maken**.

3. Voer de gegevens in bij **Naam** en **Beschrijving** voor het PKCS-certificaatprofiel.  

4. Selecteer in de vervolgkeuzelijst **Platform** een ondersteund apparaatplatform.

5. Selecteer in de vervolgkeuzelijst **Profieltype** de optie **PKCS-certificaat**.
 
6. Configureer in het deelvenster **PKCS-certificaat** parameters met de waarden uit de volgende tabel. Deze waarden zijn vereist om PKCS-certificaten uit een DigiCert-CA uit te geven via Intune Certificate Connector. 

   |Parameter van PKCS-certificaat | Waarde | Beschrijving |
   | --- | --- | --- |
   | Certificeringsinstantie | pki-ws.symauth.com | Deze waarde moet de FQDN van de basisservice van de DigiCert-CA zijn, zonder afsluitende schuine strepen. Als u niet zeker weet of dit is de juiste FQDN voor de basisservice voor uw DigiCert-CA-abonnement is, neemt u contact op met de klantenondersteuning van DigiCert. <br><br>*Ondanks de wijziging van Symantec in DigiCert, blijft deze URL ongewijzigd*. <br><br> Als deze FQDN onjuist is, geeft Intune Certificate Connector geen PKCS-certificaten van de DigiCert-CA uit.| 
   | Naam van certificeringsinstantie | Symantec | Deze waarde moet de tekenreeks **Symantec** zijn. <br><br> Als deze waarde afwijkt, geeft Intune Certificate Connector geen PKCS-certificaten van de DigiCert-CA uit.|
   | Naam van certificaatsjabloon | Certificaatprofiel-OID van de DigiCert-CA. Bijvoorbeeld: **2.16.840.1.113733.1.16.1.2.3.1.1.61904612**| Deze waarde moet de certificaatprofiel-OID zijn die [in het vorige gedeelte is verkregen](#get-the-certificate-profile-oid) van de certificaatprofielsjabloon van de DigiCert-CA. <br><br> Als Intune Certificate Connector geen certificaatsjabloon kan vinden die is gekoppeld aan deze certificaatprofiel-OID in de DigiCert-CA, worden geen PKCS-certificaten van de DigiCert-CA uitgegeven.|  

   ![Selecties voor CA en certificaatsjabloon](./media/certificates-digicert-configure/certificates-digicert-pkcs-example.png)  

   > [!NOTE]
   > Het PKCS-certificaatprofiel voor Windows-platforms hoeft niet te zijn gekoppeld aan een vertrouwd certificaatprofiel. Dit is echter wel vereist voor profielen voor andere platforms dan Windows, zoals Android.
7. Voltooi de configuratie van het profiel om te voldoen aan de behoeften van uw bedrijf en selecteer vervolgens **OK** om het profiel op te slaan. 

8. Selecteer **Toewijzingen** configureer een geschikte groep die dit profiel zal ontvangen. Ten minste één gebruiker of apparaat moet deel uitmaken van de toegewezen groep.
 
Nadat u de vorige stappen hebt voltooid, geeft Intune Certificate Connector PKCS-certificaten van de DigiCert-CA uit voor met Intune beheerde apparaten in de toegewezen groep. Deze certificaten zijn beschikbaar in het **persoonlijke** archief van het certificaatarchief van de **huidige gebruiker** op het met Intune beheerde apparaat.

### <a name="supported-attributes-for-the-pkcs-certificate-profile"></a>Ondersteunde kenmerken voor het PKCS-certificaatprofiel

|Kenmerk | Door Intune ondersteunde indelingen | Door DigiCert Cloud-CA ondersteunde indelingen | result |
| --- | --- | --- | --- |
| Onderwerpnaam |Intune ondersteunt de onderwerpnaam in de volgende drie indelingen: <br><br> 1. Algemene naam <br> 2. Algemene naam met e-mailadres <br> 3. Algemene naam als e-mailadres <br><br> Bijvoorbeeld: <br><br> `CN = IWUser0 <br><br> E = IWUser0@samplendes.onmicrosoft.com` | De DigiCert-CA ondersteunt meer kenmerken.  Als u meer kenmerken wilt selecteren, moeten deze worden gedefinieerd met vaste waarden in de sjabloon voor het DigiCert-certificaatprofiel.| We gebruiken algemene naam of e-mailadres uit de PKCS-certificaataanvraag. <br><br> Als de geselecteerde kenmerken voor het Intune-certificaatprofiel en de sjabloon voor het DigiCert-certificaatprofiel niet overeenkomen, worden er geen certificaten uitgegeven door de DigiCert-CA.|
| SAN | Intune ondersteunt alleen de volgende waarden voor SAN-velden: <br><br> **AltNameTypeEmail** <br> **AltNameTypeUpn** <br> **AltNameTypeOtherName** (gecodeerde waarde) | De DigiCert Cloud-CA ondersteunt deze parameters ook. Als u meer kenmerken wilt selecteren, moeten deze worden gedefinieerd met vaste waarden in de sjabloon voor het DigiCert-certificaatprofiel. <br><br> **AltNameTypeEmail**: Als dit type niet in het SAN wordt gevonden, gebruikt Intune Certificate Connector de waarde uit **AltNameTypeUpn**.  Als **AltNameTypeUpn** ook niet wordt gevonden in het SAN, gebruikt Intune de waarde van de onderwerpnaam als deze de indeling van een e-mailadres heeft.  Als het type nog steeds niet wordt gevonden, kan Intune Certificate Connector de certificaten niet uitgeven. <br><br> Voorbeeld: `RFC822 Name=IWUser0@ndesvenkatb.onmicrosoft.com`  <br><br> **AltNameTypeUpn**: Als dit type niet wordt gevonden in het SAN, gebruikt Intune Certificate Connector de waarde van **AltNameTypeEmail**. Als **AltNameTypeEmail** ook niet in het SAN wordt gevonden, gebruikt Intune de waarde van de onderwerpnaam als deze de indeling van een e-mailadres heeft. Als het type nog steeds niet wordt gevonden, kan Intune Certificate Connector de certificaten niet uitgeven.  <br><br> Voorbeeld: `Other Name: Principal Name=IWUser0@ndesvenkatb.onmicrosoft.com` <br><br> **AltNameTypeOtherName**: Als dit type niet in het SAN wordt gevonden, kan Intune Certificate Connector de certificaten niet uitgeven. <br><br> Voorbeeld: `Other Name: DS Object Guid=04 12 b8 ba 65 41 f2 d4 07 41 a9 f7 47 08 f3 e4 28 5c ef 2c` <br><br>  De waarde van dit veld wordt alleen door de DigiCert-CA ondersteund in de gecodeerde indeling (hexadecimale waarde). Elke waarde in dit veld wordt door Intune Certificate Connector geconverteerd naar base-64 codering voordat de certificaataanvraag wordt verzonden. *Intune Certificate Connector valideert niet of deze waarde al is gecodeerd.* | Geen |

## <a name="troubleshooting"></a>Probleemoplossing

De servicelogboeken van Intune Certificate Connector zijn beschikbaar in **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\Logs\Logs** op de NDES Connector-computer. Open de logboeken in [SvcTraceViewer](https://docs.microsoft.com/dotnet/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe) en zoek naar uitzonderingen of foutmeldingen.

| Probleem/foutbericht | Stappen voor het oplossen |
| --- | --- |
| Kan niet aanmelden met beheerdersaccount van Intune-tenant in de gebruikersinterface van NDES Connector | Dit kan gebeuren wanneer de on-premises certificaatconnector niet is ingeschakeld in de Intune-beheerportal. Voer een van de volgende procedures uit om dit probleem op te lossen: <br><br> Vanuit de Silverlight-gebruikersinterface: <br> 1. Meld u aan bij de [Intune-beheerportal](https://admin.manage.microsoft.com). <br> 2. Selecteer **ADMIN**. <br> 3. Selecteer **Beheer van mobiele apparaten** > **Certificaatconnector**. <br> 4. Selecteer **On-premises certificaatconnector configureren**. <br> 5. Schakel het selectievakje **Certificaatconnector inschakelen** in. <br> 6. Selecteer **OK**. <br><br> Vanuit Azure Portal: <br> 1. Meld u aan bij [Azure Portal](https://portal.azure.com). <br> 2. Ga naar Microsoft Intune. <br> 3. Selecteer **Apparaatconfiguratie** > **Certificeringsinstantie**. <br> 4. Selecteer **Inschakelen**. <br><br> Nadat u de vorige stappen hebt voltooid vanuit de Silverlight-interface of de Azure-portal, probeert u zich aan te melden met hetzelfde Intune-beheerdersaccount in de interface van NDES Connector. |
| NDES Connector-certificaat kan niet worden gevonden. <br><br> System.ArgumentNullException: De waarde mag niet null zijn. | Intune Certificate Connector toont deze fout als het beheerdersaccount van de Intune-tenant zich nooit heeft aangemeld bij de interface van NDES Connector. <br><br> Als deze fout zich blijft voordoen, start u Intune Service Connector opnieuw. <br><br> 1. Open **services.msc**. <br> 2. Selecteer **Intune-connectorservice**. <br> 3. Klik met de rechtermuisknop en selecteer **Opnieuw starten**.|
| NDES Connector: IssuePfx - Algemene uitzondering: <br> System.NullReferenceException: Objectverwijzing niet ingesteld op een exemplaar van een object. | Deze fout is tijdelijk. Start Intune Service Connector opnieuw op. <br><br> 1. Open **services.msc**. <br> 2. Selecteer **Intune-connectorservice**. <br> 3. Klik met de rechtermuisknop en selecteer **Opnieuw starten**. |
| DigiCert-provider: Kan het DigiCert-beleid niet ophalen. <br><br>'Er is een time-out opgetreden voor de bewerking.' | Intune Certificate Connector heeft een foutbericht ontvangen over een time-out in een bewerking tijdens de communicatie met de DigiCert-CA. Als deze fout zich blijft voordoen, verhoogt u de time-outwaarde voor de verbinding en probeert u het opnieuw. <br><br> De time-out voor de verbinding verhogen: <br> 1. Ga naar de computer met NDES Connector. <br>2. Open het bestand **%ProgramFiles%\Microsoft Intune\NDESConnectorSvc\NDESConnector.exe.config** in Kladblok. <br> 3. Verhoog de time-outwaarde voor de volgende parameter: <br><br> `CloudCAConnTimeoutInMilliseconds` <br><br> 4. Start de Intune Certificate Connector-service opnieuw op. <br><br> Als het probleem zich blijft voordoen, neemt u contact op met de klantenondersteuning van DigiCert. |
| DigiCert-provider: Kan clientcertificaat niet ophalen. | Intune Certificate Connector kan het certificaat voor bronautorisatie niet ophalen uit het persoonlijke certificaatarchief van de lokale computer. U lost dit probleem op door het certificaat voor bronautorisatie, samen met de persoonlijke sleutel, te installeren in het persoonlijke certificaatarchief van de lokale computer. <br><br> Het certificaat voor bronautorisatie moet worden opgehaald bij de DigiCert-CA. Neem voor meer informatie contact op met de klantenondersteuning van DigiCert. | 
| DigiCert-provider: Kan het DigiCert-beleid niet ophalen. <br><br>'De aanvraag is afgebroken: Kan geen beveiligd SSL/TLS-kanaal maken.’ | Deze fout treedt op in de volgende scenario's: <br><br> 1. De Intune Certificate Connector-service beschikt over onvoldoende machtigingen om het certificaat voor bronautorisatie, samen met de persoonlijke sleutel, te lezen in het persoonlijke certificaatarchief van de lokale computer. U kunt dit probleem oplossen door het account in de actieve context van de connectorservice in services.msc te controleren. De connectorservice moet worden uitgevoerd in de context NT AUTHORITY\SYSTEM. <br><br> 2. Het PKCS-certificaatprofiel in de Intune-beheerportal is mogelijk geconfigureerd met een ongeldige basisservice-FQDN voor de DigiCert CA. De FQDN lijkt op **pki-ws.symauth.com**. U lost dit probleem door contact op te nemen met de klantenondersteuning van DigiCert en te vragen of de URL juist is voor uw abonnement. <br><br> 3. Intune Certificate Connector kan niet worden geverifieerd bij de DigiCert-CA met het certificaat voor bronautorisatie omdat het de persoonlijke sleutel niet kan ophalen. U lost dit probleem op door het certificaat voor bronautorisatie, samen met de persoonlijke sleutel, te installeren in het persoonlijke certificaatarchief van de lokale computer. <br><br> Als het probleem zich blijft voordoen, neemt u contact op met de klantenondersteuning van DigiCert. |
| DigiCert-provider: Kan het DigiCert-beleid niet ophalen. <br><br>'Een aanvraag element is niet begrepen.' | Intune Certificate Connector kan de sjabloon voor het DigiCert-certificaatprofiel niet ophalen omdat de clientprofiel-OID niet overeenkomt met het Intune-certificaatprofiel. Het is ook mogelijk dat Intune Certificate Connector de certificaatprofielsjabloon die is gekoppeld aan de opgegeven clientprofiel-OID in de DigiCert-CA, niet kan vinden. <br><br> U lost dit probleem op door de juiste clientprofiel-OID te verkrijgen via de DigiCert-certificaatsjabloon in de DigiCert-CA. Werk vervolgens het PKCS-certificaatprofiel in de Intune-beheerportal bij. <br><br> Haal de clientprofiel-OID op van de DigiCert-CA: <br> 1. Meld u aan bij de beheerportal van DigiCert-CA. <br> 2. Selecteer **Certificaatprofielen beheren**. <br> 3. Selecteer het certificaatprofiel dat u wilt gebruiken. <br> 4. Haal de certificaatprofiel-OID op. Deze ziet er ongeveer uit zoals in het volgende voorbeeld: <br> `Certificate Profile OID = 2.16.840.1.113733.1.16.1.2.3.1.1.47196109` <br><br> Werkt het PKCS-certificaatprofiel bij met de juiste certificaatprofiel-OID: <br>1. Meld u aan bij de Intune-beheerportal. <br> 2. Ga naar het PKCS-certificaatprofiel en selecteer **Bewerken**. <br> 3. Werk de certificaatprofiel-OID bij in het veld met de naam van de certificaatsjabloon. <br> 4. Sla het PKCS-certificaatprofiel op. |
| DigiCert-provider: Verificatie van beleid is mislukt. <br><br> Het kenmerk staat niet op de lijst met door DigiCert ondersteunde kenmerken voor certificaatsjablonen. | De DigiCert-CA toont dit bericht wanneer er een discrepantie is tussen de sjabloon voor het DigiCert-certificaatprofiel en het Intune-certificaatprofiel. Dit probleem ontstaat waarschijnlijk doordat kenmerken in **SubjectName** of **SubjectAltName** niet overeenkomen. <br><br> U lost dit probleem op door voor **SubjectName** en **SubjectAltName** in de sjabloon voor het DigiCert-certificaatprofiel door Intune ondersteunde kenmerken te selecteren. Raadpleeg de door Intune ondersteunde kenmerken in de sectie **Certificaatparameters** voor meer informatie. |
| Sommige gebruikersapparaten ontvangen geen PKCS-certificaten van de DigiCert-CA. | Dit probleem treedt op als de UPN van de gebruiker speciale tekens bevat, zoals een onderstrepingsteken (bijvoorbeeld: `global_admin@intune.onmicrosoft.com`). <br><br> De DigiCert-CA ondersteunt geen speciale tekens in **mail_firstname** en **mail_lastname**. <br><br> Voer de volgende stappen uit om dit probleem op te lossen: <br><br> 1. Meld u aan bij de beheerportal van DigiCert-CA. <br> 2. Ga naar **Certificaatprofielen beheren**. <br> 3. Selecteer het certificaatprofiel dat wordt gebruikt voor Intune. <br> 4. Selecteer de koppeling **Opties aanpassen**. <br> 5. Klik op de knop **Geavanceerde opties**. <br> 6. Voeg onder **Certificaatvelden – Subject DN** het veld **Common Name (CN)** toe en verwijder het bestaande veld **Common Name (CN)** . De bewerkingen voor het toevoegen en verwijderen moeten tegelijk worden uitgevoerd. <br> 7. Selecteer **Opslaan**. <br><br> Na de voorgaande wijziging vraagt het DigiCert-certificaatprofiel om **“CN=<upn>”** in plaats van **mail_firstname** en **mail_lastname**. |
| De gebruiker heeft een reeds geïmplementeerd certificaat van het apparaat verwijderd. | Intune implementeert hetzelfde certificaat opnieuw wanneer opnieuw wordt ingecheckt of het beleid wordt afgedwongen. In dit geval ontvangt NDES Connector geen PKCS-certificaataanvraag. |

## <a name="next-steps"></a>Volgende stappen

Gebruik de informatie in dit artikel naast de informatie in [Wat zijn Microsoft Intune-apparaatprofielen?](../configuration/device-profiles.md) om de apparaten van uw organisatie en de certificaten erop te beheren.

