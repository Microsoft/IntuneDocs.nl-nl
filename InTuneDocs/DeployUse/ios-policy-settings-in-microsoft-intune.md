---
title: Instellingen voor iOS-beleid | Microsoft Intune
description: Maak beleid waarmee instellingen en functies worden beheerd op iOS-apparaten die u met Intune beheert.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/26/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 947328a5c28839d8227a9e5ae0dd8b1fc5ad8e81
ms.openlocfilehash: 63bc2cedf8d81b050a384a947a0b43827de5c352


---

# Instellingen voor iOS-beleid in Microsoft Intune

Intune biedt diverse ingebouwde algemene instellingen die u op iOS-apparaten kunt configureren. Daarnaast kunt u het hulpprogramma Apple Configurator gebruiken om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.

## Instellingen voor algemeen configuratiebeleid

Gebruik het **algemene iOS-configuratiebeleid** van Microsoft Intune om instellingen te configureren voor:

-   **Algemene apparaat- en beveiligingsinstellingen**: hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u diverse functies en functionaliteiten op het apparaat kunt beheren.

-   **Kioskmodus**: hiermee vergrendelt u een apparaat, zodat alleen bepaalde functies werken. U kunt bijvoorbeeld toestaan dat een apparaat slechts één beheerde app uitvoert die u opgeeft, of u kunt de volumeknoppen op een apparaat uitschakelen. Deze instellingen kunnen worden gebruikt voor een demonstratiemodel van een apparaat of voor een apparaat dat is toegewezen aan slechts één functie, zoals een verkooppuntapparaat.

-   **Compatibele en niet-compatibele apps**: hiermee geeft u een lijst op met toepassingen die compatibel of niet compatibel zijn in uw bedrijf. Op Android- en iOS-apparaten kan het **Rapport niet-compatibele apps** worden gebruikt om de compatibiliteit van apps die u in de lijst hebt opgegeven, te vergelijken met de apps die gebruikers hebben geïnstalleerd (de installatie van de app kan echter niet worden geblokkeerd).

> [!TIP]
> U kunt voorwaarden voor gebruikers configureren om ervoor te zorgen dat ze ermee instemmen dat apps op hun apparaat, waaronder persoonlijke apps, worden geëvalueerd, en dat niet-compatibele apps worden geblokkeerd of gerapporteerd als niet-compatibel. Gebruikers moeten deze voorwaarden accepteren voordat ze hun apparaat kunnen registreren en de bedrijfsportal kunnen gebruiken om apps op te halen. Zie [Instellingen voor het voorwaardenbeleid in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md) voor meer informatie over het gebruik van de voorwaarden.

