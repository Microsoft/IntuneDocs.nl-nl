---
title: Windows-beleidsinstellingen
description: Gebruik de algemene regels voor het Intune Windows-configuratiebeleid (Windows 8.1 en later) om instellingen te configureren voor geregistreerde Windows 8.1- en Windows 8-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab39a1847dbba495b4946d12b96b6f8c724f38d8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="windows-policy-settings-in-microsoft-intune"></a>Windows-beleidsinstellingen in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Gebruik het **algemene Windows-configuratiebeleid (Windows 8.1 en hoger)** om de volgende instellingen te configureren voor geregistreerde Windows 8-, Windows 8.1- en Windows RT 8.1-apparaten:

## <a name="applicability-settings"></a>Toepasselijkheidsinstellingen

|Naam van de instelling|Details|
|----------------|----------------------------------|
|**Alle configuraties toepassen op Windows 10**|Hiermee worden de instellingen in dit beleid behalve op Windows 8- en Windows 8.1-apparaten, ook op Windows 10-apparaten toegepast.|

## <a name="security-settings"></a>Beveiligingsinstellingen

|Naam van de instelling|Details|
|----------------|------|
|**Vereist wachtwoordtype**|Hiermee geeft u het wachtwoordtype op dat is vereist, zoals alfanumeriek of alleen numeriek.|
|**Vereist wachtwoordtype – minimumaantal tekensets**|Hiermee geeft u op hoeveel verschillende tekensets er moeten worden opgenomen in het wachtwoord. Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Voor iOS-apparaten geeft u met deze instelling echter het aantal symbolen op dat moet worden opgenomen in het wachtwoord.|
|**Minimale wachtwoordlengte**|Hiermee configureert u de minimaal vereiste lengte (in tekens) voor het wachtwoord.|
|**Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Hiermee wist u het apparaat als er meer mislukte aanmeldingspogingen zijn gedaan dan het toegestane aantal pogingen.|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u het aantal minuten op dat een apparaat inactief moet zijn voordat er een wachtwoord is vereist om het apparaat te ontgrendelen.|
|**Dagen tot wachtwoord verloopt**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u op of de gebruiker eerder gebruikte wachtwoorden kan configureren.|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat door het apparaat wordt onthouden.|
|**Afbeeldingswachtwoord en PIN toestaan**|Hiermee maakt u het gebruik van een afbeeldingswachtwoord en pincode mogelijk. Met een afbeeldingswachtwoord kan de gebruiker zich aanmelden met aanraakbewegingen op een afbeelding. Met een pincode kunnen gebruikers zich snel met een code van 4 cijfers aanmelden.|

## <a name="encryption-settings"></a>Versleutelingsinstellingen

|Naam van de instelling|Details|
|----------------|-----|
|**Versleuteling vereisen op mobiele apparaat**<sup>1</sup>|Vereist dat bestanden op het apparaat zijn versleuteld.|
<sup>1</sup> Aanvullende informatie voor apparaten met Windows 8.1

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Versleuteling werkt alleen indien het apparaat voldoet aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanuit het Microsoft-account van de gebruiker, waartoe de gebruiker alleen toegang heeft vanuit zijn of haar OneDrive-account. U kunt deze sleutel niet namens een gebruiker herstellen.

## <a name="malware-settings"></a>Instellingen voor malware

|Naam van de instelling|Details|
|----------------|-----|
|**Netwerkfirewall vereisen**|Hiermee vereist u dat Windows Firewall is ingeschakeld.|
|**SmartScreen inschakelen**|Hiermee vereist u het gebruik van Windows SmartScreen.|

## <a name="system-settings"></a>Systeeminstellingen

