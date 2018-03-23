---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e91745abb7c3409b31724101b3071157407acec9
ms.sourcegitcommit: 54fc806036f84a8667cf8f74086358bccd30aa7d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/20/2018
---
# <a name="the-early-edition-for-microsoft-intune---march-2018"></a>De vroege editie voor Microsoft Intune - maart 2018

De **vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Deel deze informatie niet buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
>De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Zie de pagina met [nieuwe hybridefuncties](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Engelstalig) voor meer informatie over nieuwe hybridefuncties.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->

## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Ondersteuning voor meerdere Exchange Connectors <!-- 2070451 -->

U bent niet langer beperkt tot één Microsoft Intune Exchange Connector per tenant. Intune ondersteunt meerdere Exchange Connectors, zodat u voorwaardelijke toegang van Intune kunt instellen met meerdere on-premises Exchange-organisaties.

Met een on-premises Exchange Connector voor Intune kunt u apparaattoegang tot uw on-premises Exchange-postvakken beheren op basis van of een apparaat is ingeschreven bij Intune en voldoet aan het Intune-nalevingsbeleid voor apparaten. Als u een connector wilt instellen, downloadt u de on-premises Exchange Connector voor Intune vanaf Azure Portal en installeert u deze op een server in uw Exchange-organisatie. Kies op het Microsoft Intune-dashboard **On-premises toegang** en kies vervolgens onder **Installatie** de optie **Exchange ActiveSync-connector**. Download de on-premises Exchange Connector en installeer deze op een server in uw Exchange-organisatie. Nu u niet meer beperkt bent tot één Exchange Connector per tenant, kunt u, als u extra Exchange-organisaties hebt, dit zelfde proces volgen om een connector te downloaden en installeren voor elke extra Exchange-organisatie.

### <a name="support-coming-for-new-cisco-anyconnect-client-for-ios----1333708---"></a>Ondersteuning voor nieuwe Cisco AnyConnect-client voor iOS is binnenkort beschikbaar<!-- 1333708 -->

Nieuwe VPN-profielen gemaakt voor Cisco AnyConnect voor iOS werken met Cisco AnyConnect 4.0.7x en hoger. Bestaande iOS Cisco AnyConnect VPN-profielen krijgen het label **Cisco Legacy AnyConnect** en blijven op dezelfde manier werken met Cisco AnyConnect 4.0.5x .

> [!NOTE]
> Deze wijziging is alleen voor iOS; er blijft slechts één Cisco AnyConnect-optie voor Android, Android for Work en macOS. 

#### <a name="more-information"></a>Meer informatie

U moet een nieuw iOS Cisco AnyConnect VPN-profiel maken voor de ondersteuning van de nieuwe app, omdat de nieuwe Cisco AnyConnect-app en de Cisco Legacy AnyConnect-app verschillende apps zijn. Als u de AnyConnect-client in uw omgeving beheert, moet u ook de nieuwe Cisco AnyConnect-app implementeren. Als u een upgrade wilt voltooien, moet u ook uw Cisco Legacy AnyConnect VPN-profiel wissen en de Cisco Legacy AnyConnect-app verwijderen. 

NAC-integratie (Network Access Control) werkt in de eerste release niet voor de nieuwe AnyConnect-client. We werken samen met Cisco om NAC-integratie te bieden in een toekomstige versie van Intune.

### <a name="enhanced-jailbreak-detection----846515---"></a>Verbeterde jailbreakdetectie <!-- 846515 -->

Verbeterde jailbreakdetectie is een nieuwe nalevingsinstelling die de manier waarop Intune opengebroken apparaten evalueert, verbetert. De instelling zorgt ervoor dat het apparaat regelmatiger incheckt bij Intune, waarvoor de locatie-services van het apparaat worden gebruikt en wat invloed heeft op het accugebruik.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Mogelijkheid om vereiste line-of-business-apps (LOB) te implementeren voor alle gebruikers op apparaten met Windows 10 Desktop <!-- 1627835 RS4 -->
Klanten kunnen vereiste Windows 10 line-of-business-apps implementeren om in apparaatcontexten te installeren. Hierdoor worden deze apps beschikbaar voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 Desktop-apparaten. 

