---
title: Uw apparaten bekijken met Microsoft Intune - Azure | Microsoft Docs
description: "Bekijk uw apparaatdetails, waaronder informatie over het besturingssysteem, de opbergruimte, de fabrikant, het model en meer. Bekijk een lijst met geïnstalleerde apps, controleer de beleidsregels voor naleving, stel TeamViewer in en doe nog meer met Microsoft Intune in Azure. Vergelijkbaar met het bekijken van de inventaris van de apparaten die u beheert."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 934ba0853f8bee851f7027580c276a9fff911b7f
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="see-device-details-in-intune"></a>Apparaatdetails bekijken in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De functie **Apparaten** biedt meer informatie over de apparaten die u beheert, zoals over de hardware en welke apps zijn geïnstalleerd. 

In dit artikel leest u hoe u al uw apparaten en hun eigenschappen kunt bekijken in Azure Portal.

## <a name="view-your-device-details"></a>Uw apparaatdetails bekijken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten**. In Apparaten hebt u verschillende opties:

  - **Overzicht**: informatie over apparaten die u hebt ingeschreven en de besturingssystemen die op elk apparaat worden uitgevoerd.
  - **Beheren**: kies **Alle apparaten** of **Azure AD-apparaten** voor een overzicht van de apparaten die u beheert.
    Selecteer een van de apparaten in de lijst. Hiermee opent u <*apparaatnaam*> **Overzicht**, waar u het volgende kunt selecteren:
    - **Overzicht**: bekijk de naam van het apparaat, de eigenaar, of het een BYOD-apparaat is (Bring Your Own Device), wanneer het apparaat is ingecheckt en meer
    - **Hardware**: bekijk hoeveel beschikbare opslagruimte er is, wat het model is, wie de fabrikant is en meer gegevens over het apparaat
    - **Gedetecteerde toepassingen**: hiermee ziet u een lijst met alle apps die volgens Intune op het apparaat zijn geïnstalleerd
    - **Apparaatnaleving**: hiermee geeft u de nalevingsstatus weer voor alle beleidsregels voor naleving die zijn toegewezen aan het apparaat
    - **Apparaatconfiguratie**: hiermee geeft u de nalevingsstatus weer van alle beleidsregels voor apparaatconfiguratie die zijn toegewezen aan het apparaat
- **Bewaken**: kies **Apparaatacties** voor een overzicht van acties die zijn uitgevoerd op apparaten die u beheert en de huidige status hiervan. **Auditlogboeken** biedt inzicht in de status van verschillende taken.
- **Installatie** > **TeamViewer-connector**: hiermee kunt u met behulp van de TeamViewer-software extern beheer configureren op apparaten. Zie [Hulp op afstand verlenen voor Android-apparaten die worden beheerd met Intune](device-profile-android-teamviewer.md) voor meer informatie.

Intune maakt alleen op apparaten in bedrijfseigendom een lijst met apps. Apps op persoonlijke apparaten worden niet gecontroleerd. Bij pc's met Windows 10 worden alleen de moderne apps vermeld voor apparaten in bedrijfseigendom. Intune verzamelt geen informatie over Win32-apps op het apparaat. Afhankelijk van welke provider op de apparaten wordt gebruikt, worden mogelijk niet alle apps vermeld.

## <a name="next-steps"></a>Volgende stappen
Bekijk wat u nog meer kunt doen om met Intune uw [apparaten te beheren](device-management.md).
