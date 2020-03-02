---
title: Sophos Mobile gebruiken met Intune
titleSuffix: Intune on Azure
description: Meer informatie over hoe u de Sophos Mobile-oplossing met Microsoft Intune gebruikt om de toegang van mobiele apparaten tot uw bedrijfsresources te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d17749353bc3904a3d99210a5d56531d9af9c28
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514809"
---
# <a name="sophos-mobile-threat-defense-connector-with-intune"></a>Sophos Mobile Threat Defense-connector met Intune
U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren met voorwaardelijke toegang op basis van een risicoanalyse die wordt uitgevoerd door Sophos Mobile, een MDT-oplossing (Mobile Threat Defense) die in Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens die zijn verzameld op apparaten waarop de Sophos Mobile-app wordt uitgevoerd.
U kunt beleidsregels voor voorwaardelijke toegang configureren op basis van de Sophos Mobile-risicoanalyse die via het Intune-nalevingsbeleid voor apparaten wordt ingeschakeld. U kunt met dit beleid de toegang tot bedrijfsresources voor niet-conforme apparaten toestaan of blokkeren op basis van de gedetecteerde bedreigingen.

## <a name="how-do-intune-and-sophos-mobile-help-protect-your-company-resources"></a>Hoe kunt u met Intune en Sophos Mobile uw bedrijfsresources beter beveiligen?
Met de Sophos Mobile-app voor Android of iOS/iPadOS worden telemetriegegevens vastgelegd over het bestandssysteem, de netwerkstack, apparaten en toepassingen waar dergelijke gegevens beschikbaar zijn. De app verzendt de telemetriegegevens vervolgens naar de Sophos Mobile-cloudservice om te bepalen hoe groot het risico van bedreigingen is voor het mobiele apparaat.
Het Intune-nalevingsbeleid voor apparaten bevat een regel voor Sophos Mobile Threat Defense die is gebaseerd op de Sophos Mobile-risicoanalyse. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld. Als het apparaat niet aan het beleid blijkt te voldoen, wordt de toegang van gebruikers tot resources als Exchange Online en SharePoint Online geblokkeerd. Gebruikers ontvangen ook richtlijnen van de Sophos Mobile-app die op hun apparaat is geïnstalleerd, zodat ze het probleem kunnen oplossen en weer toegang kunnen krijgen tot bedrijfsresources.  

## <a name="sample-scenarios"></a>Voorbeeldscenario's
Hier volgen enkele veelvoorkomende scenario's.  
### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps
Als er op apparaten schadelijke apps zoals malware worden gedetecteerd, kunt u apparaten blokkeren tegen acties als de volgende totdat de bedreiging is opgelost:
- Verbinding met bedrijfs-e-mail
- Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk
- Toegang tot bedrijfs-apps

**Blokkeren wanneer er schadelijke apps zijn gedetecteerd**:
 
![Conceptafbeelding van detectie van schadelijke apps](./media/sophos-mtd-connector/sophos_malicious_apps_blocked.png)  

**Toegang na herstel**:  
![Conceptafbeelding van verleende toegang na herstel](./media/sophos-mtd-connector/sophos_malicious_apps_unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk  
Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen en de toegang tot Wi-Fi-netwerken wordt beveiligd op basis van apparaatrisico.  

**Netwerktoegang via Wi-Fi blokkeren**:  
![Netwerktoegang via Wi-Fi blokkeren](./media/sophos-mtd-connector/sophos_network_wifi_blocked.png)

**Toegang na herstel**:   
![Toegang na herstel](./media/sophos-mtd-connector/sophos_network_wifi_unblocked.png)  

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk  
Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen en synchronisatie van bedrijfsbestanden wordt voorkomen op basis van het apparaatrisico.  

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd**:   
![SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd](./media/sophos-mtd-connector/sophos_network_spo_blocked.png)  

**Toegang na herstel**:  
![Voorbeeld waarin na herstel toegang is verleend aan Sharepoint](./media/sophos-mtd-connector/sophos_network_spo_unblocked.png)  

## <a name="supported-platforms"></a>Ondersteunde platforms  
- Android 5.0 en hoger
- iOS 11.0 en hoger

## <a name="prerequisites"></a>Vereisten  
- Azure Active Directory Premium
- Microsoft Intune-abonnement 
- Sophos Mobile Threat Defense-abonnement

Zie de [Sophos-website](https://www.sophos.com/en-us/products/mobile-control.aspx) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen  
- [Sophos integreren met Intune](sophos-mtd-connector-integration.md)
- [Sophos-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Een nalevingsbeleid voor Sophos-apparaten maken](mtd-device-compliance-policy-create.md)
- [Sophos MTD-connector inschakelen](mtd-connector-enable.md)
