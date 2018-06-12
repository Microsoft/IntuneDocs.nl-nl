---
title: Vroege editie
description: ''
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 95ad588b084319cd8a0f5f5c5d92da0e892eed50
ms.sourcegitcommit: 97b9f966f23895495b4c8a685f1397b78cc01d57
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34745040"
---
# <a name="the-early-edition-for-microsoft-intune---june-2018"></a>De vroege editie voor Microsoft Intune - juni 2018

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

<!-- 1806 start -->

### <a name="corporate-owned-single-use-cosu-support-for-android-devices----1630973---"></a>COSU-ondersteuning (corporate-owned, single use) voor Android-apparaten <!-- 1630973 -->

Intune ondersteunt maximaal beheerde, vergrendelde Android-apparaten in de kiosk-stijl. Hierdoor kunnen beheerders het gebruik van een apparaat verder vergrendelen tot een enkele app of een klein aantal apps en kan worden voorkomen dat gebruikers andere apps inschakelen of andere bewerkingen uitvoeren op het apparaat.

### <a name="macos-support-for-apple-device-enrollment-program----747651---"></a>macOS-ondersteuning voor het Apple Device Enrollment Program <!-- 747651 -->

Intune ondersteunt inschrijving van macOS-apparaten in het Apple Device Enrollment Program (DEP). Hiervoor doet u het volgende:

1. Wijs op deploy.apple.com macOS-serienummers toe aan een MDM-server.
2. Importeer de serienummers in Intune.
3. Maak een profiel voor het inschrijvingsprogramma dat specifiek is voor macOS-apparaten.

### <a name="google-name-changes-for-android-for-work-and-play-for-work---842873---"></a>Google-naamwijzigingen voor Android for Work en Play for Work <!--842873 -->
Intune werkt de Android for Work-terminologie bij om de wijzigingen in de Google-huisstijl te weerspiegelen.  De termen Android for Work en Play for Work worden niet meer gebruikt. Afhankelijk van de context wordt andere terminologie gebruikt:

- Android Enterprise verwijst naar de algemene moderne Android-beheerstack.
- Werkprofiel of Profieleigenaar verwijst naar BYOD-apparaten die worden beheerd met werkprofielen.
- Beheerde Google Play verwijst naar de Google App Store.

### <a name="monitor-ios--app-configuration-status-per-device----880037-eeready-eestaged---"></a>Configuratiestatus van een iOS-app per apparaat controleren <!-- 880037 eeready eestaged -->

Als Microsoft Intune-beheerder kunt u de configuratiestatus van iOS-apps voor elk beheerd apparaat controleren. Selecteer vanaf **Microsoft Intune** in Azure Portal de optie **Apparaten** > **Alle apparaten**. Selecteer in de lijst met beheerde apparaten een specifiek apparaat om een blade voor het apparaat weer te geven. Selecteer **App-configuratie** op de apparaatblade.  

### <a name="3rd-party-keyboards-can-be-blocked-by-app-settings-on-ios----1248481---"></a>Toetsenborden van derden kunnen worden geblokkeerd door APP-instellingen op iOS <!-- 1248481 -->
Op iOS-apparaten kunnen Intune-beheerders het gebruik blokkeren van toetsenborden van derden bij het benaderen van organisatiegegevens in door beleid beveiligde apps. Wanneer het Application Protection Policy (APP; appbeveiligingsbeleid) is ingesteld om toetsenborden van derden te blokkeren, ontvangt de gebruiker een bericht als hij de eerste keer met bedrijfsgegevens werkt met een toetsenbord van derden. Alle opties, behalve het systeemeigen toetsenbord, worden geblokkeerd en zijn niet zichtbaar voor apparaatgebruikers. Apparaatgebruikers zien het dialoogvenster slechts één keer. 

### <a name="create-device-compliance-policy-using-firewall-settings-on-macos-devices----1497640---"></a>Apparaatnalevingsbeleid maken met behulp van firewallinstellingen op macOS-apparaten <!-- 1497640 -->
Wanneer u een nieuw macOS-nalevingsbeleid maakt (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken**  >  **Platform: macOS** > **Systeembeveiliging**), ziet u enkele nieuwe instellingen bij **Firewall**: 
- **Firewall**: configureer hoe binnenkomende verbindingen in uw omgeving worden verwerkt.
- **Binnenkomende verbindingen**: **blokkeer** alle binnenkomende verbindingen, behalve de verbindingen die vereist zijn voor basisinternetservices, zoals DHCP, Bonjour en IPSec. Deze instelling blokkeert ook alle services voor delen.
- **Verborgen modus**: u kunt de verborgen modus **inschakelen** om te voorkomen dat het apparaat reageert op peilverzoeken. Het apparaat reageert nog wel op binnenkomende verzoeken voor toegestane apps.

