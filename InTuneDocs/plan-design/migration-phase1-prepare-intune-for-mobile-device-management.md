---
title: Intune voorbereiden op het beheer van mobiele apparaten | Microsoft Docs
description: Lezers kunnen aan de hand van dit artikel hun bedrijf en de technische vereisten evalueren voordat ze naar Intune migreren.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 2e7bcedebdf777db64a9ec90aa758822634ed435
ms.lasthandoff: 03/28/2017


---

# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a>Fase 1: Intune voorbereiden op het beheer van mobiele apparaten (MDM)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Alvorens in te gaan op de details van de Intune-configuratie, komen eerst de vereisten voor het beheer van mobiele apparaten voor uw organisatie aan bod. Het kan handig zijn om rapporten uit te voeren van actieve gebruikers bij uw huidige MDM-provider om te bepalen wat de kritieke gebruikersgroepen zijn. Vervolgens kunt u beginnen met het beantwoorden van de vragen onder het [gedeelte MDM-vereisten beoordelen](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>MDM-vereisten beoordelen

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Wat voor apparaten moet u beheren?

-   Voor welke [platformen](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers) moet u ondersteuning bieden?

-   Zijn de apparaten waarvoor u ondersteuning wilt bieden bedrijfsapparaten of BYOD-apparaten?

-   Wat voor verbinding wordt er gebruikt? Wi-Fi, mobiel, VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Wat moeten de gebruikers op de beheerde apparaten doen?

-   Moet u apps verstrekken aan uw eindgebruikers?

-   Gebruikt u aangepaste LOB-apps? Of gebruikt u alleen openbare Store-apps?

-   Moet u e-mailaccounts inrichten?

### <a name="what-kinds-of-users"></a>Welke soorten gebruikers zijn er?

-   Hoeveel gebruikers maken gebruik van één apparaat?

-   Welke gebruiksvoorwaarden hebt u nodig?

    -   Zorg ervoor dat uw juridische afdeling in een vroeg stadium hierbij wordt betrokken.

    -   Wat voor lokalisatie is er vereist?

-   Zijn de gebruikers bekend bent met technologie en IT in het algemeen?

### <a name="what-is-your-device-security-policy"></a>Wat voor beveiligingsbeleid voor apparaten hanteert u? 

-   Wilt u gebruikmaken van versleuteling op apparaatniveau?

-   De lengte van de wachtwoordcode/pincode voor apparaten?

-   Moet u apparaatfuncties uitschakelen of bepaald gedrag van apparaten beperken?

    -   U kunt een aantal platformspecifieke instellingen beheren met apparaatconfiguratieprofielen, zoals het uitschakelen van de camera en het vergrendelen van apparaten in de modus voor één app.
<br></br>
-   Voor welke soorten verificatie moet u ondersteuning bieden?

    -   Als u gebruikmaakt van verificatie op basis van certificaten, welke certificaten moeten er dan worden verstrekt?

        -   Intune kan certificaten verstrekken met resourcetoegangsprofielen voor ingeschreven apparaten.
<br></br>
    -   Voor wat voor PKI-infrastructuur (Public Key Infrastructure) moet u ondersteuning bieden?
<br></br>
-   Moet u voor VPN (Virtual Private Network) ondersteuning bieden op apparaat- of appniveau?

    -   Intune kan VPN-configuraties verstrekken voor externe VPN-providers.
<br></br>
-   Kunnen er tijdelijke uitzonderingen worden gemaakt voor bepaalde vereisten om uitvaltijd te voorkomen? Of moeten apparaten met toegang altijd voldoen aan alle beveiligingsvereisten?

## <a name="additional-information"></a>Aanvullende informatie

-   Bekijk voor meer gedetailleerde voorbeelden deze [casestudy's](https://customers.microsoft.com/en-US/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) uit verschillende bedrijfstakken om te zien hoe organisaties de vereisten voor het beheer van mobiele apparaten hebben geëvalueerd.

## <a name="next-steps"></a>Volgende stappen

[Fase 1: basisconfiguratie](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

