---
title: Op rollen gebaseerd toegangs beheer (RBAC) en bereik Tags gebruiken voor gedistribueerde toegang in intune | Microsoft Docs
description: Bereiktags gebruiken voor het filteren van configuratieprofielen op specifieke rollen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.technology: ''
ms.assetid: a21d3039-f2ed-4f43-b6fa-d00c071edbc4
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6b92dca399afeb035bf58d998efdd469318de389
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504954"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT

U kunt op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken om ervoor te zorgen dat de juiste beheerders de juiste toegang tot en zichtbaarheid van de juiste Intune-objecten hebben. Rollen bepalen welke toegang beheerders hebben tot welke objecten. Bereiktags bepalen welke objecten zichtbaar zijn voor beheerders.

Laten we bijvoorbeeld zeggen dat een beheerder van het regionale kantoor in Seattle de rol van beleids- en profielbeheerder heeft. U wilt dat deze beheerder alleen de profielen en beleidsregels ziet en beheert die van toepassing zijn op de apparaten in Seattle. Als u deze toegang wilt instellen, doet u het volgende:

1. Maak een bereiktag met de naam Seattle.
2. Maak een roltoewijzing voor de rol beleids- en profielbeheerder met: 
    - Leden (groepen) = een beveiligingsgroep met de naam IT-beheerders in Seattle. Alle beheerders in deze groep hebben toestemming voor het beheren van beleidsregels en profielen voor gebruikers/apparaten binnen het bereik (Groepen).
    - Bereik (Groepen) = een beveiligingsgroep met de naam gebruikers in Seattle. Alle gebruikers/apparaten in deze groep kunnen hun profielen en beleidsregels laten beheren door de beheerders in Leden (Groepen). 
    - Bereik(tags) = Seattle. Beheerders in Leden (Groepen) zien Intune-objecten die ook de bereiktag Seattle hebben.
3. Voeg de bereiktag Seattle toe aan beleidsregels en profielen waartoe beheerders in Leden (Groepen) toegang moeten hebben.
4. Voeg de bereiktag Seattle toe aan apparaten die zichtbaar moeten zijn voor beheerders in Leden (Groepen). 

## <a name="default-scope-tag"></a>Standaardbereiktag
De standaard bereik code wordt automatisch toegevoegd aan alle niet-gelabelde objecten die ondersteuning bieden voor bereik Tags.

Deze functie voor standaardbereiktags is vergelijkbaar met de functie voor beveiligingsbereiken in System Center Configuration Manager. 

## <a name="to-create-a-scope-tag"></a>Een bereiktag maken

1. Kies in Intune **Rollen** > **Bereik(tags)**  > **Maken**.

    ![Schermopname van Een bereiktag maken.](./media/scope-tags/create-scope-tag.png)

3. Als u alle apparaten in specifieke groepen wilt, kiest u **Scope-label toewijzen aan alle apparaten in de geselecteerde groepen**.
    1. Kies op de pagina **groepen selecteren** die u wilt toevoegen de groepen met de apparaten waaraan u deze bereik markering wilt toewijzen.
    2. Kies **Selecteren**.
4. Kies **Maken**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Een bereiktag toewijzen aan een rol

1. Kies in Intune **Rollen** > **Alle rollen** > kies een rol > **Toewijzingen** > **Toewijzen**.

    ![Schermopname van het bereik aan een rol toewijzen.](./media/scope-tags/assign-scope-to-role.png)

2. Geef een **toewijzingsnaam** en een **beschrijving** op.
3. Kies **Leden (Groepen)**  > **Toevoegen** > kies de groepen die deel moeten uitmaken van deze toewijzing > **Selecteren** > **OK**. Gebruikers in deze groep hebben machtigingen voor het beheren van gebruikers/apparaten in het bereik (groepen).

    ![Schermopname van Lidgroepen selecteren.](./media/scope-tags/select-member-groups.png)

