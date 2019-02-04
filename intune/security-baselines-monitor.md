---
title: Controleer het succes of falen van beveiligingsbasislijnen in Microsoft Intune - Azure | Microsoft Docs
description: Controleer de fout-, conflict- en successtatus bij het implementeren van beveiligingsbasislijnen voor gebruikers en apparaten in Microsoft Intune MDM. Leer hoe u problemen oplost met clientlogboeken en bekijk de rapportagefuncties in Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28a98a20e5f0b5181628da46ccd662f1f8f503dd
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2019
ms.locfileid: "55070210"
---
# <a name="monitor-the-security-baseline-and-profile-in-microsoft-intune"></a>Controleer de beveiligingsbasislijn en het beveiligingsprofiel in Microsoft Intune

Er zijn verschillende controleopties bij het gebruik van beveiligingsbasislijnen. U kunt het beveiligingsbasislijnprofiel bewaken dat op uw gebruikers en apparaten van toepassing is. U kunt tevens de daadwerkelijke basislijn controleren evenals apparaten die (al dan niet) overeenkomen met de aanbevolen waarden.

Dit artikel bespreekt beide controleopties.

In [Security baselines in Intune](security-baselines.md) (Beveiligingsbasislijnen in Intune) vindt u meer informatie over de basislijnbeveiligingsfunctie in Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Bewaak de basislijn en uw apparaten

Als u de basislijn controleert, krijgt u inzicht in de beveiligingsstatus van uw apparaten op basis van de aanbevelingen van Microsoft.

> [!NOTE]
> Nadat een basislijn voor het eerst is toegewezen, kan het tot wel 24 uur duren om rapporten bij te werken. Daarna duurt een update maximaal 6 uur.

