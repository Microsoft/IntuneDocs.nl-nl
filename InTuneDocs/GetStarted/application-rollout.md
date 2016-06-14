---
# required metadata

title: Toepassingen implementeren | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 0fc32ed3-bcf4-472a-80e7-eb20986f78fa

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Toepassingen implementeren
In dit onderwerp vindt u specifieke aanbevelingen voor een gefaseerde implementatie van apps in Microsoft Intune. Voor algemene informatie over implementatiefasen raadpleegt u [Implementatiefasen voor Microsoft Intune-implementatie](rollout-phases-for-microsoft-intune-deployment.md).

### De fasen van app-implementatie
De fasen van app-implementatie zijn:

-   Projectbereik

-   Testen van het concept

-   Testfase

-   Implementatie in het bedrijf

-   Bewerkingen en onderhoud

## Projectbereik
Neem het volgende in overweging:

-   De taak die de gebruiker met de app moet kunnen uitvoeren.

-   De geschiktheid van de app voor uw gebruikers en hun apparaten (alle besturingssystemen die waarschijnlijk zullen worden gebruikt).

-   Controleer of het installatieprogramma voor de app die u hebt gekozen, wordt ondersteund door Intune-app-distributie, zoals wordt beschreven in  [Apps toevoegen met Microsoft Intune](/intune/deploy-use/add-apps).

-   Zorg ervoor dat alle vereiste zaken voor app-distributie worden geïnstalleerd. <!---, as described in [Plan for app deployment in Microsoft Intune](plan-for-app-deployment-in-microsoft-intune.md--->).

-   Controleer of het app-type wordt ondersteund door Intune.

-   Controleer of u voldoende cloudopslagruimte hebt om de app te uploaden. Instructies voor het aanschaffen van extra opslagruimte vindt u in [Apps toevoegen met Microsoft Intune](/intune/deploy-use/add-apps).

## Testen van het concept
In de fase Testen van het concept wordt de app-implementatie getest in een testomgeving. De app wordt geïmplementeerd op apparaten en voor gebruikers die u uitsluitend gebruikt voor testdoeleinden.

-   Laat uw helpdesk deelnemen aan deze fase zodat het voor iedereen duidelijk wordt welke problemen er kunnen optreden tijdens de test en productie-implementatie. Informatie voor probleemoplossing vindt u in [Problemen met app-implementaties oplossen in Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune).

-   Op dit punt in het proces ontwikkelt u communicatieplannen voor de test- en productiegebruikers. Het plan moet minimaal bevatten welke app wordt geïmplementeerd, hoe en wanneer gebruikers de app kunnen downloaden, wat het zakelijke doel is van de implementatie en wat er moet worden gedaan in geval van problemen (met zelfhulpinformatie én contactinformatie van de helpdesk).

## Testfase
Tijdens de testfase implementeert u de app voor een kleine groep testgebruikers en op een klein aantal apparaten. Neem het volgende in overweging:

-   Zorg ervoor dat de testgroep een goede vertegenwoordiging vormt van de gebruikers die de app na de implementatie gaan gebruiken en van de apparaten waarop de app zal worden gebruikt.

-   Breng de helpdesk op de hoogte van de implementatie van de app en zorg ervoor dat de helpdeskmedewerkers klaarstaan om de gebruikers uit de testgroep te helpen.

-   Kies testgebruikers die de app normaal gaan gebruiken en problemen altijd zullen melden aan de testbeheerders.

-   Activeer uw communicatieplan voor testgebruikers.

## Implementatie in het bedrijf

-   Gebruik de testresultaten om de plannen voor implementatie binnen het bedrijf te verbeteren.

-   Breng de helpdesk op de hoogte van de implementatieplanning voor de app. Zorg ervoor dat u een systeem hebt om te reageren op hulpverzoeken en om de implementatie indien nodig aan te passen.

-   Wees erop voorbereid om problemen met de implementatie op te lossen, indien deze zich voordoen.

-   Activeer uw communicatieplan voor productiegebruikers.

-   Ga gefaseerd te werk bij het implementeren van de apps: voeg steeds meer groepen toe om ervoor te zorgen dat de implementatie soepel verloopt.

## Bewerkingen en onderhoud
**Bewerkingen:** bewaak de Intune-console om in de gaten te houden of er waarschuwingen zijn en of er problemen met gebruikers of apparaten zijn. U kunt in de console ook controleren of de toepassingsdistributie naar wens wordt uitgevoerd.

**Helpdesk:** zorg ervoor dat uw helpdesk op de hoogte is van alle veranderingen in de beschikbaarheid van de app waardoor mogelijk meer ondersteuningsaanvragen kunnen worden ingediend.

### Zie tevens
[Apps implementeren](/intune/deploy-use/deploy-apps)

[Problemen met app-implementaties oplossen in Microsoft Intune](/intune/troubleshoot/troubleshoot-app-deployment-problems-in-microsoft-intune)


<!--HONumber=May16_HO1-->


