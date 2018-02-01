---
title: Mobile Threat Defense-nalevingsbeleid voor apparaten maken met Intune
titlesuffix: Azure portal
description: Mobile Threat Defense-nalevingsbeleid voor apparaten maken in Intune
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 23155cbb84c2d170f1b0216981621e35fd3ac0f1
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>MTD-nalevingsbeleid (Mobile Threat Defense) voor apparaten maken met Intune

> [!NOTE] 
> Dit onderwerp is van toepassing op alle Mobile Threat Defense-partners.

Intune met MTD helpt u bij het detecteren van bedreigingen en het beoordelen van risico op mobiele apparaten. U kunt een Intune-nalevingsbeleidsregel maken voor een risicoanalyse waarmee wordt bepaald of het apparaat compatibel is. Vervolgens kunt u beleid voor voorwaardelijke toegang gebruiken om toegang tot services te blokkeren op basis van de apparaatcompatibiliteit.

## <a name="before-you-begin"></a>Voordat u begint

Als onderdeel van de configuratie van MTD in de MTD-partnerconsole, hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. U moet nu het MTD-niveau instellen in het nalevingsbeleid van Intune voor apparaten.

Vereisten voor apparaatnalevingsbeleid met MTD:

-   De integratie van MTD met Intune instellen

## <a name="to-create-a-mtd-device-compliance-policy"></a>Een nalevingsbeleid voor MTD-apparaten maken

1.  Ga naar [Azure Portal](https://portal.azure.com/) en meld u aan met uw Intune-referenties.

2.  Kies in het **Azure-dashboard** in het linkermenu de optie **Meer services** en typ vervolgens **Intune** in het filtertekstvak.

3.  Kies **Intune**. Vervolgens ziet u het **Intune-dashboard**.

4. Kies in het **Intune-dashboard** de optie **Apparaatcompatibiliteit** en kies vervolgens **Beleidsregels** onder de sectie **Beheren**.

5.  Kies **Beleid maken**, voer waarden in voor **Naam**, **Beschrijving** van apparaatcompatibiliteit, selecteer het **Platform** en kies vervolgens **Configureren** onder de sectie **Instellingen**.

6.  Kies **Apparaatstatus** op de blade **Nalevingsbeleid**.

7.  Kies op de blade **Apparaatstatus** het Mobile Threat-niveau uit de vervolgkeuzelijst onder **Vereisen dat het apparaat het Mobile Threat-niveau niet overschrijdt**.

    a.  **Beveiligd**: dit is het veiligste niveau. Het apparaat kan geen enkele bedreiging hebben en heeft nog altijd toegang tot bedrijfsbronnen. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.

    b.  **Laag**: het apparaat is compatibel als er alleen bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.

    c.  **Gemiddeld**: het apparaat is compatibel als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.

    d.  **Hoog**: dit is de minst veilige optie. Hiermee worden alle bedreigingsniveaus toegestaan en wordt Mobile Threat Defense uitsluitend gebruikt voor rapportagedoeleinden. Op apparaten moet de MTD-app met deze instelling zijn geactiveerd.

8.  Klik tweemaal op **OK** en kies vervolgens **Maken**.

> [!IMPORTANT]
> Als u beleid voor voorwaardelijke toegang voor Office 365 of andere services maakt, wordt de compatibiliteitsevaluatie van het apparaat bekeken en wordt niet-compatibele apparaten de toegang tot bedrijfsresources geweigerd tot de bedreiging op het apparaat is opgelost.

## <a name="to-assign-a-mtd-device-compliance-policy"></a>Een nalevingsbeleid voor MTD-apparaten toewijzen

Als u een nalevingsbeleid voor apparaten aan gebruikers wilt toewijzen, kiest u een beleid dat u eerder hebt geconfigureerd. Bestaande beleidsregels vindt u op de blade **Alle beleidsregels voor apparaatcompatibiliteit**.

1. Kies het beleid dat u aan gebruikers wilt toewijzen en kies **Toewijzingen**. Hiermee opent u de blade waar u **Azure Active Directory-beveiligingsgroepen** kunt selecteren en aan het beleid kunt toewijzen.

2. Kies **Groepen selecteren** om de blade met de Azure AD-beveiligingsgroepen te openen.  Als u **Selecteren** kiest, wordt het beleid bij gebruikers geïmplementeerd.

    > [!NOTE] 
    > U hebt het beleid toegepast op gebruikers. De apparaten die worden gebruikt door de gebruikers op wie het beleid is toegepast, worden gecontroleerd om te zien of ze voldoen aan het beleid.

## <a name="next-steps"></a>Volgende stappen

- [MTD met Intune inschakelen](mtd-connector-enable.md)