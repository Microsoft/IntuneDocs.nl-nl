---
title: Apparaatprofielen weergeven met Microsoft Intune - Azure | Microsoft Docs
description: Bekijk en beheer de gegevens voor apparaatconfiguratieprofielen in Microsoft Intune. Bekijk een grafiek van het aantal apparaten dat is toegewezen aan een profiel, en bekijk aan welke apparaten profielen zijn toegewezen of op welke apparaten een profiel is geïmplementeerd.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1c2eb08db58940ed575b3dea011395edd6711fc
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/28/2018
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Apparaatprofielen controleren in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune bevat functies in Azure Portal om u te helpen bij het controleren en beheren van uw apparaatconfiguratieprofielen. U kunt bijvoorbeeld de status van een profiel controleren, zien welke apparaten zijn toegewezen en de eigenschappen van een profiel bijwerken.

## <a name="view-existing-profiles"></a>Bestaande profielen weergeven

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Profielen**.

Al uw bestaande profielen worden weergegeven en bevatten gegevens zoals het platform en of het profiel is toegewezen aan een of meer apparaten.

## <a name="view-details-on-a-profile"></a>Gegevens van een profiel weergeven

Nadat u een apparaatprofiel hebt gemaakt, biedt Intune grafieken. In deze grafieken wordt de status van een profiel weergegeven, zoals of het is toegewezen aan apparaten en of op het apparaat een conflict bestaat.

1. Selecteer een bestaand profiel. Selecteer bijvoorbeeld een macOS-profiel.
2. Selecteer het tabblad **Overzicht**.

    In de grafiek wordt het aantal apparaten weergegeven dat is toegewezen aan het specifieke apparaatprofiel. Als het apparaatconfiguratieprofiel bijvoorbeeld is toegepast op macOS-apparaten, geeft de grafiek het aantal macOS-apparaten weer.

    De grafiek geeft ook voor andere platforms het aantal apparaten weer dat is toegewezen aan hetzelfde apparaatprofiel. Zo wordt bijvoorbeeld het aantal niet-macOS-apparaten weergegeven.

    ![Het aantal apparaten weergeven dat is toegewezen aan het apparaatprofiel](./media/device-configuration-profile-graphical-chart.png)

3. Selecteer de cirkel in de grafiek. **Apparaatstatus** wordt geopend.

    De apparaten die zijn toegewezen aan het profiel, worden vermeld, en er wordt weergegeven of het profiel is geïmplementeerd. U ziet ook dat alleen de apparaten met het specifieke platform (bijvoorbeeld macOS) worden vermeld.

    Sluit de apparaatstatusgegevens.

4. In de eigenschappen van het profiel (**Profielen** > selecteer een specifiek profiel) kunt u ook de bestaande eigenschappen wijzigen:
  - **Eigenschappen**: wijzig de naam, of werk alle bestaande instellingen bij.
  - **Toewijzingen**: neem apparaten op waarop het apparaat moet worden toegepast, of sluit deze uit. Kies **Groepen selecteren** om specifieke groepen te kiezen.
  - **Apparaatstatus**: de apparaten die zijn toegewezen aan het profiel, worden vermeld en er wordt weergegeven of het profiel is geïmplementeerd. U kunt een specifiek apparaat selecteren om meer details op te halen, inclusief de geïnstalleerde apps.
  - **Gebruikersstatus**: geeft de gebruikersnamen weer met apparaten die worden beïnvloed door dit profiel, en of het profiel is geïmplementeerd. U kunt een specifieke gebruiker selecteren om nog meer details op te halen.
  - **Status per instelling**: filtert de uitvoer door de afzonderlijke instellingen binnen het profiel weer te geven en laat zien of de instelling is toegewezen.

## <a name="next-steps"></a>Volgende stappen
[Gebruikers- en apparaatprofielen toewijzen](device-profile-assign.md)  
[Veelvoorkomende problemen met apparaatprofielen en oplossingen](device-profile-troubleshoot.md)