---
title: Apparaatbeperkingsinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over de Microsoft Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op apparaten met Windows 10.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ac0348736e5975633776c86dee88555dfceb6919
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576882"
---
# <a name="device-restriction-for-windows-10-and-newer-settings-in-intune"></a>Apparaatbeperkingsinstellingen voor Windows 10 (en hoger) in Intune
In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met Windows 10.

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

> [!Note]
> Niet alle opties zijn beschikbaar in alle edities van Windows

## <a name="general"></a>Algemeen
- **Schermafbeelding (alleen mobiel)**: hiermee kan de gebruiker het apparaatscherm vastleggen als afbeelding.
- **Kopiëren en plakken (alleen mobiel)**: hiermee staat u kopieer- en plakbewerkingen tussen apps op het apparaat toe.
- **Registratie handmatig ongedaan maken**: hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen.
   - Deze beleidsinstelling wordt niet toegepast als de computer is toegevoegd aan Azure AD en automatische inschrijving is ingeschakeld. 
   - Deze beleidsinstelling geldt niet voor computers met Windows 10 Home.
- **Handmatige installatie van het basiscertificaat (alleen mobiel)**: de gebruiker kan niet langer basiscertificaten en tussenliggende CAP-certificaten handmatig installeren.

- **Camera**: hiermee kunt u het gebruik van de camera op het apparaat toestaan of blokkeren.
- **Bestandssynchronisatie met OneDrive**: hiermee blokkeert u dat het apparaat bestanden synchroniseert naar OneDrive.
- **Verwisselbare opslag**: hiermee geeft u op of er met het apparaat externe opslagapparaten, zoals SD-kaarten, kunnen worden gebruikt.
- **Geolocatie**: hiermee geeft u aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt.
- **Gedeeld internet**: hiermee staat u het gebruik van een gedeelde internetverbinding op het apparaat toe.
- **Telefoon opnieuw instellen**: hiermee bepaalt u of de gebruiker het apparaat kan wissen.
- **USB-verbinding (alleen mobiel)**: hiermee bepaalt u of apparaten via een USB-verbinding toegang kunnen krijgen tot externe opslagapparaten.
- **AntiTheft-modus (alleen mobiel)**: hiermee configureert u of de AntiTheft-modus van Windows is ingeschakeld.
- **Cortana**: hiermee schakelt u de spraakassistent Cortana in en uit.
- **Spraakopname (alleen mobiel)**: hiermee kunt u het gebruik van het spraakopnameapparaat van het apparaat toestaan of blokkeren.
- **Apparaatnaam wijzigen**: hiermee voorkomt u dat de eindgebruiker de apparaatnaam wijzigt (alleen voor Windows 10 Mobile)
- **Inrichtingspakketten toevoegen**: hiermee blokkeert u de runtime configuratieagent die inrichtingspakketten installeert.
- **Inrichtingspakketten verwijderen**: hiermee blokkeert u de runtime configuratieagent die inrichtingspakketten verwijdert.
- **Apparaatdetectie**: hiermee voorkomt u dat een apparaat wordt gedetecteerd door andere apparaten.
- **Taakwisselaar (alleen mobiel)**: hiermee blokkeert u de taakwisselaar op het apparaat.
- **Foutberichtvenster voor SIM-kaart (alleen mobiel)**: hiermee voorkomt u dat op het apparaat een foutbericht wordt weergegeven als er geen SIM-kaart wordt gedetecteerd.
- **Ink-werkruimte**: blokkeer gebruikers zodat ze geen toegang meer hebben tot de Ink-werkruimte. Als dit is ingesteld op **Niet geconfigureerd**, wordt de Ink-werkruimte ingeschakeld (de functie wordt ingeschakeld) en mag de gebruiker deze gebruiken boven het vergrendelingsscherm.
- **Automatisch opnieuw implementeren**: hiermee kunnen gebruikers met beheerdersrechten alle gebruikersgegevens en -instellingen verwijderen met **CTRL + Win + R** op het vergrendelingsscherm van het apparaat. Het apparaat wordt automatisch opnieuw geconfigureerd en opnieuw ingeschreven bij het beheer.
- **Gebruikers verplichten om verbinding te maken met het netwerk tijdens de configuratie van het apparaat (alleen Windows Insider)**: kies **Vereisen** om gebruikers er tijdens de installatie van Windows 10 toe te verplichten dat het apparaat verbinding kan maken met een netwerk voordat dit na de netwerkpagina verder kan gaan. Hoewel deze functie nog in preview is, moet deze instelling worden gebruikt door een Windows Insider build 1809 of hoger.

## <a name="password"></a>Wachtwoord
-   **Wachtwoord**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Vereist wachtwoordtype**: hiermee geeft u aan of het wachtwoord alleen numeriek of alfanumeriek moet zijn.
    -   **Minimale wachtwoordlengte**: alleen van toepassing op Windows 10 Mobile.
    -   **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voor apparaten met Windows 10: als BitLocker is ingeschakeld op het apparaat, wordt het in de herstelmodus van BitLocker gezet nadat het aanmelden het aantal keren dat u opgeeft is mislukt. Als BitLocker niet is ingeschakeld op het apparaat, is deze instelling niet van toepassing.
