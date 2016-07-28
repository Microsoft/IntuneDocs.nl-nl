---
title: Windows-beleidsinstellingen | Microsoft Intune
description: Gebruik de algemene regels voor het Intune Windows-configuratiebeleid (Windows 8.1 en later) om instellingen te configureren voor geregistreerde Windows 8.1- en Windows 8-apparaten.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: a70b81e490a5c55d9ce11bd8dbdfc42ab364273c


---

# Windows-beleidsinstellingen in Microsoft Intune
Gebruik de **algemene regels voor het Windows-configuratiebeleid (Windows 8.1 en later)** om de volgende instellingen te configureren voor geregistreerde Windows 8.1- en Windows 8-apparaten:

## Toepasselijkheidsinstellingen

|Naam van de instelling|Details|
|----------------|----------------------------------|
|**Alle configuraties toepassen op Windows 10**|Hiermee kunt de instellingen in dit beleid naast Windows 8 en Windows 8.1-apparaten toepassen op Windows 10-apparaten.|

## Beveiligingsinstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Vereist wachtwoordtype**|Hiermee geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek.|Ja|Ja|
|**Vereist wachtwoordtype – minimumaantal tekensets**|Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets moeten worden opgenomen in het wachtwoord. Voor iOS-apparaten geeft u hiermee echter het aantal symbooltekens aan dat moet zijn opgenomen in het wachtwoord.|Ja|Ja|
|**Minimale wachtwoordlengte**<sup>1</sup>|Hiermee configureert u de minimaal vereiste lengte (in tekens) voor het wachtwoord op apparaten.|Ja|Ja|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Hiermee worden de gegevens op het apparaat gewist als het aanmelden dit aantal keren mislukt.|Ja|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee kiest u het aantal minuten dat een apparaat inactief moet zijn voordat er een wachtwoord is vereist om het apparaat te ontgrendelen.| Ja|Ja|
|**Wachtwoordverlooptijd (dagen)**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u op of de gebruiker eerder gebruikte wachtwoorden kan configureren.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|Ja|Ja|
|**Afbeeldingswachtwoord en PIN toestaan**|Hiermee kunt het gebruik van een afbeeldingswachtwoord en pincode op het apparaat toestaan. Met een afbeeldingswachtwoord kan de gebruiker zich met gebaren op een afbeelding aanmelden. Met een pincode kunnen gebruikers zich snel met 4 cijfers aanmelden.|Ja|Ja|
<sup>1</sup> Wanneer u beleid voor de wachtwoordlengte implementeert op apparaten met Windows RT, worden gebruikers gedwongen hun wachtwoord opnieuw in te stellen, zelfs als het huidige wachtwoord voldoet aan de beleidsvereisten.

## Versleutelingsinstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Versleuteling vereisen voor mobiel apparaat**<sup>1</sup>|Vereist dat bestanden op het apparaat zijn versleuteld.<br>Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.|Ja|Nee|
<sup>1</sup> Aanvullende informatie voor apparaten met Windows 8.1

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Versleuteling werkt alleen indien het apparaat voldoet aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanaf het Microsoft-account van de gebruiker, wanneer deze sleutel vanaf het bijbehorende OneDrive-account wordt geopend. U kunt deze sleutel niet namens een gebruiker herstellen.

## Instellingen voor malware

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Netwerkfirewall vereisen**|Hiermee vereist u dat Windows Firewall is ingeschakeld.|Ja|Nee|
|**SmartScreen inschakelen**|Hiermee vereist u het gebruik van Windows SmartScreen op apparaten.|Ja|Nee|

## Systeeminstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Automatische updates vereisen**|Hiermee schakelt u de instelling voor automatische updates op apparaten in.|Ja|Nee|
|**Automatische updates vereisen: minimale classificatie van updates automatisch laten installeren**|Kies de classificatie van updates die automatisch worden geïnstalleerd:<br /><br />-   **Belangrijk**: hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk.<br />-   **Aanbevolen**: hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk of aanbevolen.|Ja|Nee|
|**Gebruikersaccountbeheer**|Hiermee vereist u het gebruik van Gebruikersaccountbeheer (UAC) op apparaten.|Ja|Nee|
|**Verzending van diagnostische gegevens toestaan**|Hiermee staat u toe dat het apparaat diagnostische gegevens verzendt naar Microsoft.|Ja|Nee|


## Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**URL voor werkmappen**|Hiermee stelt u de URL van de werkmap in, zodat documenten over verschillende apparaten kunnen worden gesynchroniseerd|Ja|Nee|

## E-mailinstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Het Microsoft-account optioneel maken in de Windows Mail-toepassing**|Hiermee staat u toegang zonder Microsoft-account toe tot de toepassing Windows Mail.|Ja|Nee|

## Toepassingsinstellingen - browser

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Automatisch invullen toestaan**|Gebruiker kan de instellingen voor automatisch aanvullen in de browser wijzigen.|Ja|Nee|
|**Pop-upblokkering toestaan**|Hiermee schakelt u de pop-upblokkering voor browsers in of uit.|Ja|Nee|
|**Invoegtoepassingen toestaan**|Gebruiker kan invoegtoepassingen toevoegen aan Internet Explorer.|Ja|Nee|
|**Active Scripting toestaan**|Browser kan scripts, zoals Active X-scripts, uitvoeren.|Ja|Nee|
|**Waarschuwing voor fraude toestaan**|Hiermee schakelt u de waarschuwingen voor mogelijke frauduleuze websites in of uit.|Ja|Nee|
|**Naar een intranetsite gaan voor invoer van één woord toestaan**|Hiermee staat u het gebruik toe van één woord om Internet Explorer naar een website te sturen, zoals Bing|Ja|Nee|
|**Automatische detectie van een intranetnetwerk toestaan**|Hiermee wordt de beveiliging geconfigureerd voor intranetsites in Internet Explorer.|Ja|Nee|
|**Beveiligingsniveau voor internet**|Hiermee stelt u het beveiligingsniveau voor internetsites in Internet Explorer in.|Ja|Nee|
|**Beveiligingsniveau voor intranet**|Hiermee stelt u het beveiligingsniveau voor intranetsites in Internet Explorer in.|Ja|Nee|
|**Beveiligingsniveau voor vertrouwde sites**|Hiermee stelt u het beveiligingsniveau in voor de zone voor vertrouwde sites.|Ja|Nee|
|**Beveiligingsniveau voor websites met beperkte toegang**|Hiermee stelt u het beveiligingsniveau in voor de zone voor websites met beperkte toegang.|Ja|Nee|
|**Do Not Track-header verzenden**|Hiermee verzendt u in Internet Explorer een Do Not Track-header naar bezochte websites.|Ja|Nee|
|**Toegang tot Bedrijfsmodus-menu toestaan**|Hiermee kunnen gebruikers toegang krijgen tot de menuoptie Ondernemingsmodus van Internet Explorer.<br>Indien geselecteerd, kunt u ook een **Locatie van registratierapport** opgeven, die een URL bevat naar een rapport waarin websites zijn opgenomen waarvoor gebruikers de bedrijfsmodus hebben ingeschakeld.|Ja|Nee|
|**Locatie van de lijst met websites van Bedrijfsmodus**|U kunt de locatie van de lijst met websites opgeven die door Bedrijfsmodus wordt gebruikt als het actief is.|Ja|Nee|

## Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Gegevensroaming toestaan**|Hiermee staat u gegevensroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Ja|Nee|



### Zie ook
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


