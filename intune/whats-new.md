---
title: Wat is er nieuw in Microsoft Intune?
titlesuffix: Azure portal
description: Ontdekken wat er nieuw is in Intune Azure Portal
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 11/18/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1f3f9832a643628cf18aee6131b9c8a43843e94d
ms.sourcegitcommit: 71e6e80b7370024624ce2e5fad1ca5b372975748
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Wat is er nieuw in Microsoft Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ontdek elke week wat er nieuw is in Microsoft Intune. U vindt hier ook informatie over [toekomstige wijzigingen](#whats-coming), [belangrijke kennisgevingen](#notices) betreffende de service en informatie over [oudere releases](whats-new-archive.md).

> [!Note]
> Veel van deze functies worden uiteindelijk ondersteund voor hybride implementaties met Configuration Manager. Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot

-->   

## <a name="week-of-november-13-2017"></a>Week van 13 november 2017

### <a name="intune-apps"></a>Intune-apps
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>De bedrijfsportal-app voor macOS is beschikbaar <!--1541700-->
De Intune-bedrijfsportal op macOS is bijgewerkt en geoptimaliseerd, zodat alle informatie en nalevingsmeldingen die uw gebruikers nodig hebben voor alle apparaten die ze hebben ingeschreven, overzichtelijk wordt weergegeven. En als de Intune-bedrijfsportal eenmaal is geïmplementeerd op een apparaat, zorgt Microsoft AutoUpdate voor macOS voor de updates. U kunt de nieuwe Intune-bedrijfsportal voor macOS downloaden door u aan te melden bij de website van de Intune-bedrijfsportal vanaf een macOS-apparaat.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner maakt nu deel uit van de MAM-lijst (beheer van mobiele apps) met goedgekeurde apps <!-- 1248473 -->
De app Microsoft Planner voor iOS en Android maakt nu deel uit van de goedgekeurde apps voor Mobile App Management (MAM). De app kan via de blade Intune-app-beveiliging in Azure Portal worden geconfigureerd voor alle tenants.
- Meer informatie over de [MAM-lijst met goedgekeurde apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Vereiste updatefrequentie voor VPN per app op iOS-apparaten <!-- 1547061 -->  
Beheerders kunnen nu de vereisten voor VPN per app verwijderen voor apps op iOS-apparaten. Dit wordt toegepast op de betreffende apparaten na de eerstvolgende check-in bij Intune, gewoonlijk binnen 15 minuten.  

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Ondersteuning van management pack van System Center Operations Manager voor Exchange Connector <!-- 885457 -->
Het management pack van System Center Operations Manager (SCOM) voor Exchange Connector is nu beschikbaar om de logboeken van Exchange Connector te parseren. Hiermee kunt u de service op verschillende manieren controleren wanneer u problemen moet oplossen.

## <a name="week-of-november-6-2017"></a>Week van 6 november 2017

### <a name="device-enrollment"></a>Apparaatinschrijving
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Co-management voor Windows 10-apparaten <!-- 1243445 -->
Co-management is een oplossing die een brug slaat tussen traditioneel en modern beheer en het biedt een gefaseerde benadering om de overstap te maken. Co-management is in feite een oplossing waarbij Windows 10-apparaten gelijktijdig worden beheerd door Configuration Manager en Microsoft Intune en zijn gekoppeld aan Active Directory (AD) en Azure Active Directory (Azure AD).  Deze configuratie geeft u een manier om mettertijd te moderniseren, in een tempo dat geschikt is voor uw organisatie als u niet allemaal tegelijk kunt overstappen.  

#### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Pagina Status van nieuwe inschrijving voor Windows 10-inschrijvingen <!--1063201-->    
U kunt nu een begroeting configureren die verschijnt wanneer uw gebruikers Windows 10-apparaten inschrijven. Gebruik het **scherm Status van inschrijving** om een aangepast bericht en een hyperlink te configureren die aan uw eindgebruikers worden getoond wanneer ze hun Windows 10-apparaten inschrijven.  Op het **scherm Status van inschrijving** kunnen eindgebruikers ook de voortgang zien van beleidsinstellingen die op hun apparaat worden toegepast.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Windows-inschrijving beperken door de versie van het besturingssysteem <!-- 245498 -->
Als Intune-beheerder kunt u een minimale en maximale versie opgeven van Windows 10 voor de inschrijving van apparaten. U kunt deze beperkingen instellen op de blade **Platformconfiguraties**.

Intune blijft ondersteuning bieden voor registratie Windows 8.1-pc's en -telefoons. U kunt echter alleen minimale en maximale versies instellen voor Windows 10-versies. Als u de inschrijving van 8.1-apparaten wilt toestaan, laat u de minimale versie leeg.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Waarschuwingen voor niet-toegewezen Windows AutoPilot-apparaten <!-- 1631236 -->
Er is een nieuwe waarschuwing voor niet-toegewezen Windows AutoPilot-apparaten op de pagina **Microsoft Intune** > **Apparaatinschrijving** > **Overzicht**. Deze waarschuwing geeft aan voor hoeveel apparaten van het AutoPilot-programma geen AutoPilot-implementatieprofielen zijn toegewezen. Aan de hand van de informatie in de waarschuwing kunt u profielen maken en deze toewijzen aan de niet-toegewezen apparaten. Als u op de waarschuwing klikt, verschijnt een volledige lijst met Windows AutoPilot-apparaten en gedetailleerde informatie. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](https://docs.microsoft.com/intune/enrollment-autopilot) voor meer informatie.

### <a name="device-management"></a>Apparaatbeheer

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Knop voor het vernieuwen van de lijst met apparaten    <!-- 1333581 -->
Omdat de lijst met apparaten niet automatisch wordt vernieuwd, kunt u de nieuwe knop gebruiken om de apparaten bij te werken die worden weergegeven in de lijst.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Ondersteuning voor Symantec Cloud Certification Authority (CA)  <!-- 1333638 -->    
Intune ondersteunt nu Symantec Cloud CA die de Intune Certificate Connector in staat stelt PKCS-certificaten van Symantec Cloud CA vrij te geven voor beheerde Intune-apparaten. Als u de Intune Certificate Connector al gebruikt met Microsoft Certification Authority (CA), kunt u de bestaande configuratie van de Intune Certificate Connector gebruiken om de ondersteuning voor Symantec Cloud CA toe te voegen.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Nieuwe items toegevoegd aan de apparaatinventarisatie   <!--1404455 -->
In deze release zijn de volgende nieuwe items toegevoegd aan de [inventaris van ingeschreven apparaten](device-inventory.md):

- Mac-adres van Wi-Fi
- Totale opslagruimte
- Totale vrije ruimte
- MEID
- Provider van abonnee


### <a name="app-management"></a>Appbeheer
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Toegang instellen voor apps via minimale Android-beveiligingspatch op het apparaat<!-- 1278463 -->   
Een beheerder kan de minimale Android-beveiligingspatch definiëren die op het apparaat moet zijn geïnstalleerd om toegang te kunnen krijgen tot een beheerde toepassing onder een beheerd account.

> [!Note]  
> Deze functie beperkt alleen beveiligingspatches die door Google zijn vrijgegeven op Android 6.0+ apparaten.

#### <a name="app-conditional-launch-support----1193313---"></a>Ondersteuning voor app-voorwaardelijk starten <!-- 1193313 -->
IT-beheerders kunnen nu via de Azure-beheerportal een vereiste instellen om een wachtwoordcode in plaats van een numerieke pincode af te dwingen via Mobile App Management (MAM) wanneer de toepassing start. Als dit is geconfigureerd, moet de gebruiker een wachtwoordcode instellen en gebruiken wanneer daarom wordt gevraagd, alvorens toegang te krijgen tot toepassingen met MAM-functionaliteit. Een wachtwoordcode wordt gedefinieerd als een numerieke pincode met ten minste één speciaal teken of een hoofdletter/kleine letter. Bij deze release van Intune wordt deze functie **alleen op iOS** ingeschakeld. Intune ondersteunt wachtwoordcodes op dezelfde manier als numerieke pincodes: er is een minimumlengte, en tekens en tekenreeksen mogen worden herhaald. Deze functie vereist dat toepassingen (WXP, Outlook, Managed Browser, Yammer) de Intune App SDK integreren met de code voor deze functie om de wachtwoordcode-instellingen af te dwingen in de doeltoepassingen.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>App-versienummer voor line-of-business in rapport Installatiestatus van het apparaat <!-- 1233999 -->
Bij deze release toont het rapport Installatiestatus van het apparaat het app-versienummer voor de line-of-business-apps voor iOS en Android. U kunt deze informatie gebruiken om problemen met uw apps op te lossen of om apparaten te vinden waarop verouderde app-versies worden uitgevoerd.


### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Beheerders kunnen de firewall-instellingen op een apparaat nu configureren met behulp van een apparaatconfiguratieprofiel <!-- 951708 -->   
Beheerders kunnen de firewall inschakelen voor apparaten, en ook verschillende protocollen voor domein-, privé- en openbare netwerken configureren.  Deze firewall-instellingen staan in het profiel 'Endpoint Protection'.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard helpt apparaten te beschermen tegen niet-vertrouwde websites, zoals gedefinieerd door uw organisatie <!-- 958257 -->   
Beheerders kunnen sites als 'vertrouwd' of 'zakelijk' definiëren met behulp van een Windows Information Protection-werkstroom of het nieuwe profiel 'Netwerkgrens' onder apparaatconfiguraties. Sites die niet in een vertrouwde netwerkgrens van een 64-bits Windows 10-apparaat staan, worden in een browser op een virtuele Hyper-V-computer geopend als ze met Microsoft Edge worden bekeken.

Application Guard staat in de apparaatconfiguratieprofielen, in het profiel 'Endpoint Protection'. Beheerders kunnen daar interactie configureren tussen de gevirtualiseerde browser en de hostcomputer, niet-vertrouwde sites en vertrouwde sites, en gegevens opslaan die in de gevirtualiseerde browser worden gegenereerd. Als u Application Guard op een apparaat wilt gebruiken, moet er eerst een netwerkgrens worden geconfigureerd. Het is belangrijk slechts één netwerkgrens te definiëren voor een apparaat.  

#### <a name="windows-defender-application-guard-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Guard op Windows 10 Enterprise biedt een modus om alleen geautoriseerde apps te vertrouwen <!-- 1031096 -->    
Aangezien er elke dag duizenden nieuwe schadelijke bestanden worden gemaakt, biedt malwaredetectie op basis van handtekeningen misschien niet meer voldoende bescherming tegen nieuwe aanvallen. Met Windows Defender Application Guard op Windows 10 Enterprise kunt u de apparaatconfiguratie wijzigen van een modus waarin apps worden vertrouwd tenzij ze door een antivirus- of andere beveiligingsoplossing worden geblokkeerd, naar een modus waarin het besturingssysteem alleen apps vertrouwt die door uw onderneming zijn geautoriseerd. In Windows Defender Application Guard definieert u welke apps u vertrouwt.

Met Intune kunt u het toepassingsbeheerbeleid configureren in de modus 'Alleen controle' of in de modus 'Afdwingen'. Apps worden niet geblokkeerd wanneer ze in de modus 'alleen controle' worden uitgevoerd. De modus 'Alleen controle' registreert alle gebeurtenissen in lokale clientlogboeken. U kunt ook configureren of alleen Windows-onderdelen en Windows Store-apps mogen worden uitgevoerd of dat aanvullende apps met goede reputaties zoals gedefinieerd door de Intelligent Security Graph ook mogen worden uitgevoerd.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard is een nieuwe verzameling inbraakpreventiefuncties voor Windows 10 <!-- 1063615 -->   
Window Defender Exploit Guard omvat aangepaste regels om de exploiteerbaarheid van toepassingen te reduceren, voorkomt macro- en scriptbedreigingen, blokkeert automatisch netwerkverbindingen naar IP-adressen met een slechte reputatie, en kan gegevens uit ransomware en onbekende bedreigingen beveiligen. Windows Defender Exploit Guard bestaat uit de volgende onderdelen:

- **Attack Surface Reduction (ASR)** biedt regels waarmee u macro-, script- en e-mailbedreigingen kunt voorkomen.
- **Gecontroleerde maptoegang** blokkeert automatisch de toegang tot inhoud in beveiligde mappen.
- **Netwerkfilter** blokkeert uitgaande verbindingen van een app naar een IP/domein met een slechte reputatie
- **Exploit-beveiliging** biedt geheugen-, controlestroom- en beleidsbeperkingen die kunnen worden gebruikt om een toepassing te beschermen tegen aanvallen.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>PowerShell-scripts in Intune beheren voor Windows 10-apparaten <!-- 790537 -->

Met de Intune-beheeruitbreiding kunt u PowerShell-scripts uploaden in Intune om deze uit te voeren op Windows 10-apparaten. De uitbreiding is een aanvulling op de Windows 10 MDM-functionaliteit en maakt het eenvoudiger voor u om uw beheer te moderniseren. Zie [PowerShell-scripts in Intune beheren voor Windows 10-apparaten](intune-management-extension.md) voor meer informatie.

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Nieuwe apparaatbeperkingsinstellingen voor Windows 10      <!-- 1308850 -->
-    Berichten (alleen mobiel) - testen of MMS-berichten uitschakelen
-    Wachtwoord - instellingen om FIPS en het gebruik van secundaire Windows Hello-apparaten in te schakelen voor verificatie 
-    Weergave - instellingen om GDI-schaalbaarheid in of uit te schakelen voor verouderde apps

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Apparaatbeperkingen Windows 10-kioskmodus <!-- 1308872 -->   
U kunt gebruikers van Windows 10-apparaten beperken tot de kioskmodus, zodat ze worden beperkt tot een verzameling vooraf gedefinieerde apps.  Om dit te doen, maakt u een Windows 10-apparaatbeperkingsprofiel en configureert u de kioskinstellingen.

De kioskmodus ondersteunt twee modi: **één app** (waarbij een gebruiker slechts één app mag uitvoeren) en **meerdere apps** (geeft toegang tot een verzameling apps).  U definieert het gebruikersaccount en de apparaatnaam, waarmee de ondersteunde apps worden bepaald.  Wanneer de gebruiker is aangemeld, is hij/zij beperkt tot de gedefinieerde apps.  Zie [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp) voor meer informatie. 

De kioskmodus vereist het volgende:

- Intune moet de MDM-instantie zijn.
- De apps moeten al op het doelapparaat zijn geïnstalleerd.
- Het apparaat moet [goed ingericht](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) zijn.

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Nieuw apparaatconfiguratieprofiel voor het maken van netwerkgrenzen <!-- 1311967 -->   
Wij hebben een apparaatconfiguratieprofiel genaamd **Netwerkgrens** gemaakt, dat bij uw andere apparaatconfiguratieprofielen staat. Gebruik dit profiel om onlinebronnen te definiëren die u als zakelijk en vertrouwd wilt beschouwen. U moet een netwerkgrens voor een apparaat definiëren *voordat* functies zoals Windows Defender Application Guard en Windows Information Protection op het apparaat kunnen worden gebruikt. Het is belangrijk slechts één netwerkgrens te definiëren voor elk apparaat.

U kunt bedrijfscloudresources, IP-adresbereiken en interne proxyservers definiëren die u als vertrouwd wilt beschouwen. Nadat u de netwerkgrens hebt gedefinieerd, kan deze worden gebruikt door andere functies zoals Windows Defender Application Guard en Windows Information Protection.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Twee aanvullende instellingen voor Windows Defender Antivirus <!-- 1338409 -->  
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

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix-VPN toegevoegd voor Windows 10-apparaten <!-- 1512457 -->  
U kunt Citrix-VPN configureren voor Windows 10-apparaten van klanten. U kunt de Citrix-VPN kiezen in de lijst *Een verbindingstype selecteren* in de blade **Basis-VPN** wanneer u een VPN voor Windows 10 en hoger configureert.

> [!Note]
> Citrix-configuratie bestond voor iOS en Android.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>Wi-Fi-verbindingen ondersteunen vooraf gedeelde sleutels voor iOS <!-- 1550823 -->
Klanten kunnen Wi-Fi-profielen configureren voor het gebruik van vooraf gedeelde sleutels (PSK) voor WPA/WPA2 persoonlijke verbindingen op iOS-apparaten. Deze profielen worden gepusht naar het apparaat van de gebruiker als het apparaat is ingeschreven bij Intune.

Wanneer het profiel naar het apparaat is gepusht, is de volgende stap afhankelijk van de profielconfiguratie.  Als automatische verbinding is ingesteld, wordt automatisch verbinding gemaakt zodra het netwerk nodig is.  Als handmatige verbinding is ingesteld, moet de gebruiker de verbinding handmatig activeren.  

### <a name="intune-apps"></a>Intune-apps

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Toegang tot de logboeken van de beheerde app voor iOS <!-- 1469920 -->
Eindgebruikers waarvoor de beheerde browser is geïnstalleerd kunnen de beheerstatus van alle gepubliceerde Microsoft-apps bekijken en logbestanden versturen om problemen met hun beheerde iOS-apps op te lossen.

Zie [Toegang tot de logboeken van de beheerde app voor iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios) voor meer informatie over het inschakelen van de probleemoplossingsmodus in de beheerde browser op een iOS-apparaat.

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal voor iOS in versie 2.9.0 <!---1417174--->

We hebben de werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor iOS verbeterd. De taal is gebruiksvriendelijker en waar mogelijk hebben we schermen gecombineerd. We hebben de taal ook specifieker voor uw bedrijf gemaakt door overal in de installatietekst de naam van uw bedrijf te gebruiken. U kunt deze bijgewerkte werkstroom zien op de  [pagina met nieuwe functies in de app](whats-new-app-ui.md).

### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>De gebruikersentiteit bevat de meest recente gebruikersgegevens in het datawarehouse-gegevensmodel <!-- 1544273 -->
De eerste versie van het gegevensmodel Intune-datawarehouse bevat alleen recente, historische Intune-gegevens. Rapportopstellers kunnen de huidige status van een gebruiker niet vastleggen. In deze update wordt  **Gebruikersentiteit** ingevuld met de meest recente gebruikersgegevens.


## <a name="week-of-october-30-2017"></a>Week van 30 oktober 2017

### <a name="app-management"></a>Appbeheer

#### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Het versienummer van de line-of-business-app voor iOS en Android is zichtbaar <!-- 1380712 -->

In Apps in Intune wordt nu het versienummer voor iOS- en Android-line-of-business-apps weergegeven. Het nummer wordt in de Azure Portal in de app-lijst en in de blade App-overzicht getoond. Eindgebruikers kunnen het app-nummer in de bedrijfsportal-app en in de webportal zien.

__Volledig versienummer__ Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800)

Het volledige versienummer bevat twee onderdelen:

 - **Versie**  
   Het versienummer is het door mensen leesbare releasenummer van de app. Dit wordt door eindgebruikers gebruikt om de verschillende releases van de app aan te duiden.

 - **Buildnummer**  
    Het buildnummer is een intern nummer dat voor de detectie van apps en het beheer van apps via een programma kan worden gebruikt. Het buildnummer verwijst naar een iteratie van de app die refereert aan wijzigingen in de code.

Meer informatie over versienummers en het ontwikkelen van line-of-business-apps in [Aan de slag met Microsoft Intune App SDK](app-sdk-get-started.md#line-of-business-app-version-numbers).

#### <a name="device-and-app-management-integration----677972---"></a>Integratie van apparaat- en appbeheer <!-- 677972 -->   
Nu Mobile Device Management (MDM) en Mobile Application Management (MAM) van Intune beide toegankelijk zijn vanuit de Azure-portal, is Intune begonnen met het integreren van de IT-beheerervaring omtrent app- en apparaatbeheer. Deze wijzigingen zijn bedoeld om uw apparaat- en appbeheer te vereenvoudigen.

Meer informatie over de aangekondigde MDM- en MAM-wijzigingen staat in de [blog van het Intune-ondersteuningsteam](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

#### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Nieuwe inschrijvingswaarschuwingen voor Apple-apparaten<!-- 1471790 -->
De overzichtspagina voor de inschrijving toont nuttige waarschuwingen voor IT-beheerders met betrekking tot beheer van apparaten van Apple. Waarschuwingen worden weergegeven op de overzichtspagina wanneer het Apple MDM push-certificaat verloopt of al is verlopen, wanneer het token Device Enrollment Program verloopt of al is verlopen en wanneer er zich niet-toegewezen apparaten in het Device Enrollment Program bevinden.

#### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Ondersteuning voor token-vervanging voor de configuratie van de app zonder apparaatinschrijving <!-- 1080364 -->

U kunt tokens gebruiken voor dynamische waarden in app-configuraties voor apps op apparaten die niet zijn ingeschreven. Zie voor meer informatie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).

### <a name="intune-apps"></a>Intune-apps

#### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Updates in de bedrijfsportal-app voor Windows 10 <!--1299474-->
De pagina Instellingen in de bedrijfsportal-app voor Windows 10 is bijgewerkt, zodat de instellingen en de beoogde gebruikersacties consistenter zijn voor alle instellingen. De pagina komt nu ook beter overeen met de indeling van andere Windows-apps. U vindt afbeeldingen voor/na op de [pagina met nieuwe functies in de app](whats-new-app-ui.md).

#### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Eindgebruikers informeren welke apparaatgegevens voor Windows 10-apparaten kunnen worden gezien <!--1337920-->
De optie **Eigendomstype** is toegevoegd aan het scherm Apparaatgegevens in de bedrijfsportal-app voor Windows 10. Hierdoor kunnen gebruikers meer over privacy te weten komen vanaf deze pagina in de documenten voor Intune-eindgebruikers. Deze informatie is ook te vinden op het scherm **Info**.

#### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Vragen om feedback over de bedrijfsportal-app voor Android <!--1165249-->
De bedrijfsportal-app voor Android vraagt nu om feedback van eindgebruikers. Deze feedback wordt rechtstreeks naar Microsoft verzonden en biedt eindgebruikers de kans de app te beoordelen in de openbare Google Play Store. Feedback is niet vereist en kan eenvoudig worden gesloten, zodat gebruikers kunnen doorgaan met het gebruik van de app.

#### <a name="update-to-what-device-details-an-organization-can-see---1616825--"></a>Wijziging in de apparaatgegevens die een organisatie kan zien <!--1616825-->
De bedrijfsportal-app voor Android kan nu geofencing gebruiken om de toegang tot bedrijfsbronnen te beveiligen. Netwerkgegevens zoals IP-adres, standaardgatewayadres en Domain Name System (DNS) worden gebruikt om te bepalen of toegang tot beveiligde bedrijfsbronnen is toegestaan.

#### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Uw gebruikers helpen om zichzelf te redden met de bedrijfsportal-app voor Android<!---1573324, 1573150, 1558616, 1564878--->

De bedrijfsportal-app voor Android voegt aanwijzingen toe, zodat eindgebruikers meer inzicht krijgen en, waar mogelijk, nieuwe gebruikssituaties zelf kunnen oplossen.
- Eindgebruikers worden naar de (Azure Active Directory-portal) geleid [https://account.activedirectory.windowsazure.com/r/#/profile] om een apparaat verwijderen als zij het maximum aantal apparaten hebben bereikt dat ze mogen toevoegen.
- Eindgebruikers krijgen een stapsgewijze instructie om hen te helpen [foutmeldingen bij de activering van Samsung KNOX-apparaten op te lossen](https://go.microsoft.com/fwlink/?linkid=859718) of [de energiebesparende modus uit te schakelen](/intune-user-help/power-saving-mode-android). Als geen van deze oplossingen het probleem verhelpt, krijgt u een uitleg over het verzenden van [logboeken naar Microsoft](/intune-user-help/send-logs-to-microsoft-ios).

#### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Nieuwe actie 'Oplossen' beschikbaar voor Android-apparaten<!---1583480--->

De bedrijfsportal-app voor Android introduceert een actie 'Oplossen' op de pagina _Apparaatinstellingen bijwerken_. Als de eindgebruiker deze optie selecteert, komt deze rechtstreeks bij de instelling terecht die de oorzaak ervan is dat hun apparaat niet compatibel is. De bedrijfsportal-app voor Android ondersteunt momenteel deze actie ten aanzien van de instellingen [Toegangscode](/intune-user-help/set-your-pin-or-password-android), [USB-foutopsporing](/intune-user-help/you-need-to-turn-off-usb-debugging-android), en [Onbekende bronnen](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

#### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Voortgangsindicator voor apparaatinstallatie in Android-bedrijfsportal <!---1565657--->
In de bedrijfsportal-app voor Android wordt een voortgangsindicator voor de apparaatinstallatie weergegeven wanneer een gebruiker zijn of haar apparaat inschrijft. De aanduiding toont nieuwe statussen, te beginnen met 'Uw apparaat instellen...', vervolgens 'Het apparaat registreren...', daarna 'Registreren van het apparaat voltooien...' en tot slot 'Instellen van het apparaat voltooien...'.

## <a name="week-of-october-23-2017"></a>Week van 23 oktober 2017

### <a name="intune-apps"></a>Intune-apps
#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Ondersteuning voor op certificaten gebaseerde verificatie op de bedrijfsportal voor iOS <!--1029830-->
We hebben ondersteuning voor op certificaten gebaseerde verificatie toegevoegd in de bedrijfsportal-app voor iOS. Gebruikers met deze verificatie voeren hun gebruikersnaam in en tikken vervolgens op de koppeling 'Aanmelden met een certificaat'. Dit wordt al ondersteund in de bedrijfsportal-app voor Android en Windows. Meer informatie staat op de pagina [Aanmelden bij de bedrijfsportal-app](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

#### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps die met of zonder inschrijving beschikbaar zijn, kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd. <!-- 1334712 -->

Bedrijfs-apps die met of zonder inschrijving beschikbaar zijn gemaakt in de bedrijfsportal-app voor Android kunnen nu worden geïnstalleerd zonder dat er om inschrijving wordt gevraagd.

## <a name="week-of-october-16-2017"></a>Week van 16 oktober 2017
### <a name="device-enrollment"></a>Apparaatinschrijving
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Ondersteuning voor het Windows AutoPilot Deployment-programma in Microsoft Intune <!-- 747617  -->
U kunt nu Microsoft Intune gebruiken met het Windows AutoPilot Deployment-programma om uw gebruikers de mogelijkheid te geven hun bedrijfsapparaten in te richten zonder de tussenkomst van de IT-afdeling. U kunt de Out-of-the-box-ervaring (OOBE) aanpassen en gebruikers begeleiden bij het toevoegen van hun apparaat aan Azure AD en inschrijven bij Intune. Samen nemen Microsoft Intune en Windows AutoPilot de noodzaak weg voor het implementeren, onderhouden en beheren van installatiekopieën van besturingssystemen. Zie [Windows-apparaten inschrijven met het Windows AutoPilot Deployment-programma](https://docs.microsoft.com/intune/enrollment-autopilot) voor meer informatie.

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Snel starten met apparaatinschrijving <!-- 1425655 --> 
Snel starten is nu beschikbaar in **Apparaatinschrijving** en bevat een tabel met naslagonderwerpen voor het beheren van platformen en configureren van het inschrijvingsproces. Dankzij een korte beschrijving van elk item en koppelingen naar documentatie met stapsgewijze instructies kunt u sneller aan de slag.

#### <a name="device-categorization----1427491---"></a>Categorisatie van apparaten <!-- 1427491 -->
In de grafiek met platformen van ingeschreven apparaten op de blade **Apparaten > Overzicht** zijn apparaten geordend op platform, zoals Android, iOS, macOS, Windows en Windows Mobile.  Apparaten met een ander besturingssysteem zijn gegroepeerd in de categorie ‘Overig’.  Dit omvat apparaten van Blackberry, Nokia en andere fabrikanten.  

Als u wilt weten wat dit voor gevolgen heeft voor de apparaten in uw tenant, kiest u **Beheren > Alle apparaten** en gebruikt u vervolgens **Filter** om de inhoud van het veld **Besturingssysteem** te beperken.

### <a name="device-management"></a>Apparaatbeheer
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium - nieuwe Mobile Threat Defense-partner   <!-- 954681 -->  
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Zimperium, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd.

##### <a name="how-integration-with-intune-works"></a>Hoe werkt de integratie met Intune
Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten met door Zimperium. U kunt het EMS-beleid voor voorwaardelijke toegang configureren op basis van de Zimperium-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-compatibele apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10-apparaten  <!--- 978575, 1308849, -->  
Er worden nieuwe instellingen toegevoegd aan het apparaatbeperkingsprofiel voor Windows 10 in de categorie Windows Defender SmartScreen.

Zie [Apparaatbeperkingsinstellingen voor Windows 10-apparaten en hoger]( device-restrictions-windows-10.md) voor meer informatie.

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Externe ondersteuning voor Windows- en Windows Mobile-apparaten  <!-- 1070473 -->  
Intune kan de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software gebruiken zodat u uw gebruikers met Windows- en Windows Mobile-apparaten hulp op afstand kunt bieden.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Apparaten scannen met Windows Defender <!-- 1280988  1280990   -->
U kunt nu een **Snelle scan** en **Volledige scan** uitvoeren en **Handtekeningen bijwerken** met Windows Defender Antivirus op beheerde Windows 10-apparaten. Kies op de overzichtsblade van het apparaat de actie die u op het apparaat wilt uitvoeren. U wordt gevraagd om de actie te bevestigen voordat de opdracht naar het apparaat wordt verzonden. 

**Snelle scan**: een snelle scan scant locaties waar malware zich registreert, zoals registercodes en bekende opstartmappen in Windows. Een snelle scan duurt gemiddeld vijf minuten. In combinatie met de instelling **Realtimebeveiliging altijd ingeschakeld**, die bestanden scant wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map gaat, helpt een snelle scan om bescherming te bieden tegen malware die zich mogelijk in het systeem of de kernel bevindt. Gebruikers zien de scanresultaten op hun apparaten wanneer hij is voltooid. 

**Volledige scan**: een volledige scan kan handig zijn om vast te stellen of er inactieve componenten zijn die een diepgaandere opschoning vereisen op apparaten die met een malwarebedreiging te maken hebben gekregen. De scan is handig voor het uitvoeren van scans op aanvraag. Het uitvoeren van volledige scans kan een uur duren. Gebruikers zien de scanresultaten op hun apparaat wanneer de scan is voltooid. 

**Handtekeningen bijwerken**: de opdracht Handtekeningen bijwerken werkt de malwaredefinities en-handtekeningen in Windows Defender Antivirus bij. Dit helpt ervoor te zorgen dat Windows Defender Antivirus malware effectief detecteert. Deze functie is alleen voor Windows 10-apparaten en zolang er een internetverbinding is. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>De knop Inschakelen/Uitschakelen is verwijderd van de pagina Intune-certificaatinstantie van de Intune Azure-portal <!-- 1400455 -->
 We verwijderen een extra stap voor het instellen van de certificaatconnector in Intune. Op dit moment downloadt u de certificaatconnector en schakelt u die in de Intune-console in. Als u de connector echter uitschakelt in de Intune-console, blijft de connector toch certificaten uitgeven.

##### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Met ingang van oktober is de knop Inschakelen/Uitschakelen niet langer aanwezig op de pagina Certificaatinstantie in de Azure-portal. De functionaliteit van de connector blijft hetzelfde. Certificaten worden nog steeds geïmplementeerd naar apparaten die zijn ingeschreven in Intune. U kunt de certificaatconnector nog steeds downloaden en installeren. Als u niet langer certificaten wilt uitgeven, verwijdert u de certificaatconnector in plaats van dat u die uitschakelt.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Als de certificaatconnector momenteel is uitgeschakeld, moet u die verwijderen.

### <a name="device-configuration"></a>Apparaatconfiguratie
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Nieuwe instellingen voor het beperkingsprofiel voor Windows 10 Team-apparaten <!--- 1308838 -->
In deze versie hebben we veel nieuwe instellingen toegevoegd aan het beperkingsprofiel voor Windows 10 Team-apparaten, om u te helpen bij het beheren van Surface Hub-apparaten.

Raadpleeg [Intune-apparaatbeperkingen voor Windows 10 Team](device-restrictions-windows-10-teams.md) voor meer informatie over dit profiel.

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Voorkomen dat gebruikers van Android-apparaten de datum en tijd van hun apparaat wijzigen  <!-- 1333292 -->
U kunt een [aangepast beleid voor Android-apparaten](custom-settings-android.md) gebruiken om te voorkomen dat gebruikers van Android-apparaten de datum en tijd van het apparaat wijzigen.

Configureer hiervoor een aangepast Android-beleid met de instelling URI ./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange Stel dit in op **TRUE** en wijs het vervolgens toe aan de vereiste groepen.

#### <a name="bitlocker-device-configuration----1397398---"></a>Configuratie van BitLocker-apparaat <!-- 1397398 -->
**Windows-versleuteling > Basisinstellingen** bevat een nieuwe instelling **Waarschuwing voor een andere schijfversleuteling** waarmee u de [waarschuwing](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) voor versleuteling van een andere schijf die mogelijk op het apparaat van de gebruiker wordt gebruikt kunt uitschakelen.  De waarschuwing vereist dat eindgebruikers toestemming geven voordat ze BitLocker op het apparaat configureren en blokkeert de configuratie van Bitlocker totdat de eindgebruiker bevestigend heeft gereageerd.  De nieuwe instelling schakelt de waarschuwing voor de eindgebruiker uit.


### <a name="app-management"></a>Appbeheer
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Het volume-aankoopprogramma voor zakelijke apps synchroniseert nu met uw Intune-tenant <!-- 800882 -->  
Externe ontwikkelaars kunnen privé apps distribueren naar geautoriseerde VPP (volume-aankoopprogramma) for Business-leden die zijn opgegeven in iTunes Connect. Deze VPP for Business-leden kunnen zich aanmelden bij de Volume Purchase Program App Store en hun apps kopen.

Met ingang van deze release worden VPP for Business-apps die door de gebruiker zijn gekocht, gesynchroniseerd met hun Intune-tenant.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Specifieke Apple Store selecteren om VPP-apps te synchroniseren  <!-- 1332311 -->  
U kunt de store in het land voor het volumeaankoopprogramma (VPP) configureren als u uw VPP-token uploadt. Intune synchroniseert VPP-apps voor alle landinstellingen uit de opgegeven store uit het land waar de VPP geldt.

> [!NOTE]  
> Op dit moment synchroniseert Intune alleen VPP-apps uit de store van het VPP-land dat overeenkomt met de Intune-landinstelling waarin de Intune-tenant werd gemaakt.


### <a name="intune-apps"></a>Intune-apps
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Kopiëren en plakken tussen werkprofielen en persoonlijke profielen blokkeren in Android for Work <!-- 1098994 -->
Door deze release kunt u het werkprofiel voor Android for Work zo configureren dat kopiëren en plakken tussen zakelijke en persoonlijke apps wordt geblokkeerd. U kunt deze nieuwe instelling vinden in het profiel **Apparaatbeperkingen** voor het **Android for Work**-platform onder **Werkprofielinstellingen**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>iOS-apps maken die zijn beperkt tot specifieke regionale Apple App Stores <!-- 1281692 -->
U kunt de landinstelling voor een land opgeven wanneer u een beheerde app voor de Apple App Store maakt.

> [!Note]  
> Op dit moment kunt u alleen beheerde apps voor de Apple App Store maken die aanwezig zijn in de store voor de VS.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Gelicentieerde iOS-apps voor VPP-gebruikers en -apparaten bijwerken  <!-- 1305564 -->  
U kunt het VPP-token voor iOS zo configureren dat alle apps die voor dat token zijn gekocht worden bijgewerkt via de Intune-service. Intune detecteert updates voor de VPP-app in de app store en stuurt ze automatisch naar het apparaat als dit incheckt.

Zie [iOS-apps beheren die zijn aangeschaft via een volumeaankoopprogramma met Microsoft Intune] (/intune/vpp-apps-ios) voor meer informatie over het instellen van een VPP-token en inschakelen van automatische updates.


### <a name="monitor-and-troubleshoot"></a>Bewaken en problemen oplossen
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Verzameling voor koppelingsentiteit voor apparaten van gebruikers toegevoegd aan het Intune-datawarehouse-gegevensmodel <!-- 1187917 -->
U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten. Het gegevensmodel is toegankelijk via het Power BI-bestand (PBIX) dat wordt opgehaald op de datawarehouse-pagina in Intune, via het OData-eindpunt of door een aangepaste client te ontwikkelen.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Naleving van het beleid voor Windows 10-update-ringen controleren <!-- 1067886 -->
U kunt een beleidsrapport voor uw Windows 10-update-ringen bekijken via Software-updates > Implementatiestatus per update-ring. Het beleidsrapport bevat de implementatiestatus voor de update-ringen die u hebt geconfigureerd. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Nieuw rapport met iOS-apparaten met oudere iOS-versies   <!-- 1352223 -->
Het rapport **Out-of-date iOS Devices** (Verouderde iOS-apparaten) is beschikbaar in de werkruimte **Software-updates**. Het rapport bevat een lijst met gecontroleerde iOS-apparaten waarop een iOS-updatebeleid van toepassing is geweest en waarvoor updates beschikbaar zijn. Voor elk apparaat kunt u bekijken waarom het apparaat niet automatisch is bijgewerkt. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Beleidstoewijzingen voor app-beveiliging bekijken om problemen op te lossen <!--  1475003 -->
In deze toekomstige release wordt de optie **App-beveiligingsbeleid** toegevoegd aan de vervolgkeuzelijst **Toewijzingen** op de blad voor probleemoplossing. U kunt nu beleid voor app-beveiliging selecteren om de beleidsregels voor app-beveiliging te zien die aan de geselecteerde gebruikers zijn toegewezen.



## <a name="week-of-october-2-2017"></a>Week van 2 oktober 2017
### <a name="intune-apps"></a>Intune-apps
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Verbeteringen in de werkstroom voor apparaatinstellingen in de bedrijfsportal <!--1490692-->
We hebben de werkstroom voor apparaatinstellingen in de bedrijfsportal-app voor Android verbeterd. De taal is gebruiksvriendelijker en specifiek voor uw bedrijf. Daarnaast hebben we waar mogelijk schermen gecombineerd. U kunt deze zien op de pagina [Nieuw in de app-gebruikersinterface](whats-new-app-ui.md#week-of-october-2-2017).

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Verbeterde richtlijnen voor het aanvragen van toegang tot contactpersonen op Android-apparaten <!--1484985-->

Voor de bedrijfsportal-app voor Android moet de eindgebruiker vaak de machtiging Contactpersonen accepteren. Als een eindgebruiker deze toegang weigert, ziet deze nu een melding in de app waarin wordt aangegeven dat deze moet worden verleend voor voorwaardelijke toegang. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Beveiligd opstartherstel voor Android<!--1490712-->

Eindgebruikers met Android-apparaten kunnen tikken op de reden van niet-naleving in de bedrijfsportal-app. Indien mogelijk worden ze hiermee rechtstreeks naar de juiste locatie geleid in de instellingen-app om het probleem te verhelpen. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Aanvullende pushmeldingen voor eindgebruikers op de bedrijfsportal-app voor Android Oreo <!--1475932-->

Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal-app voor Android Oreo achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service. Dit biedt gebruikers meer transparantie over wanneer de bedrijfsportal-app beheertaken uitvoert op hun apparaat. Dit maakt deel uit van de algehele [optimalisatie van de gebruikersinterface van de bedrijfsportal](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) voor de bedrijfsportal-app voor Android Oreo. 

Er zijn nog meer optimalisaties voor nieuwe UI-elementen die in Android Oreo zijn ingeschakeld.  Eindgebruikers ontvangen aanvullende meldingen wanneer de bedrijfsportal achtergrondtaken uitvoert, zoals het ophalen van beleid van de Intune-service.  Dit biedt eindgebruikers meer transparantie over wanneer met de bedrijfsportal-app beheertaken worden uitgevoerd op het apparaat.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Nieuw gedrag voor de bedrijfsportal-app voor Android met werkprofielen <!---1485783--->

Als u een Android voor Work-apparaat met een werkprofiel inschrijft, voert de bedrijfsportal-app in het werkprofiel beheertaken uit op het apparaat. 

De bedrijfsportal-app voor Android wordt niet langer gebruikt, tenzij u een app met MAM-functionaliteit in het persoonlijke profiel gebruikt. Intune zal automatisch de persoonlijke bedrijfsportal-app verbergen om uw ervaring met het werkprofiel te verbeteren nadat de inschrijving van het werkprofiel is geslaagd.

De bedrijfsportal-app voor Android kan op elk gewenst moment in het persoonlijke profiel worden ingeschakeld door naar [Bedrijfsportal te zoeken in de Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) en op **Inschakelen** te tikken.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Bedrijfsportal voor Windows 8.1 en Windows Phone 8.1 wordt verplaatst naar onderhoudsmodus <!--1428681-->

Vanaf oktober 2017 worden de bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 verplaatst naar de onderhoudsmodus. Dit betekent dat de apps en bestaande scenario’s, zoals inschrijving en naleving, op deze platforms ondersteund blijven worden. De apps blijven beschikbaar om te worden gedownload via bestaande release-kanalen, zoals de Microsoft Store. 

In de onderhoudsmodus worden er alleen kritieke beveiligingsupdates voor deze apps uitgebracht. Er worden geen extra updates of functies voor deze apps uitgebracht. Wanneer u nieuwe functies wilt, raden we u aan om uw apparaten bij te werken naar Windows 10 of Windows 10 Mobile. 


### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="block-unsupported-samsung-knox-device-enrollment------1490695----"></a>Registratie van niet-ondersteunde Samsung Knox-apparaten blokkeren <!--- 1490695 --->

Via de bedrijfsportal-app worden alleen ondersteunde Samsung Knox-apparaten geregistreerd. Om KNOX activeringsfouten te voorkomen waardoor de MDM-registratie onmogelijk wordt, wordt de apparaatregistratie alleen uitgevoerd als het apparaat wordt weergegeven in de [lijst met apparaten die is gepubliceerd door Samsung](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Bepaalde modelnummers van Samsung-apparaten bieden ondersteuning voor KNOX, andere niet. Controleer de KNOX-compatibiliteit bij de verkoper van uw apparaat voordat u een apparaat koopt en implementeert. U vindt de volledige lijst met gecontroleerde apparaten in de [beleidsinstellingen voor Android en Samsung KNOX Standard](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920----"></a>Einde van ondersteuning voor Android 4.3 en lager <!---1171126, 1326920 --->
Beheerde apps en de Intune-bedrijfsportal-app voor Android vereisen Android 4.4 en hoger voor toegang tot bedrijfsresources. Vanaf december worden alle ingeschreven apparaten verplicht buiten gebruik gesteld, waardoor bedrijfsresources niet meer toegankelijk zijn. Als u beleid voor app-beveiliging zonder MDM gebruikt, krijgen apps geen updates meer en neemt de gebruikservaring na verloop van tijd steeds verder af.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Eindgebruikers informeren over welke apparaatgegevens worden weergegeven op geregistreerde apparaten <!--1165314-->
Aan het scherm voor apparaatgegevens in alle bedrijfsportal-apps wordt de optie **Eigendomstype** toegevoegd. Hierdoor kunnen gebruikers meer over privacy te weten komen rechtstreeks via het artikel [Welke informatie kan uw bedrijf zien?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) Dit zal binnenkort worden geïmplementeerd in alle bedrijfsportal-apps. Voor iOS hebben we dit aangekondigd in [september](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017).


## <a name="week-of-september-25-2017"></a>Week van 25 september 2017

### <a name="device-enrollment"></a>Apparaatinschrijving

#### <a name="intune-supports-ios-11---1428975--"></a>Intune biedt ondersteuning voor iOS 11 <!--1428975-->
Intune biedt ondersteuning voor iOS 11. Dit werd eerder aangekondigd in de [blog Intune Support](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/).

#### <a name="end-of-support-for-ios-80----1164477---"></a>Einde van ondersteuning voor iOS 8.0 <!---1164477--->
Beheerde apps en de Intune-bedrijfsportal-app voor iOS vereisen iOS 9.0 en hoger voor toegang tot bedrijfsresources. Apparaten die niet voor september zijn bijgewerkt, hebben geen toegang meer tot de bedrijfsportal of beheerde apps. 

### <a name="intune-apps"></a>Intune-apps

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Actie voor vernieuwen toegevoegd aan de bedrijfsportal-app voor Windows 10 <!--1132468-->
Met de bedrijfsportal-app voor Windows 10 kunnen gebruikers de gegevens in de app vernieuwen door deze op te halen voor vernieuwing of door op pc’s op F5 te drukken.



## <a name="notices"></a>Mededelingen

### <a name="deprecating-support-for-os-x-yosemite-1010-and-previous-versions-of-macos---1489263-plan-for-change-for-1802--"></a>Beëindigde ondersteuning voor OS X Yosemite 10.10 en eerdere versies van macOS <!--1489263, plan for change for 1802-->

De inschrijving van apparaten met OS X Yosemite 10.10 en eerdere versies van macOS wordt vanaf februari 2018 niet meer ondersteund. Intune biedt volledige ondersteuning voor OS X El Capitan 10.11 en nieuwer.

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Nieuw pad voor beheerde apparaten in Graph API <!-- 1586728 -->
We wijzigen we het pad dat wordt gebruikt voor toegang tot beheerde apparaten in de bètaversie van de Graph API. 

| | |
|--|--|
| Huidig pad |  https://graph.microsoft.com/beta/managedDevices |
| Nieuw pad | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Beide paden zullen werken gedurende de maand oktober. Na de servicerelease van oktober zal alleen het nieuwe pad werken.  Als u de Graph API gebruikt voor toegang tot beheerde apparaten, moet u uw scripts en toepassingen bijwerken en verifiëren met het nieuwe pad. Bekijk het maandelijkse [Graph API-wijzigingslogboek](https://developer.microsoft.com/graph/docs/concepts/changelog) voor aanvullende wijzigingen.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->
Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in Azure Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot Azure Portal.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Beheerdersrollen die worden vervangen in Azure Portal
De bestaande MAM-beheerdersrollen (Mobile Application Management), namelijk Inzender, Eigenaar en Alleen-lezen, die in de klassieke Intune-portal (Silverlight) worden gebruikt, worden vervangen door een volledig nieuw op rollen gebaseerd toegangsbeheer in Intune Azure Portal. Wanneer u naar Azure Portal bent gemigreerd, moet u uw beheerders opnieuw toewijzen aan deze nieuwe beheerdersrollen. Zie [Op rollen gebaseerd toegangsbeheer voor Microsoft Intune](/intune/role-based-access-control) voor meer informatie over op rollen gebaseerd toegangsbeheer en de nieuwe rollen.



## <a name="whats-coming"></a>Binnenkort

### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Via Jamf ingeschreven macOS-apparaten beheren met de Intune-engine voor apparaatnaleving<!---1592747--->
Vanaf begin 2018 stuurt Jamf statusinformatie over macOS-apparaten naar Intune, waarna het apparaat wordt geëvalueerd op naleving van het beleid dat is gedefinieerd in de Intune-console. Op basis van de nalevingsstatus van het apparaat en van andere omstandigheden (zoals locatie, gebruikersrisico en dergelijke) dwingt voorwaardelijke toegang naleving af voor macOS-apparaten die toegang hebben tot toepassingen in de cloud en on-premises die zijn verbonden met Azure AD, met inbegrip van Office 365.

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Wijzigingen in de ondersteuning van de Intune-bedrijfsportal-app voor iOS  <!-- 1164474  -->
Binnen afzienbare tijd zal er een nieuwe versie van de Microsoft Intune-bedrijfsportal-app voor iOS uitkomen die alleen nog werkt met apparaten met iOS 9.0 of hoger. De versie van de bedrijfsportal die ondersteuning biedt voor iOS 8 zal nog maar voor zeer korte tijd beschikbaar zijn. Als u echter ook iOS-apps met MAM-functionaliteit gebruikt, is iOS 9.0 en hoger vereist. Het is dus belangrijk om te controleren of uw eindgebruikers zijn bijgewerkt naar de nieuwste versie van het besturingssysteem. 

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?
Hoewel er nog geen specifieke datums bekend zijn, melden we dit nu al zodat u genoeg tijd hebt om de update te plannen. Zorg ervoor dat uw gebruikers een update uitvoeren naar iOS 9 of hoger. Op het moment dat de nieuwe versie van de Intune-bedrijfsportal-app uitkomt, moeten uw eindgebruikers de bedrijfsportal-app bijwerken.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wat moet ik doen om me voor te bereiden op deze wijziging?
Vertel uw gebruikers dat ze een update moeten uitvoeren naar iOS 9.0 of hoger om optimaal gebruik te kunnen maken van nieuwe Intune-functies.  Vertel uw gebruikers dat ze de nieuwe versie van de bedrijfsportal moeten installeren om toegang te krijgen tot de nieuwe functies van de portal.

Ga naar de Intune-portal in de Azure-portal en kies Apparaten > Alle apparaten. Filter op iOS-versie om apparaten te zien met een oudere versie dan iOS 9.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->
Apple heeft aangekondigd dat specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS.

Een versie van de bedrijfsportal-app is beschikbaar gemaakt voor iOS via het Apple TestFlight-programma waarmee naleving van de nieuwe ATS-vereisten wordt afgedwongen. Als u dit wilt proberen zodat u uw ATS-compatibiliteit kunt testen, stuurt u een e-mail naar <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app"> CompanyPortalBeta@microsoft.com </a> met uw voornaam, achternaam, e-mailadres en bedrijfsnaam. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

## <a name="see-also"></a>Zie tevens
* [Microsoft Intune-blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap voor cloudplatform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Wat is er nieuw in de gebruikersinterface van de bedrijfsportal?](whats-new-app-ui.md)
* [Wat was er in de vorige maanden nieuw](whats-new-archive.md)
