---
title: Apps zonder moderne verificatie blokkeren in Intune
titleSuffix: Microsoft Intune
description: Informatie over app en moderne verificatie (ADAL) met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ca96f36f8813d80c7ebb07bfb3bd65f8aa0b392
ms.sourcegitcommit: 71314481e644025c005019b478b4cbeaf2390ea9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2019
ms.locfileid: "59569100"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Blokkeer apps die geen gebruikmaken van moderne verificatie (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Voorwaardelijke toegang voor apps met een app-beveiligingsbeleid is afhankelijk van toepassingen die gebruikmaken van [moderne verificatie](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), een implementatie van OAuth2. De meeste huidige mobiele en desktoptoepassingen van Office maken gebruik van moderne verificatie. Er zijn echter ook apps van derden en oudere Office-apps die gebruikmaken van andere verificatiemethoden, zoals basisverificatie en op formulieren gebaseerde verificatie.

## <a name="block-access-to-apps"></a>Toegang blokkeren tot apps

Als u toegang wilt blokkeren tot apps die niet gebruikmaken van moderne verificatie, gebruikt u Intune-appbeschermingsbeleid om voorwaardelijke toegang te implementeren. Raadpleeg [Op app gebaseerde voorwaardelijke toegang met Intune](app-based-conditional-access-intune.md) voor meer informatie.

## <a name="additional-information"></a>Aanvullende informatie

Bekijk de volgende onderwerpen voor meer informatie over voorwaardelijke toegang met Azure AD:
- [Wat is voorwaardelijke toegang in Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Hoe op apps gebaseerde voorwaardelijke toegang werkt](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [SharePoint Online en Exchange Online instellen voor voorwaardelijke toegang voor Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Volgende stappen

- [Op apps gebaseerde voorwaardelijke toegang met Intune](app-based-conditional-access-intune.md)
