---
title: Certificaten met een persoonlijke en openbare sleutel gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: 'PKCS-certificaten (PKCS: Public Key Cryptography Standards) toevoegen of maken met Microsoft Intune, inclusief de stappen om een basiscertificaat te exporteren, de certificaatsjabloon te configureren, de Intune Certificate Connector (NDES) te downloaden en installeren, een apparaatconfiguratieprofiel te maken en een PKCS-certificaatprofiel in Azure en uw certificeringsinstantie (CA) te maken.'
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/05/2019
ms.topic: article
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: c1119a5681033574ec0a114442b122990da872bf
ms.sourcegitcommit: cb76efd3db60a422a65478ebce83d3aea7b5eeed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2019
ms.locfileid: "66749818"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-certificaten configureren en gebruiken met Intune

Intune ondersteunt het gebruik van certificaten voor persoonlijke en openbare sleutelparen (PKCS). Met behulp van dit artikel kunt u de vereiste infrastructuur, zoals on-premises certificaatconnectors, configureren, een PKCS-certificaat exporteren en vervolgens het certificaat toevoegen aan een Intune-apparaatconfiguratieprofiel.

Microsoft Intune bevat ingebouwde instellingen voor het gebruik van PKCS-certificaten voor toegang en verificatie van uw bedrijfsbronnen. Met certificaten wordt de toegang tot uw bedrijfsbronnen, zoals een VPN of Wi-Fi-netwerk, geverifieerd en beveiligd. U implementeert deze instellingen naar apparaten met behulp van apparaatconfiguratieprofielen in Intune.


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

- **Intune-certificaatconnector** (ook wel de *NDES-certificaatconnector* genoemd):  
  Ga in de Intune-portal naar **Apparaatconfiguratie** > **Certificaatconnectors** > **Toevoegen** en volgt u de *stappen om de connector te installeren voor PKCS #12*. Gebruik de downloadkoppeling om het downloaden van het installatieprogramma voor de certificaatconnector **NDESConnectorSetup.exe** te starten.  

  Met deze connector worden PKCS-certificaataanvragen verwerkt die worden gebruikt voor verificatie of S/MIME-e-mailondertekening.

  De NDES-certificaatconnector ondersteunt ook de Federal Information Processing Standard-modus (FIPS). FIPS is niet vereist, maar wanneer deze modus is ingeschakeld, kunt u certificaten uitgeven en intrekken.

- **PFX-certificaatconnector voor Microsoft Intune**:  
   Als u van plan bent om S/MIME-versleuteling te gebruiken voor e-mailberichten, moet u via de Intune-portal de connector voor *geïmporteerde PFX-certificaten* downloaden.  Ga naar **Apparaatconfiguratie** > **Certificaatconnectors** > **Toevoegen** en volg de *stappen om de connector installeren voor geïmporteerde PFX-certificaten*. Gebruik de downloadkoppeling om het downloaden van het installatieprogramma **PfxCertificateConnectorBootstrapper.exe** te starten. 

  Deze connector verwerkt aanvragen voor PFX-bestanden die zijn geïmporteerd in Intune voor S/MIME-e-mailversleuteling voor een specifieke gebruiker.  

  Deze connector kan automatisch worden bijgewerkt wanneer nieuwe versies beschikbaar komen. Als u de updatemogelijkheid wilt gebruiken, moet u:
  - De connector voor geïmporteerde PFX-certificaten voor Microsoft Intune installeren op uw server.
  - Voor het automatisch ontvangen van belangrijke updates moet u ervoor zorgen dat firewalls geopend zijn, waarmee de connector contact kan opnemen met **autoupdate.msappproxy.net** op poort **443**.  


- **Windows Server**:  
  U gebruikt een Windows Server als host voor:

  - Microsoft Intune Certificate Connector: voor verificatie en voor scenario's met S/MIME-e-mailondertekening
  - PFX-certificaatconnector voor Microsoft Intune: voor scenario's met S/MIME-e-mailversleuteling.

  U kunt beide connectors (*Microsoft Intune Certificate Connector* en *PFX-certificaatconnector*) op dezelfde server installeren.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Het basiscertificaat exporteren vanuit de CA voor ondernemingen

Voor verificatie van een apparaat met VPN, Wi-Fi of andere resources hebt u op elk apparaat een basis- of tussen-CA-certificaat nodig. In de volgende stappen wordt uitgelegd hoe u het vereiste certificaat kunt verkrijgen op basis van uw CA voor ondernemingen.

