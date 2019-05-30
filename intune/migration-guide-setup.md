---
title: Basisconfiguratie van Microsoft Intune
description: In dit artikel wordt beschreven wat de benodigde stappen zijn voor het instellen van Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 233b093ba9c062618740fd8f14c5ea306647acdd
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050499"
---
# <a name="basic-setup"></a>Basisconfiguratie

Nadat u uw omgeving hebt geëvalueerd, is het tijd om Microsoft Intune in te stellen.

## <a name="external-dependencies-for-an-intune-deployment"></a>Externe afhankelijkheden voor een Intune-implementatie

### <a name="identity"></a>Identiteit

Voor Intune is Azure Active Directory (Azure AD) vereist als id- en gebruikersgroepprovider. Meer informatie over:

-  [Identiteitsvereisten](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [Adreslijstsynchronisatie](https://docs.microsoft.com/azure/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [Multi-factor authentication (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

-   [Gebruikers- en apparaatgroepen plannen](users-add.md)

-   [Gebruikers- en apparaatgroepen maken](groups-get-started.md)

Als uw organisatie al met Office 365 werkt, moet Intune van dezelfde Azure Active Directory-omgeving gebruikmaken.

### <a name="pki-optional"></a>PKI (optioneel)

Als u van plan bent om bij Intune verificatie op basis van certificaten te gebruiken voor VPN-, Wi-Fi- of e-mailprofielen, moet u ervoor zorgen dat u over een ondersteunde [PKI-infrastructuur](certificates-configure.md) beschikt waarmee certificaatprofielen kunnen worden gemaakt en geïmplementeerd. Meer informatie over het configureren van certificaten in Intune:

-   [De certificaatinfrastructuur voor SCEP configureren](/intune/certificates-scep-configure)

-   [De certificaatinfrastructuur voor PFX configureren](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Lijst met taken voor een Intune-configuratie

### <a name="task-1-intune-subscription"></a>Taak 1: Intune-abonnement

Voordat u naar Intune kunt migreren, moet u eerst beschikken over een Intune-abonnement.

-   U kunt naar [deze pagina](https://admin.microsoft.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) gaan, waar instructies worden gegeven voor het volgende:

    -   Een nieuw Intune-abonnement maken dat is gekoppeld aan een nieuwe AAD-tenant.

    -   Het Intune-abonnement koppelen door aanmelding bij een bestaande AAD-tenant.

### <a name="task-2-assign-intune-user-licenses"></a>Taak 2: Intune-gebruikerslicenties toewijzen

-   Meer informatie over het [toewijzen van Intune-gebruikerslicenties](licenses-assign.md).

-   Als u een nieuwe AAD-tenant hebt gemaakt, lees dan [hoe u nieuwe gebruikers maakt of gebruikers uit uw on-premises Active Directory (AD) synchroniseert.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Taak 3: de MDM-instantie instellen op Intune

Intune kan worden beheerd via Azure Portal of de Configuration Manager Current Branch-console. Tenzij u Intune wilt integreren met een Configuration Manager Current Branch-implementatie, raden we u aan Intune te beheren via de [Azure Portal](https://portal.azure.com).

Stel de MDM-instantie in op **Intune** om Intune Azure Portal in te schakelen. Door het gebruik van een andere MDM-instantie kan Intune het MDM-beheer overdragen aan andere Microsoft-beheerconsoles. Deze gevallen zijn niet gebruikelijk.

> [!IMPORTANT]
> Als u het beheer van mobiele apparaten voor het eerst overdraagt aan Intune, moet u de MDM-instantie instellen op Intune.

Meer informatie over [het instellen van de instantie voor het beheer van mobiele apparaten](mdm-authority-set.md).

## <a name="next-step"></a>Volgende stap

[Beheerbeleid voor apparaten en apps configureren](migration-guide-configure-policies.md).