Van toepassing op: macOS 10.12 en hoger

### <a name="use-samaccountname-as-the-account-username-for-email-profiles----1500307---"></a>Gebruik sAMAccountName als de accountgebruikersnaam voor e-mailprofielen <!-- 1500307 -->

U kunt de on-premises **sAMAccountName** gebruiken als de accountgebruikersnaam voor e-mailprofielen voor Android, iOS en Windows 10. U kunt ook het domein krijgen van het kenmerk `domain` of `ntdomain` in Azure Active Directory (Azure AD). Of geef een aangepast statisch domein op.

Om deze functie te gebruiken, moet u het kenmerk `sAMAccountName` van uw on-premises Active Directory-omgeving synchroniseren naar Azure AD.

Van toepassing op: Android, iOS, Windows 10 en hoger

### <a name="require-non-biometric-passcode-on-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het starten en een time-out van een app <!-- 1506985 -->

Door een niet-biometrische wachtwoordcode te vereisen bij het starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Mobiele apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

### <a name="selective-wipe-of-organizations-app-data----1507030---"></a>Selectief wissen van de app-gegevens van een organisatie <!-- 1507030 -->
Beheerders kunnen een selectieve wisbewerking van de gegevens van de organisatie als een nieuwe actie configureren wanneer niet wordt voldaan aan de voorwaarden van Application Protection Policies-toegangsinstellingen.  Dankzij deze functie kunnen beheerders gevoelige organisatiegegevens automatisch beveiligen en verwijderen uit toepassingen op basis van vooraf geconfigureerde criteria.

### <a name="revoking-an-ios-app-purchased-through-vpp----1777384---"></a>Een iOS-app intrekken die is aangeschaft via VPP <!-- 1777384 -->
Als Microsoft Intune-beheerder kunt u de licentie voor een geselecteerde iOS-app intrekken die is gekocht via het volume-aankoopprogramma (VPP). U kunt gebruikers waarschuwen wanneer een app niet meer aan hen is toegewezen. Als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen, moet u de toewijzingsactie wijzigen in **Verwijderen**. Het aantal geregenereerde licenties wordt weergegeven in het knooppunt **Gelicentieerde apps** in de workload **App** van Intune. Zie [iOS-apps beheren die zijn aangeschaft via een volume-aankoopprogramma met Microsoft Intune](vpp-apps-ios.md) voor meer informatie over iOS VPP-apps.

### <a name="office-365-pro-plus-language-packs----1833450---"></a>Office 365 Pro Plus-taalpakketten <!-- 1833450 -->
Als Intune-beheerder kunt extra talen implementeren voor Office 365 Pro Plus-apps die via Intune worden beheerd. De lijst met beschikbare talen bevat het taalpakket **Type** (kern, gedeeltelijk en spellingcontrole). Selecteer in de Azure-portal **Microsoft Intune** > **Mobiele apps** > **Apps** > **Toevoegen**. In de lijst **App-type** op de blade **App toevoegen** selecteert u **Windows 10** onder **Office 365-suite**. Selecteer **Talen** in de blade **Instellingen voor app-suite**.

### <a name="revoke-ios-vpp-app-license----1863797---"></a>iOS VPP-app-licentie intrekken <!-- 1863797 -->
Als beheerder kunt u een iOS VPP-app-licentie die is toegewezen aan een gebruiker of apparaat vrijmaken. Wanneer u een iOS VPP-app verwijdert, kunt u ook de app-licentie vrijmaken. U kunt vervolgens de app-licentie toewijzen aan een andere gebruiker of een ander apparaat. Zie [Apps beheren die zijn gekocht via het iOS-volumeaankoopprogramma in Microsoft Intune](vpp-apps-ios.md) voor meer informatie over iOS VPP-app-licenties.

