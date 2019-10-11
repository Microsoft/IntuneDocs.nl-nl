---
title: Op apps gebaseerd beleid instellen voor voorwaardelijke toegang met Intune
titleSuffix: Microsoft Intune
description: Ontdek hoe u op apps gebaseerd beleid voor voorwaardelijke toegang maakt met Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9cbe57d0cf69f036cd36d2c1b95c48b198645e7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723083"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Op apps gebaseerd beleid instellen voor voorwaardelijke toegang met Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Op apps gebaseerd beleid instellen voor voorwaardelijke toegang voor apps die deel uitmaken van de lijst met goedgekeurde apps. De lijst met goedgekeurde apps bestaat uit apps die zijn getest door Microsoft.

> [!IMPORTANT]
> In dit artikel worden de stappen besproken die u moet volgen om een beleid voor voorwaardelijke toegang op basis van apps toe te voegen. U kunt dezelfde stappen volgen voor het toevoegen van apps zoals SharePoint Online, Microsoft Teams en Microsoft Exchange Online uit de lijst met goedgekeurde apps.

## <a name="create-app-based-conditional-access-policies"></a>Op apps gebaseerd beleid maken voor voorwaardelijke toegang
Voorwaardelijke toegang is een technologie van Azure Active Directory (Azure AD). Het knooppunt voor voorwaardelijke toegang dat via *Intune* wordt geopend, is hetzelfde als het knooppunt dat u opent via *Azure AD*. Dit betekent dat u niet hoeft te schakelen tussen Intune en Azure AD om beleid te configureren.

> [!IMPORTANT]
> U hebt een Azure AD Premium-licentie nodig om beleid voor voorwaardelijke toegang in te stellen vanuit de Intune-portal.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Op apps gebaseerd beleid voor voorwaardelijke toegang maken

> [!IMPORTANT]
> U moet [op apps gebaseerd beveiligingsbeleid voor Intune](../apps/app-protection-policies.md) hebben toegepast op uw apps voordat u op apps gebaseerd beleid voor voorwaardelijke toegang kunt gebruiken.

1. Selecteer op het **Intune-dashboard** de optie **Voorwaardelijke toegang**.

2. Kies in het deelvenster **Beleid** de optie **Nieuw beleid** om uw nieuw op apps gebaseerd beleid voor voorwaardelijke toegang te maken.

4. Nadat u een naam voor het beleid hebt ingevoerd en de instellingen in de sectie **Toewijzingen** hebt geconfigureerd, kiest u **Verlenen** onder de sectie **Toegangscontroles**.

5. Kies **Goedgekeurde client-app vereisen** , kies **Selecteren** en kies vervolgens **Maken** om het nieuwe beleid op te slaan.

## <a name="next-steps"></a>Volgende stappen
[Apps die geen gebruikmaken van moderne verificatie blokkeren](app-modern-authentication-block.md)

## <a name="see-also"></a>Zie tevens

[App-gegevens beveiligen met app-beveiligingsbeleid](../apps/app-protection-policies.md)
[Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