### <a name="expiring-line-of-business-lob-apps-for-microsoft-intune----748789---"></a>Line-of-business-apps (LOB) voor Microsoft Intune verlopen <!-- 748789 -->
In Azure Portal waarschuwt Intune u met betrekking tot line-of-business-apps die bijna verlopen. Nadat een nieuwe versie van de line-of-business-app is geüpload, verwijdert Intune de melding over het verlopen uit de lijst met apps.

### <a name="company-portal-enrollment-improved----1874230--"></a>Inschrijving bedrijfsportal verbeterd <!-- 1874230-->
Gebruikers die een apparaat inschrijven via de bedrijfsportal op Windows 10 build 1703 en hoger, kunnen de eerste stap van de inschrijving voltooien zonder de app te verlaten.

### <a name="new-management-name-column----1333586---"></a>Nieuwe kolom Naam voor beheer <!-- 1333586 -->
Een nieuwe kolom met de naam **Naam voor beheer** wordt toegevoegd aan de blade voor apparaten. Dit is een automatisch gegenereerde, niet bewerkbare naam die per apparaat wordt toegewezen op basis van de volgende formule: 
- Standaardnaam voor alle apparaten: <username>_<devicetype>_<enrollmenttimestamp>
- Voor bulksgewijs toegevoegde apparaten: < PackageId/ProfileId >_<DeviceType>_<EnrollmentTime> 
 
Dit is een optionele kolom in de blade voor apparaten. Deze is niet standaard beschikbaar en u kunt de kolom alleen openen via de kolomkiezer. De naam van het apparaat wordt niet beïnvloed door deze nieuwe kolom.

### <a name="new-settings-for-windows-defender-security-center-notifications-device-configuration-profile----1631906---"></a>Nieuwe instellingen voor apparaatconfiguratieprofiel voor Windows Defender Security Center<!-- 1631906 -->

Er worden drie nieuwe stellingen voor het apparaatconfiguratieprofiel voor Windows Defender Security Center (WDSC) toegevoegd.

Beheerders kunnen het volgende:

- De pilaar Identiteit verbergen
- De pilaar Hardware en de bijbehorende subinstellingen verbergen
- De pilaar Ransomware (Onedrive voor bedrijven-bestandsherstel) verbergen

Wanneer u deze pilaren verbergt voor de WDSC-app verbergt, kunnen eindgebruikers deze instellingen niet configureren en worden geen enkele meldingen die zijn gekoppeld aan de verborgen onderdelen gegenereerd.

### <a name="mam-policies-targeted-based-on-management-state----1665993---"></a>Gericht MAM-beleid op basis van de beheerstatus <!-- 1665993 -->

U kunt zich richten op MAM-beleid op basis van de beheerstatus van het apparaat:

- **iOS-apparaten**: u kunt zich richten op niet-beheerde apparaten (alleen MAM) of door Intune beheerde apparaten.
- **Android-apparaten**: u kunt zich richten op niet-beheerde apparaten, door Intune beheerde apparaten en door Intune beheerde Android Enterprise-profielen (voorheen Android for Work).

### <a name="configure-gatekeeper-to-control-macos-app-download-source----1690459--"></a>Gatekeeper configureren om de downloadbron van macOS-apps te beheren <!-- 1690459-->

U kunt Gatekeeper configureren om uw apparaten te beveiligen tegen apps door te bepalen waarvan de apps kunnen worden gedownload. U kunt de volgende downloadbronnen configureren: **Mac App Store**, **Mac App Store en geïdentificeerde ontwikkelaars** of **Overal**. U kunt ook configureren of gebruikers een app kunnen installeren door middel van CTRL+klikken om deze Gatekeper-voorzieningen te overschrijven.

