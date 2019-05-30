---
title: Controleer het succes of falen van beveiligingsbasislijnen in Microsoft Intune - Azure | Microsoft Docs
description: Controleer de fout-, conflict- en successtatus bij het implementeren van beveiligingsbasislijnen voor gebruikers en apparaten in Microsoft Intune MDM. Leer hoe u problemen oplost met clientlogboeken en bekijk de rapportagefuncties in Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a87b54dde9afe9803d71f7cbef62f7c55375f51b
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66040644"
---
# <a name="monitor-security-baseline-and-profiles-in-microsoft-intune"></a>De beveiligingsbasislijn en het beveiligingsprofiel controleren in Microsoft Intune  

Intune biedt verschillende opties om uw beveiligingsbasislijnen te bewaken. U kunt het beveiligingsbasislijnprofiel bewaken dat op uw gebruikers en apparaten van toepassing is. U kunt tevens de daadwerkelijke basislijn controleren evenals apparaten die (al dan niet) overeenkomen met de aanbevolen waarden.

Dit artikel bespreekt beide controleopties.

In [Security baselines in Intune](security-baselines.md) (Beveiligingsbasislijnen in Intune) vindt u meer informatie over de basislijnbeveiligingsfunctie in Microsoft Intune.

## <a name="monitor-the-baseline-and-your-devices"></a>Bewaak de basislijn en uw apparaten  

Als u een basislijn controleert, krijgt u inzicht in de beveiligingsstatus van uw apparaten op basis van de aanbevelingen van Microsoft. U kunt deze inzichten weergeven in het overzichtsvenster van de beveiligingsbasislijn op de Intune-console.  Het kan tot 24 uur na de eerste toewijzing van een basislijn duren voordat gegevens worden weergegeven. Latere wijzigingen worden na maximaal zes uur weergegeven.  

Meld u aan bij de [Intune-portal](https://go.microsoft.com/fwlink/?linkid=2090973) om bewakingsgegevens voor de basislijn en apparaten weer te geven. Selecteer vervolgens **Apparaatbeveiliging** > **Beveiligingsbasislijnen (preview-versie)**, selecteer een basislijn en bekijk het **overzichtsvenster**.

In het **overzichtsvenster** staan twee methoden om de status te bewaken:
- **Apparaatweergave**: een samenvatting van het aantal apparaten in elke statuscategorie voor de basislijn.  
- **Per categorie**: een weergave waarbij elke categorie in de basislijn wordt weergegeven, inclusief het percentage apparaten voor elke statusgroep voor elke basislijncategorie. 

Elk apparaat wordt vertegenwoordigd door een van de volgende statussen, die zowel in de *apparaatweergave* als de *weergave per categorie* worden gebruikt:  
- **Komt overeen met de basislijn**: alle instellingen in de basislijn komen overeen met de aanbevolen instellingen.
- **Komt niet overeen met de basislijn**: minstens één instelling in de basislijn komt niet overeen met de aanbevolen instellingen.
- **Onjuist geconfigureerd**: minstens één instelling is niet juist geconfigureerd. Deze status betekent dat de instelling een conflict of fout ervaart of in behandeling is.
- **Niet van toepassing**: minstens één instelling is niet van toepassing en wordt niet toegepast.


### <a name="device-view"></a>Apparaatweergave
In het overzichtsvenster staat een op diagrammen gebaseerde samenvatting van het aantal apparaten met een specifieke status voor de basislijn; **Security baseline posture for assigned Windows 10 devices** (Postuur van de beveiligingsbasislijn voor toegewezen Windows 10-apparaten).  

![Controleer de status van de apparaten](./media/security-baselines-monitor/overview.png)

Als de status van een apparaat afwijkt van verschillende categorieën in de basislijn, wordt het apparaat door één status vertegenwoordigd. De status die het apparaat vertegenwoordigt, is afkomstig uit de volgende volgorde van prioriteit: **Onjuist geconfigureerd**, **Komt niet overeen met basislijn**, **Niet van toepassing**, **Komt overeen met basislijn**.  

Als een apparaat bijvoorbeeld over een instelling beschikt die als *onjuist geconfigureerd* is geclassificeerd en een of meer instellingen die als *Komt niet overeen met basislijn* zijn geclassificeerd, dan wordt het apparaat als *Onjuist geconfigureerd* geclassificeerd.  

Klik op het diagram om in te zoomen en door een lijst met apparaten met verschillende statussen te bladeren. U kunt vervolgens afzonderlijke apparaten uit die lijst selecteren om details over die afzonderlijke apparaten weer te geven. Bijvoorbeeld:
- Selecteer **Apparaatconfiguratie** > selecteer het profiel met een foutstatus:

  ![Controleer de status van de apparaten](./media/security-baselines-monitor/device-configuration-profile-list.png)

- Selecteer het foutenprofiel. Er wordt een lijst met alle instellingen in het profiel en hun status weergegeven. Nu kunt u schuiven om de instelling te vinden die de fout veroorzaakt:

  ![Bekijk de instelling die de fout veroorzaakt](./media/security-baselines-monitor/profile-with-error-status.png)

Gebruik deze rapportage om instellingen in een profiel te bekijken die een probleem veroorzaken. Krijg daarnaast meer informatie over beleidsregels en profielen die zijn geïmplementeerd op apparaten.

> [!NOTE]
> Wanneer een eigenschap in de basislijn is ingesteld op **Niet geconfigureerd**, wordt de instelling genegeerd en gelden er geen beperkingen. De eigenschap wordt niet in rapporten weergegeven.

### <a name="per-category-view"></a>Per categorieweergave
In het overzichtsvenster wordt een grafiek per categorie weergegeven voor de basislijn; **Security baseline posture by category** (Postuur van de beveiligingsbasislijn per categorie).  In deze weergave ziet u elke categorie van de basislijn en wordt het percentage apparaten geïdentificeerd dat in een bepaalde statusclassificiatie voor elk van die categorieën valt. 
 
![Statusweergave per categorie](./media/security-baselines-monitor/monitor-baseline-per-category.png)

De status voor **Komt overeen met basislijn** wordt pas weergegeven wanneer 100% van de apparaten die status voor de categorie hebben.   

U kunt de weergave per categorie sorteren op elke kolom door bovenaan de kolom het pictogram met de pijl omhoog/omlaag te selecteren.  


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
