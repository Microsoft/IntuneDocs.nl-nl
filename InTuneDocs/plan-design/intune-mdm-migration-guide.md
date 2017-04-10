---
title: Migratiehandleiding voor het beheer van mobiele apparaten in Intune | Microsoft Docs
description: Deze handleiding bevat stapsgewijze instructies voor klanten die migreren van een externe MDM-provider naar Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 444cb61ea57b92924a681c564a1a913f4204ea89
ms.lasthandoff: 03/28/2017


---

# <a name="intune-migration-guide"></a>Migratiehandleiding voor Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Afbeelding voor de migratiehandleiding voor Intune](../media/MDM-migration-guide-art.PNG)

Een geslaagde migratie naar Intune begint met een goed onderbouwd plan waarin rekening wordt gehouden met de huidige MDM-omgeving, bedrijfsdoelstellingen en technische vereisten. Daarnaast moet u de steun hebben van de belangrijkste belanghebbenden die met u samenwerken aan uw migratieplan.

In deze handleiding vindt u stapsgewijze instructies voor de migratie van een externe MDM-provider naar Microsoft Intune.

## <a name="whats-included-in-this-guide"></a>Wat is er opgenomen in deze handleiding?

Deze handleiding is onderverdeeld in twee fasen die beide taken, strategieën en tactische richtlijnen bevatten, aan de hand waarvan u stapsgewijs de gehele procedure voor de migratie naar Intune MDM doorloopt.

-   [Fase 1: Intune voorbereiden op het beheer van mobiele apparaten](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [De vereisten voor de MDM-migratie beoordelen](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Basisconfiguratie](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

    -   [Beheerbeleid voor apparaten en apps configureren](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Beveiligingsbeleid voor apps configureren (optioneel)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Speciale overwegingen bij migraties](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

-   [Fase 2: migratiecampagne](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

    -   [Communicatieplan](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

    -   [Eindgebruikers accepteren door middel van voorwaardelijke toegang](https://docs.microsoft.com/intune/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Normale migratiecyclus](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)
        -   [Migratiebewaking](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Na de migratie](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Aannames

-   U hebt Intune al geëvalueerd in een omgeving voor het testen van een concept en hebt besloten om het te gebruiken voor het beheer van mobiele apparaten in uw organisatie.

-   U bent al bekend met Intune en de bijbehorende functies. 

> [!NOTE]
> Bekijk de [Intune-evaluatiehandleiding](https://docs.microsoft.com/intune/understand-explore/sign-up-for-30-day-trial-microsoft-intune), als u meer vertrouwd wilt raken met Intune voordat u de migratie uitvoert.

## <a name="before-you-begin"></a>Voordat u begint

Het is belangrijk dat u beseft dat de nieuwe Intune-implementatie kan afwijken van uw oude MDM-implementatie. In tegenstelling tot traditionele MDM-services speelt bij Intune het toegangsbeheer op basis van identiteit een centrale rol. Er is dus geen netwerkproxyapparaat vereist om de toegang tot bedrijfsgegevens vanaf mobiele apparaten buiten de netwerkperimeter van de organisatie te beheren. Microsoft biedt oplossingen voor het beveiligen van gegevensservices in de cloud zelf via een pakket van goed geïntegreerde cloudservices, gezamenlijk aangeduid als Enterprise Client + Security.

-   Neem de [gebruikelijke manieren om Intune te gebruiken](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune) door en begin met het beantwoorden van de vragen onder [Fase 1: MDM-vereisten beoordelen](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Volgende stappen

[Fase 1: Intune voorbereiden op het beheer van mobiele apparaten](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