**Opdrachtregel invoeren**:  
1. Meld u aan bij de basiscertificeringsinstantieserver met een beheerdersaccount.
 
2. Ga naar **Start** > **Uitvoeren** en voer vervolgens **Cmd** uit om de opdrachtprompt openen. 
    
3. Geef **certutil-ca.cert ca_name.cer** op om het basiscertificaat te exporteren als een bestand met de naam *ca_name.cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Certificaatsjablonen configureren op de CA

1. Meld u aan bij uw CA voor ondernemingen met een account met beheerdersbevoegdheden.
2. Open de console **Certificeringsinstantie**, klik met de rechtermuisknop op **Certificaatsjablonen** en selecteer **Beheren**.
3. Zoek naar de certificaatsjabloon **Gebruiker**, klik er met de rechtermuisknop op en kies **Sjabloon dupliceren**. **Eigenschappen van nieuwe sjabloon** wordt geopend.

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

## <a name="download-install-and-configure-the-certificate-connectors"></a>De certificaatconnectors downloaden, installeren en configureren

### <a name="microsoft-intune-certificate-connector"></a>Microsoft Intune-certificaatconnector

> [!IMPORTANT]  
> De Microsoft Intune-certificaatconnector kan niet worden geïnstalleerd op de verlenende certificeringsinstantie (CA) en moet in plaats daarvan op een afzonderlijke Windows-server worden geïnstalleerd.  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Certificaatconnectors** > **Toevoegen**.
3. Download het connectorbestand en sla dit op een locatie op waar u het kunt openen vanaf de server waarop u de connector gaat installeren.

    ![De NDES-connector downloaden](media/certificates-pfx-configure/download-ndes-connector.png)
 

4. Nadat het downloaden is voltooid, meldt u zich aan bij de server. Vervolgens:

    1. Controleer of .NET 4.5 Framework of hoger is geïnstalleerd. Dit is vereist voor de NDES-certificaatconnector. .NET Framework 4.5 wordt automatisch geïnstalleerd met Windows Server 2012 R2 en nieuwere versies.
    2. Start het installatieprogramma (NDESConnectorSetup.exe) en accepteer de standaardlocatie. De connector wordt geïnstalleerd in `\Program Files\Microsoft Intune\NDESConnectorUI`. Selecteer in de opties voor het installatieprogramma **PFX-distributie**. Ga verder en voltooi de installatie.
    3. De connectorservice wordt standaard uitgevoerd onder het lokale systeemaccount. Als een proxy is vereist voor toegang tot internet, moet u bevestigen dat het lokale serviceaccount toegang heeft tot de proxy-instellingen op de server.

5. De NDES Connector opent het tabblad **Inschrijving**. Als u de verbinding met Intune wilt inschakelen, kiest u **Aanmelden** en geeft u een account met globale beheerdersmachtigingen op.
6. U wordt aangeraden om op het tabblad **Geavanceerd** het keuzerondje **Systeemaccount van deze computer gebruiken (standaard)** ingeschakeld te laten.
7. **Toepassen** > **Sluiten**
8. Ga terug naar de Intune-portal (**Intune** > **Apparaatconfiguratie** > **Certificaatconnectors**). Even later wordt een groen vinkje weergegeven en is de **Verbindingsstatus** **Actief**. Uw connector-server kan nu communiceren met Intune.
9. Als u een webproxy in uw netwerkomgeving hebt, hebt u mogelijk extra configuraties nodig voordat de connector werkt. Raadpleeg [Werken met bestaande on-premises proxyservers](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) in de Azure Active Directory-documentatie voor meer informatie.

> [!NOTE]  
> Microsoft Intune Certificate Connector ondersteunt TLS 1.2. Als TLS 1.2 is geïnstalleerd op de server die als host fungeert voor de connector, maakt de connector gebruik van TLS 1.2. Anders wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>PFX-certificaatconnector voor Microsoft Intune

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Certificaatconnectors** > **Toevoegen**
3. Download de PFX-certificaatconnector voor Microsoft Intune en sla deze op. Sla het bestand op op een locatie die toegankelijk is vanaf de server waar u de connector gaat installeren.
4. Nadat het downloaden is voltooid, meldt u zich aan bij de server. Vervolgens:

    1. Controleer of .NET 4.6 Framework of hoger is geïnstalleerd. Dit is vereist voor de PFX-certificaatconnector voor Microsoft Intune. Als .NET 4.6 Framework niet is geïnstalleerd, wordt dit automatisch door het installatieprogramma geïnstalleerd.
    2. Voer het installatieprogramma (PfxCertificateConnectorBootstrapper.exe) uit en accepteer de standaardlocatie, waardoor de connector op `Program Files\Microsoft Intune\PFXCertificateConnector` wordt geïnstalleerd.
    3. De connectorservice wordt uitgevoerd onder het lokale systeemaccount. Als een proxy is vereist voor toegang tot internet, moet u bevestigen dat het lokale serviceaccount toegang heeft tot de proxy-instellingen op de server.

