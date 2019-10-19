---
title: Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen
titleSuffix: Microsoft Intune
description: Suggesties voor het oplossen van problemen met een aantal van de meest voorkomende problemen bij het inschrijven van Windows-apparaten bij intune.
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
ms.openlocfilehash: 1089c382a39afb5aad0456e669cb3a2434af73c1
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503104"
---
# <a name="troubleshoot-windows-device-enrollment-problems-in-microsoft-intune"></a>Problemen met inschrijving van Windows-apparaten in Microsoft Intune oplossen

Dit artikel helpt intune-beheerders bij het registreren en oplossen van problemen bij het inschrijven van Windows-apparaten in intune.

## <a name="prerequisites"></a>Vereisten
Voordat u begint met het oplossen van problemen, is het belang rijk om enkele basis informatie te verzamelen. Deze informatie kan u helpen het probleem beter te begrijpen en de tijd te verkorten om een oplossing te vinden.

Verzamel de volgende informatie over het probleem:
- Is er een geldige intune-licentie toegewezen aan de gebruiker? Voordat gebruikers hun apparaat kunnen inschrijven, moet de benodigde licentie aan hen zijn toegewezen.
- Is de meest recente update geïnstalleerd op het Windows-apparaat? Sommige functies in intune werken alleen met de nieuwste versie van Windows. Er zijn veel oplossingen voor bekende problemen die beschikbaar zijn via Windows Update. Het Toep assen van alle meest recente updates corrigeert vaak een probleem met het registreren van Windows-apparaten. 
- Wat is het exacte foutbericht?
- Waar wordt het fout bericht weer gegeven?
- Wanneer is het probleem begonnen? Heeft de inschrijving ooit gewerkt? 
- Welk platform (Android, iOS, Windows) heeft het probleem?
- Hoeveel gebruikers zijn er betrokken? Zijn alle gebruikers betrokken of slechts een deel ervan?
- Hoeveel apparaten heeft het probleem? Zijn alle apparaten betrokken of slechts een deel ervan?
- Wat is de MDM-instantie? Als het System Center Configuration Manager, welke versie van Configuration Manager gebruikt u?
- Hoe wordt de inschrijving uitgevoerd? Kunt u uw eigen apparaat (BYOD) of Apple Device Enrollment Program (DEP) met inschrijvings profielen meenemen?

## <a name="error-messages"></a>Foutberichten

### <a name="this-user-is-not-authorized-to-enroll"></a>Deze gebruiker is niet gemachtigd om in te schrijven.

Fout 0x801c003: deze gebruiker is niet gemachtigd om in te schrijven. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode (0x801c0003) "
Fout 80180003: Er is iets misgegaan. Deze gebruiker is niet gemachtigd om in te schrijven. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode 80180003 "

**Oorzaak:** Een van de volgende voor waarden: 

- De gebruiker heeft het Maxi maal toegestane aantal apparaten in intune al Inge schreven.    
- Het apparaat wordt geblokkeerd door de beperkingen voor het apparaattype.    
- Op de computer wordt Windows 10 Home uitgevoerd. Registratie in intune of deelname aan Azure AD wordt alleen ondersteund in Windows 10 Pro en hogere versies.

#### <a name="resolution"></a>Oplossing
Er zijn verschillende mogelijke oplossingen voor dit probleem:

##### <a name="remove-devices-that-were-enrolled"></a>Apparaten verwijderen die zijn geregistreerd
1. Meld u aan bij [Azure Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).    
2. Ga naar **gebruikers**  > **alle gebruikers**.    
3. Selecteer het betrokken gebruikers account en klik vervolgens op **apparaten**.    
4. Selecteer alle ongebruikte of ongewenste apparaten en klik vervolgens op **verwijderen**. 

##### <a name="increase-the-device-enrollment-limit"></a>Verhoog de limiet voor apparaatinschrijvingen

> [!NOTE]
> Deze methode verhoogt de registratie limiet voor apparaten voor alle gebruikers, niet alleen de betrokken gebruiker.

