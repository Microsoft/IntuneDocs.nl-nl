---
title: RBAC met Microsoft Intune
description: Meer informatie over hoe u met op rollen gebaseerd toegangsbeheer (RBAC) kunt bepalen wie acties kunnen uitvoeren en wijzigingen kunnen aanbrengen in Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 5c75bd80e848bbd309051a9c6f3e149abd7a46ed
ms.sourcegitcommit: 378474debffbc85010c54e20151d81b59b7a7828
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/24/2018
ms.locfileid: "47028695"
---
# <a name="role-based-administration-control-rbac-with-microsoft-intune"></a>Op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune

Met RBAC kunt u bepalen wie de verschillende Intune-taken binnen uw organisatie kunnen uitvoeren en op wie die taken van toepassing zijn. U kunt de ingebouwde rollen gebruiken die voorzien in bepaalde algemene Intune-scenario's of u kunt uw eigen rollen maken. Een rol wordt gedefinieerd op basis van het volgende:

- **Roldefinitie**: de naam van een rol, de resources die ermee worden beheerd en de machtigingen die voor elke resource worden toegewezen.
- **Leden**: de gebruikersgroepen waaraan de machtigingen zijn toegewezen.
- **Bereik**: de gebruikers- of apparaatgroepen die de leden kunnen beheren.
- **Toewijzing**: wanneer de definitie, leden en het bereik zijn geconfigureerd, wordt de rol toegewezen.

![Voorbeeld van Intune RBAC](./media/intune-rbac-1.PNG)

Met ingang van de nieuwe Azure-portal beschikt **Azure Active Directory (Azure AD)** over twee Directory-rollen die kunnen worden gebruikt met Intune. Aan deze rollen worden volledige machtigingen toegewezen voor het uitvoeren van alle activiteiten in Intune:

- **Globale beheerder:** gebruikers met deze rol hebben toegang tot alle beheerfuncties in Azure AD, evenals de services die worden gekoppeld aan Azure AD, zoals Exchange Online, SharePoint Online en Skype voor Bedrijven Online. De persoon die zich aanmeldt voor de Azure AD-tenant wordt globale beheerder. Alleen globale beheerders kunnen andere Azure AD-beheerdersrollen toewijzen. Er kan meer dan een algemeen beheerder binnen uw organisatie zijn. Globale beheerders kunnen het wachtwoord voor elke gebruiker en alle andere beheerders opnieuw instellen.

- **Intune-servicebeheerder:** gebruikers met deze rol beschikken over globale machtigingen in Intune wanneer de service aanwezig is. Daarnaast biedt deze rol behalve vervangende Azure-beperkingen de mogelijkheid om gebruikers en apparaten te beheren en Intune-groepen te maken en beheren.

- **Beheerder van voorwaardelijke toegang:** gebruikers met deze rol hebben alleen machtigingen om beleidsregels voor voorwaardelijke toegang te bekijken, maken, wijzigen en verwijderen.

    > [!IMPORTANT]
    > De rol Intune-servicebeheerder biedt niet de mogelijkheid om de instellingen voor voorwaardelijke toegang van Azure AD te beheren.
    > Leden met Intune-rollen hebben een Intune-licentie nodig.

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
- **Toepassingsbeheerder**: hiermee beheert u mobiele en beheerde toepassingen, kunt u apparaatgegevens lezen en kunt u apparaatconfiguratieprofielen weergeven.
- **Beheerder Intune-rol**: hiermee beheert u aangepaste Intune-rollen en voegt u toewijzingen toe voor ingebouwde Intune-rollen. Het is de enige rol in Intune die machtigingen aan beheerders kan toewijzen.
- **School Administrator**: beheert Windows 10-apparaten in [Intune voor onderwijs](introduction-intune-education.md) en kan de volgende acties uitvoeren: 

|Machtiging|Bewerking|
|---|---|
|Controledatabase|Raadplegen|
|DeviceConfigurations|Toewijzen, maken, verwijderen, lezen, bijwerken|
|Apparaatinschrijvingsmanagers|Lezen, bijwerken|
|Beheerde apparaten|Lezen, bijwerken<!--, Delete [To be added in 1803]-->|
|Mobiele apps|Toewijzen, maken, verwijderen, lezen, bijwerken|
|Reports|Raadplegen|
|Externe acties|Pc opruimen, opnieuw opstarten, op afstand vergrendelen, buiten gebruik stellen, apparaten synchroniseren, wissen|
|Organisatie|Raadplegen|

### <a name="to-assign-a-built-in-role"></a>Een ingebouwde rol toewijzen

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Rollen** > **Alle rollen**.
1. Kies in het deelvenster **Intune-rollen - Alle rollen** de ingebouwde rol die u wilt toewijzen.

2. Kies in het deelvenster <*Rolnaam*> - **Overzicht** de optie **Beheren** en vervolgens **Toewijzingen**.

    > [!NOTE]
    > U kunt ingebouwde rollen niet verwijderen of bewerken

3. Kies in het deelvenster voor aangepaste rollen de optie **Toewijzen**.

4. Voer in het deelvenster **Roltoewijzingen** een **naam** en desgewenst een **beschrijving** in voor de toewijzing en kies het volgende:
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

2. Kies **Alle services** in het linkermenu en typ dan **Intune** in het filtertekstvak.

3. Kies **Intune** > **Rollen** > **Alle rollen** > **Aangepaste toevoegen**.

4. Voer in het deelvenster **Aangepaste rol toevoegen** een naam en beschrijving in voor de nieuwe rol en klik vervolgens op **Machtigingen**.

5. Kies in het deelvenster **Machtigingen** de machtigingen die u voor deze rol wilt gebruiken. Gebruik de [Intune RBAC-tabel](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) om te bepalen welke machtigingen u wilt toepassen.

6. Kies **OK** als u klaar bent.

7. Klik in het deelvenster **Aangepaste rol toevoegen** op **Maken**. De nieuwe rol wordt weergegeven in de lijst in het deelvenster **Intune-rollen - Alle rollen**.

### <a name="to-assign-a-custom-role"></a>Een aangepaste rol toewijzen

1. Kies in het deelvenster **Intune-rollen - Alle rollen** de aangepaste rol die u wilt toewijzen.

2. Kies in het deelvenster <*Rolnaam*> - **Overzicht** de optie **Beheren** en vervolgens **Toewijzingen**. In dit deelvenster kunt u ook bestaande rollen bewerken of verwijderen.

3. Kies in het deelvenster voor aangepaste rollen de optie **Toewijzen**.

4. Voer in het deelvenster **Roltoewijzingen** een **naam** en desgewenst een **beschrijving** in voor de toewijzing en kies het volgende:
    - **Leden**: selecteer de groep die de gebruiker bevat aan wie u de machtigingen wilt verlenen.
    - **Bereik**: selecteer de groep met de gebruikers die het bovenstaande lid mogen beheren.
<br></br>
5. Wanneer u klaar bent, klikt u op **OK**. De nieuwe toewijzing wordt in de lijst met toewijzingen weergegeven.

## <a name="next-steps"></a>Volgende stappen

[De rol voor Intune Helpdesk-operator gebruiken met de portal voor probleemoplossing](help-desk-operators.md)

## <a name="see-also"></a>Zie ook

[Rollen toewijzen met Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