Deze instellingen zijn te vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS**  ->   **Eindpuntbeveiliging**.

### <a name="configure-the-mac-application-firewall----1690461---"></a>De firewall van Mac-toepassingen configureren <!-- 1690461 -->

U kunt de firewall van Mac-toepassingen configureren. U kunt deze gebruiken om verbindingen per toepassing te controleren, in plaats van per poort. Zo kunt u beter profiteren van de voordelen van firewallbeveiliging. Bovendien helpt het te voorkomen dat ongewenste apps gebruikmaken van netwerkpoorten die zijn geopend voor legitieme apps.
 
Deze functie kunt u vinden onder **Apparaatconfiguratie** -> **Profiel maken** -> **macOS** -> **Eindpuntbeveiliging**.

Wanneer u de Firewall-instelling hebt ingeschakeld, kunt u de firewall configureren met behulp van twee strategieën:

- Alle binnenkomende verbindingen blokkeren

   U kunt alle binnenkomende verbindingen voor de doelapparaten blokkeren. Als u ervoor kiest om dit te doen, worden binnenkomende verbindingen voor alle apps geblokkeerd. 

- Specifieke apps blokkeren of toestaan

   U kunt specifieke apps toestemming geven binnenkomende verbindingen te ontvangen of u kunt apps blokkeren. U kunt ook de verborgen modus inschakelen om reacties op peilverzoeken te voorkomen.
 
#### <a name="more-information"></a>Meer informatie

- Alle binnenkomende verbindingen blokkeren

   Hiermee worden alle services voor delen (zoals delen van bestanden en delen van het scherm) geblokkeerd en kunnen deze geen binnenkomende verbindingen ontvangen. De systeemservices die nog steeds binnenkomende verbindingen kunnen ontvangen, zijn:
   - configd - implementeert DHCP en andere services voor netwerkconfiguratie
   - mDNSResponder - implementeert Bonjour
   - racoon - implementeert IPSec

   Als u services voor delen wilt gebruiken, zorgt u ervoor dat **Binnenkomende verbindingen** is ingesteld op **Niet geconfigureerd** (niet op **Blokkeren**).

- Verborgen modus

   Schakel deze optie in om te voorkomen dat de computer reageert op peilverzoeken. De computer reageert nog wel op binnenkomende verzoeken voor toegestane apps. Onverwachte aanvragen, zoals ICMP (ping), worden genegeerd.
 

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android bijwerken <!--1631531 -->

We updaten de Help- en Feedback-ervaring op de bedrijfsportal-app voor Android zodat deze overeenkomt met de aanbevolen procedures voor Android-apps. We werken de bedrijfsportal-app voor Android in de komende maanden bij om het menu-item **Help en Feedback** op te delen in afzonderlijke menu-items, namelijk **Help** en **Feedback verzenden**. Op de **Help**-pagina komt een sectie **Veelgestelde vragen** sectie en een knop **E-mailondersteuning** waarmee eindgebruikers logboeken naar Microsoft kunnen uploaden en e-mail kunnen verzenden naar bedrijfsondersteuning om het probleem te beschrijven. **Feedback verzenden** leidt de gebruiker door een standaard Microsoft-feedbackformulier, waarin de gebruiker wordt gevraagd een keuze te maken uit: "Ik vindt iets leuk", "Ik vind iets niet leuk" of "Ik heb een idee."

### <a name="custom-book-categories-for-volume-purchase-program-vpp-ebooks----1488911---"></a>Aangepaste boekcategorieën voor eBooks in het VPP-programma (volume-aankoopprogramma) <!-- 1488911 -->
U kunt aangepaste eBook-categorieën maken en vervolgens VPP eBooks toewijzen aan deze aangepaste eBook-categorieën. Eindgebruikers kunnen de nieuwe eBook-categorieën en de boeken die zijn toegewezen aan de categorieën bekijken.

