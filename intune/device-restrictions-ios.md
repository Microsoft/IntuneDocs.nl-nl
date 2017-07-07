---
title: Intune-apparaatbeperkingsinstellingen voor iOS
titleSuffix: Intune on Azure
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op iOS-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 365b56082207c2110965681663432cce10f27c99
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="ios-device-restriction-settings-in-microsoft-intune"></a>iOS-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Algemeen
-   **Camera**: hiermee kunt u aangeven of de camera op het apparaat kan worden gebruikt.   
-   **Verzenden van diagnostische gegevens**: hiermee kunt u verzending van diagnostische gegevens naar Apple voor het apparaat toestaan of blokkeren.
-   **FaceTime**: hiermee staat u toe dat de FaceTime-app op het apparaat mag worden gebruikt.
-   **Schermafbeelding**: hiermee staat u de gebruiker toe om de inhoud van het scherm vast te leggen als afbeelding.
-   **Siri**: hiermee staat u het gebruik van de spraakassistent Siri op het apparaat toe.
    -   **Siri wanneer het apparaat is vergrendeld**: hiermee staat u het gebruik van de spraakassistent Siri op het apparaat toe terwijl het apparaat is vergrendeld.
    -   **Siri-filter voor scheldwoorden (alleen onder toezicht)**: hiermee voorkomt u het dicteren van grove taal met Siri of dat Siri grove taal spreekt.
    -   **Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet (alleen onder toezicht)**: hiermee staat u Siri toe websites te raadplegen om vragen te beantwoorden.
