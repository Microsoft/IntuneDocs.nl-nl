---
title: Intune gebruiken voor het oplossen van beveiligingsproblemen gevonden door Microsoft Defender ATP - Azure | Microsoft Docs
description: Lees hoe u vanuit de Intune-console beveiligingstaken beheert met Threat & Vulnerability Management, een onderdeel van Microsoft Defender Advanced Threat Protection (ATP).
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa6dfef745157ae96736f8405fd5cafc33d4335f
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045286"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>Intune gebruiken voor het oplossen van beveiligingsproblemen geïdentificeerd door Microsoft Defender ATP  

Wanneer u Intune integreert met Microsoft Defender Advanced Threat Protection (ATP), hebt u ook toegang tot Threat & Vulnerability Management (TVM) van ATP en kunt u Intune gebruiken voor het wegnemen van beveiligingsproblemen die door TVM zijn geïdentificeerd op eindpunten. Met deze integratie wordt bij de detectie en de prioriteitsbepaling van beveiligingsproblemen het risico centraal gesteld, waardoor de reactietijd bij problemen kan verbeteren in uw omgeving.  

[Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) maakt deel uit van [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).  

## <a name="how-integration-works"></a>Hoe de integratie werkt  

Nadat u Intune hebt verbonden met Microsoft Defender Advanced Threat Protection, ontvangt ATP gegevens van bedreigingen en beveiligingsproblemen van beheerde apparaten.  

Beveiligingsbeheerders van ATP kunnen in het beveiligingscentrum van Windows Defender gegevens bekijken van beveiligingsproblemen op eindpunten. De beheerders kunnen vervolgens met één muisklik beveiligingstaken maken die de getroffen apparaten markeren voor actie. De beveiligingstaken worden onmiddellijk doorgegeven aan de Intune-console, waar Intune-beheerders ze kunnen bekijken. De beveiligingstaak identificeert het type beveiligingsproblemen, de prioriteit, status en de stappen voor het oplossen van het probleem. De Intune-beheerder kan de taak accepteren of weigeren.  

Wanneer een taak is geaccepteerd, gaat de Intune-via Intune proberen om het beveiligingsprobleem op te lossen, aan de hand van de adviezen die zijn opgenomen in de beveiligingstaak.  

Algemene acties voor probleemoplossing:  
- De uitvoering van een toepassing **blokkeren**  
- Een update van het besturingssysteem **implementeren**  
- Een registerwaarde **wijzigen**  
- Een configuratie **uitschakelen** of **inschakelen**  
- De status **Aandacht vereist** waarschuwt de beheerder voor de bedreiging wanneer er geen geschikte oplossing beschikbaar is.  

Hier volgt een voorbeeld van een werkstroom:  
- Binnen Microsoft Defender ATP is een beveiligingsprobleem voor een app met de naam Contoso Media Player v4 geconstateerd en een beheerder maakt een beveiligingstaak om de app bij te werken. Contoso Media Player is een niet-beheerde app die is geïmplementeerd met Intune.  

  Deze beveiligingstaak wordt in de Intune-beheerconsole weergegeven met de status In behandeling:  
  ![De lijst met beveiligingstaken bekijken in de Intune-console](./media/atp-manage-vulnerabilities/temp-security-tasks.png)
 
- De Intune-beheerder selecteert de beveiligingstaak om details van de taak te lezen.  Vervolgens selecteert de beheerder **Accepteren**, waardoor de status wordt bijgewerkt in Intune. In ATP wordt de status gewijzigd in *Accepted* (Geaccepteerd).  
  ![Een beveiligingstaak accepteren of weigeren](./media/atp-manage-vulnerabilities/temp-accept-task.png) 
 