1. Selecteer in [Azure Portal](https://portal.azure.com/) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer **Beveiligingsbasislijnen (preview)**> selecteer een basislijn.
3. In **Overzicht** toont het diagram hoeveel apparaten worden beïnvloed door de basislijn die u hebt gekozen evenals de verschillende statussen:

    ![Controleer de status van de apparaten](./media/security-baselines-monitor/overview.png)

    De volgende statussen zijn beschikbaar:

    - **Komt overeen met de basislijn**: Alle instellingen in de basislijn komen overeen met de aanbevolen instellingen.
    - **Komt niet overeen met de basislijn**: Minstens één instelling in de basislijn komt niet overeen met de aanbevolen instellingen.
    - **Onjuist geconfigureerd**: Minstens één instelling is niet juist geconfigureerd. Deze status betekent dat de instelling een conflict of fout ervaart of in behandeling is.
    - **Niet van toepassing**: Minstens één instelling is niet van toepassing en wordt niet toegepast.

4. Selecteer een van de statussen die apparaten heeft. Selecteer bijvoorbeeld de status **Onjuist geconfigureerd**.

5. Er wordt een lijst weergegeven met alle apparaten die deze status hebben. Selecteer een specifiek apparaat voor meer informatie. 

    Selecteer in het volgende voorbeeld **Apparaatconfiguratie** > Selecteer het profiel met een foutstatus:

    ![Controleer de status van de apparaten](./media/security-baselines-monitor/device-configuration-profile-list.png)

    Selecteer het foutenprofiel. Er wordt een lijst met alle instellingen in het profiel en hun status weergegeven. Nu kunt u schuiven om de instelling te vinden die de fout veroorzaakt:

    ![Bekijk de instelling die de fout veroorzaakt](./media/security-baselines-monitor/profile-with-error-status.png)

Gebruik deze rapportage om instellingen in een profiel te bekijken die een probleem veroorzaken. Krijg daarnaast meer informatie over beleidsregels en profielen die zijn geïmplementeerd op apparaten.

> [!NOTE]
> Wanneer een eigenschap in de basislijn is ingesteld op **Niet geconfigureerd**, wordt de instelling genegeerd en gelden er geen beperkingen. De eigenschap wordt niet in rapporten weergegeven.

## <a name="monitor-the-profile"></a>Bewaak het profiel

Het bewaken van het profiel geeft u inzicht in de implementatiestatus van uw apparaten, maar niet in de beveiligingsstatus op basis van de aanbevelingen uit de basislijn.

1. Selecteer in Intune **Beveiligingsbasislijnen** > selecteer een basislijn > **Gemaakte profielen**.

2. Selecteer een profiel. In **Overzicht** geeft de afbeelding weer aan hoeveel apparaten en gebruikers dit profiel is toegewezen:

    ![Bekijk aan hoeveel apparaten en gebruikers het beveiligingsbasislijnprofiel is toegewezen](./media/security-baselines-monitor/existing-profile-overview.png)

3. Onder **Eigenschappen** > **beheren** staat een overzicht van alle instellingen in de basislijn. U kunt deze instellingen eveneens wijzigen:

    ![Bekijk en update instellingen in het beveiligingsbasislijnprofiel](./media/security-baselines-monitor/manage-settings.png)

4. In **Bewaken** ziet u de implementatiestatus van het profiel op afzonderlijke apparaten, de status voor elke gebruiker en de status voor elke instelling in de basislijn:

    ![Bekijk de verschillende controleopties voor een beveiligingsbasislijnprofiel](./media/security-baselines-monitor/monitor-status-options.png)

## <a name="troubleshoot-using-per-setting-status"></a>Los problemen op met de status per instelling

U hebt een beveiligingsbasislijn geïmplementeerd, maar de implementatiestatus bevat een fout. De volgende stappen leggen uit hoe u de fout oplost.

1. Selecteer in Intune **Beveiligingsbasislijnen** > selecteer een basislijn > **Gemaakte profielen**.
2. Selecteer een profiel > onder **Bewaken** > **Status per instelling**.
3. De tabel toont alle instellingen en hun status. Selecteer de kolom **Fout** of **Conflict** om te zien welke instelling de fout veroorzaakt.

### <a name="mdm-diagnostic-information"></a>Diagnostische gegevens over MDM

Nu weet u welke instelling de boosdoener is. De volgende stap is om erachter te komen waarom deze instelling een fout of een conflict veroorzaakt. 

Op Windows 10-apparaten is er een ingebouwd rapport met diagnostische gegevens over MDM. Dit rapport bevat standaardwaarden en huidige waarden, benoemt de beleidsregels, geeft aan of het op het apparaat of de gebruiker is geïmplementeerd en meer. Gebruik dit rapport om te bepalen waarom de instelling een conflict of fout veroorzaakt.

1. Ga op het apparaat naar **Instellingen** > **Accounts** > **Toegang tot werk of school**.
2. Selecteer het account > **Info** > **Geavanceerd diagnostisch rapport** > **Rapport maken**.
3. Kies **Exporteren** en open het gegenereerde bestand.
4. Zoek in de verschillende onderdelen van het rapport naar de instelling met de fout of het conflict.

  Zoek bijvoorbeeld in het gedeelte **Ingeschreven configuratiebronnen en doelbronnen** of **Onbeheerd beleid**. Mogelijk komt u erachter waarom deze instelling een fout of conflict veroorzaakt.

[Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10) (MDM-Fouten diagnosticeren in Windows 10) bevat meer informatie over dit ingebouwde rapport.

> [!TIP]
> - Sommige instellingen vermelden tevens de GUID. U kunt deze GUID in het lokale register (regedit) zoeken voor eventuele ingestelde waarden.
> - De Event Viewer-logboeken kunnen ook bepaalde foutinformatie over de problematische instelling bevatten (**Event viewer** > **Logboeken van toepassingen en services** > **Microsoft** > **Windows** > **DeviceManagement-Enterprise-Diagnostics-Provider** > **Beheerder**).

## <a name="next-steps"></a>Volgende stappen

[Bewaak apparaatprofielen](device-profile-monitor.md) en [bekijk veelvoorkomende problemen en oplossingen](device-profile-troubleshoot.md).
