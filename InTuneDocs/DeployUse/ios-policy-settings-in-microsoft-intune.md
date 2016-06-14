---
# required metadata

title: Instellingen voor iOS-beleid in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ab46be6c-ab73-4c99-8492-66d1dd418293

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instellingen voor iOS-beleid in Microsoft Intune

## Instellingen voor algemeen configuratiebeleid

Gebruik het **algemene iOS-configuratiebeleid** van Microsoft Intune om instellingen te configureren voor:

-   **Beveiligingsinstellingen voor mobiele apparaten**: hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u een bereik aan functies en functionaliteiten op het apparaat kunt beheren.

-   **Kioskmodus**: hiermee vergrendelt u een apparaat, zodat alleen bepaalde functies werken. U kunt bijvoorbeeld toestaan dat een apparaat slechts één beheerde app uitvoert die u opgeeft, of u kunt de volumeknoppen op een apparaat uitschakelen. Deze instellingen kunnen worden gebruikt voor een demonstratiemodel van een apparaat of voor een apparaat dat is toegewezen aan slechts één functie, zoals een verkooppuntapparaat.

-   **Compatibele en niet-compatibele apps**: hiermee geeft u een lijst op met toepassingen die compatibel of niet compatibel zijn in uw bedrijf. Op Android- en iOS-apparaten kan het **Rapport niet-compatibele apps** worden gebruikt om de compatibiliteit van apps die u in de lijst hebt opgegeven, te vergelijken met de apps die gebruikers hebben geïnstalleerd (de installatie van de app kan echter niet worden geblokkeerd).

> [!TIP]
> U kunt voorwaarden voor gebruikers configureren om ervoor te zorgen dat ze ermee instemmen dat apps op hun apparaat, waaronder persoonlijke apps, worden geëvalueerd, en dat niet-compatibele apps worden geblokkeerd of gerapporteerd als niet-compatibel. Gebruikers moeten deze voorwaarden accepteren voordat ze hun apparaat kunnen registreren en de bedrijfsportal kunnen gebruiken om apps op te halen. Zie voor meer informatie over het gebruik van voorwaarden [Beleidsinstellingen voor voorwaarden in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md)..

Als de instelling die u zoekt, niet wordt weergegeven in dit onderwerp, kunt u de instelling wellicht maken met behulp van een aangepast iOS-beleid dat u in staat stelt instellingen te importeren die u hebt gemaakt met behulp van de [Apple Configurator Tool](https://itunes.apple.com/us/app/apple-configurator/id434433123?mt=12). Zie **Aangepaste beleidsinstellingen** verderop in dit onderwerp voor meer informatie.

### Beveiligingsinstellingen

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Hiermee geeft u op of gebruikers een wachtwoord moeten invoeren voor toegang tot hun apparaat.|Ja|
|**Vereist wachtwoordtype**|Geeft het type wachtwoord op dat vereist is, zoals alleen numeriek of alfanumeriek.|Ja|
|**Vereist wachtwoordtype – minimumaantal tekensets**|Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets er moeten worden opgenomen in het wachtwoord). Voor iOS-apparaten geeft u hiermee echter het aantal symbooltekens aan dat moet zijn opgenomen in het wachtwoord)|Ja|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimumaantal tekens op voor het wachtwoord.|Ja|
|**Eenvoudige wachtwoorden toestaan**|Hiermee staat u eenvoudige wachtwoorden toe, bijvoorbeeld '0000' en '1234'.|Ja|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Wist de gegevens op het apparaat als dit aantal aanmeldingspogingen mislukt.|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**<sup>1</sup>|Hiermee geeft u het aantal minuten op waarna het apparaatscherm wordt uitgeschakeld.|Ja|
|**Wachtwoordverlooptijd (dagen)**|Hiermee geeft u het aantal dagen op voordat het wachtwoord van het apparaat moet worden gewijzigd.|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u op of de gebruiker eerder gebruikte wachtwoorden mag gebruiken.|Ja|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|Ja|
|**Minuten inactief voordat wachtwoord is vereist**<sup>1</sup>|Hiermee geeft u op hoelang het apparaat inactief kan zijn voordat gebruikers hun wachtwoord opnieuw moeten invoeren.|Ja|
|**Vingerafdruk voor ontgrendelen toestaan**|Hiermee staat u toe dat het apparaat kan worden ontgrendeld met een vingerafdruk.|iOS 7.1 en hoger|
<sup>1</sup> Wanneer u bij iOS-apparaten de instellingen **Minuten van inactiviteit voordat het scherm wordt uitgeschakeld** en **Minuten van inactiviteit voordat wachtwoord vereist is** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **5** minuten, wordt het scherm na 5 minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens 5 minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat 5 minuten later vergrendeld.

