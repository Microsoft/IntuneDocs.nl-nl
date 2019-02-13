---
title: Certificaten met een persoonlijke en openbare sleutel gebruiken in Microsoft Intune - Azure | Micrososft Docs
description: PKCS-certificaten (Public Key Cryptography Standards) toevoegen of maken met Microsoft Intune, inclusief de stappen om een basiscertificaat te exporteren, de certificaatsjabloon te configureren, de Microsoft Intune Certificate Connector (NDES) te downloaden en installeren, een apparaatconfiguratieprofiel te maken, een PKCS-certificaatprofiel te maken in Azure en uw certificeringsinstantie (CA).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5c2c649df23a84d8836a68fd0456da6ce8dda2c0
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837278"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>PKCS-certificaten configureren en gebruiken met Intune

Met certificaten wordt de toegang tot uw bedrijfsbronnen, zoals een VPN of Wi-Fi-netwerk, geverifieerd en beveiligd. Veel organisaties maken gebruik van certificaten die gebruikmaken van een persoonlijk en openbaar sleutelpaar, ook wel bekend als PKCS-certificaten. Microsoft Intune bevat ingebouwde instellingen voor het gebruik van PKCS-certificaten voor toegang en verificatie van uw bedrijfsbronnen. Deze instellingen worden gepusht naar (of geïmplementeerd op) apparaten met behulp van apparaatconfiguratieprofielen in Intune.

In dit artikel worden de vereisten beschreven voor het gebruik van PKCS-certificaten en leest u hoe u een PKCS-profiel exporteert en toevoegt aan een Intune-apparaatconfiguratieprofiel.

## <a name="requirements"></a>Vereisten

Als u PKCS-certificaten wilt gebruiken met Intune, moet u de volgende infrastructuur hebben:

- **Active Directory-domein**: Alle servers die in dit gedeelte worden genoemd, moeten lid zijn van uw Active Directory-domein.

  Zie [AD DS-ontwerp- en -planning](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning) voor meer informatie over het installeren en configureren van AD DS.