### <a name="new-user-experience-update-for-the-company-portal-website---2000968---"></a>Nieuwe update van de gebruikerservaring voor de bedrijfsportalwebsite <!--2000968 -->
Op basis van feedback van klanten voegen we nieuwe functies toe aan de website van de bedrijfsportal. U zult een aanzienlijke verbetering ervaren wat betreft de bestaande functionaliteit en bruikbaarheid van uw Android-, iOS- en Windows-apparaten. Delen van de site, zoals apparaatdetails, feedback en ondersteuning, en apparaatoverzicht, krijgen een nieuw, modern, responsief ontwerp. U ziet ook:

- Gestroomlijnde werkstromen voor alle apparaatplatforms
- Verbeterde apparaat-id en inschrijvingsstromen
- Nuttigere foutberichten
- Toegankelijker taal, minder technische jargon
- Mogelijkheid om directe koppelingen naar apps te delen
- Verbeterde prestaties voor grote app-catalogi
- Beter toegankelijk voor alle gebruikers

### <a name="edit-your-office-365-pro-plus-app-deployments----2150145---"></a>Uw implementaties van de Office 365 Pro Plus-app bewerken <!-- 2150145 -->
Als beheerder van Microsoft Intune hebt u meer mogelijkheden om de implementaties van de Office 365 Pro Plus-app te bewerken. Selecteer in de Azure-portal **Microsoft Intune** > **Mobiele apps** > **Apps**. Selecteer uw Office 365 Pro Plus-pakket in de lijst met apps.  

### <a name="per-row-review-of-duplicate-corporate-device-identifiers-uploaded----2203794---"></a>Controle per rij van geüploade dubbele zakelijke apparaat-id's <!-- 2203794 -->
Tijdens het uploaden van zakelijke id's geeft Intune een lijst weer met dubbele waarden en hebt u de optie om de bestaande gegevens te vervangen of te behouden. Het rapport wordt weergegeven als er dubbele waarden zijn nadat u **Apparaatinschrijving** > **Zakelijke apparaat-id's** > **Id's toevoegen** hebt gekozen. 

### <a name="manually-add-corporate-device-identifiers----2203803---"></a>Zakelijke apparaat-id's handmatig toevoegen <!-- 2203803 -->
U kunt zakelijke apparaat-id's handmatig toevoegen. Kies **Apparaatinschrijving** > **Zakelijke apparaat-id’s** > **Toevoegen**.

### <a name="new-status-for-devices-in-device-configuration----2308882---"></a>Nieuwe status voor apparaten in apparaatconfiguratie <!-- 2308882 -->
In **Apparaatconfiguratie** > **Overzicht** worden de volgende nieuwe statussen toegevoegd:
- geslaagd
- fout
- conflict
- in behandeling
- niet van toepassing Er wordt ook een afbeelding weergegeven waarin het aantal apparaten van een ander platform wordt weergegeven. Als u bijvoorbeeld een iOS-profiel kijkt, laat de nieuwe tegel ook het aantal niet-iOS-apparaten zien die ook zijn toegewezen aan dit profiel. 

### <a name="device-compliance-supports-3rd-party-anti-virus-solutions----2325484---"></a>Apparaatcompatibiliteit ondersteunt antivirusoplossingen van derden <!-- 2325484 -->
Wanneer u een apparaatnalevingsbeleid? maakt (**Apparaatcompatibiliteit** > **Beleid** > **Beleid maken** > **Platform: Windows 10 en hoger** > **Instellingen** > **Systeembeveiliging**), komen enkele nieuwe opties voor **Apparaatbeveiliging** beschikbaar: 
- **Antivirussoftware**: als deze is ingesteld op **Vereisen**, kunt u de naleving controleren met behulp van antivirusoplossingen die zijn geregistreerd bij Windows Beveiligingscentrum, zoals Symantec. 
- **AntiSpyware**: als deze is ingesteld op **Vereisen**, kunt u naleving controleren met behulp van antispyware-oplossingen die zijn geregistreerd bij Windows Beveiligingscentrum, zoals Symantec. 

Van toepassing op Windows 10 en hoger 

<!-- 1805 start -->

### <a name="support-for-palo-alto-networks-globalprotect-vpn-profiles----1333680-eeready----"></a>Ondersteuning voor Palo Alto Networks GlobalProtect VPN-profielen <!-- 1333680 eeready ! -->

