---
title: Voorwaardelijke toegang met Microsoft Intune
titlesuffix: ''
description: Meer informatie over het definiëren van de voorwaarden waaraan gebruikers, apparaten en apps moeten voldoen voor toegang tot bedrijfsresources in Microsoft Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 03/06/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a62166792570c5bb81391d05d1cbc3f8486543a4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022336"
---
# <a name="whats-conditional-access"></a>Wat is voorwaardelijke toegang?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Voorwaardelijke toegang verwijst naar de manieren waarop u de apparaten en apps die daarvoor toestemming hebben, kunt beheren om verbinding te maken met uw e-mail en bedrijfsgegevens. In dit onderwerp vindt u meer informatie over apparaat- en appgebaseerde voorwaardelijke toegang en vindt u algemene scenario's voor het gebruiken van voorwaardelijke toegang met Intune.

Enterprise Mobility + Security (EMS) Conditional Access is geen zelfstandig product, maar een oplossing die kan worden gebruikt voor alle services en producten die onderdeel zijn van de EMS. Met deze oplossing kunt u een gedetailleerd toegangsbeheer configureren om uw bedrijfsgegevens te beveiligen, terwijl gebruikers de mogelijkheid wordt geboden om op elk apparaat en op elke locatie optimaal te presteren.

U kunt voorwaarden opgeven die de toegang tot uw bedrijfsgegevens beperken op basis van de locatie, de apparaat- en gebruikersstatus en de gevoeligheid van een toepassing.

> [!NOTE] 
> Voorwaardelijke toegang kan nu ook worden toegepast voor [Office 365-services](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).

![Architectuurdiagram voor voorwaardelijke toegang](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Voorwaardelijke toegang met Intune

Intune voegt nalevingsbeleid voor mobiele apparaten en app-beheer toe voor de ondersteuning van de EMS Conditional Access-oplossing.

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