### Systeeminstellingen

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Schermopname toestaan**|Hiermee staat u de gebruiker toe om de inhoud van het scherm vast te leggen als afbeelding.|Ja|
|**Beheercentrum in vergrendelingsscherm toestaan**|Bepaalt of toegang tot de Control Center-app mogelijk is wanneer het apparaat is vergrendeld.|iOS 7.1 en hoger|
|**Weergave van meldingen in vergrendelingsscherm toestaan**|Hiermee staat u de gebruiker toegang tot de weergave van meldingen toe zonder het apparaat te ontgrendelen.|iOS 7.1 en hoger|
|**Weergave van vandaag in vergrendelingsscherm toestaan**|Bepaalt of meldingen kunnen worden bekeken wanneer het apparaat is vergrendeld.|iOS 7.1 en hoger|
|**Verzending van diagnostische gegevens toestaan**|Hiermee staat u verzending van diagnostische gegevens naar Apple toe voor het apparaat of weigert u dit.|Ja|
|**Niet-vertrouwde TLS-certificaten toestaan**|Hiermee staat u niet-vertrouwde TLS-certificaten (Transport Layer Security) op het apparaat toe.|Ja|
|**Passbook tijdens vergrendeling toestaan**|Hiermee staat u de gebruiker toegang tot de app Passbook toe terwijl het apparaat is vergrendeld.|Ja|

### Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Back-up naar iCloud® toestaan**|Hiermee staat u de gebruiker toe een back-up van het apparaat naar iCloud te maken.|Ja|
|**Documentsynchronisatie met iCloud toestaan**|Hiermee staat u synchronisatie van documenten en sleutelwaarden naar uw iCloud-opslagruimte toe.Ja|
|**Photo Stream-synchronisatie met iCloud toestaan**|Hiermee staat u synchronisatie van foto's op het apparaat met iCloud toe.|Ja|
|**Versleutelde back-ups vereisen**|Hiermee vereist u dat back-ups van het apparaat worden versleuteld.|Ja|

### Toepassingsinstellingen - browser

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Safari toestaan**|Hiermee geeft u op of de Safari-browser op het apparaat kan worden gebruikt.|Ja|
|**Automatisch invullen toestaan**|Gebruiker kan de instellingen voor automatisch aanvullen in de browser wijzigen.|Ja|
|**Pop-upblokkering toestaan**|Hiermee schakelt u de pop-upblokkering voor de browser in of uit.|Ja|
|**Cookies toestaan**|Hiermee staat u toe dat de webbrowser van het apparaat gebruikmaakt van cookies.|Ja|
|**Gebruik van Java-scripts toestaan**|Hiermee staat u de uitvoering van Java-scripts in de browser toe.|Ja|
|**Waarschuwing voor fraude toestaan**|Hiermee staat u waarschuwingen voor fraude in de browser van het apparaat toe.|Ja|

### Toepassingsinstellingen - apps

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Toepassingsarchief toestaan**|Hiermee staat u het apparaat toegang tot de App Store toe.|Ja|
|**Wachtwoord vereisen voor toegang tot het toepassingsarchief**|Ja|
|**Aankopen in app toestaan**|Hiermee staat u toe dat Store-aankopen kunnen worden uitgevoerd vanuit een actieve app.|Ja|
|**Beheerde documenten in andere niet-beheerde apps toestaan**|Hiermee staat u toe dat zakelijke documenten kunnen worden weergegeven in elke app.|iOS 7.1 en hoger|
|**Niet-beheerde documenten in andere beheerde apps toestaan**|Hiermee staat u toe dat elk document kan worden weergegeven in zakelijke beheerde apps.|iOS 7.1 en hoger|
|**Videovergaderingen toestaan**|Hiermee staat u videovergadering-apps, zoals Facetime, op het apparaat toe.|Ja|
|**Inhoud voor volwassenen in media store toestaan**|Hiermee staat u het apparaat toegang tot inhoud voor volwassenen toe.|Ja|

### Toepassingsinstellingen - games

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Game Center-vrienden toestaan**|Hiermee staat u de gebruiker toe vrienden toe te voegen in Game Center.|Ja|
|**Games voor meerdere spelers toestaan**|Hiermee staat u de gebruiker toe op het apparaat games voor meerdere spelers te spelen.|Ja|

### Instellingen voor apparaatmogelijkheden - hardware

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Camera toestaan**|Hiermee geeft u op of de camera op het apparaat kan worden gebruikt.|Ja|

### Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Spraakroaming toestaan**|Hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Ja|
|**Gegevensroaming toestaan**|Hiermee staat u gegevensroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Ja|
|**Op de achtergrond ophalen tijdens roamen toestaan**|Hiermee staat u toe dat het apparaat gegevens zoals e-mail ophaalt tijdens roaming op een mobiel netwerk.|Ja|

### Instellingen voor apparaatmogelijkheden - functies

