---
title: Apparaatbeperkingsinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een overzicht van alle instellingen en de bijbehorende beschrijvingen voor het maken van apparaatbeperkingen op apparaten met Windows 10 en hoger. Gebruik deze instellingen in een configuratieprofiel om controle te houden over schermafdrukken, wachtwoordvereisten, instellingen voor de kioskmodus, apps in de store, de Microsoft Edge-browser, Windows Defender, toegang tot de cloud, het startmenu en meer in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8957c8d8aad2eaa1741b1a625afd4b5a41a8bb51
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423693"
---
# <a name="windows-10-and-newer-device-settings-to-allow-or-restrict-features-using-intune"></a>Apparaatinstellingen voor Windows 10 en hoger om functies toe te staan of te beperken met behulp van Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op apparaten met Windows 10 en hoger. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, het vergrendelingsscherm aan te passen, Windows Defender te gebruiken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw Windows 10-apparaten.

> [!Note]
> Niet alle opties zijn beschikbaar in alle edities van Windows. Zie de ondersteunde versies, de [beleid CSP's](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider) (opent u een andere Microsoft-website).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](device-restrictions-configure.md#create-the-profile).

## <a name="app-store"></a>App Store

- **App Store (alleen mobiel)**: hiermee kunt u het gebruik van de App Store op Windows 10 Mobile-apparaten inschakelen of blokkeren.
- **Apps uit Store automatisch bijwerken**: apps die zijn geïnstalleerd vanuit Microsoft Store, kunnen automatisch worden bijgewerkt.
- **Installatie van vertrouwde app**: voor apps die zijn ondertekend met een vertrouwd certificaat is sideloaden mogelijk.
- **Ontgrendeling voor ontwikkelaars**: de eindgebruiker mag instellingen voor Windows-ontwikkelaars wijzigen, zoals het toestaan van sideloaden van apps.
- **Gedeelde app-gegevens voor gebruikers**: apps mogen gegevens delen tussen verschillende gebruikers op hetzelfde apparaat.
- **Alleen persoonlijke store gebruiken**: schakel dit in als eindgebruikers alleen apps mogen downloaden uit uw privé-store.
- **Uit Store afkomstige app starten**: alle apps uitschakelen die vooraf zijn geïnstalleerd op het apparaat of die zijn gedownload via Microsoft Store.
- **Appgegevens installeren op systeemvolume**: apps kunnen geen gegevens opslaan op het systeemvolume van het apparaat.
- **Apps installeren op systeemstation**: apps kunnen geen gegevens opslaan op het systeemstation van het apparaat.
- **Game-DVR (alleen bureaublad)**: hiermee bepaalt u of het opnemen en uitzenden van games is toegestaan.
- **Alleen voor apps uit de Store**: hiermee bepaalt u of gebruikers apps kunnen installeren vanuit andere locaties dan de App Store.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit

- **Mobiel gegevenskanaal**: hiermee voorkomt u dat gebruikers toegang hebben tot gegevens, bijvoorbeeld tijdens het surfen op internet, wanneer ze zijn verbonden met een mobiel netwerk. 
- **Dataroaming**: hiermee staat u roaming tussen netwerken toe tijdens het ophalen van data.
- **VPN via het mobiele netwerk**: hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen indien verbonden met een mobiel netwerk.
- **VPN-roaming via het mobiele netwerk**: hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen tijdens het roamen op een mobiele netwerk.
- **Bluetooth**: hiermee bepaalt u of de gebruiker Bluetooth op het apparaat kan inschakelen en configureren.
- **Bluetooth-detectie**: hiermee geeft u aan dat het apparaat kan worden gedetecteerd door andere Bluetooth-apparaten.
- **Vooraf koppelen van Bluetooth**: hiermee kunt u instellen dat bepaalde Bluetooth-apparaten automatisch worden gekoppeld met een hostapparaat.
- **Aankondigingen via Bluetooth**: hiermee geeft u aan dat het apparaat aankondigingen via Bluetooth kan ontvangen.
- **Service voor verbonden apparaten**: hiermee kunt u opgeven of de service voor verbonden apparaten is toegestaan, waardoor detectie van en verbinding met andere Bluetooth-apparaten mogelijk is.
- **NFC**: hiermee kan de gebruiker functies voor Near Field Communications (NFC) op het apparaat inschakelen en configureren.
- **Wi-Fi**: hiermee kan de gebruiker Wi-Fi op het apparaat inschakelen en configureren (alleen voor Windows 10 Mobile).
- **Automatisch verbinding maken met Wi-Fi-hotspots**: hiermee kunt u het apparaat automatisch verbinding laten maken met gratis Wi-Fi-hotspots en automatisch de voorwaarden voor de verbinding laten accepteren.
- **Handmatige configuratie van Wi-Fi**: hiermee geeft u aan of de gebruiker zijn of haar eigen Wi-Fi-verbindingen kan instellen, of dat de gebruiker alleen verbindingen kan gebruiken die door een Wi-Fi-profiel zijn geconfigureerd (alleen voor Windows 10 Mobile).
- **Wi-Fi-scaninterval**: voer in hoe vaak apparaten zoeken naar Wi-Fi-netwerken. Geef een waarde op tussen 1 (zo vaak mogelijk) en 500 (zo min mogelijk).
- **Services waarvoor Bluetooth is toegestaan**: geef een lijst met toegestane Bluetooth-services en -profielen op in de vorm van hexadecimale tekenreeksen.

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Microsoft-account**: hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.
- **Niet-Microsoft-account**: hiermee staat u toe dat gebruikers e-mailaccounts aan het apparaat kunnen toevoegen die niet aan een Microsoft-account zijn gekoppeld.
- **Synchronisatie van instellingen voor Microsoft-accounts**: hiermee staat u synchronisatie tussen apparaten toe van apparaat- en app-instellingen die aan een Microsoft-account zijn gekoppeld.
- **Aanmeldhulp voor Microsoft-account toestaan**: kies **Uitschakelen** om te voorkomen dat eindgebruikers de Microsoft-aanmeldhulp (wlidsvc) beheren, en de service bijvoorbeeld handmatig stoppen of starten. Als dit is ingesteld op **Niet geconfigureerd**, gebruikt de NT-service wlidsvc de standaardinstelling van het besturingssysteem, die eindgebruikers kan toestaan de service te starten en te stoppen. Deze service wordt door het besturingssysteem gebruikt om gebruikers zich te laten aanmelden bij hun Microsoft-account.

## <a name="cloud-printer"></a>Cloudprinter

- **Printerdetectie-URL**: voer de URL in voor het vinden van cloudprinters.
- **Verificatie-URL voor printertoegang**: voer de URL van het verificatie-eindpunt in om OAuth-tokens op te halen. Voer bijvoorbeeld iets in zoals `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **GUID van de systeemeigen client-app voor Azure**: voer de GUID in waarmee de clienttoepassing wordt geïdentificeerd die gemachtigd is voor het ophalen van OAuth-tokens van OAuthAuthority.
- **Resource-URI voor de afdrukservice**: voer de OAuth-resource-URI in voor de afdrukservice zoals geconfigureerd in de Azure-portal. Voer bijvoorbeeld iets in zoals `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maximumaantal printers waarvoor een query moet worden uitgevoerd (alleen mobiel)**: voer het maximumaantal printers in waarvoor u een query wilt uitvoeren. Voer bijvoorbeeld `10` in.
- **Resource-URI voor de printerdetectieservice**: voer de OAuth-resource-URI in voor de printerdetectieservice zoals geconfigureerd in de Azure-portal. Voer bijvoorbeeld iets in zoals `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Na het instellen van een [Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview) kunt u deze instellingen configureren en vervolgens implementeren naar Windows-apparaten.

## <a name="control-panel-and-settings"></a>Configuratiescherm en instellingen

- **App Instellingen**: hiermee blokkeert u toegang tot de app Instellingen van Windows.
  - **Systeem**: hiermee blokkeert u de toegang tot het systeemgebied van de app Instellingen.
    - **Instellingen voor in-/uitschakelen en slaapstand wijzigen (alleen desktop)**: hiermee voorkomt u dat de eindgebruiker de instellingen voor in-/uitschakelen en de slaapstand op het apparaat wijzigt.
  - **Apparaten**: hiermee blokkeert u de toegang tot het apparatengebied van de instellingen-app.
  - **Netwerk en internet**: hiermee blokkeert u de toegang tot het gebied voor netwerk en internet van de instellingen-app.
  - **Persoonlijke instellingen**: hiermee blokkeert u de toegang tot het gebied voor persoonlijke instellingen van de instellingen-app.
  - **Accounts**: hiermee blokkeert u de toegang tot het accountsgebied van de instellingen-app.
  - **Tijd en taal**: hiermee blokkeert u de toegang tot het gebied voor tijd en taal van de instellingen-app.
    - **Systeemtijd wijzigen**: hiermee voorkomt u dat de eindgebruiker de datum en tijd van het apparaat wijzigt.
    - **Regio-instellingen aanpassen (alleen desktop)**: hiermee voorkomt u dat de eindgebruiker de regionale instellingen op het apparaat wijzigt.
    - **Taalinstellingen wijzigen (alleen bureaublad)**: hiermee voorkomt u dat de eindgebruiker de taalinstellingen op het apparaat wijzigt.
  - **Gaming**: hiermee blokkeert u de toegang tot de gaming-app in Instellingen.
  - **Betere toegankelijkheid**: hiermee blokkeert u de toegang tot het gebied voor betere toegankelijkheid van de instellingen-app.
  - **Privacy**: hiermee blokkeert u de toegang tot het privacygebied van de instellingen-app.
  - **Bijwerken en beveiliging**: hiermee blokkeert u de toegang tot het gebied voor updates en beveiliging van de instellingen-app.

## <a name="display"></a>Weergave

- **GDI-schaalbaarheid voor apps inschakelen**
- **GDI-schaalbaarheid voor apps uitschakelen**

  Met GDI DPI-schaalbaarheid krijgen apps die geen DPI-status hebben, een per-monitor-DPI-status. Geef de verouderde apps op waarvoor GDI DPI-schaalbaarheid is ingeschakeld. Als GDI DPI-schaalbaarheid is geconfigureerd voor zowel in- als uitschakelen voor een app, wordt de schaalbaarheid voor de app uitgeschakeld.

## <a name="general"></a>Algemeen

- **Schermafbeelding (alleen mobiel)**: hiermee kan de gebruiker het apparaatscherm vastleggen als afbeelding.
- **Kopiëren en plakken (alleen mobiel)**: hiermee staat u kopieer- en plakbewerkingen tussen apps op het apparaat toe.
- **Registratie handmatig ongedaan maken**: hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen.
  - Deze beleidsinstelling is niet van toepassing als de computer is toegevoegd aan Azure AD en automatische inschrijving is ingeschakeld. 
  - Deze beleidsinstelling geldt niet voor computers met Windows 10 Home.
- **Handmatige installatie van het basiscertificaat (alleen mobiel)**: voorkomt dat de gebruiker handmatig basiscertificaten en tussenliggende CAP-certificaten kan installeren.

- **Camera**: hiermee kunt u het gebruik van de camera op het apparaat toestaan of blokkeren.
- **Bestandssynchronisatie met OneDrive**: hiermee voorkomt u dat het apparaat bestanden synchroniseert naar OneDrive.
- **Verwisselbare opslag**: hiermee geeft u op of er met het apparaat externe opslagapparaten, zoals SD-kaarten, kunnen worden gebruikt.
- **Geolocatie**: hiermee geeft u aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt.
- **Gedeeld internet**: hiermee staat u het gebruik van een gedeelde internetverbinding op het apparaat toe.
- **Telefoon opnieuw instellen**: hiermee bepaalt u of de gebruiker het apparaat kan wissen.
- **USB-verbinding (alleen mobiel)**: hiermee bepaalt u of apparaten via een USB-verbinding toegang kunnen krijgen tot externe opslagapparaten.
- **AntiTheft-modus (alleen mobiel)**: hiermee configureert u of de AntiTheft-modus van Windows is ingeschakeld.
- **Cortana**: hiermee schakelt u de spraakassistent Cortana in en uit.
- **Spraakopname (alleen mobiel)**: hiermee kunt u het gebruik van het spraakopnameapparaat van het apparaat toestaan of blokkeren.
- **Apparaatnaam wijzigen**: hiermee voorkomt u dat de eindgebruiker de apparaatnaam wijzigt (alleen voor Windows 10 Mobile)
- **Inrichtingspakketten toevoegen**: hiermee blokkeert u de runtime configuratieagent die de inrichtingspakketten installeert.
- **Inrichtingspakketten verwijderen**: hiermee blokkeert u de runtime configuratieagent die de inrichtingspakketten verwijdert.
- **Apparaatdetectie**: hiermee voorkomt u dat een apparaat wordt gedetecteerd door andere apparaten.
- **Taakwisselaar (alleen mobiel)**: hiermee blokkeert u de taakwisselaar op het apparaat.
- **Foutberichtvenster voor SIM-kaart (alleen mobiel)**: hiermee voorkomt u dat op het apparaat een foutbericht wordt weergegeven als er geen SIM-kaart wordt gedetecteerd.
- **Ink-werkruimte**: hiermee voorkomt u dat gebruikers toegang hebben tot de Ink-werkruimte. Als dit is ingesteld op **Niet geconfigureerd**, wordt de Ink-werkruimte ingeschakeld (de functie wordt ingeschakeld) en mag de gebruiker deze gebruiken boven het vergrendelingsscherm.
- **Automatisch opnieuw implementeren**: hiermee kunnen gebruikers met beheerdersrechten alle gebruikersgegevens en -instellingen verwijderen met **Ctrl + Win + R** op het vergrendelingsscherm van het apparaat. Het apparaat wordt automatisch opnieuw geconfigureerd en opnieuw ingeschreven bij het beheer.
- **Gebruikers verplichten om verbinding te maken met het netwerk tijdens de configuratie van het apparaat (alleen Windows Insider)**: kies **Vereisen** om gebruikers tijdens de installatie van Windows 10 te verplichten het apparaat te verbinden met een netwerk voordat de configuratie van Windows 10 verder wordt uitgevoerd na de netwerkpagina.

  De instelling van kracht wordt de volgende keer dat het apparaat is gewist of teruggezet. Net als elke andere Intune-configuratie, moet het apparaat worden geregistreerd en beheerd door Intune voor het ontvangen van configuratie-instellingen. Maar nadat deze geregistreerd en beleid ontvangt, klikt u vervolgens opnieuw instellen van het apparaat dwingt de instelling tijdens de volgende Windows-installatie.

- **Directe geheugentoegang**: met **Blokkeren** blokkeert u directe geheugentoegang (DMA) voor alle downstream hot-pluggable PCI-poorten totdat een gebruiker zich bij Windows aanmeldt. **Ingeschakeld** (standaard) staat toegang tot DMA toe, zelfs wanneer een gebruiker niet is aangemeld.

  CSP: [DataProtection/AllowDirectMemoryAccess](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-dataprotection#dataprotection-allowdirectmemoryaccess)

- **Beëindigen van processen in Taakbeheer**: deze instelling bepaalt of niet-beheerders Taakbeheer end taken kunnen gebruiken. Met **Blokkeren** voorkomt u dat standaardgebruikers (niet-beheerders) processen of taken op het apparaat kunnen beëindigen met behulp van Taakbeheer. Met **Niet geconfigureerd** (standaard) kunnen standaardgebruikers processen of taken beëindigen met behulp van Taakbeheer.

## <a name="locked-screen-experience"></a>Vergrendeld scherm

- **Meldingen van het Actiecentrum (alleen mobiel)**: hiermee kunt u meldingen van het actiecentrum op het vergrendelingsscherm van het apparaat weergeven (alleen Windows 10 Mobile).
- **Afbeeldings-URL vergrendelingsscherm (alleen bureaublad)**: voer de URL in van een afbeelding in JPEG-indeling die wordt gebruikt als achtergrond van het Windows-vergrendelingsscherm. Door deze instelling wordt de afbeelding vergrendeld. De afbeelding kan later niet worden gewijzigd.
- **Time-out voor het scherm die door de gebruiker kan worden ingesteld (alleen mobiel)**: hiermee kunnen gebruikers de tijd configureren opgeven waarna het scherm wordt uitgeschakeld nadat het scherm is vergrendeld. 
- **Cortana op vergrendeld scherm (alleen bureaublad)**: de gebruiker geen toestemming geven voor interactie met Cortana wanneer het vergrendelingsscherm wordt weergegeven op het apparaat (alleen Windows 10 voor desktops).
- **Pop-upmeldingen op vergrendeld scherm**: geen waarschuwingsberichten weergeven op het vergrendelingsscherm van het apparaat.
- **Time-out voor het scherm (alleen mobiel)**: hiermee geeft u de tijd in seconden op waarna het scherm wordt uitgeschakeld nadat het scherm is vergrendeld.

## <a name="messaging"></a>Berichten

- **Berichten synchroniseren (alleen mobiel)**: schakel back-up en herstel van Berichten overal en tekstberichten uit.
- **Mms (alleen mobiel)**: schakel de Mms-functie voor verzenden/ontvangen op het apparaat uit.
- **Rcs (alleen mobiel)**: schakel de Rich Communication Services-functie voor verzenden/ontvangen op het apparaat uit.

## <a name="microsoft-edge-browser"></a>Microsoft Edge-browser

### <a name="use-microsoft-edge-kiosk-mode"></a>Gebruik Microsoft Edge-kioskmodus

De beschikbare instellingen wijzigen, afhankelijk van wat u kiest. Uw opties zijn:

- **Geen** (standaard): Microsoft Edge wordt niet uitgevoerd in de kioskmodus bevindt. Alle instellingen voor Microsoft Edge zijn beschikbaar voor u om te wijzigen en te configureren.
- **Digitale/interactief aankondigingen (kiosk voor één app)**: Filters Microsoft Edge-instellingen die van toepassing voor digitale/interactief borden tot stand brengen Microsoft Edge in kioskmodus alleen op één kiosken Windows 10 zijn. Kies deze instelling om een volledige URL-scherm te openen en de inhoud alleen weergeven op die website. [Instellen van digitale borden](https://docs.microsoft.com/windows/configuration/setup-digital-signage) vindt u meer informatie over deze functie.
- **Openbare InPrivate-navigatie (kiosk voor één app)**: Filters Microsoft Edge-instellingen die van toepassing voor de InPrivate-navigatie openbare bladeren door Microsoft Edge kioskmodus voor gebruik op Windows 10 één app kiosken zijn. Een meerdere tabblad-versie van Microsoft Edge wordt uitgevoerd.
- **Normale modus (kiosk voor meerdere Apps)**: Filters Microsoft Edge-instellingen die voor de kioskmodus normaal Microsoft Edge gelden. Voert een volledige versies van Microsoft Edge met alle functies van de browser.
- **Openbare bladeren (kiosk voor meerdere Apps)**: Filters Microsoft Edge-instellingen die van toepassing voor het openbare-bladeren door op een Windows 10-kiosk voor meerdere Apps zijn.  Een meerdere tabblad-versie van Microsoft Edge InPrivate-navigatie wordt uitgevoerd.

> [!TIP]
> Zie voor meer informatie over het doen van deze opties [Microsoft Edge kiosk modus configuratie typen](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-configuration-types).

Dit apparaatbeperkingsprofiel is direct gerelateerd aan de kiosk-profiel u maken met behulp van de [kiosk-instellingen voor Windows](kiosk-settings-windows.md). Samenvatting:

1. Maak de [kiosk-instellingen voor Windows](kiosk-settings-windows.md) profiel voor het uitvoeren van het apparaat in kioskmodus bevindt. Microsoft Edge als de toepassing te selecteren en stel de kioskmodus van Microsoft Edge in de Kiosk-profiel.
2. In dit artikel beschreven profiel voor de beperkingen van het apparaat maken en configureren van specifieke functies en instellingen die zijn toegestaan in Microsoft Edge. Zorg ervoor dat de dezelfde type kiosk-modus Microsoft Edge geselecteerd in de kiosk-profiel te kiezen ([kiosk-instellingen voor Windows](kiosk-settings-windows.md)). 

    [Instellingen voor de kioskmodus ondersteund](https://docs.microsoft.com/microsoft-edge/deploy/microsoft-edge-kiosk-mode-deploy#supported-policies-for-kiosk-mode) is een fantastische bron.

> [!IMPORTANT] 
> Zorg ervoor dat u dit Microsoft Edge-profiel toewijzen aan de dezelfde apparaten als uw kiosk-profiel ([kiosk-instellingen voor Windows](kiosk-settings-windows.md)).

[ConfigureKioskMode CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskmode)

### <a name="start-experience"></a>Gebruikerservaring

- **Microsoft Edge starten met**: kies welke pagina's worden geopend wanneer Microsoft Edge wordt gestart. Uw opties zijn:
  - **Startpagina's**: Microsoft Edge starten met de standaardstartpagina zoals gedefinieerd door het besturingssysteem
  - **Nieuwe tabbladpagina**: Microsoft Edge laden met wat er is gedefinieerd in de instelling **URL van nieuw tabblad**
  - **Pagina van laatste sessie**: Microsoft Edge laden met de pagina van de laatste sessie 
  - **Aangepaste startpagina**: Microsoft Edge laden met de startpagina die is gedefinieerd door de IT-beheerder
- **Gebruiker kan startpagina's wijzigen**: met **Toestaan** kunnen gebruikers de startpagina's wijzigen. Beheerders kunnen gebruikmaken van `EdgeHomepageUrls` om de startpagina's in te voeren die gebruikers standaard zien wanneer ze Microsoft Edge openen. Met **Niet geconfigureerd** wordt voorkomen dat gebruikers de startpagina's wijzigen.
- **URL van nieuw tabblad**: voer de URL in die moet worden geopend op de pagina Nieuw tabblad. Voer bijvoorbeeld `https://www.bing.com` in.
- **Webinhoud openen op een nieuw tabblad**: kies **Blokkeren** om te voorkomen dat Microsoft Edge een website opent op een nieuw tabblad. In dat geval wordt er een nieuw, leeg tabblad geopend. Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem op het apparaat gebruikt, waardoor gebruikers mogelijk kunnen kiezen wat er wordt weergegeven.
- **De knop Start**: kiezen wat er gebeurt wanneer de knop Start wordt geselecteerd. Uw opties zijn:
  - **Startpagina's**: de optie die u hebt gekozen voor de instelling **Microsoft Edge starten met** wordt geopend
  - **Nieuwe tabbladpagina**: de optie die u hebt gekozen voor de instelling **URL van nieuw tabblad** wordt geopend
  - **URL van aangepaste startknop**: de optie die u hebt gekozen voor de instelling **URL van startknop** wordt geopend
  - **Startknop verbergen**: hiermee verbergt u de knop Start
- **Gebruiker kan de knop Start wijzigen**: met **Toestaan** kunnen gebruikers de knop Start wijzigen. Wijzigingen van de gebruiker overschrijven instellingen van een beheerder voor de knop Start. Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem op het apparaat gebruikt, waardoor gebruikers mogelijk niet kunnen wijzigen hoe de beheerder de knop Start heeft geconfigureerd.
- **Pagina voor first-run experience weergeven**: met **Blokkeren** wordt de introductiepagina niet weergegeven wanneer Microsoft Edge de eerste keer wordt uitgevoerd. Bedrijven kunnen deze functie gebruiken om deze pagina te blokkeren, bijvoorbeeld omdat ze werken met 'zero configuration'. Met **Niet geconfigureerd** wordt de introductiepagina weergegeven.
  - **URL van first-run experience**: voer de URL in van de pagina die moet worden weergegeven wanneer een gebruiker de eerste keer Microsoft Edge uitvoert (alleen Windows 10 Mobile).
- **Vernieuw de browser na niet-actieve tijd**: Voer het aantal niet-actieve minuten op waarna de browser wordt vernieuwd, van 0-1440 minuten. De standaardwaarde is `5` minuten. Als de waarde `0` (nul), de browser niet na een inactiviteit wordt vernieuwd.

  Deze instelling is alleen beschikbaar bij het uitvoeren van [openbare InPrivate-browsing (kiosk voor één app)](#use-microsoft-edge-kiosk-mode).

  CSP: [ConfigureKioskResetAfterIdleTimeout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-configurekioskresetafteridletimeout)

- **Pop-ups**: kies **Blokkeren** om pop-upvensters in de browser tegen te houden. Dit is alleen van toepassing op Windows 10 Desktop. Met **Niet geconfigureerd** zijn pop-ups toegestaan in de webbrowser.
- **Intranetverkeer naar Internet Explorer sturen**: met **Toestaan** kunnen gebruikers intranetwebsites in Internet Explorer openen in plaats van Microsoft Edge (alleen bureaubladversie van Windows 10). Met **Niet geconfigureerd** kunnen gebruikers Microsoft Edge gebruiken.
- **Locatie van de lijst met websites van Bedrijfsmodus**: voer de URL in met de lijst met websites die in Bedrijfsmodus worden geopend. Gebruikers kunnen deze lijst niet wijzigen. Dit is alleen van toepassing op Windows 10 Desktop.
- **Bericht bij openen van sites in Internet Explorer**: gebruik deze instelling om Microsoft Edge zo te configureren dat er een melding wordt weergeven voordat er een site wordt geopend in Internet Explorer 11. Uw opties zijn:
  - **Niet geconfigureerd**: het standaardgedrag van het besturingssysteem wordt gebruikt, waardoor er mogelijk geen bericht wordt weergegeven.
  - **Bericht weergeven zonder optie voor het openen van sites in Microsoft Edge**: het bericht weergeven bij het openen van sites in Internet Explorer. Sites worden geopend in IE. Er is geen optie voor het openen van sites in Microsoft Edge.
  - **Bericht weergeven bij openen van sites in Microsoft Edge**: het bericht weergeven bij het openen van sites in IE. Het bericht bevat een koppeling **Verdergaan in Microsoft Edge**, zodat gebruikers Microsoft Edge kunnen kiezen in plaats van Internet Explorer.

  > [!IMPORTANT]
  > Voor deze instelling moet u de instelling **Sitelijst Bedrijfsmodus configureren**, de instelling **Alle intranetsites naar Internet Explorer 11 verzenden** of beide instellingen inschakelen.

- **Microsoft-compatibiliteitslijst**: met **Blokkeren** wordt de Microsoft-compatibiliteitslijst voorkomen in Microsoft Edge. Deze lijst van Microsoft helpt Microsoft Edge om sites met bekende compatibiliteitsproblemen toch goed weer te geven. Met **Niet geconfigureerd** kan een compatibiliteitslijst van Microsoft worden gebruikt.
- **Startpagina's en nieuw tabblad vooraf laden**: kies **Blokkeren** om te voorkomen dat er vooraf startpagina's en een nieuw tabblad worden geladen door Microsoft Edge. Vooraf laden minimaliseert de tijd voor het starten van Microsoft Edge en het laden van een nieuw tabblad. **Niet geconfigureerd** maakt gebruik van het standaardgedrag van het besturingssysteem, wat inhoudt dat deze pagina's mogelijk vooraf worden geladen.
- **Startpagina's en nieuw tabblad vooraf starten**: kies **Blokkeren** om te voorkomen dat de startpagina's en een nieuw tabblad vooraf worden gestart door Microsoft Edge. Vooraf starten verbetert de prestaties van Microsoft Edge en minimaliseert de tijd die nodig is om Microsoft Edge te starten. **Niet geconfigureerd** maakt gebruik van het standaardgedrag van het besturingssysteem, wat inhoudt dat deze pagina's mogelijk vooraf worden gestart.

### <a name="favorites-and-search"></a>Favorieten en zoeken

- **Werkbalk met Favorieten**: kies wat er moet gebeuren er met de werkbalk met favorieten op een pagina van Microsoft Edge. Uw opties zijn:
  - **Niet geconfigureerd**: maakt gebruik van het standaardgedrag van het besturingssysteem, wat kan betekenen dat de werkbalk met favorieten op alle pagina's wordt verborgen. Gebruikers kunnen deze instelling wijzigen.
  - **Verbergen**: hiermee verbergt u de werkbalk met favorieten op alle pagina's. Gebruikers kunnen deze instelling niet wijzigen.
  - **Weergeven**: hiermee toont u de werkbalk met favorieten op alle pagina's. Gebruikers kunnen deze instelling niet wijzigen.
- **Lijst met favorieten**: voeg een lijst met URL's toe aan het bestand met favorieten. Voeg bijvoorbeeld `http://contoso.com/favorites.html` toe.
- **Wijzigingen aan Favorieten beperken**: stel dit in op **Blokkeren** om te voorkomen dat gebruikers items aan de lijst met favorieten toevoegen, of de lijst importeren, sorteren of bewerken. Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem gebruikt, wat kan betekenen dat gebruikers de lijst kunnen wijzigen.
- **Favorieten synchroniseren tussen Microsoft-browsers (alleen bureaublad)**: met **Vereisen** stelt u in dat favorieten moeten worden gesynchroniseerd tussen Internet Explorer en Microsoft Edge. Toevoegingen, verwijderingen, aanpassingen en wijzigingen van de volgorde worden gedeeld tussen browsers.  Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem gebruikt, zodat de kans bestaat dat gebruikers zelf bepalen of ze favorieten willen synchroniseren tussen de browsers.
- **Standaardzoekmachine**: kies de zoekmachine die u standaard op het apparaat wilt gebruiken. Eindgebruikers kunnen deze waarde op elk moment wijzigen. Uw opties zijn:
  - Standaard
  - Bing
  - Google
  - Yahoo
  - Aangepaste waarde
- **Zoeksuggesties**: met **Niet geconfigureerd** stelt u in dat de zoekmachine sites kan voorstellen wanneer u zoektermen typt op de adresbalk. Met **Blokkeren** wordt deze functie geblokkeerd.
- **Wijzigingen in de zoekmachine toestaan**: **Ja** (standaard) kan gebruikers nieuwe zoekmachines toevoegen of wijzigen van de standaardzoekmachine in Microsoft Edge. Kies **Nee** om te voorkomen dat gebruikers de zoekmachine aanpassen.

  Deze instelling is alleen beschikbaar bij het uitvoeren van [normale modus (kiosk voor meerdere Apps)](#use-microsoft-edge-kiosk-mode).

  CSP: [AllowSearchEngineCustomization](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-browser#browser-allowsearchenginecustomization)

### <a name="privacy-and-security"></a>Privacy en beveiliging

- **InPrivate-navigatie**: met  **Blokkeren** voorkomt u dat eindgebruikers InPrivate-navigatiesessies openen. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Browsegeschiedenis opslaan**: met **Blokkeren** voorkomt u dat Microsoft Edge de browsegeschiedenis opslaat. Met **Niet geconfigureerd** kan de browsegeschiedenis worden opgeslagen.
- **Browsegegevens wissen bij afsluiten (alleen bureaublad)**: met **Vereisen** worden de geschiedenis en de browsegegevens gewist wanneer de gebruiker Microsoft Edge afsluit. Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem gebruikt, wat betekent dat de browsegegevens mogelijk in de cache worden opgeslagen.
- **Browserinstellingen synchroniseren tussen apparaten van gebruiker**: geef aan hoe u browserinstellingen wilt synchroniseren tussen apparaten. Uw opties zijn:
  - **Toestaan**: synchronisatie van instellingen van de Microsoft Edge-browser toestaan tussen apparaten van de gebruiker
  - **Blokkeren en overschrijven door gebruiker inschakelen**: synchronisatie van Microsoft Edge-browserinstellingen tussen apparaten van de gebruiker blokkeren. Gebruikers kunnen deze instelling wijzigen.
  - **Blokkeren**: synchronisatie van Microsoft Edge-browserinstellingen tussen apparaten van de gebruiker blokkeren. Gebruikers kunnen deze instelling niet wijzigen.
- **Wachtwoordbeheer**: met  **Blokkeren** schakelt u de functie Wachtwoordbeheer van Microsoft Edge uit. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Cookies**: geef aan hoe cookies worden verwerkt in de browser. Uw opties zijn:
  - **Toestaan**: cookies worden op het apparaat opgeslagen.
  - **Alle cookies blokkeren**: cookies worden niet op het apparaat opgeslagen.
  - **Alleen cookies van derden blokkeren**: cookies van derden of partners worden niet op het apparaat opgeslagen.
- **Automatisch doorvoeren**: met **Blokkeren** wordt de functie Automatisch doorvoeren uitgeschakeld op het apparaat. **Niet geconfigureerd**: hiermee kunnen gebruikers instellingen voor automatisch doorvoeren wijzigen in de browser (alleen Windows 10 Desktop).
- **Do Not Track-headers verzenden**: met **Niet geconfigureerd** moeten apparaten Do Not Track-headers verzenden naar websites die om traceringsgegevens vragen (aanbevolen). Kies **Blokkeren** om te voorkomen dat het apparaat deze headers verstuurt, waarmee websites de gebruiker kunnen volgen.
- **LocalHost IP-adres voor WebRTC**: met **Blokkeren** voorkomt u dat het IP-adres van de LocalHost van gebruikers wordt weergegeven tijdens het plaatsen van telefoonoproepen via het WebRTC-protocol. Met **Niet geconfigureerd** kan het IP-adres van de LocalHost van gebruikers worden weergegeven bij het plaatsen van telefoonoproepen met behulp van dit protocol.
- **Verzamelen van livetegelgegevens**: kies  **Blokkeren** om te voorkomen dat Windows gegevens verzamelt van de livetegel waaraan een site is vastgemaakt in het startmenu van Microsoft Edge. Met **Niet geconfigureerd** kunnen deze gegevens worden verzameld.
- **Gebruiker kan certificaatfouten negeren**: met **Blokkeren** wordt voorkomen dat gebruikers toegang hebben tot websites met SSL- of TLS-fouten. Met **Niet geconfigureerd** hebben gebruikers toegang tot deze sites.

### <a name="additional"></a>Aanvullende informatie

- **Microsoft Edge-browser (alleen mobiel)**: kies **Blokkeren** om te voorkomen dat Microsoft Edge wordt gebruikt op het apparaat. Als u Microsoft Edge blokkeert, gelden de afzonderlijke instellingen alleen voor de desktop. Met **Niet geconfigureerd** kan de webbrowser Microsoft Edge worden gebruikt op het apparaat.
- **Vervolgkeuzelijst van de adresbalk (alleen desktop)**: met **Blokkeren** voorkomt u dat er in Microsoft Edge een lijst met suggesties wordt weergeven wanneer u typt in het invoervak van een vervolgkeuzelijst. Deze optie helpt bij het beperken van de netwerkbandbreedte die nodig is tussen Microsoft Edge en Microsoft-services. Met **Niet geconfigureerd** kan Microsoft Edge een lijst met suggesties weergeven.
- **Volledig scherm**: kies **Blokkeren** om te voorkomen dat Microsoft Edge alleen de webinhoud weergeeft en de interface van Microsoft Edge verbergt (volledig scherm). Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem gebruikt, waardoor Microsoft Edge schermvullend kan worden weergegeven.
- **Over-vlaggen**: met **Blokkeren** wordt voorkomen dat eindgebruikers toegang hebben tot de pagina `about:flags` in Microsoft Edge met onder andere informatie over de ontwikkelaar en experimentele instellingen. Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem gebruikt, wat kan betekenen dat de pagina `about:flags` toegankelijk is.
- **Ontwikkelhulpprogramma's**: met  **Blokkeren** voorkomt u dat eindgebruikers de ontwikkelhulpprogramma's van Microsoft Edge openen. Met **Niet geconfigureerd** kunnen gebruikers de ontwikkelhulpprogramma's openen.
- **Extensies**: met **Niet geconfigureerd** kunnen eindgebruikers extensies van Microsoft Edge installeren op het apparaat. Met **Blokkeren** wordt de installatie hiervan voorkomen.
- **Ontwikkelaarsuitbreidingen sideloaden**: met **Blokkeren** voorkomt u sideloading door Microsoft Edge, waarbij niet-geverifieerde extensies worden geïnstalleerd en uitgevoerd met behulp van de functie **Extensies laden**. Met **Niet geconfigureerd** wordt het standaardgedrag van het besturingssysteem gebruikt, wat kan betekenen dat sideloading is toegestaan.
- **Vereiste extensies**: kies welke extensies niet kunnen worden uitgeschakeld door eindgebruikers in Microsoft Edge. Voer de familienamen van pakketten in en selecteer **Toevoegen**. De lijsten in [Een PFN (Package Family Name) zoeken](https://docs.microsoft.com/sccm/protect/deploy-use/find-a-pfn-for-per-app-vpn) geven meer informatie.

  U kunt ook een CSV-bestand **importeren** met de familienamen van pakketten.

- **JavaScript**: kies **Blokkeren** om te voorkomen dat Java-scripts worden uitgevoerd in de browser op het apparaat. Met **Niet geconfigureerd** kunnen scripts, zoals JavaScript, worden uitgevoerd in de Microsoft Edge-browser.

## <a name="network-proxy"></a>Netwerkproxy

- **Proxy-instellingen automatisch detecteren**: wanneer deze optie is ingeschakeld, probeert het apparaat het pad naar een PAC-script te vinden.
- **Proxyscript gebruiken**: selecteer deze optie als u een pad naar een PAC-script wilt opgeven om de proxyserver te configureren.
  - **URL voor het installatiescriptadres**: geef de URL op van een PAC-script dat u wilt gebruiken om de proxyserver te configureren.
- **Handmatige proxyserver gebruiken**: selecteer deze optie om de gegevens van de proxyserver handmatig in te voeren.
  - **Adres**: voer de naam of het IP-adres van de proxyserver in.
  - **Poortnummer**: voer het poortnummer van uw proxyserver in.
  - **Proxy-uitzonderingen**: voer URL's in die geen gebruik mogen maken van de proxyserver. Scheid de items van elkaar met een puntkomma.
  - **Proxyserver niet gebruiken voor lokale adressen**: schakel deze optie in als u de proxyserver niet wilt gebruiken voor lokale adressen in uw intranet.

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
  - **Vereist wachtwoordtype**: hiermee geeft u aan of het wachtwoord alleen numeriek of alfanumeriek moet zijn.
  - **Minimale wachtwoordlengte**: alleen van toepassing op Windows 10 Mobile.
  - **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voor apparaten met Windows 10: als BitLocker is ingeschakeld op het apparaat, wordt het in de herstelmodus van BitLocker gezet nadat het aanmelden het aantal keren dat u opgeeft is mislukt. Als BitLocker niet is ingeschakeld op het apparaat, is deze instelling niet van toepassing. Voor Windows 10 Mobile-apparaten: nadat het aanmelden het opgegeven aantal keer is mislukt, wordt het apparaat gewist.
  - **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u de hoeveelheid tijd op die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.
  - **Wachtwoord verloopt (dagen)**: hiermee geeft u de hoeveelheid tijd op waarna het wachtwoord van een apparaat moet worden gewijzigd.
  - **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.
  - **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status (alleen voor Mobile)**: hiermee geeft u aan dat de gebruiker een wachtwoord moet opgeven om het apparaat te ontgrendelen (alleen voor Windows 10 Mobile).
  - **Eenvoudige wachtwoorden**: hiermee kunt u instellen dat eenvoudige wachtwoorden zijn toegestaan, zoals 1111 en 1234. Met deze instelling kunt u ook het gebruik van afbeeldingswachtwoorden toestaan of blokkeren.
- **Automatische versleuteling tijdens toevoegen aan AAD**: **blok** wordt voorkomen dat automatische BitLocker-versleuteling voor apparaat wanneer het apparaat wordt voorbereid voor het eerste gebruik, wanneer het apparaat toegevoegd aan Azure AD is. **Niet geconfigureerd** (standaard) maakt gebruik van het besturingssysteem standaardoptie, Hierbij kan versleuteling inschakelen. Meer op [BitLocker apparaatversleuteling](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10#bitlocker-device-encryption).

  [Security/PreventAutomaticDeviceEncryptionForAzureADJoinedDevices CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-security#security-preventautomaticdeviceencryptionforazureadjoineddevices)

- **Federal Information Processing Standard (FIPS) beleid**: **toestaan** maakt gebruik van de Federal Information Processing Standard (FIPS)-beleid, waarvan een US government standard voor versleuteling, hashing en ondertekening. **Niet geconfigureerd** (standaard) gebruikmaakt van het besturingssysteem, die geen gebruik maakt van FIPS.

  [Cryptography/AllowFipsAlgorithmPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-cryptography#cryptography-allowfipsalgorithmpolicy)

- **Windows Hello-apparaatverificatie**: **toestaan** gebruikers op een Windows Hello secundair apparaat gebruiken, zoals een telefoon, geschiktheid band of IoT-apparaat te melden bij een Windows 10-computer. **Niet geconfigureerd** (standaard) gebruikmaakt van het besturingssysteem, waardoor Windows Hello begeleidende apparaten van verificatie met Windows.

  [Authentication/AllowSecondaryAuthenticationDevice CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowsecondaryauthenticationdevice)

- **Web-aanmelding**: Windows kan zich aanmelden voor ondersteuning voor niet-ADFS (Active Directory Federation Services) federatieve-providers, zoals Security Assertion Markup Language (SAML). SAML maakt gebruik van beveiligde tokens die biedt webbrowsers een eenmalige aanmelding (SSO). Uw opties zijn:

  - **Niet geconfigureerd** (standaard): gebruikmaakt van het besturingssysteem op het apparaat.
  - **Ingeschakeld**: de Web-Referentieprovider is ingeschakeld voor aanmelden.
  - **Uitgeschakeld**: de Web-Referentieprovider voor aanmelding is uitgeschakeld.

  [Verificatie/EnableWebSignIn CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-enablewebsignin)

- **Azure Active Directory-tenantdomein voorkeur**: Voer de domeinnaam van een bestaande in uw organisatie Azure AD. Wanneer gebruikers in dit domein zich aanmelden, moet ze geen Typ de naam van het domein. Voer bijvoorbeeld `contoso.com` in. Gebruikers in de `contoso.com` domein kunt aanmelden met hun gebruikersnaam, zoals 'abby', in plaats van 'abby@contoso.com'.

  [Authentication/PreferredAadTenantDomainName CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-preferredaadtenantdomainname)

## <a name="per-app-privacy-exceptions"></a>Privacy-uitzonderingen per app

U kunt apps toevoegen waarvoor een ander privacybeleid moet gelden dan wat u hebt gedefinieerd als 'Standaardprivacy'.

- **Pakketnaam**: familienaam van het app-pakket.
- **App-naam**: de naam van de app.

### <a name="exceptions"></a>Uitzonderingen

- **Accountgegevens**: geef aan of deze app toegang heeft tot de gebruikersnaam, afbeelding en andere contactgegevens.
- **Achtergrond-apps**: geef aan of deze app op de achtergrond kan worden uitgevoerd.
- **Agenda**: geef aan of deze app toegang heeft tot de agenda.
- **Oproepgeschiedenis**: geef aan of deze app toegang heeft tot mijn oproepgeschiedenis.
- **Camera**: geef aan of deze app toegang heeft tot de camera.
- **Contactpersonen**: geef aan of deze app toegang heeft tot contactpersonen.
- **E-mail**: geef aan of deze app toegang heeft tot e-mail en of de app e-mail kan verzenden.
- **Locatie**: geef aan of deze app toegang heeft tot locatiegegevens.
- **Berichten**: geef aan of deze app sms- of mms-berichten kan lezen of verzenden.
- **Microfoon**: geef aan of deze app de microfoon kan gebruiken.
- **Beweging**: geef aan of deze app toegang heeft tot bewegingsinformatie van het apparaat.
- **Meldingen**: geef aan of deze app toegang heeft tot meldingen.
- **Telefoon**: geef aan of deze app toegang heeft tot de telefoon.
- **Radio's**: sommige apps maken gebruik van radio's (bijvoorbeeld Bluetooth) in uw apparaat voor het verzenden en ontvangen van gegevens en moeten deze radio's kunnen in- of uitschakelen. Geef aan of deze app deze radio's kan beheren.
- **Taken**: geef aan of deze app toegang heeft tot uw taken.
- **Vertrouwde apparaten**: Kies als deze app kan worden gebruikt voor het gebruik van vertrouwde apparaten. Onder vertrouwde apparaten wordt hardware verstaan die u al hebt aangesloten of die bij deze pc, tablet of telefoon wordt geleverd. Gebruik tv's, projectoren enzovoort bijvoorbeeld als vertrouwde apparaten.
- **Feedback en diagnostische gegevens**: geef aan of deze app toegang heeft tot diagnostische gegevens.
- **Synchroniseren met apparaten**: geef aan of deze app gegevens automatisch kan delen en synchroniseren met draadloze apparaten die niet expliciet aan dit apparaat zijn gekoppeld.

## <a name="personalization"></a>Persoonlijke instellingen

- **URL achtergrondafbeelding Bureaublad (alleen bureaublad)**: voer de URL in naar een afbeelding in JPEG-indeling die u wilt gebruiken als de achtergrond van het Windows-bureaublad. Gebruikers kunnen de afbeelding niet wijzigen.

## <a name="printer"></a>Printer

- **Printers**: lijst met lokale printers die zijn toegevoegd.
- **Standaardprinter**: stel de standaardprinter in.
- **Gebruikerstoegang om nieuwe printers toe te voegen**: het gebruik van lokale printers toestaan of blokkeren.

## <a name="privacy"></a>Privacy

- **Persoonlijke instellingen invoeren**: hiermee kunt u het gebruik van cloudspraakservices voor Cortana, de dicteerfunctie of Microsoft Store-apps blokkeren. Als u deze services toestaat, kan Microsoft spraakgegevens verzamelen voor het verbeteren van de service.
- **Automatische acceptatie van de goedkeuringsvensters voor koppelen en privacy**: hiermee kunt u instellen dat Windows automatisch toestemming mag geven voor bewerkingen met koppelen en privacy bij het uitvoeren van apps.
- **Gebruikersactiviteiten publiceren**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar te voorkomen.
- **Alleen lokale activiteiten**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar alleen op basis van de lokale activiteit te voorkomen.

U kunt informatie configureren die voor alle apps op het apparaat toegankelijk is. Definieer ook uitzonderingen op een per-app basis met **Privacyuitzonderingen per app**.

### <a name="exceptions"></a>Uitzonderingen

- **Accountgegevens**: geef aan of deze app toegang heeft tot de gebruikersnaam, afbeelding en andere contactgegevens.
- **Achtergrond-apps**: geef aan of deze app op de achtergrond kan worden uitgevoerd.
- **Agenda**: geef aan of deze app toegang heeft tot de agenda.
- **Oproepgeschiedenis**: geef aan of deze app toegang heeft tot mijn oproepgeschiedenis.
- **Camera**: geef aan of deze app toegang heeft tot de camera.
- **Contactpersonen**: geef aan of deze app toegang heeft tot contactpersonen.
- **E-mail**: geef aan of deze app toegang heeft tot e-mail en of de app e-mail kan verzenden.
- **Locatie**: geef aan of deze app toegang heeft tot locatiegegevens.
- **Berichten**: geef aan of deze app sms- of mms-berichten kan lezen of verzenden.
- **Microfoon**: geef aan of deze app de microfoon kan gebruiken.
- **Beweging**: geef aan of deze app toegang heeft tot bewegingsinformatie van het apparaat.
- **Meldingen**: geef aan of deze app toegang heeft tot meldingen.
- **Telefoon**: geef aan of deze app toegang heeft tot de telefoon.
- **Radio's**: sommige apps maken gebruik van radio's (bijvoorbeeld Bluetooth) in uw apparaat voor het verzenden en ontvangen van gegevens en moeten deze radio's kunnen in- of uitschakelen. Geef aan of deze app deze radio's kan beheren.
- **Taken**: geef aan of deze app toegang heeft tot uw taken.
- **Vertrouwde apparaten**: Kies als deze app kan worden gebruikt voor het gebruik van vertrouwde apparaten. Onder vertrouwde apparaten wordt hardware verstaan die u al hebt aangesloten of die bij deze pc, tablet of telefoon wordt geleverd. Gebruik tv's, projectoren enzovoort bijvoorbeeld als vertrouwde apparaten.
- **Feedback en diagnostische gegevens**: geef aan of deze app toegang heeft tot diagnostische gegevens.
- **Synchroniseren met apparaten**: geef aan of deze app gegevens automatisch kan delen en synchroniseren met draadloze apparaten die niet expliciet aan deze pc, tablet of telefoon zijn gekoppeld.

## <a name="projection"></a>Projectie

- **Gebruikersinvoer van ontvangers van draadloze schermen**: hiermee blokkeert u gebruikersinvoer van draadloze beeldschermen.
- **Projectie naar deze PC**: andere apparaten kunnen de pc niet meer vinden voor projectie.
- **Een pincode vereisen voor koppelen**: er is een pincode vereist voor het verbinden met een projectieapparaat.

## <a name="reporting-and-telemetry"></a>Rapportage en telemetrie

- **Gebruiksgegevens delen**: kies het niveau van diagnostische gegevens die worden verzonden. Uw opties zijn:
  - Beveiliging
  - Eenvoudig
  - Uitgebreid
  - Volledig
- **Microsoft Edge browsegegevens verzenden naar Microsoft 365 Analytics**: als u deze functie wilt gebruiken, stelt u **Gebruiksgegevens delen** in op **Uitgebreid** of **Volledig**. Deze functie bepaalt welke gegevens Microsoft Edge verstuurt naar Microsoft 365 Analytics voor zakelijke apparaten met een geconfigureerde commerciële id. Uw opties zijn:
  - **Niet geconfigureerd**: hiermee wordt het standaardgedrag van het besturingssysteem gebruikt, wat betekent dat er mogelijk geen browsegegevens worden verzonden.
  - **Alleen intranetgegevens verzenden**: hiermee kan de beheerder de geschiedenis van intranetgegevens verzenden
  - **Alleen internetgegevens verzenden**: hiermee kan de beheerder de geschiedenis van internetgegevens verzenden
  - **Intranet- en internetgegevens verzenden**: hiermee kan de beheerder de geschiedenis van intranet- en internetgegevens verzenden
- **Telemetrie-proxyserver**: geef de volledig gekwalificeerde domeinnaam (FQDN) of het IP-adres van een proxyserver op voor het doorsturen van Connected User Experiences en Telemetrie-aanvragen met behulp van een SSL-verbinding (Secure Sockets Layer). De indeling voor deze instelling is *server*:*poort*. Als de benoemde proxy niet werkt of als er geen proxy is opgegeven bij het inschakelen van dit beleid, worden de Connected User Experiences en Telemetrie-gegevens niet verzonden en blijven ze op het lokale apparaat.

  Voorbeelden van indelingen:

  ```
  IPv4: 192.246.246.106:100
  IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100
  FQDN: www.contoso.com:345
  ```

## <a name="search"></a>Zoeken

- **Veilig zoeken (alleen mobiel)**: hiermee bepaalt u hoe Cortana inhoud voor volwassenen filtert in de zoekresultaten. U kunt **Strikt** of **Gemiddeld** selecteren, of u kunt toestaan dat eindgebruikers hun eigen instellingen kiezen.
- **Webresultaten weergeven in zoekopdracht**: hiermee blokkeert u of staat u toe dat webresultaten worden weergegeven in zoekopdrachten die op het apparaat worden uitgevoerd.

## <a name="start"></a>start

- **Indeling van het menu Start**: u kunt het menu Start op desktopapparaten aanpassen door een XML-bestand met uw aanpassingen te uploaden, inclusief de volgorde waarin de apps worden vermeld en meer. Gebruikers kunnen de door u ingevoerde indeling van het menu Start niet wijzigen.
- **Websites vastmaken aan tegels in het menu Start**: importeer installatiekopieën van Microsoft Edge die als koppelingen worden weergegeven het menu Start van Windows voor desktopapparaten.
- **Apps losmaken van de taakbalk**: kies **Blokkeren** zodat de gebruiker geen apps meer kan losmaken van de taakbalk.
- **Snel schakelen tussen gebruikers**: kies **Blokkeren** om schakeling tussen gebruikers die gelijkertijd zijn aangemeld te voorkomen zonder hen af te melden.
- **Meest gebruikte apps**: kies **Blokkeren** om de meest gebruikte apps te verbergen het menu Start. Hiermee wordt ook de bijbehorende wisselknop in de Instellingen-app uitgeschakeld.
- **Onlangs toegevoegde apps**: kies **Blokkeren** om onlangs toegevoegde apps te verbergen in het menu Start. Hiermee wordt ook de bijbehorende wisselknop in de Instellingen-app uitgeschakeld.
- **Modus startscherm**: kies de manier waarop het startscherm moet worden weergegeven. Kies om het scherm op **Volledig scherm** of **Niet volledig scherm** weer te geven.
- **Onlangs geopende items in jumplists**: kies **Blokkeren** om recente jumplists te verbergen in het menu Start en in de taakbalk. Hiermee wordt ook de bijbehorende wisselknop in de Instellingen-app uitgeschakeld.
- **App-lijst**: kies de manier waarop de app Instellingen moet worden weergegeven. Uw opties zijn: 
  - Samenvouwen
  - De app Instellingen samenvouwen en uitschakelen 
  - Hiermee kunt u de app Instellingen verwijderen en uitschakelen
- **Aan/uit-knop**: kies **Blokkeren** om de aan/uit-knop in het menu Start te verbergen.
- **De tegel Gebruiker**: kies **Blokkeren** om de tegel Gebruiker in het menu Start te verbergen.
  - **Vergrendelen**: kies **Blokkeren** om de optie `Lock` op de tegel Gebruiker in het menu Start te verbergen.
  - **Afmelden**: kies **Blokkeren** om de optie `Sign out` op de tegel Gebruiker in het menu Start te verbergen.
- **Uitschakelen**: kies **Blokkeren** om de opties `Update and shut down` en `Shut down` op de aan-uitknop in het menu Start te verbergen.
- **Slaapstand**: kies **Blokkeren** om de optie `Sleep` op de aan-uitknop in het menu Start te verbergen.
- **Sluimerstand**: kies **Blokkeren** om de optie `Hibernate` op de aan-uitknop in het menu Start te verbergen.
- **Account wisselen**: kies **Blokkeren** om de optie `Switch account` op de tegel Gebruiker in het menu Start te verbergen.
- **Opties voor opnieuw opstarten**: kies **Blokkeren** om de opties `Update and restart` en `Restart` op de aan-uitknop in het menu Start te verbergen.
- **Documenten op het startscherm**: de map Documenten in het menu Start van Windows weergeven of verbergen.
- **Downloads op het startscherm**: de map Downloads in het menu Start van Windows weergeven of verbergen.
- **Bestandenverkenner op het startscherm**: de app Bestandsverkenner in het menu Start van Windows weergeven of verbergen.
- **Thuisgroep op het startscherm**: de map Thuisgroep in het menu Start van Windows weergeven of verbergen.
- **Muziek op het startscherm**: de map Muziek in het menu Start van Windows weergeven of verbergen.
- **Netwerk op het startscherm**: de map Netwerk in het menu Start van Windows weergeven of verbergen.
- **Persoonlijke instellingen op het startscherm**: de map met persoonlijke instellingen in het menu Start van Windows weergeven of verbergen.
- **Afbeeldingen op het startscherm**: de map Afbeeldingen in het menu Start van Windows weergeven of verbergen.
- **Instellingen op het startscherm**: de app Instellingen in het menu Start van Windows weergeven of verbergen.
- **Video's op het startscherm**: de map voor video's in het menu Start van Windows weergeven of verbergen.

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen voor Microsoft Edge**: hiermee schakelt u Microsoft Edge SmartScreen in voor toegang tot site- en bestanddownloads.
- **Toegang tot schadelijke sites**: verhinder dat gebruikers de waarschuwingen van het Windows Defender SmartScreen-filter negeren en verhinder dat ze naar de site kunnen gaan.
- **Niet-geverifieerd bestand downloaden**: verhinder dat gebruikers de waarschuwingen van het Windows Defender SmartScreen-filter negeren en verhinder dat ze niet-geverifieerde bestanden kunnen downloaden.

## <a name="windows-spotlight"></a>Windows Spotlight

- **Windows Spotlight**: gebruik deze instelling om alle functionaliteit van Windows Spotlight te blokkeren op Windows 10-apparaten. In dat geval zijn de volgende instellingen niet beschikbaar.
  - **Windows-spotlight in het vergrendelingsscherm**: instellen dat Windows Spotlight geen informatie weergeeft op het vergrendelingsscherm van het apparaat.
  - **Suggesties van derden in Windows-spotlight**: instellen dat Windows Spotlight geen inhoud mag voorstellen die niet is gepubliceerd door Microsoft.
  - **Consumentenfuncties**: hiermee kunt u functies voor consumenten blokkeren, zoals suggesties in het menu Start lidmaatschapsmeldingen.
  - **Windows Tips**: hiermee kunt u de weergave van pop-uptips in Windows blokkeren.
  - **Windows-spotlight in het Onderhoudscentrum**: suggesties van Windows Spotlight blokkeren, zodat bijvoorbeeld nieuwe apps of beveiligingsinhoud niet wordt vermeld in het actiecentrum van Windows.
  - **Persoonlijke instellingen voor Windows-spotlight**: instellen dat Windows Spotlight de weergave van resultaten aanpast op basis van het gebruik van een apparaat.
  - **Welkomstbericht van Windows**: geen informatie weergeven over nieuwe of bijgewerkte functies.

## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus

- **Realtime-controle**: hiermee schakelt u het realtime scannen op malware, spyware en andere ongewenste software in.
- **Gedragscontrole**: hiermee kunt u Defender laten controleren op de aanwezigheid van bepaalde bekende patronen van verdachte activiteiten op apparaten.
- **Netwerkinspectiesysteem (NIS)**: NIS helpt bij de bescherming van apparaten tegen aanvallen vanaf het netwerk. NIS maakt gebruik van handtekeningen van bekende beveiligingsproblemen uit het Microsoft Endpoint Protection Center om schadelijk netwerkverkeer te detecteren en blokkeren.
- **Alle downloads scannen**: hiermee bepaalt u of Windows Defender alle bestanden moet scannen die van internet worden gedownload.
- **Scripts scannen die in webbrowsers van Microsoft worden geladen**: hiermee geeft u aan dat Defender scripts moet scannen die worden gebruikt in Internet Explorer.
- **Toegang van eindgebruikers tot Defender**: hiermee geeft u aan of de gebruikersinterface van Windows Defender voor eindgebruikers wordt verborgen. Als deze instelling wordt gewijzigd, gaat de wijziging in wanneer de pc van de eindgebruiker de volgende keer opnieuw wordt opgestart.
- **Interval voor handtekeningupdates (in uren)**: hier geeft u het interval op waarmee Defender op nieuwe handtekeningbestanden moet controleren.
- **Activiteiten van bestanden en programma's bewaken**: hiermee staat u Defender toe activiteiten van bestanden en programma's op apparaten te bewaken.
- **Dagen voordat in quarantaine geplaatste malware wordt verwijderd**: blijven volgen opgeloste problemen met malware voor het aantal dagen dat u opgeeft, zodat u handmatig eerder aangevallen apparaten kunt controleren. Als u het aantal dagen instelt op **0**, blijft malware in de map Quarantaine staan en wordt malware niet automatisch verwijderd.
- **Limiet voor het CPU-gebruik tijdens het scannen**: hiermee kunt u de hoeveelheid CPU beperken die scans mogen gebruiken (tussen **1** en **100**).
- **Archiefbestanden scannen**: hiermee kunt u toestaan dat Defender gearchiveerde bestanden scant, zoals ZIP- of CAB-bestanden.
- **Inkomende e-mailberichten scannen**: hiermee kunt u toestaan dat Defender e-mailberichten scant wanneer deze op het apparaat binnenkomen.
- **Verwisselbare stations scannen tijdens een volledige scan**: hiermee kunt u toestaan dat Defender verwisselbare stations, zoals USB-sticks, scant.
- **Toegewezen netwerkschijven scannen tijdens een volledige scan**: hiermee kunt u Defender op toegewezen netwerkstations laten scannen.
  Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.
- **Bestanden die zijn geopend vanuit mappen op het netwerk scannen**: hiermee kunt u Defender bestanden op gedeelde stations laten scannen (bijvoorbeeld bestanden die via een UNC-pad toegankelijk zijn). Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.
- **Cloudbeveiliging**: hiermee kunt u toestaan of blokkeren dat de Microsoft Active Protection-service informatie ontvangt over malware-activiteit op apparaten die u beheert. Deze informatie wordt de service in de toekomst verbeterd.
- **Gebruikers vragen voordat een voorbeeld wordt verzonden**: hiermee bepaalt u of potentieel schadelijke bestanden waarvoor verdere analyse nodig is, automatisch naar Microsoft worden verzonden.
- **Tijd voor het uitvoeren van een dagelijkse snelle scan**: Kies een dagelijkse snelle scan uitvoeren voor het uur. **Niet geconfigureerd** dagelijks een scan kan niet worden uitgevoerd. Als u meer aanpassingsmogelijkheden wilt, configureert u de **Type systeemscan** instelling.

  [Defender/ScheduleQuickScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulequickscantime)
- **Type systeemscan**: plannen een systeemscan, met inbegrip van het niveau van het scannen, de dag en tijd om de scan. Uw opties zijn:
  - **Niet geconfigureerd**: een systeemscan op het apparaat niet plannen. Eindgebruikers kunnen scans handmatig als vereist of gewenst uitvoeren op hun apparaten.
  - **Uitschakelen**: schakelt een systeem scannen op het apparaat. Selecteer deze optie als u een partneroplossing antivirusprogramma's waarmee apparaten worden gescand.
  - **Snelle scan**: kijkt naar veelvoorkomende locaties wanneer er schadelijke software kan worden geregistreerd, zoals registersleutels en bekende opstartmappen in Windows.
    - **Geplande dag**: Kies de dag waarop de scan wordt uitgevoerd.
    - **Geplande tijd**: Kies het uur de scan uit te voeren.
  - **Volledige scan**: kijkt naar veelvoorkomende locaties waar er zijn mogelijk schadelijke software geregistreerd en ook scant alle bestanden en mappen op het apparaat.
    - **Geplande dag**: Kies de dag waarop de scan wordt uitgevoerd.
    - **Geplande tijd**: Kies het uur de scan uit te voeren.

  Deze instelling kan strijdig zijn met de **tijd voor het uitvoeren van een dagelijkse snelle scan** instelling. Een aantal aanbevelingen:

  - Als u wilt een dagelijkse snelle scan uitvoert, configureert de **tijd voor het uitvoeren van een dagelijkse snelle scan** instelling.
  - Als u wilt een dagelijkse snelle scan en een volledige scan elke week uitvoert, configureert u de **tijd voor het uitvoeren van een dagelijkse snelle scan**, en stel **Type systeemscan** aan een volledige scan met de datum en tijd.
  - Configureer niet de **tijd voor het uitvoeren van een dagelijkse snelle scan** tegelijkertijd instellen met de **Type systeemscan uit te voeren** ingesteld op **snelle scan**. Deze instellingen kunnen conflicteren en een scan kan niet worden uitgevoerd.
  - Als u wilt een snelle scan elke dinsdag wordt uitgevoerd om 06.00, configureert u de **Type systeemscan** instelling.

  [Defender/ScanParameter CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-scanparameter)  
  [Defender/ScheduleScanDay CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescanday)  
  [Defender/ScheduleScanTime CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-schedulescantime)

- **Mogelijk ongewenste toepassingen detecteren**: kies het niveau van beveiliging dat moet worden ingesteld als Windows toepassingen detecteert die mogelijk ongewenst zijn:
  - **Blokkeren**
  - **Controle** Zie [Detect and block potentially unwanted applications](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus) (Mogelijk ongewenste toepassingen detecteren en blokkeren) voor meer informatie over mogelijk ongewenste apps.
- **Acties voor gedetecteerde bedreiging van malware**: kies welke acties Defender moet uitvoeren voor de verschillende bedreigingsniveaus (Laag, Gemiddeld, Hoog en Ernstig). Uw opties zijn:
  - **Reinigen**
  - **Quarantaine**
  - **Verwijderen**
  - **Toestaan**
  - **Door de gebruiker gedefinieerd**
  - **Blokkeren**

### <a name="windows-defender-antivirus-exclusions"></a>Uitsluitingen voor Windows Defender Antivirus

- **Bestanden en mappen die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer bestanden aan de uitsluitingslijst toe, zoals **C:\pad** of **%ProgramFiles%\pad\bestandsnaam.exe**. Deze bestanden en mappen worden niet opgenomen in real-timescans of geplande scans.
- **Bestandsextensies die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer bestandsextensies zoals **jpg** of **txt** aan de uitsluitingslijst toe. Bestanden met deze extensies worden niet opgenomen in realtime-scans of geplande scans.
- **Processen die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer processen van het type **.exe**, **.com** of **.scr** aan de uitsluitingslijst toe. Deze processen worden niet opgenomen in real-timescans of geplande scans.

## <a name="next-steps"></a>Volgende stappen

Voor aanvullende technische details over elke instelling en welke edities van Windows worden ondersteund, raadpleegt u het naslagwerk [Windows 10 Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)
