---
title: De doelgroepen en het tijdsbestek voor de rollout van Intune bepalen | Microsoft Docs
description: Dit artikel helpt bij het bepalen van de doelgroepen en het tijdsbestek voor de rollout van een cloudimplementatie voor Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 36530602813467c184b4f262719a56cedbaa2ba9


---

# <a name="develop-an-intune-rollout-plan"></a>Een rolloutplan voor Intune ontwikkelen

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Deze sectie helpt u bij het bepalen van de beoogde organisatiegroepen voor uw Intune-rollout, van de duur van de rollout voor elke groep en van de registratiestrategieën die worden gebruikt.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>De doelgroepen en het tijdsbestek voor de rollout van Intune bepalen

Het is belangrijk om eerst de doelgroepen voor uw Intune-rollout te identificeren. De doelgroepen zijn eerder besproken in de sectie over use-casescenario's voor Intune in deze handleiding.

In de tweede plaats moet u voor elke doelgroep het tijdsbestek bepalen voor de Intune-rollout. Hiervoor is meestal een interne bespreking van het team voor de Intune-implementatie en een gesprek met de doelgroepen vereist om de meest geschikte rollout-periode voor elke groep te bepalen.

Het team voor de Intune-implementatie kan bijvoorbeeld factoren bespreken zoals de bereidheid tot verandering van een groep, het aantal gebruikers en apparaten, de typen apparaatplatformen, vereisten, de geografische locatie en het bedrijfsrisico om het tijdsbestek van de rollout te kunnen bepalen.

Organisaties kiezen er vaak voor om de rollout van Intune te starten met een eerste pilot, voor een kleine groep gebruikers in de IT-afdeling. De pilot kan vervolgens worden uitgebreid naar een grotere groep IT-gebruikers en met de deelname van andere groepen in de organisatie. Na een geslaagde pilot kan met een volledige productie-rollout worden gestart, gericht op de overige organisatiegroepen. Enkele voorbeelden van verschillende rollout-groepen en -fasen worden hieronder vermeld:

-   **Pilot:** bij de eerste fase van de rollout moeten pilotgebruikers worden betrokken. De pilotgebruikers moeten weten dat zij de eerste gebruikers van een nieuwe oplossing zijn en moeten bereid zijn feedback te geven om de configuratie, documentatie en meldingen te helpen verbeteren en de weg te effenen voor alle andere gebruikers in latere fasen van de rollout. Deze gebruikers moeten geen leidinggevenden of VIP's zijn.

-   **Afdelingen:** elke afdeling kan worden opgenomen in een fase van de rollout. Dit scenario heeft betrekking op een volledige afdeling. In dit type rollout wordt hoogstwaarschijnlijk in elke fase het mobiele apparaat op dezelfde manier gebruikt en worden dezelfde toepassingen geopend. Bovendien gelden voor de gebruikers hoogstwaarschijnlijk dezelfde typen beleidsregels.

