---
title: Certificaten met een persoonlijke en openbare sleutel gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik PKCS-certificaten (Public Key Cryptography Standards) met Microsoft Intune, werk met basiscertificaten en certificaatsjablonen, de installatie van de Intune Certificate Connector (NDES) en gebruik apparaatconfiguratieprofielen voor een PKCS-certificaat.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6d35d7470508b610f850ca7f9f394e0d26bec677
ms.sourcegitcommit: 576b9528629981e87e775fac146932e502f07a74
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2020
ms.locfileid: "77258093"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-certificaten configureren en gebruiken met Intune

Intune ondersteunt het gebruik van certificaten voor persoonlijke en openbare sleutelparen (PKCS). Met behulp van dit artikel kunt u de vereiste infrastructuur, zoals on-premises certificaatconnectors, configureren, een PKCS-certificaat exporteren en vervolgens het certificaat toevoegen aan een Intune-apparaatconfiguratieprofiel.

Microsoft Intune bevat ingebouwde instellingen voor het gebruik van PKCS-certificaten voor toegang en verificatie van uw bedrijfsbronnen. Met certificaten wordt de toegang tot uw bedrijfsbronnen, zoals een VPN of Wi-Fi-netwerk, geverifieerd en beveiligd. U implementeert deze instellingen naar apparaten met behulp van apparaatconfiguratieprofielen in Intune.

Zie [Geïmporteerde PFX-certificaten](certificates-imported-pfx-configure.md) voor meer informatie over het gebruik van geïmporteerde PKCS-certificaten.


## <a name="requirements"></a>Vereisten

Als u PKCS-certificaten wilt gebruiken met Intune, hebt u de volgende infrastructuur nodig:

- **Active Directory-domein**:  
  Alle servers die in dit gedeelte worden genoemd, moeten lid zijn van uw Active Directory-domein.

  Zie [AD DS-ontwerp- en -planning](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) voor meer informatie over het installeren en configureren van AD DS (Active Directory Domain Services).

