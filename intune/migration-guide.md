---
title: Migratiehandleiding voor het beheer van mobiele apparaten in Intune
description: In deze handleiding vindt u instructies voor de migratie van een externe MDM-provider naar Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 888624530fe77f22ea9391b688fa9f9b92f0ac75
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="intune-migration-guide"></a>Migratiehandleiding voor Intune

![Afbeelding voor de migratiehandleiding voor Intune](./media/MDM-migration-guide-art.PNG)

Een geslaagde migratie naar Intune begint met een goed onderbouwd plan waarin rekening wordt gehouden met uw huidige MDM-omgeving (Mobile Device Management), bedrijfsdoelstellingen en technische vereisten. Daarnaast moet u de steun hebben van de belangrijkste belanghebbenden die met u samenwerken aan uw migratieplan.

In deze handleiding vindt u instructies voor de migratie van een externe MDM-provider naar Intune.

## <a name="whats-included-in-this-guide"></a>Wat is er opgenomen in deze handleiding?

In deze handleiding wordt de migratie in twee fasen onderverdeeld die taken, strategieën en tactische richtlijnen omvatten, aan de hand waarvan u stapsgewijs de gehele procedure voor de migratie naar Intune MDM doorloopt.

-   [Fase 1: Intune voorbereiden op het beheer van mobiele apparaten](migration-guide-prepare.md)

    -   [De vereisten voor de MDM-migratie beoordelen](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Basisconfiguratie](migration-guide-setup.md)

    -   [Beheerbeleid voor apparaten en apps configureren](migration-guide-configure-policies.md)

    -   [Beveiligingsbeleid voor apps configureren](migration-guide-app-protection-policies.md)

    -   [Speciale overwegingen bij migratie](migration-guide-considerations.md)

-   [Fase 2: Migratiecampagne](migration-guide-campaign.md)

    -   [Communicatieplanning](migration-guide-communication-plan.md)

    -   [Eindgebruikers accepteren door middel van voorwaardelijke toegang](migration-guide-drive-adoption.md)

    -   [Normale migratiecyclus](migration-guide-cycle.md)
        -   [Migratiebewaking](migration-guide-cycle.md#monitoring-migration)
        -   [Na de migratie](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Aannames

-   U hebt Intune al geëvalueerd in een omgeving voor het testen van een concept en hebt besloten om het te gebruiken voor het beheer van mobiele apparaten in uw organisatie.

-   U bent al bekend met Intune en de bijbehorende functies.

## <a name="before-you-begin"></a>Voordat u begint

Het is belangrijk dat u beseft dat de nieuwe Intune-implementatie kan afwijken van uw oude MDM-implementatie. In tegenstelling tot traditionele MDM-services speelt bij Intune het toegangsbeheer op basis van identiteit een centrale rol. Er is dus geen netwerkproxyapparaat vereist om de toegang tot bedrijfsgegevens vanaf mobiele apparaten buiten de netwerkperimeter van de organisatie te beheren. Microsoft biedt oplossingen voor het beveiligen van gegevensservices in de cloud zelf via een pakket van goed geïntegreerde cloudservices, gezamenlijk aangeduid als Enterprise Client + Security.

-   Raadpleeg de [algemene manieren om Intune te gebruiken](common-scenarios.md).

## <a name="next-steps"></a>Volgende stappen

[Fase 1: Intune voorbereiden op het beheer van mobiele apparaten](migration-guide-prepare.md)
