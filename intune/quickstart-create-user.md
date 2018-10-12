---
title: 'Snelstart: een gebruiker maken in Intune'
description: 'Snelstart: een gebruiker maken in Intune.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 6a1d591e635dccd99551d9b8d40e099724a85d77
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581589"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Snelstart: een gebruiker maken en er een licentie aan toewijzen

In deze snelstart maakt u een gebruiker en daarna wijst u er een licentie aan toe. Als u Intune gebruikt, moet elke persoon die u toegang wilt bieden tot de bedrijfsgegevens beschikken over een gebruikersaccount. Intune-beheerders kunnen die gebruikers vervolgens configureren om de toegang te beheren.

Als u niet over een Intune-abonnement beschikt, kunt u [zich registreren voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service.

## <a name="create-a-user"></a>Een gebruiker maken

Mensen moeten beschikken over een gebruikersaccount om zich te kunnen inschrijven voor Intune-apparaatbeheer.

1. Kies in Intune **Gebruikers** > **Alle gebruikers** > **Nieuwe gebruiker**.
![Browser](media/quickstart-create-user/create-user.png)
2. Voer in het vak **Naam** *Dewey Kellum* in.
3. Voer in het vak **Gebruikersnaam** *Dewey@contoso.onmicrosoft.com* in.
4. Kies **Groepen** > **Iedereen** > **Selecteren**.
5. Kies **Wachtwoord weergeven** en noteer het automatisch gegenereerde wachtwoord zodat u zich kunt aanmelden bij een testapparaat.
6. Kies **Maken**.

## <a name="assign-a-license-to-the-user"></a>Een licentie toewijzen aan de gebruiker

Nadat u een gebruiker hebt gemaakt, moet u de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om een Intune-licentie toe te wijzen aan die gebruiker. Zonder een licentie kan het apparaat van de gebruiker namelijk niet worden ingeschreven bij Intune. 

1. Meld u aan bij de [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) met dezelfde referenties die u hebt gebruikt om u aan te melden bij Intune.
2. Kies **Gebruikers** > **Actieve gebruikers** > kies de gebruiker die u zojuist hebt gemaakt.
3. Bij **Locatie** kiest u een locatie voor de gebruiker.
3. Kies **Productlicenties** en stel **Enterprise Mobility + Security E3** (of een andere licentie die u hebt waarbij Intune is inbegrepen) in op **Aan**.
   > [!NOTE]
   > Er wordt nu een van uw licenties gebruikt voor deze gebruiker. Als u de productieomgeving gebruikt, kunt u de toewijzing van deze licentie later uitschakelen om de licentie te gebruiken voor een echte gebruiker.
5. Kies **Opslaan**.

## <a name="clean-up-resources"></a>Resources opschonen

Als u de gebruiker niet meer nodig hebt, kunt u deze verwijderen via **Gebruikers** > **Alle gebruikers** > kies de gebruiker in de lijst > **Gebruiker verwijderen** > **Ja**.

## <a name="next-steps"></a>Volgende stappen

In deze snelstart hebt u een gebruiker gemaakt en er een licentie aan toegewezen. U kunt de gebruiker nu toewijzen aan een groep.

> [!div class="nextstepaction"]
> [Een groep maken](quickstart-create-group.md)
