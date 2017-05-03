---
title: Vroege editie | Microsoft Docs
description: 
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f49650f4-31fa-406c-a4da-d8c9a4a8384d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: cacampbell
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 5f172290d493717308446c4f9e2313a03ba8f3aa
ms.openlocfilehash: d7f25657fc7cfb9298809f76f198810718e58c39
ms.lasthandoff: 04/27/2017


---


# <a name="the-early-edition-for-microsoft-intune---april-2017"></a>De vroege editie voor Microsoft Intune - april 2017

De **Vroege editie** bevat een lijst met functies die worden toegevoegd aan toekomstige releases van Microsoft Intune. Deze informatie wordt in zeer beperkte mate onder geheimhoudingsverklaring verstrekt en kan worden gewijzigd. Sommige functies die hier worden vermeld, zullen mogelijk niet beschikbaar zijn op de sluitingsdatum en worden mogelijk beschikbaar gesteld in een latere release. Andere functies worden getest in een proefversie, zodat we zeker weten dat ze in gebruik kunnen worden genomen. Neem bij vragen contact op met uw contactpersoon voor Intune/projectmanagement.

Deze pagina wordt regelmatig bijgewerkt. Controleer op andere updates.

> [!Note]
> De volgende wijzigingen worden momenteel ontwikkeld voor Intune. Al deze functies worden uiteindelijk ondersteund voor implementaties voor hybride klanten (Configuration Manager met Intune). Bekijk voor meer informatie over nieuwe hybride functies onze [Wat is er nieuw-pagina voor hybride](https://docs.microsoft.com/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).

## <a name="new-capabilities"></a>Nieuwe mogelijkheden

### <a name="improved-app-install-status-for-the-windows-10-company-portal-app---676495--"></a>Verbeterde app-installatiestatus voor de Windows 10-bedrijfsportal-app <!--676495-->

De Windows 10-bedrijfsportal-app toont nu een voortgangsbalk voor de installatie van alle moderne apps, wanneer de installatie is gestart vanuit de bedrijfsportal. U kunt het nieuwe statusbericht voor de bedrijfsportal-app voor Windows 10 zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-in-intune-app-ui.md)

### <a name="improved-status-messaging-in-the-company-portal-app-for-ios---744866--"></a>Verbeterde statusberichten in de bedrijfsportal-app voor iOS <!--744866-->

Er worden nieuwe, specifiekere foutberichten weergegeven in de bedrijfsportal-app voor iOS, die meer toegankelijke informatie bieden over wat er gebeurt op apparaten. Deze foutsituaties maakten eerder deel uit van een algemeen foutbericht met de titel “Bedrijfsportal is tijdelijk niet beschikbaar”. Als een gebruiker nu de bedrijfsportal-app in iOS opent zonder internetverbinding, wordt er een permanente statusbalk weergegeven op de startpagina met de tekst “Geen internetverbinding”.

### <a name="myapps-available-for-managed-browser---822308-822303--"></a>MyApps beschikbaar voor Managed Browser <!--822308, 822303-->

Betere ondersteuning voor Microsoft MyApps in de Managed Browser. Gebruikers van Managed Browser die niet hoeven te worden beheerd gaan direct naar de MyApps-service, waar ze toegang hebben tot hun door de beheerder beschikbaar gestelde SaaS-apps. Gebruikers die wel moeten worden beheerd door Intune blijven MyApps gebruiken via de ingebouwde bladwijzer in Managed Browser.

### <a name="new-icons-for-the-managed-browser-and-the-company-portal---918433-918431--"></a>Nieuwe pictogrammen voor de Managed Browser en bedrijfsportal <!--918433, 918431-->

Zowel de Android- als iOS-versie van de Managed Browser heeft een nieuw pictogram. Dit nieuwe pictogram bevat het bijgewerkte Intune-logo, om het consistent te maken met de andere apps in Enterprise Mobility + Security (EM+S). U kunt het nieuwe pictogram voor de Managed Browser zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-in-intune-app-ui.md)

De pictogrammen voor de Android-, iOS- en Windows-versies van de app in de bedrijfsportal worden ook vernieuwd, voor meer consistentie met de andere apps in EM+S. Deze pictogrammen worden in de periode van april tot eind mei geleidelijk in gebruik genomen op de verschillende platformen.

