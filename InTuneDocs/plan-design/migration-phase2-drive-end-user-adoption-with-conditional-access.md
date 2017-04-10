---
title: Eindgebruikers accepteren door middel van voorwaardelijke toegang | Microsoft Docs
description: In dit artikel wordt beschreven hoe u gebruik kunt maken van voorwaardelijke toegang ter ondersteuning van de inschrijving bij Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 26d11bc64802005bcce8cc1962d531af6ffe5cd5
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>Fase 2: eindgebruikers accepteren door middel van voorwaardelijke toegang

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

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

-   Meer informatie over [voorwaardelijke toegang](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access).

## <a name="task-list-for-conditional-access"></a>Lijst met taken voor voorwaardelijke toegang

### <a name="task-1-get-ready-for-intune-conditional-access"></a>Taak 1: bereid u voor op voorwaardelijke toegang van Intune

-   Meer informatie over [het configureren van voorwaardelijke toegang](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-setup-intune-conditional-access"></a>Taak 2: voorwaardelijke toegang van Intune instellen

Kies een van de volgende soorten beleid van voorwaardelijke toegang voor meer informatie:

-   [Exchange Online en het nieuwe Exchange Online Dedicated](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Exchange On-Premises en het verouderde Exchange Online Dedicated](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype voor Bedrijven Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](https://docs.microsoft.com/intune/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Voorbeeldscenario's voor e-mailtoegang](https://docs.microsoft.com/intune/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Volgende stappen

[Fase 2: normale migratiecyclus](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)

