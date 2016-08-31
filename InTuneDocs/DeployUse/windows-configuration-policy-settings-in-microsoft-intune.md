---
title: Windows-beleidsinstellingen | Microsoft Intune
description: Gebruik de algemene regels voor het Intune Windows-configuratiebeleid (Windows 8.1 en later) om instellingen te configureren voor geregistreerde Windows 8.1- en Windows 8-apparaten.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7fdfe64a18fe359ee4b3b4507ef4108ad65ab573
ms.openlocfilehash: 3102e4637c61bbae002fb30947acd1f82204ac93


---

# Windows-beleidsinstellingen in Microsoft Intune
Gebruik het **algemene Windows-configuratiebeleid (Windows 8.1 en hoger)** om de volgende instellingen te configureren voor geregistreerde Windows 8- en Windows 8.1-apparaten:

## Toepasselijkheidsinstellingen

|Naam van de instelling|Details|
|----------------|----------------------------------|
|**Alle configuraties toepassen op Windows 10**|Hiermee worden de instellingen in dit beleid behalve op Windows 8- en Windows 8.1-apparaten, ook op Windows 10-apparaten toegepast.|

## Beveiligingsinstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Vereist wachtwoordtype**|Hiermee geeft u het wachtwoordtype op dat is vereist, zoals alfanumeriek of alleen numeriek.|Yes|Ja|
|**Vereist wachtwoordtype – minimumaantal tekensets**|Hiermee geeft u op hoeveel verschillende tekensets er moeten worden opgenomen in het wachtwoord. Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Voor iOS-apparaten geeft u met deze instelling echter het aantal symbolen op dat moet worden opgenomen in het wachtwoord.|Yes|Ja|
|**Minimale wachtwoordlengte**<sup>1</sup>|Hiermee configureert u de minimaal vereiste lengte (in tekens) voor het wachtwoord.|Yes|Ja|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Hiermee wist u het apparaat als er meer mislukte aanmeldingspogingen zijn gedaan dan het toegestane aantal pogingen.|Yes|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u het aantal minuten op dat een apparaat inactief moet zijn voordat er een wachtwoord is vereist om het apparaat te ontgrendelen.| Ja|Ja|
|**Wachtwoordverlooptijd (dagen)**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u op of de gebruiker eerder gebruikte wachtwoorden kan configureren.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|Ja|Ja|
|**Afbeeldingswachtwoord en PIN toestaan**|Hiermee maakt u het gebruik van een afbeeldingswachtwoord en pincode mogelijk. Met een afbeeldingswachtwoord kan de gebruiker zich aanmelden met aanraakbewegingen op een afbeelding. Met een pincode kunnen gebruikers zich snel met een code van 4 cijfers aanmelden.|Yes|Yes|
<sup>1</sup> Wanneer u het beleid voor de wachtwoordlengte implementeert op apparaten met Windows RT, worden gebruikers gedwongen hun wachtwoord opnieuw in te stellen, zelfs als het huidige wachtwoord voldoet aan de beleidsvereisten.

## Versleutelingsinstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Versleuteling vereisen voor mobiel apparaat**<sup>1</sup>|Vereist dat bestanden op het apparaat zijn versleuteld.<br>Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.|Ja|Nee|
<sup>1</sup> Aanvullende informatie voor apparaten met Windows 8.1

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Versleuteling werkt alleen indien het apparaat voldoet aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanuit het Microsoft-account van de gebruiker, waartoe de gebruiker alleen toegang heeft vanuit zijn of haar OneDrive-account. U kunt deze sleutel niet namens een gebruiker herstellen.

## Instellingen voor malware

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Netwerkfirewall vereisen**|Hiermee vereist u dat Windows Firewall is ingeschakeld.|Yes|Nee|
|**SmartScreen inschakelen**|Hiermee vereist u het gebruik van Windows SmartScreen.|Yes|Nee|

## Systeeminstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Automatische updates vereisen**|Hiermee schakelt u de instelling voor automatische updates op apparaten in.|Yes|Nee|
|**Automatische updates vereisen: minimale classificatie van updates automatisch laten installeren**|Hiermee kiest u de classificatie van updates die automatisch worden geïnstalleerd:<br /><br />-   **Belangrijk**: hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk.<br />-   **Aanbevolen**: hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk of aanbevolen.|Ja|Nee|
|**Gebruikersaccountbeheer**|Hiermee vereist u het gebruik van Gebruikersaccountbeheer (UAC) op apparaten.|Ja|Nee|
|**Verzending van diagnostische gegevens toestaan**|Hiermee stelt u het apparaat in staat diagnostische gegevens naar Microsoft te verzenden.|Yes|Nee|


## Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**URL voor werkmappen**|Hiermee stelt u de URL van de werkmap in, zodat documenten op verschillende apparaten kunnen worden gesynchroniseerd.|Ja|Nee|

## E-mailinstellingen

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Het Microsoft-account optioneel maken in de Windows Mail-toepassing**|Hiermee maakt u het mogelijk om toegang te krijgen tot de toepassing Windows Mail zonder Microsoft-account.|Ja|Nee|

## Toepassingsinstellingen - browser

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Automatisch invullen toestaan**|Hiermee stelt u gebruikers in staat instellingen voor automatisch aanvullen in de browser te wijzigen.|Ja|Nee|
|**Pop-upblokkering toestaan**|Hiermee schakelt u de pop-upblokkering voor browsers in of uit.|Ja|Nee|
|**Invoegtoepassingen toestaan**|Hiermee stelt u gebruikers in staat invoegtoepassingen toe te voegen aan Internet Explorer.|Ja|Nee|
|**Active Scripting toestaan**|Hiermee stelt u de browser in staat scripts, zoals Active X-scripts, uit te voeren.|Yes|Nee|
|**Waarschuwing voor fraude toestaan**|Hiermee schakelt u de waarschuwingen voor mogelijke frauduleuze websites in of uit.|Yes|Nee|
|**Naar een intranetsite gaan voor invoer van één woord toestaan**|Hiermee stelt u gebruikers in staat om Internet Explorer naar een website te sturen met één woord, zoals Bing.|Ja|Nee|
|**Automatische detectie van een intranetnetwerk toestaan**|Hiermee wordt de beveiliging geconfigureerd voor intranetsites in Internet Explorer.|Ja|Nee|
|**Beveiligingsniveau voor internet**|Hiermee stelt u het beveiligingsniveau voor internetsites in Internet Explorer in.|Yes|Nee|
|**Beveiligingsniveau voor intranet**|Hiermee stelt u het beveiligingsniveau voor intranetsites in Internet Explorer in.|Yes|Nee|
|**Beveiligingsniveau voor vertrouwde sites**|Hiermee configureert u het beveiligingsniveau voor de zone met vertrouwde sites.|Ja|Nee|
|**Beveiligingsniveau voor websites met beperkte toegang**|Hiermee configureert u het beveiligingsniveau voor de zone met websites met beperkte toegang.|Yes|Nee|
|**Do Not Track-header verzenden**|Hiermee verzendt u een Do Not Track-header naar bezochte websites in Internet Explorer.|Yes|Nee|
|**Toegang tot Bedrijfsmodus-menu toestaan**|Hiermee kunnen gebruikers toegang krijgen tot de menuoptie Ondernemingsmodus van Internet Explorer.<br>Als u deze instelling selecteert, kunt u een **Locatie van het registratierapport** opgeven, die bestaat uit een URL naar een rapport waarin websites worden weergegeven waarvoor gebruikers toegang tot de bedrijfsmodus hebben ingeschakeld.|Yes|Nee|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Hier kunt u de locatie opgeven van de lijst met websites die de bedrijfsmodus gebruiken als deze actief is.|Ja|Nee|

## Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Details|Windows 8.1 en Windows RT 8.1|Windows RT|
|----------------|----------------------------------|--------------|
|**Gegevensroaming toestaan**|Hiermee maakt u dataroaming mogelijk wanneer het apparaat verbinding heeft met een mobiel netwerk.|Yes|Nee|



### Zie ook
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Aug16_HO3-->


