---
title: Exchange ActiveSync-beleidsinstellingen | Microsoft Docs
description: Configureer met het Exchange ActiveSync-beleid voor Intune de instellingen waarmee u functies en functionaliteit op apparaten kunt beheren die worden beheerd door Exchange ActiveSync.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: f35a6da93e48141489b89e62b37b473d885479cf


---

# <a name="exchange-activesync-policy-settings-in-microsoft-intune"></a>Exchange ActiveSync-beleidsinstellingen in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Configureer met het Microsoft Intune **Exchange ActiveSync-beleid** de instellingen om verschillende functies te regelen op apparaten die worden beheerd door Exchange ActiveSync.


## <a name="password-settings"></a>Wachtwoordinstellingen

|Naam van de instelling|Details
|----------------|---|
|**Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**|Hiermee geeft u aan of apparaten met een wachtwoord moeten worden vergrendeld.<br>(Niet van toepassing op apparaten met Windows RT.)|
|**Vereist wachtwoordtype**|Hiermee geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek.|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimumaantal tekens op dat is vereist in het apparaatwachtwoord.|
|**Eenvoudige wachtwoorden toestaan**|Hiermee geeft u op of eenvoudige wachtwoorden zijn toegestaan, zoals '0000' en '1234'.|
|**Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Hiermee geeft u het aantal keer op dat de gebruiker een onjuist wachtwoord mag invoeren voordat het apparaat wordt gewist.|
|**Dagen tot wachtwoord verloopt**|Hiermee geeft u het aantal dagen op voordat de pincode van het apparaat moet worden gewijzigd.
|**Wachtwoordgeschiedenis onthouden**|Hiermee kunt u het gebruik van eerder gebruikte wachtwoorden wel of niet toestaan.|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden op dat niet opnieuw mag worden gebruikt.|
|**Minuten van inactiviteit voordat wachtwoord vereist is**|Hiermee geeft u op hoelang een apparaat inactief moet zijn voordat het scherm wordt vergrendeld.

## <a name="encryption-settings"></a>Versleutelingsinstellingen

|Naam van de instelling|Details|
|----------------|---|
|**Versleuteling vereisen op mobiele apparaat**<sup>1</sup>|Vereist dat de gegevens op een apparaat moeten worden gecodeerd als dit wordt ondersteund.<br><br>Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.<br /><br />Schakel de instelling **Wachtwoord vereist voor het ontgrendelen van mobiele apparaten** in om versleuteling van iOS-apparaten in te schakelen.|
|**Versleuteling vereisen op opslagkaarten**|Vereist dat gegevens die zijn opgeslagen op externe opslag, zoals een SD-kaart, worden versleuteld (op ondersteunde apparaten).
<sup>1</sup> Aanvullende informatie voor apparaten met Windows 8.1

-   Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](http://support.microsoft.com/kb/3013816) installeren.

-   Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.

-   Als u versleuteling wilt gebruiken op apparaten met Windows 8.1, moeten die voldoen aan de Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) -certificeringsvereisten voor hardware.

-   Wanneer u versleuteling op een apparaat met Windows 8.1 afdwingt, is de herstelsleutel alleen toegankelijk vanaf het Microsoft-account van de gebruiker, dat wordt geopend vanaf het bijbehorende OneDrive-account. U kunt deze sleutel niet namens een gebruiker herstellen.

## <a name="email-settings"></a>E-mailinstellingen

|Naam van de instelling|Details
|----------------|---|
|**Gebruikers toestaan e-mailbijlagen te downloaden**|Hiermee geeft u op of e-mailbijlagen kunnen worden gedownload naar het apparaat.|
|**Synchronisatieperiode e-mail**|Geeft het aantal dagen aan ontvangen e-mail op dat met het apparaat wordt gesynchroniseerd.
|**Mobiele apparaten die Exchange ActiveSync-instellingen niet volledig ondersteunen, toestaan om te synchroniseren met Exchange**|Hiermee kunt u toegang tot Exchange toestaan op apparaten die een of meer Exchange ActiveSync-instellingen niet ondersteunen.

## <a name="browser-settings"></a>Browserinstellingen

|Naam van de instelling|Details
|----------------|---|
|**Webbrowser toestaan**|Hiermee geeft u op of de webbrowser op het apparaat kan worden gebruikt.<br>(Niet beschikbaar voor Windows RT en Windows Phone.)

## <a name="hardware-settings"></a>Hardware-instellingen

|Naam van de instelling|Details
|----------------|---|
|**Camera toestaan**|Hiermee geeft u op of de camera op het apparaat kan worden gebruikt.<br>(Niet beschikbaar voor Windows RT en Windows Phone.)



### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Dec16_HO5-->


