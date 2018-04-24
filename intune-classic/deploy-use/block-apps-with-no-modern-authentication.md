---
title: Apps zonder moderne verificatie blokkeren
description: ''
keywords: ''
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 10/15/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e533dada76f5b996478a548af503d808831e3733
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Apps die geen gebruik maken van moderne verificatie blokkeren (ADAL)

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Voorwaardelijke toegang voor apps met een app-beveiligingsbeleid is afhankelijk van toepassingen die gebruikmaken van [moderne verificatie](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), een implementatie van OAuth2. De nieuwste Office-toepassingen voor mobiele en bureaubladtoepassingen gebruiken moderne verificatie, maar er zijn ook apps van derden en oudere Office-apps die gebruikmaken van andere verificatiemethoden, zoals basisverificatie en op formulieren gebaseerde verificatie.

Als u de toegang tot deze apps wilt blokkeren, raden we u het volgende aan:

* Met het instellen van ADFS worden er regels van kracht die niet-moderne verificatieprotocollen blokkeren. Gedetailleerde instructies vindt u in scenario 3: [alle toegang tot O365 blokkeren behalve op browser gebaseerde toepassingen](https://technet.microsoft.com/library/dn592182.aspx).
* Voor **SharePoint Online** schakelt u in de SharePoint Online-service niet-moderne verificatie in met behulp van de PowerShell-commandlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) om de eigenschap voor verouderde verificatieprotocollen in te stellen op false:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false
```


>[!IMPORTANT]
>Een app-certificeringsinstantie mag niet worden gebruikt in combinatie met verificatie via het certificaat op basis van Azure Active Directory (Azure AD). U mag slechts een van beide geconfigureerd hebben.

### <a name="see-also"></a>Zie tevens
[Alleen apps toestaan die worden ondersteund door Intune voor toegang tot O365-services](allow-policy-managed-apps-access-to-o365.md)
