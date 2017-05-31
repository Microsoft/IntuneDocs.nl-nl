---
title: Skycure-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toevoegen | Microsoft Docs
description: Voeg Skycure-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toe in de klassieke Intune-console.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 47fd977d899c7f0763801b3bb86b515b727bc5aa
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a>Skycure-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid toevoegen

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U moet Intune gebruiken om de Skycure-apps toe te voegen en te implementeren. Eindgebruikers kunnen dan meldingen ontvangen wanneer op hun mobiele apparaten een bedreiging wordt vastgesteld en ze kunnen richtlijnen ontvangen om de bedreigingen te verhelpen.

Daarnaast moet u gebruikmaken van [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) zodat de identiteit van gebruikers kan worden gecontroleerd door Azure AD. U moet ook over het configuratiebeleid voor iOS-apps beschikken waarmee aan de iOS-app voor Skycure wordt gemeld dat Intune en de eenmalige aanmelding voor Azure AD moeten worden gebruikt zodat gebruikers niet elke keer dat ze zich bij de Skycure-app aanmelden de gebruikersnaam en het wachtwoord hoeven in te voeren.

## <a name="before-you-begin"></a>Voordat u begint

-   De onderstaande stappen moeten worden uitgevoerd in de [klassieke Intune-console](https://manage.microsoft.com/).

-   Gebruik hetzelfde Azure AD-account dat eerder is geconfigureerd in de Skycure-beheerconsole. Dit moet hetzelfde account zijn als het account waarmee is aangemeld bij de klassieke Intune-console.

-   Het Skycure-integratiebestand moet klaar zijn voor gebruik. Dit is het ZIP-bestand dat eerder in de Skycure-beheerconsole is gedownload en dat het bestand **skycure\_configuration.plist** bevat met de parameters voor het configuratiebeleid voor iOS-apps.

-   Zorg ervoor dat u bekend bent met de volgende procedures:

    -   [Een app toevoegen in Intune](/intune-classic/deploy-use/add-apps).

    -   [Een configuratiebeleid voor iOS-apps toevoegen in Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-the-skycure-app-for-android"></a>De Skycure-app voor Android toevoegen

1.  Kies in de klassieke Intune-console **Apps** &gt;**Apps toevoegen** om Microsoft Intune Software Publisher te starten en klik vervolgens op **Volgende**.

2.  Kies op de pagina **Setup van software** de optie **Externe koppeling** en plak vervolgens onder **De URL opgeven** de [URL voor de Skycure-app voor Android](https://play.google.com/store/apps/details?id=com.skycure.skycure).

    ![De URL opgeven in Microsoft Intune Software Publisher](../media/mtp/skycure-add-apps-1.png)

3.  Voer op de pagina **Beschrijving van software** de **uitgever**, **naam** en **beschrijving** in en selecteer de optie **Geef deze app weer als aanbevolen app en markeer deze in de bedrijfsportal** en klik vervolgens op **Volgende**.

    ![Beschrijving van de software in Microsoft Intune Software Publisher](../media/mtp/skycure-add-apps-2.png)

4.  Klik op **Uploaden** en vervolgens op **Sluiten**.

## <a name="to-add-the-skycure-app-for-ios"></a>De Skycure-app voor iOS toevoegen

1.  Kies in de klassieke Intune-console **Apps** &gt;**Apps toevoegen** om Microsoft Intune Software Publisher te starten en klik vervolgens op **Volgende**.

2.  Kies op de pagina **Setup van software** de optie **Beheerde iOS-app uit de App Store** en plak vervolgens onder **De URL opgeven** de [URL voor de Skycure-app voor iOS](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) .

    ![Beheerde iOS-app in Microsoft Intune Software Publisher](../media/mtp/skycure-add-apps-3.png)

3.  Voer op de pagina **Beschrijving van software** de **uitgever**, **naam** en **beschrijving** in en selecteer de optie **Geef deze app weer als aanbevolen app en markeer deze in de bedrijfsportal** en klik vervolgens op **Volgende**.

    ![Opties in Microsoft Intune Software Publisher](../media/mtp/skycure-add-apps-4.png)

4.  Selecteer op de pagina **Vereisten** de optie **Elk** onder **Type mobiel apparaat** en klik vervolgens op **Volgende**.

5.  Klik op **Uploaden** en vervolgens op **Sluiten**.

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a>De Microsoft Authenticator-app voor iOS toevoegen

1.  Kies in de klassieke Intune-console **Apps** &gt;**Apps toevoegen** om Microsoft Intune Software Publisher te starten en klik vervolgens op **Volgende**.

2.  Kies op de pagina **Setup van software** de optie **Beheerde iOS-app uit de App Store** en plak vervolgens onder **De URL opgeven** de [URL voor de Microsoft Authenticator-app voor iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) .

    ![Beheerde iOS-app in Microsoft Intune Software Publisher (2)](../media/mtp/skycure-add-apps-5.png)

3.  Voer op de pagina **Beschrijving van software** de **uitgever**, **naam** en **beschrijving** in en selecteer de optie **Geef deze app weer als aanbevolen app en markeer deze in de bedrijfsportal** en klik vervolgens op **Volgende**.

    ![Beheerde iOS-app in Microsoft Intune Software Publisher (3)](../media/mtp/skycure-add-apps-6.png)

4.  Selecteer op de pagina **Vereisten** de optie **Elk** onder **Type mobiel apparaat** en klik vervolgens op **Volgende**.

5.  Klik op **Uploaden** en vervolgens op **Sluiten**.

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a>Het configuratiebeleid voor de iOS-app voor Skycure toevoegen

1.  Kies in de klassieke Intune-console **Beleid** &gt; **Overzicht &gt; Beleid toevoegen**.

2.  Vouw in de lijst met beleidsregels **iOS** uit, kies **Configuratiebeleid voor mobiele apps (iOS 8.0 en hoger)** en kies vervolgens **Beleid maken**.

    ![Configuratiebeleid voor iOS-apps](../media/mtp/skycure-add-apps-7.png)

3.  Geef in de sectie **Algemeen** op de pagina **Beleid maken** een naam en optionele beschrijving op voor het configuratiebeleid voor iOS-apps.

    a.  Open met een teksteditor, zoals Kladblok, het bestand **skycure\_configuration.plist**, kopieer de inhoud en plak deze in de hoofdtekst van het **configuratiebeleid voor mobiele apps**, kies **Valideren** en vervolgens **Beleid opslaan**.

       ![Configuratiebeleid voor iOS-apps (2)](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a>Volgende stappen

[Skycure-apps, de Microsoft Authenticator-app en het configuratiebeleid voor iOS-apps implementeren](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

