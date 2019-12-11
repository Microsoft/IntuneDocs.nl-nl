---
title: Een beveiligingsbeleid voor MTD-apps (Mobile Threat Defense) maken met Intune
titleSuffix: Microsoft Intune
description: Een beveiligingsbeleid voor MTD-apps (Mobile Threat Defense) maken met Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
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
ms.openlocfilehash: 48dc7de86965741d8ed42bd5a5f29f72ae66d4f3
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74188502"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Een beveiligingsbeleid voor Mobile Threat Defense-apps maken met Intune

Intune met Mobile Threat Defense (MTD) helpt u bij het detecteren van bedreigingen en het beoordelen van risico op mobiele apparaten. U kunt een Intune-beveiligingsbeleid maken voor het inschatten van risico's om zo te bepalen of het apparaat al dan niet toegang tot bedrijfsgegevens moet krijgen.


> [!NOTE]
> Dit artikel is van toepassing op alle Mobile Threat Defense-partners die ondersteuning bieden aan beleid voor app-beveiliging:
>
> - Better Mobile (Android)
> - Zimperium (iOS)
> - Lookout for Work (Android, iOS).

## <a name="before-you-begin"></a>Voordat u begint

Als onderdeel van de configuratie van MTD in de MTD-partnerconsole, hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. U moet nu het MTD-niveau instellen in het beveiligingsbeleid van de Intune-app.

Vereisten voor beveiligingsbeleid voor apps met MTD:

- De integratie van MTD met Intune instellen. Zonder deze integratie heeft het beveiligingsbeleid van de MTD-app geen effect.

## <a name="to-create-an-mtd-app-protection-policy"></a>Een beveiligingsbeleid voor MTD-apps maken

Gebruik de procedure om [en beleid voor toepassingsbeveiliging te maken voor iOS/iPadOS of Android](../apps/app-protection-policies.md#app-protection-policies-for-iosipados-and-android-apps) en gebruik de volgende informatie op de pagina's *Apps*, *Voorwaardelijk starten*en *Toewijzingen*:

- **Apps**: selecteer de app voor de Mobile Threat Defense-partner die u gebruikt.
- **Voorwaardelijk starten**:  gebruik onder *Apparaatvoorwaarden* de vervolgkeuzelijst om **Maximaal toegestaan bedreigingsniveau van apparaat** te selecteren.

  Opties voor de **Waarde** van het bedreigingsniveau:

  - **Beveiligd**: Dit is het veiligste niveau. Het apparaat kan geen enkele bedreiging hebben en heeft nog altijd toegang tot bedrijfsbronnen. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.
  - **Laag**: het apparaat is conform als er alleen bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.
  - **Gemiddeld**: het apparaat is conform als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.
  - **Hoog**: dit is het minst veilige niveau. Hiermee worden alle bedreigingsniveaus toegestaan en wordt Mobile Threat Defense uitsluitend gebruikt voor rapportagedoeleinden. Op apparaten moet de MTD-app met deze instelling zijn geactiveerd.

  Opties voor **Actie**:

  - **Toegang blokkeren**
  - **Gegevens wissen**

- **Toewijzingen**: wijs het beleid toe aan uw groepen gebruikers.  De apparaten die door de leden van de groep worden gebruikt, worden via Intune-app-beveiliging geëvalueerd voor toegang tot bedrijfsgegevens op bepaalde doel-apps.


## <a name="next-steps"></a>Volgende stappen  

- Meer informatie over [Mobile Threat Defense](~/protect/mobile-threat-defense.md) in Microsoft Intune.
