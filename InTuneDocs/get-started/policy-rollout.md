---
title: Implementatie van beleid | Microsoft Intune
description: Aanbevelingen voor een gefaseerde implementatie van beleid in Microsoft Intune.
keywords: 
author: Nbigman
ms.author: nbigman
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 390d5adf-86d2-4e23-ba93-1e61e6b1028b
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8921043334630bbd2955c0423ca9cd1b76c27758
ms.openlocfilehash: 0a363ed242f5968f3fb84b558cfa134e243a22ff


---

# Implementatie van beleid
Dit onderwerp bevat specifieke aanbevelingen voor een gefaseerde implementatie van beleid in Microsoft Intune. Deze aanpak is van toepassing op de eerste beleidsregels die u in een nieuwe implementatie van Intune toepast of op beleidsregels die u toevoegt aan een bestaande implementatie.

Voor algemene informatie over implementatiefasen raadpleegt u [Implementatiefasen voor Microsoft Intune-implementatie](rollout-phases-for-microsoft-intune-deployment.md).

### Fasen van de implementatie van beleid
De fasen van een beleidsimplementatie zijn:

-   Projectbereik

-   Testen van het concept

-   Test

-   Implementatie in het bedrijf

-   Bewerkingen en onderhoud

## Projectbereik
Definieer de omvang van de implementatie van uw Intune-beleid:

-   Voor een nieuwe implementatie moet u hiervoor al het gewenste apparaatgedrag en de beveiligingsvereisten definiëren die u wilt opnemen in uw beleid.

-   Bepaal op welke gebruikers en apparaten dit beleid van toepassing zal zijn.

-   Ontwerp uw gebruikers- en apparaatgroepen, zodat u het nieuwe beleid op de juiste wijze kunt toepassen.

-   Bepaal voor elk besturingssysteem of er beperkingen of vereisten zijn die van invloed zijn op het doel van uw beleid.

-   Houd rekening met ontwerpdetails van het beleid, zoals het beleidstype en de sjabloon die moeten worden gebruikt.

-   Of u nu uw eerste set beleidsregels implementeert of nieuw beleid toevoegt aan bestaand beleid, houd er rekening mee hoe verschillende beleidsregels op elkaar van invloed zijn en wat het gedrag van het apparaat waarschijnlijk zal zijn. Problemen met beleidsinteracties en conflicten kunnen worden gevonden in de testfase, maar als u beleidsconflicten in een vroeg stadium van de planning constateert, zal de uitvoering van de test eenvoudiger verlopen.

## Testen van het concept
In de fase Testen van het concept wordt de beleidsimplementatie getest in een testomgeving. Het beleid wordt toegepast op apparaten en bij gebruikers die u uitsluitend gebruikt voor testdoeleinden.

-   Laat uw helpdesk deelnemen aan deze fase, zodat het voor iedereen duidelijk wordt welke problemen er kunnen optreden tijdens de test en de productie-implementatie. Informatie over probleemoplossing vindt u in [Beleidsproblemen oplossen in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).

-   Op dit punt in het proces ontwikkelt u communicatieplannen voor de test- en productiegebruikers. Het plan moet minimaal het volgende bevatten: welk apparaatgedrag wordt gewijzigd en wanneer, het bedrijfsdoel voor de wijziging, wat te doen als gebruikers of IT-medewerkers problemen ondervinden. Dit moet zowel zelfhulpinformatie zijn als informatie over het contact opnemen met de helpdesk.

## Test
Tijdens de testfase implementeert u het beleid voor een kleine groep testgebruikers en op een klein aantal apparaten. Er zijn specifieke aandachtspunten voor het testen van beleid in Intune:

-   De testgroep moet een goede afspiegeling zijn van de groep waarop het beleid wordt toegepast voor productie-implementatie.

-   Breng de helpdesk op de hoogte van de beleidswijzigingen en zorg ervoor dat de helpdeskmedewerkers klaarstaan om de gebruikers uit de testgroep te helpen.

-   Activeer uw communicatieplan voor testgebruikers.

-   De test kan eerst worden uitgevoerd in de geïsoleerde modus, waarbij het apparaat niet is onderworpen aan ander beleid dat kan leiden tot conflicten en onbedoeld gedrag.

-   Bij de laatste test moet rekening worden gehouden met het nieuwe beleid en alle bestaande beleidsregels die worden toegepast op hetzelfde apparaat.

## Implementatie in het bedrijf

-   Op basis van de resultaten van de test past u het geplande beleid aan om te corrigeren voor beleidsconflicten en onverwacht gedrag.

-   Breng de helpdesk op de hoogte van de implementatieplanning voor de hele onderneming. Zorg ervoor dat u een systeem hebt om te reageren op hulpverzoeken en om de implementatie indien nodig aan te passen.

-   Wees erop voorbereid om problemen met het beleid op te lossen, indien deze zich voordoen.

-   Activeer uw communicatieplan voor productiegebruikers.

-   Pas het beleid geleidelijk toe op extra groepen en bewaak hierbij de beleidsstatus voor de betreffende apparaten. Houd helpdeskaanvragen bij die verband houden met het nieuwe beleid.

## Bewerkingen en onderhoud
**Bewerkingen:** controleer de Intune-beheerconsole voor waarschuwingen en problemen met gebruikers of apparaten, en controleer of beleidsregels werken volgens plan.

**Helpdesk:** zorg ervoor dat uw helpdesk op de hoogte is van eventuele wijzigingen aan beleidsregels die van invloed zijn op de ervaring van de gebruiker, aangezien deze wijzigingen mogelijk leiden tot ondersteuningsaanvragen.


### Zie tevens
[Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune](/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

[Beleidsproblemen oplossen in Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune)



<!--HONumber=Oct16_HO4-->


