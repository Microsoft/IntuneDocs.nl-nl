---
title: 'Snelstart: een gebruiker maken in Intune'
description: 'Snelstart: een gebruiker maken in Intune.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 01/17/2020
ms.author: erikje
ms.manager: dougeby
ms.assetid: 820fcb18-0927-4ebd-be79-dce92b51c261
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6aa57b71e052e3fc8566fcdff8bdd9ef5d1c39e
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754487"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-the-user-a-license"></a>Quickstart: Een gebruiker maken in Intune en een licentie toewijzen aan de gebruiker

In deze quickstart maakt u een gebruiker en wijst u vervolgens een Intune-licentie toe aan de gebruiker. Als u Intune gebruikt, moet elke persoon die u toegang wilt bieden tot de bedrijfsgegevens over een eigen gebruikersaccount beschikken. Intune-beheerders kunnen gebruikers later configureren om de toegang te beheren.

## <a name="prerequisites"></a>Vereisten

- Een Microsoft Intune-abonnement. [Aanmelden voor een gratis proefaccount](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune-in-microsoft-endpoint-manager"></a>Aanmelden bij Intune in Microsoft Endpoint Manager

Meld u bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431) aan als een [globale beheerder of een Intune-serviceondersteuningsbeheerder](users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-a-user"></a>Een gebruiker maken

Een gebruiker moet beschikken over een gebruikersaccount om zich te kunnen inschrijven voor Intune-apparaatbeheer. Ga als volgt te werk om een nieuwe gebruiker te maken:

1. Selecteer in Microsoft Endpoint Manager **Gebruikers** > **Alle gebruikers** >**Nieuwe gebruiker**:  ![selecteer in Microsoft Endpoint Manager Nieuwe gebruiker](./media/quickstart-create-user/create-user.png)
2. Voer in het vak **Naam** een naam in, bijvoorbeeld *Dewey Kellum*:  ![Gebruikersgegevens toevoegen](./media/quickstart-create-user/create-user-02.png)
3. Voer in het vak **Gebruikersnaam** een gebruikers-id in, bijvoorbeeld Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Als u de klantdomeinnaam nog niet hebt geconfigureerd, gebruikt u de geverifieerde domeinnaam die u hebt gebruikt voor het maken van het Intune-abonnement (of de [gratis proefversie](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Selecteer **Wachtwoord weergeven** en onthoud het automatisch gegenereerde wachtwoord zodat u zich kunt aanmelden bij een testapparaat.
5. Selecteer **Maken**.

## <a name="assign-a-license-to-the-user"></a>Een licentie toewijzen aan de gebruiker

Nadat u een gebruiker hebt gemaakt, moet u het [Microsoft 365-beheercentrum](https://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om een Intune-licentie aan de gebruiker toe te wijzen. Als u geen licentie aan de gebruiker toewijst, kan de gebruiker het apparaat niet registreren in Intune.

Ga als volgt te werk om een Intune-licentie aan een gebruiker toe te wijzen:

1. Meld u aan bij het [Microsoft 365-beheercentrum](https://go.microsoft.com/fwlink/p/?LinkId=698854) met dezelfde referenties die u hebt gebruikt om u aan te melden bij Intune.
2. Selecteer **Gebruikers** > **Actieve gebruikers**, en selecteer vervolgens de gebruiker die u zojuist hebt gemaakt.
3. Selecteer het tabblad **Licenties en apps**.
4. Selecteer onder **Locatie selecteren**een locatie voor de gebruiker, als deze nog niet is ingesteld.
2. Schakel het selectievakje **Intune** in het gedeelte **Licenties** in. Als een andere licentie Intune bevat, kunt u die licentie selecteren. De weergegeven [productnaam](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference) wordt gebruikt als het serviceabonnement in Azure Management.

    ![De locatie en Intune-licentie selecteren](./media/quickstart-create-user/create-user-03.png)

   > [!NOTE]
   > Via deze instelling wordt een van uw licenties gebruikt voor de gebruiker. Als u een evaluatieomgeving gebruikt, wijst u deze licentie later opnieuw toe aan een echte gebruiker in een productieomgeving.

6. Selecteer **Wijzigingen opslaan**.

Voor de nieuwe actieve Intune-gebruiker wordt nu weergegeven dat deze een **Intune**-licentie gebruikt.

## <a name="clean-up-resources"></a>Resources opschonen

Als u deze gebruiker niet meer nodig hebt, kunt u de gebruiker verwijderen door naar het [Microsoft 365-beheercentrum](https://go.microsoft.com/fwlink/p/?LinkId=698854) te gaan en **Gebruikers** > *de gebruiker* > *het pictogram Gebruiker verwijderen* > **Gebruiker verwijderen** > **Sluiten** te selecteren.

   ![Selecteer het pictogram Verwijderen](./media/quickstart-create-user/create-user-04.png)

## <a name="next-steps"></a>Volgende stappen

In deze quickstart hebt u een gebruiker gemaakt en een Intune-licentie aan deze gebruiker toegewezen. Zie [Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen](users-add.md) voor meer informatie over het toevoegen van gebruikers aan Intune.

Als u deze reeks quickstarts voor Intune wilt volgen, kunt u doorgaan met de volgende quickstart:

> [!div class="nextstepaction"]
> [Quickstart: Een groep maken om gebruikers te beheren](../quickstart-create-group.md)
