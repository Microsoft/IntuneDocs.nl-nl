---
title: Mobile Threat Defense-connector inschakelen in Microsoft Intune
titleSuffix: Microsoft Intune
description: Schakel de connector tussen uw Mobile Threat Defense (MTD) -partner en Microsoft Intune in.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 04/30/2019
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
ms.openlocfilehash: 1929b811a5a5320bc0ceefcef4f05ed2443ac070
ms.sourcegitcommit: cc5d757018d05fc03ac9ea3d30f563df9bfd61ed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2019
ms.locfileid: "66819657"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>De Mobile Threat Defense-connector inschakelen in Intune

> [!NOTE] 
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

Tijdens de configuratie van Mobile Threat Defense (MTD) hebt u een beleid geconfigureerd om bedreigingen te classificeren in de console van de MTD-partner en hebt u het nalevingsbeleid voor apparaten in Intune gemaakt. Als u de Intune-connector al hebt geconfigureerd in de console van de MTD-partner, kunt u nu de MTD-verbinding inschakelen in Intune.

## <a name="to-enable-the-mtd-connector"></a>De MTD-connector inschakelen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

4. Kies in het **Intune-dashboard** de optie **Apparaatcompatibiliteit** en kies vervolgens **Mobile Threat Defense** onder de sectie **Configuratie**.

5. Kies in het deelvenster **Mobile Threat Defense** de optie **Toevoegen**.

6. Kies in de vervolgkeuzelijst uw MTD-oplossing als de **Mobile Threat Defense-connector die moet worden geconfigureerd**.

    ![MTD configureren in de Intune-portal van Azure](./media/enable-mtd-connector-1.png)

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
