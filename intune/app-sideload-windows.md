---
title: Windows- en Windows Phone-apps voor Intune sideloaden
description: Leer hoe u Line-Of-Business-apps ondertekent, zodat u Intune kunt gebruiken voor de implementatie van deze apps.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f3c088f8aca9a7a1ef42886ff6c04d6c1662e9f7
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846465"
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Line-of-business-apps ondertekenen, zodat ze kunnen worden geïmplementeerd op Windows-apparaten met Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Als Intune-beheerder kunt u LOB-apps (line-of-business) implementeren op Windows- en Windows 10 Mobile-apparaten, met inbegrip van de bedrijfsportal-app. Als u apps van het type .appx of .xap wilt implementeren op Windows 10- en Windows 10 mobile-apparaten, of als u een LOB-app wilt implementeren op Windows 8.1- of Windows Phone 8.1-apparaten, moet u een **Symantec Enterprise Mobile certificaat voor Codeondertekening** ophalen. Alleen het Symantec-certificaat wordt voor deze apps vertrouwd voor de desbetreffende Windows-apparaten. U kunt uw eigen certificeringsinstantie gebruiken voor Windows 10-apps en voor 'universele' apps. Dit certificaat is vereist om:

-   De bedrijfsportal-app ondertekenen voor implementatie op Windows-pc's, Windows 10 Mobile-apparaten en Windows Phone-apparaten

-   Zakelijke line-of-business-apps ondertekenen, zodat Intune deze kan implementeren op Windows-apparaten

Gebruik onderstaande stappen om de vereiste certificaten op te halen en de apps te ondertekenen. U moet u aanmelden als een Microsoft-ontwikkelaar en vervolgens een Symantec-certificaat kopen.


