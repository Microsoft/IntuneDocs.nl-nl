---
title: Instellingen voor iOS-beleid | Microsoft Intune
description: Maak beleid waarmee instellingen en functies worden beheerd op iOS-apparaten die u met Intune beheert.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/06/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cd5930995a6da130fedcb6d89851460e6f0614eb
ms.openlocfilehash: 24540a74ce98adbf3f908cbea401328f027867ca


---

# Instellingen voor iOS-beleid in Microsoft Intune

Intune biedt diverse ingebouwde algemene instellingen die u op iOS-apparaten kunt configureren. Daarnaast kunt u het hulpprogramma Apple Configurator gebruiken om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.

## Instellingen voor algemeen configuratiebeleid

Gebruik het **algemene iOS-configuratiebeleid** van Microsoft Intune om instellingen te configureren voor:

-   **Algemene apparaat- en beveiligingsinstellingen**. Hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u verschillende functies en functionaliteiten op het apparaat kunt beheren.

-   **Kioskmodus**. Hiermee vergrendelt u een apparaat zodat alleen bepaalde functies werken. U kunt bijvoorbeeld toestaan dat een apparaat slechts één beheerde app uitvoert die u opgeeft, of kunt u de volumeknoppen op een apparaat uitschakelen. Deze instellingen kunnen worden gebruikt voor een demonstratiemodel van een apparaat of voor een apparaat dat is toegewezen aan slechts één functie, zoals een verkooppuntapparaat.

-   **Compatibele en niet-compatibele apps**. Hier kunt u een lijst opgeven van apps die in uw bedrijf compatibel of niet compatibel zijn. Op Android- en iOS-apparaten kan het **Rapport niet-compatibele apps** worden gebruikt om de compatibiliteit van apps die u in de lijst hebt opgegeven, te vergelijken met de apps die gebruikers hebben geïnstalleerd (de installatie van de app kan echter niet worden geblokkeerd).

> [!TIP]
> U kunt voorwaarden voor gebruikers configureren om ervoor te zorgen dat ze ermee instemmen dat apps op hun apparaat, waaronder persoonlijke apps, worden geëvalueerd, en dat niet-compatibele apps worden geblokkeerd of gerapporteerd als niet-compatibel. Gebruikers moeten deze voorwaarden accepteren voordat ze hun apparaat kunnen registreren en de bedrijfsportal kunnen gebruiken om apps op te halen. Zie [Instellingen voor het voorwaardenbeleid in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md) voor meer informatie over het gebruik van de voorwaarden.

