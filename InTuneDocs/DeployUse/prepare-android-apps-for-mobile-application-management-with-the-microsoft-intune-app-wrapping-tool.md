---
title: Android-apps verpakken met App Wrapping Tool | Microsoft Intune
description: Gebruik de informatie in dit onderwerp om meer te leren over het inpakken van uw Android-apps zonder de code van de app zelf te wijzigen. Bereid de apps voor, zodat u de Mobile App Management-beleidsregels kunt toepassen.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: fe3a9f2fd9ce9a3c3f776dcfd9ad3347a63d0fc1
ms.openlocfilehash: e623755cf926020bcb66d8a6d40e5cce9b46b0ae


---

# Android-apps voorbereiden voor Mobile Application Management met Intune App Wrapping Tool
Gebruik de **Microsoft Intune App Wrapping Tool voor Android** om de werking van in-house Android-apps te wijzigen door de functies van de apps te beperken zonder de code van de apps zelf te wijzigen.

Dit hulpprogramma is een Windows-opdrachtregelprogramma dat wordt uitgevoerd in PowerShell en een 'wrapper' (schil) rond uw app maakt. Als de app eenmaal is verpakt (van een 'wrapper' is voorzien), kunt u vervolgens de functionaliteit van de app wijzigen door [ Mobile Application Management-beleid](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) te configureren in Intune.


Controleer de [Beveiligingsoverwegingen voor het uitvoeren van App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool) voordat u het hulpprogramma uitvoert. Als u dit hulpprogramma wilt downloaden, gaat u naar [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) op GitHub.



## Stap 1: voldoe aan de vereisten voor het gebruik van de App Wrapping Tool

-   U moet de App Wrapping Tool uitvoeren op een Windows-computer met Windows 7 of hoger.

-   Uw invoerapp moet een geldig Android-toepassingspakket zijn met de extensie **.apk** en:

    -   Mag niet versleuteld zijn

    -   Mag niet al zijn verpakt met de App Wrapping Tool
    -   Moet zijn geschreven voor Android 4.0 of hoger

-   De app moet zijn ontwikkeld door of voor uw bedrijf. U kunt dit hulpprogramma niet gebruiken voor apps die zijn gedownload uit de Google Play Store.

