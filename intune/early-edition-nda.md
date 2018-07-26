---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3aed8fcefd640e5b7df46fe1ef8cd1c973a68044
ms.sourcegitcommit: 5251a630fb2c7a2e6f86abd84ab887f8eabc1481
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/23/2018
ms.locfileid: "39212134"
---
# <a name="the-early-edition-for-microsoft-intune---july-2018"></a>De vroege editie voor Microsoft Intune - juli 2018

> [!Note]
> Melding geheimhoudingsverklaring: de volgende wijzigingen worden momenteel ontwikkeld voor Intune. Deze informatie wordt in heel beperkte mate verstrekt onder de geheimhoudingsverklaring. Plaats deze informatie niet op sociale media of openbare websites als Twitter, UserVoice, Reddit, enzovoort. 

De **vroege editie** bevat een lijst met functies, gedeeld onder geheimhoudingsverklaring, die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in beperkte mate verstrekt en kan worden gewijzigd. Stuur over deze informatie geen tweets, plaats hier niets over op UserVoice en deel hier op geen enkele andere wijze iets over buiten uw bedrijf. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Als u vragen of opmerkingen hebt, kunt contact opnemen met uw contactpersoon voor de Microsoft-productgroep.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

<!--
## What's coming to Intune in the Azure portal  
## What's coming to Intune apps
## Notices
-->
 
## <a name="intune-in-the-azure-portal"></a>Intune in Azure Portal

<!-- 1807 start -->

### <a name="more-sync-opportunities-in-the-company-portal-app-for-windows----2683177---"></a>Meer synchronisatiemogelijkheden in de Bedrijfsportal-app voor Windows <!-- 2683177 -->
De Bedrijfsportal-app voor Windows voegt een optie voor apparaatsynchronisatie toe aan de Windows-taakbalk en het startmenu. Klik vanuit een van de locaties om uw apparaten snel te synchroniseren en toegang te krijgen tot bedrijfsresources.  

### <a name="reset-device-passcodes-from-company-portal-app-for-windows-10----2101282---"></a>Apparaattoegangscode opnieuw instellen vanuit de bedrijfsportal-app voor Windows 10 <!-- 2101282 --> 
Uw werknemers kunnen binnenkort hun pincodes of toegangscode van hun apparaat rechtstreeks vanuit de bedrijfsportal-app voor Windows 10 opnieuw instellen. Deze functionaliteit wordt beschikbaar op zowel extern als lokaal door Intune beheerde apparaten die ondersteuning bieden voor het opnieuw instellen van toegangscodes. Afhankelijk van het type apparaat wordt bij een aanvraag die is ingediend voor een extern apparaat de huidige toegangscode verwijderd of wordt een tijdelijke toegangscode gemaakt. Gebruikers die verzoeken om een reset voor een lokaal apparaat worden doorgestuurd naar de Instellingen-app van het apparaat.  

### <a name="new-browsing-experiences-in-the-company-portal-app-for-windows----2317227---"></a>Nieuwe bladerervaringen in de Bedrijfsportal-app voor Windows <!-- 2317227 -->  
Wanneer u bladert of apps zoekt in de Bedrijfsportal-app voor Windows, kunt u schakelen tussen de bestaande weergave **Tegels** en de recent toegevoegde weergave **Details**. De nieuwe weergave bevat informatie over toepassingen, zoals de naam, de uitgever, de publicatiedatum en de installatiestatus.  

Op de pagina **Apps** staat de weergave **Geïnstalleerd**. Hier ziet u meer informatie over app-installaties die zijn voltooid en die nog bezig zijn. Wilt u feedback of ideeën over de nieuwe wijzigingen doorgeven? Stuur uw feedback op via de Bedrijfsportal-app.

### <a name="improved-company-portal-app-experience-for-device-enrollment-manager-users----675800---"></a>Verbeterde Bedrijfsportal-app-ervaring voor gebruikers van de apparaatinschrijvingsmanager <!-- 675800 -->
Wanneer een apparaatinschrijvingsmanager (DEM) zich aanmeldt bij de Bedrijfsportal-app voor Windows, wordt in de app alleen het huidige DEM-apparaat weergegeven dat wordt uitgevoerd. Dankzij deze verbetering treden er minder time-outs op. Deze time-outs traden voorheen op wanneer de app probeerde alle apparaten met DEM-registratie te laden.  

