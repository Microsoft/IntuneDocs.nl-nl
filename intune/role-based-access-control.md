---
title: RBAC met Intune
titleSuffix: Azure portal
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u met RBAC kunt bepalen welke personen acties kunnen uitvoeren en wijzigingen kunnen aanbrengen.'
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e9dc65389485d2a77e351b5e781824eed0612054
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="role-based-administration-control-rbac-with-intune"></a>Op rollen gebaseerd toegangsbeheer (RBAC) met Intune

Met RBAC kunt u bepalen wie de verschillende Intune-taken binnen uw organisatie kunnen uitvoeren en op wie die taken van toepassing zijn. U kunt de ingebouwde rollen gebruiken die voorzien in bepaalde algemene Intune-scenario's of u kunt uw eigen rollen maken. Een rol wordt gedefinieerd op basis van het volgende:

- **Roldefinitie**: de naam van een rol, de resources die ermee worden beheerd en de machtigingen die voor elke resource worden toegewezen.
- **Leden**: de gebruikersgroepen waaraan de machtigingen zijn toegewezen.
- **Bereik**: de gebruikers- of apparaatgroepen die de leden kunnen beheren.
- **Toewijzing**: wanneer de definitie, leden en het bereik zijn geconfigureerd, wordt de rol toegewezen.

![Voorbeeld van Intune RBAC](./media/intune-rbac-1.PNG)

Met ingang van de nieuwe Azure-portal beschikt **Azure Active Directory (Azure AD)** over twee Directory-rollen die kunnen worden gebruikt met Intune. Aan deze rollen worden volledige machtigingen toegewezen voor het uitvoeren van alle activiteiten in Intune:

- **Globale beheerder:** gebruikers met deze rol hebben toegang tot alle beheerfuncties in Azure AD, evenals de services die worden gekoppeld aan Azure AD, zoals Exchange Online, SharePoint Online en Skype voor Bedrijven Online. De persoon die zich aanmeldt voor de Azure AD-tenant wordt globale beheerder. Alleen globale beheerders kunnen andere Azure AD-beheerdersrollen toewijzen. Er kan meer dan een algemeen beheerder binnen uw organisatie zijn. Globale beheerders kunnen het wachtwoord voor elke gebruiker en alle andere beheerders opnieuw instellen.

- **Intune-servicebeheerder:** gebruikers met deze rol beschikken over globale machtigingen in Intune wanneer de service aanwezig is. Daarnaast biedt deze rol de mogelijkheid om gebruikers en apparaten te beheren, en groepen te maken en te beheren.

- **Beheerder van voorwaardelijke toegang:** gebruikers met deze rol hebben alleen machtigingen om beleidsregels voor voorwaardelijke toegang te bekijken, maken, wijzigen en verwijderen.

    > [!IMPORTANT]
    > De rol Intune-servicebeheerder biedt niet de mogelijkheid om de instellingen voor voorwaardelijke toegang van Azure AD te beheren.

    > [!TIP]
    > Intune bevat ook drie Azure AD-uitbreidingen: **Gebruikers**, **Groepen** en **Voorwaardelijke toegang** die worden beheerd met Azure AD RBAC. Bovendien voert de **Beheerder van gebruikersaccounts** alleen activiteiten van AAD-gebruikers of -groepen uit en beschikt deze niet over volledige machtigingen voor het uitvoeren van alle activiteiten in Intune. Raadpleeg [RBAC met Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) voor meer informatie.

## <a name="roles-created-in-the-intune-classic-portal"></a>Rollen die zijn gemaakt in de klassieke Intune-portal

Alleen gebruikers met de rol **Intune-servicebeheerder** met volledige machtigingen worden gemigreerd van de klassieke Intune-portal naar Intune in de Azure-portal. U moet gebruikers met de rol **Intune-servicebeheerder** opnieuw toewijzen met Alleen-lezen- of Helpdesk-toegang aan de Intune-rollen in Azure Portal en deze verwijderen uit de klassieke portal.

> [!IMPORTANT]
> Mogelijk moet u de toegang als Intune-servicebeheerder behouden in de klassieke portal als de beheerder nog steeds toegang nodig heeft om pc's te beheren met Intune.

## <a name="built-in-roles"></a>Ingebouwde rollen

De volgende rollen zijn ingebouwd in Intune en u kunt deze zonder verdere configuratie aan groepen toewijzen:

