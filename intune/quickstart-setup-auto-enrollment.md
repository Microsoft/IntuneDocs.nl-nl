---
title: 'Snelstartgids: automatische inschrijving in Intune instellen'
description: 'Snelstartgids: automatische inschrijving voor Windows 10-apparaten in Intune instellen.'
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 3b713f090fb6ada884a269e286f55f6e1b1087c4
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581576"
---
# <a name="quickstart-set-up-automatic-enrollment-for-windows-10-devices"></a>Snelstartgids: automatische inschrijving voor Windows 10-apparaten instellen

In deze snelstartgids stelt u Microsoft Intune zo in dat apparaten automatisch worden ingeschreven wanneer bepaalde gebruikers zich aanmelden bij Windows 10-apparaten.

Als u niet over een Intune-abonnement beschikt, kunt u [zich aanmelden voor een gratis proefaccount](free-trial-sign-up.md).

## <a name="prerequisites"></a>Vereisten

- Als u de stappen in deze snelstartgids wilt uitvoeren, moet u eerst [een gebruiker maken](quickstart-create-user.md) en [een groep maken](quickstart-create-group.md).

## <a name="sign-in-to-intune"></a>Aanmelden bij Intune

Meld u aan bij [Intune](https://aka.ms/intuneportal) als globale beheerder of beheerder van een Intune-service.

## <a name="set-up-windows-10-automatic-enrollment"></a>Automatische inschrijving voor Windows 10 instellen

Voor dit voorbeeld gebruikt u MDM-inschrijving, zodat zowel bedrijfsapparaten als Bring Your Own-apparaten automatisch kunnen worden ingeschreven.

1. Kies in Azure **Azure Active Directory** > **Mobiliteit (MDM en MAM)** > **Microsoft Intune** >  **Sommige**.
![Browser](media/quickstart-setup-auto-enrollment/setup-automatic-enrollment-win10.png)
2. Kies **Groepen selecteren** > **Contoso-testers** > **Selecteren**.
3. Gebruik de standaardwaarden voor de volgende URL's:
    - URL voor MDM-gebruiksvoorwaarden
    - URL voor MDM-detectie
    - URL voor MDM-naleving
4. Kies **Opslaan**.
5. Meld u aan als gebruiker in de groep op een Windows 10-apparaat en volg de aanwijzingen.

## <a name="clean-up-resources"></a>Resources opschonen

Bekijk [Inschrijving voor Windows-apparaten instellen](windows-enroll.md) als u de automatische inschrijving bij Intune opnieuw wilt configureren.

## <a name="next-steps"></a>Volgende stappen

In deze snelstartgids hebt u geleerd om de automatische inschrijving voor Windows 10-apparaten in te stellen. U kunt meer lezen over andere manieren om apparaten voor alle platformen in te schrijven.

> [!div class="nextstepaction"]
> [Artikel 'Wat is apparaatinschrijving?'](device-enrollment.md)