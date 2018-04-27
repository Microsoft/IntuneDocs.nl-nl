---
title: Apparaatcompatibiliteit bewaken
titlesuffix: Microsoft Intune
description: Meer informatie over het controleren van de apparaatcompatibiliteit.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0fec00b18bd63986a537549715af84cd44539fbb
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="monitor-device-compliance-in-intune"></a>De apparaatcompatibiliteit controleren in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Op de blade **Overzicht** kunt u een overzicht bekijken van de status van uw **nalevingsprofielen**.
U kunt interactief op de verschillende grafieken klikken om in te zoomen op de details. Als u meerdere nalevingsprofielen hebt geconfigureerd, kunt u de beleidsstatus bekijken op de blade voor beleid onder **Beheren** > **rapporten**.

##  <a name="device-compliance"></a>Apparaatnaleving

In de overzichtsweergave van het rapport met de apparaatnaleving ziet u verzamelde informatie over het aantal apparaten dat als volgt wordt gerapporteerd:

- **Compatibel**: het apparaat is onlangs geëvalueerd en voldoet aan de instellingen voor nalevingsprofielen die u hebt opgegeven.
- **Niet-compatibel**: het apparaat is geëvalueerd en er is bepaald dat het apparaat niet-compatibel is.  Als er een respijtperiode in het profiel is opgegeven, kan het zijn dat de respijtperiode is verlopen waardoor de status van het apparaat Niet-compatibel is.
- **Respijtperiode**: het apparaat is geëvalueerd en er is bepaald dat het apparaat niet-compatibel is. De respijtperiode is echter nog steeds van toepassing voordat het apparaat wordt gemarkeerd als niet-compatibel.

U kunt inzoomen op elke sectie om meer informatie over de afzonderlijke apparaten en gebruikers te bekijken.

## <a name="setting-compliance"></a>Naleving van instelling

Het rapport Naleving van instelling bevat de details voor elke nalevingsinstelling zoals:

- Het aantal apparaten dat niet compatibel is met de instelling.
- Het platform waarop de instelling wordt toegepast.

U kunt inzoomen op de instellingen om meer informatie te bekijken over de profielen waarvoor deze instellingen zijn ingeschakeld en de waarde van de instelling.
