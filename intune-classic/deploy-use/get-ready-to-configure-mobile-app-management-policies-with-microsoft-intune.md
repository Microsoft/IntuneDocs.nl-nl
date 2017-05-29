---
title: Vereisten voor MAM-beleid | Microsoft Docs
description: In dit onderwerp worden de vereisten voor het instellen van gebruikers beschreven voordat u MAM-beleid (Mobile App Management) kunt maken.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3c209a350a7de7ba7ddb71468c5cd4230dcf5423
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="get-ready-to-configure-app-protection-policies-in-the-azure-portal"></a>Aan de slag met configureren van beveiligingsbeleid voor apps in Azure-portal

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt uitgelegd aan welke vereisten u moet voldoen en welke stappen u moet voltooien **voordat** u beveiligingsbeleid voor apps in Azure-portal kunt maken.

Zie [Protect apps and data using mobile app management policies](protect-apps-and-data-with-microsoft-intune.md) (Apps en gegevens beschermen met beleid voor het beheer van mobiele apps) voor informatie over hoe het beveiligingsbeleid voor apps in Intune uw bedrijfsgegevens beveiligt.

## <a name="what-is-the-azure-portal"></a>Wat is de Azure-portal?

Azure-portal is de nieuwe beheerconsole voor het maken van beveiligingsbeleid voor apps. De volgende MAM-scenario's worden ondersteund:
- Apparaten die zijn ingeschreven bij Intune
- Apparaten die worden beheerd door een andere MDM-oplossing (Mobile Device Management)
- Apparaten die niet worden beheerd door een MDM-oplossing (BYOD)

Momenteel kunt u in zowel de **Intune-beheerconsole** als **Azure Portal** beveiligingsbeleid voor apps configureren.  Bekijk het volgende:

* Het beleid dat u in **Azure Portal** maakt, wordt ondersteund voor **alle MAM-scenario's** die hiervoor aan de orde zijn gekomen. De **Intune-beheerconsole** ondersteunt alleen het maken van beleid voor **apparaten die zijn geregistreerd bij en worden beheerd in Intune**.

* U ziet mogelijk niet alle beleidsinstellingen voor apps in de Intune-beheerconsole, omdat **nieuwe instellingen** alleen kunnen worden toegevoegd in **Azure Portal**.

* Als u een beveiligingsbeleid voor apps in **zowel** de Intune-beheerconsole als Azure Portal maakt, wordt het beleid in **Azure Portal toegepast op de apps en geïmplementeerd voor gebruikers**.
    * Beveiligingsbeleid voor apps dat is gemaakt in de Intune-beheerconsole kan niet worden geïmporteerd in Azure Portal.  Het beveiligingsbeleid voor apps moet opnieuw worden gemaakt in Azure Portal.


* Andere **functies voor app-beheer**, zoals het implementeren van apps en configuratiebeleid voor apps, zijn alleen beschikbaar in de **Intune-beheerconsole**.


Als u niet bekend bent met Azure Portal, kunt u het onderwerp [Azure Portal voor Microsoft Intune beveiligingsbeleid voor apps](azure-portal-for-microsoft-intune-mam-policies.md) lezen voor een overzicht van het gebruik van Azure Portal.

Zie [Beveiligingsbeleid voor apps configureren en implementeren in de Microsoft Intune-console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) voor instructies over het maken van beveiligingsbeleid voor apps met behulp van de Intune-beheerconsole.


##  <a name="supported-platforms"></a>Ondersteunde platforms
- iOS 8.1 of hoger
- Android 4 of hoger
- Windows 10

>[!NOTE]
>Met ingang van versie 1703 kan beveiligingsbeleid voor apps worden gedefinieerd voor Windows 10-apparaten in de MAM zonder inschrijvingsscenario. Zie [Uw ondernemingsgegevens beveiligen met Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) voor meer informatie.

##  <a name="supported-apps"></a>Ondersteunde apps
* **Microsoft-apps:** bij deze apps is de Intune App SDK al ingebouwd. Deze apps hoeven daarom niet verder te worden verwerkt voordat u het beveiligingsbeleid voor apps toepast.
Ga voor de volledige lijst met ondersteunde Microsoft-apps naar de [galerie met mobiele toepassingen van Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) op de pagina voor Microsoft Intune-toepassingen van partners. Klik op een app om de ondersteunde scenario's en platformen te bekijken en om te controleren of de app meerdere identiteiten ondersteunt.

