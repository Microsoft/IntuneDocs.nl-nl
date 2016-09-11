---
title: Voorbereidingen voor de configuratie van MAM-beleid | Microsoft Intune
description: In dit onderwerp worden de vereisten en het instellen van gebruikers beschreven voordat u Mobile App Management (MAM)-beleid kunt maken.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bebf57269ae41f04a47240063cde4a4dd0bf334f
ms.openlocfilehash: aeaa64124384a71126eeca7339416b80d395d07d


---

# Voorbereidingen voor het configureren van beleid voor het beheer van mobiele apps (Mobile App Management) met Microsoft Intune
In dit onderwerp wordt uitgelegd wat u moet doen voordat u beleid voor het beheer van mobiele apps (Mobile App Management, MAM) in de Azure Portal kunt maken.

De Azure-portal is de nieuwe beheerconsole voor het maken van MAM-beleid. Wij raden u aan deze portal te gebruiken voor het maken van MAM-beleid. De Azure Portal ondersteunt de volgende MAM-scenario's:
- Apparaten die zijn ingeschreven bij Intune
- Apparaten die worden beheerd door een externe MDM-oplossing
- Apparaten die niet worden beheerd door een MDM-oplossing (BYOD)

Als u niet bekend bent met Azure Portal, kunt u het onderwerp [Azure Portal voor Microsoft Intune MAM-beleid](azure-portal-for-microsoft-intune-mam-policies.md) lezen voor een overzicht.

>[!IMPORTANT]

> Als u momenteel de Intune-beheerconsole gebruikt om uw apparaten te beheren, kunt u met de Intune-beheerconsole MAM-beleid maken dat apps ondersteunt voor apparaten die zijn ingeschreven bij Intune. Wij adviseren u echter de Azure Portal te gebruiken, zelfs voor apparaten die zijn ingeschreven bij Intune. Zie voor instructies over het maken van een MAM-beleid met behulp van de Intune-beheerconsole [Mobile Application Management-beleid configureren en implementeren in de Microsoft Intune-console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).

> Mogelijk ziet u in de Intune-beheerconsole niet alle MAM-beleidsinstellingen. Als u een MAM-beleid in zowel de Intune-beheerconsole als de Azure Portal maakt, wordt het beleid in de Azure Portal toegepast op de apps en geïmplementeerd op gebruikers.
> Een MAM-beleid dat is gemaakt in de Intune-beheerconsole kan niet worden geïmporteerd in de Azure Portal.  Het MAM-beleid moet opnieuw worden gemaakt in de Azure Portal.


##  Ondersteunde platforms
- iOS 8.1 of hoger

- Android 4 of hoger