1. Meld u aan bij [Azure Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).
2. Ga naar inschrijving van **apparaten**  > **inschrijvings beperkingen**en selecteer vervolgens **limieten voor het aantal apparaten**.    
3. Verhoog de waarde van de limiet van het **apparaat**. 

##### <a name="check-device-type-restrictions"></a>Beperkingen voor apparaattypen controleren
1. Meld u aan bij de [Intune-portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) met een account voor globale beheerders.
2. Ga naar inschrijving van **apparaten**  > **inschrijvings beperkingen**en selecteer vervolgens de **standaard** beperking onder beperkingen voor het **Apparaattype**.    
3. Selecteer **platforms**en selecteer vervolgens **toestaan** voor **Windows (MDM)** .

    > [!IMPORTANT]
    > Als de huidige instelling al is **toegestaan**, wijzigt u deze in **blok keren**, slaat u de instelling op en wijzigt u deze weer in **toestaan** en slaat u de instelling opnieuw op. Hiermee wordt de instelling voor inschrijving opnieuw ingesteld.

4. Wacht ongeveer 15 minuten en schrijf het betreffende apparaat vervolgens opnieuw in.    

##### <a name="upgrade-windows-10-home"></a>Windows 10-start pagina upgraden
Voer een [upgrade uit van Windows 10 Home naar Windows 10 Pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) of een hogere editie. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Deze gebruiker mag zich niet inschrijven.

Fout 0x801c0003: ' deze gebruiker is niet gemachtigd om in te schrijven. U kunt het opnieuw proberen of contact opnemen met uw systeembeheerder met de foutcode 801c0003."

