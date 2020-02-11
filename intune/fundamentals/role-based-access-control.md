---
title: Op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune
description: Ontdek hoe u met RBAC kunt bepalen welke personen acties kunnen uitvoeren en wijzigingen kunnen aanbrengen in Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8441a93a34af68a680aec2f48b3a5375fa74558c
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754300"
---
# <a name="role-based-access-control-rbac-with-microsoft-intune"></a>Op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune

Met op rollen gebaseerd toegangsbeheer (RBAC) kunt u beheren wie toegang heeft tot resources van uw organisatie en wat ze kunnen doen met deze resources.  Door het [toewijzen van rollen](assign-role.md) aan uw Intune-gebruikers kunt u beperken wat ze kunnen bekijken en wijzigen. Elke rol heeft een set machtigingen om te bepalen waartoe gebruikers met deze rol in uw organisatie toegang hebben en welke wijzigingen zij kunnen aanbrengen.

Als u rollen wilt maken, bewerken of toewijzen, moet uw account een van de volgende machtigingen hebben in Azure AD:
- **Globale beheerder**
- **Intune-servicebeheerder** (ook wel bekend als **Intune-beheerder**)

Voor advies en suggesties over Intune RBAC kunt u de volgende vijf video's bekijken, waarin voorbeelden en procedures worden getoond: [1](https://www.youtube.com/watch?v=5deXLMLcnKY), [2](https://www.youtube.com/watch?v=38dnMBLuxbQ), [3](https://www.youtube.com/watch?v=6vqg9cAkMbY), [4](https://www.youtube.com/watch?v=5yOLajFFMHE), [5](https://www.youtube.com/watch?v=P5DDvsSF4Wk).

## <a name="roles"></a>Rollen
Met een rol wordt bepaald welke set machtigingen aan gebruikers wordt verleend die zijn toegewezen aan die rol.
U kunt zowel ingebouwde als aangepaste rollen gebruiken. Ingebouwde rollen hebben betrekking op bepaalde algemene Intune-scenario's. U kunt [uw eigen aangepaste rollen maken](create-custom-role.md) met de exacte set machtigingen die u nodig hebt. Meerdere Azure Active Directory-rollen hebben machtigingen voor Intune.
Als u een rol wilt bekijken, kiest u **Intune** > **Rollen** > **Alle rollen** > Een rol kiezen. Hier ziet u de volgende pagina's:

- **Eigenschappen**: de naam, de beschrijving, het type, de toewijzingen en de bereiktags voor de rol. 
- **Machtigingen**: hierin wordt een lange reeks schakelknoppen vermeld waarmee wordt bepaald over welke machtigingen de rol beschikt.
- **Toewijzingen**: een lijst met [roltoewijzingen]( assign-role.md) waarin wordt gedefinieerd welke gebruikers toegang hebben tot welke gebruikers/apparaten. Een rol kan over meerdere toewijzingen beschikken, en een gebruiker kan zich in meerdere toewijzingen bevinden.

### <a name="built-in-roles"></a>Ingebouwde rollen
U kunt ingebouwde rollen toewijzen aan groepen zonder verdere configuratie. U kunt de naam, de beschrijving, het type of de machtigingen van een ingebouwde rol niet verwijderen of bewerken.

- **Helpdesk-medewerker**: voert externe taken uit voor gebruikers en apparaten en kan toepassingen of beleid toewijzen aan gebruikers of apparaten.
- **Beleid- en profielbeheerder**: Hiermee worden het nalevingsbeleid, de configuratieprofielen, de Apple-inschrijving en id's van bedrijfsapparaten en beveiligingsbasislijnen beheerd.
- **Operator met alleen-lezenmachtiging**: kan alleen gebruikers-, apparaat-, inschrijvings-, configuratie- en toepassingsgegevens weergeven. Kan geen wijzigingen aan Intune aanbrengen.
- **Toepassingsbeheerder**: hiermee beheert u mobiele en beheerde toepassingen, kunt u apparaatgegevens lezen en kunt u apparaatconfiguratieprofielen weergeven.
- **Beheerder Intune-rol**: hiermee beheert u aangepaste Intune-rollen en voegt u toewijzingen toe voor ingebouwde Intune-rollen. Het is de enige rol in Intune die machtigingen aan beheerders kan toewijzen.
- **School Administrator**: Hiermee worden Windows 10-apparaten beheerd in [Intune for Education](../introduction-intune-education.md).
- **Endpoint Security Manager**: hiermee beheert u beveiligings- en nalevingsfuncties, zoals beveiligingsbasislijnen, apparaatcompatibiliteit, voorwaardelijke toegang en Microsoft Defender ATP.

### <a name="custom-roles"></a>Aangepaste rollen
U kunt uw eigen rollen maken met aangepaste machtigingen. Zie [Een aangepaste rol maken](create-custom-role.md)voor meer informatie over aangepaste rollen.