### <a name="single-sign-on-support-from-the-company-portal-for-ios-to-outlook-for-ios---834012--"></a>Ondersteuning voor eenmalige aanmelding in bedrijfsportal-app voor iOS voor Outlook voor iOS <!--834012-->

Gebruikers hoeven zich niet langer aan te melden bij de Outlook-app als ze op hetzelfde apparaat en met hetzelfde account zijn aangemeld bij de bedrijfsportal-app voor iOS. Wanneer gebruikers de Outlook-app starten, kunnen ze hun account selecteren en worden ze automatisch aangemeld. In de toekomst wordt deze functionaliteit ook toegevoegd aan andere Microsoft-apps.

### <a name="sign-in-progress-indicator-in-android-company-portal---953374--"></a>Voortgangsindicator voor aanmelden bij Android-bedrijfsportal <!--953374-->

De Android-bedrijfsportal-app is bijgewerkt met een voortgangsindicator voor het aanmelden wanneer de gebruiker de app opent of hervat. De indicator geeft de verschillende statussen weer, beginnend bij ‘Verbinden...’, gevolgd door ‘Aanmelden...’ en ‘Beveiligingseisen controleren...’, voordat de gebruiker de app kan gebruiken. U kunt de nieuwe schermen voor de bedrijfsportal-app voor Android zien op de [pagina Wat is er nieuw in de gebruikersinterface van de Intune-app?](whats-new-in-intune-app-ui.md)


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

#### <a name="how-does-this-affect-me"></a>Wat betekent dit voor mij?

Dit heeft geen gevolgen voor uw bestaande implementaties op apparaten die worden beheerd door de Intune-pc-agent. Na de migratie kunt u die gemigreerde appx’s echter niet implementeren op nieuwe apparaten die worden beheerd door de Intune-pc-agent en waarop de appx’s eerder niet waren gericht.

#### <a name="what-action-do-i-need-to-take"></a>Wat moet ik doen?

