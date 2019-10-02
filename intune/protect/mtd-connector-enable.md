---
title: Mobile Threat Defense-connector inschakelen in Microsoft Intune
titleSuffix: Microsoft Intune
description: Schakel de connector tussen uw Mobile Threat Defense (MTD) -partner en Microsoft Intune in.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ac49edcd4ea71bdbc83cfa093f2bb5e42aefd54
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722069"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>De Mobile Threat Defense-connector inschakelen in Intune

> [!NOTE] 
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

Tijdens de configuratie van Mobile Threat Defense (MTD) hebt u een beleid geconfigureerd om bedreigingen te classificeren in de console van de MTD-partner en hebt u het nalevingsbeleid voor apparaten in Intune gemaakt. Als u de Intune-connector al hebt geconfigureerd in de console van de MTD-partner, kunt u nu de MTD-verbinding inschakelen voor toepassingen van MTD-partners.

Wanneer u een nieuwe toepassing integreert in Intune Mobile Threat Defense en u de verbinding met Intune inschakelt, maakt Intune een klassiek beleid voor voorwaardelijke toegang in Azure Active Directory. Voor elke MTD-app die u integreert, zoals [Defender ATP](advanced-threat-protection.md) of een app van een van onze aanvullende [MTD-partners](mobile-threat-defense.md#mobile-threat-defense-partners), wordt een nieuw klassiek beleid voor voorwaardelijke toegang gemaakt. De beleidsregels kunnen worden genegeerd, maar mogen niet worden bewerkt, verwijderd of uitgeschakeld.

Klassiek beleid voor voorwaardelijke toegang voor MTD-apps: 

- Wordt door Intune MTD gebruikt om te vereisen dat apparaten in Microsoft Azure Active Directory worden geregistreerd; ze beschikken dan over een apparaat-id voordat ze gaan communiceren met MTD-partners. De id is vereist omdat apparaten anders hun status niet kunnen doorgeven aan Intune.  
- Heeft geen effect op andere cloud-apps of -resources.  
- Verschilt van beleid voor voorwaardelijke toegang dat u normaal wellicht zou maken om MTD te helpen beheren.
- Standaard wordt er niet gecommuniceerd met andere beleidsregels voor voorwaardelijke toegang die voor evaluatie worden gebruikt.  

Als u klassiek beleid voor voorwaardelijke toegang wilt bekijken, gaat u in [Azure](https://portal.azure.com/#home) naar **Azure Active Directory** > **Voorwaardelijke toegang** > **Klassieke beleidsregels**.


## <a name="to-enable-the-mtd-connector"></a>De MTD-connector inschakelen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

4. Kies in het **Intune-dashboard** de optie **Apparaatcompatibiliteit** en kies vervolgens **Mobile Threat Defense** onder de sectie **Configuratie**.

5. Kies in het deelvenster **Mobile Threat Defense** de optie **Toevoegen**.

6. Kies in de vervolgkeuzelijst uw MTD-oplossing als de **Mobile Threat Defense-connector die moet worden geconfigureerd**.

    ![MTD configureren in de Intune-portal van Azure](./media/mtd-connector-enable/enable-mtd-connector-1.png)

7. Schakel de wisselknop in overeenkomstig de wensen van uw organisatie. Welke wisselopties zichtbaar zijn, is afhankelijk van de MTD-partner.

## <a name="mtd-toggle-options"></a>Wisselopties voor MTD

U kunt bepalen welke wisselopties voor MTD overeenkomstig de wensen van uw organisatie moeten worden ingeschakeld. Hier vindt u meer informatie:

- **Android 4.1+-apparaten koppelen aan [naam MTD-partner] voor Work MTD**: wanneer u deze optie inschakelt, kunnen door Android 4.1+-apparaten beveiligingsrisico's worden gerapporteerd aan Intune.
  - **Apparaat as niet-conform markeren als er geen gegevens zijn ontvangen**: als door Intune geen gegevens worden ontvangen van de MTD-partner over een apparaat op dit platform, kunt u het apparaat als niet-conform beschouwen.
<br></br>
- **iOS 8.0+-apparaten koppelen aan [naam MTD-partner] voor Work MTD**: wanneer u deze optie inschakelt, kunnen iOS 8.0+-apparaten beveiligingsrisico’s melden bij Intune.
  - **Apparaat as niet-conform markeren als er geen gegevens zijn ontvangen**: als door Intune geen gegevens worden ontvangen van de MTD-partner over een apparaat op dit platform, kunt u het apparaat als niet-conform beschouwen.
<br></br>
- **Synchronisatie van app inschakelen voor iOS-apparaten**: hiermee staat u toe dat deze Mobile Threat Defense-partner metagegevens van iOS-toepassingen kan aanvragen bij Intune om te gebruiken voor bedreigingsanalyse.

- **Niet-ondersteunde besturingssysteemversies blokkeren** : blokkeer het apparaat als hierop een besturingssysteem met een lagere versie wordt uitgevoerd dan de minimaal ondersteunde versie.

- **Aantal dagen dat partner niet reageert**: aantal dagen van inactiviteit waarna de partner in Intune als niet-reagerend wordt beschouwd omdat de verbinding is verbroken. Intune negeert de compatibiliteitsstatus voor niet-reagerende MTD-partners.

> [!IMPORTANT] 
> U moet de MTD-apps indien mogelijk toevoegen en toewijzen voordat u het nalevingsbeleid gaat maken en de beleidsregels voor voorwaardelijke toegang gaat opstellen. Dit zorgt ervoor dat de MTD-app beschikbaar is om te worden geïnstalleerd door eindgebruikers voordat ze toegang kunnen krijgen tot e-mail of andere bedrijfsresources.

> [!TIP]
> U kunt in het Mobile Threat Defense-deelvenster **Verbindingsstatus** en het tijdstip voor de **Laatste synchronisatie** tussen Intune en de MTD-partner bekijken.
