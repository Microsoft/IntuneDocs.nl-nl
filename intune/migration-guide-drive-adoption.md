---
title: Eindgebruikers accepteren door middel van voorwaardelijke toegang
description: In dit artikel wordt beschreven hoe u gebruik kunt maken van voorwaardelijke toegang ter ondersteuning van de inschrijving bij Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>Eindgebruikers accepteren door middel van voorwaardelijke toegang

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Wanneer u functies voor voorwaardelijke toegang bij Intune inschakelt, zoals het blokkeren van e-mail voor niet-ingeschreven apparaten, kan dat helpen bij de inschrijving en naleving. Functies voor voorwaardelijke toegang zijn echter geen voorwaarde voor een geslaagde migratie. Uw acceptatiedoelstellingen en beveiligingsvereisten voor de migratie moeten bepalend zijn voor het slagen van de migratie.

## <a name="migration-campaign-with-conditional-access"></a>Migratiecampagne met voorwaardelijke toegang

Hier volgt een gebruikelijke benadering voor het uitbreiden van de migratiecampagne met voorwaardelijke toegang:

1.  Stel regels voor voorwaardelijke toegang in die moeten worden doorgevoerd voor alle gebruikers. Sluit echter de gebruikers uit die moeten migreren vanuit een voorgaande MDM-provider. U kunt een Azure AD-gebruikersgroep maken met daarin alle gebruikers die zijn uitgesloten van voorwaardelijke toegang.

2.  Wanneer gebruikers migreren, verwijdert u ze uit de groep van gebruikers die zijn uitgesloten van voorwaardelijke toegang.

3.  Nadat de migratie is voltooid, configureert u alle beleidsregels voor voorwaardelijke toegang om standaard gebruikers te blokkeren, tenzij Intune toegang verleent.

### <a name="advantages"></a>Voordelen

-   Het biedt toegangsbeheer voor nieuwe gebruikersaccounts of gebruikersaccounts die niet werden beheerd door de voorgaande oplossing.

-   Het biedt een respijtperiode voor gebruikers van een voorgaande oplossing tot aan de migratie.

-   Het minimaliseert het verlies aan productiviteit.

### <a name="disadvantages"></a>Nadelen

-   Gebruikers van een voorgaande oplossing hebben mogelijk met niet-beheerde apparaten toegang tot resources totdat voorwaardelijke toegang voor die gebruikers is ingeschakeld.

> [!TIP]
> Dit is een van de vele benaderingen. U kunt een eenvoudigere procedure hanteren waarbij alle beleidsregels voor voorwaardelijke toegang worden uitgesteld totdat elke fase de instructie heeft gekregen om de apparaten in te schrijven. U kunt ook een striktere procedure hanteren waarbij vanaf het begin voorwaardelijke toegang wordt toegepast en volledige naleving voor alle toegang is vereist.

-   Meer informatie over [voorwaardelijke toegang](/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Lijst met taken voor voorwaardelijke toegang

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Taak 1: beslis hoe u voorwaardelijke toegang wilt implementeren

[Gebruikelijke manieren om voorwaardelijke toegang te gebruiken](/intune/conditional-access-intune-common-ways-use).

### <a name="task-2-set-up-intune-conditional-access"></a>Taak 2: voorwaardelijke toegang van Intune instellen

Kies een van de volgende opties:

-   [Voorwaardelijke toegang in Azure Active Directory configureren](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [De on-premises Exchange-connector installeren met Intune](/intune/exchange-connector-install)

-   [Beleid voor voorwaardelijke toegang op basis van apps instellen voor Exchange Online](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [Beleid voor voorwaardelijke toegang op basis van apps instellen voor SharePoint Online](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Apps die geen gebruik maken van moderne verificatie (ADAL) blokkeren](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>Volgende stappen

[Normale migratiecyclus](migration-guide-cycle.md)
