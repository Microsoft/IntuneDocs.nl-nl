---
title: De Mobile Threat Defense-connector inschakelen voor niet-ingeschreven apparaten
titleSuffix: Microsoft Intune
description: De Mobile Threat Defense-connector in Microsoft Intune inschakelen voor niet-ingeschreven apparaten.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9571f7d0ae10f33007d5ae50b403580232c2e870
ms.sourcegitcommit: 06dce5c8111592ad774247e86e539dd3128117e5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/30/2019
ms.locfileid: "75545924"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune-for-unenrolled-devices"></a>De Mobile Threat Defense-connector in Intune inschakelen voor niet-ingeschreven apparaten

Tijdens de configuratie van Mobile Threat Defense (MTD) hebt u een beleid geconfigureerd om bedreigingen te classificeren in de console van de Mobile Threat Defense-partner en hebt u het app-beveiligingsbeleid in Intune gemaakt. Als u de Intune-connector al hebt geconfigureerd in de console van de MTD-partner, kunt u nu de MTD-verbinding inschakelen voor toepassingen van MTD-partners.

> [!NOTE]
> Dit artikel is van toepassing op alle Mobile Threat Defense-partners die ondersteuning bieden aan beleid voor app-beveiliging: Better Mobile (Android), Zimperium (Android/iOS), Lookout for Work (Android/iOS).

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>Klassiek beleid voor voorwaardelijke toegang voor MTD-apps

Wanneer u een nieuwe toepassing integreert in Intune Mobile Threat Defense en u de verbinding met Intune inschakelt, maakt Intune een klassiek beleid voor voorwaardelijke toegang in Azure Active Directory. Voor elke MTD-app die u integreert, zoals [Defender ATP](advanced-threat-protection.md) of een app van een van onze aanvullende [MTD-partners](mobile-threat-defense.md#mobile-threat-defense-partners), wordt een nieuw klassiek beleid voor voorwaardelijke toegang gemaakt. De beleidsregels kunnen worden genegeerd, maar mogen niet worden bewerkt, verwijderd of uitgeschakeld.

Als het klassieke beleid wordt verwijderd, moet u de verbinding met Intune die verantwoordelijk is voor het maken ervan verwijderen en deze vervolgens opnieuw instellen. Met dit proces wordt het klassieke beleid opnieuw gemaakt. Het is niet mogelijk om klassiek beleid voor MTD-apps te migreren naar het nieuwe beleidstype voor voorwaardelijke toegang.

Klassiek beleid voor voorwaardelijke toegang voor MTD-apps:

- Wordt door Intune MTD gebruikt om te vereisen dat apparaten in Microsoft Azure Active Directory worden geregistreerd; ze beschikken dan over een apparaat-id voordat ze gaan communiceren met MTD-partners. De id is vereist omdat apparaten anders hun status niet kunnen doorgeven aan Intune.

- Heeft geen effect op andere cloud-apps of -resources.

- Verschilt van beleid voor voorwaardelijke toegang dat u normaal wellicht zou maken om MTD te helpen beheren.

- Standaard wordt er niet gecommuniceerd met andere beleidsregels voor voorwaardelijke toegang die voor evaluatie worden gebruikt.

Als u klassiek beleid voor voorwaardelijke toegang wilt bekijken, gaat u in [Azure](https://portal.azure.com/#home) naar **Azure Active Directory** > **Voorwaardelijke toegang** > **Klassieke beleidsregels**.

## <a name="to-enable-the-mtd-connector"></a>De MTD-connector inschakelen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Mobile Threat Defense**.

3. Kies in het deelvenster **Mobile Threat Defense** de optie **Toevoegen**.

4. Kies in de vervolgkeuzelijst uw MTD-oplossing als de **Mobile Threat Defense-connector die moet worden geconfigureerd**.

    <!-- ![MTD setup in Intune](PLACEHOLDER, need a new screenshot of this page) -->

5. Schakel de wisselknop in overeenkomstig de wensen van uw organisatie. Welke wisselopties zichtbaar zijn, is afhankelijk van de MTD-partner.

## <a name="mobile-threat-defense-toggle-options"></a>Wisselopties voor Mobile Threat Defense

U kunt bepalen welke wisselopties voor MTD overeenkomstig de wensen van uw organisatie moeten worden ingeschakeld. Hier vindt u meer informatie:

**Instellingen voor app-beveiligingsbeleid**

- **Android-apparaten van versie 4.4 en hoger verbinden met *\<MTD-partnernaam>* voor evaluatie van het app-beveiligingsbeleid**: Als u deze optie inschakelt, worden apparaten (inclusief gegevens van deze connector) geëvalueerd door app-beveiligingsbeleid met behulp van de Device Threat Level-regel.

- **iOS-apparaten van versie 11 verbinden met *\<MTD-partnernaam>* voor evaluatie van het app-beveiligingsbeleid**: Als u deze optie inschakelt, worden apparaten (inclusief gegevens van deze connector) geëvalueerd door app-beveiligingsbeleid met behulp van de Device Threat Level-regel.

**Algemene gedeelde instellingen**

- **Aantal dagen dat partner niet reageert**: aantal dagen van inactiviteit waarna de partner in Intune als niet-reagerend wordt beschouwd omdat de verbinding is verbroken. Intune negeert de compatibiliteitsstatus voor niet-reagerende MTD-partners.

> [!TIP]
> U kunt in het Mobile Threat Defense-deelvenster **Verbindingsstatus** en het tijdstip voor de **Laatste synchronisatie** tussen Intune en de MTD-partner bekijken.

## <a name="next-steps"></a>Volgende stappen

- [Een beveiligingsbeleid voor MTD-apps (Mobile Threat Defense) maken met Intune](~/protect/mtd-app-protection-policy.md).
