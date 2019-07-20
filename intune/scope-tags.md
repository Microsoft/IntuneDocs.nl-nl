---
title: Beleid met bereiktags filteren in Microsoft Intune - Azure | Microsoft Docs
description: Bereiktags gebruiken voor het filteren van configuratieprofielen op specifieke rollen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 627899eafb2175b2d3034045bd765a10f4a203d6
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882496"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT

U kunt op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken om ervoor te zorgen dat de juiste beheerders de juiste toegang tot en zichtbaarheid van de juiste Intune-objecten hebben. Rollen bepalen welke toegang beheerders hebben tot welke objecten. Bereiktags bepalen welke objecten zichtbaar zijn voor beheerders.

Laten we bijvoorbeeld zeggen dat een beheerder van het regionale kantoor in Seattle de rol van beleids- en profielbeheerder is toegewezen. U wilt dat deze beheerder alleen de profielen en beleidsregels ziet en beheert die van toepassing zijn op de apparaten in Seattle. Hiervoor zou u het volgende moeten doen:

1. Maak een bereiktag met de naam Seattle.
2. Maak een roltoewijzing voor de rol beleids- en profielbeheerder met: 
    - Leden (groepen) = een beveiligingsgroep met de naam IT-beheerders in Seattle. Alle beheerders in deze groep hebben toestemming voor het beheren van beleidsregels en profielen voor gebruikers/apparaten binnen het bereik (Groepen).
    - Bereik (Groepen) = een beveiligingsgroep met de naam gebruikers in Seattle. Alle gebruikers/apparaten in deze groep kunnen hun profielen en beleidsregels laten beheren door de beheerders in Leden (Groepen). 
    - Bereik(tags) = Seattle. Beheerders in Leden (Groepen) ziet apparaten waarvoor ook de bereiktag Seattle.
3. Voeg de bereiktag Seattle toe aan beleidsregels en profielen waartoe beheerders in Leden (Groepen) toegang moeten hebben.
4. Voeg de bereiktag Seattle toe aan apparaten die zichtbaar moeten zijn voor beheerders in Leden (Groepen). 


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
3. Kies **Leden (Groepen)**  > **Toevoegen** > kies de groepen die deel moeten uitmaken van deze toewijzing > **Selecteren** > **OK**. Gebruikers in deze groep zijn gemachtigd om beleidsregels en profielen voor gebruikers/apparaten binnen het bereik (Groepen) te beheren.

    ![Schermopname van Lidgroepen selecteren.](./media/scope-tags/select-member-groups.png)

4. Als u gebruikers/apparaten in een specifieke reeks groepen wilt beheren, kiest u **Bereik (Groepen)**  > **Geselecteerde groepen** > **Groepen selecteren om op te nemen** > kies de groepen > **Selecteren** > **OK**. Alle gebruikers/apparaten in deze groep kunnen hun profielen en beleidsregels laten beheren door de beheerders in Leden (Groep).

    ![Schermopname van Bereikgroepen selecteren.](./media/scope-tags/select-scope-groups.png)

    U kunt ook **Alle apparaten**, **Alle gebruikers**, of **Alle gebruikers en alle apparaten** kiezen.

    ![Schermopname van de andere opties voor het selecteren van bereikgroepen.](./media/scope-tags/scope-group-other-options.png)
    
5. Kies **Bereik(tags)**  > **Toevoegen** > kies de tags die u aan deze rol wilt toevoegen > **Selecteren** > **OK**. Gebruikers in Leden (Groepen) hebben toegang tot de beleidsregels en profielen die ook dezelfde bereiktag hebben.

    ![Schermopname van Bereiktags selecteren.](./media/scope-tags/select-scope-tags.png)

6. Kies **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Een bereiktag toevoegen aan een configuratieprofiel
1. Kies in Intune **Apparaatconfiguratie** > **Profielen** > kies een profiel.

    ![Schermopname van Profiel selecteren.](./media/scope-tags/choose-profile.png)

2. Kies **Eigenschappen** > **Bereik(tags)**  > **Toevoegen**.

    ![Schermopname van Bereik-tags toevoegen.](./media/scope-tags/add-scope-tags.png)

3. Kies onder **Tags selecteren** de tags die u wilt toevoegen aan het profiel.
4. Kies **Selecteren** > **OK** > **Opslaan**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Een bereiktag toewijzen aan een app-configuratiebeleid
Voor apparaten met het **Type apparaatinschrijving** ingesteld op **Beheerde apparaten**:
1. Kies **Client-apps** > **App-configuratiebeleid** > Kies een app-configuratiebeleid.
2. Kies **Eigenschappen** > **Bereik(tags)** > kies de tags die u wilt toewijzen aan het beleid.

Voor apparaten met het **Type apparaatinschrijving** ingesteld op **Beheerde apps**:
1. Kies **Client-apps** > **App-configuratiebeleid** > kies een app-configuratiebeleid.
2. Kies **Bereik(tags)** > kies de tags die u wilt toewijzen aan het beleid.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Een bereiktag toewijzen aan een inrichtingsprofiel van een iOS-app
1. Kies in Intune **Client-apps** > **inrichtingsprofielen voor iOS-apps** > kies een profiel.
2. Kies **Eigenschappen** > **Bereik(tags)** > kies de tags die u wilt toewijzen aan het profiel.
3. Kies **Selecteren** > **OK** > **Opslaan**.

## <a name="to-assign-a-scope-tag-to-an-apple-volume-purchase-program-vpp-token"></a>Een bereiktag toewijzen aan een Apple VPP-token (VPP: Volume Purchase Program)
1. Kies in Intune **Client-apps** > **Apple VPP-tokens** > kies een VPP-token.
2. Selecteer **Bereik(tags)** > kies de tags die u wilt toewijzen aan het profiel. De toegewezen tags wordt overgenomen door de VPP-apps en ebooks die zijn gekoppeld aan het VPP-token.
3. Kies **Selecteren** > **OK** > **Opslaan**.

## <a name="scope-tag-details"></a>Details bereiktags
Wanneer u met bereiktags werkt, moet u deze details onthouden:

- U kunt op dit moment bereiktags toewijzen aan:
  - Roltoewijzingen
  - Nalevingsbeleid voor apparaten
  - Apparaatconfiguratieprofielen
  - Windows 10-updateringen
  - Beheerde apparaten
  - Apps
  - App-configuratiebeleidsregels - beheerde apparaten toevoegen
  - PowerShell-scripts
  - DEP-tokens
  - Inrichtingsprofiel voor iOS-apps
  - VPP-tokens (Volume Purchase Program)
- Wanneer een beheerder een object in Intune maakt, worden alle aan die beheerder toegewezen bereiktags automatisch toegewezen aan het nieuwe object.
- Intune RBAC is niet van toepassing op Azure Active Directory-rollen. Dus hebben de rollen Intune-servicebeheerders en Globale beheerders volledige beheerderstoegang tot Intune, ongeacht welke bereiktags ze hebben.
- Voor beheerders in een roltoewijzing met bereiktags zijn ook de Intune-objecten zonder bereiktags zichtbaar.
- U kunt alleen een bereiktag toewijzen die zich in uw roltoewijzingen bevindt.
- U kunt alleen groepen die worden vermeld in Bereik (Groepen) van uw roltoewijzing als doelwit kiezen.
- Als een bereiktag aan uw rol is toegewezen, kunt u niet alle bereiktags voor een Intune-object verwijderen. Er is ten minste één bereiktag vereist.

## <a name="next-steps"></a>Volgende stappen

Beheer uw [rollen](role-based-access-control.md) en [profielen](device-profile-assign.md).
