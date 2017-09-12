---
title: Apparaatcompatibiliteit bewaken
titlesuffix: Azure portal
description: Meer informatie over het controleren van de apparaatcompatibiliteit.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 65b156923a38d9b3d976604819ede300f063a88b
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-monitor-device-compliance-in-intune"></a>De apparaatcompatibiliteit controleren in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Op de blade **Overzicht** kunt u een overzicht bekijken van de status van uw **nalevingsprofielen**.
U kunt interactief op de verschillende grafieken klikken om in te zoomen op de details. Als u meerdere nalevingsprofielen hebt geconfigureerd, kunt u ook de status voor elk beleid weergeven door naar de blade Beleid te gaan en **Rapporten** in de sectie **Beheren** te kiezen.  De details van de rapporten die beschikbaar zijn, worden hieronder weergegeven.

##  <a name="device-compliance"></a>Apparaatnaleving

In de overzichtsweergave van het rapport met de apparaatnaleving ziet u als eerste verzamelde informatie over het aantal apparaten dat als volgt wordt gerapporteerd:

- **Compatibel**: het apparaat is onlangs geëvalueerd op naleving en er is bepaald dat het apparaat compatibel is met de nalevingsprofielinstellingen die u hebt opgegeven.
- **Niet-compatibel**: het apparaat is geëvalueerd en er is bepaald dat het apparaat niet-compatibel is.  Als er een respijtperiode in het profiel is opgegeven, kan het zijn dat de respijtperiode is verlopen waardoor de status van het apparaat Niet-compatibel is.
- **Respijtperiode**: het apparaat is geëvalueerd en er is bepaald dat het apparaat niet-compatibel is. De respijtperiode is echter nog steeds van toepassing voordat het apparaat daadwerkelijk wordt gemarkeerd als niet-compatibel.

U kunt inzoomen op elke sectie om meer informatie over de afzonderlijke apparaten en gebruikers te bekijken.

## <a name="setting-compliance"></a>Naleving van instelling

Het rapport Naleving van instelling bevat de details voor alle nalevingsinstellingen zoals:

- Het aantal apparaten dat niet compatibel is met de instelling.
- Het platform waarop de instelling wordt toegepast.

U kunt inzoomen op de instellingen om meer informatie te bekijken over de profielen waarvoor deze instellingen zijn ingeschakeld en de waarde van de instelling.
