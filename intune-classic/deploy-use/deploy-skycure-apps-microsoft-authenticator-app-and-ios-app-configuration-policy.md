---
title: Skycure-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid implementeren | Microsoft Docs
description: Implementeer Skycure-apps, de Microsoft Authenticator-app en het iOS-configuratiebeleid in de klassieke Intune-console.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 19c8ca7bbfe19649585d63ce2c0c96a8f57b3739
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy"></a>Skycure-apps, de Microsoft Authenticator-app en het configuratiebeleid voor iOS-apps implementeren

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="before-you-begin"></a>Voordat u begint

-   De onderstaande stappen moeten worden uitgevoerd in de [klassieke Intune-console](https://manage.microsoft.com/).

-   Gebruik hetzelfde Azure AD-account dat eerder is geconfigureerd in de Skycure-beheerconsole. Dit moet hetzelfde account zijn als het account waarmee is aangemeld bij de klassieke Intune-console.

-   Zorg ervoor dat u bekend bent met de volgende procedures:

    -   [Het implementeren van een app met Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).

    -   [Het implementeren van een configuratiebeleid voor iOS-apps](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy"></a>Skycure-apps, de Microsoft Authenticator-app en het configuratiebeleid voor iOS-apps implementeren

1.  Kies in de klassieke Intune-console **Apps** &gt; **Apps** om de lijst met apps weer te geven die u kunt beheren.

2.  Selecteer de volgende apps:

    a.  Microsoft Authenticator

    b.  De Skycure-app voor Android

    c.  De Skycure-app voor iOS

       ![Alle apps die worden geïmplementeerd in de klassieke Intune-console](../media/mtp/skycure-deploy-app-1.png)

3.  Kies **Implementaties beheren**, selecteer de Azure AD-beveiligingsgroep met de Skycure-gebruikers en klik vervolgens op **Volgende**.

4.  Selecteer op de pagina **Implementatiebewerking** de optie **Vereiste installatie** in de vervolgkeuzelijst **Goedkeuring** en klik vervolgens op **Volgende**.

    ![Implementatiebewerking in de klassieke Intune-console](../media/mtp/skycure-deploy-app-2.png)

5.  Selecteer op de pagina **VPN-profiel** de optie **Geen** in de vervolgkeuzelijst **VPN-beleid** en klik vervolgens op **Volgende**.

6.  Selecteer op de pagina **Configuratie van mobiele apps** het eerder gemaakte configuratiebeleid voor iOS-apps in de vervolgkeuzelijst **Configuratiebeleid voor apps** en klik vervolgens op **Voltooien**.

    ![De configuratie van mobiele apps in de klassieke Intune-console](../media/mtp/skycure-deploy-app-3.png)

## <a name="next-steps"></a>Volgende stappen

[De integratie van Skycure met Intune instellen](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