**Oorzaak:** De **gebruikers kunnen lid worden van apparaten met de Azure AD** -instelling is ingesteld op **geen**. Zo voor komt u dat nieuwe gebruikers hun apparaten kunnen toevoegen aan Azure AD. Daarom mislukt de intune-inschrijving.

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij de [Azure Portal](https://portal.azure.com/) als beheerder.    
2. Ga naar **Azure Active Directory**  > **apparaten**  > **Apparaatinstellingen**.    
3. Stel **Gebruikers mogen apparaten aan Azure AD toevoegen** in op **Alle**.    
4. Schrijf het apparaat opnieuw in.   

### <a name="the-device-is-already-enrolled"></a>Het apparaat is al ingeschreven.

Fout 8018000a: er is iets verkeerd gegaan. Het apparaat is al ingeschreven.  U kunt contact opnemen met de systeem beheerder met de fout code 8018000a. "

**Oorzaak:** Een van de volgende voor waarden is waar:
- Een andere gebruiker heeft het apparaat al Inge schreven bij intune of het apparaat is toegevoegd aan Azure AD. Als u wilt weten of dit het geval is, gaat u naar **instellingen**  > **accounts**  > **toegang tot het werk**. Zoek naar een bericht dat er ongeveer als volgt uitziet: ' een andere gebruiker op het systeem is al verbonden met een werk-of school account. Verwijder die werk-of school verbinding en probeer het opnieuw. "    
- De Configuration Manager-client agent wordt op de computer geïnstalleerd.    

#### <a name="resolution"></a>Oplossing

Gebruik een van de volgende methoden om dit probleem op te lossen:

##### <a name="remove-the-other-work-or-school-account"></a>Het andere werk-of school account verwijderen
1. Meld u af bij Windows en meld u vervolgens aan met het andere account dat is inge schreven of lid is van het apparaat.    
2. Ga naar **instellingen**  > **accounts**  > **toegang tot het werk**en verwijder vervolgens het werk-of school account.
3. Meld u af bij Windows en meld u vervolgens aan met uw account.    
4. Registreer het apparaat bij intune of Voeg het apparaat toe aan Azure AD. 

##### <a name="remove-the-configuration-manager-client"></a>Configuration Manager-client verwijderen
Verwijder de Configuration Manager-client en schrijf het apparaat opnieuw in.



### <a name="this-account-is-not-allowed-on-this-phone"></a>Dit account is niet toegestaan op deze telefoon.

Fout: ' dit account is niet toegestaan op deze telefoon. Controleer of de informatie die u hebt ingevoerd juist is en probeer het opnieuw of vraag uw bedrijf om ondersteuning.

**Oorzaak:** De gebruiker die het apparaat heeft geregistreerd, heeft geen geldige intune-licentie.

#### <a name="resolution"></a>Oplossing
Wijs een geldige intune-licentie toe aan de gebruiker en schrijf het apparaat in.


### <a name="looks-like-the-mdm-terms-of-use-endpoint-is-not-correctly-configured"></a>Het eind punt voor MDM-gebruiks voorwaarden is niet juist geconfigureerd.

**Oorzaak:** Een van de volgende voor waarden is waar: 
 - U gebruikt voor het beheer van mobiele apparaten (MDM) voor Office 365 en intune op de Tenant, en de gebruiker die het apparaat probeert te registreren, heeft geen geldige intune-licentie of een Office 365-licentie.     
- De MDM-voor waarden in azure AD zijn leeg of bevatten niet de juiste URL.    

#### <a name="resolution"></a>Oplossing

Gebruik een van de volgende methoden om dit probleem op te lossen: 
 
##### <a name="assign-a-valid-license-to-the-user"></a>Een geldige licentie toewijzen aan de gebruiker
Ga naar het [Microsoft 365-beheer centrum](https://portal.office.com/adminportal/home)en wijs een intune-of een Office 365-licentie toe aan de gebruiker.

##### <a name="correct-the-mdm-terms-of-use-url"></a>De URL voor MDM-gebruiks voorwaarden corrigeren
  1. Meld u aan bij de [Azure-portal](https://portal.azure.com/) en selecteer vervolgens **Azure Active Directory**.    
  2. Selecteer **mobiliteit (MDM en mam)** en klik vervolgens op **Microsoft intune**.    
  3. Selecteer **standaard MDM-Url's herstellen**, Controleer of de **URL voor MDM-gebruiks voorwaarden** is ingesteld op **https://portal.manage.microsoft.com/TermsofUse.aspx** .    
  4. Kies **Opslaan**.    


### <a name="something-went-wrong"></a>Er is iets misgegaan.

Fout 80180026: Er is iets misgegaan. Bevestig dat u de juiste aanmeldings gegevens gebruikt en dat uw organisatie deze functie gebruikt. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode 80180026 "

**Oorzaak:** Deze fout kan optreden wanneer u probeert een Windows 10-computer toe te voegen aan Azure AD en aan beide van de volgende voor waarden wordt voldaan: 
- Automatische MDM-inschrijving is ingeschakeld in Azure.    
- De intune-PC-client (intune-PC-agent) of de Configuration Manager-client agent wordt geïnstalleerd op de Windows 10-computer.

#### <a name="resolution"></a>Oplossing
Gebruik een van de volgende methoden om dit probleem op te lossen:

##### <a name="disable-mdm-automatic-enrollment-in-azure"></a>Schakel automatische inschrijving voor MDM in azure uit.
1. Meld u aan bij [Azure Portal](https://portal.azure.com/).    
2. Ga naar **Azure Active Directory**  > **mobiliteit (MDM en MAM)**  > **Microsoft intune**.    
3. Stel het **MDM-gebruikers bereik** in op **geen**, en klik vervolgens op **Opslaan**.    
     
##### <a name="uninstall"></a>Verwijderen
Verwijder de intune-PC-client of Configuration Manager client agent van de computer.    

### <a name="the-software-cannot-be-installed"></a>De software kan niet worden geïnstalleerd.

Fout: de software kan niet worden geïnstalleerd, 0x80cf4017.

**Oorzaak:** De client software is verouderd.

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Ga naar **Admin**  > **client software downloaden**en klik vervolgens op **client software downloaden**.    
3. Sla het installatie pakket op en installeer vervolgens de client software. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>Het accountcertificaat is niet geldig en is mogelijk verlopen.

Fout: "Het accountcertificaat is niet geldig en is mogelijk verlopen, 0x80cf4017."

**Oorzaak:** De client software is verouderd.

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com).    
2. Ga naar **Admin**  > **client software downloaden**en klik vervolgens op **client software downloaden**.    
3. Sla het installatie pakket op en installeer vervolgens de client software.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Deze versie van Windows wordt niet ondersteund in uw organisatie. 

Fout: ' er is een probleem opgetreden. Deze versie van Windows wordt niet ondersteund in uw organisatie.  (0x80180014) "

**Oorzaak:** Windows MDM-inschrijving is uitgeschakeld in uw intune-Tenant.

#### <a name="resolution"></a>Oplossing
Voer de volgende stappen uit om dit probleem in een zelfstandige intune-omgeving op te lossen: 
 
1. Meld u aan bij de [Azure Portal](https://portal.azure.com/) als beheerder.    
2. Selecteer **intune** aan de linkerkant en ga vervolgens naar **inschrijvings** **beperkingen**voor apparaten  > .    
3. Klik **in beperkingen**voor het apparaattype op **platforms**en selecteer vervolgens **toestaan** voor **Windows (MDM)** .    
4. Klik op **Opslaan**.    
 
Voer de volgende stappen uit om dit probleem op te lossen in hybride MDM met intune en Configuration Manager: 
1. Open de Configuration Manager-console.    
2. Selecteer **beheer**en selecteer vervolgens **Cloud Services**.    
3. Klik met de rechter muisknop op **Microsoft intune abonnement**en selecteer vervolgens **platforms configureren > Windows**.    
4. Schakel het selectie vakje **Windows-inschrijving inschakelen**  >   > **OK** **toe** .  


### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Er is een fout opgetreden tijdens de bulk registratie.

**Oorzaak:** De Azure AD-gebruikers accounts in het account pakket (Package_GUID) voor het betreffende inrichtings pakket mogen geen apparaten toevoegen aan Azure AD. Deze Azure AD-accounts worden automatisch gemaakt wanneer u een inrichtings pakket instelt met behulp van Windows Configuration Designer (WCD) of de app school Pc's instellen. deze accounts worden vervolgens gebruikt om de apparaten samen te voegen met Azure AD.

#### <a name="resolution"></a>Oplossing
1. Meld u aan bij de [Azure Portal](https://portal.azure.com/) als beheerder.    
2. Ga naar **Azure Active Directory > apparaten > Apparaatinstellingen**.    
3. Stel **Gebruikers mogen apparaten aan Azure AD toevoegen** in op **Alle** of **Geselecteerd**.

   Als u **geselecteerd**selecteert, klikt u op **geselecteerd**en klikt u vervolgens op **leden toevoegen** om alle gebruikers toe te voegen die hun apparaten kunnen toevoegen aan Azure AD. Zorg ervoor dat alle Azure AD-accounts voor het inrichtings pakket zijn toegevoegd.
 
Zie [een inrichtings pakket maken voor Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package)voor meer informatie over het maken van een inrichtings pakket voor Windows Configuration Designer.

Zie voor meer informatie over de app school Pc's instellen [de app school-Pc's instellen gebruiken](https://docs.microsoft.com/education/windows/use-set-up-school-pcs-app).


### <a name="auto-mdm-enroll-failed"></a>Automatische MDM-inschrijving: mislukt 

Wanneer u een Windows 10-apparaat automatisch probeert te registreren met behulp van groepsbeleid, treden de volgende problemen op: 
- In Task Scheduler, onder **micro soft**  > **Windows**  > **EnterpriseMgmt**, is het resultaat van de laatste uitvoering van het schema dat is **gemaakt door de registratie-client voor automatische inschrijving in MDM van Aad** taak als volgt: **gebeurtenis 76 Automatische MDM-inschrijving: mislukt (onbekende Win32-fout code: 0x8018002b)**       
- In Logboeken wordt de volgende gebeurtenis geregistreerd onder **Logboeken toepassingen en services/micro soft/Windows/DeviceManagement-Enter prise-Diagnostics-provider/admin**:   
    ```asciidoc
    Log Name: Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
    Source: DeviceManagement-Enterprise-Diagnostics-Provider
    Event ID: 76
    Level: Error
    Description: Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x80180002b)
    ```
**Oorzaak:** Een van de volgende voor waarden is waar: 
- De UPN bevat een niet-geverifieerd of niet-routeerbaar domein, zoals. local (bijvoorbeeld joe@contoso.local).    
- Het **MDM-gebruikers bereik** is ingesteld op **geen**. 

#### <a name="resolution"></a>Oplossing
Als de UPN een niet-geverifieerd of niet-routeerbaar domein bevat, voert u de volgende stappen uit: 

1. Open op de server waarop Active Directory Domain Services (AD DS) wordt uitgevoerd, **Active Directory gebruikers en computers** door **dsa. msc** in het dialoog venster **uitvoeren** te typen en klik vervolgens op **OK**.    
2. Klik op **gebruikers** onder uw domein en Ga als volgt te werk:  
    - Als er slechts één betrokken gebruiker is, klikt u met de rechter muisknop op de gebruiker en klikt u vervolgens op **Eigenschappen**. Selecteer op het tabblad **account** in de vervolg keuzelijst UPN-achtervoegsel onder **aanmeldings naam van gebruiker**een geldig UPN-achtervoegsel, bijvoorbeeld contoso.com, en klik vervolgens op **OK**.    
    - Als er meerdere betrokken gebruikers zijn, selecteert u de gebruikers in het menu **actie** op **Eigenschappen**. Schakel op het tabblad **account** het selectie vakje **UPN-achtervoegsel** in, selecteer een geldig UPN-achtervoegsel, zoals contoso.com in de vervolg keuzelijst, en klik vervolgens op **OK**.
3. Wacht op de volgende synchronisatie of dwing een Delta synchronisatie af van de synchronisatie server door de volgende opdrachten uit te voeren in een Power shell-prompt met verhoogde bevoegdheid:
    ```powershell
    Import-Module ADSync
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

Als het **MDM-gebruikers bereik** is ingesteld op **geen**, voert u de volgende stappen uit: 
 
1. Meld u aan bij de [Azure-portal](https://portal.azure.com/) en selecteer vervolgens **Azure Active Directory**.
2. Selecteer **mobiliteit (MDM en mam)** en selecteer vervolgens **Microsoft intune**.    
3. Stel het **MDM-gebruikers bereik** in op **alle**. Of stel het **MDM-gebruikers bereik** in op **sommige**en selecteer de groepen die automatisch hun Windows 10-apparaten kunnen inschrijven.    
4. Stel **mam-gebruikers bereik** in op **geen**.


### <a name="an-error-occurred-while-creating-autopilot-profile"></a>Er is een fout opgetreden tijdens het maken van het auto pilot-profiel.

**Oorzaak:** De opgegeven naamgevings indeling voor de naam van de sjabloon voldoet niet aan de vereisten. U kunt bijvoorbeeld kleine letters gebruiken voor de seriële macro, zoals% serial% in plaats van% SERIAL%.

#### <a name="resolution"></a>Oplossing

Zorg ervoor dat de naamgevings indeling voldoet aan de volgende vereisten:

- Maak een unieke naam voor uw apparaten. Namen moeten 15 tekens of minder bevatten, en mogen letters (a-z, A-Z), cijfers (0-9) en afbreekstreepjes (-) bevatten.
- Namen mogen niet alleen uit getallen bestaan.
- Namen mogen geen spaties bevatten.
- Gebruik de %SERIAL%-macro om het serienummer toe te voegen van specifieke hardware. Of gebruik de teken reeks% ASELECT: < aantal cijfers >% macro om een wille keurige teken reeks toe te voegen, maar met een waarde van < cijfers > cijfers. Bijvoorbeeld, MYPC-% ASELECT: 6% genereert een naam zoals MYPC-123456.

### <a name="something-went-wrong-oobeidps"></a>Er is iets misgegaan. OOBEIDPS.

**Oorzaak:** Dit probleem doet zich voor als er een proxy, een firewall of een ander netwerk apparaat is dat de toegang tot de ID-provider (IdP) blokkeert.

#### <a name="resolution"></a>Oplossing
Zorg ervoor dat de vereiste toegang tot op internet gebaseerde services voor automatische pilot niet wordt geblokkeerd. Zie [Windows auto pilot Network requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements-network)(Engelstalig) voor meer informatie.


### <a name="registering-your-device-for-mobile-management-failed3-0x801c03ea"></a>Uw apparaat registreren voor mobiel beheer (mislukt: 3, 0x801C03EA).

**Oorzaak:** Het apparaat heeft een TPM-chip die versie 2,0 ondersteunt, maar nog niet is bijgewerkt naar versie 2,0.

#### <a name="resolution"></a>Oplossing
Voer een upgrade uit van de TPM-chip naar versie 2,0.

Als het probleem zich blijft voordoen, controleert u of hetzelfde apparaat zich in twee toegewezen groepen bevindt, waarbij elke groep een ander auto pilot-profiel krijgt toegewezen. Als het zich in twee groepen bevindt, bepaalt u welk auto pilot-profiel moet worden toegepast op het apparaat en verwijdert u vervolgens de toewijzing van het andere profiel.

Zie [Deploying a kiosk using Windows auto pilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/)(Engelstalig) voor meer informatie over het implementeren van een Windows-apparaat in kiosk modus met auto pilot.


### <a name="securing-your-hardware-failed-0x800705b4"></a>Uw hardware beveiligen (mislukt: 0x800705b4).

Fout 800705b4: 
```
Securing your hardware (Failed: 0x800705b4)
Joining your organization's network (Previous step failed)
Registering your device for mobile management (Previous step failed)
```

**Oorzaak:** Het beoogde Windows-apparaat voldoet niet aan een van de volgende vereisten:

- Het apparaat moet een fysieke TPM 2,0-chip hebben. Apparaten met virtuele-Tpm's (bijvoorbeeld Hyper-V-Vm's) of TPM 1,2-chips werken niet met de modus zelf implementeren.
- Op het apparaat moet een van de volgende versies van Windows worden uitgevoerd:
    - Windows 10 build 1703 of een latere versie.
    - Als hybride Azure AD-deelname wordt gebruikt, bouwt u 1809 of een latere versie van Windows 10.


#### <a name="resolution"></a>Oplossing
Zorg ervoor dat het doel apparaat voldoet aan beide vereisten die worden beschreven in de sectie **oorzaak** .

Zie [Deploying a kiosk using Windows auto pilot](https://blogs.technet.microsoft.com/mniehaus/2018/06/07/deploying-a-kiosk-using-windows-autopilot/)(Engelstalig) voor meer informatie over het implementeren van een Windows-apparaat in kiosk modus met auto pilot.


### <a name="something-went-wrong-error-code-80070774"></a>Er is iets misgegaan. Foutcode 80070774.

Fout 0x80070774: er is iets verkeerd gegaan. Bevestig dat u de juiste aanmeldings gegevens gebruikt en dat uw organisatie deze functie gebruikt. U kunt dit opnieuw proberen of contact opnemen met de systeembeheerder met de foutcode 80070774.

Dit probleem treedt doorgaans op voordat het apparaat opnieuw wordt opgestart in een hybride Azure AD Auto Pilot-scenario, wanneer het apparaat een time-out heeft tijdens het eerste aanmeldings scherm. Dit betekent dat de domein controller niet kan worden gevonden of niet kan worden bereikt vanwege verbindings problemen. Of het apparaat heeft een status opgegeven die niet kan worden toegevoegd aan het domein.

**Oorzaak:** De meest voorkomende oorzaak is dat hybride Azure AD-deelname wordt gebruikt en dat de functie gebruikers toewijzen is geconfigureerd in het auto pilot-profiel. Met de functie gebruiker toewijzen wordt een Azure AD-koppeling op het apparaat uitgevoerd tijdens het eerste aanmeldings scherm waarmee het apparaat in een staat wordt geplaatst waar het niet kan worden toegevoegd aan uw on-premises domein. Daarom mag de functie gebruikers toewijzen alleen worden gebruikt in de standaard Azure AD-deelname voor auto pilot.  De functie mag niet worden gebruikt in hybride Azure AD-samenvoegings scenario's.

#### <a name="resolution"></a>Oplossing

1. Ga naar**de registratie van** **intune** - >   apparaten  >  Windows-**inschrijving**  > **apparaten**.
2. Selecteer het apparaat waarop het probleem zich voordoet > Klik op het weglatings teken (...) aan de rechter kant.
3. Selecteer **gebruiker niet toewijzen** en wacht totdat het proces is voltooid.
4. Controleer of het hybride Azure AD Auto Pilot-profiel is toegewezen voordat u OOBE opnieuw probeert uit te voeren.

#### <a name="second-resolution"></a>Tweede omzetting
Als het probleem zich blijft voordoen, controleert u op de server die als host fungeert voor het offline domein de intune-connector, of gebeurtenis-ID 30312 is geregistreerd in het ODJ-connector service-logboek. Gebeurtenis 30312 lijkt op het volgende:

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

Dit probleem wordt meestal veroorzaakt door onjuiste delegering van machtigingen voor de organisatie-eenheid waar de Windows auto pilot-apparaten worden gemaakt. Zie [de limiet voor het computer account in de organisatie-eenheid verg Roten](windows-autopilot-hybrid.md#increase-the-computer-account-limit-in-the-organizational-unit)voor meer informatie.

1. Open **Active Directory: gebruikers en computers (DSA.msc)** .
2. Klik met de rechtermuisknop op de organisatie-eenheid die u gaat gebruiken om aan Hybrid Azure AD gekoppelde computers te maken > **Beheer delegeren**.
3. Kies in de wizard **Overdracht van beheer** **Volgende** > **Toevoegen** > **Objecttypen**.
4. Selecteer in het deelvenster **Objecttypen** het selectievakje **Computers** > **OK**.
5. Voer in het deelvenster voor het selecteren van **Gebruikers**, **Computers** of **Groepen** in het vak **Te selecteren objectnamen invoeren** de naam in van de computer waarop de connector is geïnstalleerd.
6. Selecteer **Namen controleren** om uw invoer te valideren > **OK**  > **volgende**.
7. Selecteer **Een aangepaste taak maken om te delegeren** > **Volgende**.
8. Selecteer het selectievakje **Alleen de volgende objecten in de map** en schakel vervolgens de selectievakjes **Computerobjecten**, **Geselecteerde objecten in deze map maken** en **Geselecteerde objecten in deze map verwijderen** in.
9. Selecteer **Volgende**.
10. Onder **Machtigingen** schakelt u het selectievakje **Volledige bevoegdheid** in. Met deze actie selecteert u alle andere opties.
11. Selecteer **volgende**  > **volt ooien**.

## <a name="next-steps"></a>Volgende stappen

- [Problemen bij de apparaatinschrijving oplossen](../troubleshoot-device-enrollment-in-intune.md)
- [Stel een vraag op het Intune-forum](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Raadpleeg de blog van het Microsoft Intune-ondersteunings team](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Bekijk de micro soft Enter prise Mobility and Security-Blog](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Ondersteuning voor Microsoft Intune krijgen](../fundamentals/get-support.md)
