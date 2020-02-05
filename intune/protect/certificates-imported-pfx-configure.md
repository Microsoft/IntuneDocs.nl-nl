---
title: Geïmporteerde PFX-certificaten gebruiken in Microsoft Intune - Azure | Microsoft Docs
description: Geïmporteerde PKCS-certificaten (Public Key Cryptography Standards) gebruiken met Microsoft Intune, inclusief het importeren van certificaten, het configureren van certificaatsjablonen, het installeren van de Intune Imported PFX Certificate Connector en het maken van een geïmporteerd PKCS-certificaatprofiel.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/10/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda; rimarram
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 469ee615cd9a9f1d3a7aee40ce764b8d8100fe69
ms.sourcegitcommit: c46b0c2d4507be6a2786a4ea06009b2d5aafef85
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/01/2020
ms.locfileid: "76912894"
---
# <a name="configure-and-use-imported-pkcs-certificates-with-intune"></a>Geïmporteerde PKCS-certificaten configureren en gebruiken met Intune

Microsoft Intune ondersteunt het gebruik van geïmporteerde PKCS-certificaten (openbare sleutelparen), die meestal worden gebruikt voor S/MIME-versleuteling met e-mailprofielen. Bepaalde e-mailprofielen in Intune ondersteunen een optie om S/MIME in te schakelen, waarbij u een S/MIME-handtekeningscertificaat en een S/MIME-versleutelingscertificaat kunt definiëren.

S/MIME-versleuteling is uitdagend, omdat e-mail wordt versleuteld met een specifiek certificaat. U moet op het apparaat waarop u het e-mailbericht leest beschikken over de persoonlijke sleutel van het certificaat dat is gebruikt om het e-mailbericht te versleutelen, zodat het kan worden ontsleuteld. Versleutelingscertificaten worden regelmatig vernieuwd. Dit betekent dat u mogelijk de versleutelingsgeschiedenis op al uw apparaten nodig hebt om ervoor te zorgen dat u oudere e-mailberichten kunt lezen.  Omdat hetzelfde certificaat moet worden gebruikt op meerdere apparaten, is het niet mogelijk [SCEP](certificates-scep-configure.md)- of [PKCS](certficates-pfx-configure.md)-certificaatprofielen te gebruiken voor dit doel, omdat deze mechanismen voor het aanleveren van certificaten per apparaat unieke certificaten leveren.

Voor meer informatie over het gebruik van s/MIME met Intune raadpleegt u [S/MIME gebruiken voor e-mailversleuteling](certificates-s-mime-encryption-sign.md).

## <a name="requirements"></a>Vereisten

Als u geïmporteerde PKCS-certificaten wilt gebruiken met Intune, hebt u de volgende infrastructuur nodig:

- **PFX-certificaatconnector voor Microsoft Intune**:

  Elke Intune-tenant ondersteunt één instantie van deze connector. U kunt deze connector op dezelfde server installeren als een instantie van de Microsoft Intune Certificate Connector.

  Deze connector verwerkt aanvragen voor PFX-bestanden die zijn geïmporteerd in Intune voor S/MIME-e-mailversleuteling voor een specifieke gebruiker.

  Deze connector kan automatisch worden bijgewerkt wanneer nieuwe versies beschikbaar komen. Om de update-mogelijkheid te gebruiken, moet u ervoor zorgen dat firewalls zo zijn ingesteld dat de connector verbinding kan maken met **autoupdate.msappproxy.net** via poort **443**.

  Zie, voor meer informatie over alle netwerkeindpunten die de connector benadert, de [Netwerkconfiguratievereisten en bandbreedte voor Intune](../fundamentals/network-bandwidth-use.md).

- **Windows Server**:

  U kunt een Windows-server gebruiken als host voor de PFX-certificaatconnector voor Microsoft Intune.  De connector wordt gebruikt om aanvragen te verwerken voor certificaten die in Intune worden geïmporteerd.

  Intune staat toe dat de *Microsoft Intune-certificaatconnector* en de *PFX-certificaatconnector voor Microsoft Intune* op dezelfde server worden geïnstalleerd.

  Voor de connector moet op de server .NET 4.6 Framework of hoger worden uitgevoerd. Als .NET 4.6 Framework nog niet is geïnstalleerd wanneer u de installatie van de connector start, wordt dit automatisch geïnstalleerd tijdens de installatie van de connector.

- **Visual Studio 2015 of hoger** (optioneel):

  U kunt Visual Studio gebruiken om de PowerShell-hulpmodule te maken met cmdlets voor het importeren van PFX-certificaten in Microsoft Intune. Ga naar het [PowerShell-project PFXImport op GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell) om de PowerShell-hulpcmdlets te downloaden.

