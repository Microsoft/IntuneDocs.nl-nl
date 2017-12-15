---
title: Instellingen voor beveiligingsbeleid voor mobiele apparaten
description: Gebruik Intune voor het configureren van een breed scala aan instellingen die u kunt implementeren op beheerde apparaten in uw organisatie.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e5ab3b76-08af-4893-b294-fb6627fdc4c6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fa86e50ebf7e65be0ce8ace65e2cb0bc7e38658e
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/12/2017
---
# <a name="mobile-device-security-policy-settings-in-microsoft-intune"></a>Instellingen voor beveiligingsbeleid van mobiele apparaten in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

> [!IMPORTANT]
> Microsoft Intune heeft nu afzonderlijke configuratiebeleidsregels voor elk apparaatplatform. Deze beleidsregels bevatten de meest recente instellingen die u kunt gebruiken. U kunt het beveiligingsbeleid voor mobiele apparaten blijven gebruiken en eventuele bestaande implementaties zullen nog steeds werken. U moet echter zo snel mogelijk de migratie naar de nieuwe configuratiebeleidsregels uitvoeren omdat het beveiligingsbeleid voor mobiele apparaten in de toekomst wordt verwijderd.

U kunt het Intune-beveiligingsbeleid voor mobiele apparaten gebruiken voor het configureren van een breed scala aan instellingen die u kunt implementeren op beheerde apparaten in uw organisatie. Deze instellingen worden gebruikt om de functionaliteit en beveiliging van uw apparaten te beheren.

U kunt beveiligingsbeleidsregels voor mobiele apparaten maken en implementeren voor de volgende typen apparaten:

-   Windows RT 8.1 en ingeschreven apparaten met Windows 8.1

-   Windows RT

-   Windows Phone 8 en Windows Phone 8.1

-   iOS

-   Android en Samsung KNOX Standard

> [!NOTE]
> Sommige instellingen zijn niet van toepassing op sommige apparaten. Zie de onderstaande tabellen voor een volledige lijst met instellingen die u kunt configureren.
> Vanaf oktober 2016 biedt Microsoft Intune geen ondersteuning meer voor Windows 8-bedrijfsportal-apps. Microsoft Intune biedt dan ook geen ondersteuning meer voor het Windows Phone 8- en Windows RT-platform. Als gevolg hiervan kunt u geen Windows Phone 8- of Windows RT-apparaten meer registreren of bijwerken. U kunt Windows Phone 8-, Windows RT- en Windows 8-apparaten die al zijn geregistreerd, blijven beheren. Werk Windows 8- en Windows Phone 8-apparaten bij naar Windows 8.1 en Windows Phone 8.1. Gebruik de bijbehorende bedrijfsportal-apps voor Windows 8.1 en Windows Phone 8.1 om zonder onderbrekingen door te gaan met het distribueren van apps naar deze apparaten.

## <a name="security-settings"></a>Beveiligingsinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**|Nee|Nee|Ja|Ja|Ja|
|**Vereist wachtwoordtype**<br /><br />Met deze instelling geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek.|Ja|Ja|Ja|Ja|Nee|
|**Vereist wachtwoordtype – minimumaantal tekensets**<br /><br />Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets moeten worden opgenomen in het wachtwoord. Voor iOS-apparaten geeft u hiermee echter het aantal symbooltekens aan dat moet zijn opgenomen in het wachtwoord.|Ja|Ja|Ja|Ja|Nee|
|**Minimale wachtwoordlengte**|Yes|Ja|Ja|Ja|Ja|
|**Eenvoudige wachtwoorden toestaan**<br /><br />Eenvoudige wachtwoorden zijn onder andere '0000' en '1234'.|Nee|Nee|Ja|Ja|Nee|
|**Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Yes|Ja|Ja|Ja|Yes|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**<sup>1</sup>|Yes|Ja|Ja|Ja|Ja|
|**Dagen tot wachtwoord verloopt**|Yes|Ja|Ja|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Yes|Ja|Ja|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Ja|Ja|Ja|Ja|Ja|
|**Wachtwoordkwaliteit**|Nee|Nee|Nee|Nee|Yes|
|**Afbeeldingswachtwoord en PIN toestaan**|Yes|Ja|Nee|Nee|Nee|
|**Minuten van inactiviteit voordat wachtwoord vereist is**|Nee|Nee|Nee|Ja|Nee|
|**Vingerafdruk voor ontgrendelen toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
<sup>1</sup> Wanneer u voor iOS-apparaten de instellingen **Minuten van inactiviteit voordat het scherm wordt uitgeschakeld** en **Minuten van inactiviteit voordat wachtwoord vereist is** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen instelt op bijvoorbeeld **5** minuten, wordt het scherm na 5 minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens 5 minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat 5 minuten later vergrendeld.

