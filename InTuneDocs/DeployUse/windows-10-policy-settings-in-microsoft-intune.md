---
title: Windows 10-beleidsinstellingen | Microsoft Intune
description: Gebruik de beleidsinstellingen die in dit onderwerp worden genoemd als u ingebouwde en aangepaste instellingen wilt configureren voor geregistreerde Windows 10 Desktop- en Windows 10 Mobile-apparaten.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 01356d08257cf381d1a981f749702800c173de33
ms.openlocfilehash: 08336c56f4e099c8cd0a0152364824455cae0f03


---

# Windows 10-beleidsinstellingen in Microsoft Intune

Gebruik de beleidsinstellingen die in dit onderwerp worden genoemd als u ingebouwde en aangepaste instellingen wilt configureren voor geregistreerde Windows 10 Desktop- en Windows 10 Mobile-apparaten.

> [!IMPORTANT]
> U kunt Windows 10-pc's op twee manieren beheren; door ze in te schrijven of de pc-clientsoftware van Intune te installeren. Elke methode biedt verschillende mogelijkheden (zie [Kiezen hoe u apparaten beheert](/intune/get-started/choose-how-to-manage-devices) voor meer informatie.
> Wanneer u uw Windows-10-computers met de Intune-pc-clientsoftware beheert, kunt u niet de beleidsregels en instellingen gebruiken die in dit onderwerp worden genoemd. Als u deze instellingen wilt toepassen, moeten uw Windows 10-apparaten bij Intune worden ingeschreven.

## Algemene instellingen voor configuratiebeleid

Gebruik de **algemene configuratiebeleidsregels** van Microsoft Intune voor Windows 10 om algemene instellingen te configureren voor geregistreerde Windows 10 Desktop- en Windows 10 Mobile-apparaten. 


### Wachtwoord

|Naam van de instelling|Details|
|----------------|----------------------|
|**Een wachtwoord vereisen om apparaten te ontgrendelden**|Hiermee vereist u een wachtwoord op ondersteunde apparaten.|
|**Vereist wachtwoordtype**|Hiermee geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek|
|**Vereist wachtwoordtype** - **Minimum aantal tekensets**|Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets moeten worden opgenomen in het wachtwoord.|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimale aantal tekens aan dat het wachtwoord voor het apparaat moet hebben.<br>(alleen Windows 10 Mobile)|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Wist de gegevens op het apparaat als dit aantal aanmeldingspogingen mislukt.|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u de hoeveelheid tijd aan die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.|
|**Verlopen van wachtwoorden (dagen)**|Met deze instelling bepaalt u de periode waarna het wachtwoord van een apparaat moet worden gewijzigd.|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u aan of u wilt voorkomen dat de eindgebruiker eerder gebruikte wachtwoorden mag hergebruiken.|
|**Wachtwoordgeschiedenis onthouden** - **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|
|**Afbeeldingswachtwoord en PIN toestaan**|Hiermee kunt u eenvoudige bewegingen op een afbeelding of een eenvoudige pincode gebruiken voor aanmelden.<br>(alleen Windows 10 Desktop)|
|**Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**|Indien ingeschakeld, moet de gebruiker een wachtwoord opgeven om het apparaat vanuit een niet-actieve status te ontgrendelen.<br>(alleen Windows 10 Mobile)|

### Versleuteling

|Naam van de instelling|Details|
|----------------|----------------------|
|**Versleuteling vereisen voor mobiel apparaat**|Hiermee schakelt u versleuteling op doelapparaten in.<br>(alleen Windows 10 Mobile)|

### Systeem

|Naam van de instelling|Details|
|----------------|----------------------|
|**Schermafbeelding toestaan**|Hiermee kan de gebruiker het apparaatscherm als afbeelding vastleggen.<br>(alleen Windows 10 Mobile)|
|**Handmatige uitschrijving toestaan**|Hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen.|
|**Handmatige installatie van basiscertificaat toestaan**|Hiermee geeft u op of de gebruiker basiscertificaten handmatig kan installeren.<br>(alleen Windows 10 Mobile)|
|**Toestaan dat diagnostische en gebruiksgegevens worden verzonden naar Microsoft**|Hiermee bepaalt u de hoeveelheid diagnostische en gebruiksgegevens die vanaf apparaten naar Microsoft wordt verzonden.<br><br>**Geen**: er worden geen gegevens naar Microsoft verzonden<br>**Basis**: het apparaat verzendt alleen een beperkte hoeveelheid informatie naar Microsoft<br>**Uitgebreid**: hiermee worden uitgebreide diagnostische gegevens naar Microsoft verzonden<br>**Volledig (aanbevolen)**: hiermee worden dezelfde gegevens verzonden als bij **Uitgebreid**, aangevuld met gegevens over de apparaatstatus|


### Account en synchronisatie

