---
title: Apps voor Windows en Windows Phone sideloaden | Microsoft Intune
description: Leer hoe u line-of-business-apps ondertekent, zodat u Intune kunt gebruiken voor de implementatie van deze apps.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 938e3a1914f379d115bf24ebd7d990f6e1d319a9


---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Line-of-business-apps ondertekenen, zodat ze kunnen worden geïmplementeerd op Windows-apparaten met Intune

Als Intune-beheerder kunt u LOB-apps (line-of-business) implementeren op Windows- en Windows 10 Mobile-apparaten, met inbegrip van de bedrijfsportal-app. Als u apps van het type .appx of .xap wilt implementeren op Windows 10- en Windows 10 mobile-apparaten, of als u een LOB-app wilt implementeren op Windows 8.1- of Windows Phone 8.1-apparaten, moet u een **Symantec Enterprise Mobile certificaat voor Codeondertekening** ophalen. Alleen het Symantec-certificaat wordt voor deze apps vertrouwd voor de desbetreffende Windows-apparaten. U kunt uw eigen certificeringsinstantie gebruiken voor Windows 10-apps en voor 'universele' apps. Dit certificaat is vereist om:

-   De bedrijfsportal-app ondertekenen voor implementatie op Windows-pc's, Windows 10 Mobile-apparaten en Windows Phone-apparaten

-   Zakelijke line-of-business-apps ondertekenen, zodat Intune deze kan implementeren op Windows-apparaten

Gebruik onderstaande stappen om de vereiste certificaten op te halen en de apps te ondertekenen. U hebt een Windows Phone Dev Center-account nodig en vervolgens moet u een Symantec-certificaat kopen.


