---
title: Intune-acties en -opties die worden ondersteund bij Apple-gebruikersinschrijving
titleSuffix: Microsoft Intune
description: Meer informatie over Intune-acties en -opties die worden ondersteund bij Apple-gebruikersinschrijving
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/2/2019
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
ms.openlocfilehash: 96c802e76aab673aa6a9108dc0a14f553c26b96b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505417"
---
# <a name="intune-actions-and-options-supported-with-apple-user-enrollment"></a>Intune-acties en -opties die worden ondersteund bij Apple-gebruikersinschrijving

Gebruikersinschrijving ondersteunt een subset van apparaatbeheeropties. Als een bestaand configuratieprofiel wordt toegepast op een gebruikersinschrijvingsapparaat, worden alleen door gebruikersinschrijving ondersteunde instellingen toegepast op dat apparaat.

## <a name="password-settings"></a>Wachtwoordinstellingen

Als u op gebruikersinschrijvingsapparaten een wachtwoordinstelling configureert, worden de instellingen voor **Eenvoudige wachtwoorden** automatisch ingesteld op **Blokkeren** en wordt een 6-cijferige pincode afgedwongen.

U kunt bijvoorbeeld de instelling **Wachtwoord verloopt** configureren en dit beleid pushen naar de door gebruikers ingeschreven apparaten. Op de apparaten gebeurt dan het volgende:
- De instelling **Wachtwoord verloopt** wordt genegeerd.
- Eenvoudige wachtwoorden, zoals `1111` of `1234`, worden niet toegestaan.
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

## <a name="other-supported-options"></a>Andere ondersteunde opties

De volgende opties worden ondersteund in Intune voor apparaten die zijn ingeschreven met Apple-gebruikersinschrijving:
- VPN per app. Safari-domeinen zijn uitgesloten, omdat het configureren van Safari-instellingen niet wordt ondersteund voor gebruikersinschrijving.
- WiFi 
- Verwijdering van zakelijke app na uitschrijving
- App-implementatie via een Volume Purchasing Plan (VPP) voor gebruikerslicenties
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
- SCEP-gebruikersprofielen met Serienummer als de indeling van de onderwerpnaam
- VPN op apparaatniveau.
- Implementatie van VPP-apps met een apparaatlicentie.
- MDM-beheer van toepassingen buiten het beheerde APFS-volume.
- Beveiligingsbeleid voor toepassingen is nog steeds van toepassing op deze apps. U kunt echter niet het beheer overnemen of een beheerde versie van deze apps implementeren, tenzij de gebruiker deze apps van het apparaat verwijdert.
- Acties, configuraties, instellingen en opdrachten waarvoor toezicht is vereist. 

## <a name="next-steps"></a>Volgende stappen

[Gebruikersinschrijving voor iOS en iPadOS instellen](ios-user-enrollment.md)