---
title: Android-apparaten inschrijven in Intune
titleSuffix: Microsoft Intune
description: Meer informatie over het inschrijven van Android-apparaten in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4a9de31ce7a08edcb7dddc6a65a061c1883021e4
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723590"
---
# <a name="enroll-android-devices"></a>Android-apparaten inschrijven

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Als Intune-beheerder kunt u Android-apparaten op de volgende manieren inschrijven:
- Android Enterprise (biedt een reeks registratie-opties waardoor gebruikers over de meest recente en veilige functies beschikken):
    - [**Apparaten met Android Enterprise-werkprofiel**](android-work-profile-enroll.md): Voor persoonlijke apparaten die zijn gemachtigd voor toegang tot bedrijfsgegevens. Beheerders kunnen werkaccounts, apps en gegevens beheren. Persoonlijke gegevens op het apparaat worden geïsoleerd van bedrijfsgegevens en beheerders hebben geen toegang tot persoonlijke instellingen of gegevens. 
    - [**Toegewezen Android Enterprise-apparaten**](android-kiosk-enroll.md): Voor apparaten in bedrijfseigendom voor eenmalig gebruik, bijvoorbeeld voor digitale ondertekening, het afdrukken van tickets of inventarisbeheer. Beheerders vergrendelen het gebruik van een apparaat voor een beperkt aantal apps en webkoppelingen. Ook wordt voorkomen dat gebruikers andere apps kunnen toevoegen of andere acties op het apparaat kunnen uitvoeren.
    - [**Volledig beheerde Android Enterprise-apparaten**](android-fully-managed-enroll.md): Voor apparaten in bedrijfseigendom voor één gebruiker, die exclusief worden gebruikt voor werk, niet voor persoonlijk gebruik. Beheerders kunnen het hele apparaat beheren en beleidscontroles afdwingen die niet beschikbaar zijn voor werkprofielen. 
- [**Android-apparaatbeheerder**](android-enroll-device-administrator.md), waaronder Samsung Knox Standard-apparaten en [Zebra-apparaten](../configuration/android-zebra-mx-overview.md). 

## <a name="prerequisites"></a>Vereisten

U moet de MDM-instantie instellen op **Microsoft Intune** als voorbereiding op het beheer van mobiele apparaten. Zie [Set the MDM authority](../fundamentals/mdm-authority-set.md) (De MDM-instantie instellen) voor instructies. U stelt de instantie slechts één keer in, wanneer u Intune voor het eerst instelt voor het beheer van mobiele apparaten.

Voor apparaten die zijn gemaakt door Zebra Technologies moet u de bedrijfsportal mogelijk extra machtigingen verlenen, afhankelijk van de mogelijkheden van het specifieke apparaat. [Mobility-extensies op Zebra-apparaten](../configuration/android-zebra-mx-overview.md) bevat meer informatie hierover.

Voor Samsung Knox Standard-apparaten zijn er [meer vereisten](android-samsung-knox-mobile-enroll.md).

## <a name="next-steps"></a>Volgende stappen

- [Inschrijvingen met Android Enterprise-werkprofiel instellen](android-work-profile-enroll.md)
- [Inschrijvingen van toegewezen Android Enterprise-apparaat instellen](android-kiosk-enroll.md)
- [Volledig beheerde Android Enterprise-inschrijvingen instellen](android-fully-managed-enroll.md)
- [Inschrijving van Android-apparaatbeheerder instellen](android-enroll-device-administrator.md)