-   **Geografie:** dit type implementatie omvat het implementeren van alle gebruikers in een specifiek geografisch gebied, of dat nu hetzelfde continent, hetzelfde land, dezelfde regio of hetzelfde bedrijfsgebouw is. Dit type gefaseerde implementatie biedt de mogelijkheid om u te richten op een specifieke gebruikerslocatie. Dit kan leiden tot een [effectievere](#user-assisted-enrollment) aanpak omdat het aantal locaties afneemt waar Intune op hetzelfde moment wordt geïmplementeerd. Omdat het mogelijk is dat er op dezelfde locatie verschillende afdelingen of use cases zijn, kunnen er verschillende use cases op hetzelfde moment worden geïmplementeerd.

-   **Platform:** dit type implementatie omvat het tegelijkertijd implementeren van soortgelijke platformen. Een voorbeeld daarvan is de implementatie op alle iOS-apparaten tijdens de eerste maand, gevolgd door Android, gevolgd door Windows. Dit type gefaseerde implementatie maakt ondersteuning door de helpdesk gemakkelijker. De helpdesk hoeft dan maar één platform tegelijk te ondersteunen.

Hier is een voorbeeld van een rollout-plan voor Intune met doelgroepen en tijdlijnen:

| **Rollout-fase** | **Juli** | **Augustus** | **September** | **Oktober** |
|:---:|:---:|:---:|:---:|:---:|
| Beperkte pilot | IT (50 gebruikers) |  |  |  |                                                         
| Uitgebreide pilot | IT (200 gebruikers) IT-managers (10 gebruikers) |  |  |  |                                                         
| Productie-rollout fase 1 |  | Verkoop en Marketing (2000 gebruikers) |  |  |
| Productie-rollout fase 2 |  |  | Retail (1000 gebruikers) |  |
| Productie-rollout fase 3 |  |  |  | HR (50 gebruikers), Financiën (40 gebruikers), Leidinggevenden (30 gebruikers) |

## <a name="determine-the-intune-enrollment-approach"></a>De methode voor Intune-registratie bepalen

Nu u de doelgroepen en het tijdsbestek voor de Intune-rollout hebt bepaald, bestaat de volgende stap uit de keuze voor de meest geschikte methode voor de Intune-registratie voor elke groep. Er zijn verschillende registratiemethoden die organisaties kunnen gebruiken voor de rollout van Intune. Enkele veelgebruikte registratiemethoden zijn selfservice door de gebruiker, gebruikersregistratie met ondersteuning en een IT-informatiedag.

### <a name="user-self-service"></a>Selfservice door de gebruiker

Met deze methode zijn de gebruikers verantwoordelijk voor het registreren van hun eigen apparaat aan de hand van registratie-instructies van de IT-organisatie. Deze methode wordt het meest gebruikt in organisaties en is beter schaalbaar dan gebruikersregistratie met ondersteuning.

### <a name="user-assisted-enrollment"></a>Gebruikersregistratie met ondersteuning

Bij deze methode ondersteunt een medewerker van het IT-team de gebruiker bij het doorlopen van het registratieproces, persoonlijk of via Skype. Deze methode wordt doorgaans gebruikt voor leidinggevenden en andere groepen die wellicht meer hulp nodig hebben tijdens het registratieproces.

### <a name="it-tech-fair"></a>IT-informatiedag

Een andere optie voor het registreren van gebruikers bij Intune is een informatiedag van de IT-afdeling. Op zo'n dag kan de IT-afdeling een stand inrichten met informatie over registratie bij Intune, waar gebruikers informatie kunnen krijgen, vragen kunnen stellen en hulp bij het registratieproces kunnen ontvangen. Deze optie kan van pas komen voor zowel de IT-afdeling als de gebruikers, met name tijdens de eerste fasen van de rollout van Intune.

Hier is een voorbeeld van een rollout-plan voor Intune met doelgroepen, tijdlijnen en registratiemethoden:

| **Rollout-fase** | **Juli** | **Augustus** | **September** | **Oktober** |
|:---:|:---:|:---:|:---:|:---:|
| Beperkte pilot |  |  |  |  |                                                         
| Selfservice | IT |  |  |  |
| Uitgebreide pilot |  |  |  |  |                                                         
| Selfservice | IT |  |  |  |
| Gebruikersregistratie met ondersteuning | IT-managers |  |  |  |
| Productie-rollout fase 1 |  | Verkoop, Marketing |  |  |
| Selfservice |  | Verkoop en Marketing |  |  |
| Productie-rollout fase 2 |  |  | Retail |  |
| Selfservice |  |  |  |  |
| Productie-rollout fase 3 |  |  | Retail |  |
| Selfservice |  |  |  | HR, Financiën |
| Gebruikersregistratie met ondersteuning |  |  |  | Leidinggevenden |

## <a name="next-section"></a>Volgende sectie

De volgende sectie bevat richtlijnen over het [ontwikkelen van een communicatieplanning voor de Intune-rollout](section-5-develop-a-rollout-communication-plan.md).



<!--HONumber=Dec16_HO5-->