|Naam van de instelling|Details|
|----------------|----------------------|---------------------|
|**Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen.|
|**Handmatig toevoegen van een ander account dan een Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker aan het apparaat e-mailaccounts kan toevoegen die niet aan een Microsoft-account zijn gekoppeld.|
|**Synchronisatie van instellingen toestaan voor Microsoft-accounts**|Hiermee staat u synchronisatie tussen apparaten toe van apparaat- en app-instellingen die aan een Microsoft-account zijn gekoppeld.|

### E-mailinstellingen

|Naam van de instelling|Details|
|----------------|----------------------|---------------------|
|**Het Microsoft-account optioneel maken in de Windows Mail-toepassing**|Configureer dit als u de vereiste voor een Microsoft-account in Windows Mail wilt verwijderen.<br>Alleen Windows 10 Desktop|



### Microsoft Edge

|Naam van de instelling|Details|
|----------------|----------------------|
|**Webbrowser toestaan**|Hiermee staat u het gebruik van de webbrowser Edge op het apparaat toe.<br>(alleen Windows 10 Mobile)|
|**Zoeksuggesties in de adresbalk toestaan**|Hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt.|
|**Verzenden van intranetverkeer naar Internet Explorer toestaan**|Hiermee staat u toe dat gebruikers intranetsites in Internet Explorer kunnen openen.<br>(alleen Windows 10 Desktop)|
|**Do Not Track toestaan**|Hiermee configureert u de browser Edge zodanig dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken.|
|**SmartScreen inschakelen**|Hiermee schakelt u de instelling van de SmartScreen-browser op apparaten in.|
|**Active Scripting toestaan**|Hiermee staat u toe dat er in de browser Edge scripts, zoals JavaScript, kunnen worden uitgevoerd.|
|**Pop-ups toestaan**|Hiermee schakelt u de pop-upblokkering voor browsers in of uit.<br>(alleen Windows 10 Desktop)|
|**Cookies toestaan**|Hiermee staat u cookies toe of niet.|
|**Automatisch invullen toestaan**|Hiermee staat u gebruikers toe instellingen voor automatisch aanvullen in de browser te wijzigen.<br>(alleen Windows 10 Desktop)|
|**Wachtwoordbeheer toestaan**|Hiermee schakelt u de functie Wachtwoordbeheer van Edge in of uit.|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Geeft de plaats aan van de lijst met websites die in Bedrijfsmodus worden geopend. Gebruikers kunnen deze lijst niet bewerken.<br>(alleen Windows 10 Desktop)|

### Apps

|Naam van de instelling|Details|
|----------------|----------------------|---------------------|
|**Toepassingsarchief toestaan**|Hiermee geeft u de gebruiker toegang tot de app store op het apparaat.<br>(alleen Windows 10 Mobile)|



### Mobiel

|Naam van de instelling|Details|
|----------------|----------------------|---------------------|
|**Gegevensroaming toestaan**|Roaming tussen netwerken toestaan tijdens het ophalen van gegevens.|
|**VPN via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen indien verbonden met het mobiele netwerk.|
|**VPN-roaming via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen tijdens het roamen op een mobiel netwerk.|

### Hardware

|Naam van de instelling|Details|
|----------------|----------------------|
|**Camera toestaan**|Hiermee geeft u op of de camera van het apparaat kan worden gebruikt.|
|**Verwisselbare opslag toestaan**|Hiermee geeft u op of er op het apparaat externe opslagapparaten, zoals een SD-kaart, kunnen worden gebruikt.|
|**Wi-Fi toestaan**|Hiermee kunt het gebruik van de Wi-Fi-functionaliteit van het apparaat toestaan.<br>(alleen Windows 10 Mobile)|
|**Internetverbinding delen toestaan**|Hiermee kunt u het gebruik van een gedeelde internetverbinding op het apparaat toestaan.|
|**Handmatige Wi-Fi-configuratie toestaan**|Hiermee bepaalt u of de gebruiker zijn eigen Wi-Fi-verbindingen kan instellen, of dat de gebruiker alleen verbindingen kan gebruiken die door een Wi-Fi-profiel zijn geconfigureerd.<br>(alleen Windows 10 Mobile)|
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Hiermee kunt u het apparaat automatisch verbinding laten maken met gratis Wi-Fi-hotspots en automatisch de voorwaarden voor de verbinding laten accepteren.|
|**Geolocatie toestaan**|Geeft aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt.|
|**NFC toestaan**|Hiermee staat u gebruik van de NFC-mogelijkheden op het apparaat toe.|
|**Bluetooth toestaan**|Hiermee schakelt u het gebruik van Bluetooth-mogelijkheden op het apparaat in.|
|**Modus voor Bluetooth-detectie toestaan**|Hiermee kan dit apparaat worden gedetecteerd door andere Bluetooth-apparaten.|
|**Bluetooth-promotie toestaan**|Hiermee staat u toe dat apparaten reclame via Bluetooth kunnen ontvangen.|
|**Modus voor Bluetooth-verbindbaarheid toestaan**|**Belangrijk:** deze instelling wordt niet meer ondersteund voor Windows 10 en wordt in de toekomst verwijderd.|
|**Opnieuw instellen van telefoon toestaan**|Hiermee bepaalt u of de gebruiker de fabrieksinstellingen van het apparaat kan herstellen.|
|**USB-verbinding toestaan**|Hiermee bepaalt u of apparaten via een USB-verbinding toegang kunnen hebben tot externe opslagapparaten.|
|**Antidiefstalmodus toestaan**|Hiermee configureert u of de antidiefstalmodus van Windows is ingeschakeld.|

