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
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 0da6861b6c49fc37691b8c6e464a506670643fa3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203328"
---
# <a name="use-scope-tags-to-filter-policies"></a>Bereiktags gebruiken om beleidsregels te filteren

Met bereiktags kunt u beleidsregels filteren met door uzelf gemaakte, aangepaste tags. U kunt bereiktags toepassen op rollen en apps.

Zo kunt u een bereiktag maken met de naam 'Technische afdeling' en deze toewijzen aan configuratieprofielen met betrekking tot de technische afdeling. Wijs dezelfde tag toe aan de rol 'Technische beheerders'. Deze zien alleen de beleidsregels met de tag 'Technische afdeling'.

## <a name="to-create-a-scope-tag"></a>Een bereiktag maken

Kies **Rollen** > **Bereik (tags)** > **Maken**.

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Een bereiktag toevoegen aan een configuratieprofiel

Kies **Apparaatconfiguratie** > **Profielen** > Een profiel kiezen > **Eigenschappen** > **Bereik (tags)**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Een bereiktag toewijzen aan een rol

Kies **Rollen** > **Alle rollen** > **Beleids- en profielbeheerder** > **Toewijzingen**  >  **Bereik (Tags)**.

## <a name="to-assign-a-scope-tag-to-an-app"></a>Een bereiktag toewijzen aan een app

Kies **Client-apps** > **Apps** > kies een app > **Eigenschappen** > **Bereik (tags)** > **Toevoegen** > kies de tags > **Selecteren** > **OK** > **Opslaan**.


## <a name="next-steps"></a>Volgende stappen

Beheer uw [rollen](role-based-access-control.md) en [profielen](device-profile-assign.md).

