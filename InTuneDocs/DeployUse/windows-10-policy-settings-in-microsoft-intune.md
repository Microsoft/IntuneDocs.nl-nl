---
# required metadata

title: Windows 10-beleidsinstellingen in Microsoft Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Windows 10-beleidsinstellingen in Microsoft Intune

Gebruik de beleidsinstellingen in dit onderwerp als u instellingen wilt configureren voor ingeschreven Windows 10 Desktop- en Windows 10 Mobile-apparaten.

## Algemene instellingen voor configuratiebeleid

Gebruik de **algemene configuratiebeleidsregels** van Microsoft voor Windows 10 om algemene instellingen te configureren voor ingeschreven Windows 10 Desktop- en Windows 10 Mobile-apparaten:


### Wachtwoord

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Een wachtwoord vereisen om apparaten te ontgrendelden**|Hiermee vereist u een wachtwoord op ondersteunde apparaten.|Ja|Ja|
|**Vereist wachtwoordtype**|Hiermee geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek|Ja|Ja|
|**Vereist wachtwoordtype** - **Minimum aantal tekensets**|Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets er in het wachtwoord moeten worden opgenomen.|Ja|Ja|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimale aantal tekens aan dat het wachtwoord voor het apparaat moet hebben.|Nee|Ja|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Wist de gegevens op het apparaat als dit aantal aanmeldingspogingen mislukt.|Ja|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u de hoeveelheid tijd aan die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.|Ja|Ja|
|**Wachtwoordverlooptijd (dagen)**|Met deze instelling bepaalt u de periode waarna het wachtwoord van een apparaat moet worden gewijzigd.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u aan of u wilt voorkomen dat de eindgebruiker eerder gebruikte wachtwoorden mag hergebruiken.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** - **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|Ja|Ja|
|**Afbeeldingswachtwoord en PIN toestaan**|Hiermee kunt u eenvoudige bewegingen op een afbeelding of een eenvoudige pincode gebruiken voor aanmelden.|Ja|Nee|
|**Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**|Indien ingeschakeld, moet de gebruiker een wachtwoord opgeven om het apparaat vanuit een niet-actieve status te ontgrendelen.|Nee|Ja|

### Versleuteling

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Versleuteling vereisen voor mobiel apparaat**|Hiermee schakelt u versleuteling op doelapparaten in.|Nee|Ja|

### Systeem

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Schermafbeelding toestaan**|Hiermee kan de gebruiker het apparaatscherm als afbeelding vastleggen.|Nee|Ja|
|**Handmatige uitschrijving toestaan**|Hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen.|Ja|Ja|
|**Handmatige installatie van basiscertificaat toestaan**|Hiermee geeft u op of de gebruiker basiscertificaten handmatig kan installeren|Nee|Ja|
|**Toestaan dat diagnostische en gebruiksgegevens worden verzonden naar Microsoft**|Hiermee bepaalt u de hoeveelheid diagnostische en gebruiksgegevens die vanaf apparaten naar Microsoft wordt verzonden.<br>**Geen**: er worden geen gegevens naar Microsoft verzonden<br>**Basis**: het apparaat verzendt alleen een beperkte hoeveelheid informatie naar Microsoft<br>**Uitgebreid**: hiermee worden uitgebreide diagnostische gegevens naar Microsoft verzonden<br>**Volledig (aanbevolen)**: hiermee worden dezelfde gegevens verzonden als bij **Uitgebreid**, aangevuld met gegevens over de apparaatstatus|Ja|Ja|


### Account en synchronisatie

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.|Ja|Ja|
|**Handmatig toevoegen van een ander account dan een Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker aan het apparaat e-mailaccounts kan toevoegen die niet aan een Microsoft-account zijn gekoppeld.|Ja|Ja|
|**Synchronisatie van instellingen toestaan voor Microsoft-accounts**|Hiermee staat u synchronisatie tussen apparaten toe van apparaat- en app-instellingen die aan een Microsoft-account zijn gekoppeld.|Ja|Ja|

### E-mailinstellingen

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Het Microsoft-account optioneel maken in de Windows Mail-toepassing**|Configureer dit als u de vereiste voor een Microsoft-account in Windows Mail wilt verwijderen.|Ja|Nee|



