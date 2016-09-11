---
title: Apparaten buiten gebruik stellen | Microsoft Intune
description: Intune biedt ondersteuning voor selectief wissen en volledig wissen waarmee apparaten uit het Intune-beheer kunnen worden verwijderd door hun beleid en de bedrijfsportal te verwijderen.
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cf471320f122eea7804ff6cd6cad208f8cd5a692
ms.openlocfilehash: 29d13dcbc367c18d64f9522fa9a3b962226feebb


---

# Apparaten buiten gebruik stellen vanuit Intune-beheer

Of apparaten nu eigendom zijn van het bedrijf of van gebruikers persoonlijk, er komt een moment waarop een beheerd apparaat buiten gebruik moet worden gesteld en moet worden verwijderd uit Intune-beheer. Er kunnen verschillende redenen zijn voor het buiten gebruik stellen van een apparaat:

-   Een gebruiker verlaat een bedrijf op de geplande wijze ('beheerd' vertrek)
-   Een gebruiker vertrekt abrupt (wordt ontslagen, neemt ontslag, etc.).
-   Verlies van apparaat
-   Een apparaat opnieuw inzetten (aan een andere gebruiker geven, voor een nieuw doel inzetten, etc.)

U kunt apparaten die worden beheerd als mobiele apparaten selectief wissen of volledig wissen, of de apparaten vergrendelen en het wachtwoord wijzigen. Wanneer het apparaat wordt gewist, komt het abonnement van de gebruiker vrij en kan het op een ander apparaat worden gebruikt. U kunt ook pc’s buiten gebruik stellen die worden beheerd met de Intune-clientsoftware.

## Gegevens en apps op apparaten wissen
Zowel het selectief wissen als het volledig wissen van een apparaat zorgt ervoor dat het apparaat uit Intune-beheer wordt verwijderd doordat hun beleid en de bedrijfsportal worden verwijderd. Dit houdt in dat het apparaat niet meer de referenties heeft die voor aanmelding bij bedrijfsbronnen nodig zijn, zoals Microsoft SharePoint, e-mail en Office 365.

[Selectief wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) is de aanbevolen actie voor werknemers die hun eigen apparaten in Intune hebben ingeschreven, omdat dit geen invloed heeft op de persoonlijke gegevens op het apparaat. Alleen zakelijke gegevens worden verwijderd.

Voor apparaten die een nieuwe bestemming krijgen, kunt u ook voor [volledig wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) kiezen. Hiermee worden de fabrieksinstellingen van het apparaat teruggezet.

## U kunt als volgt apparaten verwijderen in de Azure Active Directory-portal:

1.  Meld u aan met de referenties van uw organisatie op [http://aka.ms/accessaad](http://aka.ms/accessaad) of [https://portal.office.com](https://portal.office.com) en kies vervolgens **Beheercentrums** &gt; **Azure AD**.

2.  Een Azure-abonnement maken als u er nog geen hebt. U kunt dit zonder creditcard of betaling doen als u beschikt over een betaald account (kies de abonnementskoppeling **Uw gratis Azure Active Directory registreren**).

4.  Selecteer **Active Directory** en vervolgens uw organisatie.

5.  Selecteer het tabblad **Gebruikers** .

6.  Selecteer de gebruiker waarvoor u de apparaten wilt verwijderen.

7.  Kies **Apparaten**.

8.  Selecteer de gewenste apparaten en kies **Apparaat verwijderen**. Het apparaat wordt verwijderd bij de volgende synchronisatie met Active Directory. Dit gebeurt gewoonlijk binnen vier uur. Na het synchroniseren wordt het apparaat uit beheer verwijderd. Hiermee verwijdert u één apparaat van de apparaatlimiet voor deze gebruiker.

## Beheerde computers buiten gebruik stellen
Computers die worden beheerd met Intune-clientsoftware, kunnen worden verwijderd uit het beheer van de Intune-beheerconsole. In dit geval worden ook de clientsoftware en het Intune-beleid van de computer verwijderd. Raadpleeg de informatie over [het buiten gebruik stellen van computers die worden beheerd door de Intune-clientsoftware](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#retire-a-computer.md).

## Toegang blokkeren tot een apparaat
Als een apparaat verloren raakt of u het buiten gebruik wilt stellen omdat een medewerker het bedrijf heeft verlaten zonder het apparaat terug te geven, kunt u ook [de wachtwoordcode opnieuw instellen en het apparaat op afstand vergrendelen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Zo voorkomt u dat bedrijfsgegevens worden misbruikt. Mogelijk moet u het apparaat echter wel afschrijven.

U moet ook de licentie van het Intune-account van de werknemer intrekken. Hiermee maakt u de licentie vrij en kunt u deze toewijzen aan een nieuw gebruikersaccount.

## Hardware buiten gebruik stellen
Het kan ook zo zijn dat het apparaat het einde van de levensduur heeft bereikt. In dergelijke gevallen kunt u de [fabrieksinstellingen van het apparaat terugzetten](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). Alle gegevens worden dan gewist en het apparaat wordt uit Intune verwijderd. Vervolgens kunt de hardware volgens het beleid van uw bedrijf afvoeren.

### Zie tevens
[Uw gegevens beschermen met volledig wissen of selectief wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Aug16_HO4-->


