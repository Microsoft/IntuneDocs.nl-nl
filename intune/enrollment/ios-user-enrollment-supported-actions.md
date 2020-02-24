---
title: Intune-acties en -opties die worden ondersteund bij Apple-gebruikersinschrijving
titleSuffix: Microsoft Intune
description: Meer informatie over Intune-acties en -opties die worden ondersteund bij Apple-gebruikersinschrijving
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 2/14/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: tisilver
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9c6fb7da3a791d369fc3005367ee7670af8bc63e
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/17/2020
ms.locfileid: "77414135"
---
# <a name="intune-actions-and-options-supported-with-apple-user-enrollment"></a>Intune-acties en -opties die worden ondersteund bij Apple-gebruikersinschrijving

Gebruikersinschrijving ondersteunt een subset van apparaatbeheeropties. Als een bestaand configuratieprofiel wordt toegepast op een gebruikersinschrijvingsapparaat, worden alleen door gebruikersinschrijving ondersteunde instellingen toegepast op dat apparaat.

> [!NOTE]
> Ondersteuning voor het proces van Apple voor gebruikersinschrijving in Intune is momenteel als preview-versie beschikbaar voor iOS en iPadOS.

## <a name="password-settings"></a>Wachtwoordinstellingen

Als u op gebruikersinschrijvingsapparaten een wachtwoordinstelling configureert, worden de instellingen voor **Eenvoudige wachtwoorden** automatisch ingesteld op **Blokkeren** en wordt een 6-cijferige pincode afgedwongen.

U kunt bijvoorbeeld de instelling **Wachtwoord verloopt** configureren en dit beleid pushen naar de door gebruikers ingeschreven apparaten. Op de apparaten gebeurt dan het volgende:
- De instelling **Wachtwoord verloopt** wordt genegeerd.
- Eenvoudige wachtwoorden, zoals `111111` of `123456`, worden niet toegestaan.
- Er wordt een 6-cijferige pincode afgedwongen.

## <a name="administrator-remote-device-actions-and-options"></a>Acties en opties voor beheerders van externe apparaten
Beheerders kunnen de volgende acties en opties uitvoeren op gebruikersinschrijvingsapparaten:
- Buiten gebruik stellen
- Verwijderen
- Vergrendelen op afstand
- Synchroniseren

Alle andere acties worden niet ondersteund.

## <a name="end-user-actions"></a>Acties voor eindgebruikers
Eindgebruikers kunnen de volgende acties op hun ingeschreven apparaten uitvoeren via de toepassing en website van de bedrijfsportal:
- Naam wijzigen. Deze actie is alleen van toepassing op de gebruikersgerichte naam binnen de bedrijfsportal. De naam van het apparaat buiten die context wordt niet gewijzigd.
- Verwijderen
- Vergrendelen op afstand
- Status controleren

## <a name="app-deployment-options"></a>App-implementatieopties
De volgende app-typen kunnen worden geïmplementeerd op gebruikersinschrijvingsapparaten:
- Apps met Volume Purchasing Plan (VPP) voor gebruikerslicenties, met inbegrip van aangepaste apps
- Line-Of-Business (LOB)-apps
- Web-apps

## <a name="other-supported-options"></a>Andere ondersteunde opties

De volgende opties worden ondersteund in Intune voor apparaten die zijn ingeschreven met Apple-gebruikersinschrijving:
- VPN per app. Safari-domeinen zijn uitgesloten, omdat het configureren van Safari-instellingen niet wordt ondersteund voor gebruikersinschrijving.
- WiFi 
- Verwijdering van zakelijke app na uitschrijving
- Jailbreakdetectie

De volgende beperkingen worden ondersteund:
- Zakelijke documenten weergeven in niet-beheerde apps
- Niet-zakelijke documenten weergeven in zakelijke apps
- Toestaan dat niet-beheerde apps contactpersonen lezen in beheerde accounts voor contactpersonen
- AirDrop behandelen als een onbeheerd doel
- Versleutelde back-ups vereisen
- Beheerde apps synchroniseren met de cloud
- Toegang tot Beheercentrum wanneer het apparaat is vergrendeld
- Toegang tot Meldingencentrum wanneer het apparaat is vergrendeld
- De weergave Vandaag wanneer het apparaat is vergrendeld
- Schermafbeeldingen blokkeren
- Back-ups van Enterprise Book blokkeren
- Synchronisatie van metagegevens van Enterprise Book blokkeren
- Versleutelde back-ups vereisen
- Polsdetectie voor horloge vereisen
- Siri blokkeren
- Siri blokkeren wanneer het apparaat is vergrendeld
- Fraudewaarschuwingen van Safari vereisen
- Verzending van diagnostische gegevens naar Apple blokkeren


## <a name="options-not-supported"></a>Niet-ondersteunde opties
De volgende opties worden niet ondersteund op apparaten die zijn ingeschreven via gebruikersinschrijving. Als u deze opties nodig hebt, raadpleegt u de procedure voor inschrijving van apparaten in persoonlijk eigendom of de procedure voor automatische inschrijving van zakelijke apparaten.
- Inventaris verzamelen van apps buiten het beheerde APFS-volume.
- Inventaris verzamelen van certificaten en inrichtingsprofielen buiten het beheerde APFS-volume.
- UDID en andere permanente apparaat-id's verzamelen.
- Gebruikersinschrijving ondersteunt een unieke inschrijvings-id voor elk ingeschreven apparaat, maar deze id blijft niet behouden na uitschrijving.
- De volgende Intune-functies worden niet ondersteund vanwege deze beperking:
- SCEP-gebruikersprofielen met Serienummer als de indeling van de onderwerpnaam.
- VPN op apparaatniveau.
- Implementatie van VPP-apps met een apparaatlicentie.
- App Store-apps als beheerde apps installeren.
- MDM-beheer van toepassingen buiten het beheerde APFS-volume.
- Beveiligingsbeleid voor toepassingen is nog steeds van toepassing op deze apps. U kunt echter niet het beheer overnemen of een beheerde versie van deze apps implementeren, tenzij de gebruiker deze apps van het apparaat verwijdert.
- Acties, configuraties, instellingen en opdrachten waarvoor toezicht is vereist. 


## <a name="known-issues-in-preview"></a>Bekende problemen in Preview
- Intrekken van VPP-licentie: Er wordt geen melding weergegeven dat de licentie is ingetrokken. Het huidige gedrag is dat de intrekking slaagt, maar de eindgebruiker niet op de hoogte wordt gesteld. 
- Rapportage van VPP-toepassingen: In het rapport op Client-apps> Apps> [App-naam]> Installatiestatus van apparaat, wordt VPP-toepassingen die op door gebruikers ingeschreven apparaten zijn geïmplementeerd, gerapporteerd als 'mislukt', zelfs wanneer de toepassing met succes op het apparaat is geïmplementeerd. 
- Toepassingsrapportage: Voor app-typen die niet worden ondersteund door Gebruikersregistratie, kunnen rapporten irrelevante foutberichten bevatten. 
- Bedrijfsportal-app: Gebruikers zien alle toepassingen die op hen zijn gericht, ongeacht of die toepassingstypen worden ondersteund voor door de gebruiker ingeschreven apparaten. 
- Bedrijfsportal-app: Gebruikers zien dezelfde tekst die aangeeft wat organisaties kunnen zien voor de inschrijving van gebruikers en apparaten als de beheerder de tekst heeft aangepast die aangeeft wat organisaties niet kunnen zien.


## <a name="next-steps"></a>Volgende stappen

[Gebruikersinschrijving voor iOS/iPadOS en iPadOS instellen](ios-user-enrollment.md)