Voor Windows 10 Mobile-apparaten: nadat het aanmelden het aantal keren dat u opgeeft is mislukt, wordt het apparaat gewist.
    -   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u de hoeveelheid tijd op die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.
    -   **Wachtwoord verloopt (dagen)**: hiermee geeft u de hoeveelheid tijd op waarna het wachtwoord van een apparaat moet worden gewijzigd.
    -   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.
    -   **Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status (alleen voor Mobile)**: hiermee geeft u aan dat de gebruiker een wachtwoord moet opgeven om het apparaat te ontgrendelen (alleen voor Windows 10 Mobile).
    -   **Eenvoudige wachtwoorden**: hiermee kunt u instellen dat eenvoudige wachtwoorden zijn toegestaan, zoals 1111 en 1234. Met deze instelling kunt u ook het gebruik van afbeeldingswachtwoorden toestaan of blokkeren.
-   **Versleuteling**: Hiermee schakelt u versleuteling op doelapparaten in.

## <a name="personalization"></a>Persoonlijke instellingen

- **URL achtergrondafbeelding Bureaublad (alleen bureaublad)**: voer de URL in naar een afbeelding in JPEG-indeling die u wilt gebruiken als de achtergrond van het Windows-bureaublad. Gebruikers kunnen de afbeelding niet wijzigen.

## <a name="privacy"></a>Privacy

-   **Persoonlijke instellingen invoeren**: hiermee kunt u het gebruik van cloudspraakservices voor Cortana, de dicteerfunctie of Microsoft Store-apps blokkeren. Als u deze services toestaat, kan Microsoft spraakgegevens verzamelen voor het verbeteren van de service.
-   **Automatische acceptatie van de goedkeuringsvensters voor koppelen en privacy**: hiermee kunt u instellen dat Windows automatisch toestemming mag geven voor bewerkingen met koppelen en privacy bij het uitvoeren van apps.
- **Gebruikersactiviteiten publiceren**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar te voorkomen.
- **Alleen lokale activiteiten**: stel dit in op **Blokkeren** om gedeelde ervaringen en de detectie van recent gebruikte resources in de taakwisselaar alleen op basis van de lokale activiteit te voorkomen.

U kunt de informatie definiëren die voor alle apps op het apparaat toegankelijk is. U kunt ook uitzonderingen definiëren op een per-app basis met **Privacyuitzonderingen per app**.

### <a name="exceptions"></a>Uitzonderingen

- **Accountgegevens**: geef aan of deze app toegang heeft tot de gebruikersnaam, afbeelding en andere contactgegevens.
- **Achtergrond-apps**: geef aan of deze app kan worden uitgevoerd op de achtergrond.
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
- **Radio's**: sommige apps maken gebruik van radio's (bijvoorbeeld Bluetooth) in uw apparaat voor het verzenden en ontvangen van gegevens en moeten deze radio's kunnen inschakelen of uitschakelen. Geef aan of deze app deze radio's kan beheren.
- **Taken**: geef aan of deze app toegang heeft tot uw taken.
- **Vertrouwde apparaten**: geef aan of deze app gebruik kan maken van vertrouwde apparaten (hardware die u al hebt aangesloten of die bij deze pc, tablet of telefoon wordt geleverd). Bijvoorbeeld een tv, projectoren, enzovoort.
- **Feedback en diagnostische gegevens**: geef aan of deze app toegang heeft tot diagnostische gegevens.
- **Synchroniseren met apparaten**: geef aan of deze app gegevens automatisch kan delen en synchroniseren met draadloze apparaten die niet expliciet aan deze pc, tablet of telefoon zijn gekoppeld.

## <a name="per-app-privacy-exceptions"></a>Privacy-uitzonderingen per app

U kunt apps toevoegen waarvoor een ander privacybeleid moet gelden dan wat u hebt gedefinieerd als 'Standaardprivacy'.

- **Pakketnaam**: familienaam van het app-pakket.
- **App-naam**: de naam van de app.

### <a name="exceptions"></a>Uitzonderingen

- **Accountgegevens**: geef aan of deze app toegang heeft tot de gebruikersnaam, afbeelding en andere contactgegevens.
- **Achtergrond-apps**: geef aan of deze app kan worden uitgevoerd op de achtergrond.
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
- **Radio's**: sommige apps maken gebruik van radio's (bijvoorbeeld Bluetooth) in uw apparaat voor het verzenden en ontvangen van gegevens en moeten deze radio's kunnen inschakelen of uitschakelen. Geef aan of deze app deze radio's kan beheren.
- **Taken**: geef aan of deze app toegang heeft tot uw taken.
- **Vertrouwde apparaten**: geef aan of deze app gebruik kan maken van vertrouwde apparaten (hardware die u al hebt aangesloten of die bij deze pc, tablet of telefoon wordt geleverd). Bijvoorbeeld een tv, projectoren, enzovoort.
- **Feedback en diagnostische gegevens**: geef aan of deze app toegang heeft tot diagnostische gegevens.
- **Synchroniseren met apparaten**: geef aan of deze app gegevens automatisch kan delen en synchroniseren met draadloze apparaten die niet expliciet aan deze pc, tablet of telefoon zijn gekoppeld.

## <a name="locked-screen-experience"></a>Vergrendeld scherm

