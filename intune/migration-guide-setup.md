---
title: Intune-basisconfiguratie
description: In dit artikel wordt beschreven wat de benodigde stappen zijn voor het configureren van Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="basic-setup"></a>Basisconfiguratie

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Nadat u uw omgeving hebt geëvalueerd, is het tijd om Intune te configureren.

## <a name="external-dependencies-for-an-intune-deployment"></a>Externe afhankelijkheden voor een Intune-implementatie

### <a name="identity"></a>Identiteit

Voor Intune is Azure Active Directory (Azure AD) vereist als id- en gebruikersgroepprovider.

-   Meer informatie over [id-vereisten](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).

-   Meer informatie over [adreslijstsynchronisatie](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).

-   Meer informatie over [vereisten voor Multi-Factor Authentication](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).

-   Meer informatie over [het plannen van gebruikers- en apparaatgroepen](/intune/users-permissions-add).

-   Informatie over [het maken van gebruikers- en apparaatgroepen](/intune/groups-get-started).

Als uw organisatie al met Office 365 werkt, is het belangrijk dat Intune van dezelfde Azure Active Directory-omgeving gebruikmaakt.

### <a name="pki-optional"></a>PKI (optioneel)

Als u van plan bent om bij Intune verificatie op basis van certificaten te gebruiken voor VPN-, Wi-Fi- of e-mailprofielen, moet u ervoor zorgen dat u over een ondersteunde [PKI-infrastructuur](/intune/certificates-configure) beschikt waarmee certificaatprofielen kunnen worden gemaakt en geïmplementeerd.

Hieronder vindt u meer informatie over het configureren van certificaten in Intune.

-   [De certificaatinfrastructuur voor SCEP configureren](/intune/certificates-scep-configure).

-   [De certificaatinfrastructuur voor PFX configureren](/intune/certficates-pfx-configure).


## <a name="task-list-for-an-intune-setup"></a>Lijst met taken voor een Intune-configuratie

### <a name="task-1-intune-subscription"></a>Taak 1: Intune-abonnement

Voordat u naar Intune kunt migreren, moet u eerst beschikken over een Intune-abonnement.

-   U kunt naar [deze pagina](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) gaan, waar instructies worden gegeven voor het volgende:

    -   Een nieuw Intune-abonnement maken dat is gekoppeld aan een nieuwe AAD-tenant.

    -   Het Intune-abonnement koppelen door aanmelding bij een bestaande AAD-tenant.

### <a name="task-2-assign-intune-user-licenses"></a>Stap 2: Intune-gebruikerslicenties toewijzen

-   Meer informatie over het [toewijzen van Intune-gebruikerslicenties](licenses-assign.md).

-   Als u een nieuwe AAD-tenant hebt gemaakt, lees dan [hoe u nieuwe gebruikers maakt of gebruikers uit uw on-premises Active Directory (AD) synchroniseert.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)

### <a name="task-3-set-your-mdm-authority-to-intune"></a>Taak 3: de MDM-instantie instellen op Intune

Intune kan worden beheerd via Azure Portal of de Configuration Manager Current Branch-console. Tenzij u Intune wilt integreren met een Configuration Manager Current Branch-implementatie, kunt u Intune het beste beheren via [Azure Portal](https://portal.azure.com).

Stel de MDM-instantie in op **Intune** om Intune Azure Portal in te schakelen. Door het gebruik van een andere MDM-instantie kan Intune het MDM-beheer overdragen aan andere Microsoft-beheerconsoles. Deze gevallen zijn niet gebruikelijk.

> [!IMPORTANT]
> Als u het beheer van mobiele apparaten voor het eerst overdraagt aan Intune, moet u de MDM-instantie instellen op Intune.

-   Meer informatie over [het instellen van de instantie voor het beheer van mobiele apparaten](/intune/mdm-authority-set).

## <a name="next-step"></a>Volgende stap

[Beheerbeleid voor apparaten en apps configureren](migration-guide-configure-policies.md)