Met deze update kunt u Palo Alto Networks GlobalProtect kiezen als VPN-verbindingstype voor VPN-profielen in Intune (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Profieltype** > **VPN**). In deze versie worden de volgende platformen ondersteund: 

- iOS
- Windows 10

### <a name="set-compliance-by-device-location----851881----"></a>Naleving instellen per apparaatlocatie <!-- 851881 ! -->
In sommige situaties wilt u mogelijk de toegang beperken tot bedrijfsresources op een specifieke locatie, gedefinieerd door een netwerkverbinding. U kunt een nalevingsbeleid maken (**Apparaatnaleving** > **Locaties**) op basis van het IP-adres van het apparaat. Als het apparaat wordt verplaatst naar een locatie buiten het IP-bereik, heeft het apparaat geen toegang meer tot bedrijfsresources.

Is van toepassing op: Android-apparaten 6.0 en hoger, met de bijgewerkte Bedrijfsportal-app

### <a name="improved-troubleshooting-for-app-installation----928990---"></a>Verbeterde probleemoplossing voor app-installatie <!-- 928990 -->
Op apparaten die met Microsoft Intune MDM worden beheerd, mislukken app-installaties wel eens. Als deze apps niet kunnen worden geïnstalleerd, is het soms lastig om de reden van het probleem te achterhalen of om het probleem op te lossen. We brengen een openbare preview-versie uit van de functies voor het oplossen van problemen met apps. U ziet een nieuw knooppunt, **Beheerde apps**, onder elk apparaat. Hier ziet u de apps die via Intune MDM zijn geleverd. In het knooppunt ziet u een lijst met de installatiestatussen van de apps. Als u een bepaalde app selecteert, ziet u de probleemoplossingsweergave voor die app. In de probleemoplossingsweergave ziet u de gehele levenscyclus van de app, zoals wanneer de app is gemaakt, gewijzigd, gebruikt en geleverd aan een apparaat. En als installatie van de app niet is geslaagd, wordt de foutcode weergegeven en een informatief bericht over de oorzaak van de fout.

### <a name="require-non-biometric-passcode-on-cold-app-launch-and-timeout----1506985---"></a>Niet-biometrische wachtwoordcode vereisen bij het koud starten en een time-out van een app <!-- 1506985 --> 

Door een niet-biometrische wachtwoordcode te vereisen bij het koud starten van een app en na een door de beheerder opgegeven time-out, biedt Intune betere beveiliging voor apps die geschikt zijn voor Mobile Application Management (MAM) door het gebruik van biometrische identificatie voor toegang tot zakelijke gegevens te beperken. De instellingen hebben invloed op gebruikers die Touch ID (iOS), Face ID (iOS), Android Biometric of andere toekomstige biometrische verificatiemethoden gebruiken om toegang te krijgen tot voor APP/MAM geschikte toepassingen. Door deze instellingen hebben Intune-beheerders gedetailleerdere controle over gebruikerstoegang. Op deze manier wordt de kans kleiner dat een onjuiste gebruiker bedrijfsgegevens kan zien op een apparaat met meerdere vingerafdrukken of andere biometrische toegangsmethoden. Open **Microsoft Intune** in de Azure-Portal. Selecteer **Mobiele apps** > **App-beveiligingsbeleid** > **Een beleid toevoegen** > **Instellingen**. Ga voor specifieke instellingen naar de sectie **Toegang**.

### <a name="block-app-access-based-on-unapproved-device-vendors-and-models-----1425689----"></a>App-toegang blokkeren op basis van niet-goedgekeurde apparaatleveranciers en -modellen <!-- 1425689 ! -->
De Intune-IT-beheerder kan via het Intune-app-beveiligingsbeleid een lijst laten opstellen met Android-fabrikanten en/of iOS-modellen. De IT-beheerder kan een met puntkomma's gescheiden lijst van fabrikanten voor Android-beleid en apparaatmodellen voor iOS-beleid verstrekken. Intune-app-beveiligingsbeleid is alleen van toepassing op Android en iOS. Er zijn twee acties die kunnen worden uitgevoerd op basis van deze lijst:
- Het blokkeren van toegang tot een app voor apparaten die niet in de lijst voorkomen.
- Of het selectief wissen van bedrijfsgegevens op apparaten die niet in de lijst voorkomen. 

