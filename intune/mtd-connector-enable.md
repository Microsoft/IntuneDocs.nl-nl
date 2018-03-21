---
title: Mobile Threat Defense-connector inschakelen in Microsoft Intune
titleSuffix: 
description: Schakel de connector tussen uw Mobile Threat Defense (MTD) -partner en Microsoft Intune in.
keywords: 
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/27/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3ca0b8082e0fccc5ee4c97e281d546ba4a75d813
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2018
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>De Mobile Threat Defense-connector inschakelen in Intune

> [!NOTE] 
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

Tijdens de configuratie van Mobile Threat Defense (MTD) hebt u een beleid geconfigureerd om bedreigingen te classificeren in de console van de MTD-partner en hebt u het nalevingsbeleid voor apparaten in Intune gemaakt. Als u de Intune-connector al hebt geconfigureerd in de console van de MTD-partner, kunt u nu de MTD-verbinding inschakelen in Intune.

## <a name="to-enable-the-mtd-connector"></a>De MTD-connector inschakelen

1. Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw Intune-referenties. Nadat u zich hebt aangemeld, ziet u het **Azure-dashboard**.

2. Kies in het **Azure-dashboard** in het linkermenu de optie **Alle services** en typ vervolgens **Intune** in het filtertekstvak.

3. Kies **Intune**; het **Intune-dashboard** wordt geopend.

4. Kies in het **Intune-dashboard** de optie **Apparaatcompatibiliteit** en kies vervolgens **Mobile Threat Defense** onder de sectie **Configuratie**.

5. Kies in het deelvenster **Mobile Threat Defense** de optie **Toevoegen**.

6. Kies in de vervolgkeuzelijst uw MTD-oplossing als de **Mobile Threat Defense-connector die moet worden geconfigureerd**.

    ![MTD configureren in de Intune-portal van Azure](./media/enable-mtd-connector-1.png)

7. Schakel de wisselknop in overeenkomstig de wensen van uw organisatie.

## <a name="mtd-toggle-options"></a>Wisselopties voor MTD

U kunt bepalen welke wisselopties voor MTD overeenkomstig de wensen van uw organisatie moeten worden ingeschakeld. Hier vindt u meer informatie:

- **Android 4.1+-apparaten verbinden met [naam van MTD-partner] for Work MTD**: wanneer u deze optie inschakelt, kunnen door Android 4.1+-apparaten beveiligingsrisico's worden gerapporteerd aan Intune.
    - **Apparaat als niet-compatibel markeren als er geen gegevens worden ontvangen**: als door Intune geen gegevens worden ontvangen van de MTD-partner over een apparaat op dit platform, kunt u het apparaat als niet-compatibel beschouwen.
<br></br>
- **iOS 8.0+-apparaten verbinden met [naam van MTD-partner] for Work MTD**: wanneer u deze optie inschakelt, kunnen door Android 4.1+-apparaten beveiligingsrisico's worden gerapporteerd aan Intune.
    - **Apparaat als niet-compatibel markeren als er geen gegevens worden ontvangen**: als door Intune geen gegevens worden ontvangen van de MTD-partner over een apparaat op dit platform, kunt u het apparaat als niet-compatibel beschouwen.
<br></br>
- **Niet-ondersteunde besturingssysteemversies blokkeren** : blokkeer het apparaat als hierop een besturingssysteem met een lagere versie wordt uitgevoerd dan de minimaal ondersteunde versie.

- **Aantal dagen totdat de partner als niet-reagerend wordt beschouwd**: aantal dagen van inactiviteit waarna de partner door Intune als niet-reagerend wordt beschouwd omdat de verbinding is verbroken. Intune negeert de compatibiliteitsstatus voor niet-reagerende MTD-partners.

> [!IMPORTANT] 
> U moet de MTD-apps toevoegen en toewijzen voordat u het nalevingsbeleid gaat maken en de beleidsregels voor voorwaardelijke toegang gaat opstellen. Dit zorgt ervoor dat de MTD-app beschikbaar is om te worden geïnstalleerd door eindgebruikers voordat ze toegang kunnen krijgen tot e-mail of andere bedrijfsresources.

> [!TIP]
> U kunt in het Mobile Threat Defense-deelvenster **Verbindingsstatus** en het tijdstip voor de **Laatste synchronisatie** tussen Intune en de MTD-partner bekijken.
