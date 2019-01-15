---
title: Voorwaardelijke toegang met Microsoft Intune| Microsoft Intune
description: Meer informatie over het definiëren van de voorwaarden waaraan gebruikers, apparaten en apps moeten voldoen voor toegang tot bedrijfsresources in Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: f25fe74c9506d2179c683156821ef9afb218128a
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816562"
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

Voorwaardelijke toegang is een Azure Active Directory-functie die is opgenomen in een Azure Active Directory Premium-licentie. Deze mogelijkheid wordt verbeterd door Intune door het toevoegen van nalevingsbeleid voor mobiele apparaten en beheer van mobiele apps aan de oplossing. 

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
