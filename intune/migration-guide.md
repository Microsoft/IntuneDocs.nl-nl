---
title: Migratiehandleiding voor het beheer van mobiele apparaten in Intune
description: Deze handleiding bevat stapsgewijze instructies voor klanten die migreren van een externe MDM-provider naar Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="intune-migration-guide"></a>Migratiehandleiding voor Intune

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Afbeelding voor de migratiehandleiding voor Intune](./media/MDM-migration-guide-art.PNG)

Een geslaagde migratie naar Intune begint met een goed onderbouwd plan waarin rekening wordt gehouden met de huidige MDM-omgeving (Mobile Device Management), bedrijfsdoelstellingen en technische vereisten. Daarnaast moet u de steun hebben van de belangrijkste belanghebbenden die met u samenwerken aan uw migratieplan.

In deze handleiding vindt u stapsgewijze instructies voor de migratie van een externe MDM-provider naar Microsoft Intune.

## <a name="whats-included-in-this-guide"></a>Wat is er opgenomen in deze handleiding?

Deze handleiding is onderverdeeld in twee fasen die beide taken, strategieën en tactische richtlijnen bevatten, aan de hand waarvan u stapsgewijs de gehele procedure voor de migratie naar Intune MDM doorloopt.

-   [Fase 1: Intune voorbereiden op het beheer van mobiele apparaten] (migration-guide-prepare.md)

    -   [De vereisten voor de MDM-migratie beoordelen](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Basisconfiguratie](migration-guide-setup.md)

    -   [Beheerbeleid voor apparaten en apps configureren](migration-guide-configure-policies.md)

    -   [Het beveiligingsbeleid voor apps configureren] (migration-guide-app-protection-policies.md)

    -   [Speciale overwegingen bij migratie](migration-guide-considerations.md)

-   [Fase 2: migratiecampagne](migration-guide-campaign.md)

    -   [Communicatieplan](migration-guide-communication-plan.md)

    -   [Eindgebruikers accepteren door middel van voorwaardelijke toegang](migration-guide-drive-adoption.md)
    
    -   [Normale migratiecyclus](migration-guide-cycle.md)
        -   [Migratiebewaking](migration-guide-cycle.md#monitoring-migration)
        -   [Na de migratie](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Aannames

-   U hebt Intune al geëvalueerd in een omgeving voor het testen van een concept en hebt besloten om het te gebruiken voor het beheer van mobiele apparaten in uw organisatie.

-   U bent al bekend met Intune en de bijbehorende functies. 

> [!NOTE]
> Bekijk de [Intune-evaluatiehandleiding](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune), als u meer vertrouwd wilt raken met Intune voordat u de migratie uitvoert.

## <a name="before-you-begin"></a>Voordat u begint

Het is belangrijk dat u beseft dat de nieuwe Intune-implementatie kan afwijken van uw oude MDM-implementatie. In tegenstelling tot traditionele MDM-services speelt bij Intune het toegangsbeheer op basis van identiteit een centrale rol. Er is dus geen netwerkproxyapparaat vereist om de toegang tot bedrijfsgegevens vanaf mobiele apparaten buiten de netwerkperimeter van de organisatie te beheren. Microsoft biedt oplossingen voor het beveiligen van gegevensservices in de cloud zelf via een pakket van goed geïntegreerde cloudservices, gezamenlijk aangeduid als Enterprise Client + Security.

-   Raadpleeg de [algemene manieren om Intune te gebruiken](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="next-steps"></a>Volgende stappen

[Fase 1: Intune voorbereiden op het beheer van mobiele apparaten] (migration-guide-prepare.md)
