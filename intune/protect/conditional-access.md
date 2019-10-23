---
title: Voorwaardelijke toegang met Microsoft Intune
titleSuffix: Microsoft Intune
description: Meer informatie over het definiëren van de voorwaarden waaraan gebruikers, apparaten en apps moeten voldoen voor toegang tot bedrijfsresources in Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb9dd31c87d27ec7885d25269988cfd968e81e08
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504562"
---
# <a name="learn-about-conditional-access-and-intune"></a>Meer informatie over voorwaardelijke toegang en Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Voorwaardelijke toegang verwijst naar de manieren waarop u de apparaten en apps kunt beheren die toestemming hebben om verbinding te maken met uw e-mail- en bedrijfsgegevens. In dit onderwerp vindt u meer informatie over op apparaten en apps gebaseerde voorwaardelijke toegang en vindt u algemene scenario's voor het gebruiken van voorwaardelijke toegang met Intune.

Enterprise Mobility + Security (EMS) Conditional Access is geen zelfstandig product, maar een oplossing die kan worden gebruikt voor alle services en producten die onderdeel zijn van de EMS. Met deze oplossing kunt u een gedetailleerd toegangsbeheer configureren om uw bedrijfsgegevens te beveiligen, terwijl gebruikers de mogelijkheid wordt geboden om op elk apparaat en op elke locatie optimaal te presteren.

U kunt voorwaarden opgeven die de toegang tot uw bedrijfsgegevens beperken op basis van de locatie, de apparaat- en gebruikersstatus en de gevoeligheid van een toepassing.

> [!NOTE] 
> Voorwaardelijke toegang kan nu ook worden toegepast voor [Office 365-services](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access).

![Architectuurdiagram voor voorwaardelijke toegang](./media/conditional-access/ca-diagram-1.png)

## <a name="use-conditional-access-with-intune"></a>Voorwaardelijke toegang met Intune gebruiken

Voorwaardelijke toegang is een Azure Active Directory-functie die is opgenomen in een Azure Active Directory Premium-licentie. Deze mogelijkheid wordt verbeterd door Intune door het toevoegen van nalevingsbeleid voor mobiele apparaten en beheer van mobiele apps aan de oplossing. 

![Intune en voorwaardelijke toegang bij het gebruik van EMS](./media/conditional-access/intune-with-ca-1.png)

Manieren om voorwaardelijke toegang met Intune te gebruiken:

- **Voorwaardelijke toegang op basis van het apparaat**

  - Voorwaardelijke toegang voor Exchange On-Premises

  - Voorwaardelijke toegang op basis van netwerktoegangsbeheer

  - Voorwaardelijke toegang op basis van het apparaatrisico

  - Voorwaardelijke toegang voor Windows-pc's

    - In bedrijfseigendom

    - BYOD (Bring Your Own Device)

- **Voorwaardelijke toegang op basis van apps**

## <a name="next-steps"></a>Volgende stappen

[Gebruikelijke manieren om voorwaardelijke toegang met Intune te gebruiken](conditional-access-intune-common-ways-use.md)
