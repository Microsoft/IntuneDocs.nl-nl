---
title: Mobile Threat Defense-connector inschakelen in Microsoft Intune
titleSuffix: Microsoft Intune
description: Schakel de connector tussen uw Mobile Threat Defense (MTD) -partner en Microsoft Intune in.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: davidra
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b8243ae4014660a76c6327afd9c970ce8a9eae58
ms.sourcegitcommit: 960ffb2214c35d75ad219fa2571a999529a0abd4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/25/2019
ms.locfileid: "74478837"
---
# <a name="enable-the-mobile-threat-defense-connector-in-intune"></a>De Mobile Threat Defense-connector inschakelen in Intune

Tijdens de configuratie van Mobile Threat Defense (MTD) hebt u een beleid geconfigureerd om bedreigingen te classificeren in de console van de Mobile Threat Defense-partner en hebt u nalevingsbeleid voor apparaten in Intune gemaakt. Als u de Intune-connector al hebt geconfigureerd in de console van de MTD-partner, kunt u nu de MTD-verbinding inschakelen voor toepassingen van MTD-partners.

> [!NOTE]
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

## <a name="classic-conditional-access-policies-for-mtd-apps"></a>Klassiek beleid voor voorwaardelijke toegang voor MTD-apps

Wanneer u een nieuwe toepassing integreert in Intune Mobile Threat Defense en u de verbinding met Intune inschakelt, maakt Intune een klassiek beleid voor voorwaardelijke toegang in Azure Active Directory. Voor elke MTD-app die u integreert, zoals [Defender ATP](advanced-threat-protection.md) of een app van een van onze aanvullende [MTD-partners](mobile-threat-defense.md#mobile-threat-defense-partners), wordt een nieuw klassiek beleid voor voorwaardelijke toegang gemaakt. De beleidsregels kunnen worden genegeerd, maar mogen niet worden bewerkt, verwijderd of uitgeschakeld.

Als het klassieke beleid wordt verwijderd, moet u de verbinding met Intune die verantwoordelijk is voor het maken ervan verwijderen en deze vervolgens opnieuw instellen. Met dit proces wordt het klassieke beleid opnieuw gemaakt. Het is niet mogelijk om klassiek beleid voor MTD-apps te migreren naar het nieuwe beleidstype voor voorwaardelijke toegang.

Klassiek beleid voor voorwaardelijke toegang voor MTD-apps:

- Wordt door Intune MTD gebruikt om te vereisen dat apparaten in Microsoft Azure Active Directory worden geregistreerd; ze beschikken dan over een apparaat-id voordat ze gaan communiceren met MTD-partners. De id is vereist omdat apparaten anders hun status niet kunnen doorgeven aan Intune.

- Heeft geen effect op andere cloud-apps of -resources.

- Verschilt van beleid voor voorwaardelijke toegang dat u normaal wellicht zou maken om MTD te helpen beheren.

- Standaard wordt er niet gecommuniceerd met andere beleidsregels voor voorwaardelijke toegang die voor evaluatie worden gebruikt.

Als u klassiek beleid voor voorwaardelijke toegang wilt bekijken, gaat u in [Azure](https://portal.azure.com/#home) naar **Azure Active Directory** > **Voorwaardelijke toegang** > **Klassieke beleidsregels**.

## <a name="to-enable-the-mobile-threat-defense-connector"></a>Mobile Threat Defense-connector inschakelen

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Mobile Threat Defense**.

3. Selecteer in het deelvenster **Mobile Threat Defense** de optie **Toevoegen**.

4. Selecteer als de **Mobile Threat Defense-connector die moet worden geconfigureerd** uw MTD-oplossing in de vervolgkeuzelijst.

5. Schakel de wisselknop in overeenkomstig de wensen van uw organisatie. Welke wisselopties zichtbaar zijn, is afhankelijk van de MTD-partner.  In de volgende afbeelding ziet u bijvoorbeeld de opties die beschikbaar zijn voor Symantec Endpoint Protection:

   ![MTD configureren in de Intune-portal van Azure](./media/mtd-connector-enable/enable-mtd-connector-1.png)

## <a name="mobile-threat-defense-toggle-options"></a>Wisselopties voor Mobile Threat Defense

U kunt bepalen welke wisselopties voor MTD overeenkomstig de wensen van uw organisatie moeten worden ingeschakeld. Niet elk van de volgende opties wordt ondersteund door alle Mobile Threat Defense-partner:

**Instellingen voor MDM-nalevingsbeleid**

- **Android-apparaten van versie _\<ondersteunde versies>_ verbinden met _\<MTD-partnernaam>_** : wanneer u deze optie inschakelt, kunnen door Android 4.1+-apparaten beveiligingsrisico's worden gerapporteerd aan Intune.

- **iOS-apparaten versie _\<ondersteunde versies>_ verbinden met _\<MTD-partnernaam>_** : wanneer u deze optie inschakelt, kunnen iOS 8.0+-apparaten beveiligingsrisico’s melden bij Intune.

- **Synchronisatie van app inschakelen voor iOS-apparaten**: hiermee staat u toe dat deze Mobile Threat Defense-partner metagegevens van iOS-toepassingen kan aanvragen bij Intune om te gebruiken voor bedreigingsanalyse.

- **Niet-ondersteunde besturingssysteemversies blokkeren** : blokkeer het apparaat als hierop een besturingssysteem met een lagere versie wordt uitgevoerd dan de minimaal ondersteunde versie.

**Instellingen voor app-beveiligingsbeleid**

- **Android-apparaten van versie *\<ondersteunde versies>* verbinden met *\<MTD-partnernaam>* voor evaluatie van het app-beveiligingsbeleid**: Als u deze optie inschakelt, worden apparaten (inclusief gegevens van deze connector) geëvalueerd door app-beveiligingsbeleid met behulp van de Device Threat Level-regel.

- **iOS-apparaten versie *\<ondersteunde versies>* verbinden met *\<MTD-partnernaam>* voor evaluatie van het app-beveiligingsbeleid**: Als u deze optie inschakelt, worden apparaten (inclusief gegevens van deze connector) geëvalueerd door app-beveiligingsbeleid met behulp van de Device Threat Level-regel.

Voor meer informatie over het gebruik van Mobile Threat Defense-connectoren voor de evaluatie van het Intune app-beschermingsbeleid, zie [Mobiele Threat Defense voor niet-geregistreerde apparaten instellen](~/protect/mtd-enable-unenrolled-devices.md).

**Algemene gedeelde instellingen**

- **Aantal dagen dat partner niet reageert**: aantal dagen van inactiviteit waarna de partner in Intune als niet-reagerend wordt beschouwd omdat de verbinding is verbroken. Intune negeert de compatibiliteitsstatus voor niet-reagerende MTD-partners.

> [!IMPORTANT]
> U moet de MTD-apps indien mogelijk toevoegen en toewijzen voordat u het nalevingsbeleid gaat maken en de beleidsregels voor voorwaardelijke toegang gaat opstellen. Dit zorgt ervoor dat de MTD-app beschikbaar is om te worden geïnstalleerd door eindgebruikers voordat ze toegang kunnen krijgen tot e-mail of andere bedrijfsresources.

> [!TIP]
> U kunt in het Mobile Threat Defense-deelvenster **Verbindingsstatus** en het tijdstip voor de **Laatste synchronisatie** tussen Intune en de MTD-partner bekijken.

## <a name="next-steps"></a>Volgende stappen

- [Een beveiligingsbeleid voor MTD-apps (Mobile Threat Defense) maken met Intune](~/protect/mtd-app-protection-policy.md).
