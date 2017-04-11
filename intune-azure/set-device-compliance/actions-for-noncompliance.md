---
title: Acties voor niet-naleving
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u informatie over acties voor niet-compatibele apparaten'
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: 16da087e741e335144266c838c0a91050bd7d520
ms.lasthandoff: 03/15/2017


---

# <a name="create-actions-for-non-compliance"></a>Acties voor niet-naleving maken

Met de **acties voor niet-naleving** kunt u een op tijd geordende opeenvolgende reeks acties configureren die worden toegepast op apparaten die niet-compatibel zijn. U kunt bijvoorbeeld gebruikers van niet-compatibele apparaten hiervan per e-mail op de hoogte brengen of de toegang voor die apparaten tot bedrijfsbronnen blokkeren via voorwaardelijke toegang.

## <a name="use-case-scenario"></a>Use-casescenario

Als een apparaat door een Intune-nalevingsbeleid is gerapporteerd als niet-compatibel, wordt het apparaat standaard onmiddellijk geblokkeerd via voorwaardelijke toegang en ontvangt de gebruiker een e-mail met instructies om het apparaat weer compatibel te laten zijn. Met de **acties voor niet-naleving** beschikt u over meer flexibiliteit om te bepalen wat er gebeurt wanneer een apparaat niet compatibel is. U kunt er bijvoorbeeld voor kiezen het apparaat niet onmiddellijk te blokkeren, maar de gebruiker een respijtperiode te bieden om ervoor te zorgen dat het apparaat weer compatibel wordt.

Er zijn twee soorten acties:

-   De gebruiker waarschuwen via e-mail

-   Toegang tot zakelijke bronnen blokkeren via voorwaardelijke toegang

## <a name="notify-the-user-via-email"></a>De gebruiker waarschuwen via e-mail

U kunt kiezen uit vooraf gemaakte standaard e-mailsjablonen of een volledig aangepaste e-mailmelding maken. U kunt aanpassingen doorvoeren in het onderwerp en de berichttekst, en uw bedrijfslogo, contactgegevens en extra ontvangers toevoegen.

## <a name="block-corporate-resource-access-through-conditional-access"></a>Toegang tot zakelijke bronnen blokkeren via voorwaardelijke toegang

U kunt een schema vaststellen met het aantal dagen waarop de toegang op het apparaat tot bedrijfsbronnen moet worden geblokkeerd. Dit kan onmiddellijk, maar u kunt de gebruiker ook een respijtperiode bieden om ervoor te zorgen dat het apparaat weer voldoet aan het nalevingsbeleid.

## <a name="before-you-begin"></a>Voordat u begint

U moet ten minste één nalevingsbeleid voor apparaten hebben gemaakt om acties voor niet-naleving in te stellen.

