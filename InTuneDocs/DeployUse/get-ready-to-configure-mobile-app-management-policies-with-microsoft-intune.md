---
title: Vereisten voor MAM-beleid | Microsoft Intune
description: In dit onderwerp worden de vereisten en het instellen van gebruikers beschreven voordat u Mobile App Management (MAM)-beleid kunt maken.
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 5778ccc632b72b3cca2593febeccbf7149591275
ms.openlocfilehash: 6d7843286369e2371ea204ac70d2e85e4c086d76


---

# Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps in de Azure-portal
In dit onderwerp wordt uitgelegd aan welke vereisten u moet voldoen en welke stappen u moet voltooien **voordat** u beleid voor het beheer van mobiele apps (MAM) in de Azure Portal kunt maken.

Zie [Protect apps and data using mobile app management policies](protect-apps-and-data-with-microsoft-intune.md) (Apps en gegevens beschermen met beleid voor het beheer van mobiele apps) voor informatie over hoe MAM-beleid in Intune uw bedrijfsgegevens beveiligt.

## Wat is de Azure-portal?
De Azure-portal is de nieuwe beheerconsole voor het maken van MAM-beleid en ondersteunt de volgende MAM-scenario’s:
- **Apparaten die zijn ingeschreven bij Intune**
- **Apparaten die worden beheerd door een andere MDM-oplossing**
- **Apparaten die niet worden beheerd door een MDM-oplossing (BYOD)**


Momenteel kunt u in zowel de **Intune-beheerconsole** als de **Azure-portal** MAM-beleid configureren.  Neem het volgende in overweging:

* Het beleid dat u in de **Azure-portal** maakt, wordt ondersteund voor **alle MAM-scenario's** in de bovenstaande lijst. De **Intune-beheerconsole** ondersteunt alleen het maken van beleid voor **apparaten die zijn geregistreerd bij en worden beheerd in Intune**.
* U ziet mogelijk niet alle MAM-beleidsinstellingen in de Intune-beheerconsole, omdat **nieuwe instellingen** alleen kunnen worden toegevoegd in de **Azure-portal**.
* Als u een MAM-beleid in **zowel** de Intune-beheerconsole als de Azure Portal maakt, wordt het beleid in de **Azure Portal toegepast op de apps en geïmplementeerd voor gebruikers**.
    * Een MAM-beleid dat is gemaakt in de Intune-beheerconsole kan niet worden geïmporteerd in de Azure Portal.  Het MAM-beleid moet opnieuw worden gemaakt in de Azure Portal.
* Andere **functies voor app-beheer**, zoals het implementeren van apps en maken van configuratiebeleid voor apps, zijn alleen beschikbaar in de **Intune-beheerconsole**.


Als u niet bekend bent met Azure Portal, kunt u het onderwerp [Azure Portal voor Microsoft Intune MAM-beleid](azure-portal-for-microsoft-intune-mam-policies.md) lezen voor een overzicht van het gebruik van Azure-portal.

Zie voor instructies over het maken van een MAM-beleid met behulp van de Intune-beheerconsole [Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).


##  Ondersteunde platforms
- iOS 8.1 of hoger

- Android 4 of hoger