- **Certificeringsinstantie**:  
   Een certificeringsinstantie (CA) voor ondernemingen.

  Raadpleeg [Stapsgewijze handleiding bij Active Directory Certificate Services](https://technet.microsoft.com/library/cc772393) als u informatie wilt over het installeren en configureren van Active Directory Certificate Services (AD CS).

  > [!WARNING]  
  > Voor Intune moet u AD CS uitvoeren met een certificeringsinstantie (CA) voor ondernemingen, niet met een zelfstandige certificeringsinstantie.

- **Een client**:  
  deze wordt gekoppeld aan de CA voor ondernemingen.

- **Basiscertificaat**:  
  Een geëxporteerde kopie van uw basiscertificaat van uw CA voor ondernemingen.

- **Microsoft Intune Certificate Connector** (ook wel de *NDES-certificaatconnector* genoemd):  
  Ga in de Intune-portal naar **Apparaatconfiguratie** > **Certificaatconnectors** > **Toevoegen** en volgt u de *stappen om de connector te installeren voor PKCS #12*. Gebruik de downloadkoppeling om het downloaden van het installatieprogramma voor de certificaatconnector **NDESConnectorSetup.exe** te starten.  

  Intune ondersteunt maximaal honderd exemplaren van deze connector per tenant. Elk exemplaar van de connector moet zich op een afzonderlijke Windows-server bevinden. U kunt een instantie van deze connector op dezelfde server installeren als een instantie van de PFX-certificaatconnector voor Microsoft Intune. Wanneer u meerdere connectors gebruikt, ondersteunt de infrastructuur van de connector hoge beschikbaarheid en taakverdeling als een beschikbare connectorexempplaar uw PKCS-certificaataanvragen kan verwerken. 

  Met deze connector worden PKCS-certificaataanvragen verwerkt die worden gebruikt voor verificatie of S/MIME-e-mailondertekening.

  De Microsoft Intune Certificate Connector ondersteunt ook de Federal Information Processing Standard-modus (FIPS). FIPS is niet vereist, maar wanneer deze modus is ingeschakeld, kunt u certificaten uitgeven en intrekken.

- **PFX-certificaatconnector voor Microsoft Intune**:  
  Als u van plan bent om S/MIME-versleuteling te gebruiken voor e-mailberichten, moet u via de Intune-portal de connector voor *PFX-certificaten* downloaden die ondersteuning biedt voor het importeren van PFX-certificaten.  Ga naar **Apparaatconfiguratie** > **Certificaatconnectors** > **Toevoegen** en volg de *stappen om de connector installeren voor geïmporteerde PFX-certificaten*. Gebruik de downloadkoppeling om het downloaden van het installatieprogramma **PfxCertificateConnectorBootstrapper.exe** te starten. 

  Elke Intune-tenant ondersteunt één instantie van deze connector. U kunt deze connector op dezelfde server installeren als een instantie van de Microsoft Intune Certificate Connector.

  Deze connector verwerkt aanvragen voor PFX-bestanden die zijn geïmporteerd in Intune voor S/MIME-e-mailversleuteling voor een specifieke gebruiker.  

  Deze connector kan automatisch worden bijgewerkt wanneer nieuwe versies beschikbaar komen. Als u de updatemogelijkheid wilt gebruiken, moet u:
  - De connector voor PFX-certificaten voor Microsoft Intune installeren op uw server.  
  - Voor het automatisch ontvangen van belangrijke updates moet u ervoor zorgen dat firewalls geopend zijn, waarmee de connector contact kan opnemen met **autoupdate.msappproxy.net** op poort **443**.   

  Zie [Netwerkeindpunten voor Microsoft Intune](../fundamentals/intune-endpoints.md) en [Netwerkconfiguratievereisten en bandbreedte voor Intune](../fundamentals/network-bandwidth-use.md) voor meer informatie.

- **Windows Server**:  
  U gebruikt een Windows Server als host voor:

  - Microsoft Intune Certificate Connector: voor verificatie en voor scenario's met S/MIME-e-mailondertekening
  - PFX-certificaatconnector voor Microsoft Intune: voor scenario's met S/MIME-e-mailversleuteling.

  Intune staat toe dat de *PFX-certificaatconnector* en de *Microsoft Intune-certificaatconnector* op dezelfde server worden geïnstalleerd.
  
## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Het basiscertificaat exporteren vanuit de CA voor ondernemingen

Voor verificatie van een apparaat met VPN, Wi-Fi of andere resources hebt u op elk apparaat een basis- of tussen-CA-certificaat nodig. In de volgende stappen wordt uitgelegd hoe u het vereiste certificaat kunt verkrijgen op basis van uw CA voor ondernemingen.

**Opdrachtregel invoeren**:  
1. Meld u aan bij de basiscertificeringsinstantieserver met een beheerdersaccount.
 
2. Ga naar **Start** > **Uitvoeren** en voer vervolgens **Cmd** uit om de opdrachtprompt openen. 
    
3. Geef **certutil -ca.cert ca_name.cer** op om het basiscertificaat te exporteren als een bestand met de naam *ca_name.cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Certificaatsjablonen configureren op de CA

1. Meld u aan bij uw CA voor ondernemingen met een account met beheerdersbevoegdheden.
2. Open de console **Certificeringsinstantie**, klik met de rechtermuisknop op **Certificaatsjablonen** en selecteer **Beheren**.
3. Zoek naar de certificaatsjabloon **Gebruiker**, klik er met de rechtermuisknop op en kies **Sjabloon dupliceren** om **Eigenschappen van nieuwe sjabloon** te openen.

    > [!NOTE]
    > Voor scenario's voor S/MIME-e-mailversleuteling en -ondertekening gebruiken veel beheerders afzonderlijke certificaten voor ondertekening en versleuteling. Als u Microsoft Active Directory Certificate Services gebruikt, kunt u de sjabloon **Alleen Exchange-handtekening** gebruiken voor S/MIME-e-mailondertekeningscertificaten en de sjabloon **Exchange-gebruiker** voor S/MIME-versleutelingscertificaten.  Als u een certificeringsinstantie van derden gebruikt, is het verstandig de richtlijnen te raadplegen voor het instellen van sjablonen voor ondertekening en versleuteling.

4. Op het tabblad **Compatibiliteit**:

    - Stel **Certificeringsinstantie (CA)** in op **Windows Server 2008 R2**
    - Stel **Ontvanger van certificaat** in op **Windows 7 / Server 2008 R2**

5. Stel op het tabblad **Algemeen** **Weergavenaam van sjabloon** in op iets dat voor u herkenbaar is.

    > [!WARNING]
    > **Sjabloonnaam** is standaard hetzelfde als **Weergavenaam van sjabloon**, maar dan *zonder spaties*. Noteer de naam van de sjabloon; deze hebt u later nodig.

6. Selecteer in **Afhandeling van aanvragen** de optie **De persoonlijke sleutel exporteerbaar maken**.
7. Bevestig in **Cryptografie** dat de **Minimale sleutelgrootte** is ingesteld op 2048.
8. Kies **Leveren met het verzoek** in **Onderwerpnaam**.
9. Bevestig in **Extensies** dat Encrypting File System, Beveiligde e-mail en Clientauthenticatie worden weergegeven onder **Toepassingsbeleid**.

    > [!IMPORTANT]
    > Ga voor iOS-certificaatsjablonen naar het tabblad **Extensies**, werk **Sleutelgebruik** bij en zorg ervoor dat **Handtekening is bewijs van authenticiteit** niet is ingeschakeld.

10. Voeg in **Beveiliging** het computeraccount toe voor de server waarop u de Microsoft Intune Certificate Connector installeert. Geef dit account machtigingen voor **Lezen** en **Registreren**.
11. Selecteer **Toepassen** > **OK** om de certificaatsjabloon op te slaan. Sluit de **console Certificaatsjablonen**.
12. Klik in de **certificeringsinstantieconsole** met de rechtermuisknop op **Certificaatsjablonen** > , klik op **Nieuw** >  en klik vervolgens op **Te verlenen certificaatsjablonen**. Kies de sjabloon die u in de eerdere stappen hebt gemaakt. Selecteer **OK**.
13. Voer de volgende stappen uit om ervoor te zorgen dat de server certificaten beheert voor geregistreerde apparaten en gebruikers:

    1. Klik met de rechtermuisknop op de CA en kies **Eigenschappen**.
    2. Voeg op het tabblad Beveiliging het computeraccount toe voor de server waarop u de connectors (**Microsoft Intune-certificaatconnector** of **PFX-certificaatconnector voor Microsoft Intune**) uitvoert. 
    3. Verleen de machtigingen **Certificaten verlenen en beheren** en **Certificaten aanvragen** aan het computeraccount.

14. Meld u af bij de CA voor ondernemingen.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>De Microsoft Intune Certificate Connector downloaden, installeren en configureren

> [!IMPORTANT]  
> De Microsoft Intune-certificaatconnector kan niet worden geïnstalleerd op de verlenende certificeringsinstantie (CA) en moet in plaats daarvan op een afzonderlijke Windows-server worden geïnstalleerd.  

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Certificaatconnectors** >  **+ Toevoegen**.

3. Klik op *De certificaatconnectorsoftware downloaden* voor de connector voor PKCS #12 en sla het bestand op op een locatie waartoe u toegang hebt vanaf de server waarop u de connector gaat installeren.

   ![Microsoft Intune Certificate Connector-download](./media/certficates-pfx-configure/download-ndes-connector.png)
 
4. Nadat het downloaden is voltooid, meldt u zich aan bij de server. Vervolgens:

    1. Controleer of .NET 4.5 Framework of hoger is geïnstalleerd. Dit is vereist voor de NDES-certificaatconnector. .NET Framework 4.5 wordt automatisch geïnstalleerd met Windows Server 2012 R2 en nieuwere versies.
    2. Start het installatieprogramma (NDESConnectorSetup.exe) en accepteer de standaardlocatie. De connector wordt geïnstalleerd in `\Program Files\Microsoft Intune\NDESConnectorUI`. Selecteer in de opties voor het installatieprogramma **PFX-distributie**. Ga verder en voltooi de installatie.
    3. De connectorservice wordt standaard uitgevoerd onder het lokale systeemaccount. Als een proxy is vereist voor toegang tot internet, moet u bevestigen dat het lokale serviceaccount toegang heeft tot de proxy-instellingen op de server.

5. Het tabblad **Inschrijving** wordt geopend door de Microsoft Intune Certificate Connector. Als u de verbinding met Intune wilt inschakelen, kiest u **Aanmelden** en geeft u een account met globale beheerdersmachtigingen op.
6. U wordt aangeraden om op het tabblad **Geavanceerd** het keuzerondje **Systeemaccount van deze computer gebruiken (standaard)** ingeschakeld te laten.
7. **Toepassen** > **Sluiten**
8. Ga terug naar de Intune-portal (**Intune** > **Apparaatconfiguratie** > **Certificaatconnectors**). Even later wordt een groen vinkje weergegeven en is de **Verbindingsstatus** **Actief**. Uw connector-server kan nu communiceren met Intune.
9. Als u een webproxy in uw netwerkomgeving hebt, hebt u mogelijk extra configuraties nodig voordat de connector werkt. Raadpleeg [Werken met bestaande on-premises proxyservers](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) in de Azure Active Directory-documentatie voor meer informatie.
<ul><li>Android Enterprise (*Werkprofiel*)</li><li>iOS</li><li>macOS</li><li>Windows 10 en later > De Microsoft Intune Certificate Connector ondersteunt TLS 1.2. Als TLS 1.2 is geïnstalleerd op de server die als host fungeert voor de connector, maakt de connector gebruik van TLS 1.2. Anders wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

## <a name="create-a-trusted-certificate-profile"></a>Een vertrouwd certificaatprofiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.

   ![Ga naar Intune en maak een nieuw profiel voor een vertrouwd certificaat](./media/certficates-pfx-configure/certificates-pfx-configure-profile-new.png)

3. Voer de volgende eigenschappen in:

    - **Naam** voor het profiel
    - Een beschrijving instellen (optioneel)
    - **Platform** waarvoor het profiel moet worden geïmplementeerd
    - Stel **Profieltype** in op **Vertrouwd certificaat**

4. Selecteer **Instellingen** en geef het eerder geëxporteerde CER-bestand van het basis-CA-certificaat op.

   > [!NOTE]
   > Afhankelijk van het platform dat u in **stap 2** kiest, hebt u al dan niet de mogelijkheid het **Doelarchief** voor het certificaat te kiezen.

   ![Een profiel maken en een vertrouwd certificaat uploaden](./media/certficates-pfx-configure/certificates-pfx-configure-profile-fill.png)

5. Selecteer **OK** > **Maken** om het profiel op te slaan.

6. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](../configuration/device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="create-a-pkcs-certificate-profile"></a>Een PKCS-certificaatprofiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Ga naar **Apparaten** > **Configuratieprofielen** > **Profiel maken**.

3. Voer de volgende eigenschappen in:

    - **Naam** voor het profiel
    - Een beschrijving instellen (optioneel)
    - **Platform** waarvoor het profiel moet worden geïmplementeerd
    - Stel **Profieltype** in op **PKCS-certificaat**

4. Selecteer **Instellingen** en configureer de eigenschappen die van toepassing zijn op het platform dat u hebt geselecteerd:
   
   |Instelling     | Platform     | Details   |
   |------------|------------|------------|
   |**Drempelwaarde voor verlenging (%)**        |<ul><li>Alle         |20% wordt aanbevolen  | 
   |**Geldigheidsduur van certificaat**  |<ul><li>Alle         |Als u de certificaatsjabloon niet hebt gewijzigd, kan deze optie worden ingesteld op één jaar. |
   |**Sleutelarchiefprovider (KSP)**   |<ul><li>Windows 10  | Voor Windows selecteert u waar u de sleutels op het apparaat wilt opslaan. |
   |**Certificeringsinstantie**      |<ul><li>Alle         |Geeft de interne FQDN (Fully Qualified Domain Name) van uw CA voor ondernemingen weer.  |
   |**Naam van certificeringsinstantie** |<ul><li>Alle         |Geeft de naam van uw CA voor ondernemingen weer, bijvoorbeeld "Contoso Certification Authority". |
   |**Certificaattype**             |<ul><li>Android Enterprise (*Werkprofiel*)</li><li>iOS</li><li>macOS</li><li>Windows 10 en hoger|Selecteer een type: <ul><li> **Gebruiker**-certificaten kunnen zowel gebruikers- als apparaatkenmerken in het onderwerp ende SAN van het certificaat bevatten. </il><li>**Apparaat**-certificaten kunnen alleen apparaatkenmerken in het onderwerp en SAN van het certificaat bevatten. Gebruik Apparaat voor scenario's als apparaten zonder gebruiker, zoals kiosken of andere gedeelde apparaten.  <br><br> Deze selectie is van invloed op de indeling van de onderwerpnaam. |
   |**Indeling van de onderwerpnaam**          |<ul><li>Alle         |Voor de meeste platformen stelt u deze optie in op **Algemene naam** tenzij anders aangegeven.<br><br>Voor de volgende platformen wordt de indeling van de onderwerpnaam bepaald door het certificaattype: <ul><li>Android Enterprise (*Werkprofiel*)</li><li>iOS</li><li>macOS</li><li>Windows 10 en hoger</li></ul>  <p> Zie [Indeling van de onderwerpnaam](#subject-name-format) verderop in dit artikel. |
   |**Alternatieve naam voor het onderwerp**     |<ul><li>Alle         |Stel deze optie in op **User principal name (UPN)** tenzij anders aangegeven. |
   |**Uitgebreide-sleutelgebruik**           |<ul><li> Android-apparaatbeheerder </li><li>Android Enterprise (*Apparaateigenaar*, *Werkprofiel*) </li><li>Windows 10 |Certificaten vereisen meestal *Clientverificatie*, zodat de gebruiker of het apparaat bij een server kan worden geverifieerd. |
   |**Alle apps mogen toegang hebben tot de persoonlijke sleutel** |<ul><li>macOS  |Stel in op **Inschakelen** om apps die zijn geconfigureerd voor het bijbehorende Mac-apparaat toegang te geven tot de persoonlijke sleutel van de PKCS-certificaten. <br><br> Zie *AllowAllAppsAccess* in de sectie Nettolading van certificaat van [Referentiemateriaal configuratieprofiel](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf) in de Apple-documentatie voor ontwikkelaars voor meer informatie over deze instelling. |
   |**Basiscertificaat**             |<ul><li>Android-apparaatbeheerder </li><li>Android Enterprise (*Apparaateigenaar*, *Werkprofiel*) |Selecteer een basis-CA-certificaatprofiel dat eerder is toegewezen. |

5. Selecteer **OK** > **Maken** om het profiel op te slaan.

6. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](../configuration/device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

   > [!NOTE]
   > Op apparaten met een Android Enterprise-profiel zijn certificaten die zijn geïnstalleerd met een PKCS-certificaatprofiel niet zichtbaar op het apparaat. Controleer de status van het profiel in de Intune-console om te controleren of de implementatie van het certificaat is geslaagd.

### <a name="subject-name-format"></a>Indeling van de onderwerpnaam

Wanneer u een PKCS-certificaatprofiel voor de volgende platformen maakt, zijn de opties voor de indeling van de onderwerpnaam afhankelijk van het certificaattype dat u selecteert, ofwel **Gebruiker** ofwel **Apparaat**.  

Platformen:

- Android Enterprise (*Werkprofiel*)
- iOS
- macOS
- Windows 10 en hoger

> [!NOTE]
> Er is een bekend probleem bij het gebruik van PKCS, [hetzelfde probleem dat ook bij SCEP optreedt](certificates-profile-scep.md#avoid-certificate-signing-requests-with-escaped-special-characters), om certificaten op te halen wanneer in de onderwerpnaam in de resulterende aanvraag voor certificaatondertekening (Certificate Signing Request, CSR) een van de volgende tekens staat na een escape-teken (een backslash \\):
> - \+
> - ;
> - ,
> - =

- **Certificaattype Gebruiker**  
  De indelingsopties voor de *Indeling van de onderwerpnaam* omvatten twee variabelen: **Algemene naam (CN)** en **E-mail (E)** . **Algemene naam (CN)** kan worden ingesteld op een van de volgende variabelen:

  - **CN={{UserName}}** : De user principal name van de gebruiker, bijvoorbeeld janedoe@contoso.com.
  - **CN={{AAD_Device_ID}}** : Een id die wordt toegewezen wanneer u een apparaat in Azure Active Directory (AD) registreert. Deze id wordt doorgaans gebruikt voor verificatie met Azure AD.
  - **CN={{SERIALNUMBER}}** : Het unieke serienummer (SN) dat doorgaans wordt gebruikt door de fabrikant om een apparaat te identificeren.
  - **CN={{IMEINumber}}** : Het unieke nummer van de International Mobile Equipment Identity (IMEI) dat wordt gebruikt om een mobiele telefoon te identificeren.
  - **CN={{OnPrem_Distinguished_Name}}** : Een reeks RDN's (Relative Distinguished Name), gescheiden door komma's, zoals *CN=Jane Doe,OU=UserAccounts,DC=corp,DC=contoso,DC=com*.

    Als u de variabele *{{OnPrem_Distinguished_Name}}* wilt gebruiken, moet u het gebruikerskenmerk *onpremisesdistinguishedname* met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw Azure AD.

  - **CN={{onPremisesSamAccountName}}** : Beheerders kunnen het kenmerk samAccountName van Active Directory met behulp van Azure AD Connect synchroniseren met Azure AD in een kenmerk met de naam *onPremisesSamAccountName*. Deze variabele kan in Intune worden vervangen als onderdeel van een aanvraag voor certificaatuitgifte in het onderwerp van een certificaat. Het kenmerk samAccountName is de aanmeldingsnaam van de gebruiker die wordt gebruikt ter ondersteuning van clients en servers van een oudere versie dan Windows 2000. De indeling voor de aanmeldingsnaam van de gebruiker is: *DomainName\testUser* of alleen *testUser*.

    Als u de variabele *{{onPremisesSamAccountName}}* wilt gebruiken, moet u het gebruikerskenmerk *onPremisesSamAccountName* met behulp van [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw Azure AD.

  Door een combinatie van een of meer van deze variabelen en statische tekenreeksen te gebruiken, kunt u een aangepaste indeling voor de naam van een certificaathouder maken, bijvoorbeeld:  
  - **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US**
  
  Dat voorbeeld bevat een indeling van de onderwerpnaam waarin gebruik wordt gemaakt van de variabelen CN en E, plus tekenreeksen voor de waarden Organizational Unit, Organization, Location, State en Country. [De functie CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) beschrijft deze functie en de ondersteunde tekenreeksen.

- **Certificaattype Apparaat**  
  Indelingsopties voor de Indeling van de onderwerpnaam zijn de volgende variabelen: 
  - **{{AAD_Device_ID}}**
  - **{{Device_Serial}}**
  - **{{Device_IMEI}}**
  - **{{SerialNumber}}**
  - **{{IMEINumber}}**
  - **{{AzureADDeviceId}}**
  - **{{WiFiMacAddress}}**
  - **{{IMEI}}**
  - **{{DeviceName}}**
  - **{{FullyQualifiedDomainName}}** *(Alleen van toepassing op Windows-apparaten en apparaten die aan een domein zijn toegevoegd)*
  - **{{MEID}}**

  U kunt deze variabelen opgeven in het tekstvak, gevolgd door de tekst voor de variabele. De algemene naam voor een apparaat met de naam *Device1* kan bijvoorbeeld worden toegevoegd als **CN={{DeviceName}}Device1**.

  > [!IMPORTANT]  
  > - Plaats bij het opgeven van een variabele de naam van de variabele tussen accolades {}, zoals in het voorbeeld te zien is, om fouten te voorkomen.  
  > - Apparaateigenschappen die worden gebruikt in het *onderwerp* of de *SAN* van een apparaatcertificaat, zoals **IMEI**, **SerialNumber** en **FullyQualifiedDomainName**, zijn eigenschappen die kunnen worden vervalst door een persoon die toegang tot het apparaat heeft.
  > - Een apparaat moet alle variabelen ondersteunen die zijn opgegeven in een certificaatprofiel, anders kan het profiel niet worden geïnstalleerd op het apparaat.  Als bijvoorbeeld **{{IMEI}}** wordt gebruikt in de onderwerpnaam van een SCEP-profiel en deze variabele wordt toegewezen aan een apparaat dat geen IMEI-nummer heeft, mislukt de installatie van het profiel.  
 


## <a name="whats-new-for-connectors"></a>Wat is er nieuw voor connectors

Updates voor de twee certificaatconnectors worden regelmatig uitgebracht. Als we een connector bijwerken, kunt u hier over de wijzigingen lezen.

De *PFX-certificaatconnector voor Microsoft Intune* [biedt ondersteuning voor automatische updates](#requirements), terwijl de *Intune-certificaatconnector* handmatig wordt bijgewerkt.

### <a name="may-17-2019"></a>17 mei 2019

- **Connector voor PFX-certificaten voor Microsoft Intune - versie 6.1905.0.404**  
  Wijzigingen in deze release:  
  - Er is een probleem opgelost waarbij bestaande PFX-certificaten steeds opnieuw worden verwerkt, zodat de connector stopt met het verwerken van nieuwe aanvragen. 

### <a name="may-6-2019"></a>6 mei 2019

- **Connector voor PFX-certificaten voor Microsoft Intune - versie 6.1905.0.402**  
  Wijzigingen in deze release:  
  - De polling-interval voor de connector wordt verlaagd van 5 minuten naar 30 seconden.
 
### <a name="april-2-2019"></a>2 april 2019

- **Intune-certificaatconnector - versie 6.1904.1.0**  
  Wijzigingen in deze release:  
  - Er is een probleem opgelost waarbij de connector zich mogelijk niet kan inschrijven bij Intune na aanmelding bij de connector met een globale beheerdersaccount.  
  - Deze bevat betrouwbaarheidsoplossingen voor het intrekken van certificaten.  
  - Deze bevat prestatieoplossingen om de snelheid te verhogen waarmee PKCS-certificaataanvragen worden verwerkt.  

- **Connector voor PFX-certificaten voor Microsoft Intune - versie 6.1904.0.401**
  > [!NOTE]  
  > Er is tot en met 11 april 2019 geen automatische update voor deze versie van het PFX-connector beschikbaar.  

  Wijzigingen in deze release:  
  - Er is een probleem opgelost waarbij de connector zich mogelijk niet kan inschrijven bij Intune na aanmelding bij de connector met een globale beheerdersaccount.  


## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](../configuration/device-profile-assign.md) en [de status ervan controleren](../configuration/device-profile-monitor.md).

[Gebruik SCEP voor certificaten](certificates-scep-configure.md) of [verleen PKCS-certificaten via een webservice van Symantec PKI-manager](certificates-digicert-configure.md).
