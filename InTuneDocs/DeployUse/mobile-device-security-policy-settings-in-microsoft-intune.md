---
# required metadata

title: Instellingen voor beveiligingsbeleid van mobiele apparaten | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Instellingen voor beveiligingsbeleid van mobiele apparaten in Microsoft Intune
> [!IMPORTANT]
> Microsoft Intune biedt nu afzonderlijk configuratiebeleid voor elk apparaatplatform. Dit beleid bevat de recentste instellingen die u kunt gebruiken. U kunt het beveiligingsbeleid voor mobiele apparaten blijven gebruiken en eventuele bestaande implementaties zullen nog steeds werken. U moet echter zo snel mogelijk naar de nieuwe configuratiebeleidsregels migreren aangezien het beveiligingsbeleid voor mobiele apparaten in de toekomst wordt verwijderd.

Gebruik Intune-beveiligingsbeleid voor mobiele apparaten voor het configureren van een breed scala aan instellingen die u kunt implementeren op beheerde apparaten in uw organisatie. Deze instellingen kunnen worden gebruikt om de functionaliteit en beveiliging van uw apparaten te beheren.

U kunt beveiligingsbeleidsregels voor mobiele apparaten maken en implementeren voor de volgende typen apparaten:

-   Windows RT 8.1 en ingeschreven apparaten met Windows 8.1

-   Windows RT

-   Windows Phone 8 en Windows Phone 8.1

-   iOS

-   Android en Samsung KNOX

> [!NOTE]
> Sommige instellingen zijn niet van toepassing op sommige apparaten. Zie de onderstaande tabel voor een volledige lijst met instellingen die u kunt configureren.

## Beveiligingsinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Nee|Nee|Ja|Ja|Ja|
|**Vereist wachtwoordtype**<br /><br />(geeft het type wachtwoord op dat vereist is, zoals alleen numeriek of alfanumeriek)|Ja|Ja|Ja|Ja|Nee|
|**Vereist wachtwoordtype – minimumaantal tekensets**<br /><br />Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets moeten worden opgenomen in het wachtwoord). Voor iOS-apparaten geeft u hiermee echter het aantal symbooltekens aan dat moet zijn opgenomen in het wachtwoord)|Ja|Ja|Ja|Ja|Nee|
|**Minimale wachtwoordlengte**|Ja|Ja|Ja|Ja|Ja|
|**Eenvoudige wachtwoorden toestaan**<br /><br />Eenvoudige wachtwoorden zijn onder andere '0000' en '1234'|Nee|Nee|Ja|Ja|Nee|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Ja|Ja|Ja|Ja|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**<sup>1</sup>|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordverlooptijd (dagen)**|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordkwaliteit**|Nee|Nee|Nee|Nee|Ja|
|**Afbeeldingswachtwoord en PIN toestaan**|Ja|Ja|Nee|Nee|Nee|
|**Minuten inactief voordat wachtwoord is vereist**|Nee|Nee|Nee|Ja|Nee|
|**Vingerafdruk voor ontgrendelen toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
Wanneer u bij iOS-apparaten de instellingen **Minuten van inactiviteit voordat het scherm wordt uitgeschakeld** en **Minuten van inactiviteit voordat een wachtwoord is vereist** configureert, worden deze in volgorde toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **5** minuten, wordt het scherm na 5 minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens 5 minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat 5 minuten later vergrendeld.

Wanneer u beleid voor de wachtwoordlengte implementeert op apparaten met Windows RT, worden gebruikers gedwongen hun wachtwoord opnieuw in te stellen, zelfs als het huidige wachtwoord voldoet aan de beleidsvereisten.

## Versleutelingsinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Versleuteling vereisen op mobiele apparaat**<sup>1</sup><br /><br />Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.<br /><br />Schakel de instelling **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**in om versleuteling van iOS-apparaten in te schakelen.|Ja|Nee|Ja|Nee|Ja|
|**Versleuteling vereisen voor opslagkaarten**<br /><br />Ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t. (de apps en de bijbehorende gegevens worden automatisch versleuteld)|n.v.t.|Ja|
Aanvullende informatie voor apparaten met Windows 8.1

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Versleuteling werkt alleen indien het apparaat voldoet aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanaf het Microsoft-account van de gebruiker, wanneer deze sleutel vanaf het bijbehorende OneDrive-account wordt geopend. U kunt deze sleutel niet namens een gebruiker herstellen.

## Instellingen voor malware

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Netwerkfirewall vereisen**|Ja|Nee|Nee|Nee|Nee|
|**SmartScreen inschakelen**|Ja|Nee|Nee|Nee|Nee|

## Systeeminstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Automatische updates vereisen**|Ja|Nee|Nee|Nee|Nee|
|**Automatische updates vereisen: minimale classificatie van updates automatisch laten installeren**<br /><br />Kies de classificatie van updates die automatisch worden geïnstalleerd:<br /><br />**Belangrijk**: hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk.<br /><br />**Aanbevolen**: hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk of aanbevolen.|Ja|Nee|Nee|Nee|Nee|
|**Schermafbeelding toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Ja|Ja (alleen Samsung KNOX)|
|**Beheercentrum in vergrendelingsscherm toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Weergave van meldingen in vergrendelingsscherm toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Weergave van vandaag in vergrendelingsscherm toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Gebruikersaccountbeheer**|Ja|Nee|Nee|Nee|Nee|
|**Verzending van diagnostische gegevens toestaan**|Ja|Nee|Alleen Windows Phone 8.1|Ja|Ja (alleen Samsung KNOX)|
|**Niet-vertrouwde TLS-certificaten toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Personal Wallet-software tijdens vergrendeling toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Terugzetten op fabrieksinstellingen toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|


## Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Back-up naar iCloud® toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Documentsynchronisatie met iCloud toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Photo Stream-synchronisatie met iCloud toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Versleutelde back-ups vereisen**|Nee|Nee|Nee|Ja|Nee|
|**URL voor werkmappen**<br /><br />(stelt de URL van de werkmap in zodat documenten over verschillende apparaten kunnen worden gesynchroniseerd)|Ja|Nee|Nee|Nee|Nee|
|**Back-up van Google toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|

## Cloudinstellingen - accounts en synchronisatie

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Microsoft-account toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|
|**Automatische synchronisatie van Google-account toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|

## E-mailinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Gebruikers toestaan om e-mailbijlagen te downloaden**<sup>1</sup>|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
|**Synchronisatieperiode e-mail** Ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
|**Mobiele apparaten die deze instellingen niet volledig ondersteunen, mogen synchroniseren met Exchange (Exchange ActiveSync)** Ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
|**Het Microsoft-account optioneel maken in de Windows Mail-toepassing**|Ja|Nee|Nee|Nee|Nee|
|**Aangepaste e-mailaccounts toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|

## Toepassingsinstellingen - browser

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Webbrowser toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Ja|Ja (alleen Samsung KNOX)|
|**Automatisch invullen toestaan**|Ja|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Pop-upblokkering toestaan**|Ja|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Cookies toestaan**|Nee|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Invoegtoepassingen toestaan**|Ja|Nee|Nee|Nee|Nee|
|**Active Scripting toestaan**|Ja|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Waarschuwing voor fraude toestaan**|Ja|Nee|Nee|Ja|Nee|
|**Naar een intranetsite gaan voor invoer van één woord toestaan**<br /><br />(staat het gebruik van één woord toe om Internet Explorer rechtstreeks naar een website, zoals Bing, te laten gaan)|Ja|Nee|Nee|Nee|Nee|
|**Automatische detectie van een intranetnetwerk toestaan**|Ja|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor internet**|Ja|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor intranet**|Ja|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor vertrouwde sites**|Ja|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor websites met beperkte toegang**|Ja|Nee|Nee|Nee|Nee|
|**Do Not Track-header verzenden**|Ja|Nee|Nee|Nee|Nee|
|**Toegang tot Bedrijfsmodus-menu toestaan**|Ja|Nee|Nee|Nee|Nee|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Ja|Nee|Nee|Nee|Nee|

## Toepassingsinstellingen - apps

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Toepassingsarchief toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Ja|Ja (alleen Samsung KNOX)|
|**Wachtwoord vereisen voor toegang tot het toepassingsarchief**|Nee|Nee|Nee|Ja|Nee|
|**Aankopen in app toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Beheerde documenten in andere niet-beheerde apps toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Niet-beheerde documenten in andere beheerde apps toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Videovergaderingen toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Inhoud voor volwassenen in media store toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Installatie van app toestaan**|Nee|Nee|Nee|iOS 6 en hoger|Nee|

## Toepassingsinstellingen - gaming

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Game Center-vrienden toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Games voor meerdere spelers toestaan**|Nee|Nee|Nee|Ja|Nee|

## Instellingen voor apparaatmogelijkheden - hardware

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Camera toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Ja|Ja|
|**Verwisselbare opslag toestaan**|Nee|Nee|Ja|Nee|Ja (alleen Samsung KNOX)|
|**Wi-Fi toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**Wi-Fi-tethering toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|
|**Melden van Wi-Fi-hotspots toestaan**<br /><br />(informatie over Wi-Fi-verbindingen verzenden om nabije verbindingen te detecteren)|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|
|**Geolocatie toestaan**<br /><br />(het apparaat mag locatiegegevens gebruiken)|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**NFC toestaan**<br /><br />(hiermee kunt u bewerkingen uitvoeren waarvoor near field communication wordt gebruikt)|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**Bluetooth toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**Uitschakelen toestaan**<br>Als deze instelling is uitgeschakeld, werkt de instelling **Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist** voor Samsung KNOX-apparaten niet.|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|

## Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Spraakroaming toestaan**|Nee|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Gegevensroaming toestaan**|Ja|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Automatische synchronisatie tijdens roamen toestaan**|Nee|Nee|Nee|Ja|Nee|
|**SMS- en MMS-berichten toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|

## Instellingen voor apparaatmogelijkheden - functies

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Spraakassistent toestaan**|Nee|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Spraakassistent toestaan terwijl het apparaat is vergrendeld**|Nee|Nee|Nee|Ja|Nee|
|**Nummer inspreken toestaan**|Nee|Nee|Nee|Ja|Ja (alleen Samsung KNOX)|
|**Kopiëren en plakken toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**Klembord delen tussen toepassingen toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|
|**YouTube toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|

### Zie ook
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=May16_HO2-->


