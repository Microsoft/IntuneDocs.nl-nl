---
title: Problemen met de integratie van Jamf Pro oplossen met Microsoft Intune
titleSuffix: Microsoft Intune
description: Suggesties voor het oplossen van problemen met een aantal van de meest voorkomende problemen wanneer u Jamf Pro voor Mac-apparaten integreert, met Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 44733eb369e520d2d5f0ff548d4f1921abcb8758
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72503580"
---
# <a name="troubleshoot-integration-of-jamf-pro-with-microsoft-intune"></a>Problemen met de integratie van Jamf Pro oplossen met Microsoft Intune

Dit artikel helpt intune-beheerders bij het begrijpen en oplossen van problemen met de integratie van Jamf Pro voor macOS met intune.

> [!TIP]  
> Veel van de informatie in dit artikel leek oorspronkelijk op bij [het oplossen van problemen bij het integreren van Jamf met Microsoft intune](https://support.microsoft.com/help/4519171/troubleshoot-problems-when-integrating-jamf-with-microsoft-intune) op support.Microsoft.com.

## <a name="prerequisites"></a>Vereisten

Voordat u begint met het oplossen van problemen, verzamelt u enkele basis informatie om het probleem te verduidelijken en de tijd te verkorten om een oplossing te vinden. Als er bijvoorbeeld sprake is van een probleem met de integratie van Jamf-intune, moet u altijd controleren of aan de vereisten wordt voldaan. Bekijk de volgende overwegingen voordat u begint met het oplossen van problemen:

- Bekijk de vereisten [voor het integreren van Jamf Pro met intune](conditional-access-integrate-jamf.md#prerequisites).
- Alle gebruikers moeten beschikken over Microsoft Intune en micro soft AAD Premium P1-licenties 
- U moet een gebruikers account hebben met Microsoft Intune-integratie machtigingen in de Jamf Pro-console.
- U moet een gebruikers account hebben met globale beheerders machtigingen in Azure.


Houd rekening met de volgende informatie bij het onderzoeken van Jamf Pro-integratie met intune: 
- Wat is het exacte foutbericht?
- Waar bevindt zich het fout bericht?
- Wanneer is het probleem begonnen?  Heeft Jamf Pro-integratie met intune ooit gewerkt?
- Hoeveel gebruikers treft het probleem? Zijn alle gebruikers betrokken of slechts een deel ervan?
- Hoeveel apparaten heeft het probleem? Zijn alle apparaten betrokken of slechts een deel ervan?
 

## <a name="common-problems"></a>Algemene problemen 

De volgende informatie kan u helpen bij het identificeren en oplossen van veelvoorkomende problemen met apparaten nadat u de integratie van intune en Jamf Pro hebt ingesteld.  

| Probleem   | Meer informatie                  |
|-----------------|--------------------------|
| **Apparaten zijn gemarkeerd als niet-reagerend in Jamf Pro**  | [Apparaten kunnen niet worden ingecheckt met Jamf Pro of met Azure AD](#devices-are-marked-as-unresponsive-in-jamf-pro) |
| **Mac-apparaten vragen naar de sleutel hanger aanmelden wanneer u een app-apparaat opent, worden niet geregistreerd**  | [Gebruikers wordt gevraagd om hun wacht woord zodat apps zich kunnen registreren bij Azure AD](#mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app). |
| **Apparaten kunnen niet worden geregistreerd**  | De volgende oorzaken kunnen van toepassing zijn: <br> **-** [ ***Oorzaak 1*** : de Jamf Pro-app in azure heeft onjuiste machtigingen](#cause-1) <br> **-** [ ***oorzaak 2*** : er is een probleem met de *Jamf-systeem eigen macOS-connector* in azure AD](#cause-2) <br> **-** [ ***oorzaak 3*** : de gebruiker heeft geen geldige intune-of Jamf-licentie](#cause-3) <br> **-** [ ***oorzaak 4*** : de gebruiker heeft Jamf self service niet gebruikt om de bedrijfsportal-app te starten](#cause-4) <br> **-** [ ***oorzaak 5*** -integratie met intune is uitgeschakeld](#cause-5) <br> **-** [ ***oorzaak 6*** : het apparaat is eerder geregistreerd bij intune of de gebruiker heeft geprobeerd het apparaat meerdere keren te registreren](#cause-6) <br> **-** [ ***oorzaak dat 7*** -JamfAAD toegang tot een micro soft Workplace join-sleutel vraagt vanuit de sleutel keten van de gebruiker](#cause-7) |
|  **Mac-apparaat geeft aan dat het compatibel is in intune, maar niet-compatibel in azure** | [Problemen met apparaatregistratie](#mac-device-shows-compliant-in-intune-but-noncompliant-in-azure) |
| **Dubbele vermeldingen worden weer gegeven in de intune-console voor Mac-apparaten die zijn geregistreerd met Jamf** | [Meerdere registraties van hetzelfde apparaat](#duplicate-entries-appear-in-the-intune-console-for-mac-devices-enrolled-by-using-jamf) |
| **Het apparaat kan niet worden geëvalueerd met het nalevings beleid** | [Beleid is bedoeld voor apparaatgroepen](#compliance-policy-fails-to-evaluate-the-device) |
| **Kan het toegangs token voor de Microsoft Graph-API niet ophalen** | De volgende oorzaken kunnen van toepassing zijn: <br> -[machtigingen voor de Pro-app Jamf in azure](#theres-a-permission-issue-with-the-jamf-pro-application-in-azure) <br> - [verlopen licentie voor Jamf of intune](#a-license-required-for-jamf-intune-integration-has-expired) <br> **-** [poorten niet zijn geopend](#the-required-ports-arent-open-on-your-network)|
 

### <a name="devices-are-marked-as-unresponsive-in-jamf-pro"></a>Apparaten zijn gemarkeerd als niet-reagerend in Jamf Pro  

**Oorzaak**: Hieronder volgen enkele veelvoorkomende oorzaken van de apparaten die door Jamf Pro worden gemarkeerd als niet- *reageren* :

- Het apparaat kan niet worden ingecheckt met Jamf Pro.  
  Jamf Pro verwacht dat apparaten elke 15 minuten worden ingecheckt. Apparaten worden als niet-reagerend gemarkeerd door Jamf wanneer ze gedurende een periode van 24 uur niet worden ingecheckt.  

- Het apparaat kan niet worden ingecheckt bij Azure AD.  
  Met een geslaagde registratie bij Azure AD ontvangen macOS-apparaten een Azure-token:
  - Dit token vernieuwt elke 12 uur.   
  - Wanneer het vernieuwen van het token 24 uur of langer mislukt, markeert Jamf Pro het apparaat niet meer.  
  - Als het Azure-token verloopt, wordt gebruikers gevraagd zich aan te melden bij Azure om een nieuw token te verkrijgen. Een vernieuwings token voor Azure Access wordt elke zeven dagen gegenereerd.

**Oplossing**  
Nadat een apparaat als niet- *reagerend* is gemarkeerd door Jamf Pro, moet de Inge schreven gebruiker van het apparaat zich aanmelden om de niet-reagerende status te corrigeren. Het moet de gebruiker zijn die een werk plaats heeft toegevoegd aan het account, omdat de identiteit van intune in hun aanmeldings sleutel is ingesteld.



### <a name="mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app"></a>Mac-apparaten vragen om de sleutel hanger bij het openen van een app  

Nadat u intune en Jamf Pro-integratie hebt geconfigureerd en beleid voor voorwaardelijke toegang implementeert, krijgen gebruikers van apparaten die met Jamf Pro worden beheerd, een wacht woord wanneer ze Microsoft Office 365-toepassingen openen, zoals teams, Outlook en andere apps waarvoor Azure is vereist AD-verificatie. 

Er wordt bijvoorbeeld een prompt met tekst die lijkt op het volgende voor beeld wordt weer gegeven bij het openen van micro soft-teams:

``` 
  Microsoft Teams wants to sign using key “Microsoft Workplace Join Key” in your keychain.  
  To allow this, enter the “login” keychain password 
```

**Oorzaak**: deze prompts worden gegenereerd door Jamf Pro voor elke app waarvoor Azure AD-registratie vereist is. 

**Oplossing**   
Bij de prompt moet de gebruiker het wacht woord van het apparaat opgeven om zich aan te melden bij Azure AD. Opties zijn onder andere:
- **Deny** -niet aanmelden en de app niet gebruiken.
- Een eenmalige aanmelding **toestaan** . De volgende keer dat de app wordt geopend, wordt u gevraagd om u opnieuw aan te melden.
- **Altijd toestaan** : de aanmeldings referenties worden in de cache opgeslagen voor de toepassing. De volgende keer dat de app wordt geopend, wordt niet gevraagd om zich aan te melden.  

Als u de optie *altijd toestaan* voor één app selecteert, wordt die app alleen goedgekeurd voor toekomstige aanmeldingen. Extra apps vragen om verificatie totdat ze ook zijn ingesteld op *altijd toestaan*. Referenties in de cache voor één app kunnen niet worden gebruikt door een andere app.  

### <a name="devices-fail-to-register"></a>Apparaten kunnen niet worden geregistreerd  

Er zijn verschillende veelvoorkomende oorzaken voor Mac-apparaten die niet kunnen worden geregistreerd.  

#### <a name="cause-1"></a>Oorzaak 1  

**De Jamf Pro Enter prise-toepassing in azure heeft de verkeerde machtiging of heeft meer dan één machtiging**  

  Wanneer u de app in azure maakt, moet u alle standaard API-machtigingen verwijderen en vervolgens in intune een enkele machtiging van *update_device_attributes*toewijzen. 

  **Oplossing**  
  Controleer en indien nodig de machtigingen voor de Jamf-app die u hebt gemaakt in azure AD. Zie de procedure voor het [maken van een toepassing voor Jamf in azure AD](conditional-access-integrate-jamf.md#create-an-application-in-azure-active-directory). 

#### <a name="cause-2"></a>Oorzaak 2  

**De **Jamf native MacOS connector** -app is niet gemaakt in uw Azure AD-Tenant of de toestemming voor de connector is ondertekend door een account zonder globale beheerders rechten**  

  **Oplossing**  
  Zie de sectie *macOS intune-integratie configureren* in [integreren met Microsoft intune](https://docs.jamf.com/10.13.0/jamf-pro/administrator-guide/Integrating_with_Microsoft_Intune.html) op docs.jamf.com. 

#### <a name="cause-3"></a>Oorzaak 3

**De gebruiker heeft geen geldige intune-of Jamf-licentie**  

  Het ontbreken van een geldige licentie kan leiden tot de volgende fout, wat aangeeft dat de Jamf-licentie is verlopen:  
  ```
    Unable to connect to Microsoft Intune.  
    
    Check your Microsoft Intune Integration configuration.
  ```  

  **Oplossing**
  - Jamf-licentie: Neem contact op met Jamf voor hulp bij het verkrijgen van een nieuwe licentie voor Jamf.  
  - InTune-licentie: wijs aan de gebruiker een geldige licentie toe of neem contact op met micro soft of uw partner voor informatie over het verkrijgen van een huidige licentie.

#### <a name="cause-4"></a>Oorzaak 4  

**De gebruiker heeft *Jamf self service* niet gebruikt om de bedrijfsportal-app te starten**

Een apparaat kan alleen worden geregistreerd bij intune via Jamf als de gebruiker Jamf self service gebruikt om de Intune-bedrijfsportal te openen. Als de gebruiker de bedrijfs portal hand matig opent, wordt het apparaat geregistreerd zonder de verbinding met Jamf.  

Als u wilt bepalen welke service wordt gebruikt om het apparaat in te schrijven en te registreren, kijkt u in de Bedrijfsportal-app op het apparaat. Wanneer u bent geregistreerd via Jamf, ontvangt u een melding om de self-service app te openen en wijzigingen aan te brengen.

De gebruiker kan in de Bedrijfsportal-app **`Not registered`** zien en een item dat lijkt op het volgende voor beeld, kan worden weer gegeven in de bedrijfsportal logboeken:  

```
   Line 7783: <DATE> <IP ADDRESS> INFO com.microsoft.ssp.application TID=1  
 
   WelcomeViewController.swift: 253 (startLogin()) Portal launched without WPJ only arg while account is under partner management
```

**Oplossing**  
De registratie bron wijzigen van intune in Jamf:
1. [De registratie van het macOS-apparaat bij Intune ongedaan maken](https://docs.microsoft.com/intune-user-help/unenroll-your-device-from-intune-macos). Als u verdere complicaties wilt voor komen voor apparaten die niet volledig worden verwijderd uit intune, raadpleegt u [*oorzaak 6*](#cause-6) in deze lijst met oorzaken.  

2. Op het apparaat gebruikt u Jamf self service om de Bedrijfsportal-app te openen en vervolgens het apparaat bij intune in te schrijven. Voor deze taak moet u [Jamf gebruiken om de bedrijfsportal-app voor macOS te implementeren](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro)en [een beleid te hebben gemaakt in Jamf Pro waarmee het apparaat van de gebruiker wordt geregistreerd bij Azure AD](conditional-access-assign-jamf.md#create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory).  

3. Wanneer de portal wordt geopend, verschijnt het eerste scherm waarin u wordt gevraagd u aan te melden. Uw werk- of schoolaccount gebruiken  

4. De bedrijfsportal bevestigt uw accountgegevens en geeft de status van de apparaatregistratie en apparaatcompatibiliteit weer. Gele driehoeken markeren de acties die u moet uitvoeren om uw macOS-apparaat te beveiligen voor school of werk. Klik op Beginnen om de registratie te starten.  

5. Typ de aanmeldgegevens van uw computer in wanneer u daarom wordt gevraagd.  
     
Het duurt mogelijk enkele minuten om uw apparaat in beheer te registreren. Gedurende deze tijd kunt u andere dingen doen op uw apparaat. U krijgt een bericht zodra het instellen van de bedrijfstoegang is voltooid, zodat u weet dat u klaar bent.

#### <a name="cause-5"></a>Oorzaak 5  

**Integratie van intune is uitgeschakeld**

Als intune-integratie is uitgeschakeld, ontvangen gebruikers een pop-upvenster in de Bedrijfsportal met het volgende bericht wanneer ze een apparaat proberen te registreren:  

```
   Invalid command line input
   
   Registration-only command line flag (-r) can only be used when partner management is enabled in Intune. Please contact your IT admin.
```  

De Jamf Pro-Server verzendt een puls naar de intune-servers wanneer integratie is uitgeschakeld, waarmee wordt aangegeven dat de integratie van intune is uitgeschakeld. 

**Oplossing**  
Schakel intune-integratie in Jamf Pro opnieuw in. Zie [Microsoft Intune-integratie in Jamf Pro configureren](conditional-access-integrate-jamf.md#enable-intune-to-integrate-with-jamf-pro).


#### <a name="cause-6"></a>Oorzaak 6  

**Het apparaat is eerder geregistreerd bij intune of de gebruiker heeft geprobeerd het apparaat meerdere keren te registreren**

Als een apparaat niet is inge schreven bij Jamf, maar niet correct is verwijderd uit intune, of als er verschillende registratie pogingen zijn gedaan, kunnen er meerdere exemplaren van hetzelfde apparaat in de portal worden weer gegeven. Dit leidt ertoe dat de Jamf-inschrijving mislukt.

**Oplossing**  
1. Start op de Mac **Terminal**.
2. Voer **sudo JAMF removemdmprofile**uit.
3. Voer **sudo JAMF removeFramework**uit.
4. Verwijder op de JAMF Pro-Server de inventaris record van de computer.
5. Verwijder het apparaat uit AzureAD.
6. Verwijder de volgende bestanden op het apparaat als deze bestaan:
   - /Library/Application Support/com. micro soft. CompanyPortal. User context. info
   - /Library/Application-ondersteuning/com. micro soft. CompanyPortal
   - /Library/Application Support/com. jamfsoftware. selfservice. Mac
   - /Library/Saved-toepassing
   - Status/com. jamfsoftware. selfservice. Mac. savedState
   - /Library/Saved-toepassings status/com. micro soft. CompanyPortal. savedState
   - /Library/Preferences/com.microsoft.CompanyPortal.plist
   - /Library/Preferences/com.jamfsoftware.selfservice.mac.plist
   - /Library/Preferences/com.jamfsoftware.management.jamfAAD.plist
   - /Gebruikers/<username>/Library/Cookies/com.microsoft.CompanyPortal.binarycookies
   - /Gebruikers/<username>/Library/Cookies/com.jamf.management.jamfAAD.binarycookies
   - com. micro soft. CompanyPortal
   - com. micro soft. CompanyPortal. HockeySDK
   - enterpriseregistration.windows.net
   - https://device.login.microsoftonline.com
   - https://device.login.microsoftonline.com/
   - Micro soft-sessie transport sleutel (open bare en persoonlijke sleutels)
   - Micro soft Workplace Join-sleutel (open bare en persoonlijke sleutels)
7. Verwijder niets van de sleutel hanger op het apparaat dat verwijst naar *micro soft*, *intune*of *bedrijfsportal*, inclusief DeviceLogin.Microsoft.com-certificaten. Verwijder *JAMF* -verwijzingen, behalve voor de open bare en persoonlijke sleutel JAMF. 
   > [!IMPORTANT]  
   > Als u de open bare en persoonlijke sleutel verwijdert, wordt de registratie van het apparaat verbroken.

8. Verwijder een van de volgende vermeldingen die u vindt:  
   - Soort: toepassings wachtwoord; Account: com. micro soft. workplacejoin. vinger afdruk
   - Soort: toepassings wachtwoord; Account: com. micro soft. workplacejoin. registeredUserPrincipalName
   - Soort: certificaat; Uitgegeven door: MS-organisatie-Access
   - Soort: identiteits voorkeur; Naam (ADFS STS-URL indien aanwezig): https://adfs\<DNSName>.com/adfs/ls
   - Soort: identiteits voorkeur; Naam: https://enterpriseregistration.windows.net
   - Soort: identiteits voorkeur; Naam: https://enterpriseregistration.windows.net/  
9. Start het Mac-apparaat opnieuw.
10. Verwijder Bedrijfsportal van het apparaat.
11. Ga naar portal.manage.microsoft.com en verwijder alle exemplaren van het Mac-apparaat. Wacht ten minste 30 minuten voordat u naar de volgende stap gaat.
12. Registreer het apparaat opnieuw in JAMF Pro.
13. Open de self-service opnieuw en start het registratie beleid.


#### <a name="cause-7"></a>Oorzaak 7  

**JamfAAD vraagt toegang tot een ' micro soft Workplace Join-sleutel ' van de sleutel keten van de gebruiker**

Tijdens de registratie ontvangt de gebruiker van een macOS-apparaat de volgende prompt om JamfAAD toegang te geven tot een sleutel van hun sleutel hanger: 

```
   JamfAAD wants to access key “Microsoft Workplace Join Key" in your keychain. 
    
   To allow this, enter the “login” keychain password
```

**Oplossing**  
Om het apparaat te registreren bij Azure AD, vereist Jamf dat de gebruiker het wacht woord van hun account opgeeft en selecteert u **toestaan**.

Deze aanvraag is vergelijkbaar met de aanvraag voor [Mac-apparaten vragen om sleutel hanger aanmelding wanneer u een app opent](#mac-devices-prompt-for-keychain-sign-in-when-you-open-an-app), eerder in dit artikel.  

 
### <a name="mac-device-shows-compliant-in-intune-but-noncompliant-in-azure"></a>Mac-apparaat geeft aan dat het compatibel is in intune, maar niet-compatibel in azure  

**Oorzaak**: de volgende omstandigheden kunnen ertoe leiden dat een apparaat als compatibel wordt weer gegeven in intune, maar niet als compatibel in Azure:  
- Het apparaat is niet juist geregistreerd.  
- Het apparaat is meerdere keren geregistreerd zonder het vereiste opschonen.

**Oplossing**  
U kunt dit probleem oplossen door de oplossing te volgen voor [*oorzaak 6*](#cause-6) voor *apparaten die niet worden geregistreerd*, eerder in dit artikel. 


### <a name="duplicate-entries-appear-in-the-intune-console-for-mac-devices-enrolled-by-using-jamf"></a>Dubbele vermeldingen worden weer gegeven in de intune-console voor Mac-apparaten die zijn geregistreerd met Jamf  
 
**Oorzaak**: een apparaat is meerdere keren geregistreerd bij intune, normaal gesp roken opnieuw geregistreerd na verwijdering uit intune.  

Wanneer een apparaat wordt verwijderd uit de intune-en Jamf Pro-integratie, kunnen er enkele gegevens achterblijven, wat kan leiden tot opeenvolgende registraties voor het maken van dubbele vermeldingen.  

**Oplossing**  
U kunt dit probleem oplossen door de oplossing te volgen voor [*oorzaak 6*](#cause-6) voor *apparaten die niet worden geregistreerd*, eerder in dit artikel. 

### <a name="compliance-policy-fails-to-evaluate-the-device"></a>Het apparaat kan niet worden geëvalueerd met het nalevings beleid  

**Oorzaak**: Jamf-integratie met Intune ondersteunt geen nalevingsbeleid voor apparaatgroepen. 

**Oplossing**  
Wijzig het nalevings beleid voor macOS-apparaten die moeten worden toegewezen aan gebruikers groepen. 


### <a name="could-not-retrieve-the-access-token-for-microsoft-graph-api"></a>Kan het toegangs token voor de Microsoft Graph-API niet ophalen

U ontvangt de volgende fout:

```
   Could not retrieve the access token for Microsoft Graph API. Check the configuration for Microsoft Intune Integration.
```   

De bron van deze fout kan een van de volgende oorzaken hebben: 

#### <a name="theres-a-permission-issue-with-the-jamf-pro-application-in-azure"></a>Er is een machtigings probleem met de Jamf Pro-toepassing in azure

Tijdens het registreren van de Jamf Pro-app in Azure is een van de volgende voor waarden van toepassing:  
- De app heeft meer dan één machtiging ontvangen.
- De **toekennings beheerder toestemming geven voor *\<uw > optie voor uw bedrijf***  is niet geselecteerd.  

**Oplossing**  
Zie de oplossing voor oorzaak 1 voor [apparaten die niet kunnen worden geregistreerd](#devices-fail-to-register), eerder in dit artikel.

#### <a name="a-license-required-for-jamf-intune-integration-has-expired"></a>Een licentie vereist voor Jamf-integratie van intune is verlopen

**Oplossing**: Zie de oplossing voor oorzaak 3 voor [apparaten die niet kunnen worden geregistreerd](#devices-fail-to-register). 

#### <a name="the-required-ports-arent-open-on-your-network"></a>De vereiste poorten zijn niet geopend in uw netwerk

**Oplossing**: Raadpleeg de informatie voor netwerk poorten in [vereisten](conditional-access-integrate-jamf.md#prerequisites) voor het integreren van Jamf Pro met intune.


## <a name="next-steps"></a>Volgende stappen
Meer informatie over het [integreren van Jamf Pro met intune](conditional-access-integrate-jamf.md)