-   **Niet-vertrouwde TLS-certificaten**: hiermee staat u niet-vertrouwde TLS-certificaten (Transport Layer Security) op het apparaat toe.
-   **Toegang tot Beheercentrum wanneer het apparaat is vergrendeld**: hiermee staat u toegang tot de Control Center-app toe terwijl het apparaat is vergrendeld.
-   **Meldingen wanneer het apparaat is vergrendeld**: hiermee staat u de gebruiker toegang tot de weergave van meldingen toe zonder het apparaat te ontgrendelen.
-   **Passbook wanneer het apparaat is vergrendeld**: hiermee staat u de gebruiker toegang tot de app Passbook toe terwijl het apparaat is vergrendeld.
-   **De weergave Vandaag wanneer het apparaat is vergrendeld**: hiermee staat u de gebruiker toe de weergave Vandaag te bekijken wanneer het apparaat is vergrendeld.
-   **Bedrijfsapps vertrouwen**: hiermee kan de gebruiker aangeven apps te vertrouwen die niet uit de App Store zijn gedownload.
-   **AirDrop (alleen onder toezicht)**: hiermee staat u het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
-   **Spotlight-zoekacties voor de weergave van resultaten op internet (alleen onder toezicht)**: hiermee staat u toe dat Spotlight zoekt op en verbinding maakt met internet voor aanvullende resultaten.
-   **Opzoeken van definities van woorden (alleen onder toezicht)**: hiermee staat u de iOS-functie toe waarmee u een woord markeert en de definitie ervan opzoekt.
-   **Tekstvoorspelling (alleen onder toezicht)**: hiermee staat u toe dat suggesties worden gegeven voor woorden die de gebruiker mogelijk wil invoeren.
-   **Autocorrectie (alleen onder toezicht)**: hiermee kunnen verkeerd gespelde woorden automatisch worden gecorrigeerd.
-   **Spellingcontrole (alleen onder toezicht)**: hiermee staat u het gebruik van de spellingcontrole van het apparaat toe.
-   **Toetsenbordsneltoetsen (alleen onder toezicht)**: hiermee staat u het gebruik van sneltoetsen toe.
-   **De gekoppelde Apple Watch gebruikt Wrist Detection**: wanneer deze optie is ingeschakeld, worden op de Apple Watch geen meldingen weergegeven wanneer deze niet wordt gedragen.
- **Wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**: hiermee vereist u een wachtwoord voor koppelen wanneer AirPlay wordt gebruikt om inhoud te streamen naar andere Apple-apparaten.
- **Accountwijzigingen (alleen onder toezicht)**: wanneer deze optie is geblokkeerd, kan de gebruiker geen apparaatspecifieke instellingen wijzigen in de app voor iOS-instellingen, zoals het maken van nieuwe accounts voor het apparaat en het wijzigen van de gebruikersnaam en het wachtwoord.
Dit geldt ook voor instellingen die toegankelijk zijn vanuit de app voor iOS-instellingen, zoals de instellingen voor e-mail, contactpersonen, agenda, Facebook en Twitter. Dit geldt niet voor apps met accountinstellingen die niet in de app voor iOS-instellingen kunnen worden geconfigureerd, zoals de Microsoft Outlook-app.
- **Koppelen met Apple (alleen onder supervisie)**: hiermee staat u toe dat het apparaat aan een Apple Watch kan worden gekoppeld.
- **Bluetooth-aanpassingen (alleen onder supervisie)**: hiermee voorkomt u dat de eindgebruiker Bluetooth-instellingen op het apparaat kan wijzigen.
- **Observatie van extern scherm met de app Classroom (alleen onder supervisie)**: hiermee kunt u toestaan of voorkomen dat de app Classroom het scherm van externe apparaten kan observeren.
- **Door de gebruiker inschakelen van beperkingen in de apparaatinstellingen (alleen onder supervisie)**: hiermee staat u de gebruiker toe beperkingen voor het apparaat te configureren (ouderlijk toezicht).
- **Het gebruik van de optie voor het wissen van alle inhoud en instellingen op het apparaat (alleen onder supervisie)**: hiermee staat u de gebruiker toe de optie voor het wissen van alle inhoud en instellingen op het apparaat te gebruiken.
- **Wijzigen van apparaatnaam (alleen onder supervisie)**: hiermee staat u de gebruiker toe de naam van het apparaat te wijzigen.
- **Aanpassing van de instellingen voor het verzenden van diagnostische gegevens (alleen onder supervisie)**: hiermee kunt u de verzending van diagnostische gegevens naar Apple toestaan of blokkeren voor het apparaat.
- **Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld (alleen onder supervisie)**: hiermee staat u het koppelen met een host toe, waarmee de beheerder kan bepalen aan welke apparaten een iOS-apparaat kan worden gekoppeld.
- **Wijzigen van de meldingsinstellingen (alleen onder supervisie)**: hiermee staat u de gebruiker toe de instellingen voor apparaatmeldingen te wijzigen.
- **Wachtwoordcode wijzigen (alleen onder supervisie)**: hiermee staat u toevoeging, wijziging of verwijdering van het apparaatwachtwoord toe.
- **Achtergrond wijzigen (alleen onder supervisie)**: hiermee staat u de gebruiker toe de achtergrond van het apparaat te wijzigen.
- **Het wijzigen van de vertrouwensinstellingen voor bedrijfsapps (alleen onder supervisie)**: hiermee kan de gebruiker aangeven apps te vertrouwen die niet uit de App Store zijn gedownload.
- **Apps installeren via de App Store (alleen onder supervisie)**: hiermee staat u toegang tot de App Store en de installatie van apps toe.
- **Wijzigingen in de instellingen van de app Zoek vrienden (alleen onder supervisie)**: hiermee staat u toe dat de gebruiker de instellingen van de app Zoek vrienden kan wijzigen.
- **iBooks Store (alleen onder supervisie)**: hiermee staat u de gebruiker toe om door boeken in de iBooks Store te bladeren en om boeken te kopen.
- **De app Berichten op het apparaat (alleen onder supervisie)**: hiermee staat u toe dat de app Berichten op sms-berichten mag verzenden en lezen.
- **Podcasts (alleen onder supervisie)**: hiermee staat u het gebruik van Podcasts toe.
- **Service Music (alleen onder supervisie)**: hiermee staat u het gebruik van de app Apple Music toe.
- **iTunes Radio-service (alleen onder supervisie)**: hiermee staat u het gebruik van de app iTunes Radio toe.
- **Apple Nieuws (alleen onder supervisie)**: hiermee staat u het gebruik van de app Apple News toe.
- **Wijzigingen in configuratieprofielen**: hiermee staat u de gebruiker toe configuratieprofielen te installeren.

