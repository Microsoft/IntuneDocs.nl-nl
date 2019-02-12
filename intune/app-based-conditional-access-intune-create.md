---
title: Op apps gebaseerd beleid instellen voor voorwaardelijke toegang met Intune
titlesuffix: Microsoft Intune
description: Ontdek hoe u op apps gebaseerd beleid voor voorwaardelijke toegang maakt met Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2026a446ffef3bd845affe45a7732ef3ab8ec24
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842912"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Op apps gebaseerd beleid instellen voor voorwaardelijke toegang met Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Op apps gebaseerd beleid instellen voor voorwaardelijke toegang voor apps die deel uitmaken van de lijst met goedgekeurde apps. De lijst met goedgekeurde apps bestaat uit apps die zijn getest door Microsoft.

> [!IMPORTANT]
> In dit artikel worden de stappen besproken die u moet volgen om een beleid voor voorwaardelijke toegang op basis van apps toe te voegen. U kunt dezelfde stappen volgen voor het toevoegen van apps zoals SharePoint Online, Microsoft Teams en Microsoft Exchange Online uit de lijst met goedgekeurde apps.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Voorwaardelijk toegangsbeleid op basis van apps maken in Azure AD-werkbelasting

IT-beheerders kunnen op apps gebaseerd voorwaardelijk toegangsbeleid maken uitgaande van de workload van Azure AD. Dankzij deze toegang hoeft u niet te schakelen tussen Azure en de Intune-werkbelastingen.

> [!IMPORTANT]
> Als u beleid voor voorwaardelijke toegang voor Azure AD wilt instellen vanuit Intune Azure Portal, moet u een Azure AD Premium-licentie hebben.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Op apps gebaseerd beleid voor voorwaardelijke toegang maken

> [!IMPORTANT]
> U moet [op apps gebaseerd beveiligingsbeleid voor Intune](app-protection-policies.md) hebben toegepast op uw apps voordat u op apps gebaseerd beleid voor voorwaardelijke toegang kunt gebruiken.

1. Kies in het**Intune-dashboard** **Voorwaardelijke toegang**.

2. Kies in het deelvenster **Beleid** de optie **Nieuw beleid** om uw nieuw op apps gebaseerd beleid voor voorwaardelijke toegang te maken.

4. Nadat u een naam voor het beleid hebt ingevoerd en de instellingen in de sectie **Toewijzingen** hebt geconfigureerd, kiest u **Verlenen** onder de sectie **Toegangscontroles**.

5. Kies **Goedgekeurde client-app vereisen** , kies **Selecteren** en kies vervolgens **Maken** om het nieuwe beleid op te slaan.

## <a name="next-steps"></a>Volgende stappen
[Apps die geen gebruikmaken van moderne verificatie blokkeren](app-modern-authentication-block.md)

### <a name="see-also"></a>Zie tevens

[App-gegevens beveiligen met app-beveiligingsbeleid](app-protection-policies.md)
[Voorwaardelijke toegang in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
