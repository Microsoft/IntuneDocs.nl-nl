---
title: Mobile Threat Defense-connector inschakelen met Intune
titlesuffix: Azure portal
description: Mobile Threat Defense-connector inschakelen in Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0d5e90cb91032a88830e7dc9af1d66d854ab4963
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="enable-mobile-threat-defense-in-intune"></a>Mobile Threat Defense inschakelen in Intune

> [!NOTE] 
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

Als u de verbinding voor Mobile Threat Defense (MTD) wilt inschakelen in Intune, moet de Intune-connector al zijn geconfigureerd in de console van de MTD-partner.

## <a name="to-enable-the-mtd-connector"></a>De MTD-connector inschakelen

1. Ga naar [Azure Portal](https://portal.azure.com) en meld u aan met uw Intune-referenties. Nadat u zich hebt aangemeld, ziet u het **Azure-dashboard**.

2. Kies in het **Azure-dashboard** in het linkermenu de optie **Meer services** en typ vervolgens **Intune** in het filtertekstvak.

3. Kies **Intune**. Vervolgens ziet u het **Intune-dashboard**.

4. Kies in het **Intune-dashboard** de optie **Apparaatcompatibiliteit** en kies vervolgens **Mobile Threat Defense** onder de sectie **Configuratie**.

5. Kies op de blade **Mobile Threat Defense** de optie **Toevoegen**.

6. Kies in de vervolgkeuzelijst uw MTD-oplossing als de **Mobile Threat Defense-connector die moet worden geconfigureerd**.

    ![MTD configureren in de Intune-portal van Azure](./media/enable-mtd-connector-1.png)

7. Schakel de wisselknop in overeenkomstig de wensen van uw organisatie.

## <a name="mtd-toggle-options"></a>Wisselopties voor MTD

U kunt bepalen welke wisselopties voor MTD overeenkomstig de wensen van uw organisatie moeten worden ingeschakeld. Hieronder vindt u meer details:

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
> U kunt op de Mobile Threat Defense-blade de **Verbindingsstatus** en het tijdstip voor de **Laatste synchronisatie** tussen Intune en de MTD-partner bekijken.
