---
title: Een Intune-migratiecampagne starten | Microsoft Docs
description: In dit artikel wordt uitgelegd hoe u een migratiecampagne start.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 506b0360fb7b1f28c4c9ad3265e24c0ffa0b065d
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-migration-campaign"></a>Fase 2: migratiecampagne

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Organisaties moeten een migratiestrategie hanteren die het beste past bij hun behoeften en de implementatietactieken aanpassen op basis van hun specifieke wensen. In de rest van deze handleiding vindt u de middelen om de apparaten van de gebruikers bij Intune in te schrijven.

## <a name="keys-to-a-successful-migration"></a>Belangrijke factoren voor een geslaagde migratie

Hier volgen enkele belangrijke ervaringen die zijn opgedaan bij het migreren van een externe MDM-provider naar Intune:

-   Communicatie speelt een belangrijke rol bij het minimaliseren van de uitvaltijd voor eindgebruikers en het realiseren van tevredenheid.

-   Zorg ervoor dat u specifieke en concrete instructies voor de migratie hanteert.

-   Alle beheerde apparaten moeten worden uitgeschreven bij de bestaande MDM-provider voordat ze worden ingeschreven bij Intune.

-   Help de eindgebruikers bij het uitschrijven van hun apparaten bij de bestaande MDM-provider.

-   Hanteer een gefaseerde benadering. Begin met een kleine groep gebruikers als testfase en voeg steeds meer groepen gebruikers toe totdat u een volledige implementatie hebt bereikt.

-   Controleer de belasting voor de helpdesk en het aantal geslaagde inschrijvingen in elke cyclus. Laat tijd open in de planning zodat de slagingscriteria voor elke groep kunnen worden geëvalueerd voordat u de migratie voor de volgende groep uitvoert. Bij de implementatie in de testfase moet het volgende worden gecontroleerd:

    -   Het aantal geslaagde en mislukte inschrijvingen zijn naar verwachting.

    -   De gebruikersproductiviteit:

        -   Bedrijfsresources zoals VPN, Wi-Fi-, e-mail en certificaten functioneren naar behoren.

        -   De gebruikers kunnen toegang krijgen tot de aangeboden apps.

    -   Gegevensbeveiliging:

        -   Nalevingsrapportage

        -   De beveiliging van mobiele apps is doorgevoerd

-   Wanneer u tevreden bent over de eerste fase van de migratie, herhaalt u de migratiecyclus (zoals hieronder beschreven onder Normale migratiecyclus) voor de volgende fase.

-   Herhaal de gefaseerde cycli totdat alle gebruikers naar Intune zijn gemigreerd.

-   Zorg ervoor dat het helpdeskteam er klaar voor is om gedurende de migratiecampagne ondersteuning te bieden aan de eindgebruikers. Hanteer een migratie op vrijwillige basis totdat u een idee hebt van de werkbelasting voor ondersteuningsgesprekken.

-   Stel pas deadlines voor de inschrijving in als de ondersteuning voor de resterende gebruikers kan worden verwerkt door de helpdesk.

> [!IMPORTANT] 
> Configureer niet zowel Intune als uw bestaande MDM-oplossing van derden zo dat deze gebruikmaken van toegangsbeheer voor resources als Exchange of SharePoint Online. Daarnaast mogen apparaten maar in één oplossing tegelijk worden ingeschreven.

## <a name="next-steps"></a>Volgende stappen

[Fase 2: communicatieplan](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