1. **Lid worden van het Windows Phone Developer Center**<br>
   Word met uw zakelijke accountgegevens lid van het [Windows Phone Developer Center](http://go.microsoft.com/fwlink/?LinkId=268442) wanneer u zich aanmeldt om uw bedrijfsaccount aan te schaffen. Deze aanvraag moet worden geautoriseerd door een bedrijfsverantwoordelijke voordat u het certificaat voor ondertekening van programmacode ontvangt.

2. **Een zakelijk Symantec-certificaat kopen**<br>
  Koop een certificaat op de [Symantec-website](http://go.microsoft.com/fwlink/?LinkId=268441) met uw Symantec-id. Nadat u het certificaat hebt gekocht, ontvangt de zakelijke goedkeurder die u hebt opgegeven in uw Windows Phone Developer Center-account een e-mail met een aanvraag voor goedkeuring van de certificaataanvraag. Lees de veelgestelde vragen over het inschrijven van Windows-apparaten in [Waarom is een Symantec-certificaat vereist voor Windows Phone?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) voor meer informatie over het vereiste Symantec-certificaat.

3.  **Certificaten importeren**<br>
    Zodra de aanvraag is goedgekeurd, ontvangt u een e-mail met instructies voor het importeren van certificaten. Volg de instructies in de e-mail om de certificaten te importeren.

4.  **Geïmporteerde certificaten verifiëren**<br>
    Ga naar de module **Certificaten**, klik met de rechtermuisknop op **Certificaten** en selecteer **Certificaten zoeken** om te controleren of de certificaten correct zijn geïmporteerd. Typ 'Symantec' in het veld **Bevat** en klik op **Nu zoeken**. De certificaten die u hebt geïmporteerd, worden weergegeven in de resultaten.

    ![Het Symantec-certificaat zoeken](./media/wit.gif)

5. **Een handtekeningcertificaat exporteren**<br>
    Wanneer u hebt gecontroleerd of de certificaten aanwezig zijn, kunt u het PFX-bestand exporteren om de bedrijfsportal te ondertekenen. Selecteer het Symantec-certificaat met 'Handtekening bij programmacode' onder **Beoogde doeleinden**. Klik met de rechtermuisknop op het certificaat voor de ondertekening van de programmacode en selecteer **Exporteren**.

    ![Het handtekeningcertificaat exporteren](./media/wit-walk-cert2.gif)

    Selecteer **Ja, de persoonlijke sleutel exporteren**in de wizard **Certificaat exporteren** en klik vervolgens op **Volgende**. **Selecteer Personal Information Exchange - PKCS nr. 12 (.PFX)** en schakel **Indien mogelijk exporteren met alle certificaten in het certificeringspad** in. Voltooi de wizard. Zie [Certificaten exporteren met de persoonlijke sleutel](http://go.microsoft.com/fwlink/?LinkID=203031)voor meer informatie.

6.  **De app uploaden naar Intune**<br>
    Upload het ondertekende app-bestand en uw certificaat voor ondertekening van programmacode om de app beschikbaar te stellen aan uw eindgebruikers.

    1.  Klik in de [Intune-beheerconsole](http://manage.microsoft.com) op **Beheer** &gt; **Windows Phone**.

    2.  Klik op **Ondertekende app uploaden** en meld u aan met uw Intune-beheerder-id.

    3.  Voeg het geëxporteerde certificaatbestand (.pfx) toe aan **Certificaat voor ondertekening van programmacode** en maak een wachtwoord voor het certificaat.

    4.  Voltooi de wizard.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Voorbeeld: de bedrijfsportal-app downloaden, ondertekenen en implementeren op Windows-apparaten

U kunt de bedrijfsportal-app implementeren op Windows-apparaten (inclusief Windows Phone- en Windows 10 Mobile-apparaten) met Intune in plaats van installatie vanuit de Windows Phone Store. U moet de bedrijfsportal-app downloaden en ondertekenen met uw certificaat.  Dit is alleen nodig als uw gebruikers de Store van het bedrijf niet gebruiken en u de bedrijfsportal wilt implementeren op Windows Phone 8.1-apparaten.


1.  **De bedrijfsportal downloaden**

    Als u de bedrijfsportal-app wilt implementeren met Intune, downloadt u de [Microsoft Intune-bedrijfsportal-app voor Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) vanuit het Downloadcentrum en voert u het zelfuitpakkende bestand (.exe) uit. Dit bestand bevat twee bestanden:

    -   CompanyPortal.appx: de installatie-app van de bedrijfsportal voor Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1:  een PowerShell-script waarmee u het bestand van de bedrijfsportal-app kunt ondertekenen, zodat het kan worden geïmplementeerd naar Windows Phone 8.1-apparaten

    U kunt de Windows Phone 8.1-bedrijfsportal (offline gelicentieerd pakket) ook downloaden of de Windows 10-bedrijfsportal (offline gelicentieerd pakket) ook downloaden via de [Windows Store voor Bedrijven](http://businessstore.microsoft.com/). De bedrijfsportal-app moet worden opgehaald met een offline-licentie en het juiste pakket moet worden gedownload voor offlinegebruik. In de vermeldingen voor het Windows 8- en Windows Phone 8-platform in de selectie wordt verwezen naar de versies voor Windows 8.1. Zie [Manage apps you purchased from the Windows Store for Business](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md) (Apps beheren die u hebt aangeschaft in de Windows Store voor Bedrijven) als u wilt weten hoe u dit met Intune kunt doen.

2.  **De Windows Phone SDK downloaden** Download de Windows Phone SDK 8.0 (http://go.microsoft.com/fwlink/?LinkId=615570) en installeer de SDK op uw computer. Deze SDK is nodig om een token voor toepassingsinschrijving te genereren.

3.  **Een AETX-bestand genereren** Genereer een bestand met een registratietoken van de toepassing (.aetx) met het Symantec PFX-bestand met AETGenerator.exe, onderdeel van Windows Phone SDK 8.0. Zie [Een inschrijvingstoken van de toepassing  genereren voor Windows Phone](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)voor informatie over het maken van een AETX-bestand.

4.  **De Windows SDK voor Windows 8.1 downloaden** Download en installeer de [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=613525) (http://go.microsoft.com/fwlink/?LinkId=613525). Het PowerShell-script dat is opgenomen in de bedrijfsportal-app gebruikt de standaardinstallatielocatie `${env:ProgramFiles(x86)}\Windows Kits\8.1`. Als u op een andere locatie wilt installeren, moet u de locatie in een cmdlet-parameter opnemen.

5.  **De code van de app ondertekenen met PowerShell** Open als beheerder **Windows PowerShell** op de hostcomputer waarop de Windows SDK is geïnstalleerd en het Symantec Enterprise-certificaat voor ondertekening van de mobiele code staat, ga naar het bestand Sign-WinPhoneCompanyPortal.ps1 en voer het script uit.

    **Voorbeeld 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    In dit voorbeeld wordt de CompanyPortal.appx ondertekend op C:\temp\ en wordt  CompanyPortalEnterpriseSigned.appx gemaakt. Het PFX-wachtwoord 1234 wordt gebruikt en de uitgevers-id uit het PFX-bestand wordt gelezen. De ondernemings-id wordt ook gelezen uit het cert.aetx-bestand.

    **Voorbeeld 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    In dit voorbeeld wordt de CompanyPortal.appx ondertekend op C:\temp\ en wordt  CompanyPortalEnterpriseSigned.appx gemaakt. Het PFX-wachtwoord 1234 wordt gebruikt samen met de opgegeven uitgevers-ID.

    **Parameters:**

    -   `-InputAppx` : het lokale pad naar het bestand CompanyPortal.appx tussen enkele aanhalingstekens. Bijvoorbeeld 'C:\temp\CompanyPortal.appx'

    -   `-OutputAppx` : het lokale pad en de bestandsnaam voor de ondertekende bedrijfsportal-app tussen enkele aanhalingstekens. Bijvoorbeeld 'C:\temp\CompanyPortalEnterpriseSigned.appx'

    -   `-PfxFilePath` : het lokale pad en de bestandsnaam voor het geëxporteerde PFX-bestand van het Symantec-certificaat. Bijvoorbeeld 'C:\signing\cert.pfx'

    -   `-PfxPassword` : het wachtwoord dat is gebruikt voor het ondertekenen van het PFX-bestand in enkele aanhalingstekens. Bijvoorbeeld '1234'

    -   `-AetxPath` : het lokale pad naar het .aetx-bestand dat wordt gebruikt voor het lezen van de ondernemings-id als het argument EnterpriseId is niet gedefinieerd. Dit argument of een EnterpriseId moet worden opgegeven. Bijvoorbeeld 'C:\signing\cert.aetx'

    -   `-PublisherId`: de uitgevers-id van de onderneming. Als deze niet is opgegeven, wordt het veld Onderwerp van Symantec Enterprise-certificaat voor ondertekening van mobiele code gebruikt. Bijvoorbeeld 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1'

    -   `-SdkPath`: het pad naar de hoofdmap van de Windows-SDK voor Windows 8.1. Dit argument is optioneel en wordt standaard ingesteld op ${env:ProgramFiles(x86)} \Windows Kits\8.1.

    -   `-EnterpriseId`: de ondernemings-id. Dit argument of AetxPath moet worden opgegeven. Als dit argument niet is opgegeven, wordt de ondernemings-id uit het AETX-bestand gelezen. Bijvoorbeeld 1000000001

6.  Implementeer de Windows Phone 8.1-bedrijfsportal-app (SSP.appx). Zie [Apps implementeren in Microsoft Intune](deploy-apps-in-microsoft-intune.md) voor meer informatie.

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Het zakelijke Symantec-certificaat voor ondertekening van programmacode vernieuwen

Het Symantec-certificaat waarmee mobiele apps voor Windows en Windows Phone worden geïmplementeerd, moet regelmatig worden vernieuwd.

1.  Zoek naar een e-mail over de vereiste vernieuwing die ongeveer 14 dagen vóór de vervaldatum van het certificaat ontvangt van Symantec. Deze e-mail bevat richtlijnen van Symantec om uw zakelijke certificaat te vernieuwen.

    Ga naar [www.symantec.com](http://www.symantec.com) of bel +1-877-438-8776 of +1-650-426-3400 voor meer informatie over Symantec-certificaten.

2.  Ga naar de website (voorbeeld: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) en meld u aan met de Symantec uitgevers-ID en het e-mailadres dat is gekoppeld aan het certificaat. Start het vernieuwingsproces op het apparaat waarop u daarna ook het certificaat gaat downloaden.

3.  Nadat de vernieuwing is goedgekeurd en betaald, downloadt u het certificaat.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Het bijgewerkte certificaat voor LOB-apps (line-of-business) installeren

1.  Onderteken de nieuwste versie van uw line-of-business-app.

2.  Open uw [Intune-beheerconsole](https://admin.manage.microsoft.com) (https://admin.manage.microsoft.com) en ga naar **Beheer** &gt; **Mobile Device Management** &gt; **Windows Phone** en klik op **Ondertekende app uploaden**.

3.  Upload de zojuist ondertekende bedrijfsportal. U hebt het nieuw ondertekende SSP.xap en het nieuwe PFX-bestand nodig dat u hebt ontvangen van Symantec of het toepassingsinschrijvingstoken dat met dit nieuwe PFX-bestand is gemaakt.

4.  Nadat het uploaden is voltooid, verwijdert u de oude versie van de bedrijfsportal uit de werkruimte **Software**  .

5.  Onderteken alle nieuwe en bijgewerkte bedrijfstak-apps van de onderneming met behulp van het nieuwe certificaat. Bestaande toepassingen hoeven niet opnieuw te worden ondertekend en geïmplementeerd.



<!--HONumber=Dec16_HO2-->