### Functies

|Naam van de instelling|Details|
|----------------|----------------------|---------------------|
|**Kopiëren en plakken toestaan**|Hiermee schakelt u het gebruik van kopiëren en plakken op het apparaat in of uit.<br>(alleen Windows 10 Mobile)|
|**Spraakopname toestaan**|Hiermee schakelt u de spraakopnamefuncties op het apparaat in of uit.<br>(alleen Windows 10 Mobile)|
|**Cortana toestaan**|Hiermee schakelt u de spraakassistent Cortana in of uit.|
|**Meldingen van onderhoudscentrum toestaan**|Hiermee schakelt u de meldingen van het Onderhoudscentrum op het vergrendelingsscherm in of uit.<br>(alleen Windows 10 Mobile)|

### Defender

Alle instellingen zijn alleen voor Windows 10 Desktop.

|Naam van de instelling|Details|
|-|-|
|**Real-timecontrole toestaan**|Hiermee schakelt u het real-time scannen op malware, spyware en andere ongewenste software in.|
|**Gedragscontrole toestaan**|Hiermee kunt u Defender laten controleren op de aanwezigheid van bepaalde bekende patronen van verdachte activiteiten op apparaten.|
|**Systeem voor netwerkinspectie inschakelen**|Het Netwerkinspectiesysteem (NIS) kan u op basis van de handtekeningen van bekende beveiligingsproblemen van het Microsoft Endpoint Protection Center helpen met het detecteren en blokkeren van schadelijk verkeer, zodat de apparaten in het netwerk beveiligd zijn tegen exploits.|
|**Alle downloads scannen**|Hiermee bepaalt u of Windows Defender alle bestanden moet scannen die van internet worden gedownload.|
|**Scannen van scripts toestaan**|Hiermee laat u Defender scripts scannen die worden gebruikt in Internet Explorer.|
|**Activiteiten van bestanden en programma's bewaken**|Schakel deze instelling in om Defender toe te staan activiteiten van bestanden en programma's op apparaten te bewaken.|
|**Dagen om opgeloste problemen met malware bij te houden**|Hiermee kunt Defender gedurende het aantal dagen dat u opgeeft, opgeloste malware laten bijhouden, zodat u handmatig eerder aangevallen apparaten kunt controleren. Als u het aantal dagen instelt op **0**, blijft malware in de map Quarantaine staan en wordt malware niet automatisch verwijderd. |
|**Toegang tot gebruikersinterface van client toestaan**|Hiermee bepaalt u of de gebruikersinterface van Windows Defender voor eindgebruikers wordt verborgen.<br>Als deze instelling wordt gewijzigd, gaat de wijziging in wanneer de pc van de eindgebruiker de volgende keer opnieuw wordt opgestart.|
|**Een dagelijkse snelle scan plannen**|Hiermee kunt u een snelle scan plannen die dagelijks wordt uitgevoerd op het moment dat u selecteert.|
|**Een systeemscan plannen**|Hiermee kunt u een volledige of snelle systeemscan plannen die regelmatig wordt uitgevoerd op de dag en tijd die u selecteert.|
|**CPU-verbruik tijdens een scan beperken**|Hiermee kunt u de hoeveelheid CPU beperken die scans mogen gebruiken (van **1** tot **100**).|
|**Archiefbestanden scannen**|Hiermee kunt u toestaan dat Defender gearchiveerde bestanden scant, zoals zip- of cab-bestanden.|
|**E-mailberichten scannen**|Hiermee kunt u toestaan dat Defender e-mailberichten scant wanneer deze op het apparaat binnenkomen.|
|**Verwisselbare stations scannen**|Hiermee kunt u Defender verwisselbare stations, zoals USB-sticks, laten scannen.|
|**Toegewezen netwerkstations scannen**|Hiermee kunt u Defender bestanden op een gekoppeld netwerkstation laten scannen.<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|
|**Bestanden scannen die worden geopend vanuit gedeelde netwerkmappen**|Hiermee kunt u Defender bestanden op gedeelde stations laten scannen (bijvoorbeeld gedeelde stations die via een UNC-pad toegankelijk zijn).<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|
|**Update-interval voor handtekeningen**|Hiermee geeft u het interval op waarmee Defender op nieuwe handtekeningbestanden moet controleren.|
|**Cloudbeveiliging toestaan**|Hiermee kunt u toestaan of blokkeren dat de Microsoft Active Protection-service informatie ontvangt over malware-activiteit op apparaten die u beheert. Deze informatie wordt gebruikt om de service in de toekomst te verbeteren.|
|**Gebruikers vragen voorbeelden te verzenden**|Hiermee bepaalt u of bestanden waarvoor verdere analyse door Microsoft nodig is om te bepalen of deze schadelijk zijn, automatisch naar Microsoft moeten worden verzonden.|
|**Detectie van mogelijk ongewenste toepassingen**|U kunt deze instelling gebruiken als u geregistreerde Windows-desktopapparaten wilt beveiligen tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd.|
|**Uit te sluiten bestanden en mappen wanneer een scan wordt uitgevoerd of bij het gebruik van realtime-beveiliging**|Voeg aan de uitsluitingslijst een of meer bestanden en mappen toe, zoals **C:\pad** of **%ProgramFiles%\pad\bestandsnaam.exe**. Deze bestanden en mappen worden niet opgenomen in real-timescans of geplande scans.|
|**Uit te sluiten bestandsextensies wanneer een scan wordt uitgevoerd of bij het gebruik van realtime-beveiliging**|Voeg aan de uitsluitingslijst een of meer bestandsextensies toe, zoals **jpg** of **txt**. Alle bestanden met deze extensies worden niet opgenomen in real-timescans of geplande scans.|
|**Uit te sluiten processen wanneer een scan wordt uitgevoerd of bij het gebruik van realtime-beveiliging**|Voeg aan de uitsluitingslijst een of meer processen toe van het type **.exe**, **.com** of **.scr**. Deze processen worden niet opgenomen in real-timescans of geplande scans.| 


