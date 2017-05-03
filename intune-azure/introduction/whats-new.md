---
title: Wat is er nieuw in Microsoft Intune Preview
titleSuffix: Intune Azure preview
description: Ontdekken wat er nieuw is in Intune Azure Preview
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/20/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 62dcb40ad5a7921c514a9d41da14b991e39f3bcd
ms.openlocfilehash: 9554a431859665312daf414f2c6cdfb47baf8547
ms.lasthandoff: 04/20/2017

---

# <a name="whats-new-in-the-microsoft-intune-preview"></a>Wat is er nieuw in Microsoft Intune Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Als de openbare preview-versie verder wordt ontwikkeld en er meer functies worden toegevoegd, wordt u hier op de hoogte gebracht.

> [!Note]
> De wijzigingen die op deze pagina zijn opgesomd voor Azure Portal Preview worden uitgerold. De wijzigingen zijn echter mogelijk niet meteen beschikbaar vanwege de manier waarop de Intune-service wordt bijgewerkt.  Verschillende onderdelen van de service moeten opeenvolgend worden bijgewerkt voordat de nieuwe functies van de portal beschikbaar zijn. U zult deze wijzigingen zien wanneer ze later deze maand worden uitgerold.

## <a name="april-2017"></a>April 2017

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Ondersteuning voor beheerde configuratieopties voor Android-apps <!-- 621621 -->

Android-apps in de Play Store die beheerde configuratieopties ondersteunen kunnen nu worden geconfigureerd door Intune.  Dankzij deze functie kan de IT-afdeling een lijst weergeven met de configuratiewaarden die door een app worden ondersteund, en kunnen die waarden worden geconfigureerd in een begeleide, eersteklas gebruikersinterface.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nieuw Android-beleid voor complexe pincodes <!-- 722069 -->

