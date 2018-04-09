---
title: Microsoft Intune-apparaatbeperkingsinstellingen voor iOS
titleSuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op iOS-apparaten.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/1/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 436be436991ea4f2f295291fb95122cddf4e7ac5
ms.sourcegitcommit: a22309174e617e59ab0cdd0a55abde38711a5f35
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2018
---
# <a name="microsoft-intune-ios-device-restriction-settings"></a>iOS-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met iOS.

## <a name="general"></a>Algemeen

-   **Gebruiksgegevens delen**: stel in of het apparaat wel of niet diagnostische gegevens en gebruikstelemetriegegevens naar Apple mag verzenden.
-   **Verzenden van diagnostische gegevens**: hiermee kunt u verzending van diagnostische gegevens naar Apple voor het apparaat toestaan of blokkeren.
-   **Schermafbeelding**: hiermee staat u de gebruiker toe om de inhoud van het scherm vast te leggen als afbeelding.
    - **Observatie van extern scherm met de app Classroom (alleen onder supervisie)**: hiermee kunt u toestaan of voorkomen dat de app Apple Classroom het scherm van iOS-apparaten kan bekijken.
    - **Ongevraagde observatie van scherm met de app Classroom (alleen onder supervisie)**: indien toegestaan, kunnen docenten het scherm op de iOS-apparaten van leerlingen/studenten met de app Classroom observeren zonder dat de leerlingen/studenten dit weten.
-   **Niet-vertrouwde TLS-certificaten**: hiermee staat u niet-vertrouwde TLS-certificaten (Transport Layer Security) op het apparaat toe.
-   **Bedrijfsapps vertrouwen**: hiermee kan de gebruiker aangeven apps te vertrouwen die niet uit de App Store zijn gedownload.
- **Accountwijzigingen (alleen onder toezicht)**: wanneer deze optie is geblokkeerd, kan de gebruiker geen apparaatspecifieke instellingen wijzigen in de app voor iOS-instellingen, zoals het maken van nieuwe accounts voor het apparaat en het wijzigen van de gebruikersnaam en het wachtwoord.
Dit geldt ook voor instellingen die toegankelijk zijn vanuit de app voor iOS-instellingen, zoals de instellingen voor e-mail, contactpersonen, agenda, Facebook en Twitter. Dit geldt niet voor apps met accountinstellingen die niet in de app voor iOS-instellingen kunnen worden geconfigureerd, zoals de Microsoft Outlook-app.
- **Door de gebruiker inschakelen van beperkingen in de apparaatinstellingen (alleen onder supervisie)**: hiermee staat u de gebruiker toe beperkingen voor het apparaat te configureren (ouderlijk toezicht).
- **Het gebruik van de optie voor het wissen van alle inhoud en instellingen op het apparaat (alleen onder supervisie)**: hiermee staat u de gebruiker toe de optie voor het wissen van alle inhoud en instellingen op het apparaat te gebruiken.
- **Wijzigen van apparaatnaam (alleen onder supervisie)**: hiermee staat u de gebruiker toe de naam van het apparaat te wijzigen.
- **Wijzigen van de meldingsinstellingen (alleen onder supervisie)**: hiermee staat u de gebruiker toe de instellingen voor apparaatmeldingen te wijzigen.
- **Het wijzigen van de vertrouwensinstellingen voor bedrijfsapps (alleen onder supervisie)**: hiermee kan de gebruiker aangeven apps te vertrouwen die niet uit de App Store zijn gedownload.
- **Wijzigingen in configuratieprofielen (alleen onder toezicht)**: hiermee staat u de gebruiker toe configuratieprofielen te installeren.
- **Activeringsslot (alleen onder toezicht)**: hiermee schakelt u Activeringsslot in op iOS-apparaten in de supervisiemodus.

## <a name="configurations-requiring-supervision"></a>Configuraties die supervisie vereisen

De supervisiemodus voor iOS kan alleen worden ingeschakeld tijdens de initiële installatie van het apparaat via het Device Enrollment Program van Apple of met behulp van Apple Configurator. Zodra de supervisiemodus is ingeschakeld, kunt u in Intune een apparaat configureren met de volgende functionaliteit:

