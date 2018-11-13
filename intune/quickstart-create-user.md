---
title: 'Snelstart: een gebruiker maken in Intune'
description: 'Snelstart: een gebruiker maken in Intune.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 10/30/2018
ms.author: erikje
ms.openlocfilehash: fb88f703048eaa122bb406d8adb1fc9face764c4
ms.sourcegitcommit: 9d08545727543b434dd270371fa50233470f2bce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50410749"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Snelstart: een gebruiker maken en er een licentie aan toewijzen

In deze snelstart maakt u een gebruiker en wijst u daarna een licentie toe aan die gebruiker. Als u Intune gebruikt, moet elke persoon die u toegang wilt bieden tot de bedrijfsgegevens beschikken over een gebruikersaccount. Intune-beheerders kunnen die gebruikers later configureren om de toegang te beheren.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als [globale beheerder of Intune-servicebeheerder](users-add.md#types-of-administrators). Als u een Intune-proefabonnement hebt gemaakt, is het account waarmee u het abonnement hebt gemaakt de globale beheerder.

## <a name="create-a-user"></a>Een gebruiker maken

Mensen moeten beschikken over een gebruikersaccount om zich te kunnen inschrijven voor Intune-apparaatbeheer.

1. Kies in Intune **Gebruikers** > **Alle gebruikers** > **Nieuwe gebruiker**.
![Browser](media/quickstart-create-user/create-user.png)
2. Voer in het vak **Naam** een naam in, bijvoorbeeld *Dewey Kellum*.
3. Voer in het vak **Gebruikersnaam** een gebruikers-id in, bijvoorbeeld Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Als u de klantdomeinnaam nog niet hebt geconfigureerd, gebruikt u de geverifieerde domeinnaam die u hebt gebruikt voor het maken van het Intune-abonnement (of de [gratis proefversie](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Kies **Wachtwoord weergeven** en noteer het automatisch gegenereerde wachtwoord zodat u zich kunt aanmelden bij een testapparaat.
5. Kies **Maken**.

## <a name="assign-a-license-to-the-user"></a>Een licentie toewijzen aan de gebruiker

Nadat u een gebruiker hebt gemaakt, moet u de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om een Intune-licentie toe te wijzen aan die gebruiker. Zonder een licentie kan het apparaat van de gebruiker namelijk niet worden ingeschreven bij Intune. 

1. Meld u aan bij de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) met dezelfde referenties die u hebt gebruikt om u aan te melden bij Intune.
2. Kies **Gebruikers** > **Actieve gebruikers** > kies de gebruiker die u zojuist hebt gemaakt.
3. Selecteer naast **Productlicenties** de optie **Bewerken**.
4. Bij **Locatie** kiest u een locatie voor de gebruiker.
5. Klik op **Aan** naast de Intune-licentie (of een andere licentie waarin Intune is inbegrepen). De weergegeven [productnaam](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** wordt gebruikt als het serviceabonnement in Azure Management 

   > [!NOTE]
   > Via deze instelling wordt nu een van uw licenties gebruikt voor deze gebruiker. Als u een evaluatieomgeving gebruikt, wijst u deze licentie later toe aan een echte gebruiker in een productieomgeving.
6. Kies **Opslaan** > **Sluiten**.

Voor de nieuwe actieve Intune-gebruiker wordt nu weergegeven dat deze een **Intune**-licentie gebruikt.

## <a name="clean-up-resources"></a>Resources opschonen

Als u deze gebruiker niet meer nodig hebt, kunt u deze verwijderen door te navigeren naar [Office 365 Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854). Hier kiest u **Gebruikers** > **Actieve gebruikers** > *kies de gebruiker in de lijst* > **Gebruiker verwijderen** > **Gebruiker verwijderen** > **Wijzigingen bevestigen** > **Sluiten**.

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u een gebruiker gemaakt en een licentie toegewezen aan deze gebruiker. U kunt de gebruiker nu toewijzen aan een groep.

> [!div class="nextstepaction"]
> [Een groep maken](quickstart-create-group.md)
