---
title: Zimperium MTD-connector met Intune
titleSuffix: Intune on Azure
description: Meer informatie over de integratie van Intune met Zimperium Mobile Threat Defense om toegang tot uw bedrijfsresources met mobiele apparaten te bepalen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/29/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 33d4039e430699c5b8e15c1f9b817d8e2a25d029
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728062"
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a>Zimperium Mobile Threat Defense-connector inschakelen met Intune

U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Zimperium, een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten (MTD) die met Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten waarop de Zimperium-app wordt uitgevoerd.

U kunt het beleid voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Zimperium die wordt ingeschakeld via het Intune-nalevingsbeleid voor apparaten. Met beleid voor risicoanalyse kunt u apparaten die niet conform zijn op basis van gedetecteerde bedreigingen toegang weigeren tot bedrijfsresources.

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a>Hoe kunt u met Intune en Zimperium uw bedrijfsresources beter beveiligen?

De Zimperium-app voor Android of iOS legt telemetriegegevens vast over het bestandssysteem, de netwerkstack, apparaten en apps waar dergelijke gegevens beschikbaar zijn. De app verzendt die gegevens vervolgens naar de Zimperium-cloudservice om te bepalen hoe groot het risico van bedreigingen is voor het mobiele apparaat.

Het Intune-nalevingsbeleid voor apparaten bevat een regel voor Zimperium Mobile Threat Defense die is gebaseerd op de Zimperium-risicoanalyse. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld. Als het apparaat niet aan het beleid blijkt te voldoen, wordt de toegang van gebruikers tot resources als Exchange Online en SharePoint Online geblokkeerd. Gebruikers ontvangen ook richtlijnen van de Zimperium-app die op hun apparaat is geïnstalleerd, zodat ze het probleem kunnen oplossen en weer toegang kunnen krijgen tot bedrijfsresources.

## <a name="sample-scenarios"></a>Voorbeeldscenario's

Zie onderstaande scenario's bij het integreren van Zimperium met Intune:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps

Als er op apparaten schadelijke apps zoals malware worden gedetecteerd, kunt u apparaten blokkeren totdat de bedreiging is opgelost:

- Verbinding met bedrijfs-e-mail

- Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk

- Toegang tot bedrijfs-apps

**Blokkeren wanneer er schadelijke apps zijn gedetecteerd:**

![Conceptafbeelding van detectie van schadelijke apps](./media/zimperium-mobile-threat-defense-connector/Maliciousapps_blocked_Zimperium.png)

**Toegang na herstel:**

![Conceptafbeelding van verleende toegang na herstel](./media/zimperium-mobile-threat-defense-connector/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk

Detecteer bedreigingen zoals **man-in-the-middle**-aanvallen in het netwerk en beveilig de toegang tot Wi-Fi-netwerken op basis van het apparaatrisico.

**Netwerktoegang via Wi-Fi blokkeren:**

![Netwerktoegang via Wi-Fi blokkeren](./media/zimperium-mobile-threat-defense-connector/network_wifi_blocked_Zimperium.png)

**Toegang na herstel:**

![Toegang na herstel](./media/zimperium-mobile-threat-defense-connector/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk

Detecteer bedreigingen zoals **man-in-the-middle**-aanvallen in het netwerk en voorkom synchronisatie van bedrijfsbestanden op basis van het apparaatrisico.

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd:**

![SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd](./media/zimperium-mobile-threat-defense-connector/network_spo_blocked_Zimperium.png)

**Toegang na herstel:**

![Voorbeeld waarin na herstel toegang is verleend aan Sharepoint](./media/zimperium-mobile-threat-defense-connector/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a>Ondersteunde platforms

- **Android 4.1 en hoger**

- **iOS 8 en hoger**

## <a name="prerequisites"></a>Vereisten

- Azure Active Directory Premium

- Microsoft Intune-abonnement

- Zimperium Mobile Threat Defense-abonnement

  - Raadpleeg de [Zimperium-website](https://www.zimperium.com/zips-mobile-ips) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

- [Zimperium integreren met Intune](zimperium-mtd-connector-integration.md)

- [Zimperium-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Een nalevingsbeleid voor Zimperium-apparaten maken](mtd-device-compliance-policy-create.md)

- [Zimperium MTD-connector inschakelen](mtd-connector-enable.md)
