---
title: Intune testen en valideren
description: De details die u moet overwegen wanneer u een cloud-only-oplossing van Intune test en valideert in uw omgeving.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: ddeb71c6a678ff42b5075d65c2bb4e0d89ae47f1
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2017
---
# <a name="intune-testing-and-validation"></a>Intune testen en valideren

De testfase treedt op tijdens en na de implementatiefase. U moet testaccounts, -groepen en -apparaten hebben voor het testen van alle vereiste IT- (beheer) en eindgebruikers- (use case) scenario's die u eerder hebt geïdentificeerd.

Het is raadzaam uw team voor IT-ondersteuning en helpdesk te betrekken bij de testfase om ondersteuningsdocumentatie samen te stellen en om de medewerkers van het team vertrouwd te maken met de ondersteuning van het product. Als een onderdeel of scenario niet werkt op basis van de use cases, is het belangrijk om de noodzakelijke wijzigingen en de redenen daarvoor vast te leggen.

## <a name="before-you-begin"></a>Voordat u begint

U wordt aangeraden het volgende te documenteren:

-   **Testcriteria:** identificeer de te hanteren benchmarks.

-   **Ontwerponderdelen:** moeten in ten minste één testcriterium zijn opgenomen.

Als een ontwerponderdeel niet is opgenomen in ten minste één testcriterium voor een vereiste of scenario, moet u beslissen of het ontwerponderdeel wel of niet vereist is. Zorg er bovendien voor dat u over de volgende items beschikt:

-   **Accounts:** testaccounts die een licentie hebben voor EMS en Office 365 om alle use-casescenario's te testen.

-   **Apparaten:** testapparaten die kunnen worden gewist of teruggezet naar de fabrieksinstellingen.

-   **Integratieonderdelen:** alle integratieonderdelen (Certificate Connector, Intune Service to Service Connector voor gehoste Exchange en Intune On-Premises Exchange Connector) moeten indien nodig, worden geïnstalleerd en geconfigureerd.

U kunt ontwerpwijzigingen nodig hebben om onvoorziene problemen het hoofd te bieden. Bovendien moeten alle ontwerpwijzigingen volledig worden gedocumenteerd met de reden voor elke wijziging. Hier volgt een voorbeeld van een mogelijke wijziging:

<blockquote>U komt erachter dat u niet voldoet aan de vereisten van de Network Device Enrollment Service (NDES) en u weet ook dat de VPN- en wifi-profielen kunnen worden geconfigureerd met een basiscertificeringsinstantie die voldoet aan dezelfde vereisten zonder een NDES-implementatie.</blockquote>

U kunt te maken krijgen met uitdagingen of problemen waarvoor technische hulp of gespecialiseerde probleemoplossing is vereist tijdens het testen en valideren. We raden u aan om naar hulp te zoeken via de kanalen van Microsoft-ondersteuning.

-   [Informatie over het verkrijgen van ondersteuning voor Intune](get-support.md)

-   [Contact opnemen met telefonische ondersteuning voor Microsoft Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Functionele-validatietests

Functionele validatie bestaat uit het testen van elk onderdeel en elke configuratie om te bepalen of de werking ervan in orde is. In de onderstaande tabel ziet u een voorbeeld van een validatietest.

![Sectie 9 tabel 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Validatietest van use case

Voer validatietests van use cases uit om na te gaan of de scenario's volledig en functioneel zijn. Er zijn twee soorten use-casescenario's: voor de IT-beheerder en de eindgebruiker.

### <a name="it-admin"></a>IT-beheerder

Voer validatietests voor de IT-beheerder uit om te controleren of beheeracties die voor een apparaat of gebruiker worden uitgevoerd, goed werken. Hieronder ziet u een voorbeeld van een end-to-end validatiescenario voor IT-beheerders.

![Sectie 9 tabel 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Eindgebruiker

Voer validatietests voor de eindgebruiker uit om te controleren of de ervaring van de eindgebruiker voldoet aan de verwachtingen en op de juiste wijze in alle informatie naar de gebruiker wordt aangeboden. Het is belangrijk om te valideren dat de eindgebruikerservaring juist is. Als u niet valideert, kan dit leiden tot minder acceptatie en grotere volumes helpdeskvragen.

![Sectie 9 tabel 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Volgende stappen

Nu u de functionele en use-casescenario's van Intune hebt getest en gevalideerd, bent u klaar voor de [productie-rollout van Intune](planning-guide-rollout-plan.md).

Zie [aanvullende bronnen](planning-guide-resources.md) voor meer planningssjablonen en informatie.
