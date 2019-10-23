---
title: Lookout MTD-connector met Microsoft Intune
titleSuffix: Microsoft Intune
description: Meer informatie over de integratie van Intune met Lookout Mobile Threat Defense (MTD) om toegang tot uw bedrijfsbronnen met mobiele apparaten te bepalen.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: davera
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f0123647fb1e8a1d52506ad0753906f974103aad
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502207"
---
# <a name="lookout-mobile-endpoint-security-connector-with-intune"></a>Lookout Mobile Endpoint Security-connector met Intune

U kunt de toegang van mobiele apparaten tot bedrijfsresources beheren op basis van een risicoanalyse die door Lookout wordt uitgevoerd. Lookout is een Mobile Threat Defense-oplossing die met Microsoft Intune is geïntegreerd. Risico's worden beoordeeld op basis van telemetrische gegevens afkomstig van apparaten die door Lookout-service zijn verzameld:
- Beveiligingsproblemen voor besturingssystemen
- Schadelijke apps geïnstalleerd
- Schadelijke netwerkprofielen

U kunt beleidsregels voor voorwaardelijke toegang configureren op basis van de risicoanalyse van Lookout die wordt ingeschakeld via het nalevingsbeleid van Intune. U kunt het toestaan of blokkeren van niet-compatibele apparaten instellen op basis van gedetecteerde bedreigingen.

## <a name="how-do-intune-and-lookout-mobile-endpoint-security-help-protect-company-resources"></a>Hoe kunnen bedrijfsresources worden beveiligd met Intune en Lookout Mobile Endpoint Security?
De mobiele app van Lookout, **Lookout for Work**, wordt geïnstalleerd en uitgevoerd op mobiele apparaten. Deze app legt telemetrische gegevens vast over het bestandssysteem, de netwerkstack, apparaten en apps waar dergelijke gegevens beschikbaar zijn, en verzendt die gegevens naar de Lookout-cloudservice om te bepalen welke risico's het apparaat loopt met mobiele bedreigingen. U kunt de classificaties van het risiconiveau voor bedreigingen in de Lookout-console wijzigen op basis van uw vereisten.  

Het nalevingsbeleid van Intune bevat een regel voor Lookout Mobile Threat Defense die is gebaseerd op de risicoanalyse van Lookout. Als deze regel is ingeschakeld, controleert Intune of het apparaat voldoet aan het beleid dat u hebt ingeschakeld.

Als het apparaat niet aan het beleid blijkt te voldoen, kan de toegang tot bronnen zoals Exchange Online en SharePoint Online worden geblokkeerd. Gebruikers op geblokkeerde apparaten ontvangen een stappenplan om het probleem op te lossen en weer toegang te krijgen. De richtlijnen worden vanuit de Lookout for Work-app toegestuurd.

## <a name="supported-platforms"></a>Ondersteunde platforms  
De volgende platformen worden ondersteund door Lookout wanneer deze geregistreerd zijn in Intune:
* **Android 4.1 en hoger**  
* **iOS 8 en hoger**  

Meer informatie over ondersteunde platformen en talen kunt u vinden op de [website van Lookout](https://personal.support.lookout.com/hc/articles/114094140253).  

## <a name="prerequisites"></a>Vereisten
* Enterprise-abonnement op Lookout Mobile EndPoint Security  
* Microsoft Intune-abonnement
* Azure Active Directory Premium
* EMS (Enterprise Mobility en Security) E3 of E5, met aan gebruikers toegewezen licenties.  

Zie [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security) voor meer informatie

## <a name="sample-scenarios"></a>Voorbeeldscenario's

Hier vindt u veelvoorkomende scenario's als u Mobile Endpoint Security met Intune gebruikt.

### <a name="control-access-based-on-threats-from-malicious-apps"></a>Toegangsbeheer op basis van bedreigingen van schadelijke apps
Als er op apparaten schadelijke apps zoals malware worden gedetecteerd, kunt u apparaten blokkeren tegen zaken als de volgende totdat de bedreiging is opgelost:
* Verbinding met bedrijfs-e-mail
* Synchronisatie van bedrijfsbestanden met de app OneDrive voor werk
* Toegang tot bedrijfs-apps

**Blokkeren wanneer er schadelijke apps zijn gedetecteerd:**

![Conceptafbeelding van beleidsmatig geblokkeerde toegang vanwege schadelijke apps](./media/lookout-mobile-threat-defense-connector/malicious-apps-blocked.png)

**Toegang na herstel:**

![Conceptafbeelding van verleende toegang tot apparaten na herstel](./media/lookout-mobile-threat-defense-connector/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a>Toegangsbeheer op basis van bedreigingen voor het netwerk
Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen, en de toegang tot Wi-Fi-netwerken wordt beveiligd op basis van apparaatrisico.

**Netwerktoegang via Wi-Fi blokkeren:**

![Afbeelding met blokkering van Wi-Fi-toegang op basis van netwerkbedreigingen](./media/lookout-mobile-threat-defense-connector/network-wifi-blocked.png)

**Toegang na herstel:**

![Conceptafbeelding van voorwaardelijke toegang voor toegang na herstel](./media/lookout-mobile-threat-defense-connector/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a>Toegangsbeheer voor SharePoint Online op basis van bedreigingen voor het netwerk

Bedreigingen voor uw netwerk worden gedetecteerd, zoals man-in-the-middle-aanvallen, en synchronisatie van bedrijfsbestanden wordt voorkomen op basis van het apparaatrisico.

**SharePoint Online blokkeren wanneer netwerkbedreigingen worden gedetecteerd:**

![Conceptafbeelding van blokkering van toegang tot SharePoint Online](./media/lookout-mobile-threat-defense-connector/network-spo-blocked.png)


**Toegang na herstel:**

![Conceptafbeelding die laat zien hoe de toegang na verwijdering van de netwerkbedreiging wordt verleend met voorwaardelijke toegang](./media/lookout-mobile-threat-defense-connector/network-spo-unblocked.png)

## <a name="next-steps"></a>Volgende stappen
Hier volgen de belangrijkste stappen voor het implementeren van deze oplossing:
1. [De integratie van Lookout instellen](lookout-mtd-connector-integration.md)
2. [Mobile Endpoint Security in Intune inschakelen](mtd-connector-enable.md)
3. [De Lookout for Work-app toevoegen en toewijzen](mtd-apps-ios-app-configuration-policy-add-assign.md)
4. [Het nalevingsbeleid voor Lookout-apparaten configureren](mtd-device-compliance-policy-create.md)
