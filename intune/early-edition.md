---
title: Vroege editie
description: 
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 973408b292261b86f0a49bfaf4c786d6a6dacf28
ms.sourcegitcommit: b8d3f8da6d8c2bd5d6140d538193a02d5875aefb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2017
---
# <a name="the-early-edition-for-microsoft-intune---october-2017"></a>De vroege editie voor Microsoft Intune - oktober 2017

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->



## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->   
Met Azure Active Directory (Azure AD) kunt u de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.

### <a name="troubleshoot-enrollment-issues------746324----"></a>Inschrijvingsproblemen oplossen <!--- 746324 --->  
De werkruimte Problemen oplossen toont problemen met gebruikersinschrijving. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen.

### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Beheerders kunnen de firewall-instellingen op een apparaat nu configureren met behulp van een apparaatconfiguratieprofiel <!-- 951708 -->   
Beheerders kunnen de firewall inschakelen voor apparaten, en ook verschillende protocollen voor domein-, privé- en openbare netwerken configureren.  Deze firewall-instellingen staan in het profiel 'Endpoint Protection'.

### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard helpt apparaten te beschermen tegen niet-vertrouwde websites, zoals gedefinieerd door uw organisatie <!-- 958257 -->   
Beheerders kunnen sites als 'vertrouwd' of 'zakelijk' definiëren met behulp van een Windows Information Protection-werkstroom of het nieuwe profiel 'Netwerkgrens' onder apparaatconfiguraties. Sites die niet in een vertrouwde netwerkgrens van een 64-bits Windows 10-apparaat staan, worden in een browser op een virtuele Hyper-V-computer geopend als ze met Microsoft Edge worden bekeken.

Application Guard staat in de apparaatconfiguratieprofielen, in het profiel 'Endpoint Protection'. Beheerders kunnen daar interactie configureren tussen de gevirtualiseerde browser en de hostcomputer, niet-vertrouwde sites en vertrouwde sites, en gegevens opslaan die in de gevirtualiseerde browser worden gegenereerd. Als u Application Guard op een apparaat wilt gebruiken, moet er eerst een netwerkgrens worden geconfigureerd. Het is belangrijk slechts één netwerkgrens te definiëren voor een apparaat.  

### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Guard op Windows 10 Enterprise biedt een modus om alleen geautoriseerde apps te vertrouwen <!-- 1031096 -->    
Aangezien er elke dag duizenden nieuwe schadelijke bestanden worden gemaakt, biedt malwaredetectie op basis van handtekeningen misschien niet meer voldoende bescherming tegen nieuwe aanvallen. Met Windows Defender Application Guard op Windows 10 Enterprise kunt u de apparaatconfiguratie wijzigen van een modus waarin apps worden vertrouwd tenzij ze door een antivirus- of andere beveiligingsoplossing worden geblokkeerd, naar een modus waarin het besturingssysteem alleen apps vertrouwt die door uw onderneming zijn geautoriseerd. In Windows Defender Application Guard definieert u welke apps u vertrouwt.

Met Intune kunt u het toepassingsbeheerbeleid configureren in de modus 'Alleen controle' of in de modus 'Afdwingen'. Apps worden niet geblokkeerd wanneer ze in de modus 'alleen controle' worden uitgevoerd. De modus 'Alleen controle' registreert alle gebeurtenissen in lokale clientlogboeken. U kunt ook configureren of alleen Windows-onderdelen en Windows Store-apps mogen worden uitgevoerd of dat aanvullende apps met goede reputaties zoals gedefinieerd door de Intelligent Security Graph ook mogen worden uitgevoerd.

### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Pagina Status van nieuwe inschrijving voor Windows 10-inschrijvingen <!--1063201-->    
U kunt nu een begroeting configureren die verschijnt wanneer uw gebruikers Windows 10-apparaten inschrijven. Gebruik het **scherm Status van inschrijving** om een aangepast bericht en een hyperlink te configureren die aan uw eindgebruikers worden getoond wanneer ze hun Windows 10-apparaten inschrijven.  Op het **scherm Status van inschrijving** kunnen eindgebruikers ook de voortgang zien van beleidsinstellingen die op hun apparaat worden toegepast.  

### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard is een nieuwe verzameling inbraakpreventiefuncties voor Windows 10 <!-- 1063615 -->   
Window Defender Exploit Guard omvat aangepaste regels om de exploiteerbaarheid van toepassingen te reduceren, voorkomt macro- en scriptbedreigingen, blokkeert automatisch netwerkverbindingen naar IP-adressen met een slechte reputatie, en kan gegevens uit ransomware en onbekende bedreigingen beveiligen. Windows Defender Exploit Guard bestaat uit de volgende onderdelen:

- **Attack Surface Reduction (ASR)** biedt regels waarmee u macro-, script- en e-mailbedreigingen kunt voorkomen.
- **Gecontroleerde maptoegang** blokkeert automatisch de toegang tot inhoud in beveiligde mappen.
- **Netwerkfilter** blokkeert uitgaande verbindingen van een app naar een IP/domein met een slechte reputatie
- **Exploit-beveiliging** biedt geheugen-, controlestroom- en beleidsbeperkingen die kunnen worden gebruikt om een toepassing te beschermen tegen aanvallen.

### <a name="app-conditional-launch-support----1193313---"></a>Ondersteuning voor app-voorwaardelijk starten <!-- 1193313 -->
IT-beheerders kunnen nu via de Azure-beheerportal een vereiste instellen om een wachtwoordcode in plaats van een numerieke pincode af te dwingen via Mobile App Management (MAM) wanneer de toepassing start. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Bij deze release van Intune wordt deze functie **alleen op iOS** ingeschakeld. Intune ondersteunt wachtwoordcodes op dezelfde manier als numerieke pincodes: er is een minimumlengte, en tekens en tekenreeksen mogen worden herhaald. Voor deze functie moeten toepassingen (d.w.z. WXP, Outlook, Managed Browser, Yammer) de Intune App SDK integreren met de code voor deze functie om de wachtwoordcode-instellingen af te dwingen in de doeltoepassingen.

### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>App-versienummer voor line-of-business in rapport Installatiestatus van het apparaat <!-- 1233999 -->  
Het rapport Installatiestatus van het apparaat toont het app-versienummer voor de line-of-business-apps voor iOS en Android. U kunt deze informatie gebruiken om problemen met uw apps op te lossen of om apparaten te vinden waarop verouderde app-versies worden uitgevoerd.

### <a name="co-management-for-windows-10-devices-----124445---"></a>Co-management voor Windows 10-apparaten <!-- 124445 -->
Co-management is een oplossing die een brug slaat tussen traditioneel en modern beheer en het biedt een gefaseerde benadering om de overstap te maken. Co-management is in feite een oplossing waarbij Windows 10-apparaten gelijktijdig worden beheerd door Configuration Manager en Microsoft Intune en zijn gekoppeld aan Active Directory (AD) en Azure Active Directory (Azure AD).  Deze configuratie geeft u een manier om mettertijd te moderniseren, in een tempo dat geschikt is voor uw organisatie als u niet allemaal tegelijk kunt overstappen.  

### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Toegang instellen voor apps via minimale Android-beveiligingspatch op het apparaat<!-- 1278463 -->   
Een beheerder kan de minimale Android-beveiligingspatch definiëren die op het apparaat moet zijn geïnstalleerd om toegang te kunnen krijgen tot een beheerde toepassing onder een beheerd account.

> [!Note]  
> Deze functie beperkt alleen beveiligingspatches die door Google zijn vrijgegeven op Android 6.0+ apparaten.

### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10      <!-- 1308850 -->
-    Berichten (alleen mobiel) - testen of MMS-berichten uitschakelen
-    Wachtwoord - instellingen om FIPS en het gebruik van secundaire Windows Hello-apparaten in te schakelen voor verificatie 
-    Weergave - instellingen om GDI-schaalbaarheid in of uit te schakelen voor verouderde apps


### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Apparaatbeperkingen Windows 10-kioskmodus <!-- 1308872 -->   
U kunt gebruikers van Windows 10-apparaten beperken tot de kioskmodus, zodat ze worden beperkt tot een verzameling vooraf gedefinieerde apps.  Om dit te doen, maakt u een Windows 10-apparaatbeperkingsprofiel en configureert u de kioskinstellingen.

De kioskmodus ondersteunt twee modi: **één app** (waarbij een gebruiker slechts één app mag uitvoeren) en **meerdere apps** (geeft toegang tot een verzameling apps).  U definieert het gebruikersaccount en de apparaatnaam, waarmee de ondersteunde apps worden bepaald.  Wanneer de gebruiker is aangemeld, is hij/zij beperkt tot de gedefinieerde apps.  Zie [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) voor meer informatie. 

De kioskmodus vereist het volgende:

- Intune moet de MDM-instantie zijn.
- De apps moeten al op het doelapparaat zijn geïnstalleerd.
- Het apparaat moet [goed ingericht](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) zijn.

### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nieuw apparaatconfiguratieprofiel voor het maken van netwerkgrenzen <!-- 1311967 -->   
Wij hebben een apparaatconfiguratieprofiel genaamd **Netwerkgrens** gemaakt, dat bij uw andere apparaatconfiguratieprofielen staat. Gebruik dit profiel om onlinebronnen te definiëren die u als zakelijk en vertrouwd wilt beschouwen. U moet een netwerkgrens voor een apparaat definiëren *voordat* functies zoals Windows Defender Application Guard en Windows Information Protection op het apparaat kunnen worden gebruikt. Het is belangrijk slechts één netwerkgrens te definiëren voor elk apparaat.

U kunt bedrijfscloudresources, IP-adresbereiken en interne proxyservers definiëren die u als vertrouwd wilt beschouwen. Nadat u de netwerkgrens hebt gedefinieerd, kan deze worden gebruikt door andere functies zoals Windows Defender Application Guard en Windows Information Protection.

###  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Twee aanvullende instellingen voor Windows Defender Antivirus <!-- 1338409 -->  
**Blokkeringsniveau voor bestanden**

| | |
|---|---|
| Niet geconfigureerd | **Niet geconfigureerd** gebruikt het standaard Windows Defender Antivirus-blokkeringsniveau en biedt sterke detectie zonder het risico te vergroten dat legitieme bestanden worden gedetecteerd. |
| Hoog | **Hoog** past een sterk detectieniveau toe.
| Hoog +  | **Hoog +** biedt het niveau Hoog met aanvullende beveiligingsmaatregelen die de clientprestaties kunnen beïnvloeden.
| Zero tolerance  | **Zero tolerance** blokkeert alle onbekende uitvoerbare bestanden. |

Als u dit op **Hoog** instelt, worden sommige legitieme bestanden misschien gedetecteerd, hoewel dit onwaarschijnlijk is.
Het is raadzaam het Blokkeringsniveau voor bestanden in te stellen op de standaardinstelling **Niet geconfigureerd**.

**Time-outverlenging voor het scannen van bestanden door de cloud**  

| | |
|--|--|
| Aantal seconden (0-50) | Geef op hoelang Windows Defender Antivirus een bestand maximaal moet blokkeren terwijl u op een resultaat van de cloud wacht. De standaardinstelling is 10 seconden: de aanvullende tijd die u hier opgeeft (tot 50 seconden) wordt toegevoegd aan die 10 seconden. In de meeste gevallen duurt de scan veel korter dan de maximuminstelling. Als u de tijd verlengt, kan de cloud verdachte bestanden grondig onderzoeken. Het is raadzaam deze instelling in te schakelen en ten minste 20 aanvullende seconden op te geven. |


### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Ondersteuning voor Symantec Cloud Certification Authority (CA)  <!-- 1333638 -->    
Intune ondersteunt nu Symantec Cloud CA die de Intune Certificate Connector in staat stelt PKCS-certificaten van Symantec Cloud CA vrij te geven voor beheerde Intune-apparaten. Als u de Intune Certificate Connector al gebruikt met Microsoft Certification Authority (CA), kunt u de bestaande configuratie van de Intune Certificate Connector gebruiken om de ondersteuning voor Symantec Cloud CA toe te voegen.



### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix-VPN toegevoegd voor Windows 10-apparaten <!-- 1512457 -->  
Klanten kunnen Citrix-VPN configureren voor hun Windows 10-apparaten. U kunt de Citrix-VPN kiezen in de lijst *Een verbindingstype selecteren* in de blade **Basis-VPN** wanneer u een VPN voor Windows 10 en hoger configureert.

> [!Note]
> Citrix-configuratie bestond voor iOS en Android.





<!-- the following are present prior to 1710 -->

### <a name="google-play-protect-support-on-android----908720----"></a>Ondersteuning van Google Play Protect op Android <!-- 908720  -->  
Google introduceert tegelijkertijd met Android Oreo een reeks beveiligingsfuncties met de naam Google Play Protect waarmee gebruikers en organisaties beveiligde apps en beveiligde Android-installatiekopieën kunnen uitvoeren. Intune zal de functies van Google Play Protect, inclusief SafetyNet voor externe verklaringen, ondersteunen.  Beheerders kunnen eisen voor een nalevingsbeleid instellen die vereisen dat Google Play Protect wordt geconfigureerd en in orde is. De instelling **SafetyNet-apparaatverklaring** vereist dat het apparaat verbinding maakt met een service van Google om te controleren of het apparaat in orde is en er niet mee is geknoeid. Beheerders kunnen tevens een configuratieprofielinstelling voor Android for Work instellen om te vereisen dat geïnstalleerde apps worden geverifieerd met behulp van Google Play-services.  Voorwaardelijke toegang kan de toegang van gebruikers tot bedrijfsbronnen blokkeren als een apparaat niet aan de eisen van Google Play Protect voldoet. 


### <a name="support-for-windows-10-edition-upgrade-policy------903672archived-1119689---"></a>Ondersteuning voor het editie-upgradebeleid voor Windows 10   <!-- 903672(archived), 1119689 -->  
U kunt een editie-upgradebeleid voor Windows 10 maken dat Windows 10-apparaten upgradet naar Windows 10 Education, Windows 10 Education N, Windows 10 Professional, Windows 10 Professional N, Windows 10 Professional Education en Windows 10 Professional Education N. Raadpleeg [Editie-upgrades voor Windows 10 configureren](edition-upgrade-configure-windows-10.md) voor meer informatie over editie-upgrades voor Windows 10.





<!-- the following are present prior to 1709 -->

### <a name="actions-for-non-compliance----730266--846515---"></a>Acties voor niet-naleving  <!--730266  846515 -->     
*Acties voor niet-naleving* zijn een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="android-for-work-support-for-lookout----1087312---"></a>Android for Work-ondersteuning voor Lookout <!-- 1087312 -->   
De Intune-connector met Lookout biedt ondersteuning voor Android for Work-apparaten wanneer u de Lookout voor Work-app gebruikt. U kunt de Lookout-app binnen of buiten de container implementeren.

### <a name="intune-app-protection-and-citrix-mdx-development-tools----709185---"></a>Hulpmiddelen voor Intune-app-beveiliging en Citrix MDX <!-- 709185 -->
U kunt apparaten en apps beheren met een combinatie van Citrix XenMobile MDX en Microsoft Intune. Hierdoor kunt u apps beheren met het Intune-beveiligingsbeleid voor apps met behulp van de mVPN-technologie van Citrix.

U kunt een opslagplaats voor codes vinden met de Intune App Wrapping Tool en Intune App SDK voor iOS en Android, die integreren met Citrix MDX mVPN-technologie.

#### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met door Zimperium. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de Zimperium-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-compatibele apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hoge beschikbaarheid van on-premises Exchange Connector  <!-- 676614 -->   
U kunt meerdere CAS-rollen (Client Access Server) instellen voor on-premises Exchange Connector. Als de hoofd-CA bijvoorbeeld uitvalt, ontvangt Exchange Connector een query om over te schakelen naar een andere CAS. Deze functie zorgt ervoor dat de service niet wordt onderbroken.

### <a name="system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->   
Het management pack van System Center Operations Manager voor Exchange Connector kunt u gebruiken om de logboeken van Exchange Connector te parseren. Met dit management pack kunt u Intune op verschillende manieren controleren wanneer u problemen moet oplossen.


## <a name="intune-apps"></a>Intune-apps


### <a name="redirecting-macos-users-to-our-new-company-portal-app---1380728--"></a>MacOS-gebruikers omleiden naar onze nieuwe bedrijfsportal-app <!--1380728-->   
Wanneer eindgebruikers zich aanmelden bij de bedrijfsportalwebsite om hun macOS-apparaten in te schrijven, worden ze gevraagd de nieuwe bedrijfsportal-app voor macOS te downloaden om het proces te voltooien. Dit gebeurt voor macOS-apparaten waarop OS X El Capitan 10.11 of hoger wordt uitgevoerd. 

### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Ondersteuning voor op certificaten gebaseerde verificatie op de bedrijfsportal voor iOS <!--1029830-->
We hebben ondersteuning voor op certificaten gebaseerde verificatie toegevoegd in de bedrijfsportal-app voor iOS. Gebruikers met deze verificatie voeren hun gebruikersnaam in en tikken vervolgens op de koppeling 'Aanmelden met een certificaat'. Dit wordt al ondersteund in de bedrijfsportal-app voor Android en Windows. Meer informatie staat op de pagina [Aanmelden bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

<!-- the following are present prior to 1710 -->



### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps die met of zonder inschrijving beschikbaar zijn, kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd. <!-- 1334712 -->
Bedrijfs-apps die met of zonder inschrijving beschikbaar zijn gemaakt in de bedrijfsportal-app voor Android kunnen worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd.


<!-- the following are present prior to 1709 -->

### <a name="intune-managed-browser-support-for-ios-and-android----1374196---"></a>Ondersteuning van Intune Managed Browser voor iOS en Android <!-- 1374196 -->
Vanaf oktober 2017 ondersteunt de app Intune Managed Browser voor Android alleen nog apparaten waarop Android 4.4 en hoger wordt uitgevoerd. De app Intune Managed Browser voor iOS ondersteunt alleen apparaten met iOS 9.0 en hoger. Oudere versies van Android en iOS kunnen Managed Browser nog steeds gebruiken, maar er kunnen geen nieuwe versies van de app op worden geïnstalleerd en kan er dus geen gebruik worden gemaakt van alle mogelijkheden van de app. U wordt aangeraden deze apparaten bij te werken tot een ondersteunde versie van het besturingssysteem.


### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbeterd foutbericht als een gebruiker het maximum aantal apparaten bereikt dat mag worden ingeschreven <!-- 1270370 -->
In plaats van een algemeen foutbericht krijgen eindgebruikers een gebruikersvriendelijk foutbericht te zien waarop een actie kan worden uitgevoerd: 'U hebt het maximum aantal apparaten ingeschreven dat door de IT-beheerder is toegestaan. Verwijder een ingeschreven apparaat of vraag assistentie van uw IT-beheerder.'




## <a name="notices"></a>Mededelingen

### <a name="device-and-app-management-integration----677972---"></a>Integratie van apparaat- en appbeheer <!-- 677972 -->   
Nu Mobile Device Management (MDM) en Mobile Application Management (MAM) van Intune beide toegankelijk zijn vanuit de Azure-portal, is Intune begonnen met het integreren van de IT-beheerervaring omtrent app- en apparaatbeheer. Deze wijzigingen zijn bedoeld om uw apparaat- en appbeheer te vereenvoudigen.

Meer informatie over de aangekondigde MDM- en MAM-wijzigingen staat in de [blog van het Intune-ondersteuningsteam](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).




### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