### Microsoft Edge

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Webbrowser toestaan**|Hiermee staat u het gebruik van de webbrowser Edge op het apparaat toe.|Nee|Ja|
|**Zoeksuggesties in de adresbalk toestaan**|Hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt.|Ja|Ja|
|**Verzenden van intranetverkeer naar Internet Explorer toestaan**|Hiermee staat u toe dat gebruikers intranetsites in Internet Explorer kunnen openen.|Ja|Nee|
|**Do Not Track toestaan**|Hiermee configureert u de browser Edge zodanig dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken.|Ja|Ja|
|**SmartScreen inschakelen**|Hiermee schakelt u de instelling van de SmartScreen-browser op apparaten in.|Ja|Ja|
|**Active Scripting toestaan**|Hiermee staat u toe dat er in de browser Edge scripts, zoals JavaScript, kunnen worden uitgevoerd.|Ja|Ja|
|**Pop-ups toestaan**|Hiermee schakelt u de pop-upblokkering voor browsers in of uit.|Ja|Nee|
|**Cookies toestaan**|Hiermee staat u cookies toe of niet.|Ja|Ja|
|**Automatisch invullen toestaan**|Hiermee staat u gebruikers toe instellingen voor automatisch aanvullen in de browser te wijzigen.|Ja|Nee|
|**Wachtwoordbeheer toestaan**|Hiermee schakelt u de functie Wachtwoordbeheer van Edge in of uit.|Ja|Ja|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Geeft de plaats aan van de lijst met websites die in Bedrijfsmodus worden geopend. Gebruikers kunnen deze lijst niet bewerken.|Ja|Nee|

### Apps

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Toepassingsarchief toestaan**|Hiermee geeft u de gebruiker toegang tot de app store op het apparaat.|Nee|Ja|



### Mobiel

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Gegevensroaming toestaan**|Roaming tussen netwerken toestaan tijdens het ophalen van gegevens.|Ja|Ja|
|**VPN via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen indien verbonden met het mobiele netwerk.|Ja|Ja|
|**VPN-roaming via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen tijdens het roamen op een mobiel netwerk.|Ja|Ja|

### Hardware

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Camera toestaan**|Hiermee geeft u op of de camera van het apparaat kan worden gebruikt.|Ja|Ja|
|**Verwisselbare opslag toestaan**|Hiermee geeft u op of er op het apparaat externe opslagapparaten, zoals een SD-kaart, kunnen worden gebruikt.|Ja|Ja|
|**Wi-Fi toestaan**|Hiermee kunt het gebruik van de Wi-Fi-functionaliteit van het apparaat toestaan.|Nee|Ja|
|**Internetverbinding delen toestaan**|Hiermee kunt u het gebruik van een gedeelde internetverbinding op het apparaat toestaan.|Ja|Ja|
|**Handmatige Wi-Fi-configuratie toestaan**|Hiermee bepaalt u of de gebruiker zijn eigen Wi-Fi-verbindingen kan instellen, of dat de gebruiker alleen verbindingen kan gebruiken die door een Wi-Fi-profiel zijn geconfigureerd.|Nee|Ja|
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Hiermee kunt u het apparaat automatisch verbinding laten maken met gratis Wi-Fi-hotspots en automatisch de voorwaarden voor de verbinding laten accepteren.|Ja|Ja|
|**Geolocatie toestaan**|Geeft aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt.|Ja|Ja|
|**NFC toestaan**|Hiermee staat u gebruik van de NFC-mogelijkheden op het apparaat toe.|Ja|Ja|
|**Bluetooth toestaan**|Hiermee schakelt u het gebruik van Bluetooth-mogelijkheden op het apparaat in.|Ja|Ja|
|**Modus voor Bluetooth-detectie toestaan**|Hiermee kan dit apparaat worden gedetecteerd door andere Bluetooth-apparaten.|Ja|Ja|
|**Bluetooth-promotie toestaan**|Hiermee staat u toe dat apparaten reclame via Bluetooth kunnen ontvangen.|Ja|Ja|
|**Bluetooth-verbindingsmodus toestaan** **Belangrijk:** |Deze instelling wordt niet meer ondersteund voor Windows 10 en wordt in de toekomst verwijderd.|Ja|Ja|
|**Opnieuw instellen van telefoon toestaan**|Hiermee bepaalt u of de gebruiker de fabrieksinstellingen van het apparaat kan herstellen.|Ja|Ja|
|**USB-verbinding toestaan**|Hiermee bepaalt u of apparaten via een USB-verbinding toegang kunnen hebben tot externe opslagapparaten.|Ja|Ja|
|**Antidiefstalmodus toestaan**|Hiermee configureert u of de antidiefstalmodus van Windows is ingeschakeld.|Ja|Ja|

