---
title: Microsoft Intune-apparaatbeperkingsinstellingen voor apparaten met Windows 8.1
titleSuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op apparaten met Windows 8.1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a2b1b9a41c86caa14683a86212bba7570e36d102
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566179"
---
# <a name="microsoft-intune-windows-81-and-later-device-restriction-settings"></a>Apparaatbeperkingsinstellingen voor Windows 8.1-apparaten (en hoger) in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met Windows 8.1 en hoger.


## <a name="general"></a>Algemeen

-   **Verzending van diagnostische gegevens**: hiermee stelt u het apparaat in staat diagnostische gegevens naar Microsoft te verzenden.
-   **Firewall**: hiermee vereist u dat Windows Firewall is ingeschakeld.
-   **Gebruikersaccountbeheer**: hiermee vereist u het gebruik van Gebruikersaccountbeheer (UAC) op apparaten.

## <a name="password"></a>Wachtwoord
-   **Vereist wachtwoordtype**: hiermee stelt u in dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
-   **Minimale wachtwoordlengte**: hiermee configureert u de minimaal vereiste lengte (in tekens) voor het wachtwoord op apparaten.
-   **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee wist u het apparaat als er meer mislukte aanmeldingspogingen zijn gedaan dan het toegestane aantal pogingen.
-   **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u het aantal minuten op dat een apparaat inactief moet zijn voordat een wachtwoord is vereist om het apparaat te ontgrendelen.
-   **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.
-   **Wachtwoorden niet opnieuw gebruiken**: hiermee geeft u op of de gebruiker eerder gebruikte wachtwoorden kan configureren.
-   **Afbeeldingswachtwoord en pincode**: hiermee kunt u het gebruik van een afbeeldingswachtwoord en pincode mogelijk maken. Met een afbeeldingswachtwoord kan de gebruiker zich aanmelden met aanraakbewegingen op een afbeelding. Met een pincode kunnen gebruikers zich snel met een code van 4 cijfers aanmelden.
-   **Versleuteling**: hiermee geeft u aan dat bestanden op het apparaat moeten worden versleuteld.<br>Als u versleuteling wilt afdwingen op apparaten met Windows 8.1, moet u op elk apparaat de [December 2014 MDM-clientupdate voor Windows](https://support.microsoft.com/kb/3013816) installeren.
Als u deze instelling voor Windows 8.1-apparaten inschakelt, moeten alle gebruikers van het apparaat een Microsoft-account hebben.
Versleuteling werkt alleen indien het apparaat voldoet aan de [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97)-certificeringsvereisten voor hardware.
Wanneer u versleuteling op een apparaat afdwingt, is de herstelsleutel alleen toegankelijk vanuit het Microsoft-account van de gebruiker, waartoe de gebruiker alleen toegang heeft vanuit zijn of haar OneDrive-account. U kunt deze sleutel niet namens een gebruiker herstellen.     



## <a name="browser"></a>Browser
-   **Automatisch doorvoeren**: hiermee kunt u gebruikers in staat stellen instellingen voor automatisch aanvullen in de browser te wijzigen.
-   **Waarschuwingen voor fraude**: hiermee schakelt u de waarschuwingen voor mogelijke frauduleuze websites in of uit.
-   **SmartScreen**: hiermee schakelt u de waarschuwingen voor mogelijke frauduleuze websites in of uit.
-   **JavaScript**: hiermee staat u de uitvoering van scripts, zoals Java-scripts, toe in de browser.
-   **Pop-ups**: hiermee schakelt u de pop-upblokkering voor browsers in of uit.
-   **Do Not Track-headers verzenden**: hiermee verzendt u een Do Not Track-header naar bezochte websites in Internet Explorer.
-   **Invoegtoepassingen**: hiermee stelt u gebruikers in staat invoegtoepassingen toe te voegen aan Internet Explorer.
-   **Invoer van één woord op de intranetsite**: hiermee stelt u gebruikers in staat Internet Explorer naar een website te sturen met één woord, zoals Bing.
-   **Intranetsite automatisch detecteren**: hiermee configureert u de beveiliging voor intranetsites in Internet Explorer.
-   **Internetbeveiligingsniveau**: hiermee stelt u het beveiligingsniveau voor internetsites in Internet Explorer in.
-   **Intranetbeveiligingsniveau**: hiermee stelt u het beveiligingsniveau voor intranetsites in Internet Explorer in.
-   **Beveiligingsniveau van vertrouwde websites**: hiermee configureert u het beveiligingsniveau voor de zone met vertrouwde sites.
-   **Hoge beveiliging voor beperkte sites**: hiermee configureert u het beveiligingsniveau voor de zone met vertrouwde sites.
-   **Toegang tot Bedrijfsmodus via menu**: hiermee kunnen gebruikers toegang krijgen tot de menuoptie Bedrijfsmodus van Internet Explorer.
Als u deze instelling selecteert, kunt u een **Locatie van het registratierapport** opgeven, die bestaat uit een URL naar een rapport waarin websites worden weergegeven waarvoor gebruikers toegang tot de bedrijfsmodus hebben ingeschakeld.
-   **Locatie van de lijst met websites van Bedrijfsmodus**: hiermee geeft u de locatie op van de lijst met websites die Bedrijfsmodus gebruikt als deze actief is.

## <a name="cellular"></a>Mobiel
-   **Dataroaming**: hiermee schakelt u dataroaming in wanneer het apparaat verbinding heeft met een mobiel netwerk.

## <a name="cloud-and-storage"></a>Cloud en opslag
-   **URL voor Werkmappen**: hiermee stelt u de URL voor Werkmappen in, zodat documenten op verschillende apparaten kunnen worden gesynchroniseerd.
-   **Toegang tot de Windows Mail-app zonder Microsoft-account**: hiermee maakt u het mogelijk om toegang te krijgen tot de toepassing Windows Mail zonder Microsoft-account.    