- **Certificeringsinstantie** (CA): Een certificeringsinstantie (CA) voor ondernemingen

  Raadpleeg [Stapsgewijze handleiding bij Active Directory Certificate Services](https://technet.microsoft.com/library/cc772393) als u meer informatie wilt over het installeren en configureren van Active Directory Certificate Services (AD CS).

  > [!WARNING]
  > Voor Intune moet u AD CS uitvoeren met een certificeringsinstantie (CA) voor ondernemingen, niet met een zelfstandige certificeringsinstantie.

- **Een client**: deze wordt gekoppeld aan de CA voor ondernemingen

- **Basiscertificaat**: een geëxporteerde kopie van uw basiscertificaat van uw CA voor ondernemingen

- **Microsoft Intune Certificate Connector**: gebruik Azure Portal om het installatieprogramma voor de **certificaatconnector** (**NDESConnectorSetup.exe**) te downloaden. 

  De connector verwerkt PKCS-certificaataanvragen die worden gebruikt voor verificatie of S/MIME-e-mailondertekening.

  De NDES-certificaatconnector ondersteunt ook de Federal Information Processing Standard-modus (FIPS). FIPS is niet vereist, maar wanneer deze modus is ingeschakeld, kunt u certificaten uitgeven en intrekken.

- **PFX-certificaatconnector voor Microsoft Intune**: als u S/MIME-e-mailversleuteling wilt gebruiken, gebruikt u Azure Portal om het installatieprogramma voor de **PFX-certificaatconnector voor Microsoft Intune** ( **PfxCertificateConnectorBootstrapper.exe**) te downloaden. De connector verwerkt aanvragen voor PFX-bestanden die zijn geïmporteerd in Intune voor S/MIME-e-mailversleuteling voor een specifieke gebruiker.

- **Windows Server**: deze host het volgende:

  - Microsoft Intune-certificaatconnector (NDESConnectorSetup.exe) voor scenario's voor verificatie en S/MIME-e-mailondertekening
  - PFX-certificaatconnector voor Microsoft Intune (PfxCertificateConnectorBootstrapper.exe) voor scenario's voor S/MIME-e-mailversleuteling.

  U kunt beide connectors (**Microsoft Intune-certificaatconnector** en **PFX-certificaatconnector voor Microsoft Intune**) op dezelfde server uitvoeren.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Het basiscertificaat exporteren vanuit de CA voor ondernemingen

Voor verificatie met VPN, Wi-Fi of andere bronnen hebt u op elk apparaat een basis- of tussen-CA-certificaat nodig. In de volgende stappen wordt uitgelegd hoe u het vereiste certificaat kunt verkrijgen op basis van uw CA voor ondernemingen.

1. Meld u aan bij uw CA voor ondernemingen met een account met beheerdersbevoegdheden.
2. Open een opdrachtprompt als beheerder.
3. Exporteer het basis-CA-certificaat (.cer) naar een locatie waar u het later kunt gebruiken.
4. Nadat de wizard is voltooid, maar voordat de wizard wordt gesloten, klikt u op **Gebruikersinterface van certificaatconnector starten**.

   `certutil -ca.cert certnew.cer`

   Zie [Certutil-taken voor het beheren van certificaten](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign) voor meer informatie.

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
> De Microsoft Intune-certificaatconnector **moet** worden geïnstalleerd op een afzonderlijke Windows-server. Deze kan niet worden geïnstalleerd op de verlenende certificeringsinstantie (CA).

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Intune**.
2. Selecteer **Apparaatconfiguratie** > **Certificeringsinstantie** > **Toevoegen**.
3. Download het connectorbestand en sla het op. Sla het bestand op op een locatie die toegankelijk is vanaf de server waar u de connector gaat installeren.

    ![ConnectorDownload][ConnectorDownload]

4. Nadat het downloaden is voltooid, meldt u zich aan bij de server. Vervolgens:

    1. Controleer of .NET 4.5 Framework of hoger is geïnstalleerd. Dit is vereist voor de NDES-certificaatconnector. .NET Framework 4.5 wordt automatisch geïnstalleerd met Windows Server 2012 R2 en nieuwere versies.
    2. Start het installatieprogramma (NDESConnectorSetup.exe) en accepteer de standaardlocatie. De connector wordt geïnstalleerd in `\Program Files\Microsoft Intune\NDESConnectorUI`. Selecteer in de opties voor het installatieprogramma **PFX-distributie**. Ga verder en voltooi de installatie.
    3. De connectorservice wordt standaard uitgevoerd onder het lokale systeemaccount. Als een proxy is vereist voor toegang tot internet, moet u bevestigen dat het lokale serviceaccount toegang heeft tot de proxy-instellingen op de server.

5. De NDES Connector opent het tabblad **Inschrijving**. Als u de verbinding met Intune wilt inschakelen, kiest u **Aanmelden** en geeft u een account met globale beheerdersmachtigingen op.
6. U wordt aangeraden om op het tabblad **Geavanceerd** het keuzerondje **Systeemaccount van deze computer gebruiken (standaard)** ingeschakeld te laten.
7. **Toepassen** > **Sluiten**
8. Ga terug naar de Azure Portal (**Intune** > **Apparaatconfiguratie** > **Certificeringsinstantie**). Even later wordt een groen vinkje weergegeven en is de **Verbindingsstatus** **Actief**. Uw connector-server kan nu communiceren met Intune.
9. Als u een webproxy in uw netwerkomgeving hebt, hebt u mogelijk extra configuraties nodig voordat de connector werkt. Raadpleeg [Werken met bestaande on-premises proxyservers](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) in de Azure Active Directory-documentatie voor meer informatie.

> [!NOTE]
> TLS 1.2-ondersteuning wordt geleverd met de Microsoft Intune-certificaatconnector. Als de server met daarop de Microsoft Intune-certificaatconnector TLS 1.2 ondersteunt, wordt TLS 1.2 gebruikt. Als de server TLS 1.2 niet ondersteunt, wordt TLS 1.1 gebruikt. Momenteel wordt TLS 1.1 gebruikt voor verificatie tussen de apparaten en de server.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>PFX-certificaatconnector voor Microsoft Intune

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Certificeringsinstantie** > **Toevoegen**
3. Download de PFX-certificaatconnector voor Microsoft Intune en sla deze op. Sla het bestand op op een locatie die toegankelijk is vanaf de server waar u de connector gaat installeren.
4. Nadat het downloaden is voltooid, meldt u zich aan bij de server. Vervolgens:

    1. Controleer of .NET 4.6 Framework of hoger is geïnstalleerd. Dit is vereist voor de PFX-certificaatconnector voor Microsoft Intune. Als .NET 4.6 Framework niet is geïnstalleerd, wordt dit automatisch door het installatieprogramma geïnstalleerd.
    2. Voer het installatieprogramma (PfxCertificateConnectorBootstrapper.exe) uit en accepteer de standaardlocatie. De connector wordt geïnstalleerd in `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. De connectorservice wordt uitgevoerd onder het lokale systeemaccount. Als een proxy is vereist voor toegang tot internet, moet u bevestigen dat het lokale serviceaccount toegang heeft tot de proxy-instellingen op de server.

5. Het tabblad **Inschrijving** wordt na de installatie geopend. Als u de verbinding met Intune wilt inschakelen, kiest u **Aanmelden** en geeft u een account met globale beheerdersmachtigingen voor Azure of beheerdersbevoegdheden voor Intune op.
6. Sluit het venster.
7. Ga terug naar de Azure Portal (**Intune** > **Apparaatconfiguratie** > **Certificeringsinstantie**). Even later wordt een groen vinkje weergegeven en is de **Verbindingsstatus** **Actief**. Uw connector-server kan nu communiceren met Intune.

## <a name="create-a-trusted-certificate-profile"></a>Een vertrouwd certificaatprofiel maken

1. Ga in de [Azure-portal](https://portal.azure.com) naar **Intune** > **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.

   ![NavigateIntune][NavigateIntune]

2. Voer de volgende eigenschappen in:

    - **Naam** voor het profiel
    - Een beschrijving instellen (optioneel)
    - **Platform** waarvoor het profiel moet worden geïmplementeerd
    - Stel **Profieltype** in op **Vertrouwd certificaat**

3. Ga naar **Instellingen** en voer het eerder geëxporteerde CER-bestand van het basis-CA-certificaat in.

   > [!NOTE]
   > Afhankelijk van het platform dat u in **stap 3** kiest, hebt u al dan niet de mogelijkheid het **Doelarchief** voor het certificaat te kiezen.

   ![ProfileSettings][ProfileSettings]

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

    - **Drempelwaarde voor verlenging (%)**: 20% wordt aanbevolen.
    - **Geldigheidsduur van certificaat**: Als u de certificaatsjabloon niet hebt gewijzigd, kan deze optie worden ingesteld op één jaar.
    - **Sleutelarchiefprovider (KSP)**: Voor Windows selecteert u waar u de sleutels op het apparaat wilt opslaan.
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
    - **Sleutelarchiefprovider (KSP)**: Voor Windows selecteert u waar u de sleutels op het apparaat wilt opslaan.

4. Selecteer **OK** > **Maken** om het profiel op te slaan.
5. Raadpleeg [Microsoft Intune-apparaatprofielen toewijzen](device-profile-assign.md) om het nieuwe profiel aan een of meer apparaten toe te wijzen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

[Gebruik SCEP-certificaten](certificates-scep-configure.md) of [geef PKCS-certificaten uit van een webservice van Symantec PKI-manager](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navigeren naar Intune in Azure Portal en een nieuw profiel voor een vertrouwd certificaat maken"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Een profiel maken en een vertrouwd certificaat uploaden"
[ConnectorDownload]: ./media/certificates-download-connector.png "De certificaatconnector downloaden van Azure Portal"  
