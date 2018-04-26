---
title: Apparaatdetails weergeven met Microsoft Intune - Azure | Microsoft Docs
description: Bekijk uw apparaatdetails, waaronder informatie over het besturingssysteem, de opslagruimte, de fabrikant en het model. Bekijk een lijst met geïnstalleerde apps, controleer de beleidsregels voor naleving en stel TeamViewer in met Microsoft Intune in Azure. Vergelijkbaar met het bekijken van de inventaris van de apparaten die u beheert.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 404fb301d9ab749f887840208e12388e12d79db4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
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

## <a name="next-steps"></a>Volgende stappen
Bekijk wat u nog meer kunt doen om met Intune uw [apparaten te beheren](device-management.md).