Als de instelling die u zoekt, niet wordt weergegeven in dit onderwerp, kunt u de instelling wellicht maken met behulp van een aangepast iOS-beleid dat u in staat stelt instellingen te importeren die u hebt gemaakt met behulp van de [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Zie **Aangepaste beleidsinstellingen** verderop in dit onderwerp voor meer informatie.

### Beveiligingsinstellingen
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Hiermee geeft u op of gebruikers een wachtwoord moeten invoeren voor toegang tot hun apparaat.|
|**Vereist wachtwoordtype**|Hiermee geeft u het type wachtwoord op dat vereist is, zoals alleen numeriek of alfanumeriek.|
|**Aantal complexe tekens dat is vereist in wachtwoord**|Hiermee geeft u het aantal symbooltekens (zoals **#** of **@**) op dat moet zijn opgenomen in het wachtwoord.|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimumaantal tekens op voor het wachtwoord.|
|**Eenvoudige wachtwoorden toestaan**|Hiermee staat u eenvoudige wachtwoorden toe, bijvoorbeeld '0000' en '1234'.|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Wist de gegevens op het apparaat als dit aantal aanmeldingspogingen mislukt.|
|**Minuten inactief voordat wachtwoord is vereist**<sup>1</sup>|Hiermee geeft u op hoelang het apparaat inactief kan zijn voordat gebruikers hun wachtwoord opnieuw moeten invoeren.|
|**Wachtwoordverlooptijd (dagen)**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u op of de gebruiker eerder gebruikte wachtwoorden mag gebruiken.|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**<sup>1</sup>|Hiermee geeft u het aantal minuten op waarna het apparaatscherm wordt uitgeschakeld.|
|**Vingerafdruk voor ontgrendelen toestaan**|Hiermee staat u toe dat het apparaat kan worden ontgrendeld met een vingerafdruk.|
<sup>1</sup> Wanneer u bij iOS-apparaten de instellingen **Minuten van inactiviteit voordat het scherm wordt uitgeschakeld** en **Minuten van inactiviteit voordat wachtwoord vereist is** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **5** minuten, wordt het scherm na 5 minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens 5 minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat 5 minuten later vergrendeld.

### Systeeminstellingen
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Schermopname toestaan**|Hiermee staat u de gebruiker toe om de inhoud van het scherm vast te leggen als afbeelding.|
|**Beheercentrum in vergrendelingsscherm toestaan**|Bepaalt of toegang tot de Control Center-app mogelijk is wanneer het apparaat is vergrendeld.|
|**Weergave van meldingen in vergrendelingsscherm toestaan**|Hiermee staat u de gebruiker toegang tot de weergave van meldingen toe zonder het apparaat te ontgrendelen.|
|**Weergave van vandaag in vergrendelingsscherm toestaan**|Bepaalt of meldingen kunnen worden bekeken wanneer het apparaat is vergrendeld.|
|**Niet-vertrouwde TLS-certificaten toestaan**|Hiermee staat u niet-vertrouwde TLS-certificaten (Transport Layer Security) op het apparaat toe.|
|**Verzending van diagnostische gegevens toestaan**|Hiermee staat u verzending van diagnostische gegevens naar Apple toe voor het apparaat of weigert u dit.|
|**Passbook tijdens vergrendeling toestaan**|Hiermee staat u de gebruiker toegang tot de app Passbook toe terwijl het apparaat is vergrendeld.|

### Cloudinstellingen – documenten en gegevens
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Back-up naar iCloud® toestaan**|Hiermee staat u de gebruiker toe een back-up van het apparaat naar iCloud te maken.|
|**Documentsynchronisatie met iCloud toestaan**|Hiermee staat u synchronisatie van documenten en sleutelwaarden naar uw iCloud-opslagruimte toe.|
|**Photo Stream-synchronisatie met iCloud toestaan**|Hiermee staat u synchronisatie van foto's op het apparaat met iCloud toe.|
|**Versleutelde back-ups vereisen**|Hiermee vereist u dat back-ups van het apparaat worden versleuteld.|
|**Beheerde apps toestaan gegevens naar iCloud te synchroniseren**|Toestaan dat apps die u met Intune beheert, gegevens synchroniseren naar het iCloud-account van de gebruikers.|
|**Handoff toestaan om activiteiten op een ander apparaat voort te zetten**|Met Handoff kunt u doorgaan met werk waaraan u bent begonnen op een iOS-apparaat, op een ander iOS- of Mac OS X-apparaat.|

### Toepassingsinstellingen - browser
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Safari toestaan**|Hiermee geeft u op of de Safari-browser op het apparaat kan worden gebruikt.|
|**Automatisch invullen toestaan**|Gebruiker kan de instellingen voor automatisch aanvullen in de browser wijzigen.|
|**Pop-upblokkering toestaan**|Hiermee schakelt u de pop-upblokkering voor de browser in of uit.|
|**Cookies toestaan**|Hiermee staat u toe dat de webbrowser van het apparaat gebruikmaakt van cookies.|
|**Gebruik van Java-scripts toestaan**|Hiermee staat u de uitvoering van Java-scripts in de browser toe.|
|**Waarschuwing voor fraude toestaan**|Hiermee staat u waarschuwingen voor fraude in de browser van het apparaat toe.|

### Toepassingsinstellingen - apps
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Toepassingsarchief toestaan**|Hiermee staat u het apparaat toegang tot de App Store toe.|
|**Wachtwoord vereisen voor toegang tot het toepassingsarchief**|Hiermee wordt vereist dat gebruikers een wachtwoord invoeren voordat ze de app-winkel kunnen bezoeken.|
|**Aankopen in app toestaan**|Hiermee staat u toe dat Store-aankopen kunnen worden uitgevoerd vanuit een actieve app.|
|**Beheerde documenten in andere niet-beheerde apps toestaan**|Hiermee staat u toe dat zakelijke documenten kunnen worden weergegeven in elke app.<br>**Voorbeeld:** u wilt voorkomen dat gebruikers bestanden uit de OneDrive-app opslaan in Dropbox. Stel deze instelling in op Nee. Nadat het apparaat het beleid heeft ontvangen (bijvoorbeeld nadat het opnieuw is opgestart), kunnen er geen bestanden meer worden opgeslagen.|
|**Niet-beheerde documenten in andere beheerde apps toestaan**|Hiermee staat u toe dat elk document kan worden weergegeven in zakelijke beheerde apps.|
|**Videovergaderingen toestaan**|Hiermee staat u videovergadering-apps, zoals Facetime, op het apparaat toe.|
|**Inhoud voor volwassenen in media store toestaan**|Hiermee staat u het apparaat toegang tot inhoud voor volwassenen toe.|
|**Toestaan dat de gebruiker als Erotisch aangeduide inhoud kan downloaden uit de iBooks Store**|Gebruikers toestaan dat ze boeken uit de categorie Erotisch kunnen downloaden.|

### Toepassingsinstellingen - games
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Game Center-vrienden toestaan**|Hiermee staat u de gebruiker toe vrienden toe te voegen in Game Center.|
|**Games voor meerdere spelers toestaan**|Hiermee staat u de gebruiker toe op het apparaat games voor meerdere spelers te spelen.|

### Instellingen voor apparaatmogelijkheden - hardware
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Camera toestaan**|Hiermee geeft u op of de camera op het apparaat kan worden gebruikt.|
|**Een wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**|Met Airplay kunt u inhoud naar andere Apple-apparaten streamen. Gebruik deze instelling om een wachtwoord voor koppelen verplicht te stellen om verbinding te maken met andere apparaten.|

### Instellingen voor apparaatmogelijkheden - mobiel
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Spraakroaming toestaan**|Hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|
|**Gegevensroaming toestaan**|Hiermee staat u gegevensroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|
|**Op de achtergrond ophalen tijdens roamen toestaan**|Hiermee staat u toe dat het apparaat gegevens zoals e-mail ophaalt tijdens roaming op een mobiel netwerk.|

### Instellingen voor apparaatmogelijkheden - functies
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|-------|
|**Siri toestaan**|Hiermee staat u gebruik van de spraakassistent Siri op het apparaat toe.|
|**Siri toestaan terwijl apparaat is vergrendeld**|Hiermee staat u gebruik van de spraakassistent Siri op het apparaat toe terwijl het apparaat is vergrendeld.|
|**Nummer inspreken toestaan**|Hiermee staat u gebruik van de functie voor het inspreken van telefoonnummers op het apparaat toe.|


### Instellingen voor compatibele en niet-compatibele apps
In de lijst **Compatibele en&amp; niet-compatibele apps** geeft u een lijst met compatibele of niet-compatibele apps op met behulp van de volgende gegevens:

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met compatibele of een lijst met niet-compatibele apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Hiermee wordt een lijst gemaakt met de apps die niet worden beheerd door Intune en die niet mogen worden geïnstalleerd en uitgevoerd door gebruikers.|
|**Niet-compliantie melden wanneer gebruikers apps installeren die niet in de lijst staan**|Hiermee wordt een lijst gemaakt met de apps die gebruikers mogen installeren. Om te blijven voldoen aan het beleid, mogen gebruikers apps die niet worden vermeld, niet installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store. Lees **URL’s voor app stores opgeven** verderop in dit onderwerp voor meer informatie.|
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik de notatie, toepassingsnaam, uitgever en app-URL in het bestand.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de URL van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|

### Instellingen voor kioskmodus

|Naam van de instelling|Details|
|----------------|--------------------|
|**Een beheerde app selecteren die mag worden uitgevoerd wanneer het apparaat in kioskmodus is**|Kies **Bladeren** en geef de beheerde app, of een app in een store, op die mag worden uitgevoerd wanneer het apparaat in kioskmodus is. Er mogen geen andere apps worden uitgevoerd op het apparaat. Zie **URL's voor app stores opgeven** verderop in dit onderwerp voor meer informatie.|
|**Aanraakscherm toestaan**|Hiermee wordt het aanraakscherm op het apparaat in- of uitgeschakeld.|
|**Schermrotatie toestaan**|Hiermee wordt de wijziging van de schermstand wanneer u het apparaat roteert, in- of uitgeschakeld.|
|**Volumeknoppen toestaan**|Hiermee wordt het gebruik van de volumeknoppen op het apparaat in- of uitgeschakeld.|
|**Schakelaar voor belsignaal toestaan**|Hiermee wordt de schakelaar voor belsignaal (dempen) op het apparaat in- of uitgeschakeld.|
|**Knop voor slaapstand/ontwaken van scherm toestaan**|Hiermee wordt de knop voor slaapstand/ontwaken van het scherm in- of uitgeschakeld op het apparaat.|
|**Automatisch vergrendelen toestaan**|Hiermee wordt automatische vergrendeling van het apparaat in- of uitgeschakeld.|
|**Monogeluid inschakelen**|Hiermee wordt de toegankelijkheidsinstelling **Monogeluid**in- of uitgeschakeld.|
|**Voice-over inschakelen**|Hiermee wordt de toegankelijkheidsinstelling **Voice-over** die tekst op het apparaatscherm voorleest, in- of uitgeschakeld.|
|**Aanpassingen aan voice-over inschakelen**|Hiermee worden aanpassingen aan de functie Voice-over (bijvoorbeeld hoe snel schermtekst wordt voorgelezen) in- of uitgeschakeld.|
|**Zoomen inschakelen**|Hiermee wordt de toegankelijkheidsinstelling **Zoomen** waarmee u via aanraken kunt inzoomen op het apparaatscherm, in- of uitgeschakeld.|
|**Aanpassingen aan zoomen inschakelen**|Hiermee worden aanpassingen aan de zoomfunctie in- of uitgeschakeld.|
|**Kleuren omkeren inschakelen**|Hiermee wordt de toegankelijkheidsinstelling **Kleuren omkeren** die het scherm aanpast voor gebruikers met een beperkt gezichtsvermogen, in- of uitgeschakeld.|
|**Aanpassingen aan kleuren omkeren inschakelen**|Hiermee worden aanpassingen aan de functie Kleuren omkeren in- of uitgeschakeld.|
|**Ondersteunend aanraken inschakelen**|Hiermee wordt de toegankelijkheidsinstelling **Ondersteunend aanraken** waarmee gebruikers schermbewegingen kunnen uitvoeren die moeilijk voor hen kunnen zijn, in- of uitgeschakeld.|
|**Aanpassingen aan ondersteunend aanraken inschakelen**|Hiermee worden aanpassingen aan de functie Ondersteunend aanraken in- of uitgeschakeld.|
|**Spraakselectie inschakelen**|Hiermee worden de toegankelijkheidsinstellingen voor **Selectie uitspreken** waarmee door u geselecteerde tekst wordt voorgelezen, in- of uitgeschakeld.|
> [!NOTE]
> De volgende opmerkingen zijn van toepassing op kioskmodusinstellingen voor iOS-apparaten:
> 
> -   Voordat u een iOS-apparaat voor kioskmodus kunt configureren, moet u het [hulpprogramma Apple Configurator](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12) gebruiken om het apparaat in de modus Supervisie te plaatsen. Zie de Apple-documentatie voor meer informatie over het hulpprogramma Apple Configurator.
> -   Als de iOS-app die u opgeeft, wordt geïnstalleerd nadat u het configuratiebeleid hebt geïmplementeerd, kan het apparaat pas in kioskmodus worden geplaatst nadat het opnieuw is opgestart.

### Referentie-informatie voor compatibele en niet-compatibele apps

#### Compatibele apps en niet-compatibele apps controleren
Gebruik het **Rapport met niet-compatibele apps** om de compatibiliteit van toegestane en geblokkeerde apps weer te geven.

##### Het rapport met niet-compatibele apps uitvoeren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Rapporten** &gt; **Rapport met niet-compatibele apps**.

2.  Selecteer de apparaatgroepen die u wilt controleren, of u nu op compatibele en/of op niet-compatibele apps wilt controleren, en kies vervolgens **Rapport weergeven**.

#### URL's voor app stores opgeven
Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps of in de optie **Selecteer een beheerde app die actief mag zijn als het apparaat in kioskmodus is** (alleen iOS), gebruikt u de volgende indeling:

Gebruik een zoekmachine om de app te zoeken die u wilt gebruiken in de iTunes App Store en open de pagina voor de app.

Kopieer de URL van de pagina en gebruik deze als de URL voor het configureren van de lijst met compatibele of niet-compatibele apps of de app die u wilt uitvoeren in kioskmodus.

**Voorbeeld:** Zoek naar **Microsoft Word voor iPad**. De URL die u gebruikt, is **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> U kunt ook de iTunes-software gebruiken om de app te zoeken en vervolgens de opdracht **Koppeling kopiëren** gebruiken om de app-URL te krijgen.

### Inschrijvingsinstellingen
Alle instellingen zijn van toepassing op iOS 7.1 en hoger.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Activeringsvergrendeling toestaan wanneer de supervisiemodus voor het apparaat actief is**|Hiermee schakelt u Activeringsvergrendeling in op iOS-apparaten in de supervisiemodus.|

### Supervisie
De volgende instellingen kunnen worden geconfigureerd op apparaten met iOS 7.1 en hoger in de supervisiemodus.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Accountaanpassingen toestaan**|Toestaan dat de gebruiker accountinstellingen, zoals e-configuraties, kan wijzigen.|
|**AirDrop toestaan**|Gebruik van de functie Airdrop voor het uitwisselen van inhoud met apparaten in de omgeving toestaan.|
|**Wijzigingen in de instellingen voor het gebruik van mobiel dataverkeer voor apps toestaan**|De gebruiker toestaan om te bepalen welke apps mobiel dataverkeer mogen gebruiken.|
|**Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet toestaan**|Siri toestaan om websites te raadplegen om vragen te beantwoorden.|
|**Toegang tot de iBooks Store toestaan**|De gebruiker toestaan om door boeken in de iBooks Store te bladeren en om boeken te kopen.|
|**Wijzigingen in de instellingen van de app Zoek vrienden toestaan**|Toestaan dat de gebruiker de instellingen van de app Zoek vrienden kan wijzigen.|
|**Gebruik van de optie voor het wissen van alle inhoud en instellingen op het apparaat toestaan**|De gebruikers toestaan om de optie te gebruiken voor het wissen van alle inhoud en instellingen op het apparaat.|
|**Door de gebruiker inschakelen van beperkingen in de apparaatinstellingen toestaan**|Door de gebruiker configureren van beperkingen voor het apparaat (ouderlijk toezicht) op het apparaat toestaan|
|**Retourneren van resultaten op internet voor zoekopdrachten met Spotlight toestaan**|Spotlight laten zoeken en verbinding maken met het internet voor aanvullende resultaten.|
|**Het gebruik van de Game Center-app toestaan**|Toestaan dat de Game Center-app wordt gebruikt.|
|**Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld, toestaan**|Door te koppelen met een host kan de beheerder bepalen aan welke apparaten een iOS 7-apparaat kan worden gekoppeld.|
|**Door de gebruiker installeren van configuratieprofielen en -certificaten toestaan**|De gebruiker toestaan om configuratieprofielen en -certificaten te installeren.|
|**Gebruik van de app Berichten op het apparaat toestaan**|Toestaan dat de app Berichten kan worden gebruikt om berichten te verzenden.|


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
|**Configuratieprofielbestand**|Kies **Importeren** en blader vervolgens naar het configuratieprofiel dat u hebt gemaakt met behulp van de Apple Configurator. **Opmerking:** controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert, compatibel zijn met de iOS-versie op de apparaten waarop u het aangepaste iOS-beleid implementeert. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).|
    |**Configuratieprofieldetails**|Geeft de XML-code weer voor het configuratieprofiel dat u hebt geïmporteerd.|

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO4-->


