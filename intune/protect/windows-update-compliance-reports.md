---
title: Updatenalevingsrapporten voor Windows-updates gebruiken in Microsoft Intune
titleSuffix: Microsoft Intune
description: Gebruik OMS-updatenaleving om rapportgegevens weer te geven voor de Windows-updates die u met Intune implementeert.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 09f3cafc16d8a08885731aa244a089367c6c0933
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728101"
---
# <a name="intune-compliance-reports-for-updates"></a>Intune-nalevingsrapporten voor updates
Wanneer u Intune gebruikt om Windows-updates te implementeren naar Windows 10-apparaten, bekijkt u details over updatenaleving met behulp van Intune of de gratis oplossing *Updatenaleving*, wat deel uitmaakt van de Microsoft Operations Management Suite (OMS).

## <a name="use-intune"></a>Intune gebruiken
U kunt als volgt een beleidsrapport weergeven met de implementatiestatus voor de Windows 10-update-ringen die u hebt geconfigureerd: 
1. Meld u aan bij [Azure Portal](https://portal.azure.com/).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Software-updates** > **Overzicht**. Hier wordt algemene informatie weergegeven over de status van de update-ringen die u hebt toegewezen.
4. Open een van de volgende rapporten:  

   **Voor alle implementatieringen**:
   1. In het deelvenster **Software-updates** > **Windows 10-update-ringen**
   2. In de sectie **Bewaken** kiest u **Implementatiestatus per updatering**.  

   **Voor specifieke implementatieringen**:  

   1. Kies in **Software-updates** > **Windows 10-update-ringen** de implementatiering die u wilt weergeven.  
   2. Kies in de sectie **Bewaken** een van de volgende rapporten om meer gedetailleerde informatie over de implementatiering weer te geven:  
      - **Apparaatstatus**  
      - **Gebruikersstatus**  

## <a name="use-update-compliance"></a>Updatenaleving gebruiken
Met de Windows Analytics-oplossing [Updatenaleving](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor) kunt u de Windows 10 update-implementaties bewaken. Updatenaleving wordt u aangeboden via Azure Portal en is gratis beschikbaar voor apparaten die aan de [voorwaarden](https://docs.microsoft.com/windows/deployment/update/update-compliance-get-started#update-compliance-prerequisites) voldoen.  

Wanneer u deze oplossing gebruikt, kunt u een commerciële id implementeren op elk van uw door Intune beheerde Windows 10-apparaten waarvoor u over de naleving van updates wilt rapporteren.  

In de Intune-console kunt u de OMA-URI-instellingen van een aangepast beleid gebruiken om de commerciële id te configureren. Zie [Beleidsinstellingen voor Windows 10-apparaten in Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune) voor meer informatie.  

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

