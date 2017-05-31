---
title: Windows 10-beleidsinstellingen | Microsoft Docs
description: Gebruik de beleidsinstellingen die in dit onderwerp worden genoemd als u ingebouwde en aangepaste instellingen wilt configureren voor geregistreerde Windows 10 Desktop- en Windows 10 Mobile-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/03/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: dd81102eb768ab8ad5f9ee1d2f122f15a8e17b89
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="intune-policy-settings-for-windows-10-devices-in-microsoft-intune"></a>Beleidsinstellingen voor Windows 10-apparaten in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

De informatie in dit onderwerp kan u helpen de Intune-beleidsinstellingen te begrijpen die u kunt gebruiken voor het beheren van Windows 10-apparaten. Lees dit onderwerp, en lees daarnaast over de procedures in [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](/intune-classic/get-started/windows-pc-management-capabilities-in-microsoft-intune).

U kunt kiezen uit twee beleidstypen:

- **Aangepast beleid**: gebruik het **aangepaste beleid** van Microsoft Intune voor Windows 10 en Windows 10 Mobile om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om functies op apparaten te beheren. In Windows 10 zijn veel CSP-instellingen beschikbaar, bijvoorbeeld de [ beleids-CSP (Policy Configuration Service Provider)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
- **Algemeen configuratiebeleid**: gebruik dit beleidstype wanneer u instellingen wilt kiezen uit de ingebouwde lijst van Microsoft Intune.

## <a name="custom-policy-settings"></a>Aangepaste beleidsinstellingen

Geef de volgende instellingen op in een aangepast beleid.

### <a name="general-settings"></a>Algemene instellingen

Geef een naam en eventueel een beschrijving op voor dit beleid, zodat u het kunt herkennen in de Intune-console.

### <a name="oma-uri-settings"></a>OMA-URI-instellingen

Voer voor elke OMA-URI-instelling die u wilt toevoegen de volgende informatie in. Gebruik de [documentatie voor Windows 10-URI-instellingen](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#Windows-10-URI-settings) in dit onderwerp voor meer informatie over de instellingen die u kunt gebruiken:

- **Naam van de instelling**: voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.
- **Beschrijving van de instelling**: voer eventueel een beschrijving in voor de instelling.
- **Gegevenstype**: kies uit de volgende gegevenstypen:
    - **Tekenreeks**
    - **Tekenreeks (XML)**
    - **Datum en tijd**
    - **Geheel getal**
    - **Drijvende komma**
    - **Booleaanse waarde**
- **OMA-URI (hoofdlettergevoelig)**: geef aan voor welke OMA-URI u een instelling wilt opgeven.
- **Waarde**: geef de waarde op die moet worden gekoppeld aan de OMA-URI die u hebt opgegeven.

### <a name="example"></a>Voorbeeld
In de volgende schermopname is de instelling **Connectivity/AllowVPNOverCellular** ingeschakeld. Hiermee kan met een Windows-10-apparaat een VPN-verbinding worden gemaakt in een mobiel netwerk.

> ![Voorbeeld van een aangepast beleid met VPN-instellingen](./media/custom-policy-example.png)

### <a name="how-to-find-the-policies-you-can-configure"></a>De beleidsregels zoeken die u kunt configureren

Een complete lijst met configuratieserviceproviders (CSP's) die door Windows 10 worden ondersteund, vindt u in het artikel [Configuration service provider reference (Referentie voor Configuration Service Providers) ](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in de documentatiebibliotheek van Windows.

Niet alle instellingen zijn compatibele met alle versies van Windows 10. In de tabel in het Windows-onderwerp kunt u zien welk versie voor elke CSP worden ondersteund.

Bovendien worden niet alle instellingen in het onderwerp door Intune ondersteund. Als u wilt weten of de gewenste instelling door Intune wordt ondersteund, opent u het onderwerp voor de betreffende instelling. U kunt op elke instellingenpagina zien welke bewerkingen worden ondersteund. Voor gebruik in combinatie met Intune moet de instelling de bewerking **Toevoegen** of **Vervangen** ondersteunen.

## <a name="general-configuration-policy-settings"></a>Instellingen voor algemeen configuratiebeleid

Gebruik de **algemene configuratiebeleidsregels** van Microsoft Intune voor Windows 10 om ingebouwde instellingen te configureren voor geregistreerde Windows 10 Desktop- en Windows 10 Mobile-apparaten.

### <a name="password"></a>Wachtwoord

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Een wachtwoord vereisen om apparaten te ontgrendelden**|-|
|**Vereist wachtwoordtype**|Geeft aan of het wachtwoord alleen alfanumeriek of alleen numeriek moet zijn|
|**Vereist wachtwoordtype** - **Minimum aantal tekensets**| Geeft aan hoeveel onderdelen van tekensets (kleine letters, hoofdletters, cijfers en symbolen) moeten worden gebruikt in het wachtwoord|
|**Minimale wachtwoordlengte**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**.|Voor apparaten met Windows 10: als BitLocker is ingeschakeld op het apparaat, wordt het in de herstelmodus van BitLocker gezet nadat het aanmelden het aantal keren dat u opgeeft is mislukt. Als BitLocker niet is ingeschakeld op het apparaat, is deze instelling niet van toepassing.<br>Voor apparaten met Windows 10 Mobile: nadat het aanmelden het aantal keren dat u opgeeft is mislukt, wordt het apparaat gewist.|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u de hoeveelheid tijd aan die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld|
|**Dagen tot wachtwoord verloopt**|Met deze instelling bepaalt u de periode waarna het wachtwoord van een apparaat moet worden gewijzigd|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u aan of u wilt voorkomen dat de gebruiker eerder gebruikte wachtwoorden mag hergebruiken|
|**Wachtwoordgeschiedenis onthouden** - **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden|
|**Wachtwoord vereisen wanneer het apparaat wordt geactiveerd vanuit een niet-actieve status**|Hiermee geeft u aan dat de gebruiker een wachtwoord moet opgeven om het apparaat te ontgrendelen (alleen Windows 10 Mobile)|

### <a name="encryption"></a>Versleuteling

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Versleuteling vereisen voor mobiel apparaat**|Hiermee schakelt u versleuteling op doelapparaten in<br>(alleen Windows 10 Mobile)|

### <a name="system"></a>Systeem

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Schermopname toestaan**|Hiermee kan de gebruiker het apparaatscherm als afbeelding vastleggen (alleen Windows 10 Mobile)|
|**Handmatige uitschrijving toestaan**|Hiermee kan de gebruiker het werkplekaccount handmatig van het apparaat verwijderen|
|**Handmatige installatie van basiscertificaat toestaan**|Dit is van toepassing op Windows 10 Mobile|
|**Toestaan dat diagnostische en gebruiksgegevens worden verzonden naar Microsoft**|Mogelijke waarden zijn:<br><br>**Geen**: er worden geen gegevens naar Microsoft verzonden<br>**Basis**: beperkte informatie wordt naar Microsoft verzonden<br>**Uitgebreid**: uitgebreide diagnostische gegevens worden naar Microsoft verzonden<br>**Volledig (aanbevolen)**: hiermee worden dezelfde gegevens verzonden als bij **Uitgebreid**, aangevuld met gegevens over de apparaatstatus|


### <a name="account-and-synchronization"></a>Account en synchronisatie

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker een Microsoft-account aan het apparaat kan koppelen|
|**Handmatig toevoegen van een ander account dan een Microsoft-account toestaan**|Hiermee staat u toe dat de gebruiker aan het apparaat e-mailaccounts kan toevoegen die niet aan een Microsoft-account zijn gekoppeld|
|**Synchronisatie van instellingen toestaan voor Microsoft-accounts**|Hiermee staat u synchronisatie tussen apparaten toe van apparaat- en app-instellingen die aan een Microsoft-account zijn gekoppeld|

### <a name="microsoft-edge"></a>Microsoft Edge

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Webbrowser toestaan**|Hiermee staat u het gebruik van de webbrowser Microsoft Edge op het apparaat toe<br>(alleen Windows 10 Mobile)|
|**Zoeksuggesties in de adresbalk toestaan**|Hiermee kan de zoekmachine sites voorstellen wanneer er zoektermen worden getypt|
|**Verzenden van intranetverkeer naar Internet Explorer toestaan**|Hiermee staat u toe dat gebruikers intranetsites in Internet Explorer kunnen openen<br>(alleen Windows 10 Desktop)|
|**Do Not Track toestaan**|Hiermee configureert u de browser Microsoft Edge zodanig dat verzoeken om niet gevolgd te worden, worden verzonden naar websites die gebruikers bezoeken|
|**SmartScreen inschakelen**||
|**Active Scripting toestaan**|Toestaan dat scripts, zoals JavaScript, kunnen worden uitgevoerd in de Microsoft Edge-browser|
|**Pop-ups toestaan**|Dit is alleen van toepassing op Windows 10 Desktop|
|**Cookies toestaan**||
|**Automatisch invullen toestaan**|Hiermee stelt u gebruikers in staat instellingen voor automatisch aanvullen in de browser te wijzigen<br>(alleen Windows 10 Desktop)|
|**Wachtwoordbeheer toestaan**|Hiermee schakelt u de functie Wachtwoordbeheer van Microsoft Edge in of uit|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Geeft de plaats aan van de lijst met websites die in Bedrijfsmodus worden geopend. Gebruikers kunnen deze lijst niet bewerken.<br>(alleen Windows 10 Desktop)|

### <a name="apps"></a>Apps

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Toepassingsarchief toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|



### <a name="cellular"></a>Mobiel

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Dataroaming toestaan**|Roaming tussen netwerken toestaan tijdens het ophalen van gegevens|
|**VPN via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen indien verbonden met het mobiele netwerk|
|**VPN-roaming via mobiele verbinding toestaan**|Hiermee bepaalt u of het apparaat toegang kan krijgen tot VPN-verbindingen tijdens het roamen in een mobiel netwerk|

### <a name="hardware"></a>Hardware

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|
|**Camera toestaan**|-|
|**Verwisselbare opslag toestaan**|Hiermee geeft u op of er op het apparaat externe opslagapparaten, zoals een SD-kaart, kunnen worden gebruikt|
|**Wi-Fi toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Internetverbinding delen toestaan**|Hiermee kunt u het gebruik van een gedeelde internetverbinding op het apparaat toestaan|
|**Handmatige Wi-Fi-configuratie toestaan**|Hiermee bepaalt u of de gebruiker zijn eigen Wi-Fi-verbindingen kan instellen, of dat de gebruiker alleen verbindingen kan gebruiken die door een Wi-Fi-profiel zijn geconfigureerd<br>(alleen Windows 10 Mobile)|
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Hiermee kunt u het apparaat automatisch verbinding laten maken met gratis Wi-Fi-hotspots en automatisch de voorwaarden voor de verbinding laten accepteren|
|**Geolocatie toestaan**|Geeft aan of op het apparaat gegevens van locatieservices kunnen worden gebruikt|
|**NFC toestaan**|Hiermee staat u gebruik van de NFC-mogelijkheden op het apparaat toe|
|**Bluetooth toestaan**|-|
|**Modus voor Bluetooth-detectie toestaan**|Hiermee kan dit apparaat worden gedetecteerd door andere Bluetooth-apparaten|
|**Bluetooth-promotie toestaan**|Hiermee staat u toe dat apparaten reclame via Bluetooth kunnen ontvangen|
|**Opnieuw instellen van telefoon toestaan**|Hiermee bepaalt u of de gebruiker de fabrieksinstellingen van het apparaat kan herstellen|
|**USB-verbinding toestaan**|Hiermee bepaalt u of apparaten via een USB-verbinding toegang kunnen hebben tot externe opslagapparaten|
|**Antidiefstalmodus toestaan**|Hiermee configureert u of de antidiefstalmodus van Windows is ingeschakeld|

### <a name="features"></a>Functies

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Kopiëren en plakken toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Spraakopname toestaan**|Dit is alleen van toepassing op Windows 10 Mobile|
|**Cortana toestaan**|Hiermee schakelt u de spraakassistent Cortana in of uit|
|**Meldingen van onderhoudscentrum toestaan**|Hiermee schakelt u de meldingen van het Onderhoudscentrum op het vergrendelingsscherm in of uit<br>(alleen Windows 10 Mobile)|

### <a name="windows-defender"></a>Windows Defender

Alle instellingen zijn alleen voor Windows 10 Desktop.

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|----------------------|---------------------|
|**Real-timecontrole toestaan**|Hiermee schakelt u het real-time scannen op malware, spyware en andere ongewenste software in|
|**Gedragscontrole toestaan**|Hiermee kunt u Defender laten controleren op de aanwezigheid van bepaalde bekende patronen van verdachte activiteiten op apparaten|
|**Netwerkinspectiesysteem inschakelen**|Het Netwerkinspectiesysteem (NIS) kan u op basis van de handtekeningen van bekende beveiligingsproblemen van het Microsoft Endpoint Protection Center helpen met het detecteren en blokkeren van schadelijk verkeer, zodat de apparaten in het netwerk beveiligd zijn tegen exploits|
|**Alle downloads scannen**|Hiermee bepaalt u of Windows Defender alle bestanden moet scannen die van internet worden gedownload|
|**Scannen van scripts toestaan**|Hiermee laat u Defender scripts scannen die worden gebruikt in Internet Explorer|
|**Activiteiten van bestanden en programma's bewaken**|Hiermee staat u Defender toe om activiteiten van bestanden en programma's op apparaten te bewaken|
|**Dagen om opgeloste problemen met malware bij te houden**|Hiermee kunt Defender gedurende het aantal dagen dat u opgeeft, opgeloste malware laten bijhouden, zodat u handmatig eerder aangevallen apparaten kunt controleren. Als u het aantal dagen instelt op **0**, blijft malware in de map Quarantaine staan en wordt malware niet automatisch verwijderd. |
|**Toegang tot de gebruikersinterface voor de client toestaan**|Hiermee bepaalt u of de gebruikersinterface van Windows Defender voor gebruikers wordt verborgen.<br>Als deze instelling wordt gewijzigd, gaat de wijziging in wanneer de pc van de gebruiker de volgende keer opnieuw wordt opgestart.|
|**Een dagelijkse snelle scan plannen**|Hiermee kunt u een snelle scan plannen die dagelijks wordt uitgevoerd op het moment dat u selecteert|
|**Een systeemscan plannen**|Hiermee kunt u een volledige of snelle systeemscan plannen die regelmatig wordt uitgevoerd op de dag en tijd die u selecteert|
|**CPU-verbruik tijdens een scan beperken**|Hiermee kunt u de hoeveelheid CPU beperken die scans mogen gebruiken (van **1** tot **100**).|
|**Archiefbestanden scannen**|Hiermee kunt u toestaan dat Defender gearchiveerde bestanden scant, zoals ZIP- of CAB-bestanden.|
|**E-mailberichten scannen**|Hiermee kunt u toestaan dat Defender e-mailberichten scant wanneer deze op het apparaat binnenkomen|
|**Verwisselbare stations scannen**|Hiermee kunt u Defender verwisselbare stations, zoals USB-sticks, laten scannen|
|**Toegewezen netwerkstations scannen**|Hiermee kunt u Defender bestanden op een gekoppeld netwerkstation laten scannen.<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|
|**Bestanden scannen die zijn geopend vanuit gedeelde mappen op het netwerk**|Hiermee kunt u Defender bestanden op gedeelde stations laten scannen (bijvoorbeeld gedeelde stations die via een UNC-pad toegankelijk zijn).<br>Als de bestanden op de schijf het kenmerk Alleen-lezen hebben, kan Defender eventueel gevonden malware niet verwijderen.|
|**Interval voor handtekeningupdates**|Hiermee geeft u het interval op waarmee Defender op nieuwe handtekeningbestanden controleert.|
|**Cloudbeveiliging toestaan**|Hiermee kunt u toestaan of blokkeren dat de Microsoft Active Protection-service informatie ontvangt over malware-activiteit op apparaten die u beheert. Deze informatie wordt gebruikt om de service in de toekomst te verbeteren.|
|**Gebruikers vragen voorbeelden te verzenden**|Hiermee bepaalt u of bestanden waarvoor verdere analyse door Microsoft nodig is om te bepalen of deze schadelijk zijn, automatisch naar Microsoft moeten worden verzonden|
|**Detectie van mogelijk ongewenste toepassingen**|Hiermee worden geregistreerde Windows-desktopapparaten beveiligd tegen het uitvoeren van software die door Windows Defender als mogelijk ongewenst is gedefinieerd. U kunt voorkomen dat deze toepassingen worden uitgevoerd, of de controlemodus gebruiken om te rapporteren wanneer een mogelijk ongewenste toepassing wordt geïnstalleerd.|
|**Bestanden en mappen die moeten worden uitgesloten bij het scannen en bij real-timebeveiliging**|Voegt aan de uitsluitingslijst een of meer bestanden en mappen toe, zoals **C:\pad** of **%ProgramFiles%\pad\bestandsnaam.exe**. Deze bestanden en mappen worden niet opgenomen in real-timescans of geplande scans.|
|**Bestandsextensies die moeten worden uitgesloten bij het scannen en bij real-timebeveiliging**|Voeg aan de uitsluitingslijst een of meer bestandsextensies toe, zoals **jpg** of **txt**. Bestanden met deze extensies worden niet opgenomen in real-timescans of geplande scans.|
|**Processen die uitgesloten moeten worden bij het scannen en bij de real-timebeveiliging**|Voegt aan de uitsluitingslijst een of meer processen toe van het type **.exe**, **.com** of **.scr**. Deze processen worden niet opgenomen in real-timescans of geplande scans.|


### <a name="updates"></a>Updates

|Naam van de instelling|Aanvullende informatie (indien nodig)|
|----------------|---------------|
|**Automatische updates toestaan**|Automatische updates toestaan. Configureer een van de volgende instellingen om het gedrag voor updates te bepalen:<br />**Melding van download**<br />**Automatisch installeren op onderhoudstijdstip**<br />**Automatisch installeren en opstarten op onderhoudstijdstip**<br />**Automatisch installeren en opnieuw opstarten op het geplande tijdstip**: wanneer deze optie is geselecteerd, kunt u ook de volgende instellingen configureren: **Melding onderdrukken voor eindgebruiker** en **De installatiedag voor geplande updates definiëren**.<br>(alleen Windows 10 Desktop)|
|**Functies van evaluatieversies toestaan**|Hiermee kan Microsoft instellingen en functies van evaluatieversies implementeren op Windows 10-apparaten. U kunt selecteren dat alleen instellingen zijn toegestaan, of dat alle instellingen en functies van evaluatieversies mogen worden geïnstalleerd.|

### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