## <a name="how-it-works"></a>Hoe het werkt

Wanneer u Intune gebruikt om een **geïmporteerd PFX-certificaat** voor een gebruiker te implementeren, spelen er naast het apparaat twee andere onderdelen een rol:

- **Intune-service**: Hiermee worden de PFX-certificaten in een versleutelde status opgeslagen en wordt de implementatie van het certificaat op het apparaat van de gebruiker verwerkt.  De wachtwoorden die de persoonlijke sleutels van de certificaten beveiligen, worden versleuteld met behulp van een HSM (Hardware Security Module) of Windows Cryptography voordat ze worden geüpload, zodat Intune op geen enkel moment toegang kan krijgen tot de persoonlijke sleutel.

- **PFX-certificaatconnector voor Microsoft Intune**: Wanneer een apparaat een PFX-certificaat aanvraagt dat is geïmporteerd in Intune, worden het versleutelde wachtwoord, het certificaat en de openbare sleutel van het apparaat naar de connector gestuurd.  De connector ontsleutelt het wachtwoord met behulp van de on-premises persoonlijke sleutel en versleutelt vervolgens het wachtwoord (en eventuele plist-profielen als u iOS gebruikt) met de apparaatsleutel, om daarna het certificaat terug te sturen naar Intune.  Intune stuurt vervolgens het certificaat naar het apparaat, zodat het apparaat dit kan ontsleutelen met de persoonlijke sleutel van het apparaat en het certificaat kan installeren.

## <a name="download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune"></a>De PFX-certificaatconnector voor Microsoft Intune downloaden, installeren en configureren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Certificaatconnectors** > **Toevoegen**.

   ![PFX-certificaatconnector voor Microsoft Intune downloaden](./media/certificates-imported-pfx-configure/download-imported-pfxconnector.png)

3. Volg de richtlijnen om de *PFX-certificaatconnector voor Microsoft Intune* te downloaden naar een locatie die toegankelijk is vanaf de server waarop u de connector wilt installeren.

4. Nadat het downloaden is voltooid, meldt u zich aan bij de server en voert u het installatieprogramma (PfxCertificateConnectorBootstrapper.exe) uit.  
   - Wanneer u de standaard installatielocatie accepteert, wordt de connector geïnstalleerd in `Program Files\Microsoft Intune\PFXCertificateConnector`.
   - De connectorservice wordt uitgevoerd onder het lokale systeemaccount. Als een proxy is vereist voor toegang tot internet, moet u bevestigen dat het lokale serviceaccount toegang heeft tot de proxy-instellingen op de server.

5. Het tabblad **Inschrijving** wordt na de installatie geopend. Als u de verbinding met Intune wilt inschakelen, kiest u **Aanmelden** en geeft u een account met globale beheerdersmachtigingen voor Azure of beheerdersbevoegdheden voor Intune op.

   > [!WARNING]
   > In Windows Server wordt **Configuratie verbeterde beveiliging IE** standaard ingesteld op **Ingeschakeld**, wat kan leiden tot aanmeldingsproblemen bij Office 365.

6. Sluit het venster.

7. Ga in het Microsoft Endpoint Manager-beheercentrum terug naar **Tenantbeheer** > **Connectors en tokens** > **Certificaatconnectors**. Even later wordt een groen vinkje weergegeven en wordt de verbindingsstatus bijgewerkt. Uw connector-server kan nu communiceren met Intune.

## <a name="import-pfx-certificates-to-intune"></a>PFX-certificaten importeren in Intune