### Instellingen voor updates

|Naam van de instelling|Details|
|----------------|---------------|
|**Automatische updates toestaan**|Schakel deze instelling in om automatische updates toe te staan. Configureer vervolgens een van de volgende instellingen om het gedrag voor updates te bepalen:<br /><br />**Melding van download**<br /><br />**Automatisch installeren op onderhoudstijdstip**<br /><br />**Automatisch installeren en opstarten op onderhoudstijdstip**<br /><br />**Automatisch installeren en opnieuw opstarten op het geplande tijdstip** **Opmerking:** wanneer deze optie is geselecteerd, kunt u ook de volgende instellingen configureren: **Melding aan eindgebruiker onderdrukken** en **De installatiedag voor geplande updates definiëren**.<br>(alleen Windows 10 Desktop)|

## Aangepaste beleidsinstellingen
Gebruik het **Aangepaste configuratiebeleid** van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op Windows 10- en Windows 10 Mobile-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Windows 10-instellingen implementeren die niet met het algemene configuratiebeleid van Intune kunnen worden geconfigureerd.



### Algemene instellingen voor het aangepaste beleid

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam**|Voer een unieke naam in voor het beleid, zodat u het beleid in de Intune-console kunt herkennen.|
    |**Beschrijving**|Geef een beschrijving op die een overzicht geeft van het beleid en overige relevante informatie die u helpt om het beleid terug te vinden.|

### OMA-URI-instellingen voor het aangepaste beleid

|Naam van de instelling|Details|
    |--------|--------------------|
    |**Naam van de instelling**|Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
    |**Beschrijving van instelling**|Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    |**Gegevenstype**|Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. U kunt kiezen uit:<br /><br />-   **Tekenreeks**<br />-   **Tekenreeks (XML)**<br />-   **Datum en tijd**<br />-   **Geheel getal**<br />-   **Drijvende komma**<br />-   **Boolean-waarde**|
    |**OMA-URI (hoofdlettergevoelig)**|Geef aan voor welke OMA-URI u een instelling wilt opgeven.|
    |**Waarde**|Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|


## Aangepaste URI-instellingen voor Windows-10-apparaten
In dit onderwerp vindt u de instellingen die u in **Aangepast beleid voor Windows 10** kunt configureren voor Windows 10- en Windows 10 Mobile-apparaten.

Alle apparaten moeten worden geregistreerd bij Intune als u het aangepaste Windows URI-beleid wilt gebruiken.

### URI-instellingen voor het beleid

