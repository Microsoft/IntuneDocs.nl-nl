---
title: Overzicht van de MDM-levenscyclus | Microsoft Intune
description: Ontdek hoe Intune u helpt bij het beheren van apparaten gedurende hun levensduur, van de inschrijving en configuratie tot de uiteindelijke buitengebruikstelling.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 11260ad0e7dc45b7dec42fe12456ed18a484ab89


---

# Overview of the mobile device management (MDM) lifecycle (Overzicht van de MDM-levenscyclus (Mobile Device Management))

Alle apparaten die u beheert, hebben een zogeheten *levensduur*. Intune kan u helpen met het beheren van de levensduur, van de inschrijving tot aan de buitengebruikstelling van het apparaat, wanneer het niet meer nodig is:

![De levenscyclus van apparaten](./media/device-lifecycle.png "the Intune device lifecycle")

## Inschrijven
De hedendaagse MDM-strategieën (Mobile Device Management) hebben te maken met verschillende telefoons, tablets en pc's (iOS, Android, Windows en Mac OS X). Als u het apparaat moet kunnen beheren, wat vaak het geval is bij apparaten die bedrijfseigendom zijn, is de eerste stap de [apparaatregistratie instellen](enroll-devices-in-microsoft-intune.md). U kunt Windows-pc's ook beheren door deze in te schrijven bij Intune (MDM) of door [de Intune-clientsoftware te installeren](manage-windows-pcs-with-microsoft-intune.md).

## Configureren
Registratie van de apparaten is slechts de eerste stap. Om te profiteren van alles wat Intune te bieden heeft en te zorgen dat uw apparaten beveiligd en compatibel zijn met de standaarden van uw bedrijf, kunt u kiezen uit een breed scala aan **beleidsregels** waarmee u bijna elk aspect kunt configureren van de manier waarop beheerde apparaten werken. Bijvoorbeeld: moeten gebruikers wachtwoorden hebben op apparaten met bedrijfsgegevens? U kunt dit verplicht stellen. Hebt u Wi-Fi in het bedrijf? Dit kunt u automatisch configureren. De volgende typen configuratieopties zijn beschikbaar:

- [**Configuratiebeleid**](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md): hiermee kunt u de werkwijze configureren van de functies en mogelijkheden van apparaten die u beheert. U kunt bijvoorbeeld configureren dat het gebruik van een wachtwoord op apparaten met Windows Phone vereist is en u kunt het gebruik van de camera op iPhones uitschakelen.
- [**Beleid voor toegang tot bedrijfsbronnen**](enable-access-to-company-resources-with-microsoft-intune.md): wanneer u uw gebruikers toegang biedt tot hun werk vanaf hun persoonlijke apparaten, brengt dit uitdagingen met zich mee. Hoe kunt u er bijvoorbeeld voor zorgen dat alle apparaten die toegang moeten krijgen tot bedrijfs-e-mail, correct zijn geconfigureerd? Hoe zorgt u dat gebruikers toegang krijgen tot het bedrijfsnetwerk via een VPN-verbinding zonder dat zij de vaak complexe instellingen hoeven te kennen? Intune kan helpen deze last te verlagen door automatisch apparaten te configureren die u beheert, zodat deze toegang krijgen tot gemeenschappelijke bedrijfsbronnen.
- [**Beleid voor beheer van Windows-pc's (met de Intune-clientsoftware)**](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md): hoewel de registratie van Windows-pc's met Intune u de meeste mogelijkheden voor apparaatbeheer geeft, blijft Intune ondersteuning bieden voor het beheer van Windows-pc's met de Intune-clientsoftware. Start hier als u informatie wilt over de taken die u kunt uitvoeren met pc's.

## Beveiligen
In de huidige IT-wereld is het beveiligen van apparaten tegen ongeoorloofde toegang een van de belangrijkste taken die u moet uitvoeren. Naast de items die u in de levenscyclus van het apparaat in de stap **Configureren** vindt, biedt Intune meer mogelijkheden om apparaten die u beheert te beveiligen tegen onbevoegde toegang of aanvallen:
- [**Meervoudige verificatie**](protect-windows-devices-with-multi-factor-authentication.md): u kunt apparaten nog beter beveiligen door een extra verificatielaag toe te voegen voor gebruikersaanmelding. Apparaten met Windows, Windows Phone en Windows Mobile bieden meervoudige verificatie waarbij een tweede verificatieniveau is vereist, zoals een telefoongesprek of sms-bericht, voordat gebruikers toegang kunnen krijgen.
- [**Instellingen voor Microsoft Passport**](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md): Microsoft Passport is een alternatieve aanmeldingsmethode waarmee gebruikers gebruikmaken van een *gebaar*, zoals het laten scannen van een vingerafdruk, of van Windows Hello om zich aan te melden zonder een wachtwoord.
- [**Beleid voor het beveiligen van Windows-pc's (met de Intune-clientsoftware)**](policies-to-protect-windows-pcs-in-microsoft-intune.md): bij het beheren van Windows-pc's met de Intune-clientsoftware zijn beleidsregels beschikbaar waarmee u instellingen voor Endpoint Protection, software-updates en Windows Firewall kunt configureren op pc's die u beheert.

## Buiten gebruik stellen
Wanneer een apparaat kwijtraakt, wordt gestolen, moet worden vervangen, of als gebruikers een andere functie krijgen, is het meestal nodig het apparaat [buiten gebruik te stellen of te wissen](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). Er zijn verschillende manieren waarop u dit kunt doen, variërend van het opnieuw instellen van het apparaat, het verwijderen van het apparaat uit beheer of het wissen van de bedrijfsgegevens die er op staan.



<!--HONumber=Jul16_HO4-->


