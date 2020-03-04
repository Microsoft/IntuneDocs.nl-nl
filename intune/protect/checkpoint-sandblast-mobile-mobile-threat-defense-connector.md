---
title: Check Point SandBlast MTD instellen
titleSuffix: Microsoft Intune
description: Meer informatie over de integratie van Intune met Check Point SandBlast Mobile Threat Defense om toegang tot uw bedrijfsresources met mobiele apparaten te bepalen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/21/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2471a48a1222448a2a45c7813bbb513cefda5276
ms.sourcegitcommit: 045ca42cad6f86024af9a38a380535f42a6b4bef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782011"
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Check Point SandBlast Mobile Threat Defense-connector met Intune

U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Check Point SandBlast Mobile, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens die worden verzameld op apparaten met de Check Point SandBlast Mobile-app.

U kunt beleidsregels voor voorwaardelijke toegang configureren op basis van de Check Point SandBlast Mobile-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-conforme apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

> [!NOTE]
> Deze Mobile Threat Defense-leverancier wordt niet ondersteund voor niet-ingeschreven apparaten.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Hoe kunt u met Intune en Check Point SandBlast Mobile uw bedrijfsresources beter beveiligen?

Met de Check Point SandBlast Mobile-app voor Android of iOS/iPadOS worden telemetriegegevens vastgelegd over het bestandssysteem, de netwerkstack, apparaten en apps waar dergelijke gegevens beschikbaar zijn. Met de app worden die gegevens vervolgens verzonden naar de Check Point SandBlast-cloudservice om te bepalen hoe groot het risico van bedreigingen is voor het mobiele apparaat.

Het Intune-nalevingsbeleid voor apparaten bevat een regel voor Check Point SandBlast Mobile Threat Defense die is gebaseerd op de Check Point SandBlast-risicoanalyse. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld. Als het apparaat niet aan het beleid blijkt te voldoen, wordt de toegang van gebruikers tot resources als Exchange Online en SharePoint Online geblokkeerd. Gebruikers ontvangen ook richtlijnen van de Check Point SandBlast Mobile-app die op hun apparaat is geïnstalleerd, zodat ze het probleem kunnen oplossen en weer toegang kunnen krijgen tot bedrijfsresources.

Hier volgen enkele veelvoorkomende scenario's:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps

Als er op apparaten schadelijke apps zoals malware worden gedetecteerd, kunt u apparaten blokkeren totdat de bedreiging is opgelost:

- Verbinding met bedrijfs-e-mail

- Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk

- Toegang tot bedrijfs-apps

**Blokkeren wanneer er schadelijke apps zijn gedetecteerd:**

![Check Point MTD blokkeert wanneer er schadelijke apps worden gedetecteerd](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-2.PNG)

**Toegang na herstel:**

![Check Point MTD-toegang verleend](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-3.PNG)

### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk

Detecteer bedreigingen zoals **man-in-the-middle**-aanvallen in het netwerk en beveilig de toegang tot Wi-Fi-netwerken op basis van het apparaatrisico.

**Netwerktoegang via Wi-Fi blokkeren:**

![Check Point MTD blokkeert de netwerktoegang via Wi-Fi](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-4.PNG)

**Toegang na herstel:**

![Wi-Fi-toegang toegestaan door Check Point MTD](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-5.PNG)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk

Detecteer bedreigingen zoals **man-in-the-middle**-aanvallen in het netwerk en voorkom synchronisatie van bedrijfsbestanden op basis van het apparaatrisico.

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd:**

![Check Point MTD blokkeert de toegang tot SharePoint Online](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-6.PNG)

**Toegang na herstel:**

![Check Point MTD staat toegang tot SharePoint Online toe](./media/checkpoint-sandblast-mobile-mobile-threat-defense-connector/checkpoint-MTD-7.PNG)

## <a name="supported-platforms"></a>Ondersteunde platforms

- **Android 4.1 en hoger**

- **iOS 8 en hoger**

## <a name="pre-requisites"></a>Vereisten

- Azure Active Directory Premium

- Microsoft Intune-abonnement

- Check Point SandBlast Mobile Threat Defense-abonnement
  - Zie de[CheckPoint SandBlast-website](https://www.checkpoint.com/) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

- [CheckPoint SandBlast integreren in Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [De mobiele Check Point SandBlast-app instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Een CheckPoint SandBlast-nalevingsbeleid voor mobiele apparaten maken](mtd-device-compliance-policy-create.md)

- [De CheckPoint SandBlast Mobile MTD-connector inschakelen](mtd-connector-enable.md)