>[!NOTE]
>Windows-apparaten ondersteunen dit beleid voor het beheer van mobiele apparaten niet. Wanneer u Windows 10-apparaten registreert bij Intune, kunt u Windows Information Protection gebruiken, dat vergelijkbare functionaliteit biedt. Zie [Uw ondernemingsgegevens beveiligen met Windows Information Protection (WIP)](https://technet.microsoft.com/en-us/itpro/windows/keep-secure/protect-enterprise-data-using-wip) voor meer informatie.

##  Ondersteunde apps
* **Microsoft-apps:** bij deze apps is de Intune App SDK al ingebouwd. Deze apps hoeven daarom niet verder te worden verwerkt voordat u het MAM-beleid toepast.
Ga voor de volledige lijst met ondersteunde Microsoft-apps naar de [galerie met mobiele toepassingen van Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps) op de pagina voor Microsoft Intune-toepassingen van partners. Klik op een app om de ondersteunde scenario's en platformen te bekijken en om te controleren of de app meerdere identiteiten ondersteunt.
* **Line-Of-Business-apps van uw organisatie:** voordat u MAM-beleid kunt toepassen, moet de app worden voorbereid voor de opname van de Intune App SDK.

  * Zie [Bepalen hoe uw apps voorbereidt voor MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) voor apparaten die worden beheerd met Intune.
  * Zie [Line-Of-Business-apps en -gegevens beveiligen op apparaten die niet zijn ingeschreven bij Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) voor apparaten die niet worden beheerd als apparaten in eigendom van werknemers of voor apparaten die worden beheerd door een andere MDM-oplossing.

## Vereisten

-   Een abonnement op Microsoft Intune.    Eindgebruikers hebben [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-licenties nodig om apps met MAM-beleid te kunnen downloaden.
U hebt al een [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-abonnement als u momenteel [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] gebruikt om uw apparaten te beheren.  U hebt ook een [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-abonnement als u een Enterprise Mobility Suite (EMS)-licentie hebt aangeschaft. Als u [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] uitprobeert om te zien wat de MAM-mogelijkheden zijn, kunt u op de [webpagina van Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) een proefaccount aanvragen.

    Als u wilt controleren of u een [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-abonnement op de Office-portal hebt, gaat u naar de pagina **Facturering**.  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zou in het gedeelte met abonnementen als **Actief** moeten zijn aangemerkt.

-   Een abonnement op Office 365. Dit is vereist voor het volgende:
  - Het toepassen van MAM-beleid op apps met ondersteuning voor meerdere identiteiten.
  - Het maken van SharePoint Online- en Exchange Online-werkaccounts. Exchange on-premises en SharePoint on-premises worden niet ondersteund.
-   Skype voor Bedrijven Online instellen voor moderne authenticatie. Zie voor meer informatie [Moderne authenticatie inschakelen](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) voor het maken van gebruikers. Azure AD verifieert gebruikers wanneer ze de app openen en hun werkreferenties invoeren.

    > [!NOTE]
    > Gebruikersgroepen moeten worden ingesteld in Azure AD. Intune-gebruikersgroepen kunnen niet worden gebruikt om MAM-beleid te implementeren in de Azure-portal.

### Gebruikers maken en Microsoft Intune-licenties toewijzen

1.  Meld u met uw beheerdersreferenties aan bij de [Office-portal](http://portal.office.com).

2.  Voeg gebruikers toe zoals beschreven onder **Gebruikers toevoegen** in [dit](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-2) onderwerp, en wijs Intune-licenties toe. Als u een gebruiker toegang wilt geven tot de Office-portal, de Azure AD-portal en de Azure Portal, wijst u aan de gebruiker de **rol van algemeen beheerder** toe.

5.  MAM-beleid wordt voor gebruikersgroepen geïmplementeerd in Azure Active Directory. Als u gebruikersgroepen wilt maken voor uw MAM-beleid, maakt u een gebruikersgroep zoals beschreven onder **Een gebruikersgroep maken** in [dit](https://docs.microsoft.com/en-us/intune/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3) onderwerp.

### Niet-algemene beheerders

Algemene beheerders hebben toegang tot de [Azure Portal](https://portal.azure.com).  Als u gebruikers die geen algemene beheerders zijn, in staat wilt stellen beleid te configureren en andere taken voor het beheer van mobiele apps uit te voeren, wijst u de rol van Inzender toe aan de gebruikers. Zie [Use role assignments to manage access to your Azure subscription resources](https://azure.microsoft.com/en-us/documentation/articles/role-based-access-control-configure/) (Roltoewijzingen gebruiken voor het beheer van toegang tot uw Azure-abonnementresources).

---------------------------------

De volgende tabel bevat de rollen en machtigingen die u aan gebruikers met beheerdersrechten kunt toewijzen.

|||
|--|----|
|**Rol**|**Machtigingen**|
|Algemeen beheerder (Office 365-portal)|Toegang tot de Office 365-portal en de Azure AD-portal.<br /><br />Toegang tot de Azure Portal (kan zowel rollen beheren als taken voor het beheer van mobiele apps uitvoeren).|
|Eigenaar (Azure Portal)|Toegang tot de Azure Portal (kan zowel rollen beheren als taken voor het beheer van mobiele apps uitvoeren).|
|Inzender (Azure Portal)|Toegang tot de Azure Portal (kan alleen taken voor het beheer van mobiele apps uitvoeren).|




## Volgende stappen
[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Oct16_HO3-->


