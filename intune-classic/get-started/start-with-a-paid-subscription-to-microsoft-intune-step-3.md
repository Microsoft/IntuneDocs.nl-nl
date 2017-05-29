---
title: Gebruikers toevoegen en machtigingen verlenen | Microsoft Docs
description: On-premises gebruikers met Azure AD synchroniseren en beheerdersmachtigingen voor uw Intune-abonnement verlenen
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4a90d0bdebafeb8a9e5c73892b6f1f11b76eb9f6
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="add-users-and-give-administrative-permission-to-intune"></a>Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt aan beheerders uitgelegd hoe ze gebruikers kunnen toevoegen aan Intune en welke machtigingen beschikbaar zijn in de Intune-service.

Als beheerder kunt u gebruikers rechtstreeks toevoegen of gebruikers synchroniseren via uw on-premises Active Directory. Zodra gebruikers zijn toegevoegd, kunnen ze apparaten registreren en hebben ze toegang tot bedrijfsresources. U kunt gebruikers ook aanvullende machtigingen geven, zoals *Tenantbeheerder*, *Servicebeheerder* en *Apparaatinschrijvingsbeheerder*.

In dit onderwerp wordt uitgelegd hoe u het volgende kunt doen:

- [Gebruikers toevoegen aan Intune](#add-users-to-intune)
- [Aanvullende Intune-machtigingen verlenen](#grant-intune-permissions) met inbegrip van:
  - [Tenantbeheerder](#tenant-administrator)
  - [Servicebeheerder](#service-administrator)
  - [Apparaatinschrijvingsbeheerder](#device-enrollment-managers)

## <a name="add-users-to-intune"></a>Gebruikers toevoegen aan Intune
U kunt handmatig gebruikers aan uw Intune-abonnement toevoegen via de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854). Ze krijgen niet automatisch een Intune-licentie toegewezen. Een Intune-tenantbeheerder moet echter op een later tijdstip het gebruikersaccount bewerken om in de Office 365-portal een licentie aan de gebruiker toe te wijzen. Zie [Gebruikers afzonderlijk of bulksgewijs toevoegen aan de Office 365-portal](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) voor instructies.

### <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory synchroniseren en gebruikers toevoegen aan Intune
U kunt adreslijstsynchronisatie configureren voor het importeren van gebruikersaccounts uit de on-premises Active Directory in Microsoft Azure Active Directory (Azure AD) die Intune-gebruikers bevat. Het koppelen van uw on-premises Active Directory-service aan alle Azure Active Directory-services zorgt ervoor dat het beheer van gebruikersidentiteiten veel eenvoudiger wordt. U kunt ook eenmalige aanmelding configureren om de verificatie vertrouwd en eenvoudig te maken voor uw gebruikers. Door dezelfde [Azure AD-tenant](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) te koppelen met meerdere services, zijn de gebruikersaccounts die u eerder hebt gesynchroniseerd, beschikbaar voor alle cloudservices.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>On-premises gebruikers synchroniseren met Azure AD
Het enige hulpprogramma dat u nodig hebt om uw gebruikersaccounts te synchroniseren met Azure AD, is de [Azure AD Connect-wizard](https://www.microsoft.com/download/details.aspx?id=47594). De Azure AD Connect-wizard biedt een vereenvoudigde begeleiding voor het verbinden van de on-premises infrastructuur voor identiteiten aan de cloud.  Kies uw topologie en behoeften (een of meer mappen, wachtwoordsynchronisatie of federatie) om alle onderdelen door de wizard te laten implementeren en configureren die nodig zijn om de verbinding te laten werken. Inclusief: synchronisatieservices, Active Directory Federation Services (AD FS) en de Azure AD PowerShell-module.

> [!TIP]
> Azure AD Connect bevat functionaliteit die eerder is uitgebracht als Dirsync en Azure AD Sync. Lees meer over [adreslijstintegratie](http://technet.microsoft.com/library/jj573653.aspx). Zie [Overeenkomsten tussen Active Directory en Azure AD](http://technet.microsoft.com/library/dn518177.aspx) voor meer informatie over de voordelen van het synchroniseren van gebruikersaccounts vanuit de lokale directory naar Azure AD.

## <a name="grant-intune-permissions"></a>Intune-machtigingen verlenen

Nadat u gebruikers aan uw Intune-abonnement hebt toegevoegd, kunt u het beste beheermachtigingen aan een paar gebruikersaccounts verlenen. U kunt gebruikers drie typen Intune-machtigingen geven om Intune te beheren
-   **Tenantbeheerder**: gebruik de Office 365-portal om dit type beheerder toe te wijzen voor het beheren van uw abonnement, met inbegrip van facturering, cloudopslag en het beheren van de gebruikers die Intune kunnen gebruiken.
-   **Servicebeheerder**: gebruik de Microsoft Intune-beheerconsole om dit type beheerder toe te wijzen voor dagelijkse taken, waaronder het beheer van apparaten en computers, het implementeren van beleid en apps en het uitvoeren van rapporten.
-   **Apparaatinschrijvingsbeheerder**: gebruik de Microsoft Intune-beheerconsole om dit type beheerder toe te wijzen voor dagelijkse taken, waaronder het beheer van apparaten en computers, het implementeren van beleid en apps en het uitvoeren van rapporten.


### <a name="tenant-administrator"></a>Tenantbeheerder


Aan tenantbeheerders is één beheerdersrol toegewezen waarmee het beheerbereik voor die gebruiker en de te beheren taken zijn gedefinieerd. De beheerdersrollen voor de verschillende Microsoft-cloudservices komen overeen, hoewel bepaalde rollen door sommige services mogelijk niet worden ondersteund. Intune gebruikt de volgende rollen:
- **Globale beheerder**: heeft toegang tot alle beheerfuncties in Intune. De persoon die zich voor Intune aanmeldt, wordt standaard een globale beheerder. Globale beheerders zijn de enige beheerders die andere beheerdersrollen kunnen toewijzen. U kunt meer dan één globale beheerder hebben in uw organisatie. Als best practice is het raadzaam dat slechts een paar mensen in uw bedrijf deze rol vervullen om het risico voor uw bedrijf te reduceren.
- **Billing administrator**: doet aankopen, beheert abonnementen, beheert ondersteuningstickets en bewaakt de servicestatus.
- **Wachtwoordbeheerder**: stelt wachtwoorden opnieuw in, beheert serviceaanvragen en bewaakt de servicestatus. Wachtwoordbeheerders zijn beperkt tot het opnieuw instellen van wachtwoorden voor gebruikers.
- **Beheerder serviceondersteuning**: opent ondersteuningsaanvragen voor Microsoft en bekijkt het servicedashboard en berichtencentrum. Ze beschikken alleen over weergavemachtigingen, met uitzondering voor het openen en lezen van ondersteuningstickets.
- **Beheerder gebruikerstoegang**: wachtwoorden opnieuw instellen, de servicestatus bewaken, toevoegen en verwijderen van gebruikersaccounts en beheren van serviceaanvragen. De beheerder van de gebruikerstoegang kan geen globale beheerder verwijderen of wachtwoorden opnieuw instellen voor globale, facturerings- en servicebeheerders.

Het account dat u gebruikt om uw Microsoft Intune-abonnement te maken, is standaard een tenantbeheerder met de rol Algemeen beheerder. Als tenantbeheerder gebruikt u de Intune-beheerconsole om uw abonnement voor Intune te beheren en om tenantbeheerders toe te wijzen vanuit de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854). Gebruik een tenantbeheerder met de rol van globaal beheerder voor toegang tot de portal om uw eerste servicebeheerder toe te wijzen. Gebruik een tenantbeheerder bij voorkeur niet voor dagelijkse beheertaken. Een tenantbeheerder heeft geen licentie voor Intune nodig voor toegang tot de Intune-beheerconsole. De tenantbeheerder is een algemeen concept in Microsoft-cloudservices. Wanneer u zich abonneert op Intune, is uw service een tenant van Azure AD. Zie de sectie over de Azure AD-tenant in [Wat is een Azure AD-adreslijst?](http://technet.microsoft.com/library/jj573650.aspx).

Als tenantbeheerder gebruikt u deze [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) om uw abonnement te beheren, met inbegrip van de volgende taken wanneer dit wordt toegestaan door uw beheerdersrol:

- Gebruikersaccounts beheren en adreslijstsynchronisatie configureren vanuit uw on-premises Active Directory
- Groepen gebruikers, genaamd beveiligingsgroepen, beheren
- Gebruikers licenties toewijzen voor Intune
- De domeinnaam configureren voor uw abonnement dat u gebruikt wanneer gebruikers zich aanmelden (dat wil zeggen contoso.com)
- Facturering en aankopen beheren, inclusief licenties en cloudopslag
- Koppelingen zoeken om de status van de Intune-service weer te bekijken

Voor toegang tot de Office 365-portal moet uw account de aanmeldingsstatus **Toegestaan** hebben. Deze status is niet hetzelfde als wanneer u een licentie voor het abonnement hebt. Standaard hebben alle gebruikersaccounts de status **Toegestaan**. Gebruikers zonder beheerdersmachtigingen kunnen de Office 365-portal gebruiken om het Intune wachtwoorden opnieuw instellen.

### <a name="service-administrator"></a>Servicebeheerder

Met Intune wordt standaard geen servicebeheerder toegewezen. In plaats daarvan moet u een tenantbeheerder met de rol van algemeen beheerder gebruiken om de eerste servicebeheerder voor uw abonnement toe te wijzen. Als servicebeheerder kunt u de [Intune-beheerconsole](https://manage.microsoft.com/) gebruiken om dagelijkse taken te beheren voor Intune. U wijst servicebeheerders vanuit de beheerconsole toe. Een servicebeheerder moet een licentie voor Intune hebben voor toegang tot de beheerconsole.

Aan een servicebeheerder wordt een van de volgende machtigingen toegewezen:
- **Volledige toegang**: onbeperkte toegang tot alle gebieden van de Intune-beheerconsole, andere servicebeheerders toevoegen en beheren
- **Alleen-lezentoegang**: leesmachtiging voor alle gebieden van de Intune-beheerconsole, kan geen gegevens wijzigen, maar kan wel rapporten uitvoeren
- **Helpdesk - knooppunt Groepen**: de servicebeheerders kunnen alleen taken uitvoeren die zijn gekoppeld aan helpdeskscenario's, zie [Intune-consoleweergaven aanpassen voor beheerdersrollen](/intune-classic/deploy-use/control-what-admins-can-see-in-the-microsoft-intune-admin-console)

Als servicebeheerder gebruikt u deze portal om dagelijkse taken te beheren, waaronder:

- Beleid voor computers en mobiele apparaten maken en beheren
- Software-updates en apps uploaden en implementeren
- Endpoint Protection op computers beheren
- Apparaatstatus weergeven en rapporten uitvoeren

### <a name="device-enrollment-managers"></a>Apparaatinschrijvingsmanagers

Apparaatinschrijvingsbeheerders zijn standaardgebruikersaccounts met een aanvullende machtiging voor het registreren van meerdere apparaten zonder gebruiker. Elke Intune-gebruiker kan standaard maximaal vijf apparaten registreren. Als beheerder kunt u een gebruikersaccount de machtiging apparaatinschrijvingsbeheerder geven. Dit account kan grote aantallen apparaten in bedrijfseigendom registreren. Dit is handig als apparaten bijvoorbeeld tijdelijk aan gebruikers worden toegewezen of worden gebruikt in kioskmodus, waarbij geen gebruiker aan het apparaat gekoppeld hoeft te worden. Zie [Apparaatinschrijvingsbeheerder](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) voor meer informatie.

>[!div class="step-by-step"]

>[&larr; **Domeininstellingen**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Intune-licenties beheren** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)  

