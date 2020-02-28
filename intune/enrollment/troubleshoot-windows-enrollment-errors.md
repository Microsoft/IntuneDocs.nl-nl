---
title: Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen
titleSuffix: Microsoft Intune
description: Suggesties voor het oplossen van een aantal van de meestvoorkomende problemen bij het inschrijven van Windows-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dae8e92209a8640ab3254e073d3043d390c3791b
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514248"
---
# <a name="troubleshoot-windows-device-enrollment-problems-in-microsoft-intune"></a>Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen

Dit artikel helpt Intune-beheerders om problemen bij het inschrijven van Windows-apparaten in Intune te begrijpen en op te lossen.

## <a name="prerequisites"></a>Vereisten
Voordat u begint met de probleemoplossing, is het belangrijk om enkele basisgegevens te verzamelen. Deze gegevens kunnen u helpen het probleem beter te begrijpen en sneller een oplossing voor het probleem te vinden.

Verzamel de volgende gegevens van het probleem:
- Is er een geldige Intune-licentie toegewezen aan de gebruiker? Voordat gebruikers hun apparaat kunnen inschrijven, moet de benodigde licentie aan hen zijn toegewezen.
- Is de meest recente update geïnstalleerd op het Windows-apparaat? Sommige functies in Intune werken alleen met de nieuwste versie van Windows. Er zijn veel oplossingen voor bekende problemen beschikbaar via Windows Update. Problemen met het inschrijven van Windows-apparaten kunnen vaak worden opgelost door alle meest recente updates toe te passen. 
- Wat is het exacte foutbericht?
- Waar wordt het foutbericht weergegeven?
- Wanneer is het probleem begonnen? Heeft de inschrijving ooit gewerkt? 
- Op welk platform (Android, iOS/iPadOS, Windows) doet het probleem zich voor?
- Hoeveel gebruikers treft het probleem? Geldt het probleem voor alle gebruikers of voor bepaalde gebruikers?
- Voor hoeveel apparaten geldt het probleem? Geldt het probleem voor alle apparaten of voor bepaalde apparaten?
- Wat is de MDM-instantie?
- Hoe wordt de inschrijving uitgevoerd? Wordt BYOD (Bring Your Own Device) of Apple DEP (Device Enrollment Program) gebruikt met inschrijvingsprofielen?

## <a name="error-messages"></a>Foutberichten

### <a name="this-user-is-not-authorized-to-enroll"></a>Deze gebruiker is niet gemachtigd om zich in te schrijven.

Fout 0x801c003: Deze gebruiker is niet bevoegd om te registreren. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode (0x801c0003) "
Fout 80180003: "Er is iets misgegaan. Deze gebruiker is niet gemachtigd om zich in te schrijven. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode 80180003 "

**Oorzaak:** Een of meer van de volgende omstandigheden: 

- De gebruiker heeft het maximaal toegestane aantal apparaten ingeschreven in Intune.    
- Het apparaat wordt geblokkeerd door de beperkingen voor het apparaattype.    
- Op de computer wordt Windows 10 Home uitgevoerd. Inschrijven in Intune of deelname aan Azure AD wordt echter alleen ondersteund in Windows 10 Pro en hogere versies.

#### <a name="resolution"></a>Oplossing
Er zijn verschillende mogelijke oplossingen voor dit probleem:

##### <a name="remove-devices-that-were-enrolled"></a>Apparaten verwijderen die zijn ingeschreven
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).    
2. Ga naar **Gebruikers** > **Alle gebruikers**.    
3. Selecteer het betrokken gebruikersaccount en klik vervolgens op **Apparaten**.    
4. Selecteer alle ongebruikte of ongewenste apparaten en klik vervolgens op **Verwijderen**. 

##### <a name="increase-the-device-enrollment-limit"></a>Verhoog de limiet voor apparaatinschrijvingen

> [!NOTE]
> Met deze methode verhoogt u de inschrijvingslimiet voor apparaten voor alle gebruikers, niet alleen voor de betrokken gebruiker.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Ga naar **Apparaten** > **Inschrijvingsbeperkingen** > **Standaard** (onder **Beperkingen voor apparaatlimieten**) > **Eigenschappen** > **Bewerken** (naast **Apparaatlimiet**) > verhoog de waarde voor **Apparaatlimiet** (maximaal 15) > **Controleren en opslaan**.    
 