- De beheerder voert de taak vervolgens uit aan de hand van de suggesties in de taak.  Deze suggesties verschillen naargelang het type oplossing dat nodig is. Indien deze beschikbaar zijn, bevat de taak koppelingen die relevante configuratievensters openen in Intune. 

  Omdat de Media Player in dit voorbeeld geen beheerde app is, kan Intune alleen tekstinstructies geven. Als het een beheerde app betreft, kan Intune instructies geven om een bijgewerkte versie te downloaden en een koppeling toevoegen om de implementatie voor de app te openen, zodat de bijgewerkte bestanden kunnen worden toegevoegd aan de implementatie. 

- Als het probleem is opgelost, opent de Intune-beheerder de beveiligingstaak en selecteert hij of zij **Taak voltooien**.  De status van de taak wordt bijgewerkt voor Intune en in ATP, waar beveiligingsbeheerders de gewijzigde status voor het beveiligingsprobleem bevestigen.  

## <a name="prerequisites"></a>Vereisten  

**Abonnementen**:  
- Microsoft Intune  
- Microsoft Defender Advanced Threat Protection ([u kunt zich aanmelden voor een gratis proefversie](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink))  

**Intune-configuraties voor ATP**:  
- Configureer een verbinding tussen services met Microsoft Defender ATP.  
- Implementeer een nalevingsbeleid voor apparaten met het profieltype **Microsoft Defender ATP (Windows 10 Desktop)** op apparaten waarvan het risico wordt beoordeeld door ATP.
  Zie [Naleving voor Windows Defender ATP met voorwaardelijke toegang in Intune afdwingen](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune) voor meer informatie over het instellen van Intune voor gebruik met ATP.  

## <a name="work-with-security-tasks"></a>Werken met beveiligingstaken  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en ga naar **Apparaatbeveiliging** > **Beveiligingstaken**.  
2. Selecteer een taak in de lijst om een resourcevenster te openen met extra gegevens van die beveiligingstaak.  
3. Terwijl het venster met gegevens van de beveiligingstaak geopend is, kunt u aanvullende koppelingen selecteren:  
   - BEHEERDE APPS: bekijk de app met het probleem. Wanneer het beveiligingsprobleem op meerdere apps van toepassing is, ziet u een gefilterde lijst met apps.  
   - APPARATEN: bekijk een lijst met de *kwetsbare apparaten*, en ga via een koppeling naar een vermelding met meer informatie over het beveiligingsprobleem op dat apparaat.  
   - AANVRAGER: gebruik de koppeling om een e-mail te verzenden naar de beheerder die deze beveiligingstaak heeft verzonden.  
   - OPMERKINGEN: lees aangepaste berichten die zijn verzonden door de aanvrager bij het openen van de beveiligingstaak.  
4. Selecteer **Accepteren** of **Weigeren** om ATP te informeren over wat u van plan bent. Wanneer u een taak accepteert of weigert, kunt u notities toevoegen, die worden verzonden naar ATP.  

5. Na het accepteren van een taak, opent u de beveiligingstaak opnieuw (als deze gesloten) en volgt u instructies om het beveiligingsprobleem op te lossen.  De instructies van ATP in de details van de beveiligingstaak zijn afhankelijk van het beveiligingsprobleem.  

   Wanneer het mogelijk is om dit te doen, bevatten de instructies koppelingen voor het openen van de betreffende configuratie-objecten in de Intune-console.  

6. Nadat de stappen voor probleemoplossing zijn voltooid, opent u de beveiligingstaak en selecteert u **Taak voltooien**.  Hiermee wordt de status van de beveiligingstaak bijgewerkt in zowel Intune als ATP.  

Als het probleem is opgelost, kan de risicoscore in ATP afnemen, gebaseerd op nieuwe informatie van de herstelde apparaten. 

## <a name="next-steps"></a>Volgende stappen
Meer informatie over Intune en [Microsoft Defender ATP](https://docs.microsoft.com/intune/advanced-threat-protection)  
Meer informatie over Intune [Mobile Threat Defense](https://docs.microsoft.com/intune/mobile-threat-defense)  
Meer informatie over het [dashboard Threat & Vulnerability Management](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) in Microsoft Defender ATP