1. **Aanmelden als een Microsoft-ontwikkelaars**<br>
   [Meld u aan als een Microsoft-ontwikkelaar](https://go.microsoft.com/fwlink/?LinkId=268442) met de zakelijke accountgegevens die u hebt gebruikt bij het aanmelden om het account van uw bedrijf te kopen. Deze aanvraag moet worden geautoriseerd door een bedrijfsverantwoordelijke voordat u het certificaat voor ondertekening van programmacode ontvangt.

2. **Een zakelijk Symantec-certificaat kopen**<br>
  Koop een certificaat op de [Symantec-website](https://go.microsoft.com/fwlink/?LinkId=268441) met uw Symantec-id. Nadat u het certificaat hebt gekocht, ontvangt de zakelijke goedkeurder die u hebt opgegeven bij de aanmelding als Microsoft-ontwikkelaar een e-mail met een aanvraag voor goedkeuring van de certificaataanvraag. Lees de veelgestelde vragen over het inschrijven van Windows-apparaten in [Waarom is een Symantec-certificaat vereist voor Windows Phone?](https://technet.microsoft.com/library/dn764959.aspx#BKMK_Symantec) voor meer informatie over het vereiste Symantec-certificaat.

3.  **Certificaten importeren**<br>
    Zodra de aanvraag is goedgekeurd, ontvangt u een e-mail met instructies voor het importeren van certificaten. Volg de instructies in de e-mail om de certificaten te importeren.

4.  **Geïmporteerde certificaten verifiëren**<br>
    Ga naar de module **Certificaten**, klik met de rechtermuisknop op **Certificaten** en selecteer **Certificaten zoeken** om te controleren of de certificaten correct zijn geïmporteerd. Typ 'Symantec' in het veld **Bevat** en klik op **Nu zoeken**. De certificaten die u hebt geïmporteerd, worden weergegeven in de resultaten.

    ![De certificaatresultaten worden vermeld in het dialoogvenster Certificaten zoeken](./media/wit.gif)

5. **Een handtekeningcertificaat exporteren**<br>
    Wanneer u hebt gecontroleerd of de certificaten aanwezig zijn, kunt u het PFX-bestand exporteren om de bedrijfsportal te ondertekenen. Selecteer het Symantec-certificaat met 'Handtekening bij programmacode' onder **Beoogde doeleinden** . Klik met de rechtermuisknop op het certificaat voor de ondertekening van de programmacode en selecteer **Exporteren**.

    ![Het handtekeningcertificaat exporteren](./media/wit-walk-cert2.gif)

    Selecteer **Ja, de persoonlijke sleutel exporteren**in de wizard **Certificaat exporteren** en klik vervolgens op **Volgende**. **Selecteer Personal Information Exchange - PKCS nr. 12 (.PFX)** en schakel **Indien mogelijk exporteren met alle certificaten in het certificeringspad** in. Voltooi de wizard. Zie [Certificaten exporteren met de persoonlijke sleutel](https://go.microsoft.com/fwlink/?LinkID=203031)voor meer informatie.

6.  **De app uploaden naar Intune**<br>
    Upload het ondertekende app-bestand en uw certificaat voor ondertekening van programmacode om de app beschikbaar te stellen aan uw eindgebruikers.

    1.  Klik in de Azure-portal op **Beheer** &gt; **Windows Phone**.

    2.  Klik op **Ondertekende app uploaden** en meld u aan met uw Intune-beheerder-id.

    3.  Voeg het geëxporteerde certificaatbestand (.pfx) toe aan **Certificaat voor ondertekening van programmacode** en maak een wachtwoord voor het certificaat.

    4.  Voltooi de wizard.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Voorbeeld: de bedrijfsportal-app downloaden, ondertekenen en implementeren op Windows-apparaten

U kunt de bedrijfsportal-app implementeren op Windows-apparaten (inclusief Windows Phone- en Windows 10 Mobile-apparaten) met Intune in plaats van installatie vanuit Microsoft Store. U moet de bedrijfsportal-app downloaden en ondertekenen met uw certificaat.  Dit is alleen nodig als uw gebruikers de Store van het bedrijf niet gebruiken en u de bedrijfsportal wilt implementeren op Windows Phone 8.1-apparaten.


1.  **De bedrijfsportal downloaden**

    Als u de bedrijfsportal-app wilt implementeren met Intune, downloadt u de [Microsoft Intune-bedrijfsportal-app voor Windows Phone 8.1](https://go.microsoft.com/fwlink/?LinkId=615799) vanuit het Downloadcentrum en voert u het zelfuitpakkende bestand (.exe) uit. Dit bestand bevat twee bestanden:

    -   CompanyPortal.appx: de installatie-app van de bedrijfsportal voor Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1:  een PowerShell-script waarmee u het bestand van de bedrijfsportal-app kunt ondertekenen, zodat het kan worden geïmplementeerd naar Windows Phone 8.1-apparaten

    U kunt ook de Windows Phone 8.1-bedrijfsportal (offline gelicentieerd pakket) of de Windows 10-bedrijfsportal (offline gelicentieerd pakket) downloaden via [Microsoft Store voor Bedrijven](https://businessstore.microsoft.com/). De bedrijfsportal-app moet worden opgehaald met een offline-licentie en het juiste pakket moet worden gedownload voor offlinegebruik. In de vermeldingen voor het Windows 8- en Windows Phone 8-platform in de selectie wordt verwezen naar de versies voor Windows 8.1. Zie [Apps beheren die u hebt aangeschaft in Microsoft Store voor Bedrijven](windows-store-for-business.md) als u wilt weten hoe u dit met Intune kunt doen.

2.  **De Windows Phone SDK downloaden** Download de Windows Phone SDK 8.0](https://go.microsoft.com/fwlink/?LinkId=615570) en installeer de SDK op uw computer. Deze SDK is nodig om een token voor toepassingsinschrijving te genereren.

3.  **Een AETX-bestand genereren** Genereer een bestand met een registratietoken van de toepassing (.aetx) met het Symantec PFX-bestand met AETGenerator.exe, onderdeel van Windows Phone SDK 8.0. Zie [Een inschrijvingstoken van de toepassing  genereren voor Windows Phone](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx)voor informatie over het maken van een AETX-bestand.

4.  **De Windows SDK voor Windows 8.1 downloaden** Download en installeer de [Windows Phone SDK](https://go.microsoft.com/fwlink/?LinkId=613525) (https://go.microsoft.com/fwlink/?LinkId=613525). Het PowerShell-script dat is opgenomen in de bedrijfsportal-app gebruikt de standaardinstallatielocatie `${env:ProgramFiles(x86)}\Windows Kits\8.1`. Als u op een andere locatie wilt installeren, moet u de locatie in een cmdlet-parameter opnemen.

5.  **De code van de app ondertekenen met PowerShell** Open als beheerder **Windows PowerShell** op de hostcomputer waarop de Windows SDK is geïnstalleerd en het Symantec Enterprise-certificaat voor ondertekening van de mobiele code staat, ga naar het bestand Sign-WinPhoneCompanyPortal.ps1 en voer het script uit.

    **Voorbeeld 1**

    ```PowerShell
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    In dit voorbeeld wordt de CompanyPortal.appx ondertekend op C:\temp\ en wordt  CompanyPortalEnterpriseSigned.appx gemaakt. Het PFX-wachtwoord 1234 wordt gebruikt en de uitgevers-id uit het PFX-bestand wordt gelezen. De ondernemings-id wordt ook gelezen uit het cert.aetx-bestand.

    **Voorbeeld 2**

    ```PowerShell
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

6.  Implementeer de Windows Phone 8.1-bedrijfsportal-app (SSP.appx). Voor richtlijnen, zie [Instructies voor toevoegen van LOB-apps (line-of-business) in Windows Phone ](lob-apps-windows-phone.md).

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Het zakelijke Symantec-certificaat voor ondertekening van programmacode vernieuwen

Het Symantec-certificaat waarmee mobiele apps voor Windows en Windows Phone worden geïmplementeerd, moet regelmatig worden vernieuwd.

1.  Zoek naar een e-mail over de vereiste vernieuwing die ongeveer 14 dagen vóór de vervaldatum van het certificaat ontvangt van Symantec. Deze e-mail bevat richtlijnen van Symantec om uw zakelijke certificaat te vernieuwen.

    Ga naar [www.symantec.com](https://www.symantec.com) of bel +1-877-438-8776 of +1-650-426-3400 voor meer informatie over Symantec-certificaten.

2.  Ga naar de website (bijvoorbeeld: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) en meld u aan met de Symantec-uitgevers-id en het e-mailadres dat is gekoppeld aan het certificaat. Start het vernieuwingsproces op het apparaat waarop u daarna ook het certificaat gaat downloaden.

3.  Nadat de vernieuwing is goedgekeurd en betaald, downloadt u het certificaat.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Het bijgewerkte certificaat voor LOB-apps (line-of-business) installeren

1.  Onderteken de nieuwste versie van uw line-of-business-app.

2.  Open de Azure-portal en ga naar **Beheerder** &gt; **Mobile Device Management** &gt; **Windows Phone** en klik op **Ondertekende app uploaden**.

3.  Upload de zojuist ondertekende bedrijfsportal. U hebt het nieuw ondertekende SSP.xap en het nieuwe PFX-bestand nodig dat u hebt ontvangen van Symantec of het toepassingsinschrijvingstoken dat met dit nieuwe PFX-bestand is gemaakt.

4.  Nadat het uploaden is voltooid, verwijdert u de oude versie van de bedrijfsportal uit de werkruimte **Software**  .

5.  Onderteken alle nieuwe en bijgewerkte bedrijfstak-apps van de onderneming met behulp van het nieuwe certificaat. Bestaande toepassingen hoeven niet opnieuw te worden ondertekend en geïmplementeerd.

## <a name="manually-deploy-windows-10-company-portal-app"></a>De Windows 10-bedrijfsportal-app handmatig implementeren
U kunt de Windows 10-bedrijfsportal-app handmatig rechtstreeks implementeren vanuit Intune, zelfs als u Intune niet hebt geïntegreerd met Microsoft Store voor Bedrijven.

 > [!NOTE]
 > Voor deze optie is handmatige implementatie van updates vereist voor elke app-update.

1. Meld u aan bij uw account in [Microsoft Store voor Bedrijven](https://www.microsoft.com/business-store) en schaf de versie met de **offlinelicentie** van de bedrijfsportal-app aan.  
2. Zodra de app is aangeschaft, selecteert u de app op de pagina **Inventaris**.  
3. Selecteer **Windows 10 alle apparaten** als **Platform**. Klik vervolgens op de betreffende **Architectuur** en download. Een app-licentiebestand is niet nodig voor deze app.
![Afbeelding van Windows 10 X86-pakketdetails voor downloaden](./media/Win10CP-all-devices.png)
4. Download alle pakketten onder "Vereiste frameworks". Dit moet worden uitgevoerd voor x86-, x64- en ARM-architecturen. Totaal zijn dit 9 pakketten, zoals hieronder weergegeven.

![Afbeelding van afhankelijkheidsbestanden voor downloaden ](./media/Win10CP-dependent-files.png)
5. Voordat u de bedrijfsportal-app uploadt naar Intune, maakt u een map (bijvoorbeeld C:&#92;Company Portal) waarin de pakketten als volgt zijn gestructureerd:
   1. Plaats het bedrijfsportalpakket in C:\Bedrijfsportal. Maak op deze locatie tevens een submap Afhankelijkheden.  
   ![Afbeelding van de map Afhankelijkheden waarin het APPXBUN-bestand is opgeslagen](./media/Win10CP-Dependencies-save.png)
   2. Plaats de negen afhankelijkheidspakketten in de map Afhankelijkheden.  
   Als de afhankelijkheden niet in deze indeling worden geplaatst, worden ze niet herkend door Intune en kunnen ze niet worden geüpload tijdens de pakket-upload. Het uploaden mislukt met de volgende fout.  
   ![Foutbericht - de Windows-app-afhankelijkheid moet worden opgegeven.](./media/Win10CP-error-message.png)
6. Ga terug naar Intune en upload the Bedrijfsportal-app als nieuwe app. Implementeer als vereiste app naar de gewenste set doelgebruikers.  

Zie [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Een appxbundle met afhankelijkheden implementeren via Microsoft Intune MDM) voor meer informatie over hoe Intune afhankelijkheden voor universele apps verwerkt.  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Hoe kan ik de Bedrijfsportal op de apparaten van mijn gebruikers bijwerken als hierop al de oudere apps uit de Store zijn geïnstalleerd?
Als uw gebruikers de Windows 8.1- of Windows Phone 8.1-bedrijfsportal-apps al hebben geïnstalleerd vanuit de Store, moeten deze automatisch worden bijgewerkt naar de nieuwe versie, zonder dat hiervoor actie door u of uw gebruikers is vereist. Als de update niet wordt uitgevoerd, vraagt u uw gebruikers om te controleren of automatische updates voor Store-apps op hun apparaten is ingeschakeld.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe ik een upgrade uitvoeren van mijn gesideloade Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de implementatie voor de Windows 8.1-bedrijfsportal-app te verwijderen door de implementatieactie in te stellen op Installatie ongedaan maken. Zodra deze actie is uitgevoerd, kan de Windows 10-bedrijfsportal-app worden geïmplementeerd via een van de bovenstaande opties.  

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal hebt geïmplementeerd zonder deze ondertekenen met het Symantec-certificaat, volgt u de stappen in de bovenstaande sectie Deploy directly via Intune (Rechtstreeks implementeren via Intune) om de upgrade te voltooien.

Als u de app moet sideloaden en de Windows 8.1-bedrijfsportal hebt ondertekend en geïmplementeerd met het Symantec-certificaat voor ondertekening van programmacode, volgt u de stappen in de onderstaande sectie.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Hoe kan ik een upgrade uitvoeren van mijn ondertekende en gesideloade Windows Phone 8.1-bedrijfsportal-app of Windows 8.1-bedrijfsportal-app naar de Windows 10-bedrijfsportal-app?
Het wordt aanbevolen de bestaande implementatie voor de Windows Phone 8.1-bedrijfsportal-app of de Windows 8.1-bedrijfsportal-app te verwijderen door de implementatieactie in te stellen op Installatie ongedaan maken. Zodra deze actie is uitgevoerd, kan de Windows 10-bedrijfsportal-app normaal worden geïmplementeerd.  

Anders moet de Windows 10-bedrijfsportal-app op de juiste manier worden bijgewerkt en ondertekend om ervoor te zorgen dat het upgradepad in acht wordt genomen.  

Als de Windows 10-bedrijfsportal-app op deze manier is ondertekend en geïmplementeerd, moet u dit proces herhalen voor elke nieuwe app-update wanneer deze beschikbaar is in de Store. De app wordt niet automatisch bijgewerkt wanneer de Store wordt bijgewerkt.  

U ondertekent en implementeer de app als volgt:

1. Download het ondertekeningsscript voor de Microsoft Intune Windows 10-bedrijfsportal-app van [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Voor dit script moet de Windows SDK voor Windows 10 moet zijn geïnstalleerd op de hostcomputer. Ga naar [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) om de Windows SDK voor Windows 10 te downloaden.
2. Download de Windows 10-bedrijfsportal-app vanuit Microsoft Store voor Bedrijven, zoals hierboven beschreven.  
3. Voer het script uit met de invoerparameters die zijn opgegeven in de koptekst van het script om de Windows-10-bedrijfsportal-app (hieronder uitgepakt) te ondertekenen. Afhankelijkheden hoeven niet in het script te worden doorgegeven. Deze zijn alleen vereist wanneer de app wordt geüpload naar de Intune-beheerconsole.

|       Parameter       |                                                                    Beschrijving                                                                    |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                             Het pad naar het bron-appxbundle-bestand.                                              |
| OutputWin10AppxBundle |                                                  Het uitvoerpad voor het ondertekende appxbundle-bestand.                                                  |
|       Win81Appx       |                          Het pad naar het Windows 8.1- of Windows Phone 8.1-bedrijfsportalbestand (het APPX-bestand).                           |
|      PfxFilePath      |                                   Het pad naar het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec (het PFX-bestand).                                    |
|      PfxPassword      |                                     Het wachtwoord voor het certificaat voor ondertekening van programmacode voor mobiele bedrijfsapparaten van Symantec.                                      |
|      PublisherId      |      De uitgevers-id van de onderneming. Als deze niet is opgegeven, wordt het veld Onderwerp van Symantec Enterprise-certificaat voor ondertekening van mobiele code gebruikt.       |
|        SdkPath        | Het pad naar de hoofdmap van de Windows-SDK voor Windows 10. Dit argument is optioneel en wordt standaard ingesteld op ${env:ProgramFiles(x86)} \Windows Kits\10 |

Via het script wordt de ondertekende versie van de Windows 10-bedrijfsportal-app uitgevoerd wanneer het uitvoeren van de app is voltooid. Vervolgens implementeert u de ondertekende versie van de app als een LOB-app via Intune. De huidige geïmplementeerde versies worden bijgewerkt naar deze nieuwe app.  