### <a name="use-smime-to-encrypt-and-sign-a-users-multiple-devices-----1333642---"></a>S/MIME gebruiken om meerdere apparaten van een gebruiker te coderen en ondertekenen <!-- 1333642 -->
Een toekomstige update bevat een S/MIME-e-mailversleuteling met een nieuw profiel voor een geïmporteerd certificaat (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > selecteer het platform > profieltype **Geïmporteerd PKCS-certificaat**). In Intune kunt u certificaten importeren in PFX-indeling. Intune kan deze certificaten dan leveren aan meerdere apparaten die zijn geregistreerd door één gebruiker. Dit omvat ook:

- Het systeemeigen iOS-e-mailprofiel ondersteunt het inschakelen van S/MIME-versleuteling met behulp van geïmporteerde certificaten in de PFX-indeling.
- De systeemeigen mail-app op Windows Phone 10-apparaten gebruikt automatisch het S/MIME-certificaat.
- De persoonlijke certificaten kunnen worden afgeleverd op meerdere platformen. Maar niet alle e-mail-apps ondersteunen S/MIME.
- Op andere platformen moet u mogelijk de mail-app handmatig configureren om S/MIME in te schakelen.  
- E-mail-apps die ondersteuning bieden voor S/MIME-versleuteling, kunnen het ophalen van certificaten voor S/MIME-e-mailversleuteling verwerken op een manier die een MDM niet kan ondersteunen, zoals het lezen van het certificaatarchief van de uitgever.

Wordt ondersteund op: Windows, Windows Phone 10, macOS, iOS, Android

### <a name="use-vpp-device-licenses-to-pre-provision-the-company-portal-during-dep-enrollment----1608345---"></a>VPP-apparaatlicenties gebruiken om de bedrijfsportal vooraf in te richten tijdens DEP-registratie <!-- 1608345 -->
U kunt Volume Purchase Program-apparaatlicenties (VPP) gebruiken om de bedrijfsportal vooraf in te richten tijdens de Device Enrollment Program-registraties (DEP). Om dit te doen, geeft u, wanneer u een registratieprofiel maakt of bewerkt, het VPP-token op dat u wilt gebruiken om de bedrijfsportal te installeren. Controleer of uw token niet verloopt en of u voldoende licenties heeft voor de bedrijfsportal-app. Wanneer het token verloopt of onvoldoende licenties heeft, pusht Intune in plaats daarvan de App Store-bedrijfsportal (deze vraagt om een Apple ID).

### <a name="bulk-delete-devices-on-devices-blade----1793693---"></a>Apparaten bulksgewijs verwijderen op apparatenblade <!-- 1793693 -->
U kunt meerdere apparaten tegelijk verwijderen op de blade Apparaten. Kies **Apparaten** > **Alle apparaten** > selecteer de apparaten die u wilt verwijderen > **Verwijderen**. In het geval van apparaten die niet kunnen worden verwijderd, wordt een melding weergegeven.

### <a name="new-wi-fi-device-configuration-profile-for-windows-10-and-later----1879077---"></a>Nieuw Wi-Fi-configuratieprofiel voor Windows 10 en hoger <!-- 1879077 -->
Momenteel kunt u Wi-Fi-profielen importeren en exporteren met XML-bestanden. U kunt een Wi-Fi-apparaatconfiguratieprofiel rechtstreeks in Intune maken, evenals in enkele andere platformen.

Om het profiel te maken, opent u **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Wi-Fi**. 

Van toepassing op Windows 10 en hoger.

###  <a name="windows-line-of-business-lob-apps-file-extensions----1884873---"></a>Bestandsextensies van Windows LOB-apps (line-of-business) <!-- 1884873 -->
De beschikbare bestandsextensies voor Windows LOB-apps omvatten nu ook *.msi*, *.appx*, *.appxbundle*, *.msix* en *.msixbundle*. U kunt in Microsoft Intune apps toevoegen via **Mobiele apps** > **Apps** > **Toevoegen**. Het deelvenster **App toevoegen** wordt weergegeven. Hier kunt u het **app-type** selecteren. Selecteer voor Windows LOB-apps **Line-Of-Business-app** als het app-type, selecteer het **app-pakketbestand** en voeg vervolgens een iOS-installatiebestand toe met de juiste extensie.