|Naam van beleid|Details|
|---------------|------------|-----------|
|**​Automatisch bijwerken toestaan**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/AllowAutoUpdate<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** - **5** (standaardinstelling: **1**)|
|**Planning installatiedag**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallDay<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: elke dag (standaard)<br>**1**: zondag<br>**2**: maandag<br>**3**: dinsdag<br>**4**: woensdag<br>**5**: donderdag<br>**6**: vrijdag<br>**7**: zaterdag|
|**Planning installatietijd**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/ScheduledInstallTime<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** – **23** uur (**0** is middernacht) (standaard: **3**)|
|**DeviceLock/AllowIdleReturnWithoutPassword**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/DeviceLock/AllowIdleReturnWithoutPassword<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: de gebruiker kan de timer van de respijtperiode voor het wachtwoord niet instellen en de waarde is ingesteld als elke keer<br>**1**: de gebruiker kan de timer voor de respijtperiode van het wachtwoord instellen (standaard)|
|**WiFi/AllowWiFi**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowWiFi<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: **gebruik van Wi-Fi-verbinding** niet toestaan.<br>**1**: **gebruik van Wi-Fi-verbinding toestaan** (standaard).|
|**WiFi/AllowInternetSharing**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowInternetSharing<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : internet delen niet toestaan.<br>**1**: Gedeeld internet toestaan (standaard)|
|**WiFi/AllowAutoConnectToWiFiSenseHotspots**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowAutoConnectToWiFiSenseHotspots<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**WiFi/AllowManualWiFiConfiguration**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/WiFi/AllowManualWiFiConfiguration<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: een Wi-Fi-verbinding buiten de ingerichte MDM is niet toegestaan.<br>**1**: het toevoegen van een nieuwe netwerk-SSID buiten de al aanwezige MDM is toegestaan (standaard).|
|**System/AllowLocation**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowLocation<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**System/AllowTelemetry**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowTelemetry<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan (instelling alleen voor Enterprise)<br>**1** : beperkt<br>**2**: volledig (standaard)<br>**3**: volledige en diagnostische gegevens|
|**System/AllowExperimentation**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowExperimentation<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: alleen instellingen (standaard)<br>**2**: instellingen en experimenteren|
|**Security/AntiTheftMode**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AntiTheftMode<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: Antidiefstalmodus niet toestaan<br>**1**: gebruikersvoorkeur (standaard)|
|**Connectivity/AllowUSBConnection**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowUSBConnection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**System/AllowUserToResetPhone**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/System/AllowUserToResetPhone<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Connectivity/AllowCellularDataRoaming**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowCellularDataRoaming<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Connectivity/AllowVPNOverCellular**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNOverCellular<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: VPN is niet toegestaan via mobiele verbindingen<br>**1**: VPN mag alle verbinding gebruiken, inclusief mobiele verbindingen (standaard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Connectivity/AllowVPNRoamingOverCellular**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowVPNRoamingOverCellular<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Connectivity/AllowBluetooth**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Connectivity/AllowBluetooth<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: de gebruiker niet toestaan Bluetooth in te schakelen.<br>**1**: gereserveerd. De gebruiker kan Bluetooth inschakelen en configureren (niet ondersteund in Windows Phone 8.1 voor MDM, EAS-, Windows 10 Desktop en Windows 10 Mobile)<br>**2**: toegestaan. De gebruiker kan Bluetooth inschakelen en configureren (standaard)|
|**Experience/AllowScreenCapture**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowScreenCapture<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Experience/AllowTaskSwitcher**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowTaskSwitcher<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Experience/AllowVoiceRecording**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowVoiceRecording<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Experience/AllowSyncMySettings**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowSyncMySettings<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : roaming niet toestaan<br>**1**: roaming toestaan (standaard)|
|**Experience/AllowManualMDMUnenrollment**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowManualMDMUnenrollment<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Accounts/AllowMicrosoftAccountConnection**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowMicrosoftAccountConnection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Accounts/AllowAddingNonMicrosoftAccountsManually**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Accounts/AllowAddingNonMicrosoftAccountsManually<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Security/AllowManualRootCertificateInstallation**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AllowManualRootCertificateInstallation<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Security/AllowAddProvisioningPackages**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AllowAddProvisioningPackages<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Search/DisableBackoff**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/DisableBackoff<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** (standaardinstelling)<br>**1**|
|**Search/PreventRemoteQueries**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/PreventRemoteQueries<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**<br>**1** (standaardinstelling)|
|**SearchZoeken/AllowUsingDiacritics**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/AllowUsingDiacritics<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br> **0** (standaardinstelling)<br>**1**|
|**Search/AlwaysUseAutoLangDetection**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/AlwaysUseAutoLangDetection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** (standaardinstelling)<br>**1**|
|**Search/DisableRemovableDriveIndexing**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/DisableRemovableDriveIndexing<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** (standaardinstelling)<br>**1**|
|**Search/PreventIndexingLowDiskSpaceMB**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/PreventIndexingLowDiskSpaceMB<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**<br>**1** (standaardinstelling)|
|**Search/AllowIndexingEncryptedStoresOrItems**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/AllowIndexingEncryptedStoresOrItems<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** (standaardinstelling)<br>**1**|
|**Security/AllowRemoveProvisioningPackage**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/AllowRemoveProvisioningPackage<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Security/RequireProvisioningPackageSignature**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Security/RequireProvisioningPackageSignature<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** (standaardinstelling)<br>**1**|
|**AboveLock/AllowActionCenterNotifications**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/AboveLock/AllowActionCenterNotifications<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**TextInput/AllowIMENetworkAccess**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMENetworkAccess<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toestaan<br>De functie Uitgebreid woordenboek openen is uitgeschakeld.<br>Een gebruiker kan niet:<br>Een nieuwe functie Uitgebreid woordenboek openen toevoegen<br /><br />Een nieuw configuratiebestand voor de integratie van zoekopdrachten toevoegen<br>De functie Cloudkandidaat gebruiken<br>Een door de gebruiker geregistreerd woord verzenden<br>Aanvullend:<br>Een functie Uitgebreid woordenboek openen die is toegevoegd voordat deze beleidsinstelling is ingeschakeld, wordt niet gebruikt voor conversie.<br>Een configuratiebestand voor de integratie van zoekopdrachten dat is geïnstalleerd voordat deze beleidsinstelling werd ingeschakeld, wordt niet gebruikt.<br>**1**: toestaan<br>Een functie Uitgebreid woordenboek openen kan standaard worden toegevoegd en gebruikt. De functie voor integratie van zoekbestanden kan ook standaard worden gebruikt.<br>De gebruiker kan:<br>De functie Cloudkandidaat gebruiken<br>Een door de gebruiker geregistreerd woord verzenden.|
|**TextInput/AllowIMELogging**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowIMELogging<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: de functie Logboekregistratie voor een mislukte conversie is uitgeschakeld. Gegevens die automatisch zijn afgestemd en invoer van geschiedenisgegevens worden niet in een bestand opgeslagen.<br>**1**: de functie Logboekregistratie voor een mislukte conversie is ingeschakeld. Gegevens die automatisch zijn afgestemd en invoer van geschiedenisgegevens worden in een bestand opgeslagen (standaard)|
|**TextInput/AllowJapaneseNonPublishingStandardGlyph**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseNonPublishingStandardGlyph<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseIVSCharacters**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIVSCharacters<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseUserDictionary**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseUserDictionary<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**TextInput/AllowJapaneseIMESurrogatePairCharacters**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowJapaneseIMESurrogatePairCharacters<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**TextInput/ExcludeJapaneseIMEExceptShiftJIS**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptShiftJIS<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve Shift-JIS-tekens|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br /><br />**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve JIS0208-tekens|
|**TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/ExcludeJapaneseIMEExceptJIS0208andEUDC<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**er worden geen tekens gefilterd (standaardinstelling)<br>**1**: alle tekens worden gefilterd, behalve JIS0208-tekens en EUDC-tekens|
|**TextInput/AllowInputPanel**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/TextInput/AllowInputPanel<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Bluetooth/AllowDiscoverableMode**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowDiscoverableMode<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Bluetooth/AllowAdvertising**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Bluetooth/AllowAdvertising<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowDataSense**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDataSense<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowVPN**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowVPN<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowWorkplace**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowWorkplace<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowDateTime**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowDateTime<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowDateTime**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowLanguage<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowRegion**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowRegion<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowSignInOptions**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowSignInOptions<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowYourAccount**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowYourAccount<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowPowerSleep**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowPowerSleep<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Settings/AllowAutoPlay**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Settings/AllowAutoPlay<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Experience/AllowCortana**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCortana<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Search/SafeSearchPermissions**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Search/SafeSearchPermissions<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : strict, hoogste filtering tegen inhoud voor volwassenen<br>**1**: gemiddeld, gemiddelde filtering op inhoud voor volwassenen (geldige zoekresultaten worden standaard niet gefilterd)|
|**Experience/AllowCopyPaste**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Experience/AllowCopyPaste<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**Startgrootte forceren**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Start/ForceStartSize<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: wijziging van grootte door gebruiker toestaan (standaard)<br>**1**: niet-volledig scherm afdwingen<br>**2**: volledig scherm afdwingen|
|**Update/RequireDeferUpgrade**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/RequireDeferUpgrade<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: upgrade niet uitstellen (in huidige vertakking blijven, CB (standaard))<br>**1**: toestaan dat updates en upgrades worden uitgesteld (apparaat volgt huidige vertakking voor bedrijven, CBB, regels)<br /><br />Zie voor meer informatie:<br>[Windows 10Windows 10 servicing options for updates and upgrades (Engelstalig)](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan for Windows 10 deployment (Engelstalig)](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpdatePeriod**<br>(desktop en mobiel)|**Beschrijving:** beleid om software-updates maximaal vier weken uit te stellen<br /><br />**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpdatePeriod<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br> **0**: updates onmiddellijk toepassen (standaardinstelling)<br>**1**-**4**: aantal weken om software-updates uit te stellen.<br /><br />Zie voor meer informatie:<br>[Windows 10Windows 10 servicing options for updates and upgrades (Engelstalig)](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan for Windows 10 deployment (Engelstalig)](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/DeferUpgradePeriod**<br>(desktop en mobiel)|**Beschrijving:** beleid om upgrades van functies tot maximaal 8 maanden uit te stellen<br /><br />**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/DeferUpgradePeriod<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: updates onmiddellijk toepassen (standaardinstelling)<br>**1**-**8**: aantal maanden dat functie-upgrades moeten worden uitgesteld.<br /><br />Zie voor meer informatie:<br>[Windows 10Windows 10 servicing options for updates and upgrades (Engelstalig)](https://technet.microsoft.com/library/mt598226.aspx)<br>[Plan for Windows 10 deployment (Engelstalig)](https://technet.microsoft.com/library/mt574241.aspx)|
|**Update/PauseDeferrals**<br>(desktop en mobiel)|**Beschrijving:** hiermee kunt u instellen dat een CBB-machine vijf weken geen updates en upgrades ontvangt. Gebruik deze optie als er een probleem met een update is.<br /><br />**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Update/PauseDeferrals<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: updates onmiddellijk toepassen (standaardinstelling)<br>**1**: updates en upgrades tijdelijk onderbreken (vervalt na 5 weken)|

### URI-instellingen voor Windows Defender

|Naam van beleid|Details|
|---------------|-----------|
|**AllowRealtimeMonitoring**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowRealtimeMonitoring<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**AllowRealtimeMonitoring**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowBehaviorMonitoring<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**AllowIntrusionPreventionSystem**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIntrusionPreventionSystem<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**AllowIOAVProtection**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowIOAVProtection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**AllowScriptScanning**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScriptScanning<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**AllowOnAccessProtection**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowOnAccessProtection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**RealTimeScanDirection**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/RealTimeScanDirection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: alle bestanden controleren (in twee richtingen (standaard))<br>**1** : binnenkomende bestanden controleren<br>**1** : uitgaande bestanden controleren|
|**DaysToRetainCleanedMalware**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/DaysToRetainCleanedMalware<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** - **90**: geeft aan hoe lang malware behouden blijft<br>**Standaardwaarde:** **0**: blijft altijd in de map Quarantaine en wordt niet automatisch verwijderd|
|**AllowUserUIAccess**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowUserUIAccess<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**ScanParameter**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScanParameter<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**1**: snelle scan (standaard)<br>**2**: volledige scan|
|**ScheduleScanDay**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanDay<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: elke dag (standaard)<br>**1**: maandag<br>**2**: dinsdag<br>**3**: woensdag<br>**4**: donderdag<br>**5**: vrijdag<br>**6**: zaterdag<br>**7**: zondag<br>**8** : geen geplande scan|
|**ScheduleScanTime**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleScanTime<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: 00:00 uur<br>**60** – 1:00 uur<br>**120**: 2:00 uur (standaardinstelling)<br>**180** – 3:00 uur<br>**240** – 4:00 uur<br>**300** – 5:00 uur<br>**360** – 6:00 uur<br>**420** – 7:00 uur<br>**480** – 8:00 uur<br>**540** – 9:00 uur<br>**600** – 10:00 uur<br>**660** – 11:00 uur<br>**720** – 12:00 uur<br>**780** – 13:00 uur<br>**840** – 14:00 uur<br>**900** – 15:00 uur<br>**960** – 16:00 uur<br>**1020** – 17:00 uur<br>**1080** – 18:00 uur<br>**1140** – 19:00 uur<br>**1200** – 20:00 uur<br>**1260** – 21:00 uur<br>**1320** – 22:00 uur<br>**1381** : onderhoudsvenster|
|**ScheduleQuickScanTime**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ScheduleQuickScanTime<br>**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: 00:00 uur<br>**60** – 1:00 uur<br>**120**: 2:00 uur (standaardinstelling)<br>**180** – 3:00 uur<br>**240** – 4:00 uur<br>**300** – 5:00 uur<br>**360** – 6:00 uur<br>**420** – 7:00 uur<br>**480** – 8:00 uur<br>**540** – 9:00 uur<br>**600** – 10:00 uur<br>**660** – 11:00 uur<br>**720** – 12:00 uur<br>**780** – 13:00 uur<br>**840** – 14:00 uur<br>**900** – 15:00 uur<br>**960** – 16:00 uur<br>**1020** – 17:00 uur<br>**1080** – 18:00 uur<br>**1140** – 19:00 uur<br>**1200** – 20:00 uur<br>**1260** – 21:00 uur<br>**1320** – 22:00 uur<br>**1380** – 23:00 uur|
|**AVGCPULoadFactor**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AVGCPULoadFactor<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden: 0** - **100** (standaard: **50**)|
|**AllowArchiveScanning**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowArchiveScanning<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**AllowArchiveScanning**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowEmailScanning<br /><br />**Gegevenstype:** geheel getal<br>**Toegestane waarden:**<br>**0**: niet toegestaan (standaardinstelling)<br>**1** : toegestaan|
|**AllowFullScanRemovableDriveScanning**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanRemovableDriveScanning<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: niet toegestaan (standaardinstelling)<br>**1** : toegestaan|
|**AllowFullScanOnMappedNetworkDrives**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowFullScanOnMappedNetworkDrives<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**AllowScanningNetworkFiles**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowScanningNetworkFiles<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard). Wordt ook uitgevoerd wanneer RTP is ingesteld op toegestaan.|
|**SignatureUpdateInterval**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/SignatureUpdateInterval<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : tijdens een interval niet op handtekeningen controleren<br>**1**: elk uur op handtekeningen controleren<br>**2** : elke 2 uur op handtekeningen controleren, enz.<br>**24** : elke dag op handtekeningen controleren<br>**Standaardwaarde:** 8: elke 8 uur op handtekeningen controleren|
|**AllowCloudProtection**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/AllowCloudProtection<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0** : niet toegestaan<br>**1**: toegestaan (standaard)|
|**SubmitSamplesConsent**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/SubmitSamplesConsent<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: altijd vragen (standaard)<br>**1** : veilige voorbeelden automatisch verzenden<br>**2** : nooit verzenden<br>**3** : alle voorbeelden automatisch verzenden|
|**ExcludedExtensions**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedExtensions<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden:**<br>*&lt;door puntkomma's gescheiden lijst met extensies&gt;* Bijvoorbeeld **obj;lib**<br>**Standaard:** er worden geen extensies uitgesloten|
|**ExcludedPaths**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedPaths<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden:**<br /><br />*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br /><br />Bijvoorbeeld: **c:\test;c:\test1.exe**<br /><br />**Standaardwaarde:** er worden geen paden uitgesloten|
|**ExcludedProcesses**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Defender/ExcludedProcesses<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden:**<br>*&lt;door puntkomma's gescheiden lijst met paden&gt;*<br>Bijvoorbeeld: **c:\test.exe;c:\test1.exe**<br>**Standaardwaarde:** er worden geen processen uitgesloten|

### URI-instellingen voor de Edge-browser

|Naam van beleid|Details|
|---------------|------------|-----------|
|**Browser toestaan**<br>(alleen mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowBrowser<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: browsen uitgeschakeld<br>**1**: browsen ingeschakeld (standaard)|
|**AllowSearchSuggestionsinAddressBar**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSearchSuggestionsinAddressBar<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: geen zoeksuggesties weergeven<br>**1**: zoeksuggesties weergeven (standaard)|
|**SendIntranetTraffictoInternetExplorer**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/SendIntranetTraffictoInternetExplorer<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: uitgeschakeld (intranetsites worden standaard geopend in de Edge-browser)<br>**1**: ingeschakeld (intranetsites worden geopend in Internet Explorer)|
|**Do Not Track toestaan**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowDoNotTrack<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: uitgeschakeld (DNT niet verzonden - standaard)<br>**1**: ingeschakeld (DNT verzenden)|
|**SmartScreen configureren**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowSmartScreen<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: niet toestaan<br>**1**: toestaan (standaard)|
|**Pop-ups toestaan**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPopups<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: pop-ups blokkeren (standaard)<br>**1**: pop-ups toestaan|
|**Cookies toestaan**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowCookies<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: niet blokkeren Cookies van alle websites toestaan (standaard)<br>**1**: alleen cookies van derden blokkeren<br>**2**: alle cookies blokkeren|
|**Wachtwoord opslaan toestaan**<br>(desktop en mobiel)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowPasswordManager<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: wachtwoordbeheer is uitgeschakeld <br>**1**: wachtwoordbeheer is ingeschakeld (standaard)|
|**Automatisch invullen toestaan**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/AllowAutofill<br /><br />**Gegevenstype:** geheel getal<br /><br />**Toegestane waarden:**<br>**0**: uitgeschakeld (standaard)<br>**1**: ingeschakeld|
|**Sitelijst voor ondernemingen configureren**<br>(alleen desktop)|**Volledig URI-pad:** ./Vendor/MSFT/Policy/Config/Browser/EnterpriseModeSiteList<br /><br />**Gegevenstype:** tekenreeks<br /><br />**Toegestane waarden:<br>0** - niet geconfigureerd<br>**1**: sitelijst voor de ondernemingsmodus van IE gebruiken indien geconfigureerd (standaard)<br>**2**: locatie van de lijst van Enterprise-sites opgeven|

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


