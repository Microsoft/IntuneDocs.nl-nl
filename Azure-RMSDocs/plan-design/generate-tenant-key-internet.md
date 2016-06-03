---
# required metadata

title: Uw eigen tenantsleutel genereren en overdragen via internet | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 1bff9b06-8c5a-4b1d-9962-6668219210e6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


# Uw eigen tenantsleutel genereren en overdragen via internet

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de volgende procedures als u [uw tenantsleutel zelf wilt beheren](plan-implement-tenant-key.md#choose-your-tenant-key-topology-managed-by-microsoft-the-default-or-managed-by-you-byok-) en u deze wilt overdragen via internet in plaats van naar een vestiging van Microsoft te reizen om de tenantsleutel persoonlijk over te dragen:


## Uw met internet verbonden werkstation voorbereiden
Volg deze drie stappen om uw op internet aangesloten werkstation voor te bereiden:

-   [Stap 1: installeer Windows PowerShell voor Azure Rights Management](#step-1-install-windows-powershell-for-azure-rights-management)

-   [Stap 2: haal de tenant-id voor uw Azure Active Directory op](#step-2-get-your-azure-active-directory-tenant-id)

-   [Stap 3: download de BYOK-hulpmiddelenset](#step-3-download-the-byok-toolset)

### Stap 1: installeer Windows PowerShell voor Azure Rights Management
Download en installeer de Windows PowerShell-module voor Azure Rights Management vanaf het met internet verbonden werkstation.

> [!NOTE]
> Als u deze Windows PowerShell-module eerder hebt gedownload, voert u de volgende opdracht uit om te controleren of u minimaal over versie nummer 2.1.0.0 beschikt: `(Get-Module aadrm -ListAvailable).Version`

Zie [Windows PowerShell voor Azure Rights Management installeren](../deploy-use/install-powershell.md) voor de installatie-instructies.

### Stap 2: haal de tenant-id voor uw Azure Active Directory op
Start Windows PowerShell met de optie **Als administrator uitvoeren** en voer de volgende opdrachten uit:

-   Gebruik de cmdlet [Connect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629415.aspx) om verbinding te maken met de Azure RMS-service:

    ```
    Connect-AadrmService
    ```
    Wanneer u erom wordt gevraagd, typt u uw [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]-tenantbeheerderreferenties (meestal gebruikt u een account dat een globale beheerder is voor Azure Active Directory of Office 365).

-   Gebruik de cmdlet [Get-AadrmConfiguration](http://msdn.microsoft.com/library/windowsazure/dn629410.aspx) om de configuratie van uw tenant weer te geven:

    ```
    Get-AadrmConfiguration
    ```
    Sla de GUID van de eerste regel (BPOSId) van de uitvoer op. Dit is uw tenant-id voor Azure Active Directory, die u later nodig hebt om uw tenantsleutel voor te bereiden voor het uploaden.

-   Gebruik de cmdlet [Disconnect-AadrmService](http://msdn.microsoft.com/library/windowsazure/dn629416.aspx) om de verbinding met de Azure RMS-service te verbreken wanneer u klaar bent om uw sleutel te uploaden:

    ```
    Disconnect-AadrmService
    ```

Sluit het Windows PowerShell-venster niet.

### Stap 3: download de BYOK-hulpmiddelenset
Ga naar het Microsoft Downloadcentrum en [download de BYOK-hulpmiddelenset](http://go.microsoft.com/fwlink/?LinkId=335781) voor uw regio:

|Regio|Naam van het pakket|
|----------|----------------|
|Noord-Amerika|AzureRMS-BYOK-tools-UnitedStates.zip|
|Europa|AzureRMS-BYOK-tools-Europe.zip|
|Azië|AzureRMS-BYOK-tools-AsiaPacific.zip|
De hulpmiddelenset bevat het volgende:

-   Een KEK-pakket (Key Exchange Key) met een naam die begint met **BYOK-KEK-pkg-**.

-   Een beveiligingswereldpakket met een naam die begint met **BYOK-SecurityWorld-pkg-**.

-   Een pythonscript met de naam **verifykeypackage.py**.

-   Een uitvoerbaar opdrachtregelbestand met de naam **KeyTransferRemote.exe**, een metagegevensbestand met de naam **KeyTransferRemote.exe.config** en bijbehorende DLL-bestanden.

-   Een herdistribueerbaar Visual C++ pakket, met de naam **vcredist_x64.exe**.

Kopieer het pakket naar een USB-station of ander draagbaar opslagmedium.

## Uw niet-verbonden werkstation voorbereiden
Om uw niet met internet (of met uw interne netwerk) verbonden werkstation voor te bereiden, volgt u deze twee stappen:

-   [Stap 1: bereid het niet-verbonden werkstation met Thales HSM voor](#step-1-prepare-the-disconnected-workstation-with-thales-hsm)

-   [Stap 2: installeer de BYOK-hulpmiddelenset op het niet-verbonden werkstation](#step-2-install-the-byok-toolset-on-the-disconnected-workstation)

### Stap 1: bereid het niet-verbonden werkstation met Thales HSM voor
Op het niet-verbonden werkstation: installeer de nCipher-ondersteuningssoftware (Thales) op een Windows-computer en sluit vervolgens een Thales HSM aan op die computer.

Zorg ervoor dat de Thales-hulpprogramma's zich bevinden binnen uw pad **(%nfast_home%\bin** en **%nfast_home%\python\bin**). Typ bijvoorbeeld het volgende:

```
set PATH=%PATH%;”%nfast_home%\bin”;”%nfast_home%\python\bin”
```
Zie voor meer informatie de handleiding inbegrepen bij de Thales HSM of ga naar de Thales-website voor Azure RMS op [http://www.thales-esecurity.com/msrms/cloud](http://www.thales-esecurity.com/msrms/cloud).

### Stap 2: installeer de BYOK-hulpmiddelenset op het niet-verbonden werkstation
Kopieer het pakket met de BYOK-hulpmiddelenset van het USB-station of het andere draagbare opslagmedium en doe daarna het volgende:

1.  Pak de bestanden in het gedownloade pakket uit naar een map.

2.  Voer vcredist_x64.exe uit in die map.

3.  Volg de instructies om de Visual C++ runtime-onderdelen voor Visual Studio 2012 te installeren.

## Uw tenantsleutel genereren
Volg deze drie stappen op het niet-verbonden werkstation om uw eigen tenantsleutel te genereren:

-   [Stap 1: maak een beveiligingswereld](#step-1-create-a-security-world)

-   [Stap 2: valideer het gedownloade pakket](#step-2-validate-the-downloaded-package)

-   [Stap 3: maak een nieuwe sleutel](#step-3-create-a-new-key)

### Stap 1: maak een beveiligingswereld
Start een opdrachtprompt en voer het nieuwe-wereld-programma van Thales uit.

```
new-world.exe --initialize --cipher-suite=DLf1024s160mRijndael --module=1 --acs-quorum=2/3
```
Dit programma maakt een **Beveiligingswereld**-bestand op %NFAST_KMDATA%\local\world, wat overeenkomt met de map C:\ProgramData\nCipher\Key Management Data\local. U kunt andere waarden gebruiken voor het quorum, maar in ons voorbeeld wordt u gevraagd drie lege kaarten en pincodes voor elk adres in te voeren. Daarna hebt u een van de twee kaarten nodig voor beheerderstoegang tot de beveiligingswereld (uw opgegeven quorum).  Deze kaarten worden de **Beheerderskaartenset** voor de nieuwe beveiligingswereld. U kunt in dit stadium het wachtwoord of de pincode opgeven voor elke ACS-kaart of deze later toevoegen met een opdracht.

> [!TIP]
> U kunt de huidige status van de configuratie van uw HSM controleren met de opdracht `nkminfo`.

Ga als volgt verder:

1.  Installeer de Thales CNG-provider zoals beschreven in de Thales-documentatie en configureer deze voor gebruik van de nieuwe beveiligingswereld.

2.  Maak een back-up van het wereldbestand in **%nfast_kmdata%\local**. Beveilig en bescherm het wereldbestand, de beheerderskaarten en de bijbehorende pincodes en zorg ervoor dat niemand toegang heeft tot meer dan één kaart.

### Stap 2: valideer het gedownloade pakket
Deze stap is optioneel maar wordt aanbevolen, zodat u het volgende kunt valideren:

-   De sleutel voor sleuteluitwisseling (KEK-sleutel) die is opgenomen in de hulpmiddelenset, is gegenereerd met een legitieme Thales HSM.

-   De hash van de Azure RMS-beveiligingswereld die is opgenomen in de hulpmiddelenset, is gegenereerd met een legitieme Thales HSM.

-   De sleutel voor sleuteluitwisseling (KEK-sleutel) is niet exporteerbaar.

> [!NOTE]
> Als u het gedownloade pakket wilt valideren, moet de HSM zijn verbonden, zijn ingeschakeld en zijn voorzien van een beveiligingswereld (zoals u net hebt gemaakt).

#### Het gedownloade pakket valideren

1.  Voer het script verifykeypackage.py uit met een van de volgende opties (afhankelijk van uw regio):

    -   Voor Noord-Amerika:

        ```
        python verifykeypackage.py -k BYOK-KEK-pkg-NA-1 -w BYOK-SecurityWorld-pkg-NA-1
        ```

    -   Voor Europa:

        ```
        python verifykeypackage.py -k BYOK-KEK-pkg-EU-1 -w BYOK-SecurityWorld-pkg-EU-1
        ```

    -   Voor Azië:

        ```
        python verifykeypackage.py -k BYOK-KEK-pkg-AP-1 -w BYOK-SecurityWorld-pkg-AP-1
        ```

    > [!TIP]
    > De Thales-software bevat een Python-interpreter in %NFAST_HOME%\python\bin

2.  Controleer of het volgende wordt weergegeven (dit geeft aan dat de validatie is geslaagd): **Resultaat: GESLAAGD**

Met dit script wordt de ondertekenaarsketen gevalideerd tot en met de Thales-hoofdsleutel. De hash van deze hoofdsleutel is ingesloten in het script en de waarde moet gelijk zijn aan **59178a47 de508c3f 291277ee 184f46c4 f1d9c639**. U kunt deze waarde ook afzonderlijk controleren door de [website van Thales](http://www.thalesesec.com/) te bezoeken.

U kunt nu een nieuwe sleutel maken die uw RMS-tenantsleutel wordt.

### Stap 3: maak een nieuwe sleutel
Genereer een CNG-sleutel met de Thales-programma’s **generatekey** en **cngimport**.

Voer de volgende opdracht uit om de sleutel te genereren:

```
generatekey --generate simple type=RSA size=2048 protect=module ident=contosokey plainname=contosokey nvram=no pubexp=
```
Volg de volgende instructies om deze opdracht uit te voeren:

-   De parameter **protect** moet worden ingesteld op de waarde **module**, zoals weergegeven. Hiermee maakt u een modulair beveiligde sleutel. De BYOK-toolset biedt geen ondersteuning voor met OCS beveiligde sleutels.

-   We raden 2048 aan als sleutelgrootte, maar ondersteunen ook 1024-bits RSA-sleutels voor bestaande AD RMS-klanten die zulke sleutels hebben en migreren naar Azure RMS.

-   Vervang de waarde van *contosokey* voor de **ident** en **plainname** door een willekeurige tekenreekswaarde. Om administratieve overhead te minimaliseren en de kans op fouten te verkleinen, raden we u aan voor beide dezelfde waarde te gebruiken en altijd kleine letters te hanteren.

-   De pubexp is leeg (standaard) in dit voorbeeld, maar u kunt specifieke waarden opgeven. Zie de Thales-documentatie voor meer informatie.

Voer daarna de volgende opdracht uit om de sleutel in CNG importeren:

```
cngimport --import -M --key=contosokey --appname=simple contosokey
```
Volg de volgende instructies om deze opdracht uit te voeren:

-   Vervang *contosokey* door dezelfde waarde die u hebt opgegeven in [Stap 1: maak een beveiligingswereld](#step-1-create-a-security-world) in het gedeelte *Uw tenantsleutel genereren*.

-   Gebruik de optie **-M**, zodat de sleutel geschikt is voor dit scenario. Zonder deze optie wordt de resulterende sleutel een gebruikersspecifieke sleutel voor de huidige gebruiker.

-   De optie **appname** is de naam van de app die wordt gerapporteerd in het sleutelbestand. Als u met deze instructies een nieuwe sleutel hebt gemaakt, hebben wij de waarde Enkel gebruikt, zoals weergegeven in de opdracht. Als u echter een bestaande, met HSM beschermde sleutel voor een AD RMS-migratie migreert naar Azure RMS, geeft u uw bestaande naam op in deze opdracht en de volgende opdrachten wanneer daarin ook de optie appname wordt gebruikt.

Met deze opdracht maakt u een Tokenized sleutelbestand in uw map %NFAST_KMDATA%\local met een naam die begint met **key_caping_`_`** gevolgd door een SID. Bijvoorbeeld: **key_caping_machine--801c1a878c925fd9df4d62ba001b94701c039e2fb**. Dit bestand bevat een versleutelde sleutel.

> [!TIP]
> U kunt de huidige configuratiestatus van uw sleutels weergeven met de opdracht `nkminfo –k`.

Maak van deze Tokenized sleutel een back-up op een veilige locatie.

> [!IMPORTANT]
> Wanneer u uw sleutel later overdraagt naar Azure RMS, kan Microsoft deze niet naar u terug exporteren. Daarom is het erg belangrijk dat u een veilige back-up maakt van uw sleutel en uw beveiligingswereld. Neem contact op met Thales voor richtlijnen en best practices om een back-up van uw sleutel te maken.

U bent nu klaar om uw tenantsleutel over te dragen naar Azure RMS.

## Uw tenantsleutel voorbereiden voor overdracht
Volg deze vier stappen op het niet-verbonden werkstation om uw eigen tenantsleutel voor te bereiden:

-   [Stap 1: maak een kopie van uw sleutel met beperkte machtigingen](#step-1-create-a-copy-of-your-key-with-reduced-permissions)

-   [Stap 2: inspecteer de nieuwe kopie van de sleutel](#step-2-inspect-the-new-copy-of-the-key)

-   [Stap 3: versleutel de sleutel met de Microsoft-uitwisselingssleutel van de sleutel](#step-3-encrypt-your-key-by-using-microsoft-s-key-exchange-key)

-   [Stap 4: kopieer uw pakket voor sleuteloverdracht naar het met internet verbonden werkstation](#step-4-copy-your-key-transfer-package-to-the-internet-connected-workstation)

### Stap 1: maak een kopie van uw sleutel met beperkte machtigingen
Doe het volgende om de machtigingen op uw tenantsleutel te beperken:

-   Voer vanaf een opdrachtprompt een van de volgende opdrachten uit (afhankelijk van uw regio):

    -   Voor Noord-Amerika:

        ```
        KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-NA-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-NA-1
        ```

    -   Voor Europa:

        ```
        KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-EU-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-EU-1
        ```

    -   Voor Azië:

        ```
        KeyTransferRemote.exe -ModifyAcls -KeyAppName simple -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-AP-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-AP-1
        ```

Wanneer u deze opdracht uitvoert, vervangt u *contosokey* door dezelfde waarde als u hebt opgegeven in [Stap 1: maak een beveiligingswereld](##step-1-create-a-security-world) in het gedeelte *Uw tenantsleutel genereren*.

U wordt gevraagd de ACS-kaarten voor uw beveiligingswereld aan te brengen en, als erom wordt gevraagd, de bijbehorende wachtwoorden of pincodes op te geven.

Wanneer de opdracht is voltooid, ziet u **Resultaat: SUCCES** en bevindt de kopie van uw tenantsleutel met beperkte machtigingen zich in het bestand met de naam key_xferacId_*&lt;contosokey&gt;*.

### Stap 2: inspecteer de nieuwe kopie van de sleutel
Voer optioneel de Thales-hulpprogramma’s uit om de minimaal vereiste machtigingen voor de nieuwe tenantsleutel te controleren:

-   aclprint.py:

    ```
    "%nfast_home%\bin\preload.exe" -m 1 -A xferacld -K contosokey "%nfast_home%\python\bin\python" "%nfast_home%\python\examples\aclprint.py"
    ```

-   kmfile-dump.exe:

    ```
    "%nfast_home%\bin\kmfile-dump.exe" "%NFAST_KMDATA%\local\key_xferacld_contosokey"
    ```

Wanneer u deze opdracht uitvoert, vervangt u *contosokey* door dezelfde waarde als u hebt opgegeven in [Stap 1: maak een beveiligingswereld](##step-1-create-a-security-world) in het gedeelte *Uw tenantsleutel genereren*.

### Stap 3: versleutel de sleutel met de Microsoft-uitwisselingssleutel van de sleutel
Voer een van de volgende opdrachten uit, afhankelijk van uw regio:

-   Voor Noord-Amerika:

    ```
    KeyTransferRemote.exe -Package -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-NA-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-NA-1 -TenantBposId GUID -KeyFriendlyName ContosoFirstkey
    ```

-   Voor Europa:

    ```
    KeyTransferRemote.exe -Package -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-EU-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-EU-1 -TenantBposId GUID -KeyFriendlyName ContosoFirstkey
    ```

-   Voor Azië:

    ```
    KeyTransferRemote.exe -Package -KeyIdentifier contosokey -ExchangeKeyPackage BYOK-KEK-pkg-AP-1 -NewSecurityWorldPackage BYOK-SecurityWorld-pkg-AP-1 -TenantBposId GUID -KeyFriendlyName ContosoFirstkey
    ```

Volg de volgende instructies om deze opdracht uit te voeren:

-   Vervang *contosokey* door de id die u hebt gebruikt om de sleutel te generen in [Stap 1: maak een beveiligingswereld](##step-1-create-a-security-world) in het gedeelte *Uw tenantsleutel genereren*.

-   Vervang *GUID* door de tenant-id van de Azure Active Directory die u hebt opgehaald in [Stap 2: haal de tenant-id van uw Azure Active Directory op](#step-2-get-your-azure-active-directory-tenant-id) in het gedeelte *Uw met internet verbonden werkstation voorbereiden*.

-   Vervang *ContosoFirstKey* door een label dat wordt gebruikt voor de naam van uw uitvoerbestand.

Wanneer dit succesvol is voltooid, wordt **Resultaat: SUCCES** weergegeven en staat er in de huidige map een nieuw bestand met de volgende naam: TransferPackage-*ContosoFirstkey*.byok

### Stap 4: kopieer uw pakket voor sleuteloverdracht naar het met internet verbonden werkstation
Gebruik een USB-station of ander draagbaar opslagmedium om het uitvoerbestand uit de vorige stap (KeyTransferPackage-*ContosoFirstkey*.byok) te kopiëren naar uw met internet verbonden werkstation.

> [!NOTE]
> Volg de beveiligingsprocedures om het bestand te beveiligen, omdat het uw persoonlijke sleutel bevat.

## Uw tenantsleutel overdragen naar Azure RMS
Volg op het met internet verbonden werkstation de volgende drie stappen om uw nieuwe tenantsleutel naar Azure RMS over te dragen:

-   [Stap 1: maak verbinding met Azure RMS](#step-1-connect-to-azure-rms)

-   [Stap 2: upload het sleutelpakket](#step-2-upload-the-key-package)

-   [Stap 3: inventariseer uw tenantsleutels zo nodig](#step-3-enumerate-your-tenant-keys-as-needed)

### Stap 1: maak verbinding met Azure RMS
Ga terug naar het Windows PowerShell-venster en typ het volgende:

1.  Maak opnieuw verbinding met de [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]-service.

    ```
    Connect-AadrmService
    ```

2.  Gebruik de cmdlet [Get-AadrmKeys](http://msdn.microsoft.com/library/windowsazure/dn629420.aspx) om uw huidige tenantsleutelconfiguratie weer te geven:

    ```
    Get-AadrmKeys
    ```

### Stap 2: upload het sleutelpakket
Gebruik de cmdlet [Add-AadrmKey](http://msdn.microsoft.com/library/windowsazure/dn629418.aspx) om het sleuteloverdrachtpakket te uploaden dat u hebt gekopieerd vanaf het niet-verbonden werkstation:

```
Add-AadrmKey –KeyFile <PathToPackageFile> -Verbose
```
> [!WARNING]
> U wordt gevraagd om deze actie te bevestigen. Let op: deze actie kan niet ongedaan worden gemaakt. Tijdens het uploaden van een tenantsleutel wordt deze sleutel automatisch de primaire tenantsleutel van uw organisatie en beginnen gebruikers met deze sleutel documenten en bestanden te beveiligen.

Wanneer het uploaden is voltooid, wordt het volgende bericht weergegeven: **De Rights Management Service heeft de sleutel toegevoegd.**

Er kan een replicatievertraging optreden wanneer de wijziging wordt doorgegeven aan alle [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]-datacenters.

### Stap 3: inventariseer uw tenantsleutels zo nodig
Gebruik de cmdlet Get-AadrmKeys opnieuw om de wijziging in uw tenantsleutel weer te geven en ook telkens wanneer u een overzicht van uw tenantsleutels wilt weergeven. De weergegeven tenantsleutels bevatten ook de oorspronkelijke tenantsleutel die Microsoft voor u heeft gegenereerd, en alle tenantsleutels die u hebt toegevoegd:

```
Get-AadrmKeys
```
De tenantsleutel die is gemarkeerd als **Actief**, is de sleutel die uw organisatie momenteel gebruikt om documenten en bestanden te beveiligen.

U hebt nu alle de stappen voltooid die nodig zijn om uw eigen sleutel via internet over te dragen en kunt nu naar de volgende stappen gaan om een planning te maken voor de tenantsleutel en voor het implementeren ervan.


> [!div class="button"]
[Volgende stappen >>](plan-implement-tenant-key.md#next-steps)




<!--HONumber=Apr16_HO4-->


