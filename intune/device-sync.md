---
title: Apparaten synchroniseren met Intune
titleSuffix: Intune on Azure
description: Lees hier hoe u apparaten met Intune kunt synchroniseren om het meest recente beleid en de meest recente acties te verkrijgen.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 870eb3bf255cda92952a908596485d7b53259fb4
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/09/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Apparaten synchroniseren met Intune om het meest recente beleid en de meest recente acties te verkrijgen


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met apparaatactie **Synchroniseren** wordt het geselecteerde apparaat direct ingecheckt bij Intune. Wanneer een apparaat wordt ingecheckt, worden direct eventuele openstaande acties of toegewezen beleidsregels ontvangen die erop zijn toegepast.  Met deze actie kunt u toegewezen beleid meteen controleren en in het geval van problemen direct aanpassen, zonder dat u hoeft te wachten op de volgende geplande check-in.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: ondersteund
- Windows Phone: ondersteund
- iOS: ondersteund
- Mac OS: ondersteund
- Android: ondersteund

## <a name="how-to-sync-a-device"></a>Apparaten synchroniseren

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies een apparaat in de lijst met apparaten die u beheert en kies vervolgens de externe actie **Synchroniseren**.
7. Kies **Ja** om de actie te bevestigen.

## <a name="next-steps"></a>Volgende stappen

Kies **Apparaatacties** om de status van de synchronisatieactie te zien. 
