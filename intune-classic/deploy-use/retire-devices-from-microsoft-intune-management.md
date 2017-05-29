---
title: Apparaten buiten gebruik stellen | Microsoft Docs
description: Intune biedt ondersteuning voor selectief wissen en volledig wissen waarmee apparaten uit het Intune-beheer kunnen worden verwijderd door hun beleid en de bedrijfsportal te verwijderen.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 88a18975049158ca632d51796e8b4022c42dff94
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="retire-devices-from-intune-management"></a>Apparaten buiten gebruik stellen vanuit Intune-beheer

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Of apparaten nu eigendom zijn van het bedrijf of van gebruikers persoonlijk, er komt een moment waarop een beheerd apparaat moet worden verwijderd uit Intune-beheer.

Apparaten worden nooit uit Intune verwijderd zonder uw tussenkomst, zelfs als de apparaten een bepaalde tijd niet met de Intune-service zijn verbonden.

Er kunnen verschillende redenen zijn voor het buiten gebruik stellen van een apparaat:

-    Een gebruiker verlaat een bedrijf op de geplande wijze ('beheerd' vertrek)
-    Een gebruiker vertrekt abrupt (wordt ontslagen, neemt ontslag, etc.).
-    Verlies van apparaat
-    Een apparaat opnieuw inzetten (aan een andere gebruiker geven, voor een nieuw doel inzetten, enz.)

U kunt apparaten die worden beheerd als mobiele apparaten selectief wissen of volledig wissen, of de apparaten vergrendelen en het wachtwoord wijzigen. Als u het apparaat wist, komt het abonnement van de gebruiker vrij en kan het op een ander apparaat worden gebruikt. U kunt ook pc’s buiten gebruik stellen die worden beheerd met de Intune-clientsoftware.

## <a name="wipe-data-and-apps-from-devices"></a>Gegevens en apps op apparaten wissen
Met zowel selectief wissen als volledig wissen wordt het apparaat uit het Intune-beheer verwijderd, door het beleid en de bedrijfsportal te verwijderen. Als gevolg daarvan heeft het apparaat niet langer de vereiste referenties voor het aanmelden bij bedrijfsbronnen zoals Microsoft SharePoint, e-mail of Office 365.

[Selectief wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) is de aanbevolen actie voor werknemers die hun eigen apparaten in Intune hebben ingeschreven, omdat dit geen invloed heeft op de persoonlijke gegevens op het apparaat. Alleen zakelijke gegevens worden verwijderd.

Voor apparaten die een nieuwe bestemming krijgen, kunt u ook voor [volledig wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) kiezen. Hiermee worden de fabrieksinstellingen van het apparaat teruggezet.

### <a name="removing-user-licenses-and-managed-devices"></a>Gebruikerslicenties en beheerde apparaten verwijderen
Wanneer u een gebruikerslicentie verwijdert, zijn de ingeschreven apparaten van de gebruiker niet langer ingeschreven. Als een best practice moet u selectief wissen om bedrijfsgegevens te verwijderen van beheerde apparaten voordat u de Intune-licentie voor een gebruiker verwijdert. Nadat u de gebruikerslicentie verwijdert, kunnen er geen externe acties meer op het apparaat worden uitgevoerd.

## <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>U kunt als volgt apparaten verwijderen in de Azure Active Directory-portal:

1.  Meld u aan met de referenties van uw organisatie op [http://aka.ms/accessaad](http://aka.ms/accessaad) of [https://portal.office.com](https://portal.office.com) en kies vervolgens **Beheercentrums** &gt; **Azure AD**.

2.  Maak een Azure-abonnement maken als u er nog geen hebt. Als u een betaalde account hebt, is hiervoor geen creditcard of betaling nodig. Kies de abonnementskoppeling **Uw gratis Azure Active Directory registreren**.

4.  Kies **Active Directory** en vervolgens uw organisatie.

5.  Kies het tabblad **Gebruikers** .

6.  Kies de gebruiker waarvoor u de apparaten wilt verwijderen.

7.  Kies **Apparaten**.

8.  Kies de gewenste apparaten en kies vervolgens **Apparaat verwijderen**. Het apparaat wordt verwijderd bij de volgende synchronisatie met Active Directory. Dit gebeurt gewoonlijk binnen vier uur. Na het synchroniseren wordt het apparaat uit beheer verwijderd. Hiermee verwijdert u één apparaat van de apparaatlimiet voor deze gebruiker.

## <a name="retire-managed-computers"></a>Beheerde computers buiten gebruik stellen
Computers die worden beheerd met Intune-clientsoftware, kunnen in de Intune-beheerconsole worden verwijderd uit het beheer. In dit geval worden ook de clientsoftware en het Intune-beleid van de computer verwijderd. Raadpleeg de informatie over [het buiten gebruik stellen van computers die worden beheerd door de Intune-clientsoftware](retire-a-windows-pc-with-microsoft-intune.md).

## <a name="block-access-a-device"></a>Toegang blokkeren tot een apparaat
Als een apparaat is kwijtgeraakt, of u het buiten gebruik wilt stellen omdat een medewerker het bedrijf heeft verlaten zonder het apparaat terug te geven, kunt u ook [de wachtwoordcode opnieuw instellen en het apparaat op afstand vergrendelen](use-remote-lock-and-passcode-reset-in-microsoft-intune.md). Zo voorkomt u dat bedrijfsgegevens worden misbruikt. Mogelijk moet u het apparaat echter wel afschrijven.

U moet ook de licentie van het Intune-account van de werknemer intrekken. Hiermee maakt u de licentie vrij en kunt u deze toewijzen aan een nieuw gebruikersaccount.

## <a name="retire-hardware"></a>Hardware buiten gebruik stellen
Het kan ook zo zijn dat het apparaat het einde van de levensduur heeft bereikt. In dergelijke gevallen kunt u de [fabrieksinstellingen van het apparaat terugzetten](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). Alle gegevens worden dan gewist en het apparaat wordt uit Intune verwijderd. Vervolgens kunt de hardware volgens het beleid van uw bedrijf afvoeren.

### <a name="see-also"></a>Zie tevens
[Uw gegevens beschermen met volledig wissen of selectief wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)