-   Als u de App Wrapping Tool wilt uitvoeren, moet u de nieuwste versie van [Java Runtime Environment](http://java.com/download/) installeren en vervolgens controleren of het variabele Java-pad is ingesteld op **C:\ProgramData\Oracle\Java\javapath** in de Windows-omgevingsvariabelen. Zie de [Java-documentatie](http://java.com/download/help/) voor meer informatie.

    > [!NOTE]
    > In bepaalde gevallen kan de 32-bits versie van Java leiden tot geheugenproblemen. Het wordt aangeraden om in plaats daarvan de 64-bits versie te installeren.

- Android vereist dat alle app-pakketten (.apks) zijn ondertekend. Gebruik de Java Key Tool voor het genereren van aanmeldingsgegevens die nodig zijn om de verpakte uitvoerapp te ondertekenen. Met de opdracht hierna wordt bijvoorbeeld het uitvoerbare Java-bestand **keytool.exe** gebruikt om sleutels te genereren die door de App Wrapping Tool kunnen worden gebruikt om de verpakte uitvoerapp te ondertekenen.

    ```
    keytool.exe -genkeypair -v -keystore mykeystorefile -alias mykeyalias -keyalg RSA -keysize 2048 -validity 50000
    ```
    In dit voorbeeld wordt een sleutelpaar gegenereerd (een openbare sleutel en een bijbehorende persoonlijke sleutel met een grootte van 2048 bits) met het RSA-algoritme en wordt de openbare sleutel vervolgens verpakt in een zelf-ondertekend X.509 v3-certificaat, dat wordt opgeslagen als een certificaatketen van één enkel element. Deze certificaatketen en de persoonlijke sleutel worden opgeslagen in een nieuw sleutelopslagvermelding met de naam 'mykeystorefile' en de alias 'mykeyalias'. De sleutelopslagvermelding is 50.000 dagen geldig.

    De opdracht vraagt u om wachtwoorden te verstrekken voor de sleutelopslagplaats en de sleutel. Gebruik wachtwoorden die veilig zijn en moeilijk zijn te raden, maar onthoud ze goed, want ze zijn later nodig om de App Wrapping Tool uit te voeren.

    Uitgebreide informatie over de Java [keytool](http://docs.oracle.com/javase/6/docs/technotes/tools/windows/keytool.html) en Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) vindt u op de website met Oracle-documentatie.

## Stap 2: installeer de App Wrapping Tool

1.  Download vanuit de [GitHub-opslagplaats](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) het installatiebestand **InstallAWT.exe** voor de Intune App Wrapping Tool voor Android naar een Windows-computer en open het bestand.

2.  Accepteer de gebruiksrechtovereenkomst en voltooi de installatie.

Onthoud in welke map het hulpprogramma is geïnstalleerd. De standaardlocatie is: **C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool**.

## Stap 3: voer de App Wrapping Tool uit

1.  Open in de beheerdersmodus een PowerShell-venster op de Windows-computer waarop de App Wrapping Tool is geïnstalleerd.

2.  Importeer de App Wrapping Tool PowerShell-module uit de map waarin u het programma hebt geïnstalleerd:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Voer het hulpprogramma uit met de opdracht **invoke-AppWrappingTool** die wordt gebruikt met de volgende syntaxis:
    ```
    Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
    -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
    ```

 In de volgende tabel worden de eigenschappen van de opdracht **invoke-AppWrappingTool** beschreven:

|Eigenschap|Informatie|Voorbeeld|
|-------------|--------------------|---------|
|**-InputPath**&lt;tekenreeks&gt;|Pad van de Android-bron-app (.apk).| |
|**-OutputPath**&lt;tekenreeks&gt;|Pad naar de uit te voeren Android-app. Als dit hetzelfde mappad is als InputPath, mislukt het inpakken.| |
|**-KeyStorePath**&lt;tekenreeks&gt;|Pad naar het sleutelopslagbestand met het openbare/persoonlijke sleutelpaar voor ondertekening.|De sleutelopslagbestanden worden standaard opgeslagen in C:\Program Files (x86)\Java\jreX.X.X_XX\bin. |
|**-KeyStorePassword**&lt;SecureString&gt;|Wachtwoord voor het ontsleutelen van de sleutelopslag. Android vereist dat alle toepassingspakketten (.apk) zijn ondertekend. Gebruik de Java Key Tool voor het genereren van het KeyStorePassword. Lees hier meer informatie over de Java [keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).| |
|**-KeyAlias**&lt;tekenreeks&gt;|Naam van de sleutel die moet worden gebruikt voor het ondertekenen.| |
|**-KeyPassword**&lt;SecureString&gt;|Wachtwoord dat wordt gebruikt om de persoonlijke sleutel te ontsleutelen die wordt gebruikt voor het ondertekenen.| |
|**-SigAlg**&lt;SecureString&gt;| (Optioneel) De naam van het handtekeningalgoritme dat moet worden gebruikt voor de ondertekening. Het algoritme moet compatibel zijn met de persoonlijke sleutel.|Voorbeelden: SHA256withRSA, SHA1withRSA, MD5withRSA|
| **&lt;CommonParameters&gt;** | (Optioneel) De opdracht ondersteunt algemene PowerShell-parameters, zoals verbose, debug enzovoort. |


- Zie voor een lijst met algemene parameters het [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Als u gedetailleerde gebruiksinformatie over de App Wrapping Tool wilt weergeven, voert u deze opdracht in:

    ```
    Help Invoke-AppWrappingTool
    ```

**Voorbeeld:**

Importeer de PowerShell-module.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1" 
```
Voer de App Wrapping Tool uit op de oorspronkelijke app **HelloWorld.apk**. 
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

U wordt vervolgens gevraagd om het **KeyStorePassword** en **KeyPassword**. Voer de aanmeldingsgegevens in die u hebt gebruikt voor het maken van het sleutelopslagbestand.

De ingepakte app wordt gegenereerd en samen met een logboekbestand in het uitvoerpad opgeslagen dat u hebt opgegeven.

## Beveiligingsoverwegingen voor het uitvoeren van de App Wrapping Tool
Potentiële adresvervalsing (spoofing), vrijgeven van informatie en uitbreiding van bevoegdheden voorkomen:

-   Zorg ervoor dat de invoer-Line-Of-Bussiness-app, de uitvoerapp en de Java KeyStore zich op de Windows-computer bevinden waarop ook de App Wrapping Tool wordt uitgevoerd.

-   Importeer de uitvoerapp naar de Intune-console op de machine waarop ook de App Wrapping Tool wordt uitgevoerd. Zie [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) voor meer informatie over de Java keytool.

-   Als de uitvoertoepassing en het hulpprogramma zich op een pad (Universal Naming Convention) bevinden en u het hulpprogramma en de invoerbestanden niet op dezelfde computer uitvoert, configureert u de omgeving zodanig dat deze wordt beveiligd met [IP-beveiligingsbeleid (IPsec)](http://en.wikipedia.org/wiki/IPsec) of [Server Message Block (SMB) ondertekening](https://support.microsoft.com/en-us/kb/887429).

-   Zorg ervoor dat de app afkomstig is van een vertrouwde bron.

-   Beveilig de uitvoermap die de ingepakte app bevat. Overweeg het gebruik van een map op gebruikersniveau voor de uitvoer.



### Zie tevens
- [Bepalen hoe u apps met Microsoft Intune voorbereidt op Mobile Application Management](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md)

- [De SDK gebruiken om apps geschikt te maken voor Mobile Application Management](use-the-sdk-to-enable-apps-for-mobile-application-management.md)



<!--HONumber=Oct16_HO2-->