## <a name="password"></a>Wachtwoord
-   **Wachtwoord vereist**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
-   **Eenvoudige wachtwoorden**: hiermee staat u het gebruik van eenvoudige wachtwoorden toe, zoals 0000 en 1234.
-   **Vereist wachtwoordtype**: hiermee geeft u het type wachtwoord op dat vereist is, zoals alleen numeriek of alfanumeriek.
-   **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: hiermee geeft u het aantal symbooltekens (zoals **#** of **@**) op dat het wachtwoord moet bevatten.
-   **Minimale wachtwoordlengte**: hiermee geeft u het minimum aantal tekens op voor het wachtwoord.
-   **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee geeft u het aantal mislukte aanmeldingspogingen op dat is toegestaan voordat het apparaat wordt gewist.
-   **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** <sup>1</sup>: hiermee geeft u op hoelang het apparaat inactief moet zijn voordat gebruikers hun wachtwoord opnieuw moeten invoeren.
-   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**<sup>1</sup>: hiermee geeft u het aantal minuten op waarna het apparaatscherm wordt uitgeschakeld.
-   **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.
-   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.
-   **Vingerafdruk ontgrendelen**: hiermee staat u toe dat compatibele apparaten kunnen worden ontgrendeld met een vingerafdruk.

<sup>1</sup> Wanneer u de instellingen **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld** en **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **5** minuten, wordt het scherm na 5 minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens 5 minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat 5 minuten later vergrendeld.

## <a name="app-store-doc-viewing-gaming"></a>App Store, documenten bekijken, gamen


-   **App Store (alleen onder toezicht)**: hiermee blokkeert u de toegang tot de App Store op apparaten onder toezicht.
-   **Wachtwoord voor toegang tot de App Store**: hiermee geeft u aan dat gebruikers een wachtwoord moeten invoeren voordat ze de App Store kunnen bezoeken.
-   **Aankopen in app**: hiermee staat u toe dat Store-aankopen kunnen worden uitgevoerd vanuit een actieve app.
-   **Automatisch downloaden van apps (alleen onder supervisie)** -
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

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren.
Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Om te blijven voldoen aan het beleid, mogen gebruikers apps die niet worden vermeld, niet installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met apps, gebruikt u de volgende notatie:

Gebruik een zoekmachine om de app te zoeken die u wilt gebruiken in de iTunes App Store en open de pagina voor de app.
Kopieer de URL van de pagina en gebruik deze als de URL voor het configureren van de lijst met toegestane of niet-toegestane apps of voor een app die u wilt uitvoeren in kioskmodus.
Apparaatprofielen die instellingen voor beperkte apps bevatten, moeten worden toegewezen aan groepen met gebruikers.

Voorbeeld: Zoek naar Microsoft Word voor iPad. De URL die u gebruikt, is https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> U kunt ook de iTunes-software gebruiken om de app te zoeken en vervolgens de opdracht **Koppeling kopiëren** gebruiken om de app-URL te krijgen.



### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst te vullen met waarden uit een CSV-bestand in de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*>. Of klik op **Exporteren** om een CSV-bestand (met dezelfde indeling) te maken met de inhoud van de lijst met beperkte apps.

## <a name="show-or-hide-apps"></a>Apps weergeven of verbergen

In de lijst Apps weergeven of verbergen kunt u een van de volgende lijsten configureren (vereist toezicht voor apparaten met iOS 9.3 of hoger).

Lijst met **verborgen apps**: een lijst opstellen met verborgen apps die worden verborgen voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
Lijst met **zichtbare apps**: een lijst opstellen met apps die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met apps, gebruikt u de volgende notatie:

Gebruik een zoekmachine om de app te zoeken die u wilt gebruiken in de iTunes App Store en open de pagina voor de app.
Kopieer de URL van de pagina en gebruik deze als de URL voor het configureren van de lijst met toegestane of niet-toegestane apps of voor een app die u wilt uitvoeren in kioskmodus.

Voorbeeld: Zoek naar Microsoft Word voor iPad. De URL die u gebruikt, is https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.

> [!Note]
> U kunt ook de iTunes-software gebruiken om de app te zoeken en vervolgens de opdracht **Koppeling kopiëren** gebruiken om de app-URL te krijgen.

### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst te vullen met waarden uit een CSV-bestand in de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*>. Of klik op **Exporteren** om een CSV-bestand (met dezelfde indeling) te maken met de inhoud van de lijst met verborgen of zichtbare apps.


## <a name="cellular"></a>Mobiel
-   **Dataroaming**: hiermee staat u dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
-   **Wereldwijd ophalen op achtergrond tijdens roamen**: hiermee staat u toe dat het apparaat data zoals e-mail ophaalt tijdens roaming op een mobiel netwerk.
-   **Nummer inspreken**: hiermee staat u het gebruik van de functie voor het inspreken van telefoonnummers op het apparaat toe.
-   **Spraakroaming**: hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
-   **Wijzigingen in de instellingen voor het gebruik van mobiel dataverkeer voor apps (alleen onder supervisie)**: hiermee staat u de gebruiker toe om te bepalen welke apps mobiel dataverkeer mogen gebruiken.

## <a name="cloud-and-storage"></a>Cloud en opslag
-   **Back-up naar iCloud**: hiermee staat u de gebruiker toe een back-up van het apparaat naar iCloud te maken.
-   **Documentsynchronisatie met iCloud (alleen onder toezicht)**: hiermee staat u synchronisatie van documenten en sleutelwaarden naar uw iCloud-opslagruimte toe.
-   **Synchroniseren van Photo Stream naar iCloud**: hiermee kunnen gebruikers **Mijn fotostream** inschakelen op hun apparaat zodat foto's kunnen worden gesynchroniseerd met iCloud en beschikbaar zijn op alle apparaten van de gebruikers.
-   **Versleutelde back-up**: hiermee geeft u aan dat back-ups van het apparaat moeten worden versleuteld.
-   **iCloud-fotobibliotheek**: als deze optie wordt ingesteld op **Nee**, wordt het gebruik uitgeschakeld van de iCloud-afbeeldingsbibliotheek waarmee gebruikers foto's en video's in de cloud kunnen opslaan.    Foto's die niet volledig naar het apparaat zijn gedownload vanaf de iCloud-fotobibliotheek, worden van het apparaat verwijderd als deze optie is ingesteld op **Nee**.
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

Deze lijst bevat de bundel-id’s van een aantal algemene ingebouwde iOS-apps. Als u de bundel-ID van andere apps wilt weten, neemt u contact op met de softwareleverancier.

|||
|-|-|
|App-naam|Bundel-id|
|App Store|com.apple.AppStore|
|Rekenmachine|com.apple.calculator|
|Kalender|com.apple.mobilecal|
|Camera|com.apple.camera|
|Klok|com.apple.mobiletimer|
|Kompas|com.apple.compass|
|Contactpersonen|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Zoek vrienden|com.apple.mobileme.fmf1|
|Zoek mijn iPhone|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Status|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.Apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.Apple.mobilemail|
|Kaarten|com.apple.Maps|
|Berichten|com.apple.MobileSMS|
|Music|com.apple.Music|
|Nieuws|com.apple.news|
|Opmerkingen|com.apple.mobilenotes|
|Getallen|com.apple.Numbers|
|Pages|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Foto’s|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Herinneringen|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Instellingen|com.apple.Preferences|
|Aandelen|com.apple.stocks|
|Tips|com.apple.tips|
|Video 's|com.apple.videos|
|Dictafoon|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Watch|com.apple.Bridge|
|Weer|com.apple.weather|


## <a name="kiosk"></a>Kiosk
-   **Activeringsvergrendeling**: hiermee schakelt u Activeringsvergrendeling in op iOS-apparaten in de supervisiemodus.
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

Voeg in het veld **E-maildomein-URL** een of meer URL's toe aan de lijst. Wanneer eindgebruikers een e-mail ontvangen dat afkomstig is van een ander domein dan dat u hebt geconfigureerd, wordt de e-mail in de map iOS Mail gemarkeerd als niet-vertrouwd.


### <a name="managed-web-domains"></a>Beheerde webdomeinen

Voeg in het veld **Webdomein-URL** een of meer URL's toe aan de lijst. Documenten die zijn gedownload via de URL's die u opgeeft, worden als beheerd beschouwd. Deze instelling geldt alleen voor documenten die zijn gedownload met Safari.


### <a name="safari-password-auto-fill-domains"></a>Domeinen voor automatisch invullen van wachtwoorden in Safari

Voeg in het veld **Domein-URL** een of meer URL's toe aan de lijst. Gebruikers kunnen in deze lijst alleen webwachtwoorden van URL's opslaan. Deze instelling geldt alleen voor Safari en voor apparaten met iOS 9.3 en hoger in de modus supervisie. Als u geen URL's opgeeft, kunnen wachtwoorden van alle websites worden opgeslagen.
