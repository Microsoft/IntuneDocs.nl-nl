---
title: Beleid met bereiktags filteren in Microsoft Intune - Azure | Microsoft Docs
description: Bereiktags gebruiken voor het filteren van configuratieprofielen op specifieke rollen.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb57ea2ef5c99c58968ee25b3a75b2165ece787a
ms.sourcegitcommit: 0adb41c0640743d5cb726e66ad2427e3ad6faf20
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/29/2019
ms.locfileid: "58658546"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT

U kunt op basis van de rol beheer- en scope-tags gebruiken om ervoor te zorgen dat de juiste beheerders de juiste toegang en de zichtbaarheid van de juiste Intune-objecten hebben. Rollen bepalen welke toegang beheerders hebben op welke objecten. Bereiktags bepalen welke objecten die beheerders kunnen zien.

Laten we zeggen dat een beheerder van de regionale office Seattle de beleids- en Profielbeheerder rol is toegewezen. Wilt u deze beheerder om te zien en beheren van alleen de profielen en beleidsregels die alleen van toepassing op de Seattle-apparaten. U doet dit door u dat zou doen:

1. Maak een bereiktag Seattle genoemd.
2. Maak een roltoewijzing voor de functie beleid- en Profielbeheerder met: 
    - Leden (groepen) = van een beveiligingsgroep met de naam Seattle IT-beheerders. Alle beheerders in deze groep hebben toestemming voor het beheren van beleidsregels en profielen voor gebruikers/apparaten binnen het bereik (groepen).
    - Bereik (groepen) = van een groep met de naam Seattle gebruikers. Alle gebruikers/apparaten in deze groep kunnen hebben hun profielen en beleidsregels die worden beheerd door de beheerders in de leden (groepen). 
    - Bereik (Tags) = Seattle. Beheerders in het lid (groepen) ziet apparaten waarvoor ook de bereiktag Seattle.
3. De bereiktag Seattle aan beleidsregels en profielen die u dat beheerders in leden (groepen wilt) om toegang te kunnen toevoegen.
4. De bereiktag Seattle aan apparaten die u wilt dat zichtbaar voor beheerders in de leden (groepen) toevoegen. 


## <a name="to-create-a-scope-tag"></a>Een bereiktag maken

1. Kies in Intune **rollen** > **bereik (Tags)** > **maken**.

    ![Schermafbeelding van een bereiktag maken.](./media/scope-tags/create-scope-tag.png)

2. Geef een **naam** en **beschrijving** op.
3. Kies **Maken**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Een bereiktag toewijzen aan een rol

1. Kies in Intune **rollen** > **alle rollen** > Kies een rol > **toewijzingen** > **toewijzen**.

    ![Schermopname van het bereik aan een rol toewijzen.](./media/scope-tags/assign-scope-to-role.png)

2. Geef een **opdrachtnaam** en **beschrijving**.
3. Kies **leden (groepen)** > **toevoegen** > Kies de groepen die u wilt gebruiken als onderdeel van deze toewijzing > **Selecteer**  >   **OK**. mUsers in deze groep hebben machtigingen voor het beheren van beleidsregels en profielen voor gebruikers/apparaten binnen het bereik (groepen).

    ![Schermopname van lidgroepen selecteren.](./media/scope-tags/select-member-groups.png)

4. Als u beheren van gebruikers/apparaten in een specifieke set van groepen wilt, kiest u **bereik (groepen)** > **groepen geselecteerd** > **Selecteer groepen om op te nemen**> Kies de groepen > **Selecteer** > **OK**. Alle gebruikers/apparaten in deze groep kunnen hebben hun profielen en beleidsregels die worden beheerd door de beheerders in de leden (groep).

    ![Schermopname van de optie bereikgroepen.](./media/scope-tags/select-scope-groups.png)

    U kunt ook **alle apparaten**, **alle gebruikers**, of **alle gebruikers en alle apparaten**.

    ![Schermafbeelding van de andere opties voor select bereikgroepen.](./media/scope-tags/scope-group-other-options.png)
    
5. Kies **bereik (Tags)** > **toevoegen** > Kies de labels die u wilt toevoegen aan deze rol > **Selecteer** > **OK**. Gebruikers in leden (groepen) hebben toegang tot de beleidsregels en profielen die ook hetzelfde bereik label hebben.

    ![Schermopname van bereiktags selecteren.](./media/scope-tags/select-scope-tags.png)

6. Kies **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Een bereiktag toevoegen aan een configuratieprofiel
1. Kies in Intune **apparaatconfiguratie** > **profielen** > een profiel kiezen.

    ![Schermopname van het profiel selecteren.](./media/scope-tags/choose-profile.png)

2. Kies **eigenschappen** > **bereik (Tags)** > **toevoegen**.

    ![Schermopname van het bereik-tags toevoegen.](./media/scope-tags/add-scope-tags.png)

3. Onder **labels selecteren**, kiest u de labels die u wilt toevoegen aan het profiel.
4. Kies **Selecteer** > **OK** > **opslaan**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Een bereiktag toewijzen aan een configuratiebeleid voor apps
Voor apparaten met **type apparaatregistratie** ingesteld op **beheerde apparaten**:
1. Kies **Client-apps** > **App-configuratiebeleid** > Kies een configuratiebeleid voor apps.
2. Kies **eigenschappen** > **bereik (Tags)** > Kies de labels die u wilt toewijzen aan het beleid.

Voor apparaten met **type apparaatregistratie** ingesteld op **beheerde apps**:
1. Kies **Client-apps** > **App-configuratiebeleid** > Kies een configuratiebeleid voor apps.
2. Kies **bereik (Tags)** > Kies de labels die u wilt toewijzen aan het beleid.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Een bereiktag toewijzen aan een iOS-app inrichtingsprofiel
1. Kies in Intune **Client-apps** > **inrichtingsprofielen voor iOS-Apps** > een profiel kiezen.
2. Kies **eigenschappen** > **bereik (Tags)** > Kies de labels die u wilt toewijzen aan het profiel.
3. Kies **Selecteer** > **OK** > **opslaan**.

## <a name="scope-tag-details"></a>Bereik label details
Wanneer u werkt met bereiktags, moet u deze gegevens:

- U kunt op dit moment bereiktags aan toewijzen:
    - Roltoewijzingen
    - Nalevingsbeleid voor apparaten
    - Apparaatconfiguratieprofielen
    - Windows 10-ringen updates
    - Beheerde apparaten
    - Apps
    - Het configuratiebeleid voor apps – beheerde apparaten
    - PowerShell-scripts
    - DEP-tokens
    - Inrichtingsprofiel voor iOS-apps
- Wanneer een beheerder een object in Intune maakt, worden alle bereiktags toegewezen aan die beheerder automatisch worden toegewezen aan het nieuwe object.
- Intune RBAC niet van toepassing op Azure Active Directory-rollen. Dus hebben de rollen Intune-Service-beheerders en globale beheerders volledige beheerderstoegang tot Intune, ongeacht welke bereiktags die ze hebben.
- Beheerders in een roltoewijzing met bereiktags ziet ook de Intune-objecten met geen bereiktags.
- U kunt alleen een bereiktag die u in uw roltoewijzingen hebt toewijzen.
- U kunt alleen de doelgroepen die worden vermeld in het bereik (groepen) van de roltoewijzing.
- Als u een bereiktag toegewezen voor uw rol hebt, kunt u alle bereiktags op een Intune-object niet verwijderen. Ten minste één bereiktag is vereist.

## <a name="next-steps"></a>Volgende stappen

Beheer uw [rollen](role-based-access-control.md) en [profielen](device-profile-assign.md).
