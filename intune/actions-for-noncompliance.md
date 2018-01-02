---
title: Acties voor niet-naleving met Intune
titleSuffix: Intune on Azure
description: Informatie over het maken van acties voor niet-naleving met Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 85eb19a07ce42dcaf61ce34637644761880cb0b9
ms.sourcegitcommit: 548b9e6c1e50074a5ffb89160ae23ee3caa5ba65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/06/2017
---
# <a name="automate-actions-for-noncompliance"></a>Acties voor niet-naleving automatiseren

Met de **acties voor niet-naleving** kunt u een op tijd geordende opeenvolgende reeks acties configureren die worden toegepast op apparaten die niet voldoen aan de criteria van het nalevingsbeleid zijn. De standaardactie is dat zodra Intune detecteert dat een apparaat niet voldoet aan de criteria van het nalevingsbeleid, het apparaat wordt gemarkeerd en wordt geblokkeerd door voorwaardelijke toegang van Azure AD. Met de **acties voor niet-naleving** beschikt u over meer flexibiliteit om te bepalen wat er gebeurt bij niet-naleving van een apparaat. U kunt er bijvoorbeeld voor kiezen het apparaat niet onmiddellijk te blokkeren, maar de gebruiker een respijtperiode te bieden om ervoor te zorgen dat het apparaat weer compatibel wordt.

Er zijn twee soorten acties:

-   **Eindgebruikers informeren per e-mail**: u kunt een de e-mailmelding aanpassen voordat u die verstuurt naar de eindgebruikers. In Intune kunt u aanpassingen doorvoeren in het onderwerp, de berichttekst, inclusief het bedrijfslogo, en contactgegevens.

-   **Apparaat markeren voor niet-naleving**: u kunt een schema instellen met een aantal dagen waarna het apparaat wordt gemarkeerd voor niet-naleving. Dit kan onmiddellijk, maar u kunt de gebruiker ook een respijtperiode bieden, zodat deze ervoor kan zorgen dat het apparaat weer voldoet aan het nalevingsbeleid.

## <a name="before-you-begin"></a>Voordat u begint

U moet ten minste één nalevingsbeleid voor apparaten hebben gemaakt om acties voor niet-naleving in te stellen.

-   Meer informatie over het maken van een nalevingsbeleid voor:

    -   [Android](compliance-policy-create-android.md)

    -   [Android for Work](compliance-policy-create-android-for-work.md)

    -   [iOS](compliance-policy-create-ios.md)
    
    -   [macOS](compliance-policy-create-mac-os.md)

    -   [Windows](compliance-policy-create-windows.md)

U moet voorwaardelijke toegang voor Azure AD hebben ingesteld wanneer u van plan bent nalevingsbeleidsregels voor apparaten te gebruiken om de toegang van apparaten tot bedrijfsbronnen te blokkeren.

- Meer informatie over [het instellen van voorwaardelijke toegang voor EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Daarnaast moet u een sjabloon voor een meldingsbericht hebben gemaakt. De sjabloon voor het meldingsbericht wordt later gebruikt bij het maken van acties voor niet-naleving om een e-mail te verzenden naar uw gebruikers.

### <a name="to-create-a-notification-message-template"></a>Een sjabloon voor een meldingsbericht toevoegen

1. Ga naar [Intune-portal in Azure](https://portal.azure.com) en meld u aan met uw Intune-referenties.

2. Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

3. Kies **Intune**

4. Kies **Apparaatnaleving** en vervolgens **Meldingen** onder de sectie **Beheren**.

5. Kies **Melding maken** en voer het volgende in:

    a.  Naam

    b.  Onderwerp

    c.  Bericht

    d.  Koptekst - Bedrijfslogo opnemen

    e.  Voertekst - Bedrijfslogo opnemen

    f.  E-mailvoettekst – Contactgegevens opnemen

![voorbeeldsjabloon voor meldingsbericht](./media/actionsfornoncompliance-1.PNG)

Nadat u klaar bent met het toevoegen van informatie, kiest u **Maken**. De sjabloon voor het meldingsbericht is beschikbaar voor gebruik.

> [!NOTE] 
> U kunt ook een eerder gemaakte meldingssjabloon bewerken.

## <a name="to-create-actions-for-non-compliance"></a>Acties voor niet-naleving maken

> [!TIP]
> Intune biedt standaard een vooraf gedefinieerde actie in de sectie Acties voor niet-naleving. Dit is de actie waarbij het apparaat wordt gemarkeerd voor niet-naleving nadat is gedetecteerd dat het niet voldoet aan de criteria van het beleid voor apparaatnaleving. U kunt aanpassen hoe lang na de detectie het apparaat wordt gemarkeerd voor niet-naleving. Deze actie kan niet worden verwijderd.

U kunt een actie toevoegen op het moment dat u een nieuw nalevingsbeleid voor apparaten maakt of door een bestaand nalevingsbeleid voor apparaten te bewerken.

1.  Kies in de Intune-workload op de blade **Nalevingsbeleid voor apparaten** de optie **Beleidsregels** onder de sectie **Beheren**.

2.  Kies een beleid voor apparaatnaleving door erop te klikken, en kies vervolgens **Eigenschappen** onder de sectie **Beheren**.

3.  De blade **eigenschappen voor nalevingsbeleid voor apparaten**. Kies **Acties voor niet-naleving**.

4.  De blade Acties voor niet-naleving wordt geopend. Kies **toevoegen** om actieparameters op te geven. U kunt de eerder gemaakte berichtsjabloon kiezen, extra ontvanger en de planning voor de respijtperiode. Bij het schema kunt u het aantal dagen (0-365) instellen voor het afdwingen van het beleid voor voorwaardelijke toegang. Als u **0** dagen opgeeft, betekent dit dat voorwaardelijke toegang **onmiddellijk** toegang tot bedrijfsbronnen moet blokkeren zodra de apparaten niet voldoen aan het nalevingsbeleid voor apparaten.

5.  Nadat u klaar bent met het toevoegen van informatie, kiest u **Toevoegen** en vervolgens **OK**.

## <a name="next-steps"></a>Volgende stappen

U kunt de activiteiten van het nalevingsbeleid voor apparaten bewaken door de rapporten uit te voeren die beschikbaar zijn op de blade Apparaatnaleving. Zie [De apparaatnaleving controleren in Intune](device-compliance-monitor.md) voor meer informatie.

