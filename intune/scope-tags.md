---
title: Beleid met bereiktags filteren in Microsoft Intune - Azure | Microsoft Docs
description: Bereiktags gebruiken voor het filteren van configuratieprofielen op specifieke rollen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 000505df3c0898ed0939244dfe1b075c64097611
ms.sourcegitcommit: e814cfbbefe818be3254ef6f859a7bf5f5b99123
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/31/2018
ms.locfileid: "43329424"
---
# <a name="use-scope-tags-to-filter-policies"></a>Bereiktags gebruiken om beleidsregels te filteren

Met bereiktags kunt u beleidsregels filteren met door uzelf gemaakte, aangepaste tags.

Zo kunt u een bereiktag maken met de naam 'Technische afdeling' en deze toewijzen aan configuratieprofielen met betrekking tot de technische afdeling. Wijs dezelfde tag toe aan de rol 'Technische beheerders'. Deze zien alleen de beleidsregels met de tag 'Technische afdeling'.

## <a name="to-create-a-scope-tag"></a>Een bereiktag maken

Kies **Rollen** > **Bereik (tags)** > **Maken**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Een bereiktag toevoegen aan een configuratieprofiel

Kies **Apparaatconfiguratie** > **Profielen** > Een profiel kiezen > **Eigenschappen** > **Bereik (tags)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Een bereiktag toewijzen aan een rol

Kies **Rollen** > **Alle rollen** > **Beleids- en profielbeheerder** > **Toewijzingen**  >  **Bereik (Tags)**.

## <a name="next-steps"></a>Volgende stappen

Beheer uw [rollen](role-based-access-control.md) en [profielen](device-profile-assign.md).