De gebruiker heeft geen toegang tot de beoogde toepassing als niet is voldaan aan de vereisten van het beleid. Afhankelijk van de instellingen wordt de gebruiker geblokkeerd of worden zakelijke gegevens selectief in de app gewist. Op iOS-apparaten vereist deze functie dat toepassingen (d.w.z. WXP, Outlook, Managed Browser, Yammer) integreren met de Intune APP SDK opdat de minimale versie-instellingen worden afgedwongen voor de doeltoepassingen. Deze integratie vindt doorlopend plaats en is afhankelijk van de specifieke toepassingsteams. Op Android vereist deze functie de meest recente versie van de bedrijfsportal. 

Op apparaten van eindgebruikers moet de Intune-client actie ondernemen op basis van een eenvoudige overeenkomst met de tekenreeksen die zijn opgegeven in de Intune-blade Beveiligingsbeleid van toepassing. Dit is volledig afhankelijk van de waarde die het apparaat rapporteert. De IT-beheerder wordt dan ook aangemoedigd ervoor te zorgen dat het bedoelde gedrag correct is. Dit kan worden bereikt door deze instelling te testen voor verschillende fabrikanten en modellen en voor een kleine groep gebruikers. Selecteer in Microsoft Intune **Mobiele apps** > **App-beveiligingsbeleid** om app-beveiligingsbeleidsregels weer te geven en toe te voegen. Zie [Wat is een app-beveiligingsbeleid?](app-protection-policy.md) voor meer informatie over app-beveiligingsbeleid.

### <a name="enable-kiosk-mode-on-windows-10-devices----1560072----"></a>Kioskmodus inschakelen op Windows 10-apparaten <!-- 1560072 ! -->
Op Windows 10-apparaten kunt u een configuratieprofiel maken en de kioskmodus inschakelen (**Apparaatconfiguratie** > **Profielen** > **Profiel maken**  >  **Windows 10** > **Apparaatbeperkingen** > **Kioskmodus**). In deze update is de naam van de instelling **Kiosk (preview)** gewijzigd in **Kiosk (verouderd)**. Het gebruik van **Kiosk (verouderd)** wordt niet meer aanbevolen maar de optie blijft nog werken tot de update van juli. **Kiosk (verouderd)** wordt vervangen door het nieuwe profieltype **Kiosk** (**Profiel maken** > **Windows 10** > **Kiosk (preview)**). Dit profiel bevat de instellingen voor het configureren van kiosken in Windows 10 RS4 en hoger.

Van toepassing op Windows 10 en hoger.

### <a name="retrieve-the-associated-app-user-model-id-aumid-for-microsoft-store-for-business-apps-in-kiosk-mode----1560077----"></a>De bijbehorende app-gebruikersmodel-id (AUMID) ophalen voor de Microsoft Store voor Bedrijven-apps in de kioskmodus <!-- 1560077 ! -->
Intune kan de app-gebruikersmodel-id's (AUMID's) voor Microsoft Store voor Bedrijven-apps (WSfB) ophalen voor een verbeterde configuratie van het kioskprofiel.

Raadpleeg [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune](windows-store-for-business.md) voor meer informatie over Microsoft Store voor Business-apps.

### <a name="access-actions-for-app-protection-policies----1483510-eeready---"></a>Acties voor het apps-beveiligingsbeleid weergeven <!-- 1483510 EEready -->
Over enige tijd kunt u het app-beveiligingsbeleid expliciet configureren voor het blokkeren van niet-compatibele apparaten, het wissen van gegevens op deze apparaten of het verzenden van waarschuwingen naar deze apparaten. Met de meest recente actie *Wissen* worden bedrijfsgegevens van een apparaat verwijderd. Als een wisbewerking wordt uitgevoerd, wordt de gebruiker van het apparaat geïnformeerd over de reden en over de stappen om de gegevens te herstellen. Voor sommige instellingen, zoals de minimale versie van het besturingssysteem, moet u meerdere acties toepassen, bijvoorbeeld blokkeren en wissen. Deze acties worden geactiveerd wanneer de app wordt gestart.

### <a name="new-inventory-information-for-windows-devices----1333569-eeready---"></a>Nieuwe inventarisgegevens voor Windows-apparaten <!-- 1333569 eeready -->