- App-vergrendeling (modus voor één app) 
- Algemene HTTP-proxy 
- Activeringsslot overslaan 
- Autonome modus voor één app 
- Webinhoudsfilter 
- Achtergrond en vergrendelingsscherm instellen 
- Stille app-push 
- Permanente VPN 
- Installatie van beheerde app exclusief toestaan 
- iBookstore 
- iMessages 
- Game Center 
- AirDrop 
- AirPlay 
- Koppelen aan host 
- Cloudsynchronisatie 
- Zoeken met Spotlight 
- Handoff 
- Apparaat wissen 
- Beperkingen voor gebruikersinterface 
- Installatie van configuratieprofielen per gebruikersinterface 
- Nieuws 
- Sneltoetsen 
- Wijzigingen van de wachtwoordcode 
- Wijzigingen van de apparaatnaam 
- Automatisch downloaden van apps 
- Wijzigingen in Bedrijfsapps vertrouwen 
- Apple Music 
- Binnenkomende e-mail 
- Koppelen aan Apple Watch 

> [!NOTE]
> Apple heeft bevestigd dat bepaalde instellingen worden verplaatst naar alleen onder supervisie in 2018. We raden u aan hiermee rekening te houden wanneer u deze instellingen gebruikt in plaats van dat u wacht totdat Apple deze migreert naar alleen onder supervisie:
> - App-installatie door eindgebruikers
> - App verwijderen
> - FaceTime
> - Safari
> - iTunes
> - Expliciete inhoud
> - iCloud-documenten en -gegevens
> - Games voor meerdere spelers
> - Game Center-vrienden toevoegen

