---
title: Sophos Mobile-integratie met Intune instellen
titleSuffix: Intune on Azure
description: Meer informatie over hoe u de Sophos Mobile-oplossing met Microsoft Intune instelt om de toegang van mobiele apparaten tot uw bedrijfsresources te beheren.
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
ms.assetid: ''
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: aad6268606dfcf69c304bb5c5b270c8c4795e4b2
ms.sourcegitcommit: 1a5b185acd27954b10b6d59409d82eb80fd71284
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2019
ms.locfileid: "72681287"
---
# <a name="integrate-sophos-mobile-with-intune"></a>Sophos Mobile integreren met Intune  

Voer de volgende stappen uit om de Sophos Mobile Threat Defense-oplossing te integreren met Intune.  

> [!NOTE]
> Deze Mobile Threat Defense-leverancier wordt niet ondersteund voor niet-ingeschreven apparaten.

## <a name="before-you-begin"></a>Voordat u begint  

Zorg ervoor dat u over het volgende beschikt voordat u begint met de integratie van Sophos Mobile met Intune:  
- Microsoft Intune-abonnement  
- Azure Active Directory-beheerdersreferenties om de volgende machtigingen te verlenen:  
  - Aanmelden en gebruikersprofiel lezen  
  - Toegang tot de map als de aangemelde gebruiker  
  - Mapgegevens lezen  
  - Gegevens van een apparaat verzenden naar Intune  
- Beheerdersreferenties voor toegang tot de beheerconsole van Sophos Mobile.  


### <a name="sophos-mobile-app-authorization"></a>Autorisatie voor Sophos Mobile-apps  
  
Het autorisatieproces van de Sophos Mobile-app is als volgt:  
- De Sophos Mobile-service toestaan informatie met betrekking tot de status van apparaten naar Intune te communiceren.  
- Sophos Mobile wordt gesynchroniseerd met het Azure AD Enrollment-groepslidmaatschap om de database van het apparaat te vullen.  
- Toestaan dat Sophos Mobile-beheerconsole Azure AD-enkelvoudige aanmelding (SSO) gebruikt.  
- De Sophos Mobile-app toestaan zich aan te melden met Azure AD SSO.  


## <a name="to-set-up-sophos-mobile-integration"></a>Sophos Mobile-integratie instellen  

1. Meld u aan bij [Azure Portal]( https://portal.azure.com/), ga naar **Intune** > **Apparaatcompliantie** > **Mobile Threat Defense** en selecteer **Toevoegen**.  
2. Ga naar de pagina **Connector toevoegen** en gebruik de vervolgkeuzelijst om **Sophos** te selecteren. En selecteer vervolgens **Maken**.  
3. Selecteer de koppeling *De Sophos-beheerconsole openen*.  
4. Meld u aan bij de [Sophos-beheerconsole](https://central.sophos.com/) met uw Sophos-referenties.  
5. Ga naar **Mobile** > **Instellingen** > **Installatie** > **Sophos-installatie**.  
6. Selecteer het tabblad **Intune MTD** op de pagina **Sophos-installatie**.  
   ![Sophos-installatie](./media/sophos-mtd-connector-integration/sophos-setup.png) 
 
7. Selecteer **Binding** en selecteer vervolgens **Ja**. Sophos maakt verbinding met Intune; u moet zich aanmelden bij uw Intune-abonnement. 
8. Voer in het verificatievenster van Microsoft Intune uw Intune-referenties in en **accepteer** de aanvraag voor machtigingen voor *Sophos Mobile Thread Defense*.  
   ![Intune-verificatie](./media/sophos-mtd-connector-integration/intune-authentication.png)

9. Selecteer **Opslaan** op de pagina **Sophos-installatie** om de configuratie voor Intune te voltooien:  
   ![Sophos-installatie opslaan](./media/sophos-mtd-connector-integration/save-sophos-configuration.png)  

1. Wanneer het bericht **Successful Integration** (Integratie geslaagd) wordt weergegeven, is de integratie voltooid.  
1. Op de Intune-console is nu Sophos beschikbaar.  


## <a name="next-steps"></a>Volgende stappen  
[Sophos-clientapps configureren](mtd-apps-ios-app-configuration-policy-add-assign.md)
