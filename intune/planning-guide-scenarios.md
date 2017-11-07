---
title: Use-casescenario's bepalen
description: In dit artikel wordt beschreven hoe u gebruiksscenario's en subgebruiksscenario's voor een cloudimplementatie van Microsoft Intune. kunt identificeren.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 864f99f52e0c8b46307f1ec24d11da51d8f52662
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2017
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a>Gebruiksscenario's voor het beheer van mobiele apparaten identificeren

Het identificeren van uw gebruiksscenario's is een belangrijk onderdeel van het planningsproces voor een geslaagde Intune-implementatie. Gebruiksscenario's zijn nuttig omdat u hiermee de gebruikers kunt indelen in beheerbare groepen op basis van gebruikerstype of rol en het eigendom van het gebruikersapparaat (bijvoorbeeld eigendom van een bedrijf of individu).

Laten we een paar voorbeelden bespreken aan de hand waarvan uw organisatie gebruiksscenario's voor Intune, evenals organisatiegroepen en platformen voor mobiele apparaten voor elke gebruikssituatie kan identificeren.

## <a name="device-ownership"></a>Apparaateigendom
U kunt als eerste nagaan wat de doelen en doelstellingen van de Intune-implementatie van uw organisatie zijn om de belangrijkste gebruiksscenario's voor uw implementatie te bepalen. Beantwoord voor uw Intune-implementatieplan de volgende vragen:

-   Bent u van plan om apparaten in bedrijfseigendom te ondersteunen?

-   Bent u van plan om BYOD-apparaten te ondersteunen?

U hoeft niet per se te kiezen tussen deze opties. Het kan zijn dat u beide vormen van apparaateigendom moet ondersteunen om de doelen van uw organisatie te realiseren. De subgebruikssituaties zullen duidelijk maken in welke omstandigheden de verschillende beleidsregels voor apparaatbeheer moeten worden toegepast.

### <a name="user-type-or-device-role"></a>Gebruikerstype of apparaatrol

Bepaal of elk gebruiksscenario ook subgebruikssituaties omvat. Uw organisatie kan bijvoorbeeld hebben vastgesteld dat een bedrijfsgebruiksscenario moet worden ondersteund dat aanvullende subgebruikssituaties omvat die zijn gebaseerd op gebruikerstype of apparaatrol, zoals:

-   Informatiemedewerker

-   Executive

-   Kiosk

Hier volgen enkele voorbeelden van gebruiksscenario's en subgebruiksscenario's:

| **Use cases** | **Subgebruikssituaties** |
|:---:|:---:|
| Zakelijk | Informatiemedewerker |              
| Zakelijk | Leidinggevenden |           
| Zakelijk | Kiosk |
| BYOD | Informatiemedewerker |           
| BYOD | Leidinggevenden |

U kunt [een sjabloon van de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de gebruiksscenario's en subgebruiksscenario's van uw organisatie in te voeren.

## <a name="organizational-groups-for-your-scenarios"></a>Organisatiegroepen voor uw scenario's

Nu moet u vaststellen welke organisatiegroepen aan elk gebruiksscenario en subgebruiksscenario zijn gekoppeld. Bijvoorbeeld:

| **Use cases** | **Subgebruikssituaties** | **Organisatiegroepen** |
|:---:|:---:|:---:|
| Zakelijk | Informatiemedewerker | HR, Financiën |               
| Zakelijk | Executive | HR, Financiën |            
| Bedrijf | Kiosk | Retail |
| BYOD | Informatiemedewerker | Marketing, Verkoop |            
| BYOD | Executive | Marketing, Verkoop |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Platformen voor mobiele apparaten voor uw scenario's

In de volgende stap stelt u vast welke platformen voor mobiele apparaten zijn gekoppeld aan elk gebruiksscenario. Dat kunnen er meer dan één zijn.

Uw bedrijfsgebruiksscenario kan bijvoorbeeld de iOS- en Android Samsung KNOX-apparaatplatformen ondersteunen. Uw BYOD-beleid kan ondersteuning omvatten voor aanvullende platformen voor mobiele apparaten, zoals Android (behalve Samsung KNOX) en Windows 10 Mobile. Voortbouwend op de voorgaande voorbeelden hebben we platformen voor mobiele apparaten gekoppeld aan elk gebruiksscenario.

| **Use cases** | **Subgebruikssituaties** | **Groepen** | **Apparaatplatformen** |   
|:---:|:---:|:---:|:---:|
| Zakelijk | Informatiemedewerker | HR, Financiën | iOS |                                                           
| Zakelijk | Leidinggevenden | HR, Financiën | iOS |                                                           
| Zakelijk | Kiosk | Retail | Android |
| BYOD | Informatiemedewerker | Marketing, Verkoop | iOS |                                                           
| BYOD | Leidinggevenden | Marketing, Verkoop | iOS |

## <a name="next-steps"></a>Volgende stappen

De volgende sectie bevat richtlijnen over het [identificeren van de Intune-vereisten voor elk use-casescenario](planning-guide-requirements.md).