- **Meldingen van het Actiecentrum (alleen mobiel)**: hiermee kunt u meldingen van het actiecentrum op het vergrendelingsscherm van het apparaat weergeven (alleen Windows 10 Mobile).
- **Afbeeldings-URL vergrendelingsscherm (alleen bureaublad)**: geef de URL op naar een afbeelding in JPEG-indeling die wordt gebruikt als achtergrond van het Windows-vergrendelingsscherm. Gebruikers kunnen dit niet wijzigen.
-   **Time-out voor het scherm die door de gebruiker kan worden ingesteld (alleen mobiel)**: hiermee kunnen gebruikers de hoeveelheid tijd configureren 
-   **Cortana op vergrendeld scherm (alleen desktop)**: de gebruiker geen toestemming geven voor interactie met Cortana wanneer het vergrendelingsscherm wordt weergegeven op het apparaat (alleen Windows 10 voor desktops).
-   **Pop-upmeldingen op vergrendeld scherm**: geen waarschuwingsberichten weergeven op het vergrendelingsscherm van het apparaat.
-   **Time-out voor het scherm (alleen mobiel)**: hiermee geeft u de tijd in seconden op waarna het scherm wordt uitgeschakeld nadat het scherm is vergrendeld.

## <a name="app-store"></a>App Store

-   **App Store (alleen mobiel)**: hiermee kunt u het gebruik van de App Store op Windows 10 Mobile-apparaten inschakelen of blokkeren.
-   **Apps uit Store automatisch bijwerken**: apps die zijn geïnstalleerd vanuit Microsoft Store, kunnen automatisch worden bijgewerkt.
-   **Installatie van vertrouwde app**: voor apps die zijn ondertekend met een vertrouwd certificaat is sideloaden mogelijk.
-   **Ontgrendeling voor ontwikkelaars**: de eindgebruiker mag instellingen voor Windows-ontwikkelaars wijzigen, zoals het toestaan van sideloaden van apps.
-   **Gedeelde app-gegevens voor gebruikers**: apps mogen gegevens delen tussen verschillende gebruikers op hetzelfde apparaat.
-   **Alleen persoonlijke store gebruiken**: schakel dit in om toe te staan dat eindgebruikers apps downloaden uit uw privé-store.
-   **Uit Store afkomstige app starten**: alle apps uitschakelen die vooraf geïnstalleerd zijn op het apparaat of die zijn gedownload via Microsoft Store.
-   **Appgegevens installeren op systeemvolume**: apps kunnen geen gegevens opslaan op het systeemvolume van het apparaat.
-   **Apps installeren op systeemstation**: apps kunnen geen gegevens opslaan op het systeemstation van het apparaat.
-   **Game-DVR (alleen desktop)**: hiermee bepaalt u of het opnemen en uitzenden van games is toegestaan.
-   **Alleen voor apps uit de Store**: hiermee bepaalt u of gebruikers apps kunnen installeren vanuit andere locaties dan de App Store.

## <a name="microsoft-edge-browser"></a>Microsoft Edge-browser

-   **Microsoft Edge-browser (alleen mobiele apparaten)**: hiermee staat u het gebruik van de Microsoft Edge-webbrowser toe op het apparaat.
-   **Vervolgkeuzelijst van de adresbalk (alleen desktop)**: gebruik deze optie als u in Microsoft Edge geen lijst met suggesties wilt weergeven wanneer u typt in een vervolgkeuzelijst. Deze optie helpt bij het beperken van de netwerkbandbreedte die nodig is tussen Microsoft Edge en Microsoft-services.
-   **Favorieten synchroniseren tussen Microsoft-browsers (alleen desktop)**: hiermee kunnen favorieten worden gesynchroniseerd tussen Internet Explorer en Microsoft Edge.
-   **Do Not Track-headers verzenden**: hiermee configureert u de Microsoft Edge-browser zodanig, dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken.
-   **Cookies**: hiermee kunnen internetcookies in de browser op het apparaat worden opgeslagen.
-   **JavaScript**: hiermee staat u de uitvoering van scripts, zoals JavaScript, toe in de Microsoft Edge-browser.
-   **Pop-ups** pop-upvensters in de browser blokkeren (alleen van toepassing op Windows 10-desktop).
-   **Zoeksuggesties**: hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt.
-   **Intranetverkeer naar Internet Explorer sturen**: hiermee kunnen gebruikers intranetwebsites in Internet Explorer openen (alleen Windows 10 Desktop).
-   **Automatisch doorvoeren**: hiermee staat u gebruikers toe instellingen voor automatisch doorvoeren in de browser te wijzigen (alleen Windows 10 Desktop).
-   **Wachtwoordbeheer**: hiermee schakelt u de functie Wachtwoordbeheer van Microsoft Edge in of uit.
-   **Locatie van de lijst met websites van Bedrijfsmodus**: hiermee geeft u de plaats aan van de lijst met websites die in Bedrijfsmodus worden geopend. Gebruikers kunnen deze lijst niet bewerken.<br>(Alleen Windows 10 Desktop.)
-   **Ontwikkelhulpprogramma's**: hiermee voorkomt u dat de eindgebruiker de ontwikkelhulpprogramma's van Microsoft Edge opent.
-   **Extensies**: hiermee staat u toe dat de eindgebruiker Microsoft Edge-extensies installeert op het apparaat.
-   **InPrivate-navigatie**: hiermee voorkomt u dat de eindgebruiker InPrivate-navigatiesessies opent.
-   **Pagina voor eerste keer uitvoeren weergeven**: hiermee wordt de introductiepagina niet weergegeven wanneer Microsoft Edge de eerste keer wordt uitgevoerd.
    -   **URL voor eerste uitvoering**: hiermee geeft u de URL op van een pagina die wordt weergegeven wanneer een gebruiker de eerste keer Microsoft Edge uitvoert (alleen Windows 10 Mobile).
