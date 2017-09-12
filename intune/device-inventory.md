---
title: Inventaris van Intune-apparaten weergeven
titlesuffix: Azure portal
description: "Meer informatie over hoe u de apparaten weergeeft die u beheert met Intune en over de hardware en geïnstalleerde apps."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45ef07d68248ab4c0c6f3a3e6e8da83cb210c5c7
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-view-intune-device-inventory"></a>De inventaris van Intune-apparaten weergeven


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De workload **Apparaten** workload gives you insights into the devices you manage, including their hardware capabilities, and the apps installed on them. 

De inventaris van apparaten weergeven:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.

Kies nu een van de volgende opties:

- **Overzicht**: informatie over apparaten die u hebt ingeschreven en de besturingssystemen die op elk apparaat worden uitgevoerd.
- **Beheren**: kies **Alle apparaten** voor een overzicht van de apparaten die u beheert.
    Selecteer een van deze apparaten in de lijst om de blade <*apparaatnaam*> **Overzicht** te kiezen, waar u kunt een van de volgende opties kunt selecteren:
    - **Overzicht**: algemene informatie weergeven over het apparaat, waaronder de naam van het apparaat, de eigenaar, of het wel of geen BYOD-apparaat is en wanneer het voor het laatst is ingecheckt.
    ![Overzicht van apparaat](./media/device-overview.png)
    - **Hardware**: meer gedetailleerde informatie weergeven over het apparaat, zoals de beschikbare opslagruimte, het model en de fabrikant.
    ![Beheerde hardware-inventaris van apparaten](./media/hardware-inventory.png)
    - **Gedetecteerde toepassingen**: een lijst weergeven met alle apps die op het apparaat zijn geïnstalleerd.
    ![Knooppunt Gedetecteerde apps](./media/detected-applications.png)
    


    - **Apparaatnaleving**: de nalevingsstatus weergeven van alle beleidsregels voor nalevingsbeleid die zijn toegewezen aan het apparaat.
    - **Apparaatconfiguratie**: de nalevingsstatus weergeven van alle beleidsregels voor beleid voor apparaatconfiguratie die zijn toegewezen aan het apparaat.
- **Controleren**: kies **Apparaatacties** voor een overzicht van apparaatacties die zijn uitgevoerd op apparaten die u beheert en de huidige status van deze acties.
- **Installatie** > **TeamViewer-connector**: hiermee kunt u met behulp van de TeamViewer-software extern beheer configureren op apparaten. Zie [Hulp op afstand verlenen voor Android-apparaten die worden beheerd met Intune](/intune/device-profile-android-teamviewer) voor meer informatie.

>[!NOTE]
> Intune verzamelt app-inventaris alleen op apparaten in bedrijfseigendom. Apps worden niet geïnventariseerd op persoonlijke apparaten. Voor pc's met Windows 10 wordt alleen de moderne app-inventaris verzameld op apparaten in bedrijfseigendom. Intune verzamelt geen informatie over Win32-apps op het apparaat.
> Afhankelijk van de provider die u met apparaten gebruikt, worden mogelijk niet alle inventarisitems verzameld.
