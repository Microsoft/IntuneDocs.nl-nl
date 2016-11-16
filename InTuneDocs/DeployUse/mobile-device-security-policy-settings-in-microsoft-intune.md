---
title: Instellingen voor beveiligingsbeleid van mobiele apparaten | Microsoft Intune
description: Gebruik Intune voor het configureren van een breed scala aan instellingen die u kunt implementeren op beheerde apparaten in uw organisatie.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e95db6d0ccbe350984f11ce08749b700c2f5ad01
ms.openlocfilehash: 279b2fbcbdc7bace99d99eca5bc766972dcea3b8



---

# Instellingen voor beveiligingsbeleid van mobiele apparaten in Microsoft Intune
> [!IMPORTANT]
> Microsoft Intune heeft nu afzonderlijke configuratiebeleidsregels voor elk apparaatplatform. Deze beleidsregels bevatten de meest recente instellingen die u kunt gebruiken. U kunt het beveiligingsbeleid voor mobiele apparaten blijven gebruiken en eventuele bestaande implementaties zullen nog steeds werken. U moet echter zo snel mogelijk de migratie naar de nieuwe configuratiebeleidsregels uitvoeren omdat het beveiligingsbeleid voor mobiele apparaten in de toekomst wordt verwijderd.

U kunt het Intune-beveiligingsbeleid voor mobiele apparaten gebruiken voor het configureren van een breed scala aan instellingen die u kunt implementeren op beheerde apparaten in uw organisatie. Deze instellingen worden gebruikt om de functionaliteit en beveiliging van uw apparaten te beheren.

U kunt beveiligingsbeleidsregels voor mobiele apparaten maken en implementeren voor de volgende typen apparaten:

-   Windows RT 8.1 en ingeschreven apparaten met Windows 8.1

-   Windows RT

-   Windows Phone 8 en Windows Phone 8.1

-   iOS

-   Android en Samsung KNOX

> [!NOTE]
> Sommige instellingen zijn niet van toepassing op sommige apparaten. Zie de onderstaande tabellen voor een volledige lijst met instellingen die u kunt configureren.
> Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor Windows 8-bedrijfsportalapps. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8- en Windows RT-platform. Als gevolg hiervan kunt u geen Windows Phone 8- of Windows RT-apparaten meer registreren of bijwerken. U kunt Windows Phone 8-, Windows RT- en Windows 8-apparaten die al zijn geregistreerd, blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportalapps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.

## Beveiligingsinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Nee|Nee|Ja|Ja|Ja|
|**Vereist wachtwoordtype**<br /><br />Met deze instelling geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek.|Ja|Ja|Ja|Ja|Nee|
|**Vereist wachtwoordtype – minimumaantal tekensets**<br /><br />Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets moeten worden opgenomen in het wachtwoord. Voor iOS-apparaten geeft u hiermee echter het aantal symbooltekens aan dat moet zijn opgenomen in het wachtwoord.|Ja|Ja|Ja|Ja|Nee|
|**Minimale wachtwoordlengte**|Ja|Ja|Ja|Ja|Ja|
|**Eenvoudige wachtwoorden toestaan**<br /><br />Eenvoudige wachtwoorden zijn onder andere '0000' en '1234'.|Nee|Nee|Ja|Ja|Nee|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Ja|Ja|Ja|Ja|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**<sup>1</sup>|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordverlooptijd (dagen)**|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordkwaliteit**|Nee|Nee|Nee|Nee|Ja|
|**Afbeeldingswachtwoord en PIN toestaan**|Ja|Ja|Nee|Nee|Nee|
|**Minuten inactief voordat wachtwoord is vereist**|Nee|Nee|Nee|Ja|Nee|
|**Vingerafdruk voor ontgrendelen toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
<sup>1</sup> Wanneer u voor iOS-apparaten de instellingen **Minuten van inactiviteit voordat het scherm wordt uitgeschakeld** en **Minuten van inactiviteit voordat wachtwoord vereist is** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **5** minuten, wordt het scherm na 5 minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens 5 minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat 5 minuten later vergrendeld.

Wanneer u beleid voor de wachtwoordlengte implementeert op apparaten met Windows RT, worden gebruikers gedwongen hun wachtwoord opnieuw in te stellen, zelfs als het huidige wachtwoord voldoet aan de beleidsvereisten.

## Versleutelingsinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Versleuteling vereisen op mobiele apparaat**<sup>1</sup><br /><br />Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.<br /><br />Schakel de instelling **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**in om versleuteling van iOS-apparaten in te schakelen.|Ja|Nee|Ja|Nee|Ja|
|**Versleuteling vereisen voor opslagkaarten**<br /><br />Deze instelling is ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t. <br />De apps en de bijbehorende gegevens worden automatisch versleuteld.|n.v.t.|Ja|
<sup>1</sup>Hier is aanvullende informatie voor apparaten waarop Windows 8.1 wordt uitgevoerd:

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Versleuteling werkt alleen indien het apparaat voldoet aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanuit het Microsoft-account van de gebruiker, waartoe de gebruiker alleen toegang heeft vanuit zijn of haar OneDrive-account. U kunt deze sleutel niet namens een gebruiker herstellen.

## Instellingen voor malware

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Netwerkfirewall vereisen**|Ja|Nee|Nee|Nee|Nee|
|**SmartScreen inschakelen**|Ja|Nee|Nee|Nee|Nee|

## Systeeminstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Automatische updates vereisen**|Ja|Nee|Nee|Nee|Nee|
|**Automatische updates vereisen: minimale classificatie van updates automatisch laten installeren**<br /><br />Kies de classificatie van updates die automatisch worden geïnstalleerd:<br /><br />- **Belangrijk**. Hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk.<br /><br />- **Aanbevolen**. Hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk of aanbevolen.|Yes|Nee|Nee|Nee|Nee|
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
|**URL voor werkmappen**<br /><br />Met deze instelling stelt u de URL van de werkmap in, zodat documenten op verschillende apparaten kunnen worden gesynchroniseerd.|Ja|Nee|Nee|Nee|Nee|
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
|**E-mailsynchronisatieperiode** <br /><br />Deze instelling is ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
|**Mobiele apparaten die deze instellingen niet volledig ondersteunen, mogen synchroniseren met Exchange (Exchange ActiveSync)** <br /><br />Deze instelling is ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
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
|**Naar een intranetsite gaan voor invoer van één woord toestaan**<br /><br />(Met deze instelling staat u toe dat er één woord wordt gebruikt om Internet Explorer naar een website te sturen, zoals ‘Bing’.)|Yes|Nee|Nee|Nee|Nee|
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
|**Melden van Wi-Fi-hotspots toestaan**<br /><br />Met deze instelling kunt u het apparaat toestaan informatie over Wi-Fi-verbindingen te verzenden om verbindingen in de buurt te detecteren.|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|
|**Geolocatie toestaan**<br /><br />Met deze instelling kun u het apparaat toestaan locatiegegevens te gebruiken.|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**NFC toestaan**<br /><br />Met deze instelling staat u bewerkingen toe waarvoor Near Field Communication wordt gebruikt.|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**Bluetooth toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX)|
|**Uitschakelen toestaan**<br>Als deze instelling is uitgeschakeld, werkt de instelling **Aantal mislukte aanmeldpogingen voordat het apparaat wordt gewist** voor Samsung KNOX-apparaten niet.|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX)|

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

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Oct16_HO2-->