### Functies

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|----------------------|---------------------|
|**Kopiëren en plakken toestaan**|Hiermee schakelt u het gebruik van kopiëren en plakken op het apparaat in of uit.|Nee|Ja|
|**Spraakopname toestaan**|Hiermee schakelt u de spraakopnamefuncties op het apparaat in of uit.|Nee|Ja|
|**Cortana toestaan**|Hiermee schakelt u de spraakassistent Cortana in of uit.|Ja|Ja|
|**Meldingen van onderhoudscentrum toestaan**|Hiermee schakelt u de meldingen van het Onderhoudscentrum op het vergrendelingsscherm in of uit.|Nee|Ja|

### Defender

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|-|-|
|**Real-timecontrole toestaan**|Hiermee schakelt u het real-time scannen op malware, spyware en andere ongewenste software in.|Ja|Nee|
|**Gedragscontrole toestaan**|Hiermee kunt u Defender laten controleren op de aanwezigheid van bepaalde bekende patronen van verdachte activiteiten op apparaten.|Ja|Nee
|**Systeem voor netwerkinspectie inschakelen**|Het Netwerkinspectiesysteem (NIS) kan u op basis van de handtekeningen van bekende beveiligingsproblemen van het Microsoft Endpoint Protection Center helpen met het detecteren en blokkeren van schadelijk verkeer, zodat de apparaten in het netwerk beveiligd zijn tegen exploits.|Ja|Nee
|**Alle downloads scannen**|Hiermee bepaalt u of Windows Defender alle bestanden moet scannen die van internet worden gedownload.|Ja|Nee
|**Scannen van scripts toestaan**|Hiermee laat u Defender scripts scannen die worden gebruikt in Internet Explorer.|Ja|Nee
|**Activiteiten van bestanden en programma's bewaken**|Schakel deze instelling in om Defender toe te staan activiteiten van bestanden en programma's op apparaten te bewaken.|Ja|Nee
|**Dagen om opgeloste problemen met malware bij te houden**|Hiermee kunt Defender gedurende het aantal dagen dat u opgeeft, opgeloste malware laten bijhouden, zodat u handmatig eerder aangevallen apparaten kunt controleren. Als u het aantal dagen instelt op **0**, blijft malware in de map Quarantaine staan en wordt malware niet automatisch verwijderd. |Ja|Nee
|**Toegang tot gebruikersinterface van client toestaan**|Hiermee bepaalt u of de gebruikersinterface van Windows Defender voor eindgebruikers wordt verborgen.<br>Als deze instelling wordt gewijzigd, gaat de wijziging in wanneer de pc van de eindgebruiker de volgende keer opnieuw wordt opgestart.|Ja|Nee
|**Een dagelijkse snelle scan plannen**|Hiermee kunt u een snelle scan plannen die dagelijks wordt uitgevoerd op het moment dat u selecteert.|Ja|Nee
|**Een systeemscan plannen**|Hiermee kunt u een volledige of snelle systeemscan plannen die regelmatig wordt uitgevoerd op de dag en tijd die u selecteert.|Ja|Nee
|**CPU-verbruik tijdens een scan beperken**|Hiermee kunt u de hoeveelheid CPU beperken die scans mogen gebruiken (van **1** tot **100**)|Ja|Nee
|**Archiefbestanden scannen**|Hiermee kunt u toestaan dat Defender gearchiveerde bestanden scant, zoals zip- of cab-bestanden.|Ja|Nee
|**E-mailberichten scannen**|Hiermee kunt u toestaan dat Defender e-mailberichten scant wanneer deze op het apparaat binnenkomen.|Ja|Nee
|**Verwisselbare stations scannen**|Hiermee kunt u Defender verwisselbare stations, zoals USB-sticks, laten scannen.|Ja|Nee
|**Toegewezen netwerkstations scannen**|Hiermee kunt u Defender bestanden op een gekoppeld netwerkstation laten scannen.<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|Ja|Nee
|**Bestanden scannen die worden geopend vanuit gedeelde netwerkmappen**|Hiermee kunt u Defender bestanden op gedeelde stations laten scannen (bijvoorbeeld gedeelde stations die via een UNC-pad toegankelijk zijn).<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|Ja|Nee
|**Update-interval voor handtekeningen**|Hiermee geeft u het interval op waarmee Defender op nieuwe handtekeningbestanden moet controleren.|Ja|Nee
|**Cloudbeveiliging toestaan**|Hiermee kunt u toestaan of blokkeren dat de Microsoft Active Protection-service informatie ontvangt over malware-activiteit op apparaten die u beheert. Deze informatie wordt gebruikt om de service in de toekomst te verbeteren.|Ja|Nee
|**Gebruikers vragen voorbeelden te verzenden**|Hiermee bepaalt u of bestanden waarvoor verdere analyse door Microsoft nodig is om te bepalen of deze schadelijk zijn, automatisch naar Microsoft moeten worden verzonden.|Ja|Nee
|**Uit te sluiten bestanden en mappen wanneer een scan wordt uitgevoerd of bij het gebruik van realtime-beveiliging**|Voeg aan de uitsluitingslijst een of meer bestanden en mappen toe, zoals **C:\pad** of **%ProgramFiles%\pad\bestandsnaam.exe**. Deze bestanden en mappen worden niet opgenomen in real-timescans of geplande scans.|Ja|Nee
|**Uit te sluiten bestandsextensies wanneer een scan wordt uitgevoerd of bij het gebruik van realtime-beveiliging**|Voeg aan de uitsluitingslijst een of meer bestandsextensies toe, zoals **jpg** of **txt**. Alle bestanden met deze extensies worden niet opgenomen in real-timescans of geplande scans.|Ja|Nee
|**Uit te sluiten processen wanneer een scan wordt uitgevoerd of bij het gebruik van realtime-beveiliging**|Voeg aan de uitsluitingslijst een of meer processen toe van het type **.exe**, **.com** of **.scr**. Deze processen worden niet opgenomen in real-timescans of geplande scans.|Ja|Nee| 


