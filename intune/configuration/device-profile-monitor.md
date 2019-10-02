---
title: Apparaatprofielen weergeven met Microsoft Intune - Azure | Microsoft Docs
description: Bekijk en beheer de gegevens voor apparaatconfiguratieprofielen in Microsoft Intune. Bekijk een grafiek van het aantal apparaten dat is toegewezen aan een profiel, en bekijk aan welke apparaten profielen zijn toegewezen of op welke apparaten een profiel is geïmplementeerd. Kan tevens fouten opsporen in profielen met conflicterende instellingen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd87b33d36d17f32945eb591307eb55241173ca9
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724071"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Apparaatprofielen controleren in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune bevat functies in Azure Portal om u te helpen bij het controleren en beheren van uw apparaatconfiguratieprofielen. U kunt bijvoorbeeld de status van een profiel controleren, zien welke apparaten zijn toegewezen en de eigenschappen van een profiel bijwerken.

## <a name="view-existing-profiles"></a>Bestaande profielen weergeven

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer **Apparaatconfiguratie** > **Profielen**.

Al uw bestaande profielen worden weergegeven en bevatten gegevens zoals het platform en laat zien of het profiel is toegewezen aan een of meer apparaten.

## <a name="view-details-on-a-profile"></a>Gegevens van een profiel weergeven

Nadat u een apparaatprofiel hebt gemaakt, biedt Intune grafieken. In deze grafieken wordt de status van een profiel weergegeven, zoals of het is toegewezen aan apparaten en of op het apparaat een conflict bestaat.

1. Selecteer een bestaand profiel. Selecteer bijvoorbeeld een macOS-profiel.
2. Selecteer het tabblad **Overzicht**.

    In de bovenste grafiek wordt het aantal apparaten weergegeven dat is toegewezen aan het specifieke apparaatprofiel. Als het apparaatconfiguratieprofiel bijvoorbeeld is toegepast op macOS-apparaten, geeft de grafiek het aantal macOS-apparaten weer.

    De grafiek geeft ook voor andere platforms het aantal apparaten weer dat is toegewezen aan hetzelfde apparaatprofiel. Zo wordt bijvoorbeeld het aantal niet-macOS-apparaten weergegeven.

    ![Het aantal apparaten weergeven dat is toegewezen aan het apparaatprofiel](./media/device-profile-monitor/device-configuration-profile-graphical-chart.png)

    In de onderste grafiek wordt het aantal gebruikers weergegeven dat is toegewezen aan het specifieke apparaatprofiel. Als het apparaatconfiguratieprofiel bijvoorbeeld is toegepast op macOS-gebruikers, geeft de grafiek het aantal macOS-gebruikers weer.

3. Selecteer de cirkel in de bovenste grafiek. **Apparaatstatus** wordt geopend.

    De apparaten die zijn toegewezen aan het profiel, worden vermeld, en er wordt weergegeven of het profiel is geïmplementeerd. U ziet ook dat alleen de apparaten met het specifieke platform (bijvoorbeeld macOS) worden vermeld.

    Sluit **Apparaatstatus**.

4. Selecteer de cirkel in de onderste grafiek. **Gebruikersstatus** wordt geopend. 

    De gebruikers die zijn toegewezen aan het profiel, worden vermeld, en er wordt weergegeven of het profiel is geïmplementeerd. U ziet ook dat alleen de gebruikers met het specifieke platform (bijvoorbeeld macOS) worden vermeld.

    Sluit **Gebruikersstatus**.

5. Selecteer in de lijst **Profielen** een specifiek profiel. U kunt ook bestaande eigenschappen wijzigen:
    - **Eigenschappen**: Wijzig de naam, of werk alle bestaande instellingen bij.
    - **Toewijzingen**: Neem apparaten op waarop het apparaat moet worden toegepast, of sluit deze uit. Kies **Groepen selecteren** om specifieke groepen te kiezen.
    - **Apparaatstatus**: De apparaten die zijn toegewezen aan het profiel, worden vermeld, en er wordt weergegeven of het profiel is geïmplementeerd. U kunt een specifiek apparaat selecteren om meer details op te halen, inclusief de geïnstalleerde apps.
    - **Gebruikersstatus**: Geeft de gebruikersnamen weer met apparaten die worden beïnvloed door dit profiel, en of het profiel is geïmplementeerd. U kunt een specifieke gebruiker selecteren om nog meer details op te halen.
    - **Status per instelling**: Filtert de uitvoer door de afzonderlijke instellingen binnen het profiel weer te geven en laat zien of de instelling is toegewezen.

## <a name="view-conflicts"></a>Conflicten weergeven

In **Apparaten** > **Alle apparaten** kunt u alle instellingen bekijken die een conflict veroorzaken. Als er een conflict optreedt, krijgt u ook alle configuratieprofielen met deze instelling te zien. Beheerders kunnen deze functie gebruiken om problemen op te sporen bij deze profielen en eventuele discrepanties op te lossen.

1. Selecteer in Intune **Apparaten** > **Alle apparaten** > selecteer een bestaand apparaat in de lijst. Een eindgebruiker kan de naam van het apparaat ophalen van de bedrijfsportal-app.
2. Selecteer **Apparaatconfiguratie**. Al het configuratiebeleid dat betrekking heeft op het apparaat wordt weergegeven.
3. Selecteer het beleid. Zo ziet u alle instellingen in dat beleid die van toepassing zijn op het apparaat. Als een apparaat een status **Conflict** heeft, selecteert u die rij. In het nieuwe venster ziet u alle profielen en de profielnamen met de instelling die het conflict veroorzaakt.

Nu u weet wat de conflicterende instelling is en welke beleidsregels die instelling omvatten, moet het eenvoudiger zijn om het conflict op te lossen. 

## <a name="next-steps"></a>Volgende stappen
[Gebruikers- en apparaatprofielen toewijzen](../device-profile-assign.md)  
[Veelvoorkomende problemen met apparaatprofielen en oplossingen](device-profile-troubleshoot.md)