##### <a name="check-device-type-restrictions"></a>Beperkingen voor apparaattypen controleren
1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) met een algemeen beheerdersaccount.
2. Ga naar **Apparaten** > **Inschrijvingsbeperkingen**en selecteer vervolgens de beperking **Standaard** onder **Apparaattypebeperkingen**.    
3. Selecteer **Platformen**en selecteer vervolgens **Toestaan** voor **Windows (MDM)** .

    > [!IMPORTANT]
    > Als **Toestaan** al de huidige instelling is, wijzigt u deze in **Blokkeren**, slaat u de instelling op, wijzigt u deze weer in **Toestaan** en slaat u de instelling opnieuw op. Hiermee wordt de instelling voor inschrijving opnieuw ingesteld.

4. Wacht ongeveer 15 minuten en schrijf het betreffende apparaat vervolgens opnieuw in.    

##### <a name="upgrade-windows-10-home"></a>Upgrade uitvoeren voor Windows 10 Home
[Voer een upgrade uit van Windows 10 Home naar Windows 10 Pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) of een hogere editie. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Deze gebruiker is niet bevoegd om te registreren.

Fout 0x801c0003: 'Deze gebruiker is niet bevoegd om te registreren. U kunt het opnieuw proberen of contact opnemen met uw systeembeheerder met de foutcode 801c0003."

**Oorzaak:** De instelling **Gebruikers mogen apparaten aan Azure AD toevoegen** heeft de waarde **Geen**. Hierdoor kunnen nieuwe gebruikers hun apparaten niet toevoegen aan Azure AD. Met als gevolg dat ook de Intune-inschrijving mislukt.

