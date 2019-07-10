---
title: De doelgroepen voor de implementatie en het tijdschema bepalen
titleSuffix: Microsoft Intune
description: Aan de hand van dit artikel kunt u bepalen welke groepen in Microsoft Intune moeten worden geïmplementeerd en volgens welk tijdschema deze implementaties moeten verlopen.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7a369b3bde7967db04a76ae1794d7b8fb86c21e4
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2019
ms.locfileid: "67548417"
---
# <a name="develop-a-rollout-plan"></a>Een rollout-plan ontwikkelen

In uw implementatieplan worden de organisatiegroepen die doel zijn van de Intune-implementatie, het implementatietijdschema voor elke groep en de inschrijvingsmethoden vermeld.

## <a name="targeted-groups-and-timeframes"></a>Doelgroepen en tijdschema's

Neem eerst de groepen door die doel zijn van de Intune-implementatie en die u hebt vastgesteld in uw [gebruiksscenario's](planning-guide-scenarios.md).

Bepaal vervolgens het tijdschema voor elke doelgroep. Voor deze taak wordt meestal een bespreking tussen het team voor de Intune-implementatie en de doelgroepen georganiseerd om een geschikt implementatietijdschema voor elke groep te bepalen. Thema's die in een dergelijke bespreking aan bod komen:
* De bereidheid van de groep om de wijziging door te voeren
* Het aantal gebruikers en apparaten
* De soorten apparaatplatformen
* Vereisten
* Geografische locatie
* Bedrijfsrisico

## <a name="rollout-phases"></a>Implementatiefasen
Organisaties kiezen er vaak voor om de rollout van Intune te starten met een eerste pilot, voor een kleine groep gebruikers in de IT-afdeling. De testfase kan vervolgens worden uitgebreid naar een grotere groep IT-gebruikers en er kunnen andere groepen in de organisatie aan deelnemen.

### <a name="pilot"></a>Test
In de eerste fase van de implementatie zijn de testfasegebruikers de doelgroep. De testfasegebruikers moeten weten dat ze de eerste gebruikers van een nieuwe oplossing zijn. Zij moeten bereid zijn om feedback te geven zodat de configuratie, documentatie en meldingen kunnen worden verbeterd en zodat de weg wordt geëffend voor alle andere gebruikers in latere fasen van de implementatie. Deze gebruikers moeten geen leidinggevenden of VIP's zijn.

De testfase is een goede gelegenheid voor u om de [uitdagingen](planning-guide-deployment-goals.md) te testen en de [vereisten](planning-guide-requirements.md) die u eerder hebt verzameld te verfijnen.

Neem uw [communicatie](planning-guide-communication-plan.md)plan, [ondersteunings](planning-guide-support-plan.md)plan en [testen en validatie](planning-guide-test-validation.md) op in het project om eventuele problemen op te lossen zo lang de impact op de gebruikers nog klein is.

### <a name="production-rollout"></a>Volledige implementatie
Na een geslaagde testfase kunt u beginnen met een volledige implementatie die gericht is op de overige groepen van uw organisatie. Enkele voorbeelden van verschillende implementatiegroepen en -fasen zijn:

- **Afdelingen** <br/>Elke afdeling kan een implementatiefase vormen. Een gehele afdeling is tegelijkertijd het doel van de implementatie. Bij dit type implementatie maken de gebruikers van elke afdeling hoogstwaarschijnlijk op dezelfde manier gebruik van het mobiele apparaat en hebben ze toegang tot dezelfde toepassingen. De gebruikers moeten waarschijnlijk voldoen aan hetzelfde soort beleid.

- **Geografie** <br/>Bij deze methode vindt de implementatie plaats voor alle gebruikers in een specifiek geografisch gebied, of dat nu hetzelfde continent, hetzelfde land, dezelfde regio of hetzelfde bedrijfsgebouw is. Dit type gefaseerde implementatie biedt u de mogelijkheid om u te richten op een specifieke gebruikerslocatie. U kunt op deze manier een meer [intensieve](#user-assisted-enrollment) methode hanteren omdat het aantal locaties wordt beperkt waar Intune op hetzelfde moment wordt geïmplementeerd. Omdat het mogelijk is dat er op dezelfde locatie verschillende afdelingen of use cases zijn, kunnen er verschillende use cases op hetzelfde moment worden geïmplementeerd.

- **Platform** <br/>Bij dit type implementatie worden soortgelijke platformen gelijktijdig geïmplementeerd. Een voorbeeld daarvan is de implementatie op alle iOS-apparaten tijdens de eerste maand, gevolgd door Android, gevolgd door Windows. De helpdeskondersteuning wordt met dit type gefaseerde implementatie vereenvoudigd omdat de helpdesk slechts voor één platform tegelijkertijd ondersteuning hoeft te bieden.

Hier is een voorbeeld van een rollout-plan voor Intune met doelgroepen en tijdlijnen:

| **Rollout-fase** | **Juli** | **Augustus** | **September** | **Oktober** |
|:---:|:---:|:---:|:---:|:---:|
| Beperkte pilot | IT (50 gebruikers) |  |  |  |                                                         
| Uitgebreide pilot | IT (200 gebruikers) IT-managers (10 gebruikers) |  |  |  |                                                         
| Productie-rollout fase 1 |  | Verkoop en Marketing (2000 gebruikers) |  |  |
| Productie-rollout fase 2 |  |  | Retail (1000 gebruikers) |  |
| Productie-rollout fase 3 |  |  |  | HR (50 gebruikers), Financiën (40 gebruikers), Leidinggevenden (30 gebruikers) |

U kunt [een sjabloon van de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de implementatiefasen van uw organisatie in te voeren.
## <a name="match-rollout-groups-to-enrollment-approaches"></a>Implementatiegroepen koppelen aan inschrijvingsmethoden

Nu u de doelgroepen en het tijdschema voor de Intune-implementatie hebt bepaald, kiest u vervolgens een geschikte methode voor de Intune-inschrijving voor elke groep. Er zijn verschillende inschrijvingsmethoden die u kunt gebruiken, zoals:
* Selfservice door de gebruiker
* Gebruikersregistratie met ondersteuning
* IT-informatiedag

### <a name="user-self-service"></a>Selfservice door de gebruiker

In dit geval zijn de gebruikers verantwoordelijk voor het inschrijven van hun eigen apparaat. Voorafgaand aan de inschrijving ontvangen zij hiervoor gewoonlijk instructies van de IT-organisatie. Deze methode wordt het meest gebruikt in organisaties en is beter schaalbaar dan inschrijving met ondersteuning van de gebruiker.

### <a name="user-assisted-enrollment"></a>Inschrijving met ondersteuning van de gebruiker

Dit staat ook wel bekend als de intensieve methode. Een IT-teamlid doorloopt, persoonlijk of via Skype, samen met de gebruiker de inschrijvingsprocedure. Deze methode wordt doorgaans gebruikt voor leidinggevenden en andere groepen die wellicht meer hulp nodig hebben bij de inschrijvingsprocedure.

### <a name="it-tech-fair"></a>IT-informatiedag

Een andere optie voor het registreren van gebruikers bij Intune is een informatiedag van de IT-afdeling. Op zo'n dag zet de IT-afdeling een stand op ter ondersteuning van de Intune-inschrijving, waar gebruikers informatie kunnen krijgen, vragen kunnen stellen en hulp kunnen krijgen bij de inschrijvingsprocedure. Deze optie kan erg nuttig zijn voor zowel de IT-afdeling als de gebruikers, met name tijdens de eerste fasen van de Intune-implementatie.

Hier volgt een bijgewerkt voorbeeld van het bovenstaande Intune-implementatieplan waarin de inschrijvingsmethoden zijn opgenomen:

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

## <a name="next-steps"></a>Volgende stappen

De volgende sectie bevat richtlijnen over het [ontwikkelen van een communicatieplanning voor de Intune-rollout](planning-guide-communication-plan.md).