|Naam van de instelling|Details|iOS|
|----------------|-------|
|**Siri toestaan**|Hiermee staat u gebruik van de spraakassistent Siri op het apparaat toe.|Ja|
|**Siri toestaan terwijl apparaat is vergrendeld**|Hiermee staat u gebruik van de spraakassistent Siri op het apparaat toe terwijl het apparaat is vergrendeld.|Ja|
|**Nummer inspreken toestaan**|Hiermee staat u gebruik van de functie voor het inspreken van telefoonnummers op het apparaat toe.|Ja|


### Instellingen voor compatibele en niet-compatibele apps
In de lijst **Compatibele &amp; niet-compatibele apps** geeft u een lijst met compatibele of niet-compatibele apps op met behulp van de volgende gegevens:

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met compatibele of een lijst met niet-compatibele apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Hiermee wordt een lijst gemaakt met de apps die niet worden beheerd door Intune en die niet mogen worden geïnstalleerd en uitgevoerd door gebruikers.|
|**Niet rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Hiermee wordt een lijst gemaakt met de apps die gebruikers mogen installeren. Om aan het beleid te blijven voldoen, mogen gebruikers niet-vermelde apps niet installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store. Lees **URL’s voor app stores opgeven** verderop in dit onderwerp voor meer informatie.|
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik de notatie, toepassingsnaam, uitgever en app-URL in het bestand.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de URL van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|

### Instellingen voor kioskmodus

|Naam van de instelling|Details|
|----------------|--------------------|
|**Een beheerde app selecteren die mag worden uitgevoerd wanneer het apparaat in kioskmodus is**|Klik op **Bladeren** en geef de beheerde app, of een app in een store, op die mag worden uitgevoerd wanneer het apparaat in kioskmodus is. Er mogen geen andere apps worden uitgevoerd op het apparaat. Zie **URL's voor app stores opgeven** verderop in dit onderwerp voor meer informatie.|
|**Aanraakscherm toestaan**|Hiermee wordt het aanraakscherm op het apparaat in- of uitgeschakeld.|
|**Schermrotatie toestaan**|Hiermee wordt de wijziging van de schermstand wanneer u het apparaat roteert, in- of uitgeschakeld.|
|**Volumeknoppen toestaan**|Hiermee wordt het gebruik van de volumeknoppen op het apparaat in- of uitgeschakeld.|
|**Schakelaar voor belsignaal toestaan**|Hiermee wordt de schakelaar voor belsignaal (dempen) op het apparaat in- of uitgeschakeld.|
|**Knop voor slaapstand/ontwaken van scherm toestaan**|Hiermee wordt de knop voor slaapstand/ontwaken van het scherm in- of uitgeschakeld op het apparaat.|
|**Automatisch vergrendelen toestaan**|Hiermee wordt automatische vergrendeling van het apparaat in- of uitgeschakeld.|
|**Monogeluid inschakelen**|Hiermee wordt de toegankelijkheidsinstelling **Monogeluid** in- of uitgeschakeld..|
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

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Rapporten** &gt; **Rapport met niet-compatibele apps**..

2.  Selecteer de apparaatgroepen die u wilt controleren, geef aan of u op compatibele of op niet-compatibele apps wilt controleren en klik vervolgens op **Rapport weergeven**..

#### URL's voor app stores opgeven
Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps of in de optie **Selecteer een beheerde app die actief mag zijn als het apparaat in kioskmodus is** (alleen iOS), gebruikt u de volgende indeling:

Gebruik een zoekmachine om de app te zoeken die u wilt gebruiken in de iTunes App Store en open de pagina voor de app.

Kopieer de URL van de pagina en gebruik deze als de URL voor het configureren van de lijst met compatibele of niet-compatibele apps of de app die u wilt uitvoeren in kioskmodus.

**Voorbeeld:** Zoek naar **Microsoft Word voor iPad**. De URL die u gebruikt, is **https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8**.

> [!NOTE]
> U kunt ook de iTunes-software gebruiken om de app te zoeken en vervolgens de opdracht **Koppeling kopiëren** gebruiken om de app-URL te krijgen.


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
|**Aangepaste configuratieprofielnaam (weergegeven voor gebruikers)**|Geef voor het beleid de naam op die moet worden weergegeven op het apparaat en in de Intune-beleidsrapporten.|
|**Configuratieprofielbestand**|Klik op **Importeren** en blader vervolgens naar het configuratieprofiel dat u hebt gemaakt met behulp van de Apple Configurator. **Opmerking:** controleer of de instellingen die u vanuit het hulpprogramma Apple Configurator exporteert, compatibel zijn met de iOS-versie op de apparaten waarop u het aangepaste iOS-beleid implementeert. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).|
    |**Configuratieprofieldetails**|Geeft de XML-code weer voor het configuratieprofiel dat u hebt geïmporteerd.|

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