U kunt [Microsoft Graph](https://docs.microsoft.com/graph) gebruiken om de PFX-certificaten van uw gebruikers te importeren in Intune. Het [PowerShell-project PFXImport op GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell) biedt u hulp-cmdlets waarmee u de bewerkingen eenvoudig kunt uitvoeren.

Als u liever uw eigen aangepaste oplossing met behulp van Graph gebruikt, gebruikt u het [resourcetype userPFXCertificate](https://docs.microsoft.com/graph/api/resources/intune-raimportcerts-userpfxcertificate?view=graph-rest-beta).

### <a name="build-pfximport-powershell-project-cmdlets"></a>Cmdlets voor het 'PowerShell-project PFXImport' maken

Als u gebruik wilt maken van de PowerShell-cmdlets, bouwt u het project zelf met behulp van Visual Studio. Het proces is eenvoudig en, hoewel u het kunt uitvoeren op de server, raden we aan dit uit te voeren op uw werkstation.  

1. Ga naar de hoofdmap van de opslagplaats [Intune-Resource-Access](https://github.com/microsoft/Intune-Resource-Access) op GitHub en download of kloon de opslagplaats met Git naar uw machine.

   ![Knop Downloaden op GitHub](./media/certificates-imported-pfx-configure/github-download.png)

2. Ga naar `.\Intune-Resource-Access-develop\src\PFXImportPowershell\` en open het project met Visual Studio met behulp van het bestand **PFXImportPS.sln**.

3. Bovenin wijzigt u **Debug** naar **Release**.

4. Ga naar **Compileren** en selecteer **PFXImportPS compileren**. Na enkele ogenblikken wordt de bevestiging **Compileren voltooid** weergegeven in de linkerbenedenhoek van Visual Studio.

   ![Optie Compileren in Visual Studio](./media/certificates-imported-pfx-configure/vs-build-release.png)

5. Tijdens het compilatieproces wordt een nieuwe map met de PowerShell-module gemaakt in `.\Intune-Resource-Access-develop\src\PFXImportPowershell\PFXImportPS\bin\Release`.

   U gebruikt deze **Release**-map voor de volgende stappen.

### <a name="create-the-encryption-public-key"></a>De openbare sleutel voor versleuteling maken

U importeert PFX-certificaten en hun persoonlijke sleutels naar Intune. Het wachtwoord dat de persoonlijke sleutel beveiligt, wordt versleuteld met een openbare sleutel die on-premises wordt opgeslagen. U kunt Windows-cryptografie, een hardware-beveiligingsmodule of een ander type cryptografie gebruiken om de openbare/persoonlijke sleutelparen te genereren en op te slaan.  Afhankelijk van het gebruikte type cryptografie, kunnen de sleutelparen met openbare/persoonlijke sleutels voor back-updoeleinden worden geëxporteerd in een bestandsindeling.

De PowerShell-module biedt methoden om een sleutel te maken met behulp van Windows-cryptografie. U kunt ook andere hulpprogramma's gebruiken om een sleutel te maken.  

#### <a name="to-create-the-encryption-key-using-windows-cryptography"></a>De versleutelingssleutel maken met behulp van Windows-cryptografie

1. Kopieer de *Release*-map die door Visual Studio is gemaakt naar de server waarop u de **PFX-certificaatconnector voor Microsoft Intune** hebt geïnstalleerd. Deze map bevat de PowerShell-module.

2. Open op de server *PowerShell* als beheerder en navigeer naar de *Release*-map die de PowerShell-module bevat.

3. Als u de module wilt importeren, voert u `Import-Module .\IntunePfxImport.psd1` uit om de module te importeren.

4. Voer vervolgens `Add-IntuneKspKey "Microsoft Software Key Storage Provider" "PFXEncryptionKey"` uit.

   > [!TIP]
   > De provider die u gebruikt, moet opnieuw worden geselecteerd wanneer u een PFX-certificaat importeert. U kunt de **Microsoft Software Key Storage Provider** gebruiken, maar het gebruik van een andere provider wordt ook ondersteund. De gebruikte sleutelnaam is een voorbeeld; u kunt een andere sleutelnaam naar keuze gebruiken.

   Als u van plan bent om het certificaat vanaf uw werkstation te importeren, kunt u deze sleutel exporteren naar een bestand met de volgende opdracht:  `Export-IntunePublicKey -ProviderName "<ProviderName>" -KeyName "<KeyName>" -FilePath "<File path\Filename.PFX>"`

   De persoonlijke sleutel moet worden geïmporteerd op de server die als host fungeert voor de PFX-certificaatconnector voor Microsoft Intune, zodat geïmporteerde PFX-certificaten correct kunnen worden verwerkt.

#### <a name="to-use-a-hardware-security-module-hsm"></a>Een Hardware Security Module (HSM) gebruiken

U kunt een HSM gebruiken om het sleutelpaar met een openbare en persoonlijke sleutel te genereren en op te slaan. Zie de documentatie van de HSM-provider voor meer informatie.

### <a name="import-pfx-certificates"></a>PFX-certificaten importeren

Het volgende proces maakt gebruik van de PowerShell-cmdlets als voorbeeld van hoe u PFX-certificaten kunt importeren. U kunt verschillende opties kiezen, afhankelijk van uw vereisten.

Opties zijn onder andere:

- Beoogd doel (de certificaten worden gegroepeerd op basis van een tag):
  - unassigned
  - smimeEncryption
  - smimeSigning

- Opvullingsschema:
  - oaepSha256
  - oaepSha384
  - oaepSha512

Selecteer de sleutelopslagprovider die overeenkomt met de provider die u hebt gebruikt om de sleutel te maken.

#### <a name="to-import-the-pfx-certificate"></a>Het PFX-certificaat importeren  

1. Exporteer de certificaten van een certificeringsinstantie (Certification Authority, CA) aan de hand van de documentatie van de provider.  Voor Microsoft Active Directory Certificate Services kunt u dit [voorbeeldscript](https://gallery.technet.microsoft.com/Export-CMPfxCertificatesFro-d55f687b)gebruiken.

2. Open op de server *PowerShell* als beheerder en navigeer naar de *Release*-map die de PowerShell-module bevat.

3. Voer `Import-Module .\IntunePfxImport.psd1` uit om de module te importeren

4. Voer `$authResult = Get-IntuneAuthenticationToken -AdminUserName "<Admin-UPN>"` uit om te verifiëren bij Intune Graph

   > [!NOTE]
   > Omdat de verificatie wordt uitgevoerd bij Graph, moet u machtigingen verlenen voor de AppID. Als dit de eerste keer is dat u dit hulpprogramma gebruikt, moet u een *globale beheerder* zijn. De PowerShell-cmdlets gebruiken dezelfde AppID als die in de [voorbeelden voor PowerShell Intune](https://github.com/microsoftgraph/powershell-intune-samples).

5. Converteer het wachtwoord voor elk PFX-bestand dat u importeert naar een beveiligde tekenreeks door `$SecureFilePassword = ConvertTo-SecureString -String "<PFXPassword>" -AsPlainText -Force` uit te voeren.

6. Voer `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>"` uit om een **UserPFXCertificate**-object te maken

   Bijvoorbeeld: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "C:\temp\userA.pfx" $SecureFilePassword "userA@contoso.com" "Microsoft Software Key Storage Provider" "PFXEncryptionKey" "smimeEncryption"`

   > [!NOTE]
   > Wanneer u het certificaat importeert van een ander systeem dan de server waarop de connector is geïnstalleerd, gebruikt u de volgende opdracht, die het pad naar het sleutelbestand bevat: `$userPFXObject = New-IntuneUserPfxCertificate -PathToPfxFile "<FullPathPFXToCert>" $SecureFilePassword "<UserUPN>" "<ProviderName>" "<KeyName>" "<IntendedPurpose>" "<PaddingScheme>" "<File path to public key file>"`

7. Importeer het **UserPFXCertificate**-object in Intune door `Import-IntuneUserPfxCertificate -AuthenticationResult $authResult -CertificateList $userPFXObject` uit te voeren

8. Voer `Get-IntuneUserPfxCertificate -AuthenticationResult $authResult -UserList "<UserUPN>"` uit om te controleren of het certificaat is geïmporteerd

Voor meer informatie over andere beschikbare opdrachten, raadpleegt u het leesmij-bestand in het [PowerShell-project PFXImport op GitHub](https://github.com/microsoft/Intune-Resource-Access/tree/develop/src/PFXImportPowershell).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Een geïmporteerd PKCS-certificaatprofiel maken

Na het importeren van de certificaten naar Intune maakt u een **geïmporteerd PKCS-certificaatprofiel** en wijst u dit toe aan Azure Active Directory-groepen.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofiel** > **Profiel maken**.

3. Voer de volgende eigenschappen in:

   - **Naam** voor het profiel
   - Een beschrijving instellen (optioneel)
   - **Platform** waarvoor het profiel moet worden geïmplementeerd
   - Stel **Profieltype** in op **Geïmporteerd PKCS-certificaat**

4. Selecteer **Instellingen** en voer de volgende eigenschappen in:

   - **Beoogd doeleinde**: Geef het beoogde doel op van de certificaten die voor dit profiel worden geïmporteerd. Beheerders kunnen certificaten importeren met verschillende beoogde doelen (zoals S/MIME-ondertekening of S/MIME-versleuteling). Het beoogde doel dat is geselecteerd in het certificaatprofiel komt overeen met het certificaatprofiel met de juiste geïmporteerde certificaten. Het beoogde doel is een tag om een groep geïmporteerde certificaten te groeperen. Dit garandeert niet dat certificaten die met die tag worden geïmporteerd, voldoen aan het beoogde doel.  
   - **Geldigheidsduur van certificaat**: Tenzij de geldigheidsperiode in de certificaatsjabloon is gewijzigd, wordt deze optie standaard op één jaar ingesteld.
   - **Sleutelarchiefprovider (KSP)**: Voor Windows selecteert u waar u de sleutels op het apparaat wilt opslaan.

5. Selecteer **OK** > **Maken** om het profiel op te slaan.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. [Wijs](../configuration/device-profile-assign.md) het nieuwe apparaatprofiel toe.