5. Het tabblad **Inschrijving** wordt na de installatie geopend. Als u de verbinding met Intune wilt inschakelen, kiest u **Aanmelden** en geeft u een account met globale beheerdersmachtigingen voor Azure of beheerdersbevoegdheden voor Intune op.
6. Sluit het venster.
7. Ga terug naar Azure Portal (**Intune** > **Apparaatconfiguratie** > **Certificaatconnectors**). Even later wordt een groen vinkje weergegeven en is de **Verbindingsstatus** **Actief**. Uw connector-server kan nu communiceren met Intune.

## <a name="create-a-trusted-certificate-profile"></a>Een vertrouwd certificaatprofiel maken

1. Ga in de [Azure-portal](https://portal.azure.com) naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
    ![Navigeren naar Intune en een nieuw profiel voor een vertrouwd certificaat maken](media/certificates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Voer de volgende eigenschappen in:

    - **Naam** voor het profiel
    - Een beschrijving instellen (optioneel)
    - **Platform** waarvoor het profiel moet worden geïmplementeerd
    - Stel **Profieltype** in op **Vertrouwd certificaat**

3. Ga naar **Instellingen** en voer het eerder geëxporteerde CER-bestand van het basis-CA-certificaat in.

   > [!NOTE]
   > Afhankelijk van het platform dat u in **stap 2** kiest, hebt u al dan niet de mogelijkheid het **Doelarchief** voor het certificaat te kiezen.

   ![Een profiel maken en een vertrouwd certificaat uploaden](media/certificates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

4. Selecteer **OK** > **Maken** om het profiel op te slaan.
5. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="create-a-pkcs-certificate-profile"></a>Een PKCS-certificaatprofiel maken

1. Ga in de [Azure-portal](https://portal.azure.com) naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
2. Voer de volgende eigenschappen in:

    - **Naam** voor het profiel
    - Een beschrijving instellen (optioneel)
    - **Platform** waarvoor het profiel moet worden geïmplementeerd
    - Stel **Profieltype** in op **PKCS-certificaat**

3. Ga naar **Instellingen** en voer de volgende eigenschappen in:

    - **Drempelwaarde voor verlenging (%)** : 20% wordt aanbevolen.
    - **Geldigheidsduur van certificaat**: Als u de certificaatsjabloon niet hebt gewijzigd, kan deze optie worden ingesteld op één jaar.
    - **Sleutelarchiefprovider (KSP)** : Voor Windows selecteert u waar u de sleutels op het apparaat wilt opslaan.
    - **Certificeringsinstantie**: Geeft de interne FQDN (Fully Qualified Domain Name) van uw CA voor ondernemingen weer.
    - **Naam van certificeringsinstantie**: Geeft de naam van uw CA voor ondernemingen weer, bijvoorbeeld "Contoso Certification Authority".
    - **Certificaatsjabloonnaam**: De naam van de sjabloon die eerder is gemaakt. Nogmaals, **Sjabloonnaam** is standaard hetzelfde als **Weergavenaam van sjabloon**, maar dan *zonder spaties*.
    - **Indeling van de onderwerpnaam**: Stel deze optie in op **Algemene naam** tenzij anders aangegeven.
    - **Alternatieve naam voor het onderwerp**: Stel deze optie in op **User principal name (UPN)** tenzij anders aangegeven.

4. Selecteer **OK** > **Maken** om het profiel op te slaan.
5. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="create-a-pkcs-imported-certificate-profile"></a>Een geïmporteerd PKCS-certificaatprofiel maken

U kunt certificaten importeren die eerder zijn uitgegeven aan een specifieke gebruiker van elke certificeringsinstantie naar Intune. Geïmporteerde certificaten worden geïnstalleerd op elk apparaat dat door een gebruiker wordt geregistreerd. S/MIME-e-mailversleuteling is het meest voorkomende scenario voor het importeren van bestaande PFX-certificaten in Intune. Een gebruiker kan verschillende certificaten hebben voor de versleuteling van e-mailberichten. De persoonlijke sleutels van die certificaten moeten bestaan op alle apparaten van een gebruiker, zodat eerder versleutelde e-mailberichten kunnen worden ontsleuteld.

Voor het importeren van certificaten in Intune kunt u de [PowerShell-cmdlets in GitHub](https://github.com/Microsoft/Intune-Resource-Access) gebruiken.

Na het importeren van de certificaten naar Intune maakt u een **geïmporteerd PKCS-certificaatprofiel** en wijst u dit toe aan Azure Active Directory-groepen.

1. Ga in de [Azure-portal](https://portal.azure.com) naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
2. Voer de volgende eigenschappen in:

    - **Naam** voor het profiel
    - Een beschrijving instellen (optioneel)
    - **Platform** waarvoor het profiel moet worden geïmplementeerd
    - Stel **Profieltype** in op **Geïmporteerd PKCS-certificaat**

3. Ga naar **Instellingen** en voer de volgende eigenschappen in:

    - **Beoogd doeleinde**: Het beoogde doel van de certificaten die voor dit profiel worden geïmporteerd. Een beheerder kan certificaten met verschillende beoogde doelen (zoals verificatie, S/MIME-ondertekening of S/MIME-versleuteling) importeren. Het beoogde doel dat is geselecteerd in het certificaatprofiel komt overeen met het certificaatprofiel met de juiste geïmporteerde certificaten.
    - **Geldigheidsduur van certificaat**: Als u de certificaatsjabloon niet hebt gewijzigd, kan deze optie worden ingesteld op één jaar.
    - **Sleutelarchiefprovider (KSP)** : Voor Windows selecteert u waar u de sleutels op het apparaat wilt opslaan.

4. Selecteer **OK** > **Maken** om het profiel op te slaan.
5. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="whats-new-for-connectors"></a>Wat is er nieuw voor connectors
Updates voor de twee certificaatconnectors worden regelmatig uitgebracht. Als we een connector bijwerken, kunt u hier over de wijzigingen lezen. 

De *PFX-certificaatconnector voor Microsoft Intune* [biedt ondersteuning voor automatische updates](#requirements), terwijl de *Intune-certificaatconnector* handmatig wordt bijgewerkt.

### <a name="may-17-2019"></a>17 mei 2019  
- **Connector voor PFX-certificaten voor Microsoft Intune - versie 6.1905.0.404**  
  Wijzigingen in deze release:  
  - Er is een probleem opgelost waarbij bestaande PFX-certificaten steeds opnieuw worden verwerkt, zodat de connector stopt met het verwerken van nieuwe aanvragen. 

### <a name="may-6-2019"></a>6 mei 2019  
- **PFX-certificaatconnector voor Microsoft Intune - versie 6.1905.0.402**  
  Wijzigingen in deze release:  
  - De polling-interval voor de connector wordt verlaagd van 5 minuten naar 30 seconden.
 
### <a name="april-2-2019"></a>2 april 2019  
- **Intune-certificaatconnector - versie 6.1904.1.0**  
  Wijzigingen in deze release:  
  - Er is een probleem opgelost waarbij de connector zich mogelijk niet kan inschrijven bij Intune na aanmelding bij de connector met een globale beheerdersaccount.  
  - Deze bevat betrouwbaarheidsoplossingen voor het intrekken van certificaten.  
  - Deze bevat prestatieoplossingen om de snelheid te verhogen waarmee PKCS-certificaataanvragen worden verwerkt.  

- **PFX-certificaatconnector voor Microsoft Intune - versie 6.1904.0.401**
  > [!NOTE]  
  > Er is tot en met 11 april 2019 geen automatische update voor deze versie van het PFX-connector beschikbaar.  

  Wijzigingen in deze release:  
  - Er is een probleem opgelost waarbij de connector zich mogelijk niet kan inschrijven bij Intune na aanmelding bij de connector met een globale beheerdersaccount.  


## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

[Gebruik SCEP-certificaten](certificates-scep-configure.md) of [geef PKCS-certificaten uit van een webservice van Symantec PKI-manager](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navigeren naar Intune in Azure Portal en een nieuw profiel voor een vertrouwd certificaat maken"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Een profiel maken en een vertrouwd certificaat uploaden"
[ConnectorDownload]: ./media/certificates-download-connector.png "De certificaatconnector downloaden van Azure Portal"  
