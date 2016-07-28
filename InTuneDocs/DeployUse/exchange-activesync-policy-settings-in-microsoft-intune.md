---
title: Exchange ActiveSync-beleidsinstellingen | Microsoft Intune
description: Configureer met het Exchange ActiveSync-beleid voor Intune de instellingen waarmee u functies en functionaliteit op apparaten kunt beheren die worden beheerd door Exchange ActiveSync.
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 7cdb34c469d2932deb10deec592a899b9848226a


---

# Exchange ActiveSync-beleidsinstellingen in Microsoft Intune
Configureer met het Microsoft Intune **Exchange ActiveSync-beleid** de instellingen waarmee u verschillende functies regelt op apparaten die worden beheerd door Exchange ActiveSync.


## Wachtwoordinstellingen

|Naam van de instelling|Details
|----------------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Hiermee geeft u aan of apparaten met een wachtwoord moeten worden vergrendeld.<br>(Niet van toepassing op apparaten met Windows RT.)|
|**Vereist wachtwoordtype**|Hiermee geeft u het type wachtwoord op dat vereist is, zoals alleen numeriek of alfanumeriek.|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimumaantal tekens op dat vereist is in het apparaatwachtwoord.|
|**Eenvoudige wachtwoorden toestaan**|Eenvoudige wachtwoorden zijn onder andere '0000' en '1234'.|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Toestaan dat dit aantal pogingen wordt gedaan voor het invoeren van het juiste wachtwoord voordat het apparaat wordt gewist.|
|**Wachtwoordverlooptijd (dagen)**|Hiermee geeft u het aantal dagen op voordat de pincode van het apparaat moet worden gewijzigd.
|**Wachtwoordgeschiedenis onthouden**|Hiermee kunt u het gebruik van eerder gebruikte wachtwoorden wel of niet toestaan.|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw mag worden gebruikt.|
|**Minuten inactief voordat wachtwoord is vereist**|Hiermee geeft u de hoeveelheid tijd op die een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.

## Versleutelingsinstellingen

|Naam van de instelling|Details|
|----------------|
|**Versleuteling vereisen voor mobiel apparaat**<sup>1</sup>|Vereist dat de gegevens op het apparaat moeten worden gecodeerd als dit wordt ondersteund.<br>Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.<br /><br />Schakel de instelling **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**in om versleuteling van iOS-apparaten in te schakelen.|
|**Versleuteling vereisen voor opslagkaarten**|Vereist dat gegevens opgeslagen in een externe opslag, zoals een SD-kaart, worden versleuteld (op ondersteunde apparaten).
<sup>1</sup> Aanvullende informatie voor apparaten met Windows 8.1

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Versleuteling werkt alleen indien het apparaat voldoet aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanaf het Microsoft-account van de gebruiker, wanneer deze sleutel vanaf het bijbehorende OneDrive-account wordt geopend. U kunt deze sleutel niet namens een gebruiker herstellen.

## E-mailinstellingen

|Naam van de instelling|Details
|----------------|
|**Gebruikers toestaan e-mailbijlagen te downloaden**|Hiermee geeft u op of e-mailbijlagen kunnen worden gedownload naar het apparaat.|
|**E-mailsynchronisatieperiode**|Selecteer het aantal dagen aan ontvangen e-mail dat met het apparaat wordt gesynchroniseerd.
|**Mobiele apparaten die Exchange ActiveSync-instellingen niet volledig ondersteunen, toestaan om te synchroniseren met Exchange**|Hiermee kunt u toegang tot Exchange toestaan op apparaten die een of meer Exchange ActiveSync-instellingen niet ondersteunen.

## Browserinstellingen

|Naam van de instelling|Details
|----------------|-
|**Webbrowser toestaan**|Hiermee geeft u op of de webbrowser op het apparaat kan worden gebruikt.<br>(Niet beschikbaar voor Windows RT en Windows Phone.)

## Hardware-instellingen

|Naam van de instelling|Details
|----------------|
|**Camera toestaan**|Hiermee geeft u op of de camera op het apparaat kan worden gebruikt.<br>(Niet beschikbaar voor Windows RT en Windows Phone.)



### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jul16_HO3-->


