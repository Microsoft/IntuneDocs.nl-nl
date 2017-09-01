---
title: Android-apps verpakken met App Wrapping Tool
description: In dit artikel vindt u meer informatie over het verpakken van uw Android-apps zonder de code van de app zelf te wijzigen. Bereid de apps voor, zodat u de Mobile App Management-beleidsregels kunt toepassen.
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8707253139ee5a12a48d38a333ae49fbb4d3ead
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/25/2017
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Android-apps voorbereiden voor app-beveiligingsbeleid met Intune App Wrapping Tool

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Gebruik Microsoft Intune App Wrapping Tool voor Android om de werking van in-house Android-apps te wijzigen door de functies van de apps te beperken zonder de code van de apps zelf te wijzigen.

Dit hulpprogramma is een Windows-opdrachtregelprogramma dat wordt uitgevoerd in PowerShell en een 'wrapper' (schil) rond uw app maakt. Als de app eenmaal is verpakt (van een 'wrapper' is voorzien), kunt u vervolgens de functionaliteit van de app wijzigen door [Mobile Application Management-beleid](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) te configureren in Intune.


Controleer [Beveiligingsoverwegingen voor het uitvoeren van App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool) voordat u het hulpprogramma uitvoert. Als u dit hulpprogramma wilt downloaden, gaat u naar [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) op GitHub.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Voldoen aan de vereisten voor het gebruik van App Wrapping Tool

-   U moet App Wrapping Tool uitvoeren op een Windows-computer met Windows 7 of hoger.

-   Uw invoer-app moet een geldig Android-toepassingspakket zijn met de extensie .apk en:

    -   Mag niet versleuteld zijn.
    -   Mag niet al zijn verpakt met App Wrapping Tool.
    -   Moet zijn geschreven voor Android 4.0 of hoger.

-   De app moet zijn ontwikkeld door of voor uw bedrijf. U kunt dit hulpprogramma niet gebruiken voor apps die zijn gedownload uit de Google Play Store.

