---
title: Android-apps verpakken met App Wrapping Tool | Microsoft Intune
description: Gebruik de informatie in dit onderwerp om meer te leren over het inpakken van uw Android-apps zonder de code van de app zelf te wijzigen. Bereid de apps voor, zodat u de Mobile App Management-beleidsregels kunt toepassen.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: matgates
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: 061bde9155c30bf8d7063d40478bbdf35fc7b53a


---

# Android-apps voorbereiden voor Mobile Application Management met de Intune App Wrapping Tool
Gebruik de **Microsoft Intune App Wrapping Tool voor Android** om het gedrag van uw ingebouwde Android-apps te wijzigen zodat u functies van de app kunt configureren zonder de code van de app zelf te wijzigen.

Het hulpprogramma is een Windows-opdrachtregelprogramma dat wordt uitgevoerd in PowerShell en een schil om uw app maakt. Nadat de app is verwerkt, kunt u vervolgens de app-functionaliteit wijzigen met [ Mobile Application Management-beleid](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) dat u configureert.

Als uw app de Azure Active Directory Authentication Library (ADAL) gebruikt, moet u, voordat u uw app inpakt, de stappen uitvoeren in [Hoe u apps inpakt die de Azure Active Directory Library gebruiken](#how-to-wrap-apps-that-use-the-azure-active-directory-library). Als u niet zeker weet of uw app gebruikmaakt van deze bibliotheek, neemt u contact op met de ontwikkelaar van de app.

Controleer de [Beveiligingsoverwegingen voor het uitvoeren van App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool) voordat u het hulpprogramma uitvoert. Zie [Microsoft Intune App Wrapping Tool for Android](https://www.microsoft.com/download/details.aspx?id=47267) als u het hulpprogramma wilt downloaden.

## Stap 1: voldoe aan de vereisten voor het gebruik van de App Wrapping Tool

-   U moet de App Wrapping Tool uitvoeren op een Windows-computer met Windows 7 of hoger.

-   Uw invoerapp moet een geldig Android-toepassingspakket zijn met de extensie **.apk** en:

    -   Mag niet versleuteld zijn

    -   Mag niet al zijn ingepakt door de App Wrapping Tool

    -   Moet zijn geschreven voor Android 4.0 of hoger

-   De app moet zijn ontwikkeld door of voor uw bedrijf. U kunt dit hulpprogramma niet gebruiken om apps te verwerken die zijn gedownload uit de Google Play Store.

-   Als u de App Wrapping Tool wilt uitvoeren, moet u de nieuwste versie van [Java Runtime Environment](http://java.com/download/) installeren en vervolgens controleren of het variabele Java-pad is ingesteld op **C:\ProgramData\Oracle\Java\javapath** in de Windows-omgevingsvariabelen. Zie voor meer informatie over de [Java-documentatie](http://java.com/download/help/).

    > [!NOTE]
    > In bepaalde gevallen kan de 32-bits versie van Java leiden tot geheugenproblemen. Het wordt aangeraden om in plaats daarvan de 64-bits versie te installeren.

## Stap 2: installeer de App Wrapping Tool

1.  Download het installatiebestand voor de App Wrapping Tool uit het Microsoft Download Center naar een Windows-computer en open het bestand.

2.  Accepteer de gebruiksrechtovereenkomst en voltooi de installatie.

Onthoud in welke map het hulpprogramma is geïnstalleerd. De standaardlocatie is: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Stap 3: voer de App Wrapping Tool uit

1.  Open in de beheerdersmodus een PowerShell-venster op de Windows-computer waarop de App Wrapping Tool is geïnstalleerd.

2.  Importeer de App Wrapping Tool PowerShell-module uit de map waarin u het programma hebt geïnstalleerd:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Voer het hulpprogramma uit met behulp van de opdracht **invoke-AppWrappingTool**, in combinatie met de volgende parameters: Parameters die zijn aangeduid als 'optioneel', zijn bedoeld voor apps die Azure Active Directory Library (ADAL) gebruiken. Zie [Hoe u apps inpakt die de Azure Active Directory Library gebruiken](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

|Parameter|Meer informatie|Voorbeelden|
|-------------|--------------------|---------|
|**-InputPath**&lt;tekenreeks&gt;|Pad van de Android-bron-app (.apk).| |
|**-OutputPath**&lt;tekenreeks&gt;|Pad naar de uit te voeren Android-app. Als dit hetzelfde mappad is als InputPath, mislukt het inpakken.| |
|**-KeyStorePath**&lt;tekenreeks&gt;|Pad naar het sleutelopslagbestand met het openbare/persoonlijke sleutelpaar voor ondertekening.| |
|**-KeyStorePassword**&lt;SecureString&gt;|Wachtwoord voor het ontsleutelen van de sleutelopslag. Android vereist dat alle toepassingspakketten (.apk) zijn ondertekend. Gebruik de Java keytool voor het genereren van het KeyStorePassword zoals weergegeven in het voorbeeld. Meer informatie over [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).|keytool.exe -genkey -v -keystore keystorefile -alias ks -keyalg RSA -keysize 2048 -validity 50000 |
|**-KeyAlias**&lt;tekenreeks&gt;|Naam van de sleutel die moet worden gebruikt voor het ondertekenen.| |
|**-KeyPassword**&lt;SecureString&gt;|Wachtwoord dat wordt gebruikt om de persoonlijke sleutel te ontsleutelen die wordt gebruikt voor het ondertekenen.| |
|**-SigAlg**&lt;SecureString&gt;|Naam van het algoritme voor de handtekening dat moet worden gebruikt voor de ondertekening. Het algoritme moet compatibel zijn met de persoonlijke sleutel.|Voorbeelden: SHA256withRSA, SHA1withRSA, MD5withRSA|
|**-ClientID**&lt;GUID&gt;|Id van de Azure Active Directory-client van de invoer-app (optioneel).| |
|**-AuthorityURI**&lt;Uri&gt;|Authority-URI van Azure Active Directory van de invoer-app (optioneel).| |
|**-SkipBroker**&lt;Booleaanse waarde&gt;|Geeft aan of de invoertoepassing ondersteuning biedt voor brede, door het apparaat verwerkte eenmalige aanmelding (optioneel). |**Waar**: de invoertoepassing biedt geen ondersteuning voor brede, door het apparaat verwerkte eenmalige aanmelding Gebruik de parameter NonBrokerRedirectURI. **Onwaar**: de invoertoepassing biedt ondersteuning voor brede, door het apparaat verwerkte eenmalige aanmelding|
|**-NonBrokerRedirectURI**&lt;URI&gt;|Te gebruiken omleidings-URI voor Azure Active Directory als SkipBroker waar is (optioneel).|  |


**&lt;CommonParameters&gt;**
    (optioneel – biedt ondersteuning voor algemene PowerShell-parameters zoals uitgebreid, foutopsporing, enz.)

- Zie voor een lijst met algemene parameters het [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Om Help voor het hulpprogramma weer te geven, gebruikt u de opdracht:

    ```
    Help Invoke-AppWrappingTool
    ```
- Meer informatie over de integratie van Azure Active Directory (AAD) vindt u in [Hoe u apps inpakt die de Azure Active Directory Library gebruiken](#how-to-wrap-apps-that-use-the-azure-active-directory-library).

**Voorbeeld:**


    Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
    invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app.wrapped\HelloWorld_wrapped2.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\keystorefile" -keyAlias ks -SigAlg SHA1withRSA -Verbose

U wordt vervolgens gevraagd om het **KeyStorePassword** en **KeyPassword**.

De ingepakte app wordt gegenereerd en samen met een logboekbestand in het uitvoerpad opgeslagen dat u hebt opgegeven.

## Beveiligingsoverwegingen voor het uitvoeren van de App Wrapping Tool
Potentiële adresvervalsing (spoofing), vrijgeven van informatie en uitbreiding van bevoegdheden voorkomen:

-   Zorg ervoor dat de invoer-Line-Of-Business-toepassing, uitvoertoepassing en Java KeyStore zich op de computer bevinden waarop de App Wrapping Tool wordt uitgevoerd.

-   Importeer de uitvoertoepassing naar de Intune-console op dezelfde computer waarop het hulpprogramma wordt uitgevoerd. Zie [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) voor meer informatie over de Java keytool.

-   Als de uitvoertoepassing en het hulpprogramma zich op een pad (Universal Naming Convention) bevinden en u het hulpprogramma en de invoerbestanden niet op dezelfde computer uitvoert, configureert u de omgeving zodanig dat deze wordt beveiligd met [IP-beveiligingsbeleid (IPsec)](http://en.wikipedia.org/wiki/IPsec) of [Server Message Block (SMB) ondertekening](https://support.microsoft.com/en-us/kb/887429).

-   Zorg ervoor dat de toepassing afkomstig is van een betrouwbare bron, met name als u Azure Active Directory (AAD) gebruikt, waarmee de toepassing tijdens de runtime toegang tot het AAD-token kan krijgen.

-   Beveilig de uitvoermap die de ingepakte app bevat. Overweeg het gebruik van een map op gebruikersniveau voor de uitvoer.

## Hoe u apps inpakt die de Azure Active Directory Library gebruiken
Als uw app de Azure Active Directory Authentication Library (ADAL) gebruikt, moet u deze stappen voltooien voordat u uw app inpakt.

### Stap 1: zorg ervoor dat u voldoet aan de vereisten voor ADAL
Voor apps die gebruikmaken van de ADAL, moet het volgende waar zijn:

-   In de app moet ADAL-versie 1.0.2 of hoger zijn opgenomen.

-   De ontwikkelaar moet de app toegang verlenen tot de Intune Mobile Application Management-resource, zoals beschreven in [Stap 3: configureer de toegang tot Mobile Application Management in AAD](#step-3-configure-access-to-mobile-app-management-in-aad).

### Stap 2: controleer de id's die u nodig hebt om de app te registreren
In de volgende stap gebruikt u de Azure-beheerportal om uw apps te registreren (die ADAL met Azure Active Directory (AAD) gebruiken) en de unieke id's te krijgen die in de volgende tabel staan vermeld. Vervolgens geeft u de id's aan de ontwikkelaar wanneer u ADAL in de app integreert.

|Id|Meer informatie|Standaardwaarde|
|--------------|--------------------|-----------------|
|**Client-id**|Een unieke GUID-id die voor de app wordt gegenereerd nadat deze is geregistreerd bij AAD.<br /><br />Als u de client-id van de app weet, geef die waarde dan op. Gebruik anders de standaardwaarde.|6c7e8096-f593-4d72-807f-a5f86dcc9c77|
|**Authority-URI**|De Authority Uniform Resource Identifier (URI)-waarde voor AAD-objecten (bijvoorbeeld gebruikers en groepen).<br /><br />De parameter AuthorityURI is optioneel voor de App Wrapping Tool. De standaard-URI wordt gebruikt als u de parameter niet gebruikt.||
|**SkipBroker**|Waarde die aangeeft of de bedrijfsportal wordt gebruikt als broker.<br /><br />**Waar**: bedrijfsportal wordt niet gebruikt voor ADAL-verificatie.<br /><br />**Onwaar**: bedrijfsportal wordt gebruikt voor ADAL-verificatie. De bedrijfsportal gebruikt de geregistreerde gebruiker voor eenmalige aanmeldingen.||
|**Omleidings-URI bij geen broker**|Aanmeldings-URI die moet worden gebruikt wanneer ADAL de broker-app niet gebruikt (Intune-bedrijfsportal).|urn:ietf:wg:oauth:2.0:oob|
|**Bron-id**|Verwijzing naar de AAD-bronnen van de app.||

### Stap 3: configureer de toegang tot Mobile Application Management in AAD
Voordat u de AAD-registratiewaarden van een app in de App Wrapping Tool kunt gebruiken, moet de ontwikkelaar van de app die app toegang verlenen tot de Intune Mobile Application Management-bron, gevolgd door de volgende stappen:

1.  Meld u aan bij een bestaand AAD-account in de Azure-beheerportal.

2.  Kies **bestaande LOB-toepassing inschrijven**.

3.  Kies in de sectie **Configureren** de optie **Toegang tot web-API's in andere toepassingen configureren**.

4.  Kies in de eerste vervolgkeuzelijst in het gedeelte **Machtiging voor andere toepassingen** de optie **Intune Mobile Application Management**.

U kunt nu de client-id van de app gebruiken in de App Wrapping Tool. U vindt de client-id in de Azure Active Directory-beheerportal, zoals beschreven in de tabel in [stap 2: controleer de id's die u nodig hebt om de app te registreren](#step-2-review-the-identifiers-you-need-to-get-when-you-register-the-app).

### Stap 4: gebruik de id-waarden van AAD in de App Wrapping Tool
Met de id-waarden die u tijdens het registratieproces hebt gekregen, geeft u de waarden als opdrachtregeleigenschappen in de App Wrapping Tool op. U moet alle waarden in de tabel opgeven, zodat eindgebruikers de app kunnen verifiëren. Als u een waarde niet opgeeft, wordt daarvoor de standaardwaarden gebruikt.

|Id|Parameter|
|--------------|-------------|
|Client-id|ClientID|
|Authority-URI|Authority-URI|
|SkipBroker|SkipBroker|
|Omleidings-URI bij geen broker|NonBrokerRedirectURI|
|Bron-id|ResourceID|
Houd rekening met de volgende punten wanneer u uw app inpakt:

-   Om te controleren of de verificatie is gelukt, haalt [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] het AAD-token op dat gekoppeld is aan de resource-id van de MAM. Het token wordt echter in geen enkele aanroep gebruikt die de geldigheid van de token valideert. [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] leest alleen de UPN (User Principal Name) van de aangemelde gebruiker om app-toegang te bepalen. De AAD-token wordt niet gebruikt voor verdere serviceaanroepen.

-   Dubbele aanmeldingsprompts worden voorkomen als u de client-id en Authority-URI voor uw clienttoepassing opgeeft. U moet de client-id registreren om ervoor te zorgen dat deze toegang krijgt tot de gepubliceerde [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] MAM-bron-id in het AAD-dashboard. Als u de client-id niet registreert, krijgen gebruikers te maken met een mislukte aanmelding als ze apps uitvoeren.


### Zie tevens
- [Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [De SDK gebruiken om apps geschikt te maken voor Mobile Application Management](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Jul16_HO5-->


