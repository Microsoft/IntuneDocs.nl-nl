---
title: Gebruikers toevoegen en machtigingen verlenen
description: On-premises gebruikers met Azure AD synchroniseren en beheerdersmachtigingen voor uw Intune-abonnement verlenen
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4289fdbdadbef34f06514b62722f84354534ae65
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

In dit onderwerp wordt aan beheerders uitgelegd hoe ze gebruikers kunnen toevoegen aan Intune en welke machtigingen beschikbaar zijn in de Intune-service.

Als beheerder kunt u gebruikers rechtstreeks toevoegen of gebruikers synchroniseren via uw on-premises Active Directory. Zodra gebruikers zijn toegevoegd, kunnen ze apparaten registreren en hebben ze toegang tot bedrijfsresources. U kunt gebruikers ook aanvullende machtigingen geven, zoals de machtigingen *globale beheerder* en *servicebeheerder*.

## <a name="add-users-to-intune"></a>Gebruikers toevoegen aan Intune
U kunt handmatig gebruikers aan uw Intune-abonnement toevoegen via de [Office 365-portal](https://www.office.com/signin) of de [Azure Intune-portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). Een beheerder kan gebruikersaccounts bewerken om Intune-licenties toe te wijzen. U kunt licenties toewijzen in de Office 365-portal of in de Intune Azure-portal. Zie [Gebruikers afzonderlijk of bulksgewijs toevoegen aan de Office 365-portal](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec) voor meer informatie over het gebruik van de Office 365-portal.

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Intune-gebruikers toevoegen in het Office 365-beheercentrum
1. Meld u aan bij de [Office 365-portal](https://www.office.com/signin).
2. Selecteer **Beheer** in het menu Office 365.
3. Selecteer **Nieuwe gebruiker** in het beheercentrum.

  ![Schermafbeelding van het Office 365-beheercentrum](media/office-add-user.png)

4. Geef de volgende gebruikersgegevens op:
  - **Voornaam**
  - **Achternaam**
  - **Weergavenaam**: wordt weergegeven in de Intune-portal
  - **Gebruikersnaam**: de UPN-naam in de Intune-portal
  - **Locatie**
  - **Contactgegevens** (optioneel)
  - **Wachtwoord**: automatisch genereren of opgeven

     ![Schermafbeelding van het Office 365-beheercentrum](media/office-add-user-details.png)

5. Wijs een Intune-licentie toe. Selecteer **Productlicenties** en kies de productlicentie.
6. Kies **Toevoegen** om de nieuwe gebruiker te maken.

### <a name="add-intune-users-in-the-azure-intune-portal"></a>Intune-gebruikers toevoegen in de Azure Intune-portal
1. Meld u aan bij [Azure Portal](https://portal.azure.com). Ga naar **Bewaking en beheer** > **Intune**. U kunt ook *zoeken naar resources* voor **Intune**.
2. Selecteer **Gebruikers**.
3. Selecteer **Nieuwe gebruiker** in het beheercentrum.
  ![Schermafbeelding van het Office 365-beheercentrum](media/intune-add-user.png)
4. Geef de volgende gebruikersgegevens op:
  - **Naam**
  - **Gebruikersnaam**: de nieuwe naam in de Azure Active Directory-portal ![Schermafbeelding van het Office 365-beheercentrum](media/intune-add-user-info.png) Kies **OK** om door te gaan.
5. U kunt desgewenst de volgende gebruikerseigenschappen opgeven:
  - **Profiel**: werkinformatie zoals **Functie** en **Afdeling**
  -  **Groepen**: selecteer groepen die u wilt toevoegen voor de gebruiker
  - **Maprol**: geef de gebruiker beheerdersmachtigingen voor Intune

  Selecteer **Maken** om de nieuwe gebruiker toe te voegen aan Intune.
6. Selecteer **Profiel** en kies vervolgens een **gebruikslocatie** voor de nieuwe gebruiker. Een gebruikslocatie is vereist om een licentie voor Intune te kunnen toewijzen aan de nieuwe gebruiker. Kies **Opslaan** om door te gaan.
    ![Schermafbeelding van het Office 365-beheercentrum](media/intune-add-user-loc.png)
7. Selecteer **Licenties** en kies vervolgens **Toewijzen** om een Intune-licentie voor deze gebruiker toe te wijzen. Een Intune-licentie is vereist voor het registreren van apparaten of om toegang te krijgen tot bedrijfsresources. Selecteer **Producten**, kies het licentietype, kies **Selecteren** en kies ten slotte **Toewijzen**.

## <a name="grant-admin-permissions"></a>Beheerdersmachtigingen verlenen

Nadat u gebruikers aan uw Intune-abonnement hebt toegevoegd, kunt u het beste aan een paar gebruikers beheermachtigingen verlenen:
-   [Globale beheerder](#tenant-administrator): gebruik de Office 365-portal om dit type beheerder toe te wijzen. De globale beheerder kan uw abonnement beheren, met inbegrip van facturering en cloudopslag en het beheren van de gebruikers die Intune kunnen gebruiken.
-   [Servicebeheerder](#service-administrator): gebruik de Office 365-console of de Azure Intune-console om dit type beheerder toe te wijzen voor dagelijkse taken, waaronder het beheer van apparaten en computers, het implementeren van beleid en apps, en het uitvoeren van rapporten.

![Afbeelding van scherm in Office 365-portal voor het toewijzen van rollen.](./media/office-assign-roles.png)

### <a name="types-of-administrators"></a>Typen beheerders

Wijs gebruikers een of meer beheerdersmachtigingen toe. Deze machtigingen bepalen het beheerbereik voor gebruikers en de taken die ze kunnen beheren. De beheerdersmachtigingen voor de verschillende Microsoft-cloudservices komen overeen, hoewel bepaalde machtigingen mogelijk niet worden ondersteund door sommige services. In Intune worden de volgende beheerdersmachtigingen gebruikt:

- **Globale beheerder**: (Office 365 en Intune) heeft toegang tot alle beheerfuncties in Intune. De persoon die zich voor Intune aanmeldt, wordt standaard een globale beheerder. Globale beheerders zijn de enige beheerders die andere beheerdersrollen kunnen toewijzen. U kunt meer dan één globale beheerder hebben in uw organisatie. Als best practice is het raadzaam dat slechts een paar mensen in uw bedrijf deze rol vervullen om het risico voor uw bedrijf te reduceren.
- **Factureringsbeheerder**: (Office 365 en Intune) doet aankopen, beheert abonnementen, beheert ondersteuningstickets en bewaakt de servicestatus.
- **Wachtwoordbeheerder**: (Office 365 en Intune) stelt wachtwoorden opnieuw in, beheert serviceaanvragen en bewaakt de servicestatus. Wachtwoordbeheerders zijn beperkt tot het opnieuw instellen van wachtwoorden voor gebruikers.
- **Servicebeheerder**: (Office 365) opent ondersteuningsaanvragen voor Microsoft en bekijkt het servicedashboard en berichtencentrum. Ze beschikken alleen over weergavemachtigingen, met uitzondering voor het openen en lezen van ondersteuningstickets.
- **Beheerder gebruikerstoegang**: (Office 365 en Intune) stelt wachtwoorden opnieuw in, bewaakt de servicestatus, voegt gebruikersaccounts toe en verwijdert deze, en beheert serviceaanvragen. De beheerder van de gebruikerstoegang kan geen globale beheerder verwijderen, andere beheerdersrollen maken of wachtwoorden opnieuw instellen voor andere beheerders.

Het account dat u gebruikt om uw Microsoft Intune-abonnement te maken, heeft standaard de rol Globale beheerder. Het is een best practice om de rol van globale beheerder niet te gebruiken voor dagelijkse beheertaken. Een beheerder heeft geen licentie voor Intune nodig voor toegang tot de Intune-beheerconsole. Zie de sectie over de Azure AD-tenant in [Wat is een Azure AD-adreslijst?](http://technet.microsoft.com/library/jj573650.aspx).

Voor toegang tot de Office 365-portal moet **Toegestane gebruikers aanmelden** zijn ingesteld voor uw account. Ga in de Intune-beheerportal naar **Profiel** en stel **Aanmelden blokkeren** in op **Nee** om toegang te verlenen. Deze status is niet hetzelfde als wanneer u een licentie voor het abonnement hebt. Standaard hebben alle gebruikersaccounts de status **Toegestaan**. Gebruikers zonder beheerdersmachtigingen kunnen de Office 365-portal gebruiken om het Intune wachtwoorden opnieuw instellen.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Active Directory synchroniseren en gebruikers toevoegen aan Intune
U kunt adreslijstsynchronisatie configureren voor het importeren van gebruikersaccounts uit de on-premises Active Directory in Microsoft Azure Active Directory (Azure AD) die Intune-gebruikers bevat. Het koppelen van uw on-premises Active Directory-service aan alle Azure Active Directory-services zorgt ervoor dat het beheer van gebruikersidentiteiten veel eenvoudiger wordt. U kunt ook eenmalige aanmelding configureren om de verificatie vertrouwd en eenvoudig te maken voor uw gebruikers. Door dezelfde [Azure AD-tenant](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) te koppelen met meerdere services, zijn de gebruikersaccounts die u eerder hebt gesynchroniseerd, beschikbaar voor alle cloudservices.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>On-premises gebruikers synchroniseren met Azure AD
Het enige hulpprogramma dat u nodig hebt om uw gebruikersaccounts te synchroniseren met Azure AD, is de [Azure AD Connect-wizard](https://www.microsoft.com/download/details.aspx?id=47594). De Azure AD Connect-wizard biedt een vereenvoudigde begeleiding voor het verbinden van de on-premises infrastructuur voor identiteiten aan de cloud.  Kies uw topologie en behoeften (één of meerdere mappen, wachtwoordsynchronisatie of federatie). De wizard implementeert en configureert alle onderdelen die zijn vereist om de verbinding mogelijk te maken. Inclusief: synchronisatieservices, Active Directory Federation Services (AD FS) en de Azure AD PowerShell-module.

> [!TIP]
> Azure AD Connect bevat functionaliteit die eerder is uitgebracht als Dirsync en Azure AD Sync. Lees meer over [adreslijstintegratie](http://technet.microsoft.com/library/jj573653.aspx). Zie [Overeenkomsten tussen Active Directory en Azure AD](http://technet.microsoft.com/library/dn518177.aspx) voor meer informatie over het synchroniseren van gebruikersaccounts vanuit de lokale directory naar Azure AD.