#### <a name="resolution"></a>Oplossing
1. Meld u als beheerder aan bij [Azure Portal](https://portal.azure.com/).    
2. Ga naar **Azure Active Directory** > **Apparaten** > **Apparaatinstellingen**.    
3. Stel **Gebruikers mogen apparaten aan Azure AD toevoegen** in op **Alle**.    
4. Schrijf het apparaat opnieuw in.   

### <a name="the-device-is-already-enrolled"></a>Het apparaat is al ingeschreven.

Fout 8018000a: 'Er is iets fout gegaan. Het apparaat is al ingeschreven.  U kunt contact opnemen met de systeembeheerder met de foutcode 8018000a.'

**Oorzaak:** Een van de volgende omstandigheden:
- Een andere gebruiker heeft het apparaat al ingeschreven in Intune of toegevoegd aan Azure AD. Als u wilt controleren of dit het geval is, gaat u naar **Instellingen** > **Accounts** > **Toegang via het werknetwerk**. Zoek naar een bericht met ongeveer deze tekst: 'Een andere gebruiker in het systeem is al verbonden met werk of school. Verwijder die verbinding met werk of school en probeer het opnieuw.'    

#### <a name="resolution"></a>Oplossing

Gebruik een van de volgende methoden om dit probleem op te lossen:

##### <a name="remove-the-other-work-or-school-account"></a>Het andere werk- of schoolaccount verwijderen
1. Meld u af bij Windows en meld u vervolgens aan met het andere account dat is ingeschreven of is toegevoegd aan het apparaat.    
2. Ga naar **Instellingen** > **Accounts** > **Toegang via het werknetwerk**en verwijder vervolgens het werk- of schoolaccount.
3. Meld u af bij Windows en meld u vervolgens aan met uw account.    
4. Schrijf het apparaat in bij Intune of voeg het apparaat toe aan Azure AD. 



### <a name="this-account-is-not-allowed-on-this-phone"></a>Dit account is niet toegestaan op deze telefoon.

Fout: 'Dit account is niet toegestaan op deze telefoon. Controleer of de informatie die u hebt ingevoerd juist is en probeer het opnieuw of vraag uw bedrijf om ondersteuning.'

**Oorzaak:** De gebruiker die heeft geprobeerd het apparaat in te schrijven, heeft geen geldige Intune-licentie.

#### <a name="resolution"></a>Oplossing
Wijs een geldige Intune-licentie toe aan de gebruiker en schrijf het apparaat vervolgens in.


### <a name="looks-like-the-mdm-terms-of-use-endpoint-is-not-correctly-configured"></a>Het lijkt erop dat het eindpunt voor de MDM-gebruiksvoorwaarden niet juist is geconfigureerd.

**Oorzaak:** Een van de volgende omstandigheden: 
 - U gebruikt zowel MDM (Mobile Device Management) voor Office 365 als Intune op de tenant en de gebruiker die probeert het apparaat in te schrijven, heeft geen geldige Intune-licentie of Office 365-licentie.     
- De MDM-voorwaarden in Azure AD zijn leeg of bevatten niet de juiste URL.    

#### <a name="resolution"></a>Oplossing

Gebruik een van de volgende methoden om dit probleem op te lossen: 
 
##### <a name="assign-a-valid-license-to-the-user"></a>Een geldige licentie toewijzen aan de gebruiker
Ga naar het [Microsoft 365-beheercentrum](https://portal.office.com/adminportal/home)en wijs een Intune-of een Office 365-licentie toe aan de gebruiker.

##### <a name="correct-the-mdm-terms-of-use-url"></a>De URL voor de MDM-gebruiksvoorwaarden corrigeren
  1. Meld u aan bij de [Azure-portal](https://portal.azure.com/) en selecteer vervolgens **Azure Active Directory**.    
  2. Selecteer **Mobiliteit (MDM en MAM)** en klik vervolgens op **Microsoft Intune**.    
  3. Selecteer **Standaard MDM-URL's herstellen** en controleer of **URL voor MDM-gebruiksvoorwaarden** is ingesteld op **https://portal.manage.microsoft.com/TermsofUse.aspx** .    
  4. Kies **Opslaan**.    


### <a name="something-went-wrong"></a>Er is iets misgegaan.

Fout 80180026: "Er is iets misgegaan. Controleer of u de juiste aanmeldingsgegevens gebruikt en uw organisatie deze functie gebruikt. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode 80180026 "

**Oorzaak:** Deze fout kan optreden wanneer u probeert een Windows 10-computer toe te voegen aan Azure AD en aan beide van de volgende voorwaarden wordt voldaan: 
- Automatische MDM-inschrijving is ingeschakeld in Azure.    
- De Intune PC-client (Intune PC-agent) is geïnstalleerd op de Windows 10-computer.

#### <a name="resolution"></a>Oplossing
Gebruik een van de volgende methoden om dit probleem op te lossen:

##### <a name="disable-mdm-automatic-enrollment-in-azure"></a>Schakel automatische MDM-inschrijving in Azure uit.
1. Meld u aan bij [Azure Portal](https://portal.azure.com/).    
2. Ga naar **Azure Active Directory** > **Mobiliteit (MDM en MAM)**  > **Microsoft Intune**.    
3. Stel **MDM-gebruikersbereik** in op **Geen** en klik vervolgens op **Opslaan**.    
     
##### <a name="uninstall"></a>Verwijderen
Verwijder de Intune PC-clientagent van de computer.    

### <a name="the-software-cannot-be-installed"></a>De software kan niet worden geïnstalleerd.

Fout: 'De software kan niet worden geïnstalleerd, 0x80cf4017.'

**Oorzaak:** De clientsoftware is verouderd.

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Ga naar **Beheerder** > **Clientsoftware downloaden**en klik vervolgens op **Clientsoftware downloaden**.    
3. Sla het installatie pakket op en installeer vervolgens de clientsoftware. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>Het accountcertificaat is niet geldig en is mogelijk verlopen.

Fout: "Het accountcertificaat is niet geldig en is mogelijk verlopen, 0x80cf4017."

**Oorzaak:** De clientsoftware is verouderd.

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Ga naar **Beheerder** > **Clientsoftware downloaden**en klik vervolgens op **Clientsoftware downloaden**.    
3. Sla het installatie pakket op en installeer vervolgens de clientsoftware.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Uw organisatie biedt geen ondersteuning voor deze versie van Windows. 

Fout: 'Er is een probleem opgetreden. Uw organisatie biedt geen ondersteuning voor deze versie van Windows.  (0x80180014)'

**Oorzaak:** Windows MDM-inschrijving is uitgeschakeld in uw Intune-tenant.

#### <a name="resolution"></a>Oplossing
Voer deze stappen uit om dit probleem op te lossen in een zelfstandige Intune-omgeving: 
 
1. Kies in het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) **Apparaten** > **Inschrijvingsbeperkingen** > kies een beperking voor het apparaattype.    
2. Kies **Eigenschappen** > **Bewerken** (naast **Platforminstellingen**) > **Toestaan** voor **Windows (MDM)** .    
3. Klik op **Beoordelen en opslaan**.    

### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Er is een configuratiefout opgetreden tijdens de bulkinschrijving.

**Oorzaak:** De Azure AD-gebruikersaccounts in het accountpakket (Package_GUID) voor het betreffende inrichtingspakket mogen geen apparaten toevoegen aan Azure AD. Deze Azure AD-accounts worden automatisch gemaakt wanneer u een inrichtingspakket instelt met behulp van WCD (Windows Configuration Designer) of de app Set up School PCs. Deze accounts kunnen worden vervolgens gebruikt om de apparaten toe te voegen aan Azure AD.

#### <a name="resolution"></a>Oplossing
1. Meld u als beheerder aan bij [Azure Portal](https://portal.azure.com/).    
2. Ga naar **Azure Active Directory > Apparaten > Apparaatinstellingen**.    
3. Stel **Gebruikers mogen apparaten aan Azure AD toevoegen** in op **Alle** of **Geselecteerd**.

   Als u **Geselecteerd** kiest, klikt u op **Geselecteerd**en klikt u vervolgens op **Leden toevoegen** om alle gebruikers toe te voegen die hun apparaten kunnen toevoegen aan Azure AD. Zorg ervoor dat alle Azure AD-accounts voor het inrichtingspakket worden toegevoegd.
 
Zie [Create a provisioning package for Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package) (Een inrichtingspakket maken voor Windows 10) voor meer informatie over het maken van een inrichtingspakket voor Windows Configuration Designer.

Zie [Use the Set up School PCs app](https://docs.microsoft.com/education/windows/use-set-up-school-pcs-app) (De app Set up School PCs gebruiken) voor meer informatie over de app Set up School PCs.


### <a name="auto-mdm-enroll-failed"></a>Automatische MDM-inschrijving: mislukt 

Wanneer u probeert een Windows 10-apparaat automatisch in te schrijven met behulp van groepsbeleid, treden de volgende problemen op: 
- In Task Scheduler, onder **Microsoft** > **Windows** > **EnterpriseMgmt**, is het resultaat van de laatste uitvoering van de taak **Planning gemaakt door inschrijvingsclient voor automatische inschrijving in MDM vanuit AAD** als volgt: **Event 76 Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x8018002b)**       
- In Logboeken wordt de volgende gebeurtenis vastgelegd onder **Applications and Services Logs/Microsoft/Windows/DeviceManagement-Enterprise-Diagnostics-Provider/Admin**:   
    ```asciidoc
    Log Name: Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
    Source: DeviceManagement-Enterprise-Diagnostics-Provider
    Event ID: 76
    Level: Error
    Description: Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x80180002b)
    ```
**Oorzaak:** Een van de volgende omstandigheden: 
- De UPN bevat een niet-geverifieerd of niet-routeerbaar domein, zoals. local (bijvoorbeeld joe@contoso.local).    
- **MDM-gebruikersbereik** is ingesteld op **Geen**. 

#### <a name="resolution"></a>Oplossing
Als de UPN een niet-geverifieerd of niet-routeerbaar domein bevat, voert u deze stappen uit: 

1. Open op de server waarop AD DS (Active Directory Domain Services) wordt uitgevoerd **Active Directory: gebruikers en computers** door **dsa.msc** te typen in het dialoogvenster **Uitvoeren** en vervolgens op **OK** te klikken.    
2. Klik op **Gebruikers** onder uw domein en ga als volgt te werk:  
    - Als er slechts één betrokken gebruiker is, klikt u met de rechtermuisknop op de gebruiker en klikt u vervolgens op **Eigenschappen**. Ga op het tabblad **Account** naar de vervolgkeuzelijst UPN-achtervoegsel onder **Aanmeldingsnaam gebruiker** en selecteer een geldig UPN-achtervoegsel, bijvoorbeeld contoso.com, en klik vervolgens op **OK**.    
    - Als er meerdere betrokken gebruikers zijn, selecteert u de gebruikers en klikt u in het menu **Actie** op **Eigenschappen**. Schakel op het tabblad **Account** het selectievakje **UPN-achtervoegsel** in, selecteer een geldig UPN-achtervoegsel zoals contoso.com in de vervolgkeuzelijst en klik vervolgens op **OK**.
3. Wacht op de volgende synchronisatie of dwing een deltasynchronisatie af vanaf de synchronisatieserver door de volgende opdrachten uit te voeren in een PowerShell-prompt met verhoogde bevoegdheid:
    ```powershell
    Import-Module ADSync
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

Als **MDM-gebruikersbereik** is ingesteld op **Geen**, voert u deze stappen uit: 
 
1. Meld u aan bij de [Azure-portal](https://portal.azure.com/) en selecteer vervolgens **Azure Active Directory**.
2. Selecteer **Mobiliteit (MDM en MAM)** en selecteer vervolgens **Microsoft Intune**.    
3. Stel **MDM-gebruikersbereik** in op **Alle**. Of stel **MDM-gebruikersbereik** in op **Sommige**en selecteer de groepen die hun Windows 10-apparaten automatisch kunnen inschrijven.    
4. Stel **MAM-gebruikersbereik** in op **Geen**.


### <a name="an-error-occurred-while-creating-autopilot-profile"></a>Er is een fout opgetreden bij het maken van het Autopilot-profiel.

**Oorzaak:** De opgegeven naamgevingsindeling voor de sjabloon voor de apparaatnaam voldoet niet aan de vereisten. U gebruikt bijvoorbeeld kleine letters voor de %SERIAL%-macro, zoals %serial% in plaats van %SERIAL%.

#### <a name="resolution"></a>Oplossing

Zorg ervoor dat de naamgevingsindeling voldoet aan de volgende vereisten:

- Maak een unieke naam voor uw apparaten. Namen moeten 15 tekens of minder bevatten, en mogen letters (a-z, A-Z), cijfers (0-9) en afbreekstreepjes (-) bevatten.
- Namen mogen niet alleen uit getallen bestaan.
- Namen mogen geen spaties bevatten.
- Gebruik de %SERIAL%-macro om het serienummer toe te voegen van specifieke hardware. Of gebruik de macro %RAND:<aantal cijfers>% om een willekeurige reeks getallen toe te voegen, waarbij de tekenreeks <aantal cijfers> cijfers bevat. Met MYPC-%RAND:6% genereert u bijvoorbeeld een naam zoals MYPC-123456.

### <a name="something-went-wrong-oobeidps"></a>Er is iets misgegaan. OOBEIDPS.

**Oorzaak:** Dit probleem doet zich voor als er een proxy, een firewall of een ander netwerkapparaat is dat de toegang tot de id-provider (IdP) blokkeert.

#### <a name="resolution"></a>Oplossing
Zorg ervoor dat de vereiste toegang tot op internet gebaseerde services voor Autopilot niet wordt geblokkeerd. Zie [Windows Autopilot requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements-network) (Vereisten voor Windows Autopilot) voor meer informatie.


### <a name="registering-your-device-for-mobile-management-failed3-0x801c03ea"></a>Uw apparaat registreren voor mobiel beheer (Failed:3, 0x801C03EA).

**Oorzaak:** Het apparaat heeft een TPM-chip die versie 2.0 ondersteunt, maar die nog niet is bijgewerkt naar versie 2.0.

#### <a name="resolution"></a>Oplossing
Voer een upgrade van de TPM-chip uit naar versie 2.0.

Als het probleem zich blijft voordoen, controleert u of hetzelfde apparaat zich in twee toegewezen groepen bevindt, waarbij aan elke groep een ander Autopilot-profiel wordt toegewezen. Als dit het geval is, bepaalt u welk Autopilot-profiel moet worden toegepast op het apparaat en verwijdert u vervolgens de toewijzing van het andere profiel.

Zie [Deploying a kiosk using Windows Autopilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/) (Engelstalig) voor meer informatie over het implementeren van een Windows-apparaat in kioskmodus met Autopilot.


### <a name="securing-your-hardware-failed-0x800705b4"></a>Uw hardware beveiligen (Failed: 0x800705b4).

Fout 800705b4: 
```
Securing your hardware (Failed: 0x800705b4)
Joining your organization's network (Previous step failed)
Registering your device for mobile management (Previous step failed)
```

**Oorzaak:** Het Windows-doelapparaat voldoet niet aan een van de volgende vereisten:

- Het apparaat moet een fysieke TPM 2.0-chip hebben. Apparaten met virtuele TPM's (bijvoorbeeld Hyper-V-VM's) of TPM 1.2-chips werken niet met de zelf-implementatiemodus.
- Op het apparaat moet een van de volgende versies van Windows worden uitgevoerd:
    - Windows 10 build 1703 of een hogere versie.
    - Als Hybrid Azure AD Join wordt gebruikt, Windows 10 build 1809 of een hogere versie.


#### <a name="resolution"></a>Oplossing
Zorg ervoor dat het doelapparaat voldoet aan beide vereisten die worden beschreven in de sectie **Oorzaak**.

Zie [Deploying a kiosk using Windows Autopilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/) (Engelstalig) voor meer informatie over het implementeren van een Windows-apparaat in kioskmodus met Autopilot.


### <a name="something-went-wrong-error-code-80070774"></a>Er is iets misgegaan. Foutcode 80070774.

Fout 0x80070774: Er is iets fout gegaan. Controleer of u de juiste aanmeldingsgegevens gebruikt en uw organisatie deze functie gebruikt. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode 80070774.

Dit probleem treedt meestal op voordat het apparaat opnieuw wordt opgestart in een Autopilot-scenario met hybride Azure AD, wanneer het apparaat een time-out heeft tijdens het eerste aanmeldingsscherm. Dit betekent dat de domeincontroller niet kan worden gevonden of niet kan worden bereikt vanwege verbindingsproblemen. Of het apparaat heeft een status waardoor het apparaat niet kan worden toegevoegd aan het domein.

**Oorzaak:** De meestvoorkomende oorzaak is dat hybride Azure AD Join wordt gebruikt en dat de functie voor het toewijzen van gebruikers is geconfigureerd in het Autopilot-profiel. Met deze functie wordt een Azure AD Join op het apparaat uitgevoerd tijdens het eerste aanmeldingsscherm waarmee het apparaat in een toestand wordt geplaatst waarin het niet kan worden toegevoegd aan uw on-premises domein. Daarom mag de functie voor het toewijzen van gebruikers alleen worden gebruikt in standaardscenario's van Autopilot met Azure AD Join.  De functie mag niet worden gebruikt in scenario's met hybride Azure AD Join.

#### <a name="resolution"></a>Oplossing

1. Kies in het [beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) > **Apparaten** > **Windows** - > **Windows-apparaten**.
2. Selecteer het apparaat waarop het probleem zich voordoet > klik op het beletselsteken (...) helemaal rechts.
3. Selecteer **Toewijzing van de gebruiker intrekken** en wacht totdat het proces is voltooid.
4. Controleer of het Autopilot-profiel voor hybride Azure AD is toegewezen voordat u OOBE opnieuw probeert uit te voeren.

#### <a name="second-resolution"></a>Tweede oplossing
Als het probleem zich blijft voordoen, controleert u op de server die als host fungeert voor de Intune-connector Offline Domain Join of gebeurtenis-id 30312 is geregistreerd in het logboek van de ODJ Connector-service. Gebeurtenis 30312 lijkt op het volgende:

```
Log Name:      ODJ Connector Service
Source:        ODJ Connector Service Source
Event ID:      30132
Level:         Error
Description:
{
          "Metric":{
                   "Dimensions":{
                             "RequestId":"<RequestId>",
                             "DeviceId":"<DeviceId>",
                             "DomainName":"contoso.com",
                             "ErrorCode":"5",
                             "RetryCount":"1",
                              "ErrorDescription":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation",
                              "InstanceId":"<InstanceId>",
                              "DiagnosticCode":"0x00000800",
                              "DiagnosticText":"Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation [Exception Message: \"DiagnosticException: 0x00000800. Failed to get the ODJ Blob. The ODJ connector does not have sufficient privileges to complete the operation\"] [Exception Message: \"Failed to call NetProvisionComputerAccount machineName=<ComputerName>\"]"
                   },
                   "Name":"RequestOfflineDomainJoinBlob_Failure",
                   "Value":0
          }
}
```

Dit probleem wordt meestal veroorzaakt door het onjuist delegeren van machtigingen aan de organisatie-eenheid waar de Windows Autopilot-apparaten worden gemaakt. Zie [Increase the computer account limit in the Organizational Unit](windows-autopilot-hybrid.md#increase-the-computer-account-limit-in-the-organizational-unit) (Engelstalig) voor meer informatie.

1. Open **Active Directory: gebruikers en computers (DSA.msc)** .
2. Klik met de rechtermuisknop op de organisatie-eenheid die u gaat gebruiken om aan Hybrid Azure AD gekoppelde computers te maken > **Beheer delegeren**.
3. Kies in de wizard **Overdracht van beheer** **Volgende** > **Toevoegen** > **Objecttypen**.
4. Selecteer in het deelvenster **Objecttypen** het selectievakje **Computers** > **OK**.
5. Voer in het deelvenster voor het selecteren van **Gebruikers**, **Computers** of **Groepen** in het vak **Te selecteren objectnamen invoeren** de naam in van de computer waarop de connector is geïnstalleerd.
6. Selecteer **Namen controleren** om uw invoer te valideren > **OK** > **Volgende**.
7. Selecteer **Een aangepaste taak maken om te delegeren** > **Volgende**.
8. Selecteer het selectievakje **Alleen de volgende objecten in de map** en schakel vervolgens de selectievakjes **Computerobjecten**, **Geselecteerde objecten in deze map maken** en **Geselecteerde objecten in deze map verwijderen** in.
9. Selecteer **Volgende**.
10. Onder **Machtigingen** schakelt u het selectievakje **Volledige bevoegdheid** in. Met deze actie selecteert u alle andere opties.
11. Selecteer **Volgende** > **Voltooien**.

### <a name="the-enrollment-status-page-times-out-before-the-sign-in-screen"></a>Er treedt een time-out op voor de pagina met de inschrijvingsstatus voordat het aanmeldingsscherm wordt weergegeven

**Oorzaak:** Dit probleem kan zich voordoen als alle volgende voorwaarden van toepassing zijn:
- U gebruikt de pagina met de inschrijvingsstatus om apps van Microsoft Store voor Bedrijven bij te houden.
- U hebt een beleid voor voorwaardelijke toegang van Azure AD dat vereist dat een apparaat expliciet wordt gemarkeerd als compatibel.
- Het beleid is van toepassing op alle cloud-apps en Windows.

#### <a name="resolution"></a>Oplossing:
Probeer een van de volgende methoden:
- Richt uw Intune-nalevingsbeleid op apparaten. Zorg ervoor dat naleving kan worden bepaald voordat de gebruiker zich aanmeldt.
- Gebruik offline licenties voor Store-apps. Op deze manier hoeft de Windows-client geen contact op te nemen met de Microsoft Store om de naleving van het apparaat te bepalen.



## <a name="next-steps"></a>Volgende stappen

- [Problemen bij de apparaatinschrijving oplossen](../troubleshoot-device-enrollment-in-intune.md)
- [Stel een vraag op het Intune-forum](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Lees de blog van het Microsoft Intune Support Team](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Lees de blog Microsoft Enterprise Mobility and Security](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md)
- [Inschrijvingsfouten van co-beheer zoeken](https://docs.microsoft.com/configmgr/comanage/how-to-monitor#enrollment-errors)