### Instellingen voor updates

|Naam van de instelling|Details|Windows 10 Desktop|Windows 10 Mobile|
|----------------|---------------|----------------------|---------------------|
|**Automatische updates toestaan**|Schakel deze instelling in om automatische updates toe te staan. Configureer vervolgens een van de volgende instellingen om het gedrag voor updates te bepalen:<br /><br />**Melding van download**<br /><br />**Automatisch installeren op onderhoudstijdstip**<br /><br />**Automatisch installeren en opstarten op onderhoudstijdstip**<br /><br />**Automatisch installeren en opnieuw opstarten op het geplande tijdstip** **Opmerking:** wanneer deze optie is geselecteerd, kunt u ook de volgende instellingen configureren: **Melding aan eindgebruiker onderdrukken** en **De installatiedag voor geplande updates definiëren**.|Ja|Nee|

## Aangepaste beleidsinstellingen
Gebruik het **Aangepaste configuratiebeleid** van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op Windows 10- en Windows 10 Mobile-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Windows 10-instellingen implementeren die niet met het algemene configuratiebeleid van Intune kunnen worden geconfigureerd. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor informatie over de instellingen die u met dit beleid kunt configureren..

Zie 'Aangepaste URI-instellingen voor Windows 10-apparaten' verderop in dit onderwerp voor een lijst met OMA-URI-instellingen die u voor ingeschreven Windows 10-apparaten kunt configureren.

### Algemene instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam**|Voer een unieke naam in voor het beleid, zodat u het beleid in de Intune-console kunt herkennen.|
    |**Beschrijving**|Geef een beschrijving op die een overzicht geeft van het beleid en overige relevante informatie die u helpt om het beleid terug te vinden.|

### OMA-URI-instellingen

|Naam van de instelling|Details|
    |--------|--------------------|
    |**Naam van de instelling**|Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
    |**Beschrijving van instelling**|Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    |**Gegevenstype**|Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. U kunt kiezen uit:<br /><br />-   **Tekenreeks**<br />-   **Tekenreeks (XML)**<br />-   **Datum en tijd**<br />-   **Geheel getal**<br />-   **Drijvende komma**<br />-   **Boolean-waarde**|
    |**OMA-URI (hoofdlettergevoelig)**|Geef aan voor welke OMA-URI u een instelling wilt opgeven.|
    |**Waarde**|Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|


## Aangepaste URI-instellingen voor Windows-10-apparaten
In dit onderwerp vindt u de instellingen die u in **Aangepast beleid voor Windows 10** kunt configureren voor Windows 10- en Windows 10 Mobile-apparaten..


> [!NOTE]
> In de kolom **Ondersteunt** van de volgende tabel worden de volgende waarden gebruikt:
> 
> -   **Desktop**: de instelling ondersteunt alleen computers met Windows 10 Professional en Enterprise die zijn ingeschreven bij Intune.
> -   **Mobiel** : de instelling ondersteunt alleen apparaten met Windows 10 Mobile.
> -   **Beide** : de instelling ondersteunt zowel desktopapparaten als mobiele apparaten.
> 
> Alle apparaten moeten worden ingeschreven bij Intune als u het aangepaste Windows URI-beleid wilt gebruiken.