-   Als u App Wrapping Tool wilt uitvoeren, moet u de nieuwste versie van [Java Runtime Environment](http://java.com/download/) installeren en vervolgens controleren of het variabele Java-pad is ingesteld op C:\ProgramData\Oracle\Java\javapath in de Windows-omgevingsvariabelen. Zie de [Java-documentatie](http://java.com/download/help/) voor meer informatie.

    > [!NOTE]
    > In bepaalde gevallen kan de 32-bits versie van Java leiden tot geheugenproblemen. Het is verstandig de 64-bits versie te installeren.

- Android vereist dat alle app-pakketten (.apks) zijn ondertekend. Zie [Ondertekeningscertificaten hergebruiken en apps verpakken](https://docs.microsoft.com/en-us/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps) als u bestaande certificaten **opnieuw wilt gebruiken** en voor hulp bij het algemeen ondertekenen van certificaten. Het uitvoerbare Java-bestand keytool.exe wordt gebruikt om **nieuwe** referenties te genereren die nodig zijn om de verpakte uitvoer-app te ondertekenen. Ingestelde wachtwoorden moeten veilig zijn, maar onthoud ze goed, want ze zijn later nodig om App Wrapping Tool uit te voeren.

## <a name="install-the-app-wrapping-tool"></a>De App Wrapping Tool installeren

1.  Download vanuit de [GitHub-opslagplaats](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) het installatiebestand InstallAWT.exe voor Intune App Wrapping Tool voor Android naar een Windows-computer. Open het installatiebestand.

2.  Accepteer de gebruiksrechtovereenkomst en voltooi de installatie.

Onthoud in welke map het hulpprogramma is geïnstalleerd. De standaardlocatie is: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>De App Wrapping Tool uitvoeren

1.  Open een PowerShell-venster op de Windows-computer waarop de App Wrapping Tool is geïnstalleerd.

2.  Importeer de App Wrapping Tool PowerShell-module uit de map waarin u het programma hebt geïnstalleerd:

    ```
    Import-Module .\IntuneAppWrappingTool.psm1
    ```

3.  Voer het hulpprogramma uit met de opdracht **invoke-AppWrappingTool**, die wordt gebruikt met de volgende syntaxis:
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
|**-KeyStorePassword**&lt;SecureString&gt;|Wachtwoord voor het ontsleutelen van de sleutelopslag. Android vereist dat alle toepassingspakketten (.apk) zijn ondertekend. Gebruik Java-keytool voor het genereren van het KeyStorePassword. Lees hier meer informatie over de Java [Keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html).| |
|**-KeyAlias**&lt;tekenreeks&gt;|Naam van de sleutel die moet worden gebruikt voor het ondertekenen.| |
|**-KeyPassword**&lt;SecureString&gt;|Wachtwoord dat wordt gebruikt om de persoonlijke sleutel te ontsleutelen die wordt gebruikt voor het ondertekenen.| |
|**-SigAlg**&lt;SecureString&gt;| (Optioneel) De naam van het handtekeningalgoritme dat moet worden gebruikt voor de ondertekening. Het algoritme moet compatibel zijn met de persoonlijke sleutel.|Voorbeelden: SHA256withRSA, SHA1withRSA|
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
Voer App Wrapping Tool uit in de oorspronkelijke app HelloWorld.apk.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

U wordt vervolgens gevraagd om het **KeyStorePassword** en **KeyPassword**. Voer de aanmeldingsgegevens in die u hebt gebruikt voor het maken van het sleutelopslagbestand.

De verpakte app wordt samen met een logboekbestand gegenereerd en opgeslagen in het uitvoerpad dat u hebt opgegeven.

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>Ondertekeningscertificaten hergebruiken en apps verpakken
Android vereist dat alle apps zijn ondertekend met een geldig certificaat voordat ze kunnen worden geïnstalleerd op Android-apparaten.

Verpakte apps kunnen zijn ondertekend tijdens het wrapping-proces of *na* het verpakken, met gebruik van uw bestaande hulpmiddelen voor ondertekening. Alle aanwezige ondertekeningsinformatie in de app voorafgaand aan het verpakken wordt verwijderd.
 
Indien mogelijk moet de ondertekeningsinformatie die is gebruikt tijdens het buildproces worden gebruikt tijdens het verpakken. In bepaalde organisaties vereist dit mogelijk samenwerking met de eigenaar van de informatie over de sleutelopslag (zoals degenen die de app maken). 

Als het vorige ondertekeningscertificaat niet kan worden gebruikt of de app nog niet eerder is geïmplementeerd, kunt u een nieuw ondertekeningscertificaat maken aan de hand van de instructies in de [Android Developer Guide](https://developer.android.com/studio/publish/app-signing.html#signing-manually).

Als de app al eerder is geïmplementeerd met een ander ondertekeningscertificaat, kan de app niet worden geüpload naar de Intune-console na de upgrade. Scenario's voor het upgraden van apps werken niet meer als uw app is ondertekend met een ander certificaat dan het certificaat waarmee de app is gebouwd. Onderhoud nieuwe ondertekeningscertificaten dus voor app-upgrades. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Beveiligingsoverwegingen voor het uitvoeren van App Wrapping Tool
Potentiële adresvervalsing (spoofing), vrijgeven van informatie en uitbreiding van bevoegdheden voorkomen:

-   Zorg ervoor dat de invoer-Line-Of-Bussiness-app, de uitvoer-app en de Java KeyStore zich op de Windows-computer bevinden waarop ook App Wrapping Tool wordt uitgevoerd.

-   Importeer de uitvoer-app naar de Intune-console op de machine waarop ook de App Wrapping Tool wordt uitgevoerd. Zie [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) voor meer informatie over Java-keytool.

-   Als de uitvoertoepassing en het hulpprogramma zich in een UNC-pad (Universal Naming Convention) bevinden en u het hulpprogramma en de invoerbestanden niet op dezelfde computer uitvoert, stelt u de omgeving zodanig in dat deze wordt beveiligd met [IP-beveiligingsbeleid (IPsec)](http://wikipedia.org/wiki/IPsec) of [Server Message Block (SMB)-ondertekening](https://support.microsoft.com/kb/887429).

-   Zorg ervoor dat de app afkomstig is van een vertrouwde bron.

-   Beveilig de uitvoermap die de verpakte app bevat. Overweeg het gebruik van een map op gebruikersniveau voor de uitvoer.

### <a name="see-also"></a>Zie tevens
- [Bepalen hoe u apps voorbereidt op Mobile Application Management met Microsoft Intune](apps-prepare-mobile-application-management.md)

- [De SDK gebruiken om apps geschikt te maken voor Mobile Application Management](/intune/classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