-   **Startpagina's**: hiermee kunt u een lijst met sites toevoegen die u wilt gebruiken als startpagina's in Microsoft Edge (alleen desktop).
-   **Wijzigingen van de startpagina**: hiermee kunnen gebruikers de startpagina's wijzigen die worden weergegeven bij het openen van Microsoft Edge. Gebruik de instelling Startpagina's om de pagina, of een lijst van pagina's, te maken die u wilt openen bij het starten van Microsoft Edge.
-   **Toegang tot About-vlaggen blokkeren**: Hiermee voorkomt u dat de eindgebruiker toegang krijgt tot de pagina met about-vlaggen in Microsoft Edge. Op deze pagina staan instellingen voor ontwikkelaars en experimentele instellingen.
-   **LocalHost IP-adres voor WebRTC**: hiermee blokkeert u het weergeven van het IP-adres van de localhost van gebruikers tijdens het doen van telefoonoproepen via het WebRTC-protocol.
-   **Standaardzoekmachine**: geef de zoekmachine op die u standaard wilt gebruiken. Eindgebruikers kunnen deze waarde op elk moment wijzigen.
-   **Browsegegevens wissen bij afsluiten**: hiermee worden de geschiedenis en de browsegegevens gewist wanneer de gebruiker Microsoft Edge afsluit.
-   **Verzamelen van livetegelgegevens**: hiermee geeft u op dat Windows geen gegevens moet verzamelen van de livetegel wanneer gebruikers vanuit Microsoft Edge een site vastmaken aan het startmenu.
-  **Lijst met favorieten**: hier vindt u het pad naar het favorietenbestand. Voorbeeld: http://contoso.com/favorites.html.
-  **Wijzigingen aan Favorieten beperken**: - stel dit in op **Blokkeren** om te voorkomen dat gebruikers items aan de lijst Favorieten toevoegen, of de lijst importeren, sorteren of bewerken. 

## <a name="windows-defender-smart-screen"></a>Windows Defender Smart Screen

- **SmartScreen voor Microsoft Edge**: schakel Microsoft Edge SmartScreen in voor toegang tot site- en bestanddownloads.
- **Toegang tot schadelijke sites**: verhinder dat gebruikers de waarschuwingen van het Windows Defender SmartScreen-filter negeren en verhinder dat ze naar de site kunnen gaan.
- **Niet-geverifieerd bestand downloaden**: verhinder dat gebruikers de waarschuwingen van het Windows Defender SmartScreen-filter negeren en verhinder dat ze niet-geverifieerde bestanden kunnen downloaden.

## <a name="search"></a>Zoeken
- **Veilig zoeken (alleen mobiel)**: hiermee bepaalt u hoe Cortana inhoud voor volwassenen filtert in de zoekresultaten. U kunt **Strikt** of **Gemiddeld** selecteren, of u kunt toestaan dat eindgebruikers hun eigen instellingen kiezen.
- **Display web results in search** (Webresultaten weergeven in zoekopdracht): hiermee blokkeert u of staat u toe dat webresultaten worden weergegeven in zoekopdrachten die op het apparaat worden uitgevoerd.

## <a name="cloud-and-storage"></a>Cloud en opslag
-   **Microsoft-account**: hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.
-   **Niet-Microsoft-account**: hiermee staat u toe dat de gebruiker e-mailaccounts aan het apparaat kan toevoegen die niet aan een Microsoft-account zijn gekoppeld.
-   **Synchronisatie van instellingen voor Microsoft-accounts**: hiermee staat u synchronisatie tussen apparaten toe van apparaat- en app-instellingen die aan een Microsoft-account zijn gekoppeld.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit

-   **Mobiel gegevenskanaal**: hiermee voorkomt u dat gebruikers toegang hebben tot gegevens, bijvoorbeeld tijdens het surfen op internet, wanneer ze zijn verbonden met een mobiel netwerk. 
-   **Dataroaming**: hiermee staat u roaming tussen netwerken toe tijdens het ophalen van data.
-   **VPN via het mobiele netwerk**: hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen indien verbonden met een mobiel netwerk.
-   **VPN-roaming via het mobiele netwerk**: hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen tijdens het roamen op een mobiele netwerk.
-   **Bluetooth**: hiermee bepaalt u of de gebruiker Bluetooth op het apparaat kan inschakelen en configureren.
-   **Bluetooth-detectie**: hiermee geeft u aan dat het apparaat kan worden gedetecteerd door andere Bluetooth-apparaten.
-   **Vooraf koppelen van Bluetooth**: hiermee kunt u instellen dat bepaalde Bluetooth-apparaten automatisch worden gekoppeld met een hostapparaat.
-   **Aankondigingen via Bluetooth**: hiermee geeft u aan dat het apparaat aankondigingen via Bluetooth kan ontvangen.
-   **Service voor verbonden apparaten**: hiermee kunt u opgeven of de service voor verbonden apparaten is toegestaan, waardoor detectie van en verbinding met andere Bluetooth-apparaten mogelijk is.
-   **NFC**: hiermee kan de gebruiker mogelijkheden voor Near Field Communications op het apparaat inschakelen en configureren.
-   **Wi-Fi**: hiermee kan de gebruiker Wi-Fi op het apparaat inschakelen en configureren (alleen voor Windows 10 Mobile).
-   **Automatisch verbinding maken met Wi-Fi-hotspots**: hiermee kunt u het apparaat automatisch verbinding laten maken met gratis Wi-Fi-hotspots en automatisch de voorwaarden voor de verbinding laten accepteren.
-   **Handmatige configuratie van Wi-Fi**: hiermee geeft u aan of de gebruiker zijn of haar eigen Wi-Fi-verbindingen kan instellen, of dat de gebruiker alleen verbindingen kan gebruiken die door een Wi-Fi-profiel zijn geconfigureerd (alleen voor Windows 10 Mobile).
-   **Wi-Fi-scaninterval**: geef op hoe vaak apparaten zoeken naar Wi-Fi-netwerken. Geef een waarde op tussen 1 (zo vaak mogelijk) en 500 (zo min mogelijk).
-   **Services waarvoor Bluetooth is toegestaan**: geef een lijst met toegestane Bluetooth-services en -profielen op, in de vorm van hexadecimale tekenreeksen.

