---
title: Op apps gebaseerd beleid instellen voor voorwaardelijke toegang met Intune
titleSuffix: Microsoft Intune
description: Ontdek hoe u op apps gebaseerd beleid voor voorwaardelijke toegang maakt met Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 465f8b0001e5e2a049a3ffe12469bdb5057854ec
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "73712843"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Op apps gebaseerd beleid instellen voor voorwaardelijke toegang met Intune

Op apps gebaseerd beleid instellen voor voorwaardelijke toegang voor apps die deel uitmaken van de lijst met goedgekeurde apps. De lijst met goedgekeurde apps bestaat uit apps die zijn getest door Microsoft.

Voordat u op apps gebaseerd beleid voor voorwaardelijke toegang kunt gebruiken, moet u [op apps gebaseerd beveiligingsbeleid voor Intune](../apps/app-protection-policies.md) op uw apps hebben toegepast.

> [!IMPORTANT]
> In dit artikel worden de stappen besproken die u moet volgen om een beleid voor voorwaardelijke toegang op basis van apps toe te voegen. U kunt dezelfde stappen volgen voor het toevoegen van apps zoals SharePoint Online, Microsoft Teams en Microsoft Exchange Online uit de lijst met goedgekeurde apps.

## <a name="create-app-based-conditional-access-policies"></a>Op apps gebaseerd beleid maken voor voorwaardelijke toegang

Voorwaardelijke toegang is een technologie van Azure Active Directory (Azure AD). Het knooppunt voor voorwaardelijke toegang dat u via *Intune* opent, is hetzelfde knooppunt dat u opent via *Azure AD*. Aangezien het om hetzelfde knooppunt gaat, hoeft u niet te schakelen tussen Intune en Azure AD om beleid te configureren.

Voordat u beleid voor voorwaardelijke toegang kunt maken vanuit het Microsoft Endpoint Manager-beheercentrum, moet u een Azure AD Premium-licentie hebben.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Op apps gebaseerd beleid voor voorwaardelijke toegang maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431)

2. Selecteer **Eindpuntbeveiliging** > **Voorwaardelijke toegang** > **Nieuw beleid**.

3. Voer een **naam** voor het beleid in en selecteer onder *Toewijzingen* **Gebruikers en groepen**. Gebruik de opties Opnemen of Uitsluiten om uw groepen voor het beleid toe te voegen en selecteer **Klaar**.

4. Selecteer **Cloud-apps of acties** en kies welke apps u wilt beveiligen. Kies bijvoorbeeld **Apps selecteren** en selecteer **Office 365 SharePoint Online** en **Office 365 Exchange Online**.

   Selecteer **OK** om uw wijzigingen op te slaan.

5. Selecteer **Voorwaarden** > **Client-apps** om het beleid toe te passen op apps en browsers. Selecteer bijvoorbeeld **Ja** en schakel vervolgens **Browser** en **Mobiele apps en bureaublad-clients** in.

   Selecteer **OK** om uw wijzigingen op te slaan.

6. Selecteer onder *Besturingselementen voor toegang* de optie **Verlenen** om voorwaardelijke toegang toe te passen op basis van apparaatcompatibiliteit. Selecteer bijvoorbeeld **Toegang verlenen** > **Vereisen dat apparaat wordt gemarkeerd als conform**.

   Kies **Selecteren** om uw wijzigingen op te slaan.

7. Voor **Beleid inschakelen** selecteert u **Aan** en vervolgens **Maken** om de wijzigingen op te slaan.





## <a name="next-steps"></a>Volgende stappen
[Apps die geen gebruikmaken van moderne verificatie blokkeren](app-modern-authentication-block.md)

## <a name="see-also"></a>Zie tevens

[App-gegevens beveiligen met app-beveiligingsbeleid](../apps/app-protection-policies.md)
[Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
