---
title: Apps zonder moderne verificatie blokkeren in Intune
titleSuffix: Microsoft Intune
description: Meer informatie over het blokkeren van apps die geen gebruik maken van moderne verificatie (ADAL).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf8b323d6f7afa5fc7e3cfecbf04f61e0d11d9c5
ms.sourcegitcommit: 6ff5df63a2fff291d7ac5fed9c51417fe808650d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52167362"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Apps die geen gebruik maken van moderne verificatie blokkeren (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Voorwaardelijke toegang voor apps met een app-beveiligingsbeleid is afhankelijk van toepassingen die gebruikmaken van [moderne verificatie](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), een implementatie van OAuth2. De meeste huidige mobiele en desktoptoepassingen van Office maken gebruik van moderne verificatie. Er zijn echter ook apps van derden en oudere Office-apps die gebruikmaken van andere verificatiemethoden, zoals basisverificatie en op formulieren gebaseerde verificatie.

Als u de toegang tot deze apps wilt blokkeren, raden we u de volgende methoden aan:

* Met het instellen van ADFS worden er regels van kracht die niet-moderne verificatieprotocollen blokkeren. Gedetailleerde instructies vindt u in scenario 3: [alle toegang tot O365 blokkeren behalve op browser gebaseerde toepassingen](https://technet.microsoft.com/library/dn592182.aspx).
* Gebruik voorwaardelijke toegang voor Azure Active Directory voor **Exchange en SharePoint Online** en gebruik de PowerShell-cmdlet Set-SPOTenant voor SharePoint Online. Zie [SharePoint Online en Exchange Online instellen voor voorwaardelijke toegang voor Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols) voor gedetailleerde instructies.


>[!IMPORTANT]
>Een app-certificeringsinstantie mag niet worden gebruikt in combinatie met verificatie via het certificaat op basis van Azure Active Directory (Azure AD). U mag slechts een van beide geconfigureerd hebben.

### <a name="see-also"></a>Zie tevens
[Op apps gebaseerde voorwaardelijke toegang met Intune](app-based-conditional-access-intune.md)