## <a name="control-panel-and-settings"></a>Configuratiescherm en instellingen

-   **App Instellingen**: hiermee blokkeert u toegang tot de app Instellingen van Windows.
    -   **Systeem**: hiermee blokkeert u de toegang tot het systeemgebied van de app Instellingen.
        -   **Instellingen voor in-/uitschakelen en slaapstand wijzigen (alleen desktop)**: hiermee voorkomt u dat de eindgebruiker de instellingen voor in-/uitschakelen en de slaapstand op het apparaat wijzigt.
    -   **Apparaten**: hiermee blokkeert u de toegang tot het apparatengebied van de instellingen-app.
    -   **Netwerk en internet**: hiermee blokkeert u de toegang tot het gebied voor netwerk en internet van de instellingen-app.
    -   **Persoonlijke instellingen**: hiermee blokkeert u de toegang tot het gebied voor persoonlijke instellingen van de instellingen-app.
    -   **Accounts**: hiermee blokkeert u de toegang tot het accountsgebied van de instellingen-app.
    -   **Tijd en taal**: hiermee blokkeert u de toegang tot het gebied voor tijd en taal van de instellingen-app.
        -   **Systeemtijd wijzigen**: hiermee voorkomt u dat de eindgebruiker de datum en tijd van het apparaat wijzigt.
        -   **Regio-instellingen aanpassen (alleen desktop)**: hiermee voorkomt u dat de eindgebruiker de regionale instellingen op het apparaat wijzigt.
        -   **Taalinstellingen wijzigen (alleen bureaublad)**: hiermee voorkomt u dat de eindgebruiker de taalinstellingen op het apparaat wijzigt.
    -   **Gaming**: hiermee blokkeert u de toegang tot de gaming-app in Instellingen.
    -   **Betere toegankelijkheid**: hiermee blokkeert u de toegang tot het gebied voor betere toegankelijkheid van de instellingen-app.
    -   **Privacy**: hiermee blokkeert u de toegang tot het privacygebied van de instellingen-app.
    -   **Bijwerken en beveiliging**: hiermee blokkeert u de toegang tot het gebied voor updates en beveiliging van de instellingen-app.

## <a name="start"></a>start

- **Indeling van het menu Start**: u kunt het menu Start op desktopapparaten aanpassen door een XML-bestand met uw aanpassingen te uploaden, inclusief de volgorde waarin de apps worden vermeld en meer. Gebruikers kunnen de door u ingevoerde indeling van het menu Start niet wijzigen.
- **Websites vastmaken aan tegels in het menu Start**: importeer installatiekopieën van Microsoft Edge die als koppelingen worden weergegeven het menu Start van Windows voor desktopapparaten.
- **Apps losmaken van de taakbalk**: kies **Blokkeren** zodat de gebruiker geen apps meer kan losmaken vanuit het menu Start.
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

## <a name="display"></a>Weergave

- **GDI-schaalbaarheid voor apps inschakelen**
- **GDI-schaalbaarheid voor apps uitschakelen**

  Met GDI DPI-schaalbaarheid krijgen apps die geen DPI-status hebben, een per-monitor-DPI-status. Geef de verouderde apps op waarvoor GDI DPI-schaalbaarheid is ingeschakeld. Als GDI DPI-schaalbaarheid zodanig is geconfigureerd dat een app zowel in als uit kan worden ingeschakeld, wordt de schaalbaarheid voor de app uitgeschakeld.

## <a name="kiosk-preview---obsolete"></a>Kiosk (preview) - verouderd

Deze instellingen zijn alleen-lezen en kunnen niet worden gewijzigd. Zie [Kiosk-instellingen in Windows 10 en hoger](kiosk-settings.md) voor het configureren van de kioskmodus.

Op een kioskapparaat wordt doorgaans één app of een specifieke set met apps uitgevoerd. Gebruikers hebben geen toegang tot functies op het apparaat buiten de kiosk-apps.

- **Kioskmodus**: hiermee identificeert u het type kioskmodus dat wordt ondersteund door het beleid. Opties zijn onder andere:

  - **Niet geconfigureerd** (standaard): door het beleid wordt geen kioskmodus ingeschakeld. 
  - **Kiosk voor één enkele app**: volgens het profiel kan het apparaat slechts één enkele app uitvoeren. Wanneer de gebruiker zich aanmeldt, wordt een specifieke app gestart. Deze modus voorkomt ook dat de gebruiker nieuwe apps kan openen of de actieve app kan wijzigen.
  - **Kiosk voor meerdere apps**: volgens het profiel kan het apparaat meerdere apps uitvoeren. Alleen de apps die u toevoegt, zijn beschikbaar voor de gebruiker. Het voordeel van een kiosk voor meerdere apps, of apparaat voor een vast doel, is dat het een eenvoudige ervaring biedt voor gebruikers door alleen toegang te geven tot apps die ze nodig hebben en de apps die ze niet nodig hebben te verwijderen uit hun weergave.

