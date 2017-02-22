---
title: Apparaatnaleving controleren | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u de apparaatnaleving kunt controleren.'
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
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: eb27002f449b3bbebb2a9b4ed780350c71eda881


---
# <a name="how-to-monitor-compliance-in-intune-azure-preview"></a>Naleving controleren in Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Op de blade **Overzicht** kunt u een overzicht bekijken van de status van uw **nalevingsprofielen**.
U kunt interactief op de verschillende grafieken klikken om in te zoomen op de details. Als u meerdere nalevingsprofielen hebt geconfigureerd, kunt u ook de status voor elk beleid weergeven door naar de blade Beleid te gaan en **Rapporten** in de sectie **Beheren** te kiezen.  De details van de rapporten die beschikbaar zijn voor de preview-versie, worden hieronder weergegeven.

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

U kunt inzoomen op de instellingen om meer informatie te bekijken over de profielen waarvoor deze instellingen zijn ingeschakeld en de geconfigureerde waarde van de instelling.



<!--HONumber=Feb17_HO1-->


