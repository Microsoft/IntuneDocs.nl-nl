---
title: Informatie over levering en timing van app-beveiligingsbeleid
titleSuffix: Microsoft Intune
description: Krijg informatie over de verschillende implementatievensters voor app-beveiligingsbeleid, zodat u weet wanneer wijzigingen op de apparaten van uw eindgebruikers moeten worden weergegeven.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/09/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ec111319-7e02-434f-946b-88647726bf1a
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0ed343f652c4afe87273eeaa4a2e35b7669056d
ms.sourcegitcommit: 637375a390b6e34f9c4415c77b99fe2980bbf554
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2020
ms.locfileid: "75839229"
---
# <a name="understand-app-protection-policy-delivery-timing"></a>Meer informatie over de timing van het leveren van app-beveiligingsbeleid

Krijg informatie over de verschillende implementatievensters voor app-beveiligingsbeleid, zodat u weet wanneer wijzigingen op de apparaten van uw eindgebruikers moeten worden weergegeven.

## <a name="delivery-timing-summary"></a>Samenvatting van leveringstiming

De levering van het toepassingsbeveiligingsbeleid hangt af van de licentiestatus en de Intune-serviceregistratie voor uw gebruikers.  

|    Gebruikersstatus    |    App-beveiligingsgedrag     |    Interval voor opnieuw proberen (zie opmerking)    |    Waarom gebeurt dit?    |
|-----------------------------------------------------|-------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
|    Geen onboarding uitgevoerd voor tenant    |    Wacht op de volgende interval voor opnieuw proberen.  App-beveiliging is niet actief voor de gebruiker.    |    24 uur    |    Vindt plaatst wanneer u de tenant voor Intune niet hebt ingesteld.    |
|    De gebruiker is niet gelicentieerd     |    Wacht op de volgende interval voor opnieuw proberen.  App-beveiliging is niet actief voor de gebruiker.     |    12 uur: Voor deze interval is op Android-apparaten echter Intune APP-SDK versie 5.6.0 of hoger nodig. Anders is de interval voor Android-apparaten 24 uur.   |    Vindt plaats wanneer u de gebruiker geen licentie voor Intune hebt gegeven.    |
|    Geen app-beveiligingsbeleid aan de gebruiker toegewezen    |    Wacht op de volgende interval voor opnieuw proberen.  App-beveiliging is niet actief voor de gebruiker.    |    12 uur        |    Vindt plaats wanneer u geen APP-instellingen aan de gebruiker hebt toegewezen.    |
|    De gebruiker is geregistreerd voor Intune MAM    |    App-beveiliging wordt toegepast volgens de beleidsinstellingen.    Updates treden op basis van de interval voor opnieuw proberen op    |    De Intune-service wordt gebaseerd op de gebruikersbelasting.    Doorgaans 30 min.     |    Vindt plaats wanneer de gebruiker zich heeft geregistreerd bij de Intune-service voor de MAM-configuratie.    |

> [!NOTE]
> Voor intervallen voor opnieuw proberen is mogelijk actief gebruik van de app vereist. Dit houdt in dat de app moet worden geopend en moet worden gebruikt.  Als deze interval 24 uur is en de gebruiker 48 uur wacht met het openen van de app, zal de toepassingsbeveiligingsclient het na 48 uur opnieuw proberen.

## <a name="handling-network-connectivity-issues"></a>Problemen met de netwerkverbinding oplossen

Wanneer de gebruikersregistratie niet kan worden uitgevoerd als gevolg van problemen met de netwerkverbinding, wordt een versnelde interval gebruikt.  De toepassingsbeveiligingsclient probeert het opnieuw in steeds langere intervallen, totdat de interval 60 minuten is of een verbinding tot stand is gebracht.  De client probeert het vervolgens opnieuw in intervallen van 60 minuten, totdat een verbinding tot stand is gebracht. Vervolgens wordt de standaardinterval voor opnieuw proberen weer ingeschakeld, op basis van de gebruikersstatus.

## <a name="next-steps"></a>Volgende stappen

[Licenties toewijzen aan gebruikers zodat ze apparaten kunnen inschrijven bij Intune](../fundamentals/licenses-assign.md)