#### <a name="single-app-kiosks"></a>Kiosken voor één enkele app
Voer de volgende instellingen in:

- **Gebruikersaccount**: voer het lokale (op het apparaat) gebruikersaccount, een AD-domeinaccount of een Azure AD-account in dat is gekoppeld aan de kiosk-app.
  - Lokaal account: voer in als `devicename\accountname`, `.\accountname` of `accountname`
  - Domeinaccount: voer in als `domain\accountname`
  - Azure AD-account: voer in als `AzureAD\emailaddress`. Zorg dat u AzureAD invoert, aangezien dit een vaste domeinnaam is. Voer vervolgens het Azure AD-e-mailadres in. Voer bijvoorbeeld `AzureAD\user@contoso.onmicrosoft.com` in.

    Voor kiosken in openbare omgevingen waarvoor automatische aanmelding is ingeschakeld, moet een gebruikerstype met minimale bevoegdheden (zoals het lokale standaardgebruikersaccount) worden gebruikt. Als u een Azure AD-account voor de kioskmodus gebruikt, voert u `AzureAD\user@yourorganization.com` in.

- **Model-id van toepassingsgebruiker (AUMID)**: voer de AUMID van de kiosk-app in. Zie [De model-id van toepassingsgebruiker van een geïnstalleerde app vinden](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) voor meer informatie.

