---
title: Een beveiligingsbeleid voor MTD-apps (Mobile Threat Defense) maken met Intune
titleSuffix: Microsoft Intune
description: Een beveiligingsbeleid voor MTD-apps (Mobile Threat Defense) maken met Microsoft Intune.
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
ms.openlocfilehash: 15d986bc5017a44571c6194f9c6b53167b671349
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72794417"
---
# <a name="create-mobile-threat-defense-app-protection-policy-with-intune"></a>Een beveiligingsbeleid voor Mobile Threat Defense-apps maken met Intune

> [!NOTE] 
> Dit artikel is van toepassing op alle MTD-partners (Mobile Threat Defense) die ondersteuning bieden aan beleid voor app-beveiliging: Better Mobile (Android), Zimperium (iOS), Lookout for Work (Android/iOS).

Intune met MTD helpt u bij het detecteren van bedreigingen en het beoordelen van risico op mobiele apparaten. U kunt een Intune-beveiligingsbeleid maken voor het inschatten van risico's om zo te bepalen of het apparaat al dan niet toegang tot bedrijfsgegevens moet krijgen. 

## <a name="before-you-begin"></a>Voordat u begint

Als onderdeel van de configuratie van MTD in de MTD-partnerconsole, hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. U moet nu het MTD-niveau instellen in het beveiligingsbeleid van de Intune-app.

Vereisten voor beveiligingsbeleid voor apps met MTD:

- De integratie van MTD met Intune instellen. Zonder deze integratie heeft het beveiligingsbeleid van de MTD-app geen effect.

## <a name="to-create-an-mtd-app-protection-policy"></a>Een beveiligingsbeleid voor MTD-apps maken

1. Ga naar [Azure Portal](https://portal.azure.com/) en meld u aan met uw Intune-referenties.

2. Kies in het **Azure-dashboard** in het linkermenu de optie **Alle services** en typ vervolgens **Intune** in het filtertekstvak.

3. Kies **Intune**. Vervolgens ziet u het **Intune-dashboard**.

4. Kies in het **Intune-dashboard** de optie **Client-apps** en kies vervolgens **Beleid voor app-beveiliging** onder de sectie **Beheren**.

5. Kiese **Beleid maken**, voer de **naam** en de **beschrijving** in en selecteer het **platform**. 

6. Kies in het deelvenster **Voorwaardelijk starten** onder de tabel **Apparaatvoorwaarden** het Mobile Threat-niveau in de vervolgkeuzelijst onder **Maximaal toegestaan bedreigingsniveau van apparaat**.

    a.  **Beveiligd**: Dit is het veiligste niveau. Het apparaat kan geen enkele bedreiging hebben en heeft nog altijd toegang tot bedrijfsbronnen. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.

    b.  **Laag**: het apparaat is conform als er alleen bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.

    c.  **Gemiddeld**: het apparaat is conform als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.

    d.  **Hoog**: dit is het minst veilige niveau. Hiermee worden alle bedreigingsniveaus toegestaan en wordt Mobile Threat Defense uitsluitend gebruikt voor rapportagedoeleinden. Op apparaten moet de MTD-app met deze instelling zijn geactiveerd.

7. Klik tweemaal op **Opslaan** en kies vervolgens **Maken**.

## <a name="to-assign-an-mtd-app-protection-policy"></a>Een beveiligingsbeleid voor MTD-apps toewijzen

Als u een nalevingsbeleid voor apparaten aan gebruikers wilt toewijzen, kiest u een beleid dat u eerder hebt geconfigureerd. Bestaande beleidsregels vindt u in het deelvenster **Apparaatnaleving - beleid**.

1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Met deze actie opent u het deelvenster waar u **Azure Active Directory-beveiligingsgroepen** kunt selecteren en aan het beleid kunt toewijzen.

2. Kies **Groepen selecteren om op te nemen** om het deelvenster met de Azure AD-beveiligingsgroepen te openen. Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.

> [!NOTE] 
> U hebt het beleid toegepast op gebruikers. De apparaten die door de gebruikers worden gebruikt en waarop het beleid zich richt, worden via Intune-app-beveiliging geëvalueerd voor toegang tot bedrijfsgegevens op bepaalde doel-apps.

## <a name="next-steps"></a>Volgende stappen  

- Meer informatie over [Mobile Threat Defense](~/protect/mobile-threat-defense.md) in Microsoft Intune.