Wanneer u beleid voor de wachtwoordlengte implementeert op apparaten met Windows RT, worden gebruikers gedwongen hun wachtwoord opnieuw in te stellen, zelfs als het huidige wachtwoord voldoet aan de beleidsvereisten.

## <a name="encryption-settings"></a>Versleutelingsinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Versleuteling vereisen op mobiele apparaat**<sup>1</sup><br /><br />Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.<br /><br />Schakel de instelling **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**in om versleuteling van iOS-apparaten in te schakelen.|Ja|Nee|Ja|Nee|Ja|
|**Versleuteling vereisen op opslagkaarten**<br /><br />Deze instelling is ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t. <br />De apps en de bijbehorende gegevens worden automatisch versleuteld.|n.v.t.|Ja|
<sup>1</sup>Dit is aanvullende informatie voor apparaten met Windows 8.1:

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Versleuteling werkt alleen indien het apparaat voldoet aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanuit het Microsoft-account van de gebruiker, waartoe de gebruiker alleen toegang heeft vanuit zijn of haar OneDrive-account. U kunt deze sleutel niet namens een gebruiker herstellen.

## <a name="malware-settings"></a>Instellingen voor malware

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Netwerkfirewall vereisen**|Ja|Nee|Nee|Nee|Nee|
|**SmartScreen inschakelen**|Ja|Nee|Nee|Nee|Nee|

## <a name="system-settings"></a>Systeeminstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Automatische updates vereisen**|Yes|Nee|Nee|Nee|Nee|
|**Automatische updates vereisen: minimale classificatie van updates die automatisch moeten worden geïnstalleerd**<br /><br />Kies de classificatie van updates die automatisch worden geïnstalleerd:<br /><br />- **Belangrijk**. Hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk.<br /><br />- **Aanbevolen**. Hiermee worden alle updates geïnstalleerd die zijn geclassificeerd als belangrijk of aanbevolen.|Yes|Nee|Nee|Nee|Nee|
|**Schermopname toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Yes|Ja (alleen Samsung KNOX Standard)|
|**Beheercentrum in vergrendelingsscherm toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Weergave van meldingen in vergrendelingsscherm toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Weergave van vandaag in vergrendelingsscherm toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Gebruikersaccountbeheer**|Ja|Nee|Nee|Nee|Nee|
|**Verzending van diagnostische gegevens toestaan**|Yes|Nee|Alleen Windows Phone 8.1|Yes|Ja (alleen Samsung KNOX Standard)|
|**Niet-vertrouwde TLS-certificaten toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Persoonlijke portemonneesoftware tijdens vergrendeling toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Fabrieksinstellingen terugzetten toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX Standard)|


## <a name="cloud-settings--documents-and-data"></a>Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Back-up naar iCloud® toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Documentsynchronisatie met iCloud toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Fotostreamsynchronisatie met iCloud toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Versleutelde back-ups vereisen**|Nee|Nee|Nee|Ja|Nee|
|**URL voor werkmappen**<br /><br />Met deze instelling stelt u de URL van de werkmap in, zodat documenten op verschillende apparaten kunnen worden gesynchroniseerd.|Ja|Nee|Nee|Nee|Nee|
|**Google-back-up toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX Standard)|

## <a name="cloud-settings--accounts-and-synchronization"></a>Cloudinstellingen - accounts en synchronisatie

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Microsoft-account toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|
|**Automatisch synchroniseren van Google-account toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX Standard)|

## <a name="email-settings"></a>E-mailinstellingen

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Gebruikers toestaan om e-mailbijlagen te downloaden**<sup>1</sup>|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
|**Synchronisatieperiode e-mail** <br /><br />Deze instelling is ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
|**Mobiele apparaten die deze instellingen niet volledig ondersteunen, mogen synchroniseren met Exchange (Exchange ActiveSync)** <br /><br />Deze instelling is ook van toepassing op apparaten die worden beheerd door Exchange Active Sync.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|n.v.t.|
|**Microsoft-account optioneel maken in de Windows Mail-toepassing**|Yes|Nee|Nee|Nee|Nee|
|**Aangepaste e-mailaccounts toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|

