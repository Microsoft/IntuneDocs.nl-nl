---
title: Wandera Mobile Security instellen met Intune
titleSuffix: Intune on Azure
description: Lees hoe u Wandera Mobile Security met Microsoft Intune instelt om de toegang van mobiele apparaten tot uw bedrijfsresources te beheren.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: f4043ddc2a9f960b30e753c24e0b806e72b6850c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728283"
---
# <a name="wandera-mobile-threat-defense-connector-with-intune"></a>Wandera Mobile Threat Defense-connector met Intune  

Beheer de toegang van mobiele apparaten tot zakelijke resources met behulp van voorwaardelijke toegang op basis van een risicoanalyse door Wandera. Wandera is een Mobile Threat Defense-oplossing (MTD) die kan worden geïntegreerd met Microsoft Intune.  Risico's worden beoordeeld op basis van telemetrische gegevens die afkomstig zijn van apparaten die door de Wandera-service zijn verzameld:
- Beveiligingsproblemen voor besturingssystemen
- Schadelijke apps geïnstalleerd
- Schadelijke netwerkprofielen
- Cryptojacking

U kunt beleid voor *voorwaardelijke toegang* configureren dat is gebaseerd op de risicoanalyse van Wandera en dat via Intune-nalevingsbeleid wordt ingeschakeld. Met beleid voor risicoanalyse kunt u apparaten die niet conform zijn op basis van gedetecteerde bedreigingen toegang weigeren tot bedrijfsresources.  


## <a name="how-do-intune-and-wandera-mobile-threat-defense-help-protect-your-company-resources"></a>Hoe kunnen uw bedrijfsresources worden beveiligd met Intune en Wandera Mobile Threat Defense?  

De mobiele app van Wandera wordt met Microsoft Intune moeiteloos geïnstalleerd. De app legt het bestandssysteem, de netwerkstacks en de apparaat- en toepassingstelemetrie vast (indien beschikbaar). Deze informatie wordt gesynchroniseerd met de Wandera-cloudservice om het risico van het apparaat met betrekking tot mobiele bedreigingen te beoordelen. De classificaties van het risiconiveau zijn in de Wandera-console, RADAR, naar wens te configureren.

Het compliancebeleid in Intune omvat een regel voor MTD op basis van de risicobeoordeling van Wandera. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld.

Voor apparaten die niet-compatibel zijn, kan toegang tot resources als Office 365 worden geblokkeerd. Gebruikers van een geblokkeerd apparaat ontvangen richtlijnen van de Wandera-app, zodat ze het probleem kunnen oplossen en weer toegang kunnen krijgen.

## <a name="supported-platforms"></a>Ondersteunde platforms  

De volgende platforms worden door Wandera ondersteund bij inschrijving in Intune:

- Android 5.0 en hoger  
- iOS 10.2 en hoger  

Raadpleeg voor meer informatie over platforms en apparaten de [website van Wandera](https://www.wandera.com/why-wandera/features/device-support/).

## <a name="prerequisites"></a>Vereisten  

- Microsoft Intune-abonnement  
- Azure Active Directory  
- Wandera Mobile Threat Defense (voorheen Wandera Secure)  

Raadpleeg voor meer informatie [Wandera Mobile Security](https://www.wandera.com/mobile-security/).
 
## <a name="sample-scenarios"></a>Voorbeeldscenario's

Hier vindt u algemene scenario's voor wanneer u Wandera MTD met Intune gebruikt.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps  

Als er op een apparaat schadelijke apps (bijvoorbeeld malware) worden gedetecteerd, kunt u de toegang van het apparaat tot veelgebruikte hulpprogramma's blokkeren totdat de bedreiging is geëlimineerd. Veelvoorkomende blokkeringen zijn onder meer:  
- Verbinding met bedrijfs-e-mail  
- Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk  
- Toegang tot bedrijfs-apps  

**Blokkeren wanneer er schadelijke apps zijn gedetecteerd**:

![Conceptafbeelding van detectie van schadelijke apps](./media/wandera-mtd-connector/wandera-malicious-apps-blocked.png)  

**Toegang na herstel**: 

![Conceptafbeelding van verleende toegang na herstel](./media/wandera-mtd-connector/wandera-malicious-apps-unblocked.png)


### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk  

Detecteer bedreigingen voor uw netwerk, zoals man-in-the-middle-aanvallen, en beveilig de toegang tot wifinetwerken op basis van het apparaatrisico.  

**Netwerktoegang via Wi-Fi blokkeren**:  

![Netwerktoegang via Wi-Fi blokkeren](./media/wandera-mtd-connector/wandera-network-wifi-blocked.png)

**Toegang na herstel**:  

![Toegang na herstel](./media/wandera-mtd-connector/wandera-network-wifi-unblocked.png)  

## <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk

Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen, en synchronisatie van bedrijfsbestanden wordt voorkomen op basis van het apparaatrisico.

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd**:  

![SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd](./media/wandera-mtd-connector/wandera-network-spo-blocked.png)  


**Toegang na herstel**:  

![Voorbeeld waarin na herstel toegang is verleend aan SharePoint](./media/wandera-mtd-connector/wandera-network-spo-unblocked.png)  

## <a name="next-steps"></a>Volgende stappen

- [Wandera integreren met Intune](wandera-mtd-connector-integration.md)
- [Wandera-apps instellen](mtd-apps-ios-app-configuration-policy-add-assign.md)
- [Wandera-nalevingsbeleid voor apparaten maken](mtd-device-compliance-policy-create.md)
- [Wandera MTD-connector inschakelen](mtd-connector-enable.md)