|Naam van de instelling|Details|
|----------------|-------|
|**Automatische updates vereisen**|Hiermee schakelt u de instelling voor automatische updates op apparaten in.|
|**Automatische updates vereisen: minimale classificatie van updates die automatisch moeten worden geïnstalleerd**|Hiermee kiest u de classificatie van updates die automatisch worden geïnstalleerd:<br /><br />-   **Belangrijk:** hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk.<br />-   **Aanbevolen:** hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk of aanbevolen.|
|**Gebruikersaccountbeheer**|Hiermee vereist u het gebruik van Gebruikersaccountbeheer (UAC) op apparaten.|
|**Verzending van diagnostische gegevens toestaan**|Hiermee stelt u het apparaat in staat diagnostische gegevens naar Microsoft te verzenden.|


## <a name="cloud-settings--documents-and-data"></a>Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Details|
|----------------|------|
|**URL voor werkmappen**|Hiermee stelt u de URL van de werkmap in, zodat documenten op verschillende apparaten kunnen worden gesynchroniseerd.|

## <a name="email-settings"></a>E-mailinstellingen

|Naam van de instelling|Details|
|----------------|-----|
|**Microsoft-account optioneel maken in de Windows Mail-toepassing**|Hiermee maakt u het mogelijk om toegang te krijgen tot de toepassing Windows Mail zonder Microsoft-account.|

## <a name="application-settings---browser"></a>Toepassingsinstellingen - browser

|Naam van de instelling|Details|
|----------------|-----|
|**Automatisch invullen toestaan**|Hiermee stelt u gebruikers in staat instellingen voor automatisch aanvullen in de browser te wijzigen.|
|**Pop-upblokkering toestaan**|Hiermee schakelt u de pop-upblokkering voor browsers in of uit.|
|**Invoegtoepassingen toestaan**|Hiermee stelt u gebruikers in staat invoegtoepassingen toe te voegen aan Internet Explorer.|
|**Active Scripting toestaan**|Hiermee stelt u de browser in staat scripts, zoals Active X-scripts, uit te voeren.|
|**Waarschuwingen voor fraude toestaan**|Hiermee schakelt u de waarschuwingen voor mogelijke frauduleuze websites in of uit.|
|**Intranetsite voor invoer van één woord toestaan**|Hiermee stelt u gebruikers in staat om Internet Explorer naar een website te sturen met één woord, zoals Bing.|
|**Automatische detectie van intranetnetwerk toestaan**|Hiermee wordt de beveiliging geconfigureerd voor intranetsites in Internet Explorer.|
|**Beveiligingsniveau voor internet**|Hiermee stelt u het beveiligingsniveau voor internetsites in Internet Explorer in.|
|**Beveiligingsniveau voor intranet**|Hiermee stelt u het beveiligingsniveau voor intranetsites in Internet Explorer in.|
|**Beveiligingsniveau voor vertrouwde sites**|Hiermee configureert u het beveiligingsniveau voor de zone met vertrouwde sites.|
|**Beveiligingsniveau voor sites met beperkte toegang**|Hiermee configureert u het beveiligingsniveau voor de zone met websites met beperkte toegang.|
|**Niet traceren-header verzenden**|Hiermee verzendt u een Do Not Track-header naar bezochte websites in Internet Explorer.|
|**Toegang tot Bedrijfsmodus-menu toestaan**|Hiermee kunnen gebruikers toegang krijgen tot de menuoptie Ondernemingsmodus van Internet Explorer.<br>Als u deze instelling selecteert, kunt u een **Locatie van het registratierapport** opgeven, die bestaat uit een URL naar een rapport waarin websites worden weergegeven waarvoor gebruikers toegang tot de bedrijfsmodus hebben ingeschakeld.|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Hier kunt u de locatie opgeven van de lijst met websites die de bedrijfsmodus gebruiken als deze actief is.|

## <a name="device-capabilities-settings---cellular"></a>Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Details|
|----------------|----|
|**Dataroaming toestaan**|Hiermee maakt u dataroaming mogelijk wanneer het apparaat verbinding heeft met een mobiel netwerk.|



### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
