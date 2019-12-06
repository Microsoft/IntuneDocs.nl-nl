---
title: Updatenalevingsrapporten voor Windows-updates gebruiken in Microsoft Intune
titleSuffix: Microsoft Intune
description: Gebruik OMS-updatenaleving om rapportgegevens weer te geven voor de Windows-updates die u met Intune implementeert.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0de98a0820e15a09c2b3724b216359580327259e
ms.sourcegitcommit: ce518a5dfe62c546a77f32ef372f36efbaad473f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2019
ms.locfileid: "74465721"
---
# <a name="intune-compliance-reports-for-updates"></a>Intune-nalevingsrapporten voor updates

Wanneer u Intune gebruikt om Windows-updates te implementeren naar Windows 10-apparaten, bekijkt u details over updatenaleving met behulp van Intune of de gratis oplossing *Updatenaleving*, wat deel uitmaakt van de Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Intune gebruiken

U kunt als volgt een beleidsrapport weergeven met de implementatiestatus voor de Windows 10-update-ringen die u hebt geconfigureerd:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Overzicht** > **Status van software-update**. Hier wordt algemene informatie weergegeven over de status van de update-ringen die u hebt toegewezen.

3. Als u meer details wilt zien, selecteert u **Bewaken**. Selecteer onder **Software-updates** de optie **Implementatiestatus per updatering** en kies de implementatiering die u wilt controleren.

   Kies in de sectie **Bewaken** een van de volgende rapporten om meer gedetailleerde informatie over de implementatiering weer te geven:

   - **Apparaatstatus**: hier wordt de configuratiestatus van het apparaat weergegeven. Zie [Update deviceConfigurationDeviceStatus]( https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationdevicestatus-update?view=graph-rest-1.0) voor meer details.

   - **Gebruikersstatus**: hier wordt de gebruikersnaam, de status en de laatste rapportagedatum weergegeven. Zie [List deviceConfigurationUserStatuses](https://docs.microsoft.com/graph/api/intune-deviceconfig-deviceconfigurationuserstatus-list?view=graph-rest-1.0) voor meer details.

   - **Updatestatus van de eindgebruiker**: hier wordt de updatestatus van het Windows-apparaat weergegeven. Zie [windowsUpdateState](https://docs.microsoft.com/graph/api/resources/intune-shared-windowsupdatestate?view=graph-rest-beta) voor meer details.

## <a name="use-update-compliance"></a>Updatenaleving gebruiken

Met de Windows Analytics-oplossing [Updatenaleving](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) kunt u de Windows 10 update-implementaties bewaken. Updatenaleving wordt u aangeboden via Azure Portal en is gratis beschikbaar voor apparaten die aan de [voorwaarden](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites) voldoen.  

Wanneer u deze oplossing gebruikt, kunt u een commerciële id implementeren op elk van uw door Intune beheerde Windows 10-apparaten waarvoor u over de naleving van updates wilt rapporteren.  

In Intune worden de OMA-URI-instellingen van een aangepast beleid gebruikt om de commerciële id te configureren. Zie [Beleidsinstellingen voor Windows 10-apparaten in Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).  

Het pad voor de OMA-URI (hoofdlettergevoelig) voor het configureren van de commerciële id is: *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*  

U kunt bijvoorbeeld de volgende waarden gebruiken in **OMA-URI-instelling toevoegen of bewerken**:

- **Naam van instelling**: Commerciële id voor Windows Analytics
- **Beschrijving van instelling**: Commerciële id voor Windows Analytics-oplossingen configureren
- **OMA-URI** (hoofdlettergevoelig): *./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID*
- **Gegevenstype**: Tekenreeks
- **Waarde**: \<gebruik de GUID die wordt weergegeven op het tabblad Windows-telemetrie in uw OMS-werkruimte>

> [!NOTE]
> Zie [DMClient configuratieserviceprovider (CSP)]( https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp) voor meer informatie over MS DM Server.

## <a name="next-steps"></a>Volgende stappen

[Software-updates beheren in Intune](windows-update-for-business-configure.md)