### Beleid

|Naam van beleid|Ondersteunt|Details|
|---------------|------------|-----------|
|**​Automatisch bijwerken toestaan**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0** - **5**<br /><br />**Standaardwaarde:** 1|
|**Planning installatiedag**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: elke dag.<br /><br />**1**: zondag<br /><br />**2**: maandag<br /><br />**3**: dinsdag<br /><br />**4**: woensdag<br /><br />**5**: donderdag<br /><br />**6**: vrijdag<br /><br />**7**: zaterdag.<br /><br />**Standaardwaarde:** 0|
|**Planning installatietijd**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: **23** uur (0 is middernacht)<br /><br />**Standaardwaarde:** 3|
|**DeviceLock/AllowIdleReturnWithoutPassword**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: de gebruiker kan de timer van de respijtperiode voor het wachtwoord niet instellen en de waarde is ingesteld als 'elke keer'<br /><br />**1**: de gebruiker kan de timer van de respijtperiode voor het wachtwoord instellen<br /><br />**Standaardwaarde:** 1|
|**WiFi/AllowWiFi**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: **Wi-Fi-verbinding gebruiken** niet toestaan.<br /><br />**1**: **Gebruik van Wi-Fi-verbinding toestaan**.<br /><br />**Standaardwaarde:** 1|
|**WiFi/AllowInternetSharing**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : internet delen niet toestaan.<br /><br />**1** : internet delen toestaan<br /><br />**Standaardwaarde:** 1|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**WiFi/AllowManualWiFiConfiguration**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: een Wi-Fi-verbinding buiten de ingerichte MDM is niet toegestaan.<br /><br />**1** : het toevoegen van een nieuwe netwerk SSID buiten de al aanwezige MDM is toegestaan.<br /><br />**Standaardwaarde:** 1|
|**System/AllowLocation**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**System/AllowTelemetry**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan (instelling alleen voor Enterprise)<br /><br />**1** : beperkt<br /><br />**2** : volledig<br /><br />**3**: volledige en diagnostische gegevens<br /><br />**Standaardwaarde:** 2|
|**System/AllowExperimentation**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1**: alleen instellingen<br /><br />**2**: instellingen en experimenteren<br /><br />**Standaardwaarde:** 1|
|**Security/AntiTheftMode**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: Antidiefstalmodus niet toestaan<br /><br />**1** : gebruikersvoorkeur<br /><br />**Standaardwaarde:** 1|
|**Connectivity/AllowUSBConnection**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**System/AllowUserToResetPhone**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Connectivity/AllowCellularDataRoaming**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Connectivity/AllowVPNOverCellular**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: VPN is niet toegestaan via mobiele verbindingen<br /><br />**1** : VPN mag alle verbinding gebruiken, inclusief mobiele verbindingen.<br /><br />**Standaardwaarde:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Connectivity/AllowVPNRoamingOverCellular**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Connectivity/AllowBluetooth**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: de gebruiker niet toestaan Bluetooth in te schakelen.<br /><br />**1**: gereserveerd. De gebruiker kan Bluetooth inschakelen en configureren (niet ondersteund in Windows Phone 8.1 voor MDM, EAS-, Windows 10 Desktop en Windows 10 Mobile)<br /><br />**2**: toegestaan. De gebruiker kan Bluetooth inschakelen en configureren.<br /><br />**Standaardwaarde:** 2|
|**Experience/AllowScreenCapture**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Experience/AllowTaskSwitcher**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Experience/AllowVoiceRecording**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Experience/AllowSyncMySettings**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : roaming niet toestaan<br /><br />**1** : roaming toestaan<br /><br />**Standaardwaarde:** 1|
|**Experience/AllowManualMDMUnenrollment**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Accounts/AllowMicrosoftAccountConnection**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Security/AllowManualRootCertificateInstallation**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Security/AllowAddProvisioningPackages**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Search/DisableBackoff**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 0|
|**Search/PreventRemoteQueries**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 1|
|**SearchZoeken/AllowUsingDiacritics**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 0|
|**Search/AlwaysUseAutoLangDetection**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 0|
|**Search/DisableRemovableDriveIndexing**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 0|
|**Search/PreventIndexingLowDiskSpaceMB**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 1|
|**Search/AllowIndexingEncryptedStoresOrItems**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 0|
|**Security/AllowRemoveProvisioningPackage**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Security/RequireProvisioningPackageSignature**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**<br /><br />**1**<br /><br />**Standaardwaarde:** 0|
|**AboveLock/AllowActionCenterNotifications**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**TextInput/AllowIMENetworkAccess**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toestaan<br /><br />De functie Uitgebreid woordenboek openen is uitgeschakeld.<br /><br />Een gebruiker kan niet:<br /><br />Een nieuwe functie Uitgebreid woordenboek openen toevoegen<br /><br />Een nieuw configuratiebestand voor de integratie van zoekopdrachten toevoegen<br /><br />De functie Cloudkandidaat gebruiken<br /><br />Een door de gebruiker geregistreerd woord verzenden<br /><br />Aanvullend:<br /><br />Een functie Uitgebreid woordenboek openen die is toegevoegd voordat deze beleidsinstelling is ingeschakeld, wordt niet gebruikt voor conversie.<br /><br />Een configuratiebestand voor de integratie van zoekopdrachten dat is geïnstalleerd voordat deze beleidsinstelling werd ingeschakeld, wordt niet gebruikt.<br /><br />**1**: toestaan<br /><br />Een functie Uitgebreid woordenboek openen kan standaard worden toegevoegd en gebruikt. De functie voor integratie van zoekbestanden kan ook standaard worden gebruikt.<br /><br />De gebruiker kan:<br /><br />De functie Cloudkandidaat gebruiken<br /><br />Een door de gebruiker geregistreerd woord verzenden<br /><br />**Standaardwaarde:**|
|**TextInput/AllowKoreanExtendedHanja**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowKoreanExtendedHanja<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**TextInput/AllowIMELogging**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: de functie Logboekregistratie voor een mislukte conversie is uitgeschakeld. Gegevens die automatisch zijn afgestemd en invoer van geschiedenisgegevens worden niet in een bestand opgeslagen.<br /><br />**1**: de functie Logboekregistratie voor een mislukte conversie is ingeschakeld. Gegevens die automatisch zijn afgestemd en invoer van geschiedenisgegevens worden in een bestand opgeslagen.<br /><br />**Standaardwaarde:** 1|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**TextInput/AllowJapaneseIVSCharacters**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**TextInput/AllowJapaneseUserDictionary**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: alle tekens worden gefilterd, behalve JIS-tekens<br /><br />**1**: er worden geen tekens gefilterd<br /><br />**Standaardwaarde:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: alle tekens worden gefilterd, behalve JIS0208-tekens<br /><br />**1**: er worden geen tekens gefilterd.<br /><br />**Standaardwaarde:** 1|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: alle tekens worden gefilterd, behalve JIS0208-tekens en EUDC-tekens<br /><br />**1**: er worden geen tekens gefilterd.<br /><br />**Standaardwaarde:** 1|
|**TextInput/AllowInputPanel**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Bluetooth/AllowDiscoverableMode**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Bluetooth/AllowAdvertising**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowDataSense**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowVPN**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowWorkplace**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowDateTime**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowDateTime**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowRegion**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowSignInOptions**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowYourAccount**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowPowerSleep**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Settings/AllowAutoPlay**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Experience/AllowCortana**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Search/SafeSearchPermissions**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : strict, hoogste filtering tegen inhoud voor volwassenen<br /><br />**1** : gemiddeld, gemiddelde filtering op inhoud voor volwassenen (geldige zoekresultaten wordt niet gefilterd)<br /><br />**Standaardwaarde:** 1|
|**Experience/AllowCopyPaste**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**Startgrootte forceren**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: wijziging van grootte door gebruiker toestaan<br /><br />**1**: niet-volledig scherm afdwingen<br /><br />**2**: volledig scherm afdwingen<br /><br />**Standaardwaarde:** 0|
|**Update/RequireDeferUpgrade**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: upgrade niet uitstellen (in huidige vertakking blijven, CB)<br /><br />**1**: toestaan dat updates en upgrades worden uitgesteld (apparaat volgt huidige vertakking voor bedrijven, CBB, regels)<br /><br />**Standaardwaarde: 0**<br /><br />Zie voor meer informatie:<br /><br />[Windows 10Windows 10 servicing options for updates and upgrades (Engelstalig)](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan for Windows 10 deployment (Engelstalig)](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpdatePeriod**|Beide|**Beschrijving:** beleid om software-updates maximaal vier weken uit te stellen<br /><br />**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:** 0: updates onmiddellijk toepassen; 1-4: aantal weken dat software-updates worden uitgesteld.<br /><br />**Standaardwaarde: 0**<br /><br /><br />Zie voor meer informatie:<br /><br />[Windows 10Windows 10 servicing options for updates and upgrades (Engelstalig)](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan for Windows 10 deployment (Engelstalig)](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/DeferUpgradePeriod**|Beide|**Beschrijving:** beleid om upgrades van functies tot maximaal 8 maanden uit te stellen<br /><br />**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:** 0: updates onmiddellijk toepassen; 1-8: aantal maanden dat upgrades van functies worden uitgesteld.<br /><br />**Standaardwaarde: 0**<br /><br />Zie voor meer informatie:<br /><br />[Windows 10Windows 10 servicing options for updates and upgrades (Engelstalig)](https://technet.microsoft.com/library/mt598226(v=vs.85).aspx)<br /><br />[Plan for Windows 10 deployment (Engelstalig)](https://technet.microsoft.com/library/mt574241(v=vs.85).aspx)|
|**Update/PauseDeferrals**|Beide|**Beschrijving:** hiermee kunt u instellen dat een CBB-machine vijf weken geen updates en upgrades ontvangt. Gebruik deze optie als er een probleem met een update is.<br /><br />**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: updates onmiddellijk toepassen (standaardinstelling)<br /><br />**1**: updates en upgrades tijdelijk onderbreken (vervalt na 5 weken)<br /><br />**Standaardwaarde: 0**|

### Windows Defender

|Naam van beleid|Ondersteunt|Details|
|---------------|------------|-----------|
|**AllowRealtimeMonitoring**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**AllowRealtimeMonitoring**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**AllowIntrusionPreventionSystem**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**AllowIOAVProtection**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**AllowScriptScanning**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**AllowOnAccessProtection**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**RealTimeScanDirection**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: alle bestanden controleren (in twee richtingen)<br /><br />**1** : binnenkomende bestanden controleren<br /><br />**2** : uitgaande bestanden controleren<br /><br />**Standaardwaarde:** 0|
|**DaysToRetainCleanedMalware**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0** - **90**: geeft aan hoelang malware behouden blijft<br /><br />**Standaardwaarde:** 0: blijft altijd in de map Quarantaine en wordt niet automatisch verwijderd|
|**AllowUserUIAccess**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**ScanParameter**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**1** : snelle scan<br /><br />**2**: volledige scan<br /><br />**Standaardwaarde:** 1|
|**ScheduleScanDay**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: elke dag<br /><br />**1**: maandag<br /><br />**2**: dinsdag<br /><br />**3**: woensdag<br /><br />**4**: donderdag<br /><br />**5**: vrijdag<br /><br />**6**: zaterdag<br /><br />**7**: zondag<br /><br />**8** : geen geplande scan<br /><br />**Standaardwaarde:** 0|
|**ScheduleScanTime**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: 00:00 uur<br /><br />**60**: 1:00 uur<br /><br />**120**: 2:00 uur<br /><br />**180**: 3:00 uur<br /><br />**240**: 4:00 uur<br /><br />**300**: 5:00 uur<br /><br />**360**: 6:00 uur<br /><br />**420**: 7:00 uur<br /><br />**480**: 8:00 uur<br /><br />**540**: 9:00 uur<br /><br />**600**: 10:00 uur<br /><br />**660**: 11:00 uur<br /><br />**720**: 12:00 uur<br /><br />**780**: 13:00 uur<br /><br />**840**: 14:00 uur<br /><br />**900**: 15:00 uur<br /><br />**960**: 16:00 uur<br /><br />**1020**: 17:00 uur<br /><br />**1080**: 18:00 uur<br /><br />**1140**: 19:00 uur<br /><br />**1200**: 20:00 uur<br /><br />**1260**: 21:00 uur<br /><br />**1320**: 22:00 uur<br /><br />**1381**: onderhoudsvenster<br /><br />**Standaardwaarde:** 120|
|**ScheduleQuickScanTime**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: 00:00 uur<br /><br />**60**: 1:00 uur<br /><br />**120**: 2:00 uur<br /><br />**180**: 3:00 uur<br /><br />**240**: 4:00 uur<br /><br />**300**: 5:00 uur<br /><br />**360**: 6:00 uur<br /><br />**420**: 7:00 uur<br /><br />**480**: 8:00 uur<br /><br />**540**: 9:00 uur<br /><br />**600**: 10:00 uur<br /><br />**660**: 11:00 uur<br /><br />**720**: 12:00 uur<br /><br />**780**: 13:00 uur<br /><br />**840**: 14:00 uur<br /><br />**900**: 15:00 uur<br /><br />**960**: 16:00 uur<br /><br />**1020**: 17:00 uur<br /><br />**1080**: 18:00 uur<br /><br />**1140**: 19:00 uur<br /><br />**1200**: 20:00 uur<br /><br />**1260**: 21:00 uur<br /><br />**1320**: 22:00 uur<br /><br />**1380**: 23:00 uur<br /><br />**Standaardwaarde:** 120|
|**AVGCPULoadFactor**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0** - **100**<br /><br />**Standaardwaarde:** 50|
|**AllowArchiveScanning**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: niet toegestaan<br /><br />**1**: toegestaan<br /><br />**Standaardwaarde:** 1|
|**AllowArchiveScanning**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**: niet toegestaan<br /><br />**1**: toegestaan<br /><br />**Standaardwaarde:** 0|
|**AllowFullScanRemovableDriveScanning**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 0|
|**AllowFullScanOnMappedNetworkDrives**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**AllowScanningNetworkFiles**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1: wordt ook uitgevoerd wanneer RTP is ingesteld op toegestaan|
|**SignatureUpdateInterval**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : tijdens een interval niet op handtekeningen controleren<br /><br />**1**: elk uur op handtekeningen controleren<br /><br />**2** : elke 2 uur op handtekeningen controleren, enz.<br /><br />**24** : elke dag op handtekeningen controleren<br /><br />**Standaardwaarde:** 8: elke 8 uur op handtekeningen controleren|
|**AllowCloudProtection**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : niet toegestaan<br /><br />**1** : toegestaan<br /><br />**Standaardwaarde:** 1|
|**SubmitSamplesConsent**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0** : altijd vragen<br /><br />**1** : veilige voorbeelden automatisch verzenden<br /><br />**2** : nooit verzenden<br /><br />**3** : alle voorbeelden automatisch verzenden<br /><br />**Standaardwaarde:** 0|
|**ExcludedExtensions**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden:**<br /><br />*&lt;door puntkomma's gescheiden lijst met extensies&gt;* bijv. **obj;lib**<br /><br />**Standaardwaarde:** er worden geen extensies uitgesloten|
|**ExcludedPaths**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden:**<br /><br />*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br /><br />Bijvoorbeeld: **c:\test;c:\test1.exe**<br /><br />**Standaardwaarde:** er worden geen paden uitgesloten|
|**ExcludedProcesses**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden:**<br /><br />*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br /><br />Bijvoorbeeld: **c:\test.exe;c:\test1.exe**<br /><br />**Standaardwaarde:** er worden geen processen uitgesloten|

### Edge-browser

|Naam van beleid|Ondersteunt|Details|
|---------------|------------|-----------|
|**Browser toestaan**|Mobiel|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: bladeren uitgeschakeld; **1**: bladeren ingeschakeld.<br /><br />**Standaardwaarde:** 1|
|**AllowSearchSuggestionsinAddressBar**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: geen zoeksuggesties weergeven; **1**: zoeksuggesties weergeven.<br /><br />**Standaardwaarde:** 1|
|**SendIntranetTraffictoInternetExplorer**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: uitgeschakeld (intranetsites openen in browser Edge); **1**: ingeschakeld (intranetsites openen in Internet Explorer).<br /><br />**Standaardwaarde:** 0|
|**Do Not Track toestaan**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: uitgeschakeld (DNT niet verzonden); **1**: ingeschakeld (DNT verzenden)<br /><br />**Standaardwaarde:** 0|
|**SmartScreen configureren**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: niet toestaan; **1**: toestaan<br /><br />**Standaardwaarde:** 1|
|**Pop-ups toestaan**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: pop-ups blokkeren; **1**: pop-ups toestaan<br /><br />**Standaardwaarde:** 0|
|**Cookies toestaan**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: niet blokkeren. Cookies van alle websites toestaan; **1**: alleen cookies van derden blokkeren; **2**: alle cookies blokkeren<br /><br />**Standaardwaarde:** 0|
|**Wachtwoord opslaan toestaan**|Beide|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: Wachtwoordbeheer uitgeschakeld; <br />                        **1**: Wachtwoordbeheer ingeschakeld<br /><br />**Standaardwaarde:** 1|
|**Automatisch invullen toestaan**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0**: uitgeschakeld; **1**: ingeschakeld<br /><br />**Standaardwaarde:** 0|
|**Sitelijst voor ondernemingen configureren**|Desktop|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden: 0**: niet geconfigureerd; **1**: gebruik de lijst met websites van Bedrijfsmodus indien geconfigureerd; **2**: geef de locatie van de lijst met websites van Bedrijfsmodus op<br /><br />**Standaardwaarde:** 1|

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO1-->