Windows-apparaten worden momenteel niet ondersteund.
##  Ondersteunde apps
* **Microsoft-apps:** bij deze apps is de Intune App SDK al ingebouwd. Deze apps hoeven daarom niet verder te worden verwerkt voordat u het MAM-beleid toepast.
Ga voor de volledige lijst met ondersteunde Microsoft-apps naar de [galerie met mobiele toepassingen van Microsoft Intune](https://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/partners.aspx) op de pagina voor Microsoft Intune-toepassingen van partners. Klik op een app om de ondersteunde scenario's en platformen te bekijken en om te controleren of de app meerdere identiteiten ondersteunt.
* **Line-Of-Business-apps van uw organisatie:** voordat u MAM-beleid kunt toepassen, moet de app worden voorbereid voor de opname van de Intune App SDK.

  * Zie [Bepalen hoe uw apps voorbereidt voor MAM](decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md) voor apparaten die worden beheerd met Intune.
  * Zie [Line-Of-Business-apps en -gegevens beveiligen op apparaten die niet zijn ingeschreven bij Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md) voor apparaten die niet worden beheerd als apparaten in eigendom van werknemers of voor apparaten die worden beheerd door een MDM-oplossing van derden.

*Voordat* u MAM-beleid kunt configureren, hebt u het volgende nodig:

-   Een abonnement op Microsoft Intune.    Eindgebruikers hebben [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-licenties nodig om apps met MAM-beleid te kunnen downloaden.

-   Een abonnement op Office 365. Dit is vereist voor het volgende:
  - Het toepassen van MAM-beleid op apps met ondersteuning voor meerdere identiteiten.
  - Het maken van SharePoint Online- en Exchange Online-werkaccounts. Exchange on-premises en SharePoint on-premises worden niet ondersteund.
-   Skype voor Bedrijven Online instellen voor moderne authenticatie. Zie voor meer informatie [Moderne authenticatie inschakelen](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).


- Azure Active Directory (Azure AD) voor het maken van gebruikers. Azure AD verifieert gebruikers wanneer ze de app openen en hun werkreferenties invoeren.

    > [!NOTE]
    > Als u gebruikers instelt met behulp van de [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-console, houd er dan rekening mee dat de configuratie van het MAM-beleid in de toekomst wordt verplaatst naar de Azure Portal. Om deze portal te gebruiken, moet u Azure AD-gebruikersgroepen instellen met behulp van de Office 365-portal.


## Gebruikers maken en Microsoft Intune-licenties toewijzen

1. Zorg ervoor dat u een Intune-abonnement hebt. U hebt al een [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-abonnement als u momenteel [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] gebruikt om uw apparaten te beheren.  U hebt ook een [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-abonnement als u een Enterprise Mobility Suite (EMS)-licentie hebt aangeschaft. Als u [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] uitprobeert om te zien wat de MAM-mogelijkheden zijn, kunt u op de [webpagina van Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/) een proefaccount aanvragen.

    Als u wilt controleren of u een [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-abonnement op de Office-portal hebt, gaat u naar de pagina **Facturering**.  [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] zou in het gedeelte met abonnementen als **Actief** moeten zijn aangemerkt.

2.  Meld u met uw beheerdersreferenties aan bij de [Office-portal](http://portal.office.com).

3.  Ga naar de pagina **Actieve gebruikers** om gebruikers toe te voegen en [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-licenties toe te wijzen.

    ![Pagina Actieve gebruikers in de Office-portal](../media/AppManagement/OfficePortal_AddUsers.png)

    ![Gebruikerspagina in de Office-portal bewerken](../media/AppManagement/OfficePortal_AssignLicenses.png)

4.  Als u een gebruiker toegang wilt geven tot de Office-portal, de Azure AD-portal en de Azure Portal, wijst u aan de gebruiker de **rol van algemeen beheerder** toe.

    ![Pagina voor het bewerken van gebruikersrollen in de Office-portal](../media/AppManagement/OfficePortal_AddRoletoUser.png)

5.  MAM-beleid wordt voor gebruikersgroepen geïmplementeerd in Azure Active Directory. Als u gebruikersgroepen wilt maken voor uw MAM-beleid, gaat u naar de pagina **Groepen** in de Office-portal en kiest u de optie **Een groep toevoegen** om een nieuwe beveiligingsgroep te maken.  Voer een naam en beschrijving in en klik op **Maken**. Nadat de groep is gemaakt, kunt u gebruikers aan de groep toevoegen door te klikken op **Leden bewerken**. De beveiligingsgroep wordt gemaakt in Azure Active Directory.

    ![Pagina voor beveiligingsgroepen in de Office-portal](../media/AppManagement/OfficePortal_CreateGroups.png)

De volgende tabel bevat de rollen en machtigingen die u aan gebruikers met beheerdersrechten kunt toewijzen.

|||
|--|----|
|**Rol**|**Machtigingen**|
|Algemeen beheerder (Office 365-portal)|Toegang tot de Office 365-portal en de Azure AD-portal.<br /><br />Toegang tot de Azure Portal (kan zowel rollen beheren als taken voor het beheer van mobiele apps uitvoeren).|
|Eigenaar (Azure Portal)|Toegang tot de Azure Portal (kan zowel rollen beheren als taken voor het beheer van mobiele apps uitvoeren).|
|Inzender (Azure Portal)|Toegang tot de Azure Portal (kan alleen taken voor het beheer van mobiele apps uitvoeren).|

## De rol van Inzender toewijzen aan een gebruiker

Algemene beheerders hebben toegang tot de [Azure Portal](https://portal.azure.com).  Als u andere gebruikers met beheerdersrechten in staat wilt stellen om beleid te configureren en andere taken voor het beheer van mobiele apps uit te voeren, wijst u de rol van Inzender toe aan de gebruiker:


1.  Klik op de blade **Instellingen** in het gedeelte **Resourcebeheer** op de optie **Gebruikers**.

    ![Blade Gebruikers in de Azure Portal](../media/AppManagement/AzurePortal_MAM_AddUsers.png)

2.  Klik op **Toevoegen** om de blade **Toegang toevoegen** te openen.

3.  Klik op **Selecteer een rol** en klik vervolgens op **Inzender**.

    ![Een rolblade selecteren in de Azure Portal](../media/AppManagement/AzurePortal_MAM_AddRole.png)

4.  Klik op **Gebruiker toevoegen** en zoek naar de gebruiker op naam of e-mailadres. De gebruikers die u in deze lijst ziet, zijn de eerste 1.000 gebruikers die u eerder in Azure AD hebt gemaakt met behulp van de Office-portal. Klik op **OK** op de blade **Toegang toevoegen** om de gebruiker op te slaan en de rol aan de gebruiker toe te wijzen.

    ![Blade Gebruikers toevoegen in de Azure Portal](../media/AppManagement/AzurePortal_MAM_AddusertoRole.png)

    > [!IMPORTANT]
    > Als u een gebruiker selecteert aan wie geen [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]-licentie is toegewezen, heeft deze geen toegang tot de portal.

## Volgende stappen
[Beleid voor Mobile App Management maken en implementeren met Microsoft Intune](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