## <a name="password"></a>Wachtwoord
-   **Wachtwoord**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
    -   **Eenvoudige wachtwoorden**: hiermee staat u het gebruik van eenvoudige wachtwoorden toe, zoals 0000 en 1234.
    -   **Vereist wachtwoordtype**: hiermee geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek.
    -   **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: hiermee geeft u het aantal symbooltekens (zoals **#** of **@**) op dat het wachtwoord moet bevatten.
    -   **Minimale wachtwoordlengte**: hiermee geeft u het minimum aantal tekens op voor het wachtwoord.
    -   **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee geeft u het aantal mislukte aanmeldingspogingen op dat is toegestaan voordat het apparaat wordt gewist.
    -   **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** <sup>1</sup>: hiermee geeft u op hoelang het apparaat inactief moet zijn voordat gebruikers hun wachtwoord opnieuw moeten invoeren.
    -   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**<sup>1</sup>: hiermee geeft u het aantal minuten op waarna het apparaatscherm wordt uitgeschakeld.
    -   **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.
    -   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.
    -   **Vingerafdruk ontgrendelen**: hiermee staat u toe dat compatibele apparaten kunnen worden ontgrendeld met een vingerafdruk.
- **Wachtwoordcode wijzigen (alleen onder supervisie)**: hiermee kan de wachtwoordcode niet langer worden gewijzigd, toegevoegd of verwijderd.
    - **Wijziging van vingerafdruk (alleen onder supervisie)**: hiermee kan de gebruiker TouchID-instellingen niet langer wijzigen, toevoegen of verwijderen.

<sup>1</sup> Wanneer u de instellingen **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld** en **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **vijf** minuten, wordt het scherm na vijf minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens vijf minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat vijf minuten later vergrendeld.

## <a name="locked-screen-experience"></a>Vergrendeld scherm

-   **Toegang tot Beheercentrum wanneer het apparaat is vergrendeld**: hiermee staat u toegang tot de Control Center-app toe terwijl het apparaat is vergrendeld.
-   **Meldingen wanneer het apparaat is vergrendeld**: hiermee staat u de gebruiker toegang tot de weergave van meldingen toe zonder het apparaat te ontgrendelen.
-   **Passbook wanneer het apparaat is vergrendeld**: hiermee staat u de gebruiker toegang tot de app Passbook toe terwijl het apparaat is vergrendeld.
-   **De weergave Vandaag wanneer het apparaat is vergrendeld**: hiermee staat u de gebruiker toe de weergave Vandaag te bekijken wanneer het apparaat is vergrendeld.

## <a name="app-store-doc-viewing-gaming"></a>App Store, documenten bekijken, gamen


-   **App Store**: hiermee blokkeert u de toegang tot de App Store op apparaten onder toezicht.
    - **Apps installeren via de App Store (alleen onder supervisie)**: hiermee blokkeert u de App Store vanaf het startscherm van het apparaat. Eindgebruikers kunnen iTunes nog steeds gebruiken of met Apple Configurator apps installeren.
    - **Automatisch downloaden van apps (alleen onder supervisie)**: hiermee kunnen apps die via een ander iOS-apparaat zijn gekocht, niet meer op dit apparaat worden gedownload.
-   **Wachtwoord voor toegang tot de App Store**: hiermee geeft u aan dat gebruikers een wachtwoord moeten invoeren voordat ze de App Store kunnen bezoeken.
-   **Aankopen in app**: hiermee staat u toe dat Store-aankopen kunnen worden uitgevoerd vanuit een actieve app.
-   **Expliciete muziek, podcasts of nieuwsinhoud in iTunes (alleen onder toezicht)**: hiermee staat u het apparaat toegang tot inhoud in de Store voor volwassenen toe.
-   **Inhoud die in de iBooks Store als Erotisch is gemarkeerd, downloaden**: hiermee staat u de gebruiker toe als erotisch aangeduide boeken te downloaden.
-   **Zakelijke documenten weergeven in niet-beheerde apps**: hiermee staat u toe dat zakelijke documenten kunnen worden weergegeven in elke app.<br>**Voorbeeld:** u wilt voorkomen dat gebruikers bestanden uit de OneDrive-app opslaan in Dropbox. Stel deze instelling in op Nee. Nadat het apparaat het beleid heeft ontvangen (bijvoorbeeld nadat het opnieuw is opgestart), kunnen er geen bestanden meer worden opgeslagen.
-   **Niet-zakelijke documenten weergeven in zakelijke apps**: hiermee staat u toe dat elk document kan worden weergegeven in zakelijke beheerde apps.
-   **AirDrop behandelen als een onbeheerd doel**: hiermee wordt het verzenden van gegevens door beheerde apps via Airdrop gestopt.
-   **Game Center-vrienden toevoegen (alleen onder toezicht)**: hiermee staat u de gebruiker toe vrienden toe te voegen in Game Center.
-   **Game Center (alleen onder supervisie)**: hiermee kunt u het gebruik van de app Game Center blokkeren of inschakelen.
-   **Games voor meerdere spelers (alleen onder toezicht)**: hiermee staat u de gebruiker toe op het apparaat games voor meerdere spelers te spelen.
-   **Classificatieregio**: kies de classificatieregio waarvoor u toegestane downloads wilt configureren en kies vervolgens de toegestane classificaties voor **Films** en **Tv-programma's**.
-   **Apps**: kies de toegestane leeftijdscategorie van apps die gebruikers kunnen downloaden of kies **Alle apps toestaan**.

## <a name="built-in-apps"></a>Ingebouwde apps

-   **Camera**: hiermee kunt u aangeven of de camera op het apparaat kan worden gebruikt.
    -   **FaceTime**: hiermee staat u toe dat de FaceTime-app op het apparaat mag worden gebruikt.
-   **Siri**: hiermee staat u het gebruik van de spraakassistent Siri op het apparaat toe.
    -   **Siri wanneer het apparaat is vergrendeld**: hiermee staat u het gebruik van de spraakassistent Siri op het apparaat toe terwijl het apparaat is vergrendeld.
    -   **Siri-filter voor scheldwoorden (alleen onder toezicht)**: hiermee voorkomt u het dicteren van grove taal met Siri of dat Siri grove taal spreekt.
    -   **Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet (alleen onder toezicht)**: hiermee staat u Siri toe websites te raadplegen om vragen te beantwoorden.
- **Apple Nieuws (alleen onder supervisie)**: hiermee staat u het gebruik van de app Apple News toe.
- **iBooks Store (alleen onder supervisie)**: hiermee staat u de gebruiker toe om door boeken in de iBooks Store te bladeren en om boeken te kopen.
- **De app Berichten op het apparaat (alleen onder supervisie)**: hiermee staat u toe dat de app Berichten op sms-berichten mag verzenden en lezen.
- **Podcasts (alleen onder supervisie)**: hiermee staat u het gebruik van Podcasts toe.
- **Service Music (alleen onder supervisie)**: hiermee staat u het gebruik van de app Apple Music toe.
- **iTunes Radio-service (alleen onder supervisie)**: hiermee staat u het gebruik van de app iTunes Radio toe.
- **Wijzigingen in de instellingen van de app Zoek vrienden (alleen onder supervisie)**: hiermee staat u toe dat de gebruiker de instellingen van de app Zoek vrienden kan wijzigen.
- **Spotlight-zoekacties voor de weergave van resultaten op internet (alleen onder toezicht)**: hiermee staat u toe dat Spotlight zoekt op en verbinding maakt met internet voor aanvullende resultaten.

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

- Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren. Zo wordt niet voorkomen dat gebruikers een niet-toegestane app installeren, maar als zij dit doen, wordt het aan u gemeld.
- Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Gebruikers mogen geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Zo wordt niet voorkomen dat gebruikers een app installeren die niet op de lijst met goedgekeurde apps staat, maar als zij dit doen, wordt het aan u gemeld.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met apps, gebruikt u de volgende notatie:

Gebruik een zoekmachine om de app te zoeken die u wilt gebruiken in de iTunes App Store en open de pagina voor de app.
Kopieer de URL van de pagina en gebruik deze als de URL voor het configureren van de lijst met toegestane of niet-toegestane apps of voor een app die u wilt uitvoeren in kioskmodus.
Apparaatprofielen die instellingen voor beperkte apps bevatten, moeten worden toegewezen aan groepen met gebruikers.

Voorbeeld: Zoek naar Microsoft Word voor iPad. U gebruikt hiervoor de URL https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> U kunt ook iTunes gebruiken om de app op te zoeken en vervolgens de opdracht **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst te vullen met waarden uit een CSV-bestand in de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*>. Of klik op **Exporteren** om een CSV-bestand (met dezelfde indeling) te maken met de inhoud van de lijst met beperkte apps.

## <a name="show-or-hide-apps-supervised-only"></a>Apps weergeven of verbergen (alleen onder supervisie)

In de lijst Apps weergeven of verbergen kunt u een van de volgende lijsten configureren (vereist toezicht voor apparaten met iOS 9.3 of hoger).

Lijst met **verborgen apps**: een lijst met apps opgeven die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
Lijst met **zichtbare apps**: een lijst met apps opgeven die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met apps, gebruikt u de volgende notatie:

Gebruik een zoekmachine om de app te zoeken die u wilt gebruiken in de iTunes App Store en open de pagina voor de app.
Kopieer de URL van de pagina en gebruik deze als de URL voor het configureren van de lijst met toegestane of niet-toegestane apps of voor een app die u wilt uitvoeren in kioskmodus.

Voorbeeld: Zoek naar Microsoft Word voor iPad. U gebruikt hiervoor de URL https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> U kunt ook de iTunes-software gebruiken om de app te zoeken en vervolgens de opdracht **Koppeling kopiëren** gebruiken om de app-URL te krijgen.

### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst te vullen met waarden uit een CSV-bestand in de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*>. Of klik op **Exporteren** om een CSV-bestand (met dezelfde indeling) te maken met de inhoud van de lijst met verborgen of zichtbare apps.


## <a name="wireless"></a>Draadloos
-   **Dataroaming**: hiermee staat u dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
-   **Wereldwijd ophalen op achtergrond tijdens roamen**: hiermee staat u toe dat het apparaat data zoals e-mail ophaalt tijdens roaming op een mobiel netwerk.
-   **Nummer inspreken**: hiermee staat u het gebruik van de functie voor het inspreken van telefoonnummers op het apparaat toe.
-   **Spraakroaming**: hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
-   **Wijzigingen in de instellingen voor het gebruik van mobiel dataverkeer voor apps (alleen onder supervisie)**: hiermee staat u de gebruiker toe om te bepalen welke apps mobiel dataverkeer mogen gebruiken.
-   **Persoonlijke hotspot**: hiermee kunt u weigeren dat het apparaat als een persoonlijke hotspot wordt gebruikt. Mogelijk is deze instelling niet compatibel met bepaalde providers.
-   **Toevoegen aan Wi-Fi=netwerken die alleen configuratieprofielen gebruiken (alleen onder toezicht)**: hiermee kunt u toestaan dat het apparaat alleen verbinding maakt met netwerken die zijn geconfigureerd met een Intune Wi-Fi-profiel.

- **Regels voor mobiel gebruik (alleen beheerde apps)**: hiermee kunt u de gegevenstypen definiëren die beheerde apps kunnen gebruiken die met een mobiel netwerk zijn verbonden. U kunt kiezen uit:
    - **Gebruik van mobiel dataverkeer blokkeren**: u kunt het gebruik van mobiel dataverkeer blokkeren voor ** Alle beheerde apps** of u kunt **specifieke apps kiezen**.
    - **Gebruik van mobiel dataverkeer tijdens roaming blokkeren**: u kunt het gebruik van mobiel dataverkeer tijdens roaming blokkeren voor ** Alle beheerde apps** of u kunt **specifieke apps kiezen**.

## <a name="connected-devices"></a>Verbonden apparaten

-   **AirDrop (alleen onder toezicht)**: hiermee staat u het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
-   **Koppelen met Apple (alleen onder supervisie)**: hiermee staat u toe dat het apparaat aan een Apple Watch kan worden gekoppeld.
-   **De gekoppelde Apple Watch gebruikt Wrist Detection**: wanneer deze optie is ingeschakeld, worden op de Apple Watch geen meldingen weergegeven wanneer deze niet wordt gedragen.
-   **Bluetooth-aanpassingen (alleen onder supervisie)**: hiermee voorkomt u dat de eindgebruiker Bluetooth-instellingen op het apparaat kan wijzigen.
-   **Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld (alleen onder supervisie)**: hiermee staat u het koppelen met een host toe, waarmee de beheerder kan bepalen aan welke apparaten een iOS-apparaat kan worden gekoppeld.
-   **Wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**: hiermee vereist u een wachtwoord voor koppelen wanneer AirPlay wordt gebruikt om inhoud te streamen naar andere Apple-apparaten.

## <a name="keyboard-and-dictionary"></a>Toetsenbord en woordenlijst

-   **Opzoeken van definities van woorden (alleen onder toezicht)**: hiermee staat u de iOS-functie toe waarmee u een woord markeert en de definitie ervan opzoekt.
-   **Tekstvoorspelling (alleen onder toezicht)**: hiermee staat u toe dat suggesties worden gegeven voor woorden die de gebruiker mogelijk wil invoeren.
-   **Autocorrectie (alleen onder toezicht)**: hiermee kunnen verkeerd gespelde woorden automatisch worden gecorrigeerd.
-   **Spellingcontrole (alleen onder toezicht)**: hiermee staat u het gebruik van de spellingcontrole van het apparaat toe.
-   **Toetsenbordsneltoetsen (alleen onder toezicht)**: hiermee staat u het gebruik van sneltoetsen toe.
-   **Dicteren (alleen onder toezicht)**: hiermee kan de gebruiker geen spraak meer gebruiken om tekst in te voeren.

## <a name="cloud-and-storage"></a>Cloud en opslag
-   **Back-up naar iCloud**: hiermee staat u de gebruiker toe een back-up van het apparaat naar iCloud te maken.
-   **Documentsynchronisatie met iCloud (alleen onder toezicht)**: hiermee staat u synchronisatie van documenten en sleutelwaarden naar uw iCloud-opslagruimte toe.
-   **Synchroniseren van Photo Stream naar iCloud**: hiermee kunnen gebruikers **Mijn fotostream** inschakelen op hun apparaat zodat foto's kunnen worden gesynchroniseerd met iCloud en beschikbaar zijn op alle apparaten van de gebruikers.
-   **Versleutelde back-up**: hiermee geeft u aan dat back-ups van het apparaat moeten worden versleuteld.
-   **iCloud-fotobibliotheek**: als deze optie wordt ingesteld op **Nee**, wordt het gebruik uitgeschakeld van de iCloud-afbeeldingsbibliotheek waarmee gebruikers foto's en video's in de cloud kunnen opslaan.   Foto's die niet volledig naar het apparaat zijn gedownload vanaf de iCloud-fotobibliotheek, worden van het apparaat verwijderd als deze optie is ingesteld op **Nee**.
-   **Beheerde apps synchroniseren met de cloud**: hiermee staat u toe dat apps die u met Intune beheert, gegevens synchroniseren naar het iCloud-account van de gebruikers.
-   **Streaming van gedeelde foto's**: stel deze optie in op **Nee** om **Foto's delen via iCloud** uit te schakelen op het apparaat.
-   **Voortzetting van activiteit**: hiermee staat u toe dat gebruikers op een ander iOS- of macOS-apparaat kunnen doorgaan met werk waaraan ze zijn begonnen op een iOS-apparaat (Handoff).

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonome modus voor enkele toepassing (alleen onder toezicht)

Gebruik deze instellingen om iOS-apparaten zodanig te configureren dat hierop opgegeven apps in de autonome één-app-modus worden uitgevoerd. Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld zodat alleen de betreffende app kan worden uitgevoerd. U kunt bijvoorbeeld een app configureren die de gebruikers een test laat uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

### <a name="settings"></a>Instellingen

- **App-naam**: voer de naam in van de app zoals die wordt weergegeven in de lijst met apps op deze blade.
- **App-bundel-id**: geef de bundel-id van de app op. Zie voor hulp **Lijst van bundel-id’s voor ingebouwde iOS-apps** in dit onderwerp.

Nadat u de naam en bundel-id van de app hebt opgegeven, kiest u **Toevoegen** om deze aan de lijst toe te voegen.

- **Importeren**: een (CSV-)bestand met een lijst met door komma's gescheiden namen van apps en de bijbehorende bundel-id's importeren.
- **Exporteren**: de namen van apps en de bijbehorende bundel-id's die u hebt geconfigureerd exporteren naar een (CSV-)bestand met door komma's gescheiden waarden.

### <a name="bundle-id-reference-for-built-in-ios-apps"></a>Lijst van bundel-id’s voor ingebouwde iOS-apps

Deze lijst bevat de bundel-id's van een aantal algemene ingebouwde iOS-apps. Als u de bundel-ID van andere apps wilt weten, neemt u contact op met de softwareleverancier.

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.MobileSafari,Safari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple


```


## <a name="kiosk-supervised-only"></a>Kiosk (alleen onder toezicht)
-   **App die wordt uitgevoerd in de kioskmodus**: kies **Beheerde app** om een app te selecteren die u aan Intune hebt toegevoegd of kies **Store-app** om de URL naar een app in de Store op te geven. Er mogen geen andere apps op het apparaat worden uitgevoerd. Zie "URL's voor app stores opgeven" verderop in dit onderwerp voor meer informatie.
    -   **AssistiveTouch**: hiermee schakelt u de toegankelijkheidsinstelling **AssistiveTouch** in of uit, waarmee gebruikers schermbewegingen kunnen uitvoeren die moeilijk voor hen kunnen zijn.
    -   **Kleuren omkeren**: hiermee schakelt u de toegankelijkheidsinstelling Kleuren omkeren in of uit, waarmee het scherm wordt aangepast voor gebruikers met een beperkt gezichtsvermogen.
    -   **Monogeluid**: hiermee schakelt u de toegankelijkheidsinstelling Monogeluid in of uit.
    -   **VoiceOver**: hiermee schakelt u de toegankelijkheidsinstelling **VoiceOver** in of uit, waarmee tekst op het apparaatscherm wordt voorgelezen.
    -   **Zoomen**: hiermee schakelt u de toegankelijkheidsinstelling **Zoomen** in of uit, waarmee de gebruiker via aanraken kan inzoomen op het apparaatscherm.
    -   **Automatische vergrendeling**: hiermee schakelt u de automatische vergrendeling van het apparaat in of uit.
    -   **Schakelaar voor belsignaal**: hiermee schakelt u de schakelaar voor het belsignaal (dempen) op het apparaat in of uit.
    -   **Scherm draaien**: hiermee schakelt u het wijzigen van de schermstand in of uit wanneer de gebruiker het apparaat draait.
    -   **Schermsluimerknop**: hiermee schakelt u de knop voor slaapstand/ontwaken van het scherm op het apparaat in of uit.
    -   **Aanraken**: hiermee schakelt u het aanraakscherm van het apparaat in of uit.
    -   **Volumeknoppen**: hiermee schakelt u het gebruik van de volumeknoppen op het apparaat in of uit.
    -   **Besturingselement voor ondersteunende aanraking**: hiermee schakelt u aanpassingen in de functie Ondersteunende aanraking in of uit.
    -   **Besturingselement voor Kleuren omkeren**: hiermee schakelt u aanpassingen in de functie Kleuren omkeren in of uit.
    -   **Geselecteerde tekst uitspreken**: hiermee schakelt u de toegankelijkheidsinstellingen voor Selectie uitspreken in of uit, waarmee door de gebruiker geselecteerde tekst wordt voorgelezen.
    -   **Besturingselement voor Voice-over**: hiermee schakelt u aanpassingen voor de functie VoiceOver (bijvoorbeeld hoe snel schermtekst wordt voorgelezen) in of uit.
    -   **Besturingselement voor in- en uitzoomen**: hiermee schakelt u aanpassingen in de zoomfunctie in of uit.

>[!NOTE]
> Voordat u een iOS-apparaat voor de kioskmodus kunt configureren, moet u het hulpprogramma Apple Configurator of het Device Enrollment Program van Apple gebruiken om het apparaat in de supervisiemodus te plaatsen. Zie de Apple-documentatie voor meer informatie over het hulpprogramma Apple Configurator.
>Als de iOS-app die u opgeeft wordt geïnstalleerd nadat u het profiel hebt toegewezen, wordt de kioskmodus van het apparaat pas geactiveerd nadat het opnieuw is opgestart.

## <a name="safari"></a>Safari
-   **Safari (alleen onder toezicht)**: hiermee geeft u op of de Safari-browser op het apparaat kan worden gebruikt.
-   **Automatisch doorvoeren**: hiermee staat u de gebruiker toe instellingen voor automatisch aanvullen in de browser te wijzigen.
-   **Cookies**: hiermee staat u toe dat de browser gebruikmaakt van cookies.
-   **JavaScript**: hiermee staat u de uitvoering van Java-scripts in de browser toe.
-   **Waarschuwingen voor fraude**: hiermee staat u toe dat waarschuwingen voor fraude in de browser worden weergegeven.
-   **Pop-ups**: hiermee schakelt u de pop-upblokkering voor de browser in of uit.


## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Niet-gemarkeerde e-maildomeinen

Voeg in het veld **E-maildomein-URL** een of meer URL's toe aan de lijst. Wanneer eindgebruikers een e-mail ontvangen die afkomstig is van een ander domein dan het domein dat u hebt geconfigureerd, wordt de e-mail in de iOS Mail-app gemarkeerd als niet-vertrouwd.


### <a name="managed-web-domains"></a>Beheerde webdomeinen

Voeg in het veld **Webdomein-URL** een of meer URL's toe aan de lijst. Documenten die zijn gedownload via de URL's die u opgeeft, worden als beheerd beschouwd. Deze instelling geldt alleen voor documenten die zijn gedownload met Safari.


### <a name="safari-password-autofill-domains"></a>Domeinen voor automatisch invullen van Safari-wachtwoorden

Voeg in het veld **Domein-URL** een of meer URL's toe aan de lijst. Gebruikers kunnen in deze lijst alleen webwachtwoorden van URL's opslaan. Deze instelling geldt alleen voor Safari en voor apparaten met iOS 9.3 en hoger in de modus supervisie. Als u geen URL's opgeeft, kunnen wachtwoorden van alle websites worden opgeslagen.