Na de migratie moet u de appx opnieuw uploaden als een pc-appx, als u deze wilt implementeren op nieuwe pc’s. Zie [Appx changes in Intune on Azure](https://aka.ms/appxchange) (Appx-wijzigingen in Intune op Azure) op het blog van het Intune-ondersteuningsteam voor meer informatie.  


## <a name="public-preview-of-the-new-intune-admin-experience-on-azure---736542--"></a>Openbare preview-versie van de nieuwe Intune-ervaring voor beheerders op Azure <!--736542-->

Aan het begin van kalenderjaar 2017 migreren we de volledige functionaliteit voor beheerders naar Azure, voor krachtig en geïntegreerd beheer van EMS-kernwerkstromen op een modern serviceplatform dat kan worden uitgebreid met Graph API’s.

Vanaf deze maand zal de openbare preview-versie van de nieuwe beheerderservaring te zien zijn voor nieuwe evaluatietenants in de Azure-portal. Tijdens de preview-periode worden de mogelijkheden en pariteit met de bestaande Intune-console iteratief geleverd.

De beheerderservaring in de Azure-portal zal gebruikmaken van de eerder aangekondigde nieuwe functionaliteit voor groepen en targeting. Wanneer uw bestaande tenant wordt gemigreerd naar de nieuwe ervaring voor groepen, vindt ook de migratie plaats naar de preview-versie van de nieuwe beheerderservaring. Als u in de tussentijd de nieuwe functionaliteit wilt testen of bekijken totdat de migratie van uw tenant is voltooid, kunt u zich aanmelden voor een nieuw Intune-evaluatieaccount of de [nieuwe documentatie](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) raadplegen.

### <a name="support-for-managed-configuration-options-for-android-apps----621621---"></a>Ondersteuning voor beheerde configuratieopties voor Android-apps <!-- 621621 -->

Android-apps in de Play Store die beheerde configuratieopties ondersteunen kunnen worden geconfigureerd door Intune.  Dankzij deze functie kan de IT-afdeling een lijst weergeven met de configuratiewaarden die door een app worden ondersteund, en kunnen die waarden worden geconfigureerd in een begeleide, eersteklas gebruikersinterface.

### <a name="remote-assistance-for-android-devices----675418---"></a>Hulp op afstand voor Android-apparaten <!-- 675418 -->

Intune werkt met de afzonderlijk verkrijgbare [TeamViewer](https://www.teamviewer.com)-software zodat u uw gebruikers met Android-apparaten hulp op afstand kunt bieden.

### <a name="new-android-policy-for-complex-pins----722069---"></a>Nieuw Android-beleid voor complexe pincodes <!-- 722069 -->

U kunt het verplichte wachtwoordtype instellen op Numeriek complex in een Android-apparaatprofiel voor apparaten met Android 5.0 en hoger.  Met deze instelling voorkomt u dat gebruikers een pincode kiezen die herhalende of opeenvolgende cijfers bevat, zoals 1111 of 1234.

### <a name="additional-support-for-android-for-work-devices"></a>Aanvullende ondersteuning voor Android for Work-apparaten

- **Wachtwoord- en werkprofieleninstellingen beheren** <!-- 612808 -->

  Er is een nieuw Android for Work-apparaatbeperkingsbeleid toegevoegd, waarmee u wachtwoord- en werkprofielinstellingen kunt beheren op de Android for Work-apparaten die u beheert.

- **Gegevens delen tussen werkprofielen en persoonlijke profielen toestaan** <!-- 1045102 -->

  De instelling **Gegevens delen tussen werkprofielen en persoonlijke profielen** in het Android for Work-apparaatbeperkingsprofiel is bijgewerkt met nieuwe opties, zodat u het delen van gegevens tussen werkprofielen en persoonlijke profielen kunt configureren.

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen beperken** <!-- 1046094 -->

  Als u Android for Work-apparaten beheert met Intune, zijn kopiëren en plakken tussen werk-apps en persoonlijke apps toegestaan. Er is nu een aangepast apparaatprofiel toegevoegd voor Android for Work-apparaten, waarmee u kunt instellen of kopiëren en plakken tussen werk-apps en persoonlijke apps zijn toegestaan.

### <a name="assign-lob-apps-to-ios-and-android-devices----1057568---"></a>LOB-apps toewijzen aan iOS- en Android-apparaten <!-- 1057568 -->

U kunt line-of-business-apps voor iOS (IPA-bestanden) en Android (APK-bestanden) toewijzen aan gebruikers of apparaten.

###  <a name="new-policies-for-ios-devices----723774-723815-723826-723830-723832---"></a>Nieuw beleid voor iOS-apparaten <!-- 723774, 723815, 723826, 723830, 723832 -->

- **Apps op beginscherm**: u kunt een apparaatbeleid gebruiken om te bepalen welke apps gebruikers zien op het beginscherm van hun iOS-apparaat. Dit beleid wijzigt de indeling van het beginscherm, maar implementeert geen apps die u hebt opgegeven maar die niet zijn geïnstalleerd.

- **Verbindingen met AirPrint-apparaten**: u kunt een Intune-apparaatbeleid gebruiken om te bepalen met welke AirPrint-apparaten (netwerkprinters) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Verbindingen met AirPlay-apparaten**: u kunt een Intune-apparaatbeleid gebruiken om te bepalen met welke AirPlay-apparaten (zoals Apple TV) de eindgebruikers van het iOS-apparaat verbinding kunnen maken.

- **Aangepast bericht vergrendelingsscherm**: u kunt een aangepast bericht configureren dat de gebruikers zien op het vergrendelingsscherm van hun iOS-apparaat. Dit bericht vervangt het standaardbericht op het vergrendelingsscherm.

- **Webinhoudsfilter**: u kunt bepalen welke websites de gebruikers van iOS-apparaten kunnen bezoeken met een van de volgende methoden:

  - Toegestane en geblokkeerde URL’s toevoegen met het ingebouwde webinhoudsfilter van Apple.
  - Alleen opgegeven websites toestaan voor de Safari-browser. Voor elke website die u opgeeft wordt een bladwijzer gemaakt in Safari.


### <a name="restrict-push-notifications-for-ios-apps----723767---"></a>Pushmeldingen voor iOS-apps beperken <!-- 723767 -->

In een Intune-apparaatbeperkingsprofiel kunt u de volgende meldingsinstellingen voor iOS-apparaten configureren:

- Meldingen voor een opgegeven app volledig in- of uitschakelen.
- Meldingen voor een opgegeven app in- of uitschakelen in het berichtencentrum.
- Het type waarschuwing opgeven: **Geen**, **Banner** of **Modale waarschuwing**.
- Opgeven of badges zijn toegestaan voor deze app.
- Opgeven of meldingsgeluiden zijn toegestaan.

### <a name="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---"></a>iOS-apps configureren voor autonome uitvoering in één-app-modus <!-- 737837 -->

U kunt een Intune-apparaatprofiel gebruiken om iOS-apparaten te configureren voor het uitvoeren van opgegeven apps in de autonome één-app-modus. Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld zodat alleen de betreffende app kan worden uitgevoerd. U kunt bijvoorbeeld een app configureren die de gebruikers een test laat uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

### <a name="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---"></a>Vertrouwde domeinen configureren voor e-mail en browsen op het web op iOS-apparaten <!-- 723765 -->

In een iOS-apparaatbeperkingsprofiel kunt u de volgende domeininstellingen configureren:

- **Niet-gemarkeerde e-maildomeinen**: e-mailberichten die de gebruiker verzendt of ontvangt die niet overeenkomen met de domeinen die u hier opgeeft, worden gemarkeerd als niet-vertrouwd.

- **Beheerde webdomeinen**: documenten die zijn gedownload via de URL's die u hier opgeeft, worden als beheerd beschouwd (alleen in Safari).  

- **Domeinen voor automatisch invullen van wachtwoorden in Safari**: gebruikers kunnen alleen wachtwoorden opslaan in Safari voor de URL’s die overeenkomen met de patronen die u hier opgeeft. Als u deze instelling wilt gebruiken, moet het apparaat in de supervisiemodus staan en niet zijn geconfigureerd voor meerdere gebruikers. (iOS 9.3+)


### <a name="vpp-apps-available-in-ios-company-portal----748782---"></a>VPP-apps beschikbaar in de iOS-bedrijfsportal <!-- 748782 -->

U kunt iOS-apps die zijn gekocht via het volume-aankoopprogramma toewijzen als **Beschikbaar** voor installatie door eindgebruikers. Eindgebruikers hebben een Apple Store-account nodig om de app te installeren.

### <a name="synchronize-ebooks-from-apple-vpp-store----800878---"></a>eBooks synchroniseren vanuit Apple VPP Store <!-- 800878 -->

U kunt eBooks die u hebt aangeschaft via het volume-aankoopprogramma van Apple synchroniseren met Intune en toewijzen aan gebruikers.

### <a name="multi-user-management-for-samsung-knox-standard-devices----971988---"></a>Beheer van meerdere gebruikers voor Samsung KNOX Standard-apparaten <!-- 971988 -->

Apparaten waarop Samsung KNOX Standard wordt uitgevoerd, bieden nu ondersteuning voor beheer van meerdere gebruikers in Intune. Dit betekent dat eindgebruikers zich kunnen aan- en afmelden bij het apparaat met hun Azure Active Directory-referenties, en dat het apparaat centraal wordt beheerd, ongeacht of het wordt gebruikt of niet.  Wanneer eindgebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.

### <a name="additional-windows-device-restriction-settings----818566---"></a>Aanvullende Windows 10-apparaatbeperkingsinstellingen <!-- 818566 -->

Er is ondersteuning toegevoegd voor aanvullende Windows 10-apparaatbeperkingsinstellingen, zoals instellingen voor de ondersteuning voor de Edge-browser, het aanpassen van het vergrendelingsscherm, het aanpassen van het startmenu, het instellen van de zoekfunctie van Windows-spotlight als achtergrondafbeelding, en proxy-instellingen.

### <a name="multi-user-support-for-windows-10-creators-update----822547---"></a>Ondersteuning voor meerdere gebruikers van Windows 10-makersupdate <!-- 822547 -->

Er is ondersteuning toegevoegd voor het beheer van meerdere gebruikers voor apparaten waarop de Windows 10-makersupdate wordt uitgevoerd en lid zijn van een Azure Active Directory-domein. Dit betekent dat wanneer verschillende standaardgebruikers zich aanmelden op het apparaat met hun Azure AD-referenties, ze de apps en beleidsregels ontvangen die zijn toegewezen aan hun gebruikersnaam. Gebruikers kunnen de bedrijfsportal op dit moment niet gebruiken voor selfservice scenario's zoals het installeren van apps.

### <a name="fresh-start-for-windows-10-pcs---1004830---"></a>Fresh Start voor Windows 10-pc’s<!-- 1004830 -->

In deze release is een nieuwe Fresh Start-apparaatactie toegevoegd voor Windows 10-pc’s.  Wanneer u deze actie uitvoert, worden alle apps die op de pc zijn geïnstalleerd verwijderd en wordt de pc automatisch bijgewerkt naar de laatste Windows-versie. Hiermee verwijdert u vooraf geïnstalleerde OEM-apps die vaak op nieuwe pc’s staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert.

### <a name="additional-windows-10-upgrade-paths----903672---"></a>Aanvullende upgradepaden voor Windows 10 <!-- 903672 -->

U kunt nu een versie-upgradebeleid maken om apparaten te upgraden naar de volgende aanvullende Windows 10-versies:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### <a name="bulk-enroll-windows-10-devices----747607---"></a>Windows 10-apparaten bulksgewijs inschrijven <!-- 747607 -->

U kunt grote aantallen apparaten waarop de Windows 10-makersupdate wordt uitgevoerd, toevoegen aan Azure Active Directory en Intune met Windows Configuration Designer (WCD). Als u automatische MDM-inschrijving voor uw Azure AD-tenant wilt inschakelen, maakt u een inrichtingspakket waarmee apparaten worden toegevoegd aan uw Azure AD-tenant met Windows Configuration Designer. U kunt het pakket toepassen op apparaten in bedrijfseigendom die u bulksgewijs wilt inschrijven en beheren. Zodra het pakket is toegepast op de apparaten, worden deze toegevoegd aan Azure AD, ingeschreven bij Intune en zijn ze klaar voor aanmelding door uw Azure AD-gebruikers.  Azure AD-gebruikers zijn standaardgebruikers op deze apparaten en ontvangen toegewezen beleid en de vereiste apps. Scenario’s voor Selfservice portal en bedrijfsportal worden momenteel niet ondersteund.

### <a name="new-mam-settings-for-pin-and-managed-storage-locations----58112-736644---"></a>Nieuwe MAM-instellingen voor pincode en beheerde opslaglocaties <!-- 58112, 736644 -->

Er zijn twee nieuwe app-instellingen beschikbaar voor het beheren van mobiele toepassingen:

- **App-pincode uitschakelen wanneer apparaatpincode wordt beheerd**: deze instelling detecteert of er een apparaatpincode aanwezig is op het ingeschreven apparaat. Als dat het geval is, wordt de app-pincode die wordt geactiveerd door het app-beveiligingsbeleid omzeild. Deze instelling zorgt ervoor dat gebruikers minder vaak een pincode hoeven in te voeren wanneer zij een beheerde mobiele toepassing openen op een ingeschreven apparaat. Deze functie is beschikbaar op Android en iOS.

- **Selecteer naar welke opslagservices bedrijfsgegevens kunnen worden opgeslagen**: hiermee kunt u opgeven welke opslaglocaties mogen worden gebruikt voor het opslaan van bedrijfsgegevens. Gebruikers kunnen alleen opslaan in de geselecteerde opslaglocatieservices, wat inhoudt dat de opslaglocatieservices die niet worden vermeld, zijn geblokkeerd.

  Lijst met ondersteunde opslaglocatieservices:

  - OneDrive
  - Zakelijke SharePoint Online
  - Lokale opslag


### <a name="see-also"></a>Zie ook
Zie [Wat is er nieuw in Microsoft Intune?](whats-new-in-microsoft-intune.md) voor meer informatie over recente ontwikkelingen.