### <a name="azure-active-directory-roles-with-intune-access"></a>Azure Active Directory-rollen met Intune-toegang
| Azure Active Directory-rol | Alle Intune-gegevens | Controlegegevens voor Intune |
| --- | :---: | :---: |
| Hoofdbeheerder | Lezen/schrijven | Lezen/schrijven |
| Intune-servicebeheerder | Lezen/schrijven | Lezen/schrijven |
| Beheerder van voorwaardelijke toegang | Geen | Geen |
| Beveiligingsbeheer | Alleen-lezen (volledige beheerdersmachtigingen voor Endpoint Security-knooppunt) | Alleen-lezen |
| Beveiligingsoperator | Alleen-lezen | Alleen-lezen |
| Beveiligingslezer | Alleen-lezen | Alleen-lezen |
| Beheerder voor naleving | Geen | Alleen-lezen |
| Beheerder voor nalevingsgegevens | Geen | Alleen-lezen |
| Algemene lezer | Alleen lezen | Alleen lezen |

> [!TIP]
> Intune bevat ook drie Azure AD-uitbreidingen: **Gebruikers**, **Groepen** en **Voorwaardelijke toegang**, die worden beheerd met Azure AD RBAC. Bovendien voert de **Beheerder van gebruikersaccounts** alleen activiteiten van AAD-gebruikers of -groepen uit en beschikt deze niet over volledige machtigingen voor het uitvoeren van alle activiteiten in Intune. Zie [RBAC met Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) voor meer informatie.
### <a name="roles-created-in-the-intune-classic-portal"></a>Rollen die zijn gemaakt in de klassieke Intune-portal
Alleen gebruikers met de rol **Intune-servicebeheerder** met volledige machtigingen worden gemigreerd van de klassieke Intune-portal naar Intune in de Azure-portal. U moet gebruikers met de rol **Intune-servicebeheerder** opnieuw toewijzen met Alleen-lezen- of Helpdesk-toegang aan de Intune-rollen in Azure Portal en deze verwijderen uit de klassieke portal.
> [!IMPORTANT]
> Mogelijk moet u de toegang als Intune-servicebeheerder behouden in de klassieke portal als de beheerder nog steeds toegang nodig heeft om pc's te beheren met Intune.

## <a name="role-assignments"></a>Roltoewijzingen
Met een roltoewijzing wordt gedefinieerd:

- Welke gebruikers aan de rol zijn toegewezen.
- Welke resources ze kunnen zien.
- Welke resources ze kunnen wijzigen.

U kunt aangepaste en ingebouwde rollen toewijzen aan uw gebruikers. Alleen aan gebruikers met een Intune-licentie kan een Intune-rol worden toegewezen.
Als u een rol wilt bekijken, kiest u **Intune** > **Rollen** > **Alle rollen** > Een rol kiezen > Een toewijzing kiezen. Hier ziet u de volgende pagina's:

- **Eigenschappen**: De naam, beschrijving, rol, leden, bereiken en tags van de toewijzing.
- **Leden**: Alle gebruikers in vermelde Azure-beveiligingsgroepen hebben een machtiging voor het beheren van de gebruikers/apparaten die in Bereik (groepen) worden vermeld.
- **Bereik (groepen)** : Alle gebruikers/apparaten in deze Azure-beveiligingsgroepen kunnen worden beheerd door de gebruikers in Leden.
- **[Bereik (tags)](scope-tags.md)** : Gebruikers in Leden kunnen de resources zien die over dezelfde bereiktags beschikken.

### <a name="multiple-role-assignments"></a>Meerdere roltoewijzingen
Als een gebruiker meerdere roltoewijzingen, machtigingen en bereiktags heeft, worden deze roltoewijzingen als volgt uitgebreid naar verschillende objecten:

- Toegewezen machtigingen en bereiktags zijn alleen van toepassing op de objecten (zoals beleid of apps) in het bereik van deze roltoewijzing (groepen). Toegewezen machtigingen en bereiktags zijn niet van toepassing op objecten in andere roltoewijzingen, tenzij de andere toewijzing deze specifiek verleent.
- Andere machtigingen (zoals maken, lezen, bijwerken en verwijderen) en bereiktags zijn van toepassing op alle objecten van hetzelfde type (zoals alle beleidsregels of alle apps) in een van de toewijzingen van de gebruiker.
- Machtigingen en bereiktags voor objecten van verschillende typen (zoals beleid of apps), zijn niet van toepassing op elkaar. Een leesmachtiging voor een beleid, bijvoorbeeld, biedt geen leesmachtiging voor apps in toewijzingen van de gebruiker.

## <a name="next-steps"></a>Volgende stappen
- [Een rol toewijzen aan een gebruiker](assign-role.md)
- [Een aangepaste rol maken](create-custom-role.md)
