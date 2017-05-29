---
title: Vroege editie | Microsoft Docs
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 249a902e6e10f799dcff4e1c46da90cd62f2c125
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="the-early-edition-for-microsoft-intune---may-2017"></a>De vroege editie voor Microsoft Intune - mei 2017

De **Vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
> De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Ondersteuning voor eenmalige aanmelding in bedrijfsportal-app voor iOS voor Outlook voor iOS <!--834012-->

Gebruikers hoeven zich niet langer aan te melden bij de Outlook-app als ze op hetzelfde apparaat en met hetzelfde account zijn aangemeld bij de bedrijfsportal-app voor iOS. Wanneer gebruikers de Outlook-app starten, kunnen ze hun account selecteren en worden ze automatisch aangemeld. In de toekomst wordt deze functionaliteit ook toegevoegd aan andere Microsoft-apps.

### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Verbeterde melding voor Samsung KNOX-opstartpincodes<!--1087143-->

Als eindgebruikers een opstartpincode op Samsung KNOX-apparaten moeten instellen om te voldoen aan de versleuteling, wordt er een melding aan eindgebruikers weergegeven. Wanneer eindgebruikers op deze melding tikken, worden ze omgeleid naar de exacte plaats in de app Instellingen.  Voorheen werd de eindgebruiker omgeleid naar het scherm voor het wijzigen van het wachtwoord.

### <a name="promoting-the-most-current-version-of-the-company-portal-for-android---1098661--"></a>Promotie van de meest recente versie van de bedrijfsportal voor Android <!--1098661-->

Eindgebruikers krijgen een in-app-melding in het meldingenscherm van de app te zien wanneer een nieuwe aanbevolen versie van de bedrijfsportal-app voor Android is uitgebracht. In deze melding worden gebruikers geïnformeerd dat er een update van bedrijfsportal beschikbaar is. Als u op de melding tikt, wordt er een webpagina geopend met een lijst van beschikbare app stores waar de bijgewerkte versie kan worden gedownload. 

### <a name="improvements-to-app-syncing-with-windows-10-creators-update----676505---"></a>Verbeterde synchronisatie van apps met Windows 10-makersupdate <!-- 676505 -->

De bedrijfsportal voor Windows 10 voert automatisch een synchronisatie uit voor app-installatieaanvragen voor apparaten met Windows 10-makersupdate (1704). Hierdoor is de kans aanzienlijk kleiner dat app-installaties worden gestopt tijdens de status Synchronisatie in behandeling. Daarnaast kunnen gebruikers handmatig een synchronisatie uitvoeren vanuit de app. 

De bedrijfsportal voor Windows 10 bevat ook een vernieuwingsknop waarmee de gebruiker zo nodig de inhoud in de app kan vernieuwen. 

## <a name="notices"></a>Mededelingen

### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple vereist updates voor Application Transport Security <!--748318-->