4. Als u gebruikers/apparaten in een specifieke reeks groepen wilt beheren, kiest u **Bereik (Groepen)**  > **Geselecteerde groepen** > **Groepen selecteren om op te nemen** > kies de groepen > **Selecteren** > **OK**. Alle gebruikers/apparaten in deze groep worden beheerd door de beheerders in de leden (groep).

    ![Schermopname van Bereikgroepen selecteren.](./media/scope-tags/select-scope-groups.png)

    U kunt ook **Alle apparaten**, **Alle gebruikers**, of **Alle gebruikers en alle apparaten** kiezen.

    ![Schermopname van de andere opties voor het selecteren van bereikgroepen.](./media/scope-tags/scope-group-other-options.png)
    
5. Kies **Bereik(tags)**  > **Toevoegen** > kies de tags die u aan deze rol wilt toevoegen > **Selecteren** > **OK**. Gebruikers in leden (groepen) hebben toegang tot intune-objecten die ook hetzelfde bereik hebben.

    ![Schermopname van Bereiktags selecteren.](./media/scope-tags/select-scope-tags.png)

6. Kies **OK**. 

## <a name="assign-scope-tags-to-other-objects"></a>Bereik tags toewijzen aan andere objecten

Voor objecten die bereik Tags ondersteunen, worden meestal Scope Tags weer gegeven onder **Eigenschappen**. Als u bijvoorbeeld een bereik label wilt toewijzen aan een configuratie profiel, volgt u deze stappen:

1. Kies in Intune **Apparaatconfiguratie** > **Profielen** > kies een profiel.

    ![Schermopname van Profiel selecteren.](./media/scope-tags/choose-profile.png)

2. Kies **Eigenschappen** > **Bereik(tags)**  > **Toevoegen**.

    ![Schermopname van Bereik-tags toevoegen.](./media/scope-tags/add-scope-tags.png)

3. Kies onder **Tags selecteren** de tags die u wilt toevoegen aan het profiel.
4. Kies **Selecteren** > **OK** > **Opslaan**.


## <a name="scope-tag-details"></a>Details bereiktags
Wanneer u met bereiktags werkt, moet u deze details onthouden: 

- U kunt bereik tags toewijzen aan een intune-object type als de Tenant meerdere versies van dat object kan hebben (zoals roltoewijzingen of apps).
  De volgende intune-objecten zijn uitzonde ringen op deze regel en ondersteunen momenteel geen bereik Tags:
    - Windows ESP-profielen
    - Apparaatcategorieën
    - Registratiebeperkingen
    - Corp-apparaat-Id's
    - Auto Pilot-apparaten
    - Locaties voor apparaatcompatibiliteit
    - Jamf-apparaten
- VPP-apps en ebooks die zijn gekoppeld aan het VPP-token nemen de bereik Tags over die zijn toegewezen aan het bijbehorende VPP-token.
- Device Enrollment Program (DEP)-apparaten en DEP-profielen die zijn gekoppeld aan het DEP-token nemen de bereik Tags over die zijn toegewezen aan het bijbehorende DEP-token.
- Wanneer een beheerder een object in Intune maakt, worden alle aan die beheerder toegewezen bereiktags automatisch toegewezen aan het nieuwe object.
- Intune RBAC is niet van toepassing op Azure Active Directory-rollen. Dus hebben de rollen Intune-servicebeheerders en Globale beheerders volledige beheerderstoegang tot Intune, ongeacht welke bereiktags ze hebben.
- Als een roltoewijzing geen bereik label heeft, kan de IT-beheerder alle objecten zien op basis van de machtigingen voor de IT-beheerder. Beheerders die geen bereik Tags hebben, hebben in wezen geen bereik Tags.
- U kunt alleen een bereiktag toewijzen die zich in uw roltoewijzingen bevindt.
- U kunt alleen groepen die worden vermeld in Bereik (Groepen) van uw roltoewijzing als doelwit kiezen.
- Als een bereiktag aan uw rol is toegewezen, kunt u niet alle bereiktags voor een Intune-object verwijderen. Er is ten minste één bereiktag vereist.

## <a name="next-steps"></a>Volgende stappen

Meer informatie over de werking van bereik Tags wanneer er [meerdere roltoewijzingen](role-based-access-control.md#multiple-role-assignments)zijn.
Beheer uw [rollen](role-based-access-control.md) en [profielen](../configuration/device-profile-assign.md).