Voor Windows-apparaten zijn per apparaat de volgende inventarisgegevens beschikbaar op het tabblad **Hardware** (**Groepen** > **Alle mobiele apparaten** > **Apparaten** > kies het apparaat van de gebruiker > **eigenschappen weergeven** > **Hardware**):
- TPM
- Antivirus
- Antispyware
- Firewall
- UAC
- Accu
- Domeinnaam.

Zie de DeviceStatus-items in het artikel [DeviceStatus-CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/devicestatus-csp) voor meer informatie over hoe deze gegevens worden opgehaald door de CSP.

### <a name="intune-and-the-microsoft-edge-browser----1818969---"></a>Intune en de Microsoft Edge-browser <!-- 1818969 -->
De Microsoft Edge-browser voor mobiele apparaten (iOS en Android) biedt nu ondersteuning voor het app-beveiligingsbeleid van Intune. Gebruikers die zich in de Edge-browsertoepassing aanmelden met hun zakelijk Azure AD-account worden beveiligd door Intune. 

### <a name="new-languageregion-setting-when-configuring-oobe-for-autopilot----1821766---"></a>Nieuwe taal-/landinstelling wanneer u OOBE configureert voor AutoPilot <!-- 1821766 -->
Er is een nieuwe configuratie-instelling waarmee u tijdens de Out of Box Experience de taal en de regio voor AutoPilot-profielen kunt instellen.

### <a name="new-setting-for-configuring-device-keyboard----1821768---"></a>Nieuwe instelling voor het configureren van het apparaattoetsenbord <!-- 1821768 -->
Er is een nieuwe configuratie-instelling waarmee u tijdens de Out of Box Experience het toetsenbord voor AutoPilot-profielen kunt instellen.

### <a name="use-teamviewer-to-screen-share-ios-and-macos-devices----1985547---"></a>TeamViewer gebruiken voor het delen van schermen op iOS- en MacOS-apparaten <!-- 1985547 -->
Op dit moment kunt u TeamViewer gebruiken om op afstand [door Intune beheerde Android- en Windows-apparaten ](device-profile-android-teamviewer.md) te beheren.

Beheerders kunnen verbinding maken met TeamViewer en een sessie voor het delen van schermen starten met iOS- en MacOS-apparaten. iPhone-, iPad- en MacOS-gebruikers kunnen hun schermen live delen met andere pc's of mobiele apparaten. 

### <a name="device-profile-graphical-user-chart-is-back----2160133---"></a>De grafische gebruikersgrafiek van het apparaatprofiel is terug <!-- 2160133 -->
Bij het verbeteren van de aantallen die in de grafische gebruikersgrafiek van het apparaatprofiel (**Apparaatconfiguratie** > **Profielen** > selecteer een bestaand profiel > **Overzicht** ) worden weergegeven, was de grafische gebruikersgrafiek tijdelijk verwijderd.

In deze update is de grafische gebruikersgrafiek terug. Deze wordt weergegeven in de Azure Portal.

### <a name="assign-all-users-and-all-devices-as-scope-groups----2196803---"></a>Alle gebruikers en apparaten toewijzen als bereikgroepen <!-- 2196803 -->
U kunt alle gebruikers, alle apparaten en alle gebruikers en alle apparaten in bereikgroepen toewijzen. Kies hiervoor **Intune-rollen** > **Alle rollen** > **Beleid en profielbeheer** > **Toewijzingen**  > kies een toewijzing > **Bereik (groepen)**.

### <a name="autopilot-profiles-moving-to-group-targeting----1877935---"></a>AutoPilot-profielen verplaatst naar de groep met <!-- 1877935 -->
Momenteel kunnen AutoPilot-implementatieprofielen worden toegewezen aan geselecteerde apparaten. Wanneer deze functie beschikbaar is, gaat u als volgt te werk om deze profielen toe te wijzen:
- Maak (Azure AD-)groepen met AutoPilot-apparaten
- Wijs de gewenste profielen toe aan een Azure AD-groep. Het AutoPilot-profiel wordt nu toegewezen aan AutoPilot-apparaten in die groep.

### <a name="management-name-field-will-be-editable----1875989---"></a>Het veld Managementnaam kan worden bewerkt <!-- 1875989 -->
U kunt het veld met de managementnaam bewerken op de blade **Eigenschappen** van een apparaat. Als u dit veld wilt bewerken, kiest u **Apparaten** > **Alle apparaten** > kies het apparaat > **Eigenschappen**. U kunt het veld Managementnaam gebruiken om een apparaat op unieke wijze te identificeren.