Apple heeft aangekondigd dat vanaf het voorjaar van 2017 specifieke vereisten gaan gelden voor Application Transport Security (ATS). ATS wordt gebruikt om betere beveiliging af te dwingen voor alle app-communicatie die verloopt via HTTPS. Deze wijziging heeft gevolgen voor Intune-klanten die de bedrijfsportal-app gebruiken op iOS. Bekijk ons [Intune-ondersteuningsblog](https://aka.ms/compportalats) voor meer informatie.

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Rechtstreekse toegang tot Apple-scenario's voor inschrijving <!--951869-->

Voor Intune-accounts die na januari 2017 zijn gemaakt, heeft Intune rechtstreekse toegang ingeschakeld tot Apple-inschrijvingsscenario's. Hiervoor is de werkstroom voor het inschrijven van apparaten gebruikt in de Azure Preview Portal. Voorheen was de Apple-inschrijvingspreview alleen toegankelijk via koppelingen in de klassieke Intune-portal. Intune-accounts die vóór januari 2017 zijn gemaakt, moeten eenmalig worden gemigreerd om de functies in Azure beschikbaar te maken. De planning voor de migratie is nog niet aangekondigd, maar de informatie wordt zo snel mogelijk beschikbaar gemaakt. Het wordt aangeraden om een testaccount te maken om de nieuwe ervaring te testen, als u met uw bestaande account geen toegang hebt tot de preview.

### <a name="whats-coming-for-appx-in-intune-on-azure----1000270---"></a>Binnenkort in Appx in Intune op Azure <!-- 1000270 -->

Als onderdeel van de migratie naar Intune op Azure, worden de volgende wijzigingen aangebracht in appx:

1. Er wordt een nieuw type appx-app toegevoegd in de klassieke Intune-console, die alleen kan worden geïmplementeerd op bij MDM ingeschreven apparaten.
2. Het bestaande appx-app-type wordt alleen nog gebruikt voor pc’s die worden beheerd via de Intune-pc-agent.
3. Alle bestaande appx’s worden geconverteerd naar MDM-appx’s bij de migratie.

Dit heeft geen gevolgen voor uw bestaande implementaties op apparaten die worden beheerd door de Intune-pc-agent. Na de migratie kunt u die gemigreerde appx’s echter niet implementeren op nieuwe apparaten die worden beheerd door de Intune-pc-agent en waarop de appx’s eerder niet waren gericht.

Na de migratie moet u de appx opnieuw uploaden als een pc-appx, als u deze wilt implementeren op nieuwe pc’s. Zie [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-wijzigingen in Intune op Azure) op het blog van het Intune-ondersteuningsteam voor meer informatie.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](https://docs.microsoft.com/intune/what-is-intune) raadplegen.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Ondersteuning voor beheerde configuratieopties voor Android-apps <!-- 621621 -->

U kunt nu Android-apps in de Play Store configureren die ondersteuning bieden voor beheerde configuratieopties.  Dankzij deze functie kunt u een lijst weergeven met de configuratiewaarden die door een app worden ondersteund, en kunnen die waarden worden geconfigureerd in een begeleide, eersteklas gebruikersinterface.

### <a name="remote-assistance-for-android-devices----675418---"></a>Hulp op afstand voor Android-apparaten <!-- 675418 -->

Intune werkt met de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software zodat u uw gebruikers met Android-apparaten hulp op afstand kunt bieden.

### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Apparaatmachtigingen voor Android for Work-apps vooraf configureren<!-- 621614 -->

Voor apps die worden geïmplementeerd voor Android for Work-apparaatwerkprofielen, kunt u de machtigingsstatus configureren voor afzonderlijke apps. Android-apps die apparaatmachtigingen vereisen, zoals voor toegang tot uw locatie of de apparaatcamera, vragen gebruikers de machtiging te accepteren of te weigeren.  Als een app bijvoorbeeld gebruikmaakt van de microfoon van het apparaat, wordt de gebruiker gevraagd de app toestemming te verlenen voor het gebruik van de microfoon. Met deze functie kunt u namen de eindgebruiker machtigingen definiëren.  De beheerder kan machtigingen als volgt configureren:

- Automatisch weigeren zonder de gebruiker hiervan op de hoogte te stellen
- Automatisch goedkeuren zonder de gebruiker hiervan op de hoogte te stellen
- De gebruiker vragen om de machtiging te accepteren of te weigeren

### <a name="define-app-specific-pin-for-android-for-work-devices---728976--"></a>Een app-specifieke pincode definiëren voor Android for Work-apparaten <!--728976-->

U kunt een wachtwoordcodebeleid definiëren dat alleen van toepassing is op apps in het werkprofiel voor apparaten met Android 7.0 en hoger die worden beheerd als een Android for Work-apparaat.  Opties zijn onder andere:

- Alleen een apparaatbreed wachtwoordcodebeleid definiëren: dit is de wachtwoordcode die de eindgebruiker moet gebruiken om het hele apparaat te ontgrendelen.
- Alleen een wachtwoordcodebeleid voor een werkprofiel definiëren: telkens wanneer eindgebruikers een app in het werkprofiel openen, worden ze gevraagd een wachtwoordcode in te voeren.
- Zowel een apparaat- als een werkprofielbeleid definiëren: de IT-afdeling kan verschillende sterktes voor de wachtwoordcodes in het beleid voor apparaten en het beleid voor werkprofielen definiëren (bijvoorbeeld een pincode van vier cijfers om het apparaat te ontgrendelen, maar een pincode van zes cijfers 6 om een werk-app te openen).

>[!NOTE]
> Dit is alleen beschikbaar in Android 7.0 en later.  De eindgebruiker heeft standaard de mogelijkheid om de twee afzonderlijk gedefinieerde pincodes te gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee.

### <a name="manage-password-and-other-android-for-work-settings---1102534--"></a>Wachtwoord- en andere Android for Work-instellingen beheren <!--1102534-->

Er is een nieuw restrictiebeleid voor Android for Work-apparaten toegevoegd, waarmee u wachtwoord- en werkprofielinstellingen kunt beheren op de Android for Work-apparaten.

###  <a name="new-web-content-filter-policy-for-ios-devices----723832---"></a>Nieuw filterbeleid voor webinhoud op iOS-apparaten <!-- 723832 -->

U kunt bepalen welke websites de gebruikers van iOS-apparaten kunnen bezoeken met een van de volgende twee methoden:

  - Toegestane en geblokkeerde URL’s toevoegen met het ingebouwde webinhoudsfilter van Apple.
  - Alleen opgegeven websites toestaan voor de Safari-browser. Voor elke website die u opgeeft wordt een bladwijzer gemaakt in Safari.

### <a name="apple-school-manager-asm-support---748864--"></a>Ondersteuning voor Apple School Manager (ASM)<!--748864-->

Intune ondersteunt het gebruik van Apple School Manager (ASM) in plaats van Apple Device Enrollment Program voor een out-of-box-registratie van iOS-apparaten. Onboarding van ASM is vereist om de app Classroom voor gedeelde iPads te kunnen gebruiken en om gegevens via Microsoft School Data Sync (SDS) te kunnen synchroniseren van ASM naar Azure Active Directory.  

### <a name="shared-ipad-support---770395-1044681---"></a>Ondersteuning voor Gedeelde iPad <!--770395, 1044681 -->

Intune biedt ondersteuning voor het configureren van de modus Gedeelde iPad in het registratieprofiel van Apple Device Enrollment Program of Apple School Manager. Met deze instellingen kunnen meerdere beheerde Apple-id's bij hetzelfde apparaat worden aangemeld.

Daarnaast wordt ook de ondersteuning voor het beheren van de iOS Classroom-app uitgebreid naar studenten die zich met hun beheerde Apple-id aanmelden bij gedeelde iPads.

### <a name="new-windows-device-restriction-settings---978585--"></a>Nieuwe beperkingsinstellingen voor Windows-apparaten<!--978585-->

Er worden instellingen toegevoegd aan het beperkingsprofiel voor Windows-apparaten. Hiermee worden zaken als draadloze beeldschermen, apparaatdetectie, het schakelen tussen taken en simkaartfoutberichten beheerd.

### <a name="office-365-proplus-app-available-for-windows-10-devices---1121362--"></a>De Office 365 ProPlus-app is beschikbaar voor Windows 10-apparaten <!--1121362-->

Het nieuwe type Office 365 ProPlus-app wordt toegevoegd. Hiermee kunt u eenvoudig Office 365 ProPlus-apps aan Windows 10-apparaten toewijzen. Daarnaast kunt u Microsoft Project en Microsoft Visio installeren als u hier licenties voor hebt. De gewenste apps worden gebundeld en worden als één app weergegeven in de lijst met apps in de Intune-console.

### <a name="new-allowblock-list-for-the-managed-browser---682960--"></a>Nieuwe acceptatie- of blokkeringslijst voor Managed Browser <!--682960-->

U kunt de acceptatie-/blokkeringslijst van domeinen en URL's voor Managed Browser configureren via de Intune Application Configuration-instellingen in Azure Portal. Deze lijst kan altijd voor Managed Browser worden geconfigureerd, ongeacht of de lijst wordt gebruikt op een beheerd of onbeheerd apparaat.

### <a name="new-app-configuration-capabilities----677969---"></a>Nieuwe mogelijkheden voor het configureren van apps<!-- 677969 -->

Dit onderdeel is gelijk aan MDM-app-configuratie (Mobile Device Management). Het biedt beheerders de mogelijkheid meer app-configuratiewaarden toe te passen dan alleen de app-configuratiewaarden die beschikbaar zijn via het app-beveiligingsbeleid in MAM zonder registratiekanaal.

### <a name="new-app-protection-policies-conditions-for-mam---679864--"></a>Nieuwe beleidsvoorwaarden voor MAM met betrekking tot de beveiliging van apps<!--679864-->

U kunt een vereiste voor MAM instellen zonder gebruikers te registreren via de beheerconsole. Hiermee kunt u het volgende afdwingen:

- Minimumversie van de toepassing
- Minimumversie van het besturingssysteem
- Minimumversie van de SDK voor de Intune-app van de doeltoepassing (alleen iOS)

Deze functie is beschikbaar op Android en iOS. Intune ondersteunt het afdwingen van een minimumversie voor besturingssystemen, toepassingen en de SDK voor de Intune-app. Voor iOS geldt dat toepassingen met een geïntegreerde SDK ook een minimumversie kunnen afdwingen op SDK-niveau.

De gebruiker heeft geen toegang tot de betreffende toepassing als niet aan de minimale vereisten van het app-beveiligingsbeleid wordt voldaan op de hierboven genoemde drie verschillende niveaus. Op dit moment kan de gebruiker kan het account (voor toepassingen met meerdere identiteiten) verwijderen, de toepassing sluiten en/of de versie van het besturingssysteem of de toepassing bijwerken om aan de vereiste te voldoen.

Daarnaast kunt u aanvullende instellingen via de beheerconsole configureren om een niet-blokkerende melding te verstrekken waarin de gebruiker wordt aanbevolen een upgrade voor het besturingssysteem of de toepassing uit te voeren. Deze melding kan worden gesloten en de toepassing kan gewoon worden gebruikt.

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Wijzig uw MDM-instantie zonder de registratie van beheerde apparaten ongedaan te maken <!--1103950-->

U kunt uw MDM-instantie wijzigen zonder dat u contact hoeft op te nemen met Microsoft Ondersteuning en zonder dat u de registratie van bestaande beheerde apparaten ongedaan hoeft te maken om ze vervolgens opnieuw te registreren. In de Configuration Manager-console kunt u uw MDM-instantie wijzigen van Ingesteld op Configuration Manager (hybride) naar Microsoft Intune (zelfstandig) of vice versa.


### <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.