#### <a name="company-portal-for-android-visual-updates---976944---"></a>Bedrijfsportal-app voor visuele Android-updates <!--976944 -->

We werken de bedrijfsportal-app voor Android bij om de richtlijnen voor [Ontwerp van materiaal](https://material.io/) van Android te volgen. We publiceren afbeeldingen van de nieuwe pictogrammen in het artikel [Wat is er nieuw in de UI van de app](whats-new-app-ui.md) wanneer de app wordt uitgebracht. 

### <a name="edge-mobile-support-for-intune-app-protection-policies----1817882---"></a>Mobiele ondersteuning in Edge voor beveiligingsbeleid voor apps in Intune <!-- 1817882 -->

De Microsoft Edge-browser voor mobiele apparaten biedt ondersteuning voor het beveiligingsbeleid voor aps dat in Intune is gedefinieerd.

### <a name="use-fully-distinguished-name-as-subject-for-scep-certificate---2221763-eeready--"></a>De volledige DN-naam gebruiken als onderwerp voor het SCEP-certificaat <!--2221763 eeready-->
Wanneer u een SCEP-certificaatprofiel maakt, voert u de naam van het onderwerp in. Als naam van het onderwerp kunt u de volledige DN-naam gebruiken. Selecteer **Aangepast** bij **Onderwerpnaam** en voer `CN={{OnPrem_Distinguished_Name}}` in. Als u de variabele `{{OnPrem_Distinguished_Name}}` wilt gebruiken, moet u het gebruikerskenmerk `onpremisesdistingishedname` met behulp van [Azure Active Directory (AD) Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) synchroniseren met uw exemplaar van Azure AD. 

### <a name="ios-devices-are-prompted-for-a-pin-every-15-minutes---1550837-eeready--"></a>Op iOS-apparaten wordt elke vijftien minuten om een pincode gevraagd <!--1550837 eeready-->
Nadat een nalevings- of configuratiebeleid op een iOS-apparaat is toegepast, wordt gebruikers elke vijftien minuten gevraagd een pincode in te stellen. Gebruikers wordt continu gevraagd een pincode in te stellen totdat de code is ingesteld.

### <a name="enable-bluetooth-contact-sharing---android-for-work---1098983-eeready--"></a>Delen van contactpersonen via Bluetooth inschakelen - Android for Work <!--1098983 eeready-->
Standaard wordt op Android-apparaten voorkomen dat contactpersonen in het werkprofiel kunnen worden gesynchroniseerd met Bluetooth-apparaten. Als gevolg hiervan worden contactpersonen in het werkprofiel niet weergegeven bij Nummerweergave voor Bluetooth-apparaten.

Er is een nieuwe instelling in **Android for Work** > **Apparaat beperkingen** > **Instellingen voor werkprofiel**:
- Contactpersoon delen via Bluetooth

De Intune-beheerder kan deze instellingen configureren om delen in te schakelen. Dit is handig als u een apparaat wilt koppelen met een Bluetooth-apparaat in auto's waarop Nummerweergave wordt weergegeven voor handsfreegebruik. Als deze instellingen zijn ingeschakeld, worden de contactpersonen voor het werkprofiel weergegeven. Als deze instellingen niet zijn ingeschakeld, worden de contactpersonen voor het werkprofiel niet weergegeven.

Van toepassing op: apparaten met Android-werkprofiel voor Android 6.0 en hoger.

### <a name="schedule-your-automatic-updates---1805514---"></a>Automatische updates plannen <!--1805514 -->

In Intune kunt u met behulp van de [instellingen voor Windows 10-updatering](windows-update-for-business-configure.md) bepalen hoe automatische updates worden geïnstalleerd. U kunt terugkerende updates plannen en de week, de dag en het tijdstip opgeven. 

### <a name="disable-checks-on-device-restart---1805490---"></a>Controles bij opnieuw starten van apparaat uitschakelen <!--1805490 -->

In Intune kunt u [software-updates beheren](windows-update-for-business-configure.md). De eigenschap **Controles voor opnieuw starten** wordt toegevoegd en standaard ingeschakeld. Als u de standaardcontroles wilt overslaan die worden uitgevoerd wanneer u een apparaat opnieuw start (controle van actieve gebruikers, batterijniveau, enzovoort), selecteert u **Overslaan**. 

<!-- 1802 start -->

### <a name="new-enrollment-failure-trend-chart-and-failure-reasons-table----1471783---"></a>Nieuwe tabel met fouten bij inschrijving, trendgrafieken en oorzaken van fouten <!-- 1471783 -->

Op de overzichtspagina voor inschrijvingen kunt u de trend van mislukte inschrijvingen en de top vijf van oorzaken van fouten bekijken. Door te klikken op de grafiek of de tabel, kunt u inzoomen op gegevens om advies voor probleemoplossing en suggesties voor herstel te krijgen.

### <a name="customize-your-company-portal-themes-with-hex-codes---1049561---"></a>De bedrijfsportalthema's aanpassen met hexadecimale codes <!--1049561 -->

U kunt de themakleur in de bedrijfsportal-apps aanpassen met behulp van hexadecimale codes. Wanneer u de hexadecimale code invoert, wordt door Intune volgens de [WCAG 2.0-standaarden](http://www.w3.org/TR/WCAG20) bepaald met welke tekstkleur de hoogste mate van contrast tussen de tekstkleur en de achtergrondkleur wordt bereikt. U kunt in **Mobiele apps** > **Bedrijfsportal** bekijken hoe de tekstkleur en uw bedrijfslogo bij deze kleur worden weergegeven. 

### <a name="new-windows-defender-credential-guard-settings-added-to-endpoint-protection-settings---1102252---"></a>Er worden nieuwe Windows Defender Credential Guard-instellingen toegevoegd aan de Endpoint Protection-instellingen <!--1102252 --> 

Nieuwe instellingen voor [Windows Defender Credential Guard](https://docs.microsoft.com/windows/access-protection/credential-guard/credential-guard] worden toegevoegd aan **Apparaatconfiguratie** > **Profielen** > **Endpoint Protection**. De volgende instellingen worden toegevoegd: 

- Platformbeveiligingsniveau: geef aan of het platformbeveiligingsniveau wordt ingeschakeld bij de volgende keer dat de computer wordt opgestart. Bij beveiliging op basis van virtualisatie is beveiligd opstarten vereist. Beveiliging op basis van virtualisatie kan eventueel worden ingeschakeld met behulp van DMA-beveiligingen (Direct Memory Access). Voor DMA-beveiligingen is hardwareondersteuning vereist en deze worden alleen ingeschakeld op apparaten die juist zijn geconfigureerd.
- Beveiliging op basis van virtualisatie: geef aan of beveiliging op basis van virtualisatie wordt ingeschakeld bij de volgende keer dat de computer wordt opgestart. 
- Windows Defender Credential Guard: schakel Credential Guard met beveiliging op basis van virtualisatie in om referenties te kunnen beveiligen bij de volgende keer dat de computer wordt opgestart, wanneer het platformbeveiligingsniveau met beveiligd opstarten en de beveiliging op basis van virtualisatie beide zijn ingeschakeld. U kunt kiezen uit de volgende opties: **Uitgeschakeld**, **Ingeschakeld met UEFI-vergrendeling**, **Ingeschakeld zonder vergrendeling** en **Niet geconfigureerd**. 
  - Met de optie Uitgeschakeld wordt Credential Guard extern uitgeschakeld als deze eerder is ingeschakeld met de optie Ingeschakeld zonder vergrendeling.

  - Bij de optie Ingeschakeld met UEFI-vergrendeling kan Credential Guard niet worden uitgeschakeld met de registersleutel of via Groepsbeleid. Als u Credential Guard wilt uitschakelen nadat deze instelling is gebruikt, moet u het groepsbeleid instellen op Uitgeschakeld en de beveiligingsfunctionaliteit van elke computer, met een fysiek aanwezige gebruiker, verwijderen om de configuratie die is bewaard in UEFI te wissen. Zolang de UEFI-configuratie behouden blijft, is Credential Guard ingeschakeld.

  - Met de optie Ingeschakeld zonder vergrendeling kan Credential Guard extern worden uitgeschakeld via Groepsbeleid. Op de apparaten die gebruikmaken van deze instelling moet ten minste Windows 10 (versie 1511) worden uitgevoerd.

  - Bij de optie Niet geconfigureerd is de beleidsinstelling niet gedefinieerd. De beleidsinstelling wordt door Groepsbeleid niet naar het register weggeschreven en deze heeft dus geen invloed op computers of gebruikers. Als het register een actuele instelling bevat, wordt deze niet gewijzigd.

### <a name="reset-passwords-for-android-o-devices----1238299---"></a>Wachtwoorden voor Android O-apparaten opnieuw instellen <!-- 1238299 -->
U kunt de wachtwoorden voor ingeschreven Android O-apparaten opnieuw instellen. Wanneer u een aanvraag Wachtwoord opnieuw instellen naar een Android O-apparaat verzendt, wordt hiermee een nieuw wachtwoord voor het ontgrendelen van het apparaat of een vraag voor het beheerde profiel ingesteld voor de huidige gebruiker. Er wordt een wachtwoord of vraag verzonden, naargelang het apparaat een apparaateigenaar of profieleigenaar heeft. Het wachtwoord of de vraag wordt onmiddellijk van kracht.

### <a name="local-device-security-option-settings----1251887---"></a>Instellingen voor de beveiligingsopties van lokale apparaten <!-- 1251887 -->
U kunt beveiligingsinstellingen op Windows 10-apparaten inschakelen met de nieuwe instellingen voor de beveiligingsopties van lokale apparaten. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

### <a name="new-printer-settings-for-education-profiles----1308900---"></a>Nieuwe printerinstellingen voor onderwijsprofielen <!-- 1308900 -->

Er komen voor onderwijsprofielen nieuwe instellingen beschikbaar onder de categorie **Printers**: **Printers**, **Standaardprinter**, **Nieuwe printers toevoegen**. 

### <a name="ios-app-provisioning-configuration----1581650---"></a>Inrichtingsconfiguratie voor iOS-apps <!-- 1581650 -->
U kunt inrichtingsprofielen voor iOS-apps toewijzen om te voorkomen dat uw apps verlopen door beveiligingsgroepen op te nemen of uit te sluiten.

### <a name="new-windows-defender-application-guard-settings----1631890---"></a>Nieuwe instellingen voor Windows Defender Application Guard <!-- 1631890 -->

- **Grafische versnelling inschakelen**

Beheerders kunnen voortaan een virtuele grafische processor inschakelen voor Windows Defender Application Guard. Met deze instelling kan de CPU taken voor de grafische weergave overdragen aan de vGPU. Dit kan de prestaties verbeteren wanneer u met websites werkt die veeleisende grafische weergaven bevatten of een video in de container bekijkt.

- **SaveFilestoHost**

Beheerders kunnen ervoor zorgen dat bestanden worden doorgegeven van Microsoft Edge, die in de container wordt uitgevoerd, naar het hostbestandsysteem. Wanneer u deze optie inschakelt, kunnen gebruikers bestanden uit Microsoft Edge in de container downloaden naar het hostbestandsysteem.

### <a name="including-and-excluding-app-assignment-based-on-groups-for-android-enterprise----1813081---"></a>App-toewijzing op basis van groepen opnemen en uitsluiten voor Android Enterprise <!-- 1813081 -->
Tijdens de app-toewijzing en na het selecteren van een toewijzingstype biedt Android Enterprise (voorheen bekend als Android for Work) ondersteuning voor het uitsluiten van functionaliteit.

<!-- the following are present prior to 1802 -->

### <a name="targeting-compliance-policies-to-devices-in-device-groups---1307012---"></a>Nalevingsbeleid afstemmen op apparaten in apparaatgroepen <!--1307012 -->

U kunt nalevingsbeleid richten op gebruikers in gebruikersgroepen. U kunt nalevingsbeleid richten op apparaten in apparaatgroepen.

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

### <a name="configure-an-ios-app-pin----1586774---"></a>Een pincode voor een iOS-app configureren <!-- 1586774 -->
U kunt binnenkort een pincode vereisen voor de betreffende iOS-apps. U kunt de vereisten voor de pincode en de vervaldatum in dagen via Azure Portal configureren. Indien vereist,wordt een gebruiker verplicht om een nieuwe pincode in te stellen en te gebruiken voordat deze toegang krijgt tot een iOS-app. Alleen iOS-apps met een app-beveiliging die is ingeschakeld met de Intune App SDK ondersteunen deze functie.

<!-- the following are present prior to 1711 -->

### <a name="azure-active-directory-web-sites-can-require-the-intune-managed-browser-app-and-support-single-sign-on-for-the-managed-browser-public-preview----710595---"></a>Azure Active Directory-websites kunnen de Intune Managed Browser-app vereisen en ondersteunen eenmalige aanmelding voor de Managed Browser (openbare preview) <!-- 710595 -->   
Met Azure Active Directory (Azure AD) kunt u de toegang tot websites op mobiele apparaten beperken tot de Intune Managed Browser-app. In de Managed Browser blijven websitegegevens veilig en gescheiden van de persoonlijke gegevens van eindgebruikers. Daarnaast ondersteunt de Managed Browser eenmalige aanmelding voor sites die door Azure AD worden beveiligd. Door u aan te melden bij de Managed Browser of door de Managed Browser op een apparaat te gebruiken met een andere app die door Intune wordt beheerd, krijgt de Managed Browser toegang tot bedrijfssites die door Azure AD worden beveiligd, zonder dat de gebruiker referenties hoeft in te voeren. Deze functionaliteit is van toepassing op sites zoals Outlook Web Access (OWA) en SharePoint Online, evenals andere bedrijfssites zoals intranetbronnen die via de Azure App Proxy worden geopend.

<!-- the following are present prior to 1711 -->

### <a name="redirecting-macos-users-to-the-new-company-portal-app---1380728--"></a>MacOS-gebruikers omleiden naar de nieuwe bedrijfsportal-app <!--1380728-->   
Wanneer eindgebruikers zich aanmelden bij de bedrijfsportalwebsite om hun macOS-apparaten in te schrijven, worden ze gevraagd de nieuwe bedrijfsportal-app voor macOS te downloaden om het proces te voltooien. Dit gebeurt voor macOS-apparaten waarop OS X El Capitan 10.11 of hoger wordt uitgevoerd. 

<!-- the following are present prior to 1709 -->

### <a name="improved-error-message-for-when-a-user-reaches-the-maximum-number-of-devices-allowed-to-enroll----1270370---"></a>Verbeterd foutbericht als een gebruiker het maximum aantal apparaten bereikt dat mag worden ingeschreven <!-- 1270370 -->
In plaats van een algemeen foutbericht krijgen eindgebruikers van Androis-apparaten een gebruikersvriendelijk foutbericht te zien waarop een actie kan worden uitgevoerd: 'U hebt het maximum aantal apparaten ingeschreven dat door de IT-beheerder is toegestaan. Verwijder een ingeschreven apparaat of vraag assistentie van uw IT-beheerder.'



## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.



### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


