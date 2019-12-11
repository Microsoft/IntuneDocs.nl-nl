---
title: 'Snelstart: een gebruiker maken in Intune'
description: 'Snelstart: een gebruiker maken in Intune.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/25/2019
ms.author: erikje
ms.manager: dougeby
ms.assetid: 820fcb18-0927-4ebd-be79-dce92b51c261
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 75a875fc3ff11eb1e3befad425c16a710544f781
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72509874"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Quickstart: Een gebruiker maken in Intune en er een licentie aan toewijzen

In deze quickstart maakt u een gebruiker en wijst u er vervolgens een Intune-licentie aan toe. Als u Intune gebruikt, moet elke persoon die u toegang wilt bieden tot de bedrijfsgegevens, beschikken over een eigen gebruikersaccount. Intune-beheerders kunnen gebruikers later configureren om de toegang te beheren.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als [globale beheerder of beheerder van een Intune-service](users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-a-user"></a>Een gebruiker maken

Gebruikers moeten beschikken over een gebruikersaccount om zich te kunnen inschrijven voor Intune-apparaatbeheer. Ga als volgt te werk om een nieuwe gebruiker te maken:

1. Kies in Intune **Gebruikers** > **Alle gebruikers** > **Nieuwe gebruiker**.
![Browser](./media/quickstart-create-user/create-user.png)
2. Voer in het vak **Naam** een naam in, bijvoorbeeld *Dewey Kellum*.
3. Voer in het vak **Gebruikersnaam** een gebruikers-id in, bijvoorbeeld Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Als u de klantdomeinnaam nog niet hebt geconfigureerd, gebruikt u de geverifieerde domeinnaam die u hebt gebruikt voor het maken van het Intune-abonnement (of de [gratis proefversie](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Kies **Wachtwoord weergeven** en noteer het automatisch gegenereerde wachtwoord zodat u zich kunt aanmelden bij een testapparaat.
5. Kies **Maken**.

## <a name="assign-a-license-to-the-user"></a>Een licentie toewijzen aan de gebruiker

Nadat u een gebruiker hebt gemaakt, moet u het [Microsoft 365-beheercentrum](http://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om een Intune-licentie aan die gebruiker toe te wijzen. Als u geen licentie aan de gebruiker toewijst, kan de gebruiker het apparaat niet registreren in Intune. 

Ga als volgt te werk om een Intune-licentie aan een gebruiker toe te wijzen:

1. Meld u aan bij het [Microsoft 365-beheercentrum](http://go.microsoft.com/fwlink/p/?LinkId=698854) met dezelfde referenties die u hebt gebruikt om u aan te melden bij Intune.
2. Kies **Gebruikers** > **Actieve gebruikers** > en selecteer de gebruiker die u zojuist hebt gemaakt.
3. Selecteer naast **Productlicenties** de optie **Bewerken**.
4. Bij **Locatie** kiest u een locatie voor de gebruiker.
5. Klik op **Aan** naast de Intune-licentie (of een andere licentie waarin Intune is inbegrepen). De weergegeven [productnaam](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** wordt gebruikt als het serviceabonnement in Azure Management 

   > [!NOTE]
   > Via deze instelling wordt nu een van uw licenties gebruikt voor deze gebruiker. Als u een evaluatieomgeving gebruikt, wijst u deze licentie later toe aan een echte gebruiker in een productieomgeving.
6. Kies **Opslaan** > **Sluiten**.

Voor de nieuwe actieve Intune-gebruiker wordt nu weergegeven dat deze een **Intune**-licentie gebruikt.

## <a name="clean-up-resources"></a>Resources opschonen

Als u deze gebruiker niet meer nodig hebt, kunt u deze verwijderen door te navigeren naar het [Microsoft 365-beheercentrum](http://go.microsoft.com/fwlink/p/?LinkId=698854). Hier kiest u **Gebruikers** > **Actieve gebruikers** > *kies de gebruiker in de lijst* > **Gebruiker verwijderen** > **Gebruiker verwijderen** > **Wijzigingen bevestigen** > **Sluiten**.

## <a name="next-steps"></a>Volgende stappen

In deze quickstart hebt u een gebruiker gemaakt en een Intune-licentie aan deze gebruiker toegewezen. Zie [Gebruikers toevoegen en beheerdersmachtigingen aan Intune toekennen](users-add.md) voor meer informatie over het toevoegen van gebruikers aan Intune.

Als u deze reeks snelstartgidsen voor Intune wilt volgen, kunt u doorgaan met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Quickstart: Een groep maken om gebruikers te beheren](../quickstart-create-group.md)
