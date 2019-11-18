---
title: Apparaatprofielen weergeven met Microsoft Intune - Azure | Microsoft Docs
description: Bekijk en beheer de gegevens voor apparaatconfiguratieprofielen in Microsoft Intune. Bekijk een grafiek van het aantal apparaten dat is toegewezen aan een profiel, en bekijk aan welke apparaten profielen zijn toegewezen of op welke apparaten een profiel is geïmplementeerd. Kan tevens fouten opsporen in profielen met conflicterende instellingen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9deaed87-fb4b-4689-ba88-067bc61686d7
ms.reviewer: karthib
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4dc349ef7af2683b4dafeaa1cc09f5b7a727e843
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755306"
---
# <a name="monitor-device-profiles-in-microsoft-intune"></a>Apparaatprofielen controleren in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune bevat functies om u te helpen bij het controleren en beheren van uw apparaatconfiguratieprofielen. U kunt bijvoorbeeld de status van een profiel controleren, zien welke apparaten zijn toegewezen en de eigenschappen van een profiel bijwerken.

## <a name="view-existing-profiles"></a>Bestaande profielen weergeven

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen**.

Al uw bestaande profielen worden weergegeven en bevatten gegevens zoals het platform en laat zien of het profiel is toegewezen aan een of meer apparaten.

## <a name="view-details-on-a-profile"></a>Gegevens van een profiel weergeven

Nadat u een apparaatprofiel hebt gemaakt, biedt Intune grafieken. In deze grafieken wordt de status van een profiel weergegeven, zoals of het is toegewezen aan apparaten en of op het apparaat een conflict bestaat.

1. Selecteer een bestaand profiel. Selecteer bijvoorbeeld een macOS-profiel.
2. Selecteer het tabblad **Overzicht**.

    In de bovenste grafiek wordt het aantal apparaten weergegeven dat is toegewezen aan het apparaatprofiel. Als het apparaatconfiguratieprofiel bijvoorbeeld is toegepast op macOS-apparaten, geeft de grafiek het aantal macOS-apparaten weer.

    De grafiek geeft ook voor andere platforms het aantal apparaten weer dat is toegewezen aan hetzelfde apparaatprofiel. Zo wordt bijvoorbeeld het aantal niet-macOS-apparaten weergegeven.

    ![Het aantal apparaten weergeven dat is toegewezen aan het apparaatprofiel](./media/device-profile-monitor/device-configuration-profile-graphical-chart.png)

    In de onderste grafiek wordt het aantal gebruikers weergegeven dat is toegewezen aan het apparaatprofiel. Als het apparaatconfiguratieprofiel bijvoorbeeld is toegepast op macOS-gebruikers, geeft de grafiek het aantal macOS-gebruikers weer.

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

In **Apparaten** > **Alle apparaten** kunt u alle instellingen bekijken die een conflict veroorzaken. Als er een conflict optreedt, ziet u ook alle configuratieprofielen met deze instelling. Beheerders kunnen deze functie gebruiken om problemen op te sporen bij deze profielen en eventuele discrepanties op te lossen.

1. Selecteer in Intune **Apparaten** > **Alle apparaten** > selecteer een bestaand apparaat in de lijst. Een eindgebruiker kan de naam van het apparaat ophalen van de bedrijfsportal-app.
2. Selecteer **Apparaatconfiguratie**. Al het configuratiebeleid dat betrekking heeft op het apparaat wordt weergegeven.
3. Selecteer het beleid. Zo ziet u alle instellingen in dat beleid die van toepassing zijn op het apparaat. Als een apparaat een status **Conflict** heeft, selecteert u die rij. In het nieuwe venster ziet u alle profielen en de profielnamen met de instelling die het conflict veroorzaakt.

Nu u weet wat de conflicterende instelling is en welke beleidsregels die instelling omvatten, moet het eenvoudiger zijn om het conflict op te lossen. 

## <a name="device-firmware-configuration-interface-profile-reporting"></a>Profielrapport configuratie-interface voor apparaatfirmware

> [!WARNING]
> Bewakingsgegevens van DFCI-profielen worden momenteel gemaakt. Wanneer DFCI in openbare preview is, kunnen bewakingsgegevens ontbreken of onvolledig zijn.

DFCI-profielen worden op basis van instellingen per instelling gerapporteerd, net als andere apparaatconfiguratieprofielen. Afhankelijk van de ondersteuning van de fabrikant voor DFCI zijn sommige instellingen mogelijk niet van toepassing.

Met uw DFCI-profielinstellingen ziet u mogelijk de volgende statussen:

- **Compatibel**: Deze status geeft aan wanneer een instellingswaarde in het profiel overeenkomt met de instelling op het apparaat. Deze status kan zich in de volgende scenario's voordoen:

  - Het DFCI-profiel heeft de instelling in het profiel geconfigureerd.
  - Het apparaat beschikt niet over de hardwarefunctie die wordt beheerd door de instelling en de profielinstelling is **Uitgeschakeld**.
  - UEFI staat DFCI niet toe om de functie uit te schakelen en de profielinstelling is **Ingeschakeld**.
  - Op het apparaat ontbreekt de hardware om de functie uit te schakelen en de profielinstelling is **Ingeschakeld**.

- **Niet van toepassing**: Deze status geeft aan wanneer een instellingswaarde in het profiel is **Ingeschakeld** en de overeenkomende instelling op het apparaat niet is gevonden. Deze status kan zich voordoen als de hardware van het apparaat niet beschikt over de functie.

- **Niet-compatibel**: Deze status geeft aan wanneer een instellingswaarde in het profiel niet overeenkomt met de instelling op het apparaat. Deze status kan zich in de volgende scenario's voordoen:

  - UEFI staat DFCI niet toe om een functie uit te schakelen en de profielinstelling wordt **Uitgeschakeld**.
  - Op het apparaat ontbreekt de hardware om de functie uit te schakelen en de profielinstelling wordt **Uitgeschakeld**.
  - Op het apparaat is niet de nieuwste versie van de DFCI-firmware geïnstalleerd.
  - DFCI wordt uitgeschakeld voordat het wordt ingeschreven bij Intune met behulp van een lokaal 'opt-out'-besturingselement in het UEFI-menu.
  - Het apparaat was geregistreerd bij Intune buiten de Autopilot-inschrijving.
  - Het apparaat is niet geregistreerd voor Autopilot door een Microsoft-cryptografie provider of is rechtstreeks geregistreerd door de OEM.

## <a name="next-steps"></a>Volgende stappen

[Algemene vragen, problemen en oplossingen met apparaatprofielen](device-profile-troubleshoot.md)  
[Beleidsregels en profielen voor het oplossen van problemen in Intune](troubleshoot-policies-in-microsoft-intune.md)
