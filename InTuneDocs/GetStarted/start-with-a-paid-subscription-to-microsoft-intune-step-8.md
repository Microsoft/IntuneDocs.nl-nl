---
title: Mobiele apparaten inschrijven en een app installeren | Microsoft Intune
description: Bevat uitleg over het inschrijven van mobiele apparaten en het installeren van een app op een apparaat dat voor Intune is ingeschreven
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3306d772b074ddcfd1bfcf7178b32f9b371321e7
ms.openlocfilehash: f57728bb41b750f53b021bed532de18187e764a0


---

# Mobiele apparaten inschrijven en een app installeren
Als u het beheer van mobiele apparaten met Intune wilt instellen, moet u eerst de instantie voor het beheer van mobiele apparaten instellen, beheer voor apparaatplatforms inschakelen en vervolgens uw apparaten inschrijven met de bedrijfsportal-app. Vervolgens kunt u de Microsoft Skype-toepassing implementeren die u in stap 6 hebt gepubliceerd.

## Apparaatbeheer inschakelen en apparaten inschrijven

1.  **Intune als de instantie voor het beheer van mobiele apparaten instellen** Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Beheer** > **Beheer van mobiele apparaten** en kies vervolgens **MDM-instantie instellen** onder **Taken**.  Klik in het dialoogvenster MDM-instantie op **Ja**.
    ![Beheerconsole. MDM instellen op Intune](./media/mdmAuthority.png)

2.  **MDM inschakelen voor uw apparaatplatform** Schakel beheer van mobiele apparaten in voor het apparaatplatform dat u wilt beheren. Afhankelijk van uw platform zijn er andere vereisten van toepassing:

    -   **iOS en Mac OS X**: zie [iOS- en Mac-beheer instellen met Microsoft Intune](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Windows Phone**: zie [Windows Phone-beheer instellen met Microsoft Intune](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune).

    -   **Android**: op mobiele apparaten met Android kunnen gebruikers zich inschrijven via de bedrijfsportal-app, die beschikbaar is via [Google Play](https://play.google.com/store/apps/details?id=com.skype.raider). Er is geen aanvullende configuratie in Intune vereist.

3.  **Apparaten inschrijven**:

    -   **Android** installeer de app **Intune-bedrijfsportal** van Microsoft Corporation via [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) en meld u aan met de Intune-gebruikersreferenties die hierboven staan vermeld.

    -   **iOS en Mac OS X**: installeer de app **Microsoft Intune-bedrijfsportal** van Microsoft Corporation via de App Store en meld u aan met de Intune-gebruikersreferenties die hierboven staan vermeld. Geef **Ingeschreven apparaten** weer om uw apparaat toe te voegen.

    -   **Windows Phone 8.1**: gebruikers installeren de app **Bedrijfsportal** van Microsoft Corporation via de Windows Phone Store en melden zich aan met de Intune-gebruikersreferenties die hierboven staan vermeld.  Geef **Ingeschreven apparaten** weer om uw apparaat toe te voegen.

    -   **Windows Phone 8.0**: gebruikers kiezen **Systeeminstellingen** &gt; **Bedrijfsapps** en melden zich aan met de Intune-gebruikersreferenties die hierboven staan vermeld. De bedrijfsportal-app wordt op uw telefoon geïmplementeerd.

    Als u wordt gevraagd om een **serveradres**op te geven, voert u ‘manage.microsoft.com’ in.

## Een app installeren op een ingeschreven apparaat
In [stap 6](start-with-a-paid-subscription-to-microsoft-intune-step-6.md) van deze snelstartgids hebt u de Skype-app gepubliceerd naar uw aangepaste Intune-gebruikersgroep. Nu gaat u die app installeren op een apparaat dat zojuist is ingeschreven.

Open de bedrijfsportal op het ingeschreven mobiele apparaat, kies **Apps** en installeer **Microsoft Skype**.

Zie [Prerequisites for enrolling devices in Microsoft Intune](/intune/deploy-use/prerequisites-for-enrollment) (Vereisten voor het registreren van apparaten in Microsoft Intune) voor meer informatie over het beheer van mobiele apparaten met [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].


### Volgende stappen
Gefeliciteerd. U hebt zojuist de laatste stap van de *Snelstartgids voor Intune* voltooid. Nu de eerste configuratie is voltooid, kunt u overwegen om aanvullende MDM-functionaliteit in te schakelen.

>[!div class="step-by-step"]

>[&larr; **Apparaten inschrijven**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Taken na configuratie** &rarr;](.\post-configuration-tasks.md)  



<!--HONumber=Oct16_HO3-->


