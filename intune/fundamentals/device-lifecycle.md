---
title: Overzicht van de Microsoft Intune MDM-levenscyclus
description: Ontdek hoe Intune u helpt bij het beheren van apparaten gedurende hun levensduur, van de inschrijving en configuratie tot de uiteindelijke buitengebruikstelling.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/04/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 816ad4bb5b17f3a480fbf834280c4e9792c394a9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502979"
---
# <a name="overview-of-the-microsoft-intune-mobile-device-management-mdm-lifecycle"></a>Overzicht van de MDM-levenscyclus (Mobile Device Management) van Microsoft Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Alle apparaten die u beheert, hebben een *levensduur*. Intune kan u helpen met het beheren van deze levensduur: van de inschrijving, configuratie en beveiliging tot de buitengebruikstelling van het apparaat, wanneer het niet meer nodig is.

![De levenscyclus van apparaten](./media/device-lifecycle/device-lifecycle.png "de levenscyclus van Intune-apparaten")

## <a name="enroll"></a>Inschrijven
De hedendaagse MDM-strategieën (Mobile Device Management) hebben te maken met verschillende telefoons, tablets en pc's (iOS, Android, Windows en Mac OS X). Als u het apparaat moet kunnen beheren, wat vaak het geval is bij apparaten die bedrijfseigendom zijn, is de eerste stap de [apparaatregistratie instellen](../enrollment/device-enrollment.md). U kunt Windows-pc's ook beheren door deze in te schrijven bij Intune (MDM) of door [de Intune-clientsoftware te installeren](../manage-windows-pcs-with-microsoft-intune.md).

## <a name="configure"></a>Configureren
Registratie van de apparaten is slechts de eerste stap. Om te profiteren van alles wat Intune te bieden heeft en te zorgen dat uw apparaten beveiligd en compatibel zijn met de standaarden van uw bedrijf, kunt u kiezen uit een breed scala aan beleidsregels. Hiermee kunt u vrijwel elk aspect configureren van de manier waarop beheerde apparaten werken. Bijvoorbeeld: moeten gebruikers wachtwoorden hebben op apparaten met bedrijfsgegevens? U kunt dit verplicht stellen. Hebt u Wi-Fi in het bedrijf? Dit kunt u automatisch configureren. De volgende typen configuratieopties zijn beschikbaar:

- [**Apparaatconfiguratie**](../configuration/device-profiles.md). Hiermee kunt u de functies en mogelijkheden configureren van de apparaten die u beheert. U kunt bijvoorbeeld configureren dat het gebruik van een wachtwoord op Windows Phones vereist is en het gebruik van de camera op iPhones uitschakelen.
- [**Toegang tot bedrijfsresources**](../configuration/device-profiles.md). Wanneer u uw gebruikers toegang biedt tot hun werk vanaf hun persoonlijke apparaten, brengt dit uitdagingen met zich mee. Hoe kunt u er bijvoorbeeld voor zorgen dat alle apparaten die toegang moeten krijgen tot bedrijfs-e-mail, correct zijn geconfigureerd? Hoe zorgt u dat gebruikers toegang krijgen tot het bedrijfsnetwerk via een VPN-verbinding zonder dat zij complexe instellingen hoeven te kennen? Intune kan helpen deze last te verlagen door automatisch de apparaten te configureren die u beheert, zodat deze toegang krijgen tot gemeenschappelijke bedrijfsbronnen.
- [**Beleid voor beheer van Windows-pc’s (met de Intune-clientsoftware)** ](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md). Hoewel de registratie van Windows-pc's met Intune u de meeste mogelijkheden voor apparaatbeheer geeft, blijft Intune ondersteuning bieden voor het beheer van Windows-pc's met de Intune-clientsoftware. Begin hier als u informatie wilt over de taken die u kunt uitvoeren met pc's.

## <a name="protect"></a>Beveiligen
In de huidige IT-wereld is het beveiligen van apparaten tegen ongeoorloofde toegang een van de belangrijkste taken die u moet uitvoeren. Naast de items die u in de levenscyclus van het apparaat in de stap **Configureren** vindt, biedt Intune deze mogelijkheden om apparaten die u beheert te beveiligen tegen onbevoegde toegang of aanvallen:
- [**Multi-factor Authentication**](../enrollment/multi-factor-authentication.md). U kunt apparaten nog beter beveiligen door een extra verificatielaag toe te voegen voor gebruikersaanmelding. Veel apparaten ondersteunen meervoudige verificatie waarbij een tweede verificatieniveau is vereist, zoals een telefoongesprek of sms-bericht, voordat gebruikers toegang kunnen krijgen.
- [**Instellingen voor Windows Hello voor Bedrijven**](../protect/windows-hello.md). Windows Hello voor Bedrijven is een alternatieve aanmeldingsmethode waarmee gebruikers gebruikmaken van een *gebaar*, zoals een vingerafdruk of Windows Hello, om zich aan te melden zonder een wachtwoord.
- [**Beleid voor het beveiligen van Windows-pc’s (met de Intune-clientsoftware)** ](../policies-to-protect-windows-pcs-in-microsoft-intune.md). Bij het beheren van Windows-pc's met de Intune-clientsoftware zijn beleidsregels beschikbaar waarmee u instellingen voor Endpoint Protection, software-updates en Windows Firewall kunt configureren op pc's die u beheert.

## <a name="retire"></a>Buiten gebruik stellen
Wanneer een apparaat kwijtraakt, wordt gestolen, moet worden vervangen, of als gebruikers een andere functie krijgen, is het meestal nodig het apparaat [buiten gebruik te stellen of te wissen](../remote-actions/device-management.md). Er zijn verschillende manieren waarop u dit kunt doen, variërend van het opnieuw instellen van het apparaat, het verwijderen van het apparaat uit beheer en het wissen van de bedrijfsgegevens die erop staan.

## <a name="next-steps"></a>Volgende stappen

- Meer informatie over [apparaatbeheer in Microsoft Intune](../remote-actions/device-management.md)