### <a name="windows-defender-atp-configuration-package-automatically-added-to-configuration-profile----2144658---"></a>Windows Defender ATP configuratiepakket automatisch toegevoegd aan configuratieprofiel <!-- 2144658 -->
Wanneer u [Advanced Threat Protection en onboarding](advanced-threat-protection.md#onboard-devices-using-a-configuration-profile)-apparaten gebruikt in Intune, downloadt u nu een configuratiepakket en voegt u dit toe aan uw configuratieprofiel. In een toekomstige update haalt Intune het pakket automatisch op uit het Windows Defender-beveiligingscentrum en voegt het toe aan uw profiel.

Van toepassing op Windows 10 en hoger.

### <a name="kiosk---obsolete-is-grayed-out-and-cant-be-changed----2149998---"></a>Kiosk - verouderd wordt grijs weergegeven en kan niet worden gewijzigd <!-- 2149998 -->
De [Kiosk-functie](device-restrictions-windows-10.md#kiosk-preview---obsolete) (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10 en hoger** > **Apparaatbeperkingen**) is binnenkort verouderd en wordt vervangen door [Kiosk-instellingen voor Windows 10 en hoger](kiosk-settings.md). De functie **Kiosk - verouderd** wordt grijs weergegeven en de gebruikersinterface kan niet worden gewijzigd of bijgewerkt. 

Zie voor het inschakelen van de kioskmodus [Kiosk-instellingen voor Windows 10 en hoger](kiosk-settings.md).

Is van toepassing op Windows 10 en hoger, Windows Holographic for Business

### <a name="apis-to-use-3rd-party-certification-authorities----2184013---"></a>API’s gaan basiscertificeringsinstanties van derden gebruiken <!-- 2184013 -->
Er komt een Java-API waarmee certificeringsinstanties van derden kunnen integreren met Intune en SCEP. Vervolgens kunnen gebruikers het SCEP-certificaat toevoegen aan een profiel en toepassen op apparaten via MDM.

Intune ondersteunt momenteel [SCEP-aanvragen met Active Directory Certificate Services](certificates-scep-configure.md).

### <a name="check-for-sccm-compliance----2192052---"></a>SCCM-naleving controleren <!-- 2192052 -->
Een toekomstige update bevat een nieuwe nalevingsinstelling van System Center Configuration Manager (SCCM) (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**   >  **Windows 10**). SCCM verzendt signalen naar Intune-nalevingsbeleid. Met de Intune-instelling kunt u vereisen dat alle SCCM-signalen 'conform' retourneren.

U kunt bijvoorbeeld vereisen dat alle software-updates worden geïnstalleerd op apparaten. Deze vereiste heeft in SCCM de status 'Geïnstalleerd'. Als programma's op het apparaat zich in onbekende staat bevinden, is het apparaat niet-compatibel in Intune.

Van toepassing op Windows 10 en hoger

### <a name="alerts-for-expiring-vpp-token-or-company-portal-license-running-low----2237572---"></a>Meldingen voor verlopend VPP-token of onvoldoende bedrijfsportal-licenties <!-- 2237572 -->
Als u het Volume Purchase Program (VPP) gebruikt om de bedrijfsportal vooraf in te richten tijdens DEP-inschrijving, waarschuwt Intune u wanneer het VPP-token bijna verloopt en wanneer er bijna te weinig licenties zijn voor de bedrijfsportal.

### <a name="confirmation-required-to-delete-vpp-token-that-is-being-used-for-company-portal-pre-provisioning----2237634---"></a>Bevestiging vereist om het VPP-token te verwijderen dat wordt gebruikt voor het vooraf inrichten van de bedrijfsportal <!-- 2237634 -->
Er is een bevestiging vereist om een Volume Purchase Program-token (VPP) te verwijderen als dit wordt gebruikt voor het vooraf inrichten van de bedrijfsportal tijdens de DEP-inschrijving.

### <a name="automatically-mark-android-devices-enrolled-by-using-samsung-knox-mobile-enrollment-as-corporate----2404851---"></a>Android-apparaten ingeschreven met Knox Mobile Enrollment van Samsung automatisch markeren als ‘zakelijk’ <!-- 2404851 -->
Android-apparaten die zijn ingeschreven met Samsung Knox Mobile Enrollment worden standaard gemarkeerd als **zakelijk** onder **Apparaateigendom**. U hoeft zakelijke apparaten niet handmatig te identificeren met IMEI- of serienummers voordat wordt ingeschreven met Knox Mobile Enrollment.

### <a name="toggle-to-show-or-not-show-the-end-session-button-on-a-kiosk-browser----2455253---"></a>In-/uitschakelen om de knop Sessie beëindigen wel of niet weer te geven in een Kiosk-browser <!-- 2455253 -->
U kunt configureren of Kiosk-browsers de knop Sessie beëindigen wel of niet weergeven. U ziet het besturingselement in **Apparaatconfiguratie** > **Kiosk (preview-versie)** > **Kiosk-webbrowser**. Indien ingeschakeld vraagt de app, wanneer een gebruiker op de knop klikt, om bevestiging om de sessie te beëindigen. Wanneer bevestigd, wist de browser alle browsegegevens en keert terug naar de standaard-URL.

### <a name="create-an-esim-cellular-configuration-profile----2564077---"></a>Een mobiel eSIM-configuratieprofiel maken <!-- 2564077 -->
In **Apparaatconfiguratie** kunt u een mobiel eSIM-profiel maken. U kunt een bestand importeren dat mobiele activeringscodes bevat die u van uw mobiele operator krijgt. Vervolgens kunt u deze profielen implementeren op uw Windows 10-apparaten met eSIM LTE, zoals de Surface Pro LTE en andere voor eSIM geschikte apparaten.

Controleer of uw [apparaten eSIM-profielen ondersteunen](https://support.microsoft.com/help/4020763/windows-10-use-esim-for-cellular-data).

Van toepassing op Windows 10 en hoger. 




<!-- 1806 start -->


### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS <!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; appbeveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Apparaatnalevingsbeleid maken met behulp van firewallinstellingen op macOS-apparaten <!-- 1497640 -->
Wanneer u een nieuw macOS-nalevingsbeleid maakt (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**  >  **Platform: macOS** > **Systeembeveiliging**), ziet u enkele nieuwe instellingen bij **Firewall**: 
- **Firewall**: configureer hoe binnenkomende verbindingen in uw omgeving worden verwerkt.
- **Binnenkomende verbindingen**: **blokkeer** alle binnenkomende verbindingen, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Deze instelling blokkeert ook alle services voor delen.
- **Verborgen modus**: u kunt de verborgen modus **inschakelen** om te voorkomen dat het apparaat reageert op peilverzoeken. Het apparaat reageert nog wel op binnenkomende verzoeken voor toegestane apps.

Van toepassing op: macOS 10.12 en hoger

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het starten en een time-out van een app <!-- 1506985 -->

Door een niet-biometrische wachtwoordcode te vereisen bij het starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Mobiele apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus-taalpakketten <!-- 1833450 -->
Als Intune-beheerder kunt extra talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in de Azure-portal **Microsoft Intune** > **Mobiele apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**.

### <a name="preview-a-new-user-experience-update-for-the-company-portal-website---2000968---"></a>Bekijk de nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968 -->
Op basis van feedback van klanten voegen we nieuwe functies toe aan de website van de bedrijfsportal/iOS-app-catalogus. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw Android-, iOS- en Windows-apparaten. Delen van de site, zoals apparaatdetails, feedback en ondersteuning, en apparaatoverzicht, krijgen een nieuw, modern, responsief ontwerp. U ziet ook:

- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers

De update is momenteel beschikbaar als preview-versie. U kunt zich aanmelden voor de preview-versie op http://aka.ms/webcpflighting


### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Uw implementaties van de Office 365 Pro Plus-app bewerken <!-- 2150145 -->
Als beheerder van Microsoft Intune hebt u meer mogelijkheden om de implementaties van de Office 365 Pro Plus-app te bewerken. Selecteer in de Azure-portal **Microsoft Intune** > **Mobiele apps** > **Apps**. Selecteer uw Office 365 Pro Plus-pakket in de lijst met apps.  

<!-- 1805 start -->

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het koud starten en een time-out van een app <!-- 1506985 --> 

Door een niet-biometrische wachtwoordcode te vereisen bij het koud starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Mobiele apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>App-toegang blokkeren op basis van niet-goedgekeurde apparaatleveranciers en -modellen <!-- 1425689 ! -->
De Intune-IT-beheerder kan via het Intune-app-beveiligingsbeleid een lijst laten opstellen met Android-fabrikanten en/of iOS-modellen. De IT-beheerder kan een met puntkomma's gescheiden lijst van fabrikanten voor Android-beleid en apparaatmodellen voor iOS-beleid verstrekken. Intune-app-beveiligingsbeleid is alleen van toepassing op Android en iOS. Er zijn twee acties die kunnen worden uitgevoerd op basis van deze lijst:
- Het blokkeren van toegang tot een app voor apparaten die niet in de lijst voorkomen.
- Of het selectief wissen van bedrijfsgegevens op apparaten die niet in de lijst voorkomen. 

De gebruiker heeft geen toegang tot de beoogde toepassing als niet is voldaan aan de vereisten van het beleid. Afhankelijk van de instellingen wordt de gebruiker geblokkeerd of worden zakelijke gegevens selectief in de app gewist. Op iOS-apparaten vereist deze functie dat toepassingen (d.w.z. WXP, Outlook, Managed Browser, Yammer) integreren met de Intune APP SDK opdat de minimale versie-instellingen worden afgedwongen voor de doeltoepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Op Android vereist deze functie de meest recente versie van de bedrijfsportal. 

Op apparaten van eindgebruikers moet de Intune-client actie ondernemen op basis van een eenvoudige overeenkomst met de tekenreeksen die zijn opgegeven in de Intune-blade Beveiligingsbeleid van toepassing. Dit is volledig afhankelijk van de waarde die het apparaat rapporteert. De IT-beheerder wordt dan ook aangemoedigd ervoor te zorgen dat het bedoelde gedrag correct is. Dit kan worden bereikt door deze instelling te testen voor verschillende fabrikanten en modellen en voor een kleine groep gebruikers. Selecteer in Microsoft Intune **Mobiele apps** > **App-beveiligingsbeleid** om app-beveiligingsbeleidsregels weer te geven en toe te voegen. Zie [Wat is een app-beveiligingsbeleid?](app-protection-policy.md) voor meer informatie over app-beveiligingsbeleid.


<!-- 1803 start -->

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Mogelijkheid om vereiste line-of-business-apps (LOB) te implementeren voor alle gebruikers op apparaten met Windows 10 Desktop <!-- 1627835 RS4 -->
Klanten kunnen vereiste Windows 10 line-of-business-apps implementeren om in apparaatcontexten te installeren. Hierdoor worden deze apps beschikbaar voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 Desktop-apparaten.

### <a name="updating-the-help-and-feedback-experience-on-company-portal-app-for-android---1631531---"></a>De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android bijwerken <!--1631531 -->

De Help- en Feedback-ervaring op de bedrijfsportal-app voor Android wordt bijgewerkt, zodat deze overeenkomt met de aanbevolen procedures voor Android-apps. De bedrijfsportal-app voor Android wordt in de komende maanden ook bijgewerkt om het menu-item **Help en Feedback** op te delen in afzonderlijke menu-items, namelijk **Help** en **Feedback verzenden**. Op de **Help**-pagina komt een sectie **Veelgestelde vragen** sectie en een knop **E-mailondersteuning** waarmee eindgebruikers logboeken naar Microsoft kunnen uploaden en e-mail kunnen verzenden naar bedrijfsondersteuning om het probleem te beschrijven. **Feedback verzenden** leidt de gebruiker door een standaard Microsoft-feedbackformulier, waarin de gebruiker wordt gevraagd een keuze te maken uit: "Ik vindt iets leuk", "Ik vind iets niet leuk" of "Ik heb een idee."

<!-- the following are present prior to 1801 -->

### <a name="app-protection-policies-----679615---"></a>Beleid voor app-beveiliging <!-- 679615 -->
Via het beveiligingsbeleid voor Intune-apps kunt u algemene standaardbeleidsregels maken om snel beveiliging in te schakelen voor alle gebruikers in de gehele tenant.

<!-- the following are present prior to 1711 -->

## <a name="notices"></a>Mededelingen

Er zijn geen actieve meldingen op dit moment.

### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.
