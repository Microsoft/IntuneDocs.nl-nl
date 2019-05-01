---
title: Een Intune-migratiecampagne starten
titleSuffix: Microsoft Intune
description: Dit artikel bevat richtlijnen voor het starten van een Microsoft Intune-migratiecampagne.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: db56bbc180a84e8b3972ffc6473126efd366faa8
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "61508179"
---
# <a name="phase-2-migration-campaign"></a>Fase 2: Migratiecampagne

Kies een migratiestrategie die het beste past bij de behoeften van uw organisatie en pas de implementatietactieken aan op basis van uw specifieke wensen. In de rest van deze handleiding vindt u de middelen om de apparaten van de gebruikers bij Intune te registreren.

## <a name="keys-to-a-successful-migration"></a>Belangrijke factoren voor een geslaagde migratie

Dit zijn de sleutels voor de migratie van een MDM-provider van derden naar Intune:

-   Heldere en nuttige communicatie kan uitvaltijd en ergernis bij de eindgebruiker minimaliseren.

-   Zorg ervoor dat u specifieke en concrete instructies voor de migratie hanteert.

-   Alle beheerde apparaten moeten worden uitgeschreven bij uw bestaande MDM-provider voordat ze kunnen worden geregistreerd bij Intune.

-   Help de eindgebruikers bij het uitschrijven van hun apparaten bij uw bestaande MDM-provider.

-   Hanteer een gefaseerde benadering. Begin met een kleine groep gebruikers als testfase en voeg steeds meer groepen gebruikers toe totdat u een volledige implementatie hebt bereikt.

-   Controleer de belasting voor de helpdesk en het aantal geslaagde registraties in elke cyclus. Laat tijd open in de planning zodat de slagingscriteria voor elke groep kunnen worden geëvalueerd voordat u de migratie voor de volgende groep uitvoert. Bij de implementatie in de testfase moet het volgende worden gecontroleerd:

    -   Het aantal geslaagde en mislukte inschrijvingen zijn naar verwachting.

    -   De gebruikersproductiviteit:

        -   Bedrijfsresources zoals VPN, Wi-Fi-, e-mail en certificaten functioneren naar behoren.

        -   De gebruikers kunnen toegang krijgen tot de aangeboden apps.

    -   Gegevensbeveiliging:

        -   Er wordt nalevingsrapportage uitgevoerd.

        -   De beveiliging van mobiele apps wordt doorgevoerd.

Wanneer u tevreden bent over de eerste fase van de migratie, herhaalt u de [migratiecyclus](migration-guide-cycle.md) voor de volgende fase.

-   Herhaal de gefaseerde cycli totdat alle gebruikers naar Intune zijn gemigreerd.

-   Zorg ervoor dat het helpdeskteam er klaar voor is om gedurende de migratiecampagne ondersteuning te bieden aan de eindgebruikers. Hanteer een migratie op vrijwillige basis totdat u een idee hebt van de werkbelasting voor ondersteuningsgesprekken.

-   Stel pas deadlines voor de registratie in als de ondersteuning voor de resterende gebruikers kan worden verwerkt door uw helpdesk

> [!IMPORTANT]
> Configureer niet zowel Intune als uw bestaande MDM-oplossing van derden zo dat deze gebruikmaken van toegangsbeheer voor resources als Exchange of SharePoint Online. Daarnaast mogen apparaten maar in één oplossing tegelijk worden ingeschreven.

## <a name="next-steps"></a>Volgende stappen

Ontwikkel uw [communicatieplan](migration-guide-communication-plan.md).
