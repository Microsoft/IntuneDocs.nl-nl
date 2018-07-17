---
title: Overzicht van de Microsoft Intune MDM-levenscyclus
description: Ontdek hoe Intune u helpt bij het beheren van apparaten gedurende hun levensduur, van de inschrijving en configuratie tot de uiteindelijke buitengebruikstelling.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c2e4cf0e77a63f0a8a3049e66ec16e563e410873
ms.sourcegitcommit: 2198a39ae48beca5fc74316976bc3fc9db363659
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2018
ms.locfileid: "38225202"
---
# <a name="overview-of-the-microsoft-intune-mobile-device-management-mdm-lifecycle"></a>Overzicht van de MDM-levenscyclus (Mobile Device Management) van Microsoft Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Alle apparaten die u beheert, hebben een *levensduur*. Intune kan u helpen met het beheren van deze levensduur: van de inschrijving, configuratie en beveiliging tot de buitengebruikstelling van het apparaat, wanneer het niet meer nodig is.

![De levenscyclus van het apparaat](./media/device-lifecycle.png "de levenscyclus van het Intune-apparaat")

## <a name="enroll"></a>Inschrijven
De hedendaagse MDM-strategieën (Mobile Device Management) hebben te maken met verschillende telefoons, tablets en pc's (iOS, Android, Windows en Mac OS X). Als u het apparaat moet kunnen beheren, wat vaak het geval is bij apparaten die bedrijfseigendom zijn, is de eerste stap de [apparaatregistratie instellen](device-enrollment.md) ([klassieke portal](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)). U kunt Windows-pc's ook beheren door deze in te schrijven bij Intune (MDM) of door [de Intune-clientsoftware te installeren](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune).

## <a name="configure"></a>Configureren
Registratie van de apparaten is slechts de eerste stap. Om te profiteren van alles wat Intune te bieden heeft en te zorgen dat uw apparaten beveiligd en compatibel zijn met de standaarden van uw bedrijf, kunt u kiezen uit een breed scala aan beleidsregels. Hiermee kunt u vrijwel elk aspect configureren van de manier waarop beheerde apparaten werken. Bijvoorbeeld: moeten gebruikers wachtwoorden hebben op apparaten met bedrijfsgegevens? U kunt dit verplicht stellen. Hebt u Wi-Fi in het bedrijf? Dit kunt u automatisch configureren. De volgende typen configuratieopties zijn beschikbaar:

- [**Apparaatconfiguratie** ](device-profiles.md) ([klassieke portal](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)). Hiermee kunt u de functies en mogelijkheden configureren van de apparaten die u beheert. U kunt bijvoorbeeld configureren dat het gebruik van een wachtwoord op Windows Phones vereist is en het gebruik van de camera op iPhones uitschakelen.
- [**Toegang tot bedrijfsbronnen**](device-profiles.md) ([klassiek portal](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune)). Wanneer u uw gebruikers toegang biedt tot hun werk vanaf hun persoonlijke apparaten, brengt dit uitdagingen met zich mee. Hoe kunt u er bijvoorbeeld voor zorgen dat alle apparaten die toegang moeten krijgen tot bedrijfs-e-mail, correct zijn geconfigureerd? Hoe zorgt u dat gebruikers toegang krijgen tot het bedrijfsnetwerk via een VPN-verbinding zonder dat zij complexe instellingen hoeven te kennen? Intune kan helpen deze last te verlagen door automatisch de apparaten te configureren die u beheert, zodat deze toegang krijgen tot gemeenschappelijke bedrijfsbronnen.
- [**Beleid voor beheer van Windows-pc’s (met de Intune-clientsoftware)**](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client). Hoewel de registratie van Windows-pc's met Intune u de meeste mogelijkheden voor apparaatbeheer geeft, blijft Intune ondersteuning bieden voor het beheer van Windows-pc's met de Intune-clientsoftware. Begin hier als u informatie wilt over de taken die u kunt uitvoeren met pc's.

## <a name="protect"></a>Beveiligen
In de huidige IT-wereld is het beveiligen van apparaten tegen ongeoorloofde toegang een van de belangrijkste taken die u moet uitvoeren. Naast de items die u in de levenscyclus van het apparaat in de stap **Configureren** vindt, biedt Intune deze mogelijkheden om apparaten die u beheert te beveiligen tegen onbevoegde toegang of aanvallen:
- [**Multi-factor Authentication**](/intune-classic/deploy-use/protect-your-devices-with-microsoft-intune). U kunt apparaten nog beter beveiligen door een extra verificatielaag toe te voegen voor gebruikersaanmelding. Veel apparaten ondersteunen meervoudige verificatie waarbij een tweede verificatieniveau is vereist, zoals een telefoongesprek of sms-bericht, voordat gebruikers toegang kunnen krijgen.
- [**Instellingen voor Windows Hello voor Bedrijven**](windows-hello.md) ([klassieke portal](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)). Windows Hello voor Bedrijven is een alternatieve aanmeldingsmethode waarmee gebruikers gebruikmaken van een *gebaar*, zoals een vingerafdruk of Windows Hello, om zich aan te melden zonder een wachtwoord.
- [**Beleid voor het beveiligen van Windows-pc’s (met de Intune-clientsoftware)**](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune). Bij het beheren van Windows-pc's met de Intune-clientsoftware zijn beleidsregels beschikbaar waarmee u instellingen voor Endpoint Protection, software-updates en Windows Firewall kunt configureren op pc's die u beheert.

## <a name="retire"></a>Buiten gebruik stellen
Wanneer een apparaat kwijtraakt, wordt gestolen, moet worden vervangen, of als gebruikers een andere functie krijgen, is het meestal nodig het apparaat [buiten gebruik te stellen of te wissen](device-management.md) ([klassieke portal](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)). Er zijn verschillende manieren waarop u dit kunt doen, variërend van het opnieuw instellen van het apparaat, het verwijderen van het apparaat uit beheer en het wissen van de bedrijfsgegevens die erop staan.
