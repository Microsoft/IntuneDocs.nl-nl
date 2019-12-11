---
title: De Pradeo-integratie instellen met Intune
titleSuffix: Intune on Azure
description: Integratie van de Pradeo-connector met Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 82872ba6-80f8-4cc9-adf4-0ccd8ff26dd2
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 32e67ac961f2831a881bc160e19cefdb75723ff0
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72681256"
---
# <a name="integrate-pradeo-mobile-threat-defense-with-intune"></a>Pradeo Mobile Threat Defense integreren met Intune

Voer de volgende stappen uit om de Pradeo Mobile Threat Defense-oplossing te integreren met Intune.

> [!NOTE]  
> Deze Mobile Threat Defense-leverancier wordt niet ondersteund voor niet-ingeschreven apparaten.

## <a name="before-you-begin"></a>Voordat u begint

> [!NOTE]
> De volgende stappen moeten worden uitgevoerd in de [Pradeo Security-console](https://www.apps-security.com).

Zorg ervoor dat u over het volgende beschikt voordat u begint met de integratie van Pradeo met Intune:

- Microsoft Intune-abonnement

- Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:

  - Aanmelden en gebruikersprofiel lezen

  - Toegang tot de map als de aangemelde gebruiker

  - Mapgegevens lezen

  - Gegevens van een apparaat verzenden naar Intune

- Beheerdersreferenties voor toegang tot de Pradeo Security-console.

### <a name="pradeo-app-authorization"></a>Pradeo-app-autorisatie

Het autorisatieproces van de Pradeo-app is als volgt:

- Sta de Pradeo-service toe informatie met betrekking tot de status van apparaten naar Intune te communiceren.

- Pradeo wordt gesynchroniseerd met het Azure AD Enrollment-groepslidmaatschap om de database van het apparaat te vullen.

- Sta toe dat de Pradeo-beheerconsole eenmalige aanmelding (SSO) van Azure AD gebruikt.

- Sta toe dat de Pradeo-app eenmalige aanmelding van Azure AD gebruikt om aan te melden.

## <a name="to-set-up-pradeo-integration"></a>Pradeo-integratie instellen

1. Ga naar [Pradeo Security Console](https://www.apps-security.com) en meld u aan met uw referenties.

2. Kies **Administration - Enterprise Mobility Management** (Beheer - Enterprise Mobility Management) in het menu.

3. Kies het **Intune-logo**.

4. Kies in het venster **EMM (Enterprise mobility management) - Intune** onder **Stap 1** de knop **Pradeo Connector**. 

    ![Schermopname van het Pradeo EMM Intune-venster](./media/pradeo-mtd-connector-integration/pradeo_setup.png)

5. Voer uw Intune-referenties in het venster Microsoft Intune connection (Microsoft Intune-verbinding) in.

5. De webpagina van Pradeo wordt opnieuw geopend. Kies onder **Stap 2** de knop **Pradeo Device Health** (Apparaatstatus Pradeo).

7. Selecteer **Accept** (Accepteren) in het venster Pradeo-Intune Connector. 

8. Selecteer **Accept** (Accepteren) in het venster Pradeo device API connector (API-connector Pradeo-apparaat).

9. De webpagina van Pradeo wordt opnieuw geopend. Kies onder **Stap 3** de knop **Connect to Microsoft** (Verbinding maken met Microsoft). 

10. Voer uw Intune-referenties in het venster Microsoft Intune authentication (Microsoft Intune-verificatie) in.

11. Wanneer het bericht **Successful Integration** (Integratie geslaagd) wordt weergegeven, is de integratie voltooid.

## <a name="next-steps"></a>Volgende stappen

- [Pradeo-apps instellen voor ingeschreven apparaten](mtd-apps-ios-app-configuration-policy-add-assign.md)
