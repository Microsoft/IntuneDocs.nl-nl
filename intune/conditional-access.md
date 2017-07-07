---
title: Voorwaardelijke toegang met Intune
titleSuffix: Intune on Azure
description: "Meer informatie over het definiëren van de voorwaarden waaraan gebruikers en apparaten moeten voldoen voor toegang tot bedrijfsresources in Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3e6b720eeed65c81e5f3a4dbf06890ea8fd09ce
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="whats-conditional-access"></a>Wat is voorwaardelijke toegang?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In dit onderwerp wordt de voorwaardelijk toegang besproken zoals van toepassing op Enterprise Mobility + Security (EMS), gevolgd door enkele algemene scenario's voor de toepassing van voorwaardelijke toegang bij het gebruik van Intune.

Enterprise Mobility + Security (EMS) Conditional Access is geen zelfstandig product, maar een oplossing die kan worden gebruikt voor alle services en producten die onderdeel zijn van de EMS. Met deze oplossing kunt u een gedetailleerd toegangsbeheer configureren om uw bedrijfsgegevens te beveiligen, terwijl gebruikers de mogelijkheid wordt geboden om op elk apparaat en op elke locatie optimaal te presteren.

U kunt voorwaarden opgeven die de toegang tot uw bedrijfsgegevens beperken op basis van de locatie, de apparaat- en gebruikersstatus en de gevoeligheid van een toepassing.

> [!NOTE] 
> Voorwaardelijke toegang kan nu ook worden toegepast voor [Office 365-services](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Architectuurdiagram voor voorwaardelijke toegang](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Voorwaardelijke toegang met Intune

Intune voegt nalevingsbeleid voor mobiele apparaten en Mobile Application Management-mogelijkheden toe voor de ondersteuning van de EMS Conditional Access-oplossing.

![Intune en voorwaardelijke toegang bij het gebruik van EMS](./media/intune-with-ca-1.png)

Manieren om voorwaardelijke toegang met Intune te gebruiken:

-   **Voorwaardelijke toegang op basis van het apparaat**

    -   Voorwaardelijke toegang voor Exchange On-Premises

    -   Voorwaardelijke toegang op basis van netwerktoegangsbeheer

    -   Voorwaardelijk op basis van het apparaatrisico

    -   Voorwaardelijke toegang voor Windows-pc's

        -   In bedrijfseigendom

        -   BYOD (Bring Your Own Device)

-   **Voorwaardelijke toegang op basis van apps**

## <a name="next-steps"></a>Volgende stappen

[Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](conditional-access-intune-common-ways-use.md)