- **Helpdesk-medewerker**: voert externe taken uit voor gebruikers en apparaten en kan toepassingen of beleid toewijzen aan gebruikers of apparaten.
- **Beleid- en profielbeheerder**: beheert het nalevingsbeleid, configuratieprofielen, Apple-inschrijving en id's van bedrijfsapparaten.
- **Operator met alleen-lezenmachtiging**: kan alleen gebruikers-, apparaat-, inschrijvings-, configuratie- en toepassingsgegevens weergeven. Kan geen wijzigingen aan Intune aanbrengen.
- **Toepassingsbeheerder**: beheert mobiele en beheerde toepassingen en kan de apparaatgegevens lezen.

### <a name="to-assign-a-built-in-role"></a>Een ingebouwde rol toewijzen

1. Kies op de blade **Intune-rollen** de ingebouwde rol die u wilt toewijzen.

2. Kies op de blade <*rolnaam*> - **Eigenschappen** de optie **Beheren** en vervolgens **Toewijzingen**.

    > [!NOTE]
    > U kunt ingebouwde rollen niet verwijderen of bewerken

3. Kies op de blade voor aangepaste rollen de optie **Toewijzen**.

4. Voer op de blade **Roltoewijzingen** een **naam** en desgewenst een **beschrijving** in voor de toewijzing en kies het volgende:
    - **Leden**: selecteer de groep die de gebruiker bevat aan wie u de machtigingen wilt verlenen.
    - **Bereik**: selecteer de groep met de gebruikers die het bovenstaande lid mogen beheren.
<br></br>
5. Wanneer u klaar bent, klikt u op **OK**. De nieuwe toewijzing wordt in de lijst met toewijzingen weergegeven.

### <a name="intune-rbac-table"></a>Intune RBAC-tabel

- Download de [Intune RBAC-tabel](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) voor meer informatie over wat u met elke rol kunt doen.

## <a name="custom-roles"></a>Aangepaste rollen

U kunt een aangepaste rol maken die alle machtigingen bevat die vereist zijn voor een bepaalde taakfunctie. Als een groep van de IT-afdeling bijvoorbeeld toepassingen, beleidsregels en configuratieprofielen beheert, kunt u al deze machtigingen samenvoegen tot één aangepaste rol.

> [!IMPORTANT]
> Als u rollen wilt maken, bewerken of toewijzen, moet uw account een van de volgende machtigingen hebben in Azure AD:
> - **Globale beheerder**
> - **Intune-servicebeheerder**

### <a name="to-create-a-custom-role"></a>Een aangepaste rol maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com) met uw Intune-referenties.

2. Kies **Meer services** in het linkermenu en typ dan **Intune** in het vak tekstfilter.

3. Kies **Intune**. Het Intune-dashboard wordt geopend en kies vervolgens **Intune-rollen**.

4. Kies op de blade **Intune-rollen** de optie **Intune-rollen** en vervolgens **Aangepaste rol toevoegen**.

5. Voer op de blade **Aangepaste rol toevoegen** een naam en beschrijving in voor de nieuwe rol en klik vervolgens op **Machtigingen**.

3. Kies op de blade **Machtigingen** de machtigingen die u voor deze rol wilt gebruiken. Gebruik de [Intune RBAC-tabel](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) om te bepalen welke machtigingen u wilt toepassen.

4. Kies **OK** als u klaar bent.

5. Klik op de blade **Aangepaste rol toevoegen** op **Maken**. De nieuwe rol wordt weergegeven in de lijst op de blade **Intune-rollen**.

### <a name="to-assign-a-custom-role"></a>Een aangepaste rol toewijzen

1. Kies op de blade **Intune-rollen** de aangepaste rol die u wilt toewijzen.

2. Kies op de blade <*rolnaam*> - **Eigenschappen** de optie **Beheren** en vervolgens **Toewijzingen**. Op deze blade kunt u ook bestaande rollen bewerken of verwijderen.

3. Kies op de blade voor aangepaste rollen de optie **Toewijzen**.

4. Voer op de blade **Roltoewijzingen** een **naam** en desgewenst een **beschrijving** in voor de toewijzing en kies het volgende:
    - **Leden**: selecteer de groep die de gebruiker bevat aan wie u de machtigingen wilt verlenen.
    - **Bereik**: selecteer de groep met de gebruikers die het bovenstaande lid mogen beheren.
<br></br>
5. Wanneer u klaar bent, klikt u op **OK**. De nieuwe toewijzing wordt in de lijst met toewijzingen weergegeven.

## <a name="next-steps"></a>Volgende stappen

[De rol voor Intune Helpdesk-operator gebruiken met de portal voor probleemoplossing](help-desk-operators.md)

## <a name="see-also"></a>Zie tevens

[Rollen toewijzen met Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
