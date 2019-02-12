---
title: Use-casescenario's bepalen
titlesuffix: Microsoft Intune
description: In dit artikel wordt beschreven hoe u gebruiksscenario's en subgebruiksscenario's voor een cloudimplementatie van Microsoft Intune. kunt identificeren.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: de72bc56bf1ec0e7f1555d889ae0684c1162fdb9
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55841399"
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
| Bedrijf | Informatiemedewerker |              
| Bedrijf | Leidinggevenden |           
| Bedrijf | Kiosk |
| BYOD | Informatiemedewerker |           
| BYOD | Leidinggevenden |

U kunt [een sjabloon van de bovenstaande tabel downloaden](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) om de gebruiksscenario's en subgebruiksscenario's van uw organisatie in te voeren.

## <a name="organizational-groups-for-your-scenarios"></a>Organisatiegroepen voor uw scenario's

Nu moet u vaststellen welke organisatiegroepen aan elk gebruiksscenario en subgebruiksscenario zijn gekoppeld. Bijvoorbeeld:

| **Use cases** | **Subgebruikssituaties** | **Organisatiegroepen** |
|:---:|:---:|:---:|
| Bedrijf | Informatiemedewerker | HR, Financiën |               
| Bedrijf | Executive | HR, Financiën |            
| Bedrijf | Kiosk | Retail |
| BYOD | Informatiemedewerker | Marketing, Verkoop |            
| BYOD | Executive | Marketing, Verkoop |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Platformen voor mobiele apparaten voor uw scenario's

In de volgende stap stelt u vast welke platformen voor mobiele apparaten zijn gekoppeld aan elk gebruiksscenario. Dat kunnen er meer dan één zijn.

Uw bedrijfsgebruiksscenario kan bijvoorbeeld de iOS- en Android Samsung Knox-apparaatplatforms ondersteunen. Uw BYOD-beleid kan ondersteuning omvatten voor aanvullende platformen voor mobiele apparaten, zoals Android (behalve Samsung Knox) en Windows 10 Mobile. Voortbouwend op de voorgaande voorbeelden hebben we platformen voor mobiele apparaten gekoppeld aan elk gebruiksscenario.

| **Use cases** | **Subgebruikssituaties** | **Groepen** | **Apparaatplatformen** |   
|:---:|:---:|:---:|:---:|
| Bedrijf | Informatiemedewerker | HR, Financiën | iOS |                                                           
| Bedrijf | Leidinggevenden | HR, Financiën | iOS |                                                           
| Bedrijf | Kiosk | Retail | Android |
| BYOD | Informatiemedewerker | Marketing, Verkoop | iOS |                                                           
| BYOD | Leidinggevenden | Marketing, Verkoop | iOS |

## <a name="next-steps"></a>Volgende stappen

De volgende sectie bevat richtlijnen over het [identificeren van de Intune-vereisten voor elk use-casescenario](planning-guide-requirements.md).