## <a name="application-settings---browser"></a>Toepassingsinstellingen - browser

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Webbrowser toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Yes|Ja (alleen Samsung KNOX Standard)|
|**Automatisch invullen toestaan**|Yes|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Pop-upblokkering toestaan**|Ja|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Cookies toestaan**|Nee|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Invoegtoepassingen toestaan**|Ja|Nee|Nee|Nee|Nee|
|**Active Scripting toestaan**|Yes|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Waarschuwingen voor fraude toestaan**|Yes|Nee|Nee|Ja|Nee|
|**Intranetsite voor invoer van één woord toestaan**<br /><br />(Met deze instelling staat u toe dat er één woord wordt gebruikt om Internet Explorer naar een website te sturen, zoals ‘Bing’.)|Yes|Nee|Nee|Nee|Nee|
|**Automatische detectie van intranetnetwerk toestaan**|Ja|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor internet**|Ja|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor intranet**|Yes|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor vertrouwde sites**|Yes|Nee|Nee|Nee|Nee|
|**Beveiligingsniveau voor sites met beperkte toegang**|Ja|Nee|Nee|Nee|Nee|
|**Niet traceren-header verzenden**|Ja|Nee|Nee|Nee|Nee|
|**Toegang tot Bedrijfsmodus-menu toestaan**|Yes|Nee|Nee|Nee|Nee|
|**Locatie van de lijst met websites van Bedrijfsmodus**|Yes|Nee|Nee|Nee|Nee|

## <a name="application-settings---apps"></a>Toepassingsinstellingen - apps

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Toepassingsarchief toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Yes|Ja (alleen Samsung KNOX Standard)|
|**Wachtwoord vereisen voor toegang tot het toepassingsarchief**|Nee|Nee|Nee|Ja|Nee|
|**Aankopen in app toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Beheerde documenten in andere niet-beheerde apps toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Niet-beheerde documenten in andere beheerde apps toestaan**|Nee|Nee|Nee|iOS 7 en hoger|Nee|
|**Videovergaderingen toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Inhoud voor volwassenen in media store toestaan**|Nee|Nee|Nee|Ja|Nee|
|**App-installatie toestaan**|Nee|Nee|Nee|iOS 6 en hoger|Nee|

## <a name="application-settings---gaming"></a>Toepassingsinstellingen - gaming

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Game Center-vrienden toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Games voor meerdere spelers toestaan**|Nee|Nee|Nee|Ja|Nee|

## <a name="device-capabilities-settings---hardware"></a>Instellingen voor apparaatmogelijkheden - hardware

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Camera toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Ja|Ja|
|**Verwisselbare opslag toestaan**|Nee|Nee|Ja|Nee|Ja (alleen Samsung KNOX Standard)|
|**Wi-Fi toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX Standard)|
|**Wi-Fi-tethering toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX Standard)|
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|
|**Rapportage van Wi-Fi-hotspots toestaan**<br /><br />Met deze instelling kunt u het apparaat toestaan informatie over Wi-Fi-verbindingen te verzenden om verbindingen in de buurt te detecteren.|Nee|Nee|Alleen Windows Phone 8.1|Nee|Nee|
|**Geolocatie toestaan**<br /><br />Met deze instelling kun u het apparaat toestaan locatiegegevens te gebruiken.|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX Standard)|
|**NFC toestaan**<br /><br />Met deze instelling staat u bewerkingen toe waarvoor Near Field Communication wordt gebruikt.|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX Standard)|
|**Bluetooth toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX Standard)|
|**Uitschakelen toestaan**<br>Als deze instelling is uitgeschakeld, werkt de instelling **Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist** voor Samsung KNOX Standard-apparaten niet.|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX Standard)|

## <a name="device-capabilities-settings---cellular"></a>Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Spraakroaming toestaan**|Nee|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Dataroaming toestaan**|Yes|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Automatische synchronisatie tijdens roaming toestaan**|Nee|Nee|Nee|Ja|Nee|
|**Sms-/mms-berichten toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX Standard)|

## <a name="device-capabilities-settings---features"></a>Instellingen voor apparaatmogelijkheden - functies

|Naam van de instelling|Windows 8.1 en Windows RT 8.1|Windows RT|Windows Phone 8 en Windows Phone 8.1|iOS|Android en Samsung KNOX Standard|
|----------------|----------------------------------|--------------|-----------------------------------------|-------|----------------------------|
|**Spraakassistent toestaan**|Nee|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Spraakassistent toestaan terwijl het apparaat is vergrendeld**|Nee|Nee|Nee|Ja|Nee|
|**Nummer inspreken toestaan**|Nee|Nee|Nee|Yes|Ja (alleen Samsung KNOX Standard)|
|**Kopiëren en plakken toestaan**|Nee|Nee|Alleen Windows Phone 8.1|Nee|Ja (alleen Samsung KNOX Standard)|
|**Klembord delen tussen toepassingen toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX Standard)|
|**YouTube toestaan**|Nee|Nee|Nee|Nee|Ja (alleen Samsung KNOX Standard)|

### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