* **Line-Of-Business-apps van uw organisatie:** voordat u beveiligingsbeleid voor apps kunt toepassen, moet u de app voorbereiden voor de opname van de Intune App SDK.

  * Zie [Bepalen hoe uw apps voorbereidt voor MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) voor apparaten die worden beheerd met Intune.

  * Zie [Line-Of-Business-apps en -gegevens beveiligen op apparaten die niet zijn ingeschreven bij Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) voor apparaten die niet worden beheerd (zoals apparaten in eigendom van werknemers) of voor apparaten die worden beheerd door een andere MDM-oplossing.

## <a name="prerequisites"></a>Vereisten

-   **Een Microsoft Intune-abonnement**. Eindgebruikers hebben Intune-licenties nodig om apps met beveiligingsbeleid voor apps te kunnen downloaden.
U hebt al een Intune-abonnement als u momenteel Intune gebruikt om uw apparaten te beheren. U hebt ook een Intune-abonnement als u een licentie voor Enterprise Mobility Suite (EMS) hebt aangeschaft. Als u Intune uitprobeert om te zien wat de MAM-mogelijkheden zijn, kunt u op de [pagina van Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/) een proefaccount aanvragen.

    Als u wilt controleren of u een Intune-abonnement op de Office-portal hebt, gaat u naar de pagina **Facturering**.  Als u een abonnement hebt, moet Intune in het gedeelte met abonnementen zijn gemarkeerd als **Actief**.

-   **Een abonnement op Office 365**. Dit is vereist voor het volgende:

  - Het toepassen van beveiligingsbeleid voor apps op apps met ondersteuning voor meerdere identiteiten.

  - Het maken van SharePoint Online- en Exchange Online-werkaccounts. Exchange on-premises en SharePoint on-premises worden niet ondersteund.

-   **Skype voor Bedrijven Online instellen voor moderne verificatie**. Zie voor meer informatie [Moderne verificatie inschakelen](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) voor het maken van gebruikers. Azure AD verifieert gebruikers wanneer ze de app openen en hun werkreferenties invoeren.

    > [!NOTE]
    > Gebruikersgroepen moeten worden ingesteld in Azure AD. Intune-gebruikersgroepen kunnen niet worden gebruikt om beveiligingsbeleid voor apps te implementeren in Azure-portal.

### <a name="create-users-and-assign-microsoft-intune-licenses"></a>Gebruikers maken en Microsoft Intune-licenties toewijzen

1.  Meld u met uw beheerdersreferenties aan bij de [Office-portal](https://portal.office.com).

2.  Voeg gebruikers toe zoals wordt beschreven in de sectie **Steps to complete a 30-day evaluation of Intune** (Stappen voor het voltooien van een 30-daagse evaluatie van Intune) in de [Intune-evaluatiehandleiding](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) en wijs vervolgens Intune-licenties toe. Als u een gebruiker toegang wilt geven tot de Office-portal, de Azure AD-portal en de Azure Portal, wijst u aan de gebruiker de **rol van algemeen beheerder** toe.

5.  Beveiligingsbeleid voor apps wordt voor gebruikersgroepen geïmplementeerd in Azure Active Directory. Als u gebruikersgroepen wilt maken voor uw beveiligingsbeleid voor apps, maakt u een gebruikersgroep zoals beschreven in de sectie **Een gebruikersgroep maken** van het artikel [Groepen maken om gebruikers en apparaten voor de evaluatieversie in te delen](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).

### <a name="assign-roles-to-non-global-admin-users"></a>Rollen toewijzen aan gebruikers die geen globale beheerder zijn

Algemene beheerders hebben toegang tot de [Azure Portal](https://portal.azure.com).  Raadpleeg het artikel [Roltoewijzingen gebruiken voor het beheer van de toegang tot de resources van uw Azure-abonnement](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) als u gebruikers die geen algemene beheerders zijn, in staat wilt stellen beleid te configureren en andere taken voor het beheer van mobiele apps uit te voeren.

## <a name="next-steps"></a>Volgende stappen
[Beveiligingsbeleid voor apps maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)

