---
title: Better Mobile Threat Defense-connector met Intune
titleSuffix: Intune on Azure
description: Stel Better Mobile Threat Defense-connector in met Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a52636a140778f6e78bfe081cda40b36ef2354f
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72509650"
---
# <a name="better-mobile-threat-defense-connector-with-intune"></a>Better Mobile Threat Defense-connector met Intune

U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren met voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Better Mobile, een MDT-oplossing (Mobile Threat Defense) die in Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten waarop de Better Mobile-app wordt uitgevoerd.

U kunt beleidsregels voor voorwaardelijke toegang configureren op basis van de Better Mobile-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-conforme apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

## <a name="how-do-intune-and-better-mobile-help-protect-your-company-resources"></a>Hoe kunt u met Intune en Better Mobile uw bedrijfsresources beter beveiligen?

De Better Mobile-app wordt geïnstalleerd en uitgevoerd op mobiele apparaten. Met deze app legt u telemetrische gegevens vast over het bestandssysteem, de netwerkstack, het apparaat en de apps waar dergelijke gegevens beschikbaar zijn, en verzendt u die gegevens naar Better Mobile om te bepalen hoe groot het risico's voor het apparaat op mobiele bedreigingen is.

Het Intune-nalevingsbeleid voor apparaten bevat een regel voor Better Mobile Threat Defense die is gebaseerd op de Better Mobile-risicoanalyse. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld. Als het apparaat niet aan het beleid blijkt te voldoen, wordt de toegang van gebruikers tot resources als Exchange Online en SharePoint Online geblokkeerd. Gebruikers ontvangen ook richtlijnen van de Better Mobile-app die op hun apparaat is geïnstalleerd, zodat ze het probleem kunnen oplossen en weer toegang kunnen krijgen tot bedrijfsresources.

## <a name="sample-scenarios"></a>Voorbeeldscenario's

Hier volgen enkele veelvoorkomende scenario's.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps

Als er op apparaten schadelijke apps zoals malware worden gedetecteerd, kunt u apparaten blokkeren tegen acties als de volgende totdat de bedreiging is opgelost:

- Verbinding met bedrijfs-e-mail

- Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk

- Toegang tot bedrijfs-apps

**Blokkeren wanneer er schadelijke apps zijn gedetecteerd:**

![Afbeelding waarin gedetecteerde schadelijke apps worden weergegeven](./media/better-mobile-threat-defense-connector/better_mobile_maliciousapps_blocked.png)

**Toegang na herstel:**

![Toegang verleend nadat schadelijke apps zijn gedetecteerd](./media/better-mobile-threat-defense-connector/better_mobile_maliciousapps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk

Bedreigingen voor uw netwerk worden gedetecteerd, zoals **man-in-the-middle-aanvallen**, en de toegang tot Wi-Fi-netwerken wordt beveiligd op basis van apparaatrisico.

**Netwerktoegang via Wi-Fi blokkeren:**

![Netwerktoegang via Wi-Fi blokkeren](./media/better-mobile-threat-defense-connector/better_mobile_network_wifi_blocked.png)

**Toegang na herstel:**

![Afbeelding waarin verleende toegang na herstel wordt weergegeven](./media/better-mobile-threat-defense-connector/better_mobile_network_wifi_unblocked.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk

Bedreigingen voor uw netwerk worden gedetecteerd, zoals **man-in-the-middle-aanvallen**, en synchronisatie van bedrijfsbestanden wordt voorkomen op basis van het apparaatrisico.

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd:**

![SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd](./media/better-mobile-threat-defense-connector/better_mobile_network_spo_blocked.png)

**Toegang na herstel:**

![Voorbeeld waarin na herstel toegang is verleend aan Sharepoint](./media/better-mobile-threat-defense-connector/better_mobile_network_spo_unblocked.png)

## <a name="supported-platforms"></a>Ondersteunde platforms

- **Android 4.1 en hoger**

- **iOS 8.0 en hoger**

## <a name="prerequisites"></a>Vereisten

- Azure Active Directory Premium

- Microsoft Intune-abonnement

- Better Mobile Threat Defense-abonnement

  - Zie de [Better Mobile-website](https://www.better.mobi/) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

- [Better Mobile integreren met Intune](better-mobile-mtd-connector-integration.md)

- [Better Mobile-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Better Mobile-nalevingsbeleid voor apparaten maken](mtd-device-compliance-policy-create.md)

- [Better Mobile MTD-connector inschakelen](mtd-connector-enable.md)