Als de instelling die u zoekt niet wordt weergegeven in dit onderwerp, kunt u de instelling wellicht maken met een aangepast iOS-beleid, dat u in staat stelt instellingen te importeren die u hebt gemaakt met de [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Zie "Aangepaste beleidsinstellingen" verderop in dit onderwerp voor meer informatie.

### Beveiligingsinstellingen
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Hier geeft u op of de gebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.|
|**Vereist wachtwoordtype**|Hier geeft u het type wachtwoord op dat vereist is, zoals alleen numeriek of alfanumeriek.|
|**Aantal complexe tekens dat is vereist in wachtwoord**|Hier geeft u het aantal symbooltekens (zoals **#** of **@**) op dat het wachtwoord moet bevatten.|
|**Minimale wachtwoordlengte**|Hier geeft u het minimumaantal tekens op voor het wachtwoord.|
|**Eenvoudige wachtwoorden toestaan**|Hiermee staat u toe dat eenvoudige wachtwoorden worden gebruikt, zoals **0000** en **1234**.|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Hier geeft u het aantal mislukte aanmeldingspogingen op dat is toegestaan voordat het apparaat wordt gewist.|
|**Minuten inactief voordat wachtwoord is vereist**<sup>1</sup>|Hier geeft u op hoelang het apparaat inactief moet zijn voordat gebruikers hun wachtwoord opnieuw moeten invoeren.|
|**Wachtwoordverlooptijd (dagen)**|Hier geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|
|**Wachtwoordgeschiedenis onthouden**|Hier geeft u op of de gebruiker eerder gebruikte wachtwoorden mag hergebruiken.|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hier geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**<sup>1</sup>|Hiermee geeft u het aantal minuten op waarna het apparaatscherm wordt uitgeschakeld.|
|**Vingerafdruk voor ontgrendelen toestaan**|Hiermee staat u toe dat het apparaat kan worden ontgrendeld met een vingerafdruk.|
<sup>1</sup> Wanneer u bij iOS-apparaten de instellingen **Minuten van inactiviteit voordat het scherm wordt uitgeschakeld** en **Minuten van inactiviteit voordat wachtwoord vereist is** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **5** minuten, wordt het scherm na 5 minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens 5 minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat 5 minuten later vergrendeld.

### Systeeminstellingen
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Schermopname toestaan**|Hiermee staat u de gebruiker toe om de inhoud van het scherm vast te leggen als afbeelding.|
|**Beheercentrum in vergrendelingsscherm toestaan**|Hiermee staat u toegang tot de Control Center-app toe terwijl het apparaat is vergrendeld.|
|**Weergave van meldingen in vergrendelingsscherm toestaan**|Hiermee staat u de gebruiker toegang tot de weergave van meldingen toe zonder het apparaat te ontgrendelen.|
|**Weergave van vandaag in vergrendelingsscherm toestaan**|Hiermee staat u toe dat meldingen worden weergegeven wanneer het apparaat is vergrendeld.|
|**Niet-vertrouwde TLS-certificaten toestaan**|Hiermee staat u niet-vertrouwde TLS-certificaten (Transport Layer Security) op het apparaat toe.|
|**Verzending van diagnostische gegevens toestaan**|Hiermee staat u verzending van diagnostische gegevens naar Apple toe voor het apparaat of weigert u dit.|
|**Passbook tijdens vergrendeling toestaan**|Hiermee staat u de gebruiker toegang tot de app Passbook toe terwijl het apparaat is vergrendeld.|

### Cloudinstellingen voor documenten en gegevens
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Back-up naar iCloud® toestaan**|Hiermee staat u de gebruiker toe een back-up van het apparaat naar iCloud te maken.|
|**Documentsynchronisatie met iCloud toestaan**|Hiermee staat u synchronisatie van documenten en sleutelwaarden naar uw iCloud-opslagruimte toe.|
|**Photo Stream-synchronisatie met iCloud toestaan**|Hiermee staat u synchronisatie van foto's op het apparaat met iCloud toe.|
|**Versleutelde back-ups vereisen**|Hiermee vereist u dat back-ups van het apparaat worden versleuteld.|
|**Beheerde apps toestaan gegevens naar iCloud te synchroniseren**|Hiermee staat u toe dat apps die u met Intune beheert, gegevens synchroniseren naar het iCloud-account van de gebruikers.|
|**Handoff toestaan om activiteiten op een ander apparaat voort te zetten**|Hiermee staat u toe dat gebruikers kunnen doorgaan met werk waaraan ze zijn begonnen op een iOS-apparaat, op een ander iOS- of Mac OS X-apparaat.|
|**Foto's delen via iCloud toestaan**|Hiermee staat u het gebruik van de iOS-functie voor streamen van gedeelde foto's toe.|
|**iCloud-fotobibliotheek toestaan**|Hiermee kan de gebruiker foto's opslaan in iCloud. Als dit wordt uitgeschakeld, worden foto's die al zijn opgeslagen in iCloud verwijderd.|

### Toepassingsinstellingen voor de browser
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Safari toestaan**|Hiermee geeft u op of de Safari-browser op het apparaat kan worden gebruikt.|
|**Automatisch invullen toestaan**|Hiermee staat u de gebruiker toe instellingen voor automatisch aanvullen in de browser te wijzigen.|
|**Pop-upblokkering toestaan**|Hiermee schakelt u de pop-upblokkering voor de browser in of uit.|
|**Cookies toestaan**|Hiermee staat u toe dat de browser gebruikmaakt van cookies.|
|**Gebruik van Java-scripts toestaan**|Hiermee staat u de uitvoering van Java-scripts in de browser toe.|
|**Waarschuwing voor fraude toestaan**|Hiermee staat u toe dat waarschuwingen voor fraude in de browser van het apparaat worden weergegeven.|

### Toepassingsinstellingen voor apps
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Installeren van apps toestaan**|Hiermee staat u toegang tot de App Store en de installatie van apps toe.|
|**Wachtwoord vereisen voor toegang tot het toepassingsarchief**|Hiermee vereist u dat gebruikers een wachtwoord invoeren voordat ze de App Store kunnen bezoeken.|
|**Aankopen in app toestaan**|Hiermee staat u toe dat Store-aankopen kunnen worden uitgevoerd vanuit een actieve app.|
|**Beheerde documenten in andere niet-beheerde apps toestaan**|Hiermee stelt u in dat zakelijke documenten kunnen worden weergegeven in elke app.<br>**Voorbeeld:** u wilt voorkomen dat gebruikers bestanden uit de OneDrive-app opslaan in Dropbox. Stel deze instelling in op Nee. Nadat het apparaat het beleid heeft ontvangen (bijvoorbeeld nadat het opnieuw is opgestart), kunnen er geen bestanden meer worden opgeslagen.|
|**Niet-beheerde documenten in andere beheerde apps toestaan**|Hiermee staat u toe dat elk document kan worden weergegeven in zakelijke beheerde apps.|
|**Videovergaderingen toestaan**|Hiermee staat u het gebruik van videovergadering-apps toe op het apparaat, zoals FaceTime.|
|**Toestaan dat de gebruiker nieuwe auteurs van bedrijfsapps vertrouwt**|Hiermee kan de gebruiker aangeven apps te vertrouwen die niet uit de App Store zijn gedownload.|


### Toepassingsinstellingen voor games
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Game Center-vrienden toestaan**|Hiermee staat u de gebruiker toe vrienden toe te voegen in Game Center.|
|**Games voor meerdere spelers toestaan**|Hiermee staat u de gebruiker toe op het apparaat games voor meerdere spelers te spelen.|

### Toepassingsinstellingen voor media-inhoud
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Classificatieregio**|Selecteer een regio en vervolgens de restrictie voor gebruikers voor het downloaden van **films**, **tv-programma’s** en **apps**.|
|**Inhoud voor volwassenen in media store toestaan**|Hiermee staat u het apparaat toegang tot inhoud voor volwassenen toe.|
|**Toestaan dat de gebruiker als Erotisch aangeduide inhoud kan downloaden uit de iBooks Store**|Hiermee staat u gebruikers toe dat ze boeken uit de categorie Erotisch downloaden.|


### Instellingen voor apparaatmogelijkheden voor hardware
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Camera toestaan**|Hiermee geeft u op of de camera op het apparaat kan worden gebruikt.|
|**Forceren dat de gekoppelde Apple Watch Wrist Detection gebruikt**|Wanneer dit is ingeschakeld, worden op de Apple Watch geen meldingen weergegeven wanneer deze niet wordt gedragen.|
|**Een wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**|Hiermee vereist u een wachtwoord voor koppelen wanneer AirPlay wordt gebruikt om inhoud te streamen naar andere Apple-apparaten.|

### Instellingen voor apparaatmogelijkheden voor mobiel
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Spraakroaming toestaan**|Hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|
|**Gegevensroaming toestaan**|Hiermee staat u gegevensroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|
|**Op de achtergrond ophalen tijdens roamen toestaan**|Hiermee staat u toe dat het apparaat gegevens zoals e-mail ophaalt tijdens roaming op een mobiel netwerk.|

### Instellingen voor apparaatmogelijkheden voor functies
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Siri toestaan**|Hiermee staat u gebruik van de spraakassistent Siri op het apparaat toe.|
|**Siri toestaan terwijl apparaat is vergrendeld**|Hiermee staat u gebruik van de spraakassistent Siri op het apparaat toe terwijl het apparaat is vergrendeld.|
|**Nummer inspreken toestaan**|Hiermee staat u gebruik van de functie voor het inspreken van telefoonnummers op het apparaat toe.|
|**AirDrop niet toestaan vanuit beheerde apps**|Hiermee wordt het verzenden van gegevens door beheerde apps via Airdrop gestopt.|


### Instellingen voor compatibele en niet-compatibele apps
In de lijst **Compatibele en niet-compatibele apps** geeft u een lijst met compatibele of niet-compatibele apps op met behulp van de volgende gegevens.

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met compatibele apps of een lijst met niet-compatibele apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren.|
|**Niet-compliantie melden wanneer gebruikers apps installeren die niet in de lijst staan**|Hiermee maakt u een lijst met apps die gebruikers mogen installeren. Om te blijven voldoen aan het beleid, mogen gebruikers apps die niet worden vermeld, niet installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store. Lees "URL’s voor app stores opgeven" verderop in dit onderwerp voor meer informatie.|
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik in dit bestand deze indeling: toepassingsnaam, uitgever, app-URL.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de URL van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|

### Instellingen voor kioskmodus

|Naam van de instelling|Details|
|----------------|--------------------|
|**Een beheerde app selecteren die mag worden uitgevoerd wanneer het apparaat in kioskmodus is**|Kies **Bladeren** en geef op welke beheerde apps, of apps in een store, mogen worden uitgevoerd wanneer het apparaat in kioskmodus is. Er mogen geen andere apps op het apparaat worden uitgevoerd. Zie "URL's voor app stores opgeven" verderop in dit onderwerp voor meer informatie.|
|**Aanraakscherm toestaan**|Hiermee schakelt u het aanraakscherm van het apparaat in of uit.|
|**Schermrotatie toestaan**|Hiermee staat u het wijzigen van de schermstand toe wanneer de gebruiker het apparaat draait.|
|**Volumeknoppen toestaan**|Hiermee schakelt u het gebruik van de volumeknoppen op het apparaat in of uit.|
|**Schakelaar voor belsignaal toestaan**|Hiermee schakelt u de schakelaar voor belsignaal (dempen) op het apparaat in of uit.|
|**Knop voor slaapstand/ontwaken van scherm toestaan**|Hiermee schakelt u de knop voor slaapstand/ontwaken van het scherm op het apparaat in of uit.|
|**Automatisch vergrendelen toestaan**|Hiermee schakelt u de automatische vergrendeling van het apparaat in of uit.|
|**Monogeluid inschakelen**|Hiermee schakelt u de toegankelijkheidsinstelling **Monogeluid**in of uit.|
|**Voice-over inschakelen**|Hiermee schakelt u de toegankelijkheidsinstelling **Voice-over**, die tekst op het apparaatscherm voorleest, in of uit.|
|**Aanpassingen aan voice-over inschakelen**|Hiermee schakelt u aanpassingen voor de functie VoiceOver (bijvoorbeeld hoe snel schermtekst wordt voorgelezen) in of uit.|
|**Zoomen inschakelen**|Hiermee schakelt u de toegankelijkheidsinstelling **Zoomen**, waarmee de gebruiker via aanraken kan inzoomen op het apparaatscherm, in of uit.|
|**Aanpassingen aan zoomen inschakelen**|Hiermee schakelt u aanpassingen aan de zoomfunctie in of uit.|
|**Kleuren omkeren inschakelen**|Hiermee schakelt u de toegankelijkheidsinstelling **Kleuren omkeren**, die het scherm aanpast voor gebruikers met een beperkt gezichtsvermogen, in of uit.|
|**Aanpassingen aan kleuren omkeren inschakelen**|Hiermee schakelt u aanpassingen aan de functie Kleuren omkeren in of uit.|
|**Ondersteunend aanraken inschakelen**|Hiermee schakelt u de toegankelijkheidsinstelling **Ondersteunend aanraken**, waarmee gebruikers schermbewegingen kunnen uitvoeren die moeilijk voor hen kunnen zijn, in of uit.|
|**Aanpassingen aan ondersteunend aanraken inschakelen**|Hiermee schakelt u aanpassingen aan de functie Ondersteunend aanraken in of uit.|
|**Spraakselectie inschakelen**|Hiermee schakelt u de toegankelijkheidsinstellingen voor **Selectie uitspreken**, waarmee door de gebruiker geselecteerde tekst wordt voorgelezen, in of uit.|
> [!NOTE]
> De volgende opmerkingen zijn van toepassing op kioskmodusinstellingen voor iOS-apparaten:
>
> -   Voordat u een iOS-apparaat voor de kioskmodus kunt configureren, moet u het [hulpprogramma Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) of het [Device Enrollment Program van Apple](ios-device-enrollment-program-in-microsoft-intune) gebruiken om het apparaat in de supervisiemodus te plaatsen. Zie de Apple-documentatie voor meer informatie over het hulpprogramma Apple Configurator.
> -   Als de iOS-app die u opgeeft, wordt geïnstalleerd nadat u het configuratiebeleid hebt geïmplementeerd, kan het apparaat pas in kioskmodus worden geplaatst nadat het opnieuw is opgestart.

### Referentie-informatie voor compatibele en niet-compatibele apps

Gebruik het **Rapport met niet-compatibele apps** om de compatibiliteit van toegestane en geblokkeerde apps weer te geven.

##### Het rapport met niet-compatibele apps uitvoeren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Rapporten** &gt; **Rapport met niet-compatibele apps**.

2.  Selecteer de apparaatgroepen die u wilt controleren, selecteer of u op compatibele en/of niet-compatibele apps wilt controleren, en kies vervolgens **Rapport weergeven**.

#### URL's voor app stores opgeven
Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps of in de optie **Selecteer een beheerde app die actief mag zijn als het apparaat in kioskmodus is** (alleen iOS), gebruikt u de volgende indeling:

1. Gebruik een zoekmachine om de app te zoeken die u wilt gebruiken in de iTunes App Store en open de pagina voor de app.

2. Kopieer de URL van de pagina en gebruik deze als de URL voor het configureren van de lijst met compatibele of niet-compatibele apps of de app die u wilt uitvoeren in kioskmodus.

**Voorbeeld:** Zoek naar **Microsoft Word voor iPad**. De URL die u gebruikt, is **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> U kunt ook de iTunes-software gebruiken om de app te zoeken en vervolgens de opdracht **Koppeling kopiëren** gebruiken om de app-URL te krijgen.

### Inschrijvingsinstellingen
Alle instellingen zijn van toepassing op iOS 8.0 en hoger.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Activeringsvergrendeling toestaan wanneer de supervisiemodus voor het apparaat actief is**|Hiermee schakelt u Activeringsvergrendeling in op iOS-apparaten in de supervisiemodus.|

### Instellingen voor de supervisiemodus
U kunt de volgende instellingen configureren op apparaten met iOS 8.0 en hoger in de supervisiemodus.

### Supervisiemodusinstellingen voor apparaatbeperkingen

|Naam van de instelling|Details|
|----------------|--------------------|
|**Accountaanpassingen toestaan**|Toestaan dat de gebruiker accountinstellingen, zoals e-configuraties, kan wijzigen.|
|**Wijzigingen in de instellingen voor het gebruik van mobiel dataverkeer voor apps toestaan**|De gebruiker toestaan om te bepalen welke apps mobiel dataverkeer mogen gebruiken.|
|**Gebruik van de optie voor het wissen van alle inhoud en instellingen op het apparaat toestaan**|Hiermee staat u gebruikers toe de optie te gebruiken voor het wissen van alle inhoud en instellingen op het apparaat.|
|**Door de gebruiker inschakelen van beperkingen in de apparaatinstellingen toestaan**|Hiermee staat u gebruikers toe beperkingen voor het apparaat te configureren (ouderlijk toezicht).|
|**Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld, toestaan**|Hiermee staat u het koppelen met een host toe, waarmee de beheerder kan bepalen aan welke apparaten een iOS-apparaat kan worden gekoppeld.|
|**Door de gebruiker installeren van configuratieprofielen en -certificaten toestaan**|De gebruiker toestaan om configuratieprofielen en -certificaten te installeren.|
|**Wijzigen van de apparaatnaam toestaan**|Hiermee staat u de gebruiker toe de naam van het apparaat te wijzigen.|
|**Wijzigen van de wachtwoordcode toestaan**|Hiermee staat u toevoeging, wijziging of verwijdering van het apparaatwachtwoord toe.|
|**Koppelen met Apple Watch toestaan**|Hiermee staat u toe dat het apparaat met een Apple Watch koppelt.|
|**Wijzigen van de meldingsinstellingen toestaan**|Hiermee staat u de gebruiker toe de instellingen voor apparaatmeldingen te wijzigen.|
|**Wijzigen van de achtergrond toestaan**|Hiermee staat u de gebruiker toe de achtergrond van het apparaat te wijzigen.|

### Supervisiemodusinstellingen voor functiebeperkingen

|Naam van de instelling|Details|
|----------------|--------------------|
|**AirDrop toestaan**|Hiermee staat u het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.|
|**Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet toestaan**|Hiermee staat u Siri toe om websites te raadplegen om vragen te beantwoorden.|
|**Siri-filter voor scheldwoorden gebruiken**|Hiermee voorkomt u het dicteren van grove taal met Siri of dat Siri grove taal spreekt.|
|**Retourneren van resultaten op internet voor zoekopdrachten met Spotlight toestaan**|Hiermee staat u toe dat Spotlight zoekt op en verbinding maakt met internet voor aanvullende resultaten.|
|**Opzoeken van definities van woorden toestaan**|Hiermee staat u de iOS-functie toe waarmee u een woord markeert en de definitie ervan opzoekt.|
|**Tekstvoorspelling toestaan**|Hiermee staat u toe dat suggesties worden gegeven voor woorden die de gebruiker mogelijk wil invoeren.|
|**Automatische correctie toestaan**|Hiermee kunnen verkeerd gespelde woorden automatisch worden gecorrigeerd.|
|**Spellingcontrole toestaan**|Hiermee staat u gebruik van de spellingcontrole van het apparaat toe.|
|**Sneltoetsen toestaan**|Hiermee staat u gebruik van sneltoetsen toe.|

### Supervisiemodusinstellingen voor app-beperkingen

|Naam van de instelling|Details|
|----------------|--------------------|
|**Wijzigen van de vertrouwensinstellingen voor bedrijfsapps toestaan**|Hiermee kunnen gebruikers de vertrouwensinstellingen voor bedrijfsapps wijzigen.|
|**Installeren van apps met alleen Apple-configuratie en iTunes toestaan**|Hiermee wordt de App Store vanaf de startpagina van het apparaat in- of uitgeschakeld. Gebruikers kunnen nog steeds iTunes of het hulpprogramma Apple Configurator gebruiken om apps te installeren en bij te werken.|
|**Automatisch downloaden van apps toestaan**|Hiermee wordt toegestaan dat apps die met andere apparaten worden gekocht automatisch naar dit apparaat worden gedownload. Deze instelling is niet van invloed op app-updates.|
|**Wijzigingen in de instellingen van de app Zoek vrienden toestaan**|Toestaan dat de gebruiker de instellingen van de app Zoek vrienden kan wijzigen.|
|**Toegang tot de iBooks Store toestaan**|De gebruiker toestaan om door boeken in de iBooks Store te bladeren en om boeken te kopen.|
|**Gebruik van de app Berichten op het apparaat toestaan**|Toestaan dat de app Berichten kan worden gebruikt om berichten te verzenden.|
|**Gebruik van Podcasts toestaan**|Hiermee staat u gebruik van Podcasts toe.|
|**Gebruik van de service Music toestaan**|Hiermee staat u gebruik van de app Apple Music toe.|
|**iTunes Radio toestaan**|Hiermee staat u gebruik van de app iTunes Radio toe.|
|**Apple Nieuws toestaan**|Hiermee staat u gebruik van de app Apple Nieuws toe.|
|**Game Center toestaan**|Toestaan dat de Game Center-app wordt gebruikt.|


### Apps weergeven of verbergen

Gebruik de **Lijst met verborgen en weergegeven apps** om de volgende bewerkingen uit te voeren op apparaten met iOS 9.3 of hoger die onder supervisie staan:

- Een lijst opstellen met apps die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of starten.
- Een lijst opstellen met apps die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.


#### Een lijst met verborgen of weergegeven apps maken

Specificeer de volgende instellingen:

|Naam van de instelling|Details|
|-|-|
|**Lijst met verborgen en weergegeven apps**|Schakel deze instelling in als u een lijst met verborgen of weergegeven apps wilt maken.|
|**De vermelde apps verbergen voor gebruikers**|Selecteer deze optie als u een lijst wilt maken met apps die verborgen zullen zijn voor gebruikers.|
|**Alleen de vermelde apps voor gebruikers weergeven**|Selecteer deze optie als u een lijst wilt maken met apps die worden weergegeven voor gebruikers.<br>Wanneer u dit lijsttype maakt, worden alle andere apps, met uitzondering van de IOS-apps **Instellingen** en **Telefoon** (voor iPhones), verborgen.<br>Bovendien moet u de app Bedrijfsportal en alle apps die u hebt geïmplementeerd en die u beheert met Intune, aan de lijst toevoegen.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst.<br>Voor de lijst met verborgen apps moet u de **Naam**, **Uitgever** en **App-URL of bundel-id** opgeven van elke app die u wilt verbergen.<br>Voor de lijst met weergegeven apps kunt u de optie **Selecteer een beheerde app** kiezen om een lijst weer te geven met de apps die u beheert met Intune en waaruit u apps kunt selecteren. U kunt voor deze lijst ook de optie Selecteer een Store-app kiezen, waarna u de **Naam**, **Uitgever** en **App-URL of bundel-id** moet opgeven van elke app die u wilt weergeven.|
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik de notatie, toepassingsnaam, uitgever en app-URL in het bestand.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de URL van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|

#### App-informatie voor ingebouwde iOS-apps

Gebruik de informatie in deze lijst om de naam, uitgever en bundel-id te achterhalen van de ingebouwde iOS-apps die u wilt weergeven of verbergen. Als u alle apps in de lijst wilt weergeven of verbergen, kunt u de gegevens eronder kopiëren naar een tekstbestand met de extensie **.csv** en vervolgens de optie **Apps importeren** gebruiken om alle apps tegelijkertijd te importeren.

```
App Store,Apple,com.apple.AppStore
Calculator,Apple,com.apple.calculator
Calendar,Apple,com.apple.mobilecal
Camera,Apple,com.apple.camera
Clock,Apple,com.apple.mobiletimer
Compass,Apple,com.apple.compass
Contacts,Apple,com.apple.MobileAddressBook
FaceTime,Apple,com.apple.facetime
Find Friends,Apple,com.apple.mobileme.fmf1
Find iPhone,Apple,com.apple.mobileme.fmip1
Game Center,Apple,com.apple.gamecenter
GarageBand,Apple,com.apple.mobilegarageband
Health,Apple,com.apple.Health
iBooks,Apple,com.apple.iBooks
iTunes Store,Apple,com.apple.MobileStore
iTunes U,Apple,com.apple.itunesu
Keynote,Apple,com.apple.Keynote
Mail,Apple,com.apple.mobilemail
Maps,Apple,com.apple.Maps
Messages,Apple,com.apple.MobileSMS
Music,Apple,com.apple.Music
News,Apple,com.apple.news
Notes,Apple,com.apple.mobilenotes
Numbers,Apple,com.apple.Numbers
Pages,Apple,com.apple.Pages
Photo Booth,Apple,com.apple.Photo-Booth
Photos,Apple,com.apple.mobileslideshow
Podcasts,Apple,com.apple.podcasts
Reminders,Apple,com.apple.reminders
Safari,Apple,com.apple.mobilesafari
Settings,Apple,com.apple.Preferences
Stocks,Apple,com.apple.stocks
Tips,Apple,com.apple.tips
Videos,Apple,com.apple.videos
VoiceMemos,Apple,com.apple.VoiceMemos
Wallet,Apple,com.apple.Passbook
Watch,Apple,com.apple.Bridge
Weather,Apple,com.apple.weather


```




## Aangepaste beleidsinstellingen

Gebruik het **Aangepaste iOS-configuratiebeleid** van Microsoft Intune om instellingen die u met het [hulpprogramma Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) hebt gemaakt, op iOS-apparaten te implementeren. Met dit hulpprogramma kunt u veel instellingen configureren die de werking van deze apparaten regelen, en deze instellingen exporteren naar een configuratieprofiel. U kunt dit configuratieprofiel vervolgens importeren naar een aangepast Intune iOS-beleid en de instellingen implementeren voor gebruikers en apparaten in uw organisatie.

Op deze manier kunt u iOS-instellingen implementeren die niet met het algemene configuratiebeleid van Intune kunnen worden geconfigureerd.

### Vereisten
Voordat u begint, moet u de Apple Configurator hebben geïnstalleerd en een configuratiebestand hebben gemaakt met de instellingen die u wilt implementeren voor de gebruikers en apparaten. In [de Mac App Store](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) kunt u de Apple Configurator downloaden en meer informatie over dit hulpprogramma vinden.

> [!NOTE]
> Er wordt door Intune niet gerapporteerd of de afzonderlijke instellingen in een aangepast iOS-beleid compatibel zijn. Er wordt echter wel gerapporteerd of het beleid in z’n geheel compatibel is.

### Algemene instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam**|Voer een unieke naam in voor het aangepaste iOS-beleid, zodat dit in de Intune-console gemakkelijk is te herkennen.|
    |**Beschrijving**|Geef een beschrijving op die een overzicht biedt van het aangepaste iOS-beleid, evenals andere relevante informatie die u helpt om het beleid terug te vinden.|

### Aangepaste instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
|**Aangepaste configuratieprofielnaam (weergegeven voor gebruikers)**|Geef een naam op voor het beleid, zoals dit moet worden weergegeven op het apparaat en in de Intune-beleidsrapporten.|
|**Configuratieprofielbestand**|Kies **Importeren** en blader vervolgens naar het configuratieprofiel dat u hebt gemaakt met de Apple Configurator. **Opmerking:** controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert, compatibel zijn met de iOS-versie op de apparaten waarop u het aangepaste iOS-beleid implementeert. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).|
    |**Configuratieprofieldetails**|Hiermee geeft u de XML-code weer voor het configuratieprofiel dat u hebt geïmporteerd.|

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Sep16_HO2-->