<!-- 1804 start -->

### <a name="additions-to-local-device-security-options-settings----1403702---"></a>Toevoegingen aan instellingen voor de beveiligingsopties van lokale apparaten <!-- 1403702 -->
U kunt aanvullende instellingen voor de beveiligingsopties van lokale apparaten voor Windows 10-apparaten configureren. Extra instellingen zijn beschikbaar voor Microsoft Network Client, Microsoft-netwerkserver, toegang tot het netwerk en beveiliging en interactief aanmelden. U vindt deze instellingen in de Endpoint Protection-categorie wanneer u een configuratiebeleid voor Windows 10-apparaten maakt.

### <a name="rules-for-removing-devices----1609459---"></a>Regels voor het verwijderen van apparaten <!-- 1609459 -->
Er zijn nieuwe regels beschikbaar waarmee u automatisch apparaten kunt verwijderen die een aantal dagen niet zijn ingecheckt. U kunt dit aantal instellen. Ga naar het deelvenster **Intune**, selecteer **Apparaten** en selecteer vervolgens **Regels voor het verwijderen van apparaten** om de nieuwe regel te zien.

### <a name="prevent-consumer-apps-and-experiences-on-windows-10-enterprise-rs4-autopilot-devices---1621980---"></a>De installatie van consumenten-apps en -ervaringen op Windows 10 Enterprise RS4 Autopilot-apparaten voorkomen<!-- 1621980 -->
U kunt voorkomen dat consumenten-apps en -ervaringen op uw apparaten met Windows 10 Enterprise RS4 AutoPilot kunnen worden geïnstalleerd. Ga voor deze functie naar **Intune** > **Apparaatinschrijving** > **Windows-inschrijving** > **Windows AutoPilot-profielen** > **Nieuwe maken** > **Inschrijvingsinstellingen**. 

<!-- 1803 start -->

#### <a name="multiple-exchange-connector-support----2070451---"></a>Ondersteuning voor meerdere Exchange Connectors <!-- 2070451 -->

U bent niet langer beperkt tot één Microsoft Intune Exchange Connector per tenant. Intune ondersteunt meerdere Exchange Connectors, zodat u voorwaardelijke toegang van Intune kunt instellen met meerdere on-premises Exchange-organisaties.

Met een on-premises Exchange Connector voor Intune kunt u apparaattoegang tot uw on-premises Exchange-postvakken beheren op basis van of een apparaat is ingeschreven bij Intune en voldoet aan het Intune-nalevingsbeleid voor apparaten. Als u een connector wilt instellen, downloadt u de on-premises Exchange Connector voor Intune vanaf Azure Portal en installeert u deze op een server in uw Exchange-organisatie. Kies op het Microsoft Intune-dashboard **On-premises toegang** en kies vervolgens onder **Installatie** de optie **Exchange ActiveSync-connector**. Download de on-premises Exchange Connector en installeer deze op een server in uw Exchange-organisatie. Nu u niet meer beperkt bent tot één Exchange Connector per tenant, kunt u, als u extra Exchange-organisaties hebt, dit zelfde proces volgen om een connector te downloaden en installeren voor elke extra Exchange-organisatie.

### <a name="ability-to-deploy-required-line-of-business-lob-apps-to-all-users-on-windows-10-desktop-devices----1627835-rs4---"></a>Mogelijkheid om vereiste line-of-business-apps (LOB) te implementeren voor alle gebruikers op apparaten met Windows 10 Desktop <!-- 1627835 RS4 -->
Klanten kunnen vereiste Windows 10 line-of-business-apps implementeren om in apparaatcontexten te installeren. Hierdoor worden deze apps beschikbaar voor alle gebruikers op het apparaat. Dit is alleen van toepassing op Windows 10 Desktop-apparaten.

### <a name="company-portal-enrollment-improved----1874230--"></a>Inschrijving bedrijfsportal verbeterd <!-- 1874230-->
Gebruikers die een apparaat inschrijven via de bedrijfsportal op Windows 10 build 1703 en hoger, kunnen de eerste stap van de inschrijving voltooien zonder de app te verlaten.

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