#### <a name="multi-app-kiosks"></a>Kiosken voor meerdere apps
[Kiosken voor meerdere apps](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#configure-a-kiosk-in-microsoft-intune) gebruiken een configuratie met een lijst met toegestane apps en andere instellingen. 

Gebruik de knop **Toevoegen** om een kioskconfiguratie te maken (of een bestaande configuratie te selecteren). Voer vervolgens de volgende instellingen in:

- **De naam van de kioskconfiguratie**: voer een beschrijvende naam in voor de identificatie van de configuratie.

- **Kiosk-apps**: voer de apps in die beschikbaar in het menu Start. De apps die u toevoegt, zijn de enige apps die de gebruiker kan openen.

  - **App-type**: kies het type kiosk-app:
    - **Win32-App**: een traditionele bureaublad-app. U hebt de volledige padnaam nodig van het uitvoerbare bestand met betrekking tot het apparaat.
    - **UWP-app**: een universele Windows-app. U hebt de [AUMID voor de app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) nodig.

  - **Id**: voer de volledige padnaam van het uitvoerbare bestand (Win32-apps) of de [AUMID van de app](https://docs.microsoft.com/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP-apps) in.

- **Taakbalk**: stel in of u de taakbalk wilt **inschakelen** (weergeven) of **niet geconfigureerd** (verborgen) in de kiosk wilt gebruiken.

- **Indeling van het menu Start**: voer een XML-bestand in dat beschrijft hoe de apps worden weergegeven in het menu Start. [Customize and export Start layout (Aanpassen en indeling Start exporteren)](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout) biedt een aantal richtlijnen en een XML-voorbeeld.


  [Create a Windows 10 kiosk that runs multiple apps (Een Windows 10-kiosk maken voor meerdere apps)](https://docs.microsoft.com/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file) bevat meer informatie over het maken en gebruiken van XML-bestanden.

- **Toegewezen gebruikers**: voer een of meer gebruikersaccounts in die de apps kunnen gebruiken die u toevoegt. Wanneer een gebruiker zich met het account aanmeldt, zijn alleen de apps beschikbaar die in de configuratie zijn gedefinieerd. Het account is een lokaal account op het apparaat of een Azure AD-account dat is gekoppeld met de kiosk-app.

    Voor kiosken in openbare omgevingen waarvoor automatische aanmelding is ingeschakeld, moet een gebruikerstype met minimale bevoegdheden (zoals het lokale standaardgebruikersaccount) worden gebruikt. Voor de configuratie van een Azure Active Directory-account voor de kioskmodus gebruikt u de indeling `domain\user@tenant.com`.

## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus

-   **Realtime-controle**: hiermee schakelt u het realtime scannen op malware, spyware en andere ongewenste software in.
-   **Gedragscontrole**: hiermee kunt u Defender laten controleren op de aanwezigheid van bepaalde bekende patronen van verdachte activiteiten op apparaten.
-   **Netwerkinspectiesysteem (NIS)**: NIS helpt bij de bescherming van apparaten tegen aanvallen vanaf het netwerk. NIS maakt gebruik van handtekeningen van bekende beveiligingsproblemen uit het Microsoft Endpoint Protection Center om schadelijk netwerkverkeer te detecteren en blokkeren.
-   **Alle downloads scannen**: hiermee bepaalt u of Windows Defender alle bestanden moet scannen die van internet worden gedownload.
-   **Scripts scannen die in webbrowsers van Microsoft worden geladen**: hiermee geeft u aan dat Defender scripts moet scannen die worden gebruikt in Internet Explorer.
-   **Toegang van eindgebruikers tot Defender**: hiermee geeft u aan of de gebruikersinterface van Windows Defender voor eindgebruikers wordt verborgen.
Als deze instelling wordt gewijzigd, gaat de wijziging in wanneer de pc van de eindgebruiker de volgende keer opnieuw wordt opgestart.
-   **Interval voor handtekeningupdates (in uren)**: hiermee geeft u het interval op waarmee Defender op nieuwe handtekeningbestanden controleert.
-   **Activiteiten van bestanden en programma's bewaken**: hiermee staat u Defender toe activiteiten van bestanden en programma's op apparaten te bewaken.
-   **Het aantal dagen voordat in quarantaine geplaatste malware wordt verwijderd**: hiermee kunt u Defender gedurende het aantal dagen dat u opgeeft, opgeloste malware laten bijhouden, zodat u handmatig eerder aangevallen apparaten kunt controleren. Als u het aantal dagen instelt op **0**, blijft malware in de map Quarantaine staan en wordt malware niet automatisch verwijderd.
-   **Limiet voor het CPU-gebruik tijdens het scannen**: hiermee kunt u de hoeveelheid CPU beperken die scans mogen gebruiken (tussen **1** en **100**).
-   **Archiefbestanden scannen**: hiermee kunt u toestaan dat Defender gearchiveerde bestanden scant, zoals ZIP- of CAB-bestanden.
-   **Inkomende e-mailberichten scannen**: hiermee kunt u toestaan dat Defender e-mailberichten scant wanneer deze op het apparaat binnenkomen.
-   **Verwisselbare stations scannen tijdens een volledige scan**: hiermee kunt u toestaan dat Defender verwisselbare stations, zoals USB-sticks, scant.
-   **Toegewezen netwerkschijven scannen tijdens een volledige scan**: hiermee kunt u Defender op toegewezen netwerkstations laten scannen.<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.
-   **Bestanden die zijn geopend vanuit mappen op het netwerk scannen**: hiermee kunt u Defender bestanden op gedeelde stations laten scannen (bijvoorbeeld bestanden die via een UNC-pad toegankelijk zijn).
Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.
-   **Cloudbeveiliging**: hiermee kunt u toestaan of blokkeren dat de Microsoft Active Protection-service informatie ontvangt over malware-activiteit op apparaten die u beheert. Deze informatie wordt gebruikt om de service in de toekomst te verbeteren.
-   **Gebruikers vragen voordat een voorbeeld wordt verzonden**: hiermee bepaalt u of potentieel schadelijke bestanden waarvoor verdere analyse nodig is, automatisch naar Microsoft worden verzonden.
-   **Tijd waarop een dagelijkse snelle scan moet worden uitgevoerd**: hiermee kunt u een snelle scan plannen die dagelijks wordt uitgevoerd op het moment dat u selecteert.
-   **Type systeemscan dat moet worden uitgevoerd**: hiermee kunt u het niveau opgeven waarop moet worden gescand tijdens een geplande systeemscan.
-   **Mogelijk ongewenste toepassingen detecteren**: kies het niveau van beveiliging dat moet worden ingesteld als Windows toepassingen detecteert die mogelijk ongewenst zijn:
        - **Blokkeren**
        - **Controle**. Zie [dit onderwerp](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus) voor meer informatie over mogelijk ongewenste apps.
-   **Acties voor gedetecteerde bedreiging van malware**: schakel deze optie in om de acties op te geven die Defender moet uitvoeren voor de verschillende bedreigingsniveaus (Laag, Gemiddeld, Hoog en Ernstig). U kunt kiezen uit deze acties:
    -   **Reinigen**
    -   **Quarantaine**
    -   **Verwijderen**
    -   **Toestaan**
    -   **Door de gebruiker gedefinieerd**
    -   **Blokkeren**

### <a name="windows-defender-antivirus-exclusions"></a>Uitsluitingen voor Windows Defender Antivirus

-   **Bestanden en mappen die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer bestanden aan de uitsluitingslijst toe, zoals **C:\pad** of **%ProgramFiles%\pad\bestandsnaam.exe**. Deze bestanden en mappen worden niet opgenomen in real-timescans of geplande scans.
-   **Bestandsextensies die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer bestandsextensies zoals **jpg** of **txt** aan de uitsluitingslijst toe. Bestanden met deze extensies worden niet opgenomen in realtime-scans of geplande scans.
-   **Processen die moeten worden uitgesloten van scans en de realtime-beveiliging**: hiermee voegt u een of meer processen van het type **.exe**, **.com** of **.scr** aan de uitsluitingslijst toe. Deze processen worden niet opgenomen in real-timescans of geplande scans.

## <a name="network-proxy"></a>Netwerkproxy

-   **Proxy-instellingen automatisch detecteren**: wanneer deze optie is ingeschakeld, probeert het apparaat het pad naar een PAC-script te vinden.
-   **Proxyscript gebruiken**: selecteer deze optie als u een pad naar een PAC-script wilt opgeven om de proxyserver te configureren.
    -   **URL voor het installatiescriptadres**: geef de URL op van een PAC-script dat u wilt gebruiken om de proxyserver te configureren.
-   **Handmatige proxyserver gebruiken**: selecteer deze optie om de gegevens van de proxyserver handmatig in te voeren.
    -   **Adres**: voer de naam of het IP-adres van de proxyserver in.
    -   **Poortnummer**: voer het poortnummer van uw proxyserver in.
    -   **Proxy-uitzonderingen**: voer URL's in die geen gebruik mogen maken van de proxyserver. Scheid de items van elkaar met een puntkomma.
    -   **Proxyserver niet gebruiken voor lokale adressen**: schakel deze optie in als u de proxyserver niet wilt gebruiken voor lokale adressen in uw intranet.

## <a name="windows-spotlight"></a>Windows Spotlight

- **Windows Spotlight**: gebruik deze instelling om alle functionaliteit van Windows Spotlight te blokkeren op Windows 10-apparaten. In dat geval zijn de volgende instellingen niet beschikbaar.
    - **Windows-spotlight in het vergrendelingsscherm**: instellen dat Windows Spotlight geen informatie weergeeft op het vergrendelingsscherm van het apparaat.
    - **Suggesties van derden in Windows-spotlight**: instellen dat Windows Spotlight geen inhoud mag voorstellen die niet is gepubliceerd door Microsoft.
    - **Consumentenfuncties**: hiermee kunt u functies voor consumenten blokkeren, zoals suggesties in het menu Start lidmaatschapsmeldingen.
    - **Windows Tips**: hiermee kunt u de weergave van pop-uptips in Windows blokkeren.
    - **Windows-spotlight in het Onderhoudscentrum**: suggesties van Windows Spotlight blokkeren, zodat bijvoorbeeld nieuwe apps of beveiligingsinhoud niet wordt vermeld in het actiecentrum van Windows.
    - **Persoonlijke instellingen voor Windows-spotlight**: instellen dat Windows Spotlight de weergave van resultaten aanpast op basis van het gebruik van een apparaat.
    - **Welkomstbericht van Windows**: geen informatie weergeven over nieuwe of bijgewerkte functies.

## <a name="projection"></a>Projectie

- **Gebruikersinvoer van ontvangers van draadloze schermen**: hiermee blokkeert u gebruikersinvoer van draadloze beeldschermen.
- **Projectie naar deze PC**: andere apparaten kunnen de pc niet meer detecteren voor projectie.
- **Een pincode vereisen voor koppelen**: er is een pincode vereist voor het verbinden met een projectieapparaat.

## <a name="cloud-printer"></a>Cloudprinter

- **Printerdetectie-URL**: voer de URL in voor het detecteren van cloudprinters.
- **Verificatie-URL voor printertoegang**: voer de URL van het verificatie-eindpunt in om OAuth-tokens op te halen. Voer bijvoorbeeld iets in zoals `https://login.microsoftonline.com/your Azure AD Tenant ID`.
- **GUID van de systeemeigen client-app voor Azure**: voer de GUID in waarmee de clienttoepassing wordt geïdentificeerd die gemachtigd is voor het ophalen van OAuth-tokens van OAuthAuthority.
- **Resource-URI voor de afdrukservice**: voer de OAuth-resource-URI in voor de afdrukservice zoals geconfigureerd in Azure Portal. Voer bijvoorbeeld iets in zoals `http://MicrosoftEnterpriseCloudPrint/CloudPrint`.
- **Maximumaantal printers waarvoor een query moet worden uitgevoerd (alleen mobiel)**: voer het maximumaantal printers in waarvoor u een query wilt uitvoeren. Voer bijvoorbeeld `10` in.
- **Resource-URI voor de printerdetectieservice**: voer de OAuth-resource-URI in voor de printerdetectieservice zoals geconfigureerd in Azure Portal. Voer bijvoorbeeld iets in zoals `http://MopriaDiscoveryService/CloudPrint`.

> [!TIP]
> Na het instellen van een [Windows Server Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-overview) kunt u deze instellingen configureren en vervolgens implementeren naar Windows-apparaten.

## <a name="local-printer"></a>Lokale printer
- **Printers**: lijst met lokale printers die zijn toegevoegd.
- **Standaardprinter**: stel de standaardprinter in.
- **Gebruikerstoegang om nieuwe printers toe te voegen**: het gebruik van lokale printers toestaan of blokkeren.

## <a name="reporting-and-telemetry"></a>Rapportage en telemetrie

- **Gebruiksgegevens delen**: selecteer het niveau voor het verzenden van diagnostische gegevens.
- **Telemetrie-proxyserver**

  Geef de volledig gekwalificeerde domeinnaam (FQDN) of het IP-adres van een proxyserver op voor het doorsturen van Connected User Experiences en Telemetrie-aanvragen met behulp van een SSL-verbinding (Secure Sockets Layer). De indeling voor deze instelling is *server*:*poort*. Als de benoemde proxy niet werkt of als er geen proxy is opgegeven wanneer dit beleid is ingeschakeld, worden de Connected User Experiences en Telemetrie-gegevens niet verzonden en blijven ze op het lokale apparaat.

   Voorbeelden van indelingen:

   IPv4: 192.246.246.106:100<br>
 IPv6: [2001:4898:4010:4013:95c1:a8b2:953c:c633]:100<br> FQDN: www.contoso.com:345

## <a name="messaging"></a>Messaging

- **Berichten synchroniseren (alleen mobiel)**: schakel back-up en herstel van Berichten overal en tekstberichten uit.
- **Mms (alleen mobiel)**: schakel de Mms-functie voor verzenden/ontvangen op het apparaat uit.
- **Rcs (alleen mobiel)**: schakel de Rich Communication Services-functie voor verzenden/ontvangen op het apparaat uit.

## <a name="more-information"></a>Meer informatie
Voor aanvullende technische details over elke instelling en welke edities van Windows worden ondersteund, raadpleegt u het naslagwerk [Windows 10 Policy CSP](https://docs.microsoft.com/en-us/windows/client-management/mdm/policy-configuration-service-provider)