-   Meer informatie over het maken van een nalevingsbeleid voor:

    -   [Android](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android)

    -   [Android for Work](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-android-for-work)

    -   [iOS](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-ios)

    -   [Windows](https://docs.microsoft.com/intune-azure/set-device-compliance/create-a-compliance-policy-for-windows)

U moet voorwaardelijke toegang voor EMS hebben ingesteld wanneer u van plan bent nalevingsbeleidsregels voor apparaten te gebruiken om de toegang van apparaten tot bedrijfsbronnen te blokkeren.

- Meer informatie over [het instellen van voorwaardelijke toegang voor EMS](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).

Daarnaast moet u een sjabloon voor een meldingsbericht hebben gemaakt. De sjabloon voor het meldingsbericht wordt later gebruikt bij het maken van acties voor niet-naleving om een e-mail te verzenden naar uw gebruikers.

### <a name="to-add-a-notification-message-template"></a>Een sjabloon voor een meldingsbericht toevoegen

Op de blade **Nalevingsbeleid voor apparaten**:

1.  Kies onder **Beheren** de optie **Meldingen**. De blade Sjabloon voor meldingsberichten wordt geopend.

    ![Een sjabloon voor een melding toevoegen](../media/afnc-1.png)

2.  Kies **Toevoegen** en definieer daarna het volgende:

    a.  Beschrijving

    b.  Van

    c.  Onderwerp

    d.  Bericht

    e.  Koptekst - Bedrijfslogo opnemen

    f.  Voertekst - Bedrijfslogo opnemen

    g.  E-mailvoettekst – Contactgegevens opnemen

     ![De sjabloon voor een meldingsbericht](../media/afnc-2.png)

Nadat u de informatie hebt toegevoegd, klikt u op **Maken**. De sjabloon voor het meldingsbericht is beschikbaar voor gebruik.

> [!NOTE] 
> U kunt ook een eerder gemaakte meldingssjabloon bewerken.

## <a name="to-create-actions-for-non-compliance"></a>Acties voor niet-naleving maken

U kunt een actie toevoegen op het moment dat u een nieuw nalevingsbeleid voor apparaten maakt of door een bestaand nalevingsbeleid voor apparaten te bewerken.

1.  Kies op de blade **Nalevingsbeleid voor apparaten** onder **Beheren** de optie **Beleidsregels**.

2.  Kies een nalevingsbeleid voor apparaten door erop te klikken.

    ![Nalevingsbeleid](../media/afnc-3.png)

3.  De blade **eigenschappen voor nalevingsbeleid voor apparaten**. Kies **Acties voor niet-naleving**.

4.  De blade Acties voor niet-naleving wordt geopend. Kies **toevoegen** om actieparameters op te geven.

    ![De blade Acties voor niet-naleving](../media/afnc-4.png)

De Acties voor niet-naleving zijn:

-   **Beleid voor voorwaardelijke toegang afdwingen**

-   **Een e-mail verzenden naar de eindgebruiker**

### <a name="enforce-conditional-access-policy"></a>Beleid voor voorwaardelijke toegang afdwingen

Ga als volgt te werk om deze actie uit voor niet-naleving toe te voegen:

1.  Kies op de blade **Acties voor niet-naleving** de optie **Toevoegen**.

2.  Selecteer op de **blade Actieparameters** de optie **Beleid voor voorwaardelijke toegang afdwingen** in de vervolgkeuzelijst voor acties.

3.  Bij **schema** kunt u het aantal dagen (0-255) instellen voor het afdwingen van het beleid voor voorwaardelijke toegang. Als u **0** dagen opgeeft, betekent dit dat voorwaardelijke toegang **onmiddellijk** toegang tot bedrijfsbronnen moet blokkeren zodra de apparaten niet compatibel zijn met het nalevingsbeleid voor apparaten.

    ![Acties voor niet-naleving plannen](../media/afnc-5.png)

4.  Kies**Toevoegen** en kies vervolgens **OK** op de blade **Acties**.

5.  Kies op de blade **eigenschappen voor nalevingsbeleid voor apparaten** de optie **Opslaan**.

### <a name="send-e-mail-to-end-user"></a>Een e-mail verzenden naar de eindgebruiker

U kunt een e-mailsjabloon gebruiken om te verzenden naar niet-compatibele gebruikers. Deze e-mailberichten helpen apparaatcompatibiliteit binnen de hele organisatie te stimuleren.

Ga als volgt te werk om deze actie uit voor niet-naleving toe te voegen:

1.  Kies op de blade **Acties voor niet-naleving** de optie **Toevoegen**.

2.  Selecteer op de **blade Actieparameters** de optie **Een e-mail verzenden naar de eindgebruiker** in de vervolgkeuzelijst voor acties.

3.  Kies een berichtsjabloon dat u eerder hebt gemaakt door te klikken op **Berichtsjabloon**. U kunt de inhoud van het berichtsjabloon bekijken. Kies vervolgens **Selecteren**.

    ![Berichtsjabloon](../media/afnc-6.png)

> [!NOTE] 
> U kunt de berichtsjabloon weergeven, maar u kunt deze niet bewerken. Als u de berichtsjabloon te bewerken wilt, moet u terugkeren naar de blade **Meldingen**.

1.  Voer bij **Schema** het aantal dagen van niet-naleving in waarna het e-mailbericht naar gebruikers moet worden verzonden. Als u **0** dagen opgeeft, betekent dit dat het e-mailbericht **onmiddellijk** wordt verzonden.

2.  Kies**Toevoegen** en kies vervolgens **OK** op de blade **Acties**.

3.  Kies op de blade **eigenschappen voor nalevingsbeleid voor apparaten** de optie **Opslaan**.

