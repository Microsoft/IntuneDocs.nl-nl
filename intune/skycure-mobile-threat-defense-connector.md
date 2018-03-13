---
title: Skycure-connector met Intune
titlesuffix: Azure portal
description: Integratie van de Skycure-connector met Intune.
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 333322022882566b55e869e5d6a1a1e2b203b830
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/23/2018
---
# <a name="skycure-mobile-threat-defense-connector"></a>Skycure Mobile Threat Defense-connector

U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren door middel van voorwaardelijke toegang op basis van een risicoanalyse die door Skycure wordt uitgevoerd. Skycure is een oplossing voor de beveiliging tegen bedreigingen op mobiele apparaten die met Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetriegegevens die zijn verzameld op apparaten met Skycure, zoals:

-   Fysieke beveiliging

-   Netwerkbeveiliging

-   Toepassingsbeveiliging

-   Beveiliging tegen zwakke plekken

U kunt beleidsregels voor voorwaardelijke toegang configureren op basis van de Skycure-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-conforme apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a>Hoe kunt u met Intune en Skycure uw bedrijfsresources beter beveiligen?

De mobiele Android- of iOS-app voor Skycure legt telemetriegegevens vast over het bestandssysteem, de netwerkstack, apparaten en apps waar dergelijke gegevens beschikbaar zijn. De app verzendt die gegevens vervolgens naar de Skycure-cloudservice om te bepalen hoe groot het risico van bedreigingen is voor het mobiele apparaat.

Het Intune-nalevingsbeleid voor apparaten bevat een regel voor Skycure Mobile Threat Defense die is gebaseerd op de Skycure-risicoanalyse. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld.

Als het apparaat niet aan het beleid blijkt te voldoen, wordt de toegang tot resources als Exchange Online en SharePoint Online geblokkeerd. Gebruikers op geblokkeerde apparaten ontvangen richtlijnen van de mobiele app voor Skycure zodat ze het probleem kunnen oplossen en weer toegang kunnen krijgen tot bedrijfsresources.

Intune ondersteunt twee modi van integratie met Skycure:

-   **Eenvoudige integratie** op basis van een modus voor alleen-lezen waarbij voor Skycure de apparaten in Intune worden weergegeven.

-   **Volledige integratie** waarbij door Skycure apparaatrisico- en beveiligingsincidentgegevens kunnen worden gemeld aan Intune.

## <a name="sample-scenarios"></a>Voorbeeldscenario's

Hier volgen enkele veelvoorkomende scenario's:

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps

Als er op apparaten schadelijke apps zoals malware worden gedetecteerd, kunt u apparaten blokkeren totdat de bedreiging is opgelost:

-   Verbinding met bedrijfs-e-mail

-   Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk

-   Toegang tot bedrijfs-apps

**Blokkeren wanneer er schadelijke apps zijn gedetecteerd:**

![Schadelijke apps gedetecteerd](./media/skycure-arch-1.png)

**Toegang na herstel:**

![Toegang verleend nadat schadelijke apps zijn gedetecteerd](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk

Detecteer bedreigingen zoals **man-in-the-middle**-aanvallen in het netwerk en beveilig de toegang tot Wi-Fi-netwerken op basis van het apparaatrisico.

**Netwerktoegang via Wi-Fi blokkeren:**

![Netwerktoegang via Wi-Fi blokkeren](./media/skycure-arch-3.png)

**Toegang na herstel:**

![Toegang na herstel](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk

Detecteer bedreigingen zoals **man-in-the-middle**-aanvallen in het netwerk en voorkom synchronisatie van bedrijfsbestanden op basis van het apparaatrisico.

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd:**

![SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd](./media/skycure-arch-5.png)

**Toegang na herstel:**

![Voorbeeld waarin na herstel toegang is verleend aan Sharepoint](./media/skycure-arch-6.png)

## <a name="supported-platforms"></a>Ondersteunde platforms

-   **Android 4.1 en hoger**

-   **iOS 8 en hoger**

## <a name="pre-requisites"></a>Vereisten

-   Azure Active Directory Premium

-   Microsoft Intune-abonnement

-   Skycure Mobile Threat Defense-abonnement

Ga naar de [Skycure-website](https://www.skycure.com/skycure-microsoft-integration/) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

Hier volgen de stappen die u moet uitvoeren om Intune met Skycure te integreren:

- [De integratie van Skycure met Intune instellen](skycure-mtd-connector-integration.md)

- [Skycure-apps, Microsoft Authenticator en het configuratiebeleid voor iOS-apps toevoegen en toewijzen](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Skycure-nalevingsbeleid voor apparaten maken met Intune](mtd-device-compliance-policy-create.md)

- [De Skycure MTD-connector in Intune inschakelen](mtd-connector-enable.md)
