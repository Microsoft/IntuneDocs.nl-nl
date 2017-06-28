---
title: Het nalevingsbeleid voor Skycure Mobile Threat Defense maken
description: Maak het nalevingsbeleid voor Skycure Mobile Threat Defense in de klassieke Intune-console.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 29caf162500e25c2a0151be92aabe4cc432e241b
ms.contentlocale: nl-nl
ms.lasthandoff: 06/08/2017


---

# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a>Het nalevingsbeleid voor Skycure Mobile Threat Defense maken

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Met Intune met Skycure Mobile Threat Defense kunt u bedreigingen op mobiele apparaten detecteren en de risico's op die apparaten beoordelen. U kunt een Intune-nalevingsbeleidsregel maken voor een risicoanalyse waarmee wordt bepaald of het apparaat compatibel is. Vervolgens kunt u beleid voor voorwaardelijke toegang gebruiken om toegang tot services te blokkeren op basis van de apparaatcompatibiliteit.

## <a name="before-you-begin"></a>Voordat u begint

Vereisten voor het nalevingsbeleid bij Skycure Mobile Threat Defense:

-   [De integratie van Skycure met Intune instellen](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [De verbinding voor Skycure inschakelen in Intune](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

Als onderdeel van de configuratie voor Skycure Mobile Threat Defense in de Skycure-console hebt u een beleid gemaakt waarmee verschillende bedreigingen in de categorieën Hoog, Gemiddeld en Laag worden ingedeeld. In het nalevingsbeleid van Intune moet u nu het maximaal toegestane bedreigingsniveau instellen.

## <a name="to-create-skycure-compliance-policy"></a>Het nalevingsbeleid voor Skycure maken

1.  Ga naar de [klassieke Intune-console](https://manage.microsoft.com/) en voer vervolgens uw referenties in.

2.  Kies **Beleid** &gt; **Nalevingsbeleid**. U kunt een bestaand nalevingsbeleid gebruiken of een nieuw beleid maken.

3.  Kies **Toevoegen** &gt; **Apparaatstatus** en schakel vervolgens **Mobile Threat Defense** in.

4.  Selecteer **Maximaal toegestaan bedreigingsniveau**:

    a.  **Geen (beveiligd)**: dit is het meest veilige niveau. Het apparaat kan geen enkele bedreiging hebben en heeft nog altijd toegang tot bedrijfsbronnen. Als er bedreigingen worden gevonden, wordt het apparaat geëvalueerd als niet-compatibel.

    b.  **Laag**: het apparaat is compatibel als er alleen bedreigingen van een laag niveau aanwezig zijn. Als een hoger niveau wordt aangetroffen, krijgt het apparaat de status niet-compatibel.

    c.  **Gemiddeld**: het apparaat is compatibel als de bedreigingen op het apparaat van laag of gemiddeld niveau zijn. Als er bedreigingen van hoog niveau worden aangetroffen, wordt het apparaat als niet-compatibel beoordeeld.

    d.  **Hoog**: dit is de minst veilige optie. Hiermee worden alle bedreigingsniveaus toegestaan en wordt Skycure Mobile Threat Defense uitsluitend gebruikt voor rapportagedoeleinden.

> [!IMPORTANT]
> Als u beleid voor voorwaardelijke toegang voor Office 365 of andere services maakt, wordt deze compatibiliteitsevaluatie bekeken en wordt niet-compatibele apparaten de toegang tot die services geweigerd tot de bedreiging is opgelost.

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Volgende stappen

-   Een beleid voor voorwaardelijke toegang maken voor:

    -   [Exchange Online](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [Exchange On-premises](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [Skype voor Bedrijven Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [Dynamics CRM](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