U kunt een verplicht type [wachtwoord](/intune-azure/configure-devices/device-restrictions-for-android#password) instellen op Numeriek complex in een Android-apparaatprofiel voor apparaten met Android 5.0 en hoger.  Met deze instelling voorkomt u dat gebruikers een pincode kiezen die herhalende of opeenvolgende cijfers bevat, zoals 1111 of 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Aanvullende ondersteuning voor Android for Work-apparaten

- **Wachtwoord- en werkprofieleninstellingen beheren** <!-- 612808 -->

  Met dit nieuwe Android for Work-apparaatbeperkingsbeleid kunt u uw wachtwoord- en werkprofielinstellingen beheren op de Android for Work-apparaten die u beheert.

- **Gegevens delen tussen werkprofielen en persoonlijke profielen toestaan** <!-- 1045102 -->

Dit werkprofiel voor Android for Work-apparaatbeperkingen heeft nieuwe opties waarmee u het delen van gegevens tussen werkprofielen en persoonlijke profielen kunt configureren.

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen beperken** <!-- 1046094 -->

  Er is nu een nieuw aangepast apparaatprofiel voor Android for Work-apparaten, waarmee u kunt instellen of het kopiëren en plakken tussen werk-apps en persoonlijke apps is toegestaan.

Zie voor meer informatie [Apparaatbeperkingen voor Android for Work](/intune-azure/configure-devices/device-restrictions-for-afw).

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>LOB-apps toewijzen aan iOS- en Android-apparaten <!-- 1057568 -->

U kunt nu line-of-business-apps (LOB) voor [iOS](/intune-azure/manage-apps/ios-lob-app) (IPA-bestanden) en [Android](/intune-azure/manage-apps/android-lob-app) (APK-bestanden) toewijzen aan gebruikers of apparaten.

###  <a name="new-device-policies-for-ios----723774-723815-723826-723830---"></a>Nieuw apparaatbeleid voor iOS <!-- 723774, 723815, 723826, 723830 -->

- **Apps op beginscherm**: u kunt instellen welke apps gebruikers zien op het [startscherm van hun iOS-apparaat](/intune-azure/configure-devices/home-screen-settings-for-ios). Dit beleid wijzigt de indeling van het beginscherm, maar implementeert geen apps die u hebt opgegeven maar die niet zijn geïnstalleerd.

- **Verbindingen met AirPrint-apparaten**: u kunt instellen met welke [AirPrint-apparaten](/intune-azure/configure-devices/air-print-settings-for-ios-and-macos) (netwerkprinters) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Verbindingen met AirPlay-apparaten**: u kunt bepalen met welke [AirPlay-apparaten](/intune-azure/configure-devices/airplay-settings-for-ios-devices) (zoals Apple TV) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Aangepast bericht vergrendelingsscherm**: U kunt een aangepast bericht configureren dat de gebruikers zien op het vergrendelingsscherm van hun iOS-apparaat. Dit bericht vervangt het standaardbericht op het vergrendelingsscherm. Zie [Beschikbare apparaatacties](/intune-azure/manage-devices/what-is#available-device-actions) voor meer informatie


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Pushmeldingen voor iOS-apps beperken <!-- 723767 -->

In een Intune-apparaatbeperkingsprofiel kunt u nu de volgende [meldingsinstellingen](/intune-azure/configure-devices/app-notification-settings-for-ios) voor iOS-apparaten configureren:

- Meldingen voor een opgegeven app volledig in- of uitschakelen.
- Meldingen voor een opgegeven app in- of uitschakelen in het berichtencentrum.
- Het type waarschuwing opgeven: **Geen**, **Banner** of **Modale waarschuwing**.
- Opgeven of badges zijn toegestaan voor deze app.
- Opgeven of meldingsgeluiden zijn toegestaan.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS-apps configureren voor autonome uitvoering in één-app-modus <!-- 737837 -->

U kunt nu een Intune-apparaatprofiel gebruiken om iOS-apparaten te configureren voor het uitvoeren van opgegeven apps in de [Autonome modus voor enkele toepassing](/intune-azure/configure-devices/device-restrictions-for-ios#autonomous-single-app-mode-supervised-only). Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld zodat alleen de betreffende app kan worden uitgevoerd. U kunt bijvoorbeeld een app configureren die de gebruikers een test laat uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Vertrouwde domeinen configureren voor e-mail en browsen op het web op iOS-apparaten <!-- 723765 -->

In een iOS-apparaatbeperkingsprofiel kunt u nu de volgende [domeininstellingen](/intune-azure/configure-devices/device-restrictions-for-ios#domains) configureren:

- **Niet-gemarkeerde e-maildomeinen**: e-mailberichten die de gebruiker verzendt of ontvangt die niet overeenkomen met de domeinen die u hier opgeeft, worden gemarkeerd als niet-vertrouwd.

- **Beheerde webdomeinen**: documenten die zijn gedownload via de URL's die u hier opgeeft, worden als beheerd beschouwd (alleen in Safari).  

- **Domeinen voor automatisch invullen van wachtwoorden in Safari**: gebruikers kunnen alleen wachtwoorden opslaan in Safari voor de URL’s die overeenkomen met de patronen die u hier opgeeft. Als u deze instelling wilt gebruiken, moet het apparaat in de supervisiemodus staan en niet zijn geconfigureerd voor meerdere gebruikers. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>VPP-apps beschikbaar in de iOS-bedrijfsportal <!-- 748782 -->

U kunt iOS-apps die zijn gekocht via het volume-aankoopprogramma toewijzen als **Beschikbaar** voor installatie door eindgebruikers. Eindgebruikers hebben een Apple Store-account nodig om de app te installeren.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>eBooks synchroniseren vanuit Apple VPP Store <!-- 800878 -->

U kunt nu met Intune [boeken synchroniseren](/intune-azure/manage-apps/ios-vpp-apps) die u hebt aangeschaft via het volume-aankoopprogramma van Apple en deze toewijzen aan gebruikers.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Beheer van meerdere gebruikers voor Samsung KNOX Standard-apparaten <!-- 971988 -->

Apparaten waarop Samsung KNOX Standard wordt uitgevoerd, bieden nu ondersteuning voor [beheer van meerdere gebruikers](/intune-azure/enroll-devices/enroll-android-and-knox-standard-devices) in Intune. Dit betekent dat eindgebruikers zich kunnen aan- en afmelden bij het apparaat met hun Azure Active Directory-referenties, en dat het apparaat centraal wordt beheerd, ongeacht of het wordt gebruikt of niet.  Wanneer eindgebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Aanvullende Windows 10-apparaatbeperkingsinstellingen <!-- 818566 -->

Er is ondersteuning toegevoegd voor aanvullende [Windows-apparaatbeperkingsinstellingen](/intune-azure/configure-devices/device-restrictions-for-windows-10), zoals aanvullende ondersteuning voor Edge, het aanpassen van het vergrendelingsscherm, het aanpassen van het startmenu, het instellen van de zoekfunctie van Windows Spotlight als achtergrondafbeelding en proxy-instellingen.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Ondersteuning voor meerdere gebruikers van Windows 10-makersupdate <!-- 822547 -->

Er is ondersteuning toegevoegd voor het [beheer van meerdere gebruikers](/intune-azure/enroll-devices/enroll-windows-devices) voor apparaten waarop de Windows 10-makersupdate wordt uitgevoerd en die zijn toegevoegd aan een Azure Active Directory-domein. Dit betekent dat wanneer verschillende standaardgebruikers zich aanmelden op het apparaat met hun Azure AD-referenties, ze de apps en beleidsregels ontvangen die zijn toegewezen aan hun gebruikersnaam. Gebruikers kunnen de bedrijfsportal op dit moment niet gebruiken voor selfservice scenario's zoals het installeren van apps.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start voor Windows 10-pc’s<!-- 1004830 -->

Er is nu een apparaatactie [Nieuwe start](/intune-azure/manage-devices/what-is#available-device-actions) voor Windows 10-pc’s beschikbaar.  Wanneer u deze actie uitvoert, worden alle apps die op de pc zijn geïnstalleerd verwijderd en wordt de pc automatisch bijgewerkt naar de laatste Windows-versie. Hiermee verwijdert u vooraf geïnstalleerde OEM-apps die vaak op nieuwe pc’s staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Aanvullende upgradepaden voor Windows 10 <!-- 903672 -->

U kunt nu een [versie-upgradebeleid maken om apparaten bij te werken](/intune-azure/configure-devices/how-to-configure-windows-10-edition-upgrade) naar de volgende aanvullende Windows 10-edities:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-apparaten bulksgewijs inschrijven <!-- 747607 -->

U kunt nu grote aantallen apparaten waarop de Windows 10-makersupdate wordt uitgevoerd toevoegen aan Azure Active Directory en Intune met Windows Configuration Designer (WCD). Als u [bulksgewijze MDM-registratie](/intune-azure/enroll-devices/bulk-enroll-windows) voor uw Azure AD-tenant wilt inschakelen, maakt u een inrichtingspakket waarmee apparaten worden toegevoegd aan uw Azure AD-tenant met Windows Configuration Designer. Vervolgens past u het pakket toe op apparaten die bedrijfseigendom zijn en die u bulksgewijs wilt registreren en beheren. Zodra het pakket is toegepast op de apparaten, worden deze toegevoegd aan Azure AD, ingeschreven bij Intune en zijn ze klaar voor aanmelding door uw Azure AD-gebruikers.  Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen beleid en de vereiste apps. Scenario’s voor Selfservice portal en bedrijfsportal worden momenteel niet ondersteund.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---"></a>Nieuwe MAM-instellingen voor pincode en beheerde opslaglocaties <!-- 581122, 736644 -->

Er zijn nu twee nieuwe app-instellingen beschikbaar voor het beheren van mobiele toepassingen:

- **App-pincode uitschakelen wanneer apparaatpincode wordt beheerd**: deze instelling detecteert of er een apparaatpincode aanwezig is op het ingeschreven apparaat. Als dat het geval is, wordt de app-pincode die wordt geactiveerd door het app-beveiligingsbeleid omzeild. Deze instelling zorgt ervoor dat gebruikers minder vaak een pincode hoeven in te voeren wanneer zij een beheerde mobiele toepassing openen op een ingeschreven apparaat. Deze functie is beschikbaar op Android en iOS.

- **Selecteer naar welke opslagservices bedrijfsgegevens kunnen worden opgeslagen**: hiermee kunt u opgeven welke opslaglocaties mogen worden gebruikt voor het opslaan van bedrijfsgegevens. Gebruikers kunnen alleen opslaan in de geselecteerde opslaglocatieservices, wat inhoudt dat de opslaglocatieservices die niet worden vermeld, zijn geblokkeerd.

  Lijst met ondersteunde opslaglocatieservices:

  - OneDrive
  - Zakelijke SharePoint Online
  - Lokale opslag

### <a name="help-desk-troubleshooting-portal----907448---"></a>Portal voor problemen oplossen van helpdesk<!-- 907448 -->

Met de nieuwe [Portal voor problemen oplossen](/intune-azure/manage-users/help-desk) kunnen helpdeskmedewerkers en Intune-beheerders de gebruikers en hun apparaten weergeven, en taken uitvoeren voor het oplossen van technische problemen met Intune.

## <a name="march-2017"></a>Maart 2017

### <a name="support-for-ios-lost-mode---431695--"></a>Ondersteuning voor iOS voor de modus Apparaat verloren<!--431695-->

Voor apparaten met iOS 9.3 en hoger is in Intune ondersteuning toegevoegd voor de **modus Apparaat verloren**. U kunt nu een apparaat vergrendelen om verder gebruik te voorkomen en een bericht en telefoonnummer weergeven op het vergrendelingsscherm van het apparaat.

De eindgebruiker kan het apparaat pas ontgrendeld wanneer een beheerder de modus Apparaat verloren heeft uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de actie **Apparaat zoeken** uitvoeren om de geografische locatie van het apparaat weer te geven op een kaart in de Intune-console.

Het apparaat moet een iOS-apparaat in bedrijfseigendom zijn, dat via DEP is ingeschreven en waarop de supervisiemodus is ingeschakeld.

Zie [Wat is Microsoft Intune-apparaatbeheer?](/intune-azure/manage-devices/what-is) voor meer informatie.

### <a name="improvements-to-device-actions-report---677150--"></a>Verbeteringen aan het rapport Apparaatacties <!--677150-->

Er zijn verbeteringen aangebracht aan het rapport Apparaatacties voor betere prestaties. Bovendien kunt u het rapport nu filteren op basis van status. U kunt het rapport bijvoorbeeld filteren zodat alleen de apparaatacties worden weergegeven die zijn voltooid.

### <a name="actions-for-non-compliance---730266--"></a>Acties voor niet-naleving <!--730266-->

**Acties voor niet-naleving** is een nieuwe functie van nalevingsbeleid waarmee u actie kunt ondernemen voor apparaten die niet meer compatibel zijn. U kunt een of meer acties opgeven, samen met de tijdsduur waarbinnen deze acties moeten plaatsvinden. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten een melding via e-mail sturen onmiddellijk nadat de compatibiliteit van de apparaten is opgeheven, of u kunt de toegang van niet-compatibele apparaten tot bedrijfsbronnen blokkeren na een respijtperiode van 3 dagen via voorwaardelijke toegang.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->

U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="assign-lob-apps-to-users-with-unenrolled-devices---748823--"></a>LOB-apps toewijzen aan gebruikers met niet-ingeschreven apparaten <!--748823-->

U kunt nu Line-Of-Business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten zijn ingeschreven bij Intune. Als een apparaat van een gebruiker niet is geregistreerd bij Intune, moet deze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app.

### <a name="new-compliance-reports---846671--"></a>Nieuwe nalevingsrapporten <!--846671-->

U hebt nu nalevingsrapporten die u informatie bieden over de naleving van apparaten in uw bedrijf. U kunt dan ook snel aan naleving gerelateerde problemen oplossen waar uw gebruikers mee te maken krijgen. U kunt informatie bekijken over

- De algemene nalevingsstatus van apparaten
- De nalevingsstatus voor een specifieke instelling
- De nalevingsstatus voor een specifiek beleid

U kunt deze rapporten ook gebruiken om in te zoomen op een specifiek appraat, om op die manier te bekijken welke instellingen en beleidsregels van invloed zijn op dat apparaat.

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.


## <a name="february-2017"></a>Februari 2017

### <a name="ability-to-restrict-mobile-device-enrollment---747600-795782--"></a>Mogelijkheid om de inschrijving van mobiele apparaten te beperken <!--747600, 795782-->
Er zijn in Intune nieuwe inschrijvingsbeperkingen toegevoegd die bepalen welke platforms voor mobiele apparaten kunnen worden ingeschreven. Intune onderscheidt platforms voor mobiele apparaten als iOS, Mac OS, Android, Windows en Windows Mobile.

* Een beperking voor de registratie van mobiele apparaten, betekent niet dat de PC-clientregistratie ook is beperkt.  
* Alleen voor iOS en Android geldt er een extra optie voor het blokkeren van de inschrijving van apparaten die in persoonlijk eigendom zijn.

Intune markeert alle nieuwe apparaten als persoonlijk, tenzij de IT-beheerder actie onderneemt om deze te markeren als bedrijfseigen, zoals uitgelegd in [dit artikel](https://docs.microsoft.com/en-us/intune/deploy-use/manage-corporate-owned-devices).

### <a name="view-all-actions-on-managed-devices---677150--"></a>Alle acties voor beheerde apparaten weergeven <!--677150-->
Er is een nieuw rapport __Apparaatacties__, waarin wordt weergegeven wie externe acties, zoals het herstellen van fabrieksinstellingen, op apparaten heeft uitgevoerd. In dit rapport wordt ook de status van de actie getoond. Zie [Wat is apparaatbeheer?](https://docs.microsoft.com/intune-azure/manage-devices/what-is).

### <a name="non-managed-devices-can-access-assigned-apps---664691--"></a>Niet-beheerde apparaten hebben toegang tot toegewezen apps <!--664691-->
Als onderdeel van de ontwerpwijzigingen op de bedrijfsportalwebsite kunnen iOS- en Android-gebruikers op hun niet-beheerde apparaten apps installeren die aan hen zijn toegewezen als 'beschikbaar zonder inschrijving'. Gebruikers kunnen zich met behulp van hun Intune-referenties aanmelden bij de bedrijfsportalwebsite en de lijst met aan hen toegewezen apps bekijken. De app-pakketten van de 'beschikbaar zonder inschrijving'-apps kunnen worden gedownload via de bedrijfsportalwebsite. Deze wijziging is niet van toepassing op apps die pas na inschrijving kunnen worden geïnstalleerd, omdat gebruikers wordt gevraagd hun apparaat in te schrijven als zij deze apps willen installeren.

### <a name="custom-app-categories---748805--"></a>Aangepaste app-categorieën <!--748805-->
U kunt nu categorieën maken, bewerken en toewijzen voor apps die u aan Intune toevoegt. Categorieën kunnen momenteel alleen worden opgegeven in het Engels.
Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="display-device-categories---814654--"></a>Apparaatcategorieën weergeven <!--814654-->
U kunt nu de apparaatcategorie als kolom in de lijst met apparaten weergeven. U kunt ook de categorie uit de sectie met eigenschappen van de apparaateigenschappenblade bewerken. Zie [Een app toevoegen aan Intune](/intune-azure/manage-apps/add-apps).

### <a name="configure-windows-update-for-business-settings---776716--"></a>Instellingen voor Windows Update voor bedrijven configureren.<!--776716-->

Windows as a Service is de nieuwe manier voor het aanbieden van updates voor Windows 10. Vanaf Windows 10 bevatten alle Upgrades van onderdelen en Kwaliteitsupdates de inhoud van alle voorgaande updates. Dit houdt in dat, als u de nieuwste update hebt geïnstalleerd, u zeker weet dat uw Windows 10-apparaten volledig zijn bijgewerkt. In tegenstelling tot eerdere versies van Windows, moet u nu de volledige update installeren in plaats van een onderdeel van een update.

Met Windows Update voor bedrijven kunt u updatebeheer vereenvoudigen, zodat u geen afzonderlijke updates voor groepen apparaten hoeft goed te keuren. U kunt nog steeds risico’s in uw omgeving beheren door een strategie voor update-implementatie te configureren. Windows Update zorgt ervoor dat updates op tijd worden geïnstalleerd. Microsoft Intune biedt de mogelijkheid update-instellingen op apparaten te configureren en biedt u de mogelijkheid de installatie van updates uit te stellen. Intune slaat de updates niet op, maar alleen de beleidstoewijzing voor de update. Apparaten hebben voor de updates rechtstreeks toegang tot Windows Update. Voor het configureren en beheren van **Windows 10-updateringen** wordt Intune gebruikt. Een updatering bevat een aantal instellingen waarin is geconfigureerd wanneer en hoe Windows 10-updates worden geïnstalleerd. Zie [Instellingen voor Windows Update voor bedrijven configureren](/intune-azure/configure-devices/how-to-configure-windows-update-for-business) voor meer informatie.

## <a name="january-2017"></a>Januari 2017

### <a name="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--"></a>Toewijzen van line-of-business-apps, ongeacht of apparaten al dan niet zijn geregistreerd <!--748823-->
U kunt nu line-of-business-apps uit de store toewijzen aan gebruikers, ongeacht of hun apparaten al dan niet zijn geregistreerd bij Intune. Als een apparaat van gebruikers niet is geregistreerd bij Intune, moeten ze daarvoor de bedrijfsportalwebsite gebruiken en niet de bedrijfsportal-app. Zie [Wat is app-beheer](/intune-azure/manage-apps/what-is-app-management).

### <a name="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them"></a>Oplossing voor het probleem waarbij iOS-apparaten inactief zijn of waarbij de beheerconsole er niet mee kan communiceren
Wanneer het contact tussen de apparaten van gebruikers en Intune verloren gaat, kunt u de gebruikers stappen voor probleemoplossing aandragen waarmee ze weer toegang krijgen tot de bedrijfsresources. Zie [Apparaten zijn inactief of de beheerconsole kan er niet mee communiceren](/intune-azure/enroll-devices/troubleshoot-device-enrollment#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## <a name="december-2016-initial-release"></a>December 2016 (oorspronkelijke versie)

### <a name="telecom-expense-management-integration-in-public-preview-of-azure-portal--747605--"></a>Integratie van onkostenbeheer voor telecom in de openbare preview-versie van Azure-portal<!--747605-->
We beginnen nu met preview-versies van de integratie met externe systemen voor onkostenbeheer voor telecom (TEM) in de Azure-portal. U kunt Intune gebruiken om limieten in te stellen voor gegevensgebruik, voor zowel nationaal als roaming. Hierbij beginnen we met [Saaswedo](http://www.saaswedo.com). Als u deze functie in uw proeftenant wilt inschakelen, neemt u [contact op met Microsoft-ondersteuning](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

- Apps uit een store op iOS-, Android- en Windows-apparaten implementeren en beheren
- LOB-apps (Line-Of-Business) op iOS-, Android- en Windows-apparaten implementeren en beheren
- Apps die zijn gekocht via het volume-aankoopprogramma, implementeren en beheren op iOS- en Windows-apparaten
- Web-apps implementeren en beheren op Android-, iOS- en Windows-apparaten
- Door iOS beheerde app-configuratieprofielen
- App-beveiligingsbeleid configureren en LOB-apps (Line-Of-Business) implementeren op apparaten die niet zijn geregistreerd met Intune
- VPN-profielen, VPN-, Wi-Fi-, e-mail- en certificaatprofielen per app
- Nalevingsbeleid
- Voorwaardelijke toegang voor Azure AD
- Voorwaardelijke toegang voor On-premises Exchange
- Apparaatinschrijving
- Op rollen gebaseerd toegangsbeheer

## <a name="deprecated-features-in-the-azure-portal"></a>Afgeschafte functies in Azure Portal

### <a name="support-for-row-by-row-review-of-hardware-identifiers"></a>Ondersteuning voor beoordeling van hardware-id's per rij
Azure Portal biedt geen ondersteuning voor de beoordeling van hardware-id's per rij voor IMEI-nummers en serienummers van Apple. U kunt in de klassieke Intune-console gegevens importeren uit een bestand met door komma's gescheiden waarden (CSV-bestand) en de bestaande gegevens voor afzonderlijke hardware-id's overschrijven. Azure Portal bevat één gestroomlijnde optie waarmee gegevens voor alle hardware-id's automatisch worden overschreven of nieuwe gegevens voor bestaande id's worden genegeerd.

#### <a name="how-this-affects-you"></a>Welke gevolgen heeft dit voor u
In Azure Portal kunt u niet per rij bepalen welke IMEI-apparaten (International Mobile Equipment Identity) moeten worden bijgewerkt. In de klassieke Intune-console blijft de ondersteuning voor deze functionaliteit gehandhaafd.

#### <a name="how-to-get-ready-for-this-change"></a>Hoe bereidt u zich voor op deze wijziging
Deze informatie wordt nu al verstrekt, zodat u uw ondersteuningsbeheerders van deze wijziging op de hoogte kunt brengen, als dit voor u van toepassing is. Deze wijziging valt samen met de overgang naar Azure Portal (naar verwachting in de eerste helft van 2017).


### <a name="support-for-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Ondersteuning voor de standaardprofielen voor de registratie van bedrijfsapparaten in Apple DEP
Azure Portal biedt geen ondersteuning voor het standaardprofiel voor de registratie van bedrijfsapparaten voor Apple DEP-apparaatserienummers (Device Enrollment Program). Deze functionaliteit, die beschikbaar is in de klassieke Intune-console, wordt stopgezet om het onbedoeld toewijzen van profielen te voorkomen. In Azure Portal worden aan serienummers die zijn gesynchroniseerd vanuit een Apple DEP-account, in eerste instantie geen profiel voor de registratie van bedrijfsapparaten toegewezen.

#### <a name="how-this-affects-you"></a>Welke gevolgen heeft dit voor u
U kunt in Azure Portal geen standaardprofielbeleid voor alle Apple-apparaten instellen. In de klassieke Intune-console blijft de ondersteuning voor deze functionaliteit gehandhaafd.

#### <a name="how-to-get-ready-for-this-change"></a>Hoe bereidt u zich voor op deze wijziging
Deze informatie wordt nu al verstrekt, zodat u uw ondersteuningsbeheerders van deze wijziging op de hoogte kunt brengen, als dit voor u van toepassing is. Deze wijziging valt samen met de overgang naar Azure Portal (naar verwachting in de eerste helft van 2017).

