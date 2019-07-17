---
title: Intune voorbereiden op het beheer van mobiele apparaten
titleSuffix: Microsoft Intune
description: Evalueer uw bedrijfs- en technische vereisten voordat u migreert naar Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 29ae889e99a843a8569782bad2b1303c7bb4304c
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882842"
---
# <a name="phase-1-prepare-microsoft-intune-for-mobile-device-management-mdm"></a>Fase 1: Microsoft Intune voorbereiden op het beheer van mobiele apparaten (MDM)

Alvorens in te gaan op de details van de Intune-configuratie, komen eerst de vereisten voor het beheer van mobiele apparaten voor uw organisatie aan bod. Het kan handig zijn rapporten uit te voeren van actieve gebruikers in uw huidige MDM-provider voor het identificeren van de kritieke gebruikersgroepen. Vervolgens kunt u beginnen met het aanpakken van de vragen in de sectie [MDM-vereisten beoordelen](migration-guide-prepare.md#assess-mdm-requirements).

## <a name="assess-mdm-requirements"></a>MDM-vereisten beoordelen

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a>Wat voor apparaten moet u beheren?

- Voor welke [platformen](supported-devices-browsers.md) moet u ondersteuning bieden?

- Zijn de apparaten waarvoor u ondersteuning wilt bieden bedrijfs- of persoonlijke apparaten?

- Wat voor verbinding gebruikt u? Wi-Fi, mobiel, VPN?

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a>Wat moeten de gebruikers op de beheerde apparaten doen?

- Moet u apps verstrekken aan uw eindgebruikers?

- Gebruikt u aangepaste LOB-apps? Of gebruikt u alleen openbare Store-apps?

- Moet u e-mailaccounts inrichten?

### <a name="what-kinds-of-users"></a>Welke soorten gebruikers zijn er?

- Hoeveel gebruikers maken gebruik van één apparaat?

- Welke gebruiksvoorwaarden hebt u nodig?

  - Zorg ervoor dat uw juridische afdeling in een vroeg stadium hierbij wordt betrokken.
  - Wat voor lokalisatie is er vereist?

- Zijn de gebruikers bekend bent met technologie en IT in het algemeen?

### <a name="what-is-your-device-security-policy"></a>Wat voor beveiligingsbeleid voor apparaten hanteert u?

- Wilt u gebruikmaken van versleuteling op apparaatniveau?

- Wat zijn de lengtes van uw huidige apparaatwachtwoordcode/-pin-code?

- Moet u apparaatfuncties uitschakelen of bepaald gedrag van apparaten beperken? U kunt een aantal platformspecifieke instellingen beheren met apparaatconfiguratieprofielen, zoals:
  - Camera uitschakelen
  - Vergrendelen op de modus voor enkele toepassing<br/>

- Voor welke soorten verificatie moet u ondersteuning bieden? Als u gebruikmaakt van verificatie op basis van certificaten, welke certificaten moeten er dan worden verstrekt?
  - Intune kan certificaten verstrekken met resourcetoegangsprofielen voor ingeschreven apparaten.
  - Voor wat voor PKI-infrastructuur (Public Key Infrastructure) moet u ondersteuning bieden?
  <br></br>
- Moet u voor VPN (Virtual Private Network) ondersteuning bieden op apparaat- of appniveau?

  - Intune kan VPN-configuraties verstrekken voor externe VPN-providers.
  <br/><br/>
- Kunnen er tijdelijke uitzonderingen worden gemaakt voor bepaalde vereisten om uitvaltijd te voorkomen? Of moeten apparaten met toegang altijd voldoen aan alle beveiligingsvereisten?

## <a name="next-steps"></a>Volgende stappen
Zie deze [casestudy's](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) uit verschillende bedrijfstakken om te zien hoe organisaties de vereisten voor het beheer van mobiele apparaten hebben geëvalueerd.

Controleer de [basisinstellingen Intune](migration-guide-setup.md).
