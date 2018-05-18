---
title: Apparaatdetails weergeven met Microsoft Intune - Azure | Microsoft Docs
description: Bekijk uw apparaatdetails, waaronder informatie over het besturingssysteem, de opslagruimte, de fabrikant en het model. Bekijk een lijst met geïnstalleerde apps, controleer de beleidsregels voor naleving en stel TeamViewer in met Microsoft Intune in Azure. Vergelijkbaar met het bekijken van de inventaris van de apparaten die u beheert.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f66c0695c7e3d1f4bb7a5ca3abceeb13f6af41f2
ms.sourcegitcommit: 3c4ea8d6809a63042705b5ed4f25ba80f522070e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2018
---
# <a name="see-device-details-in-intune"></a>Apparaatdetails bekijken in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

De functie **Apparaten** biedt meer informatie over de apparaten die u beheert, zoals over de hardware en welke apps zijn geïnstalleerd.

In dit artikel leest u hoe u al uw apparaten en hun eigenschappen kunt bekijken in Azure Portal.

## <a name="view-the-device-details"></a>Apparaatdetails weergeven

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** > **Alle apparaten** en selecteer een van de apparaten in de lijst om de details ervan te openen:

   - **Overzicht** toont de apparaatnaam en een lijst met enkele belangrijke eigenschappen van het apparaat, inclusief of het een BYOD-apparaat (Bring Your Own Device) is, wanneer het apparaat is ingecheckt, en meer. Selecteer **Meer** voor de volgende opties:
     - Bedrijfsgegevens verwijderen
     - Het apparaat verwijderen
     - Het apparaat op afstand vergrendelen
     - Wissen
     - Een externe hulpsessie starten
   - Gebruik **Eigenschappen** om een [apparaatcategorie die u maakt](device-group-mapping.md) toe te wijzen en wijzig de eigendom van het apparaat naar een persoonlijk apparaat of een bedrijfsapparaat.
   - **Hardware** bevat veel details over het apparaat, zoals de apparaat-id, het besturingssysteem en de versie, opslagruimte, het model en de fabrikant, instellingen voor voorwaardelijke toegang en meer details.
   - Bij **Gedetecteerde toepassingen** staan alle apps vermeld die volgens Intune op het apparaat zijn geïnstalleerd, en de appversies. U kunt de lijst met apps ook naar een CSV-bestand **exporteren**.
   - Bij **Apparaatnaleving** staan alle toegewezen nalevingsbeleidsregels en wordt vermeld of het apparaat compatibel of niet compatibel is.
   - Bij **Apparaatconfiguratie** ziet u het configuratiebeleid van alle apparaten die aan het apparaat zijn toegewezen en wordt vermeld of het beleid is geslaagd of mislukt.

Intune maakt alleen op apparaten in bedrijfseigendom een lijst met apps. Apps op persoonlijke apparaten worden niet gecontroleerd. Bij pc's met Windows 10 worden alleen de moderne apps vermeld voor apparaten in bedrijfseigendom. Intune verzamelt geen informatie over Win32-apps op het apparaat. Afhankelijk van de provider die door de apparaten wordt gebruikt, worden mogelijk niet alle apps vermeld.

|Platform|Voor apparaten die persoonlijk eigendom zijn|Voor apparaten die bedrijfseigendom zijn|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (zonder de Configuration Manager-client)|Alleen beheerde apps|Alleen beheerde apps|
|Windows 8.1 (zonder de Configuration Manager-client)|Alleen beheerde apps|Alleen beheerde apps|  
|Windows Phone 8|Alleen beheerde apps|Alleen beheerde apps|  
|Windows RT|Alleen beheerde apps|Alleen beheerde apps|  
|iOS|Alleen beheerde apps|Alle apps die op het apparaat zijn geïnstalleerd|
|macOS|Alle apps die op het apparaat zijn geïnstalleerd|Alle apps die op het apparaat zijn geïnstalleerd|  
|Android|Alleen beheerde apps|Alle apps die op het apparaat zijn geïnstalleerd|  

## <a name="next-steps"></a>Volgende stappen
Bekijk wat u nog meer kunt doen om met Intune uw [apparaten te beheren](device-management.md).