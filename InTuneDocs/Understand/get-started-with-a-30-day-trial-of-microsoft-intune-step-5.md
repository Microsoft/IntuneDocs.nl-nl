---
title: Mobiele apparaten inschrijven voor de evaluatieversie | Microsoft Intune
description: Zo kunt u mobiele apparaten inschrijven en een app installeren wanneer u zich aanmeldt voor een gratis evaluatieversie van Intune van 30 dagen
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47806f69-303d-41d9-9b0e-9b9445ea24ac
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 60ee39a7eeeb9068a7350ec87f60e7148ccb7826
ms.openlocfilehash: d441bb68a28a18cf45c616271cb33556df9f67f3


---

# Mobiele apparaten inschrijven voor de evaluatieversie
Als u het beheer van mobiele apparaten met Intune wilt instellen, moet u eerst de instantie voor het beheer van mobiele apparaten instellen, beheer voor apparaatplatforms inschakelen en vervolgens uw apparaten inschrijven met de bedrijfsportal-app. Vervolgens kunt u de Microsoft Skype-toepassing implementeren die u hebt gepubliceerd.

## De service voor apparaatbeheer voorbereiden

1.  **Intune als de  instantie voor het beheer van mobiele apparaten instellen**

    Kies in de [Intune-beheerconsole](https://manage.microsoft.com/) **Beheer** &gt; **Mobile Device Management**. Kies **Taken** > **MDM-instantie instellen**. Kies vervolgens **Ja** in het dialoogvenster **MDM-instantie**.

2.  **MDM inschakelen voor uw apparaatplatform**

    Schakel beheer van mobiele apparaten in voor het apparaatplatform dat u wilt beheren. Afhankelijk van uw platform zijn er andere vereisten van toepassing:

    -   **iOS en Mac OS X**: zie [iOS- en Mac-beheer instellen met Microsoft Intune](/Intune/Deploy-Use/set-up-ios-and-mac-management-with-microsoft-intune).

    -   **Android**: op mobiele apparaten met Android kunnen gebruikers zich inschrijven via de bedrijfsportal-app, die beschikbaar is via Google Play. Er is geen aanvullende configuratie in Intune vereist.

    -   **Windows Phone**: zie [Windows Phone-beheer instellen met Microsoft Intune](/Intune/Deploy-Use/set-up-windows-phone-management-with-microsoft-intune).

## Testapparaten inschrijven

### iOS en Mac OS X
Installeer de app **Microsoft Intune-bedrijfsportal** van Microsoft Corporation die u kunt vinden in de App Store en meld u aan met de Intune-gebruikersreferenties die hierboven worden vermeld. Geef **Ingeschreven apparaten** weer om uw apparaat toe te voegen.

### Android
Installeer de app **Intune-bedrijfsportal** van Microsoft Corporation die u kunt vinden op [Google Play](http://go.microsoft.com/fwlink/p/?LinkId=386612) en meld u aan met de Intune-gebruikersreferenties die hierboven worden vermeld.

### Windows Phone 8,1
Gebruikers installeren de app **Bedrijfsportal** van Microsoft Corporation die te vinden is in de Windows Phone Store en melden zich aan met de Intune-gebruikersreferenties die hierboven worden vermeld.  Geef **Ingeschreven apparaten** weer om uw apparaat toe te voegen.

 ### Windows Phone 8.0
 Gebruikers klikken op **Systeeminstellingen** &gt; **Bedrijfsapps** en melden zich aan met de Intune-gebruikersreferenties die hierboven worden vermeld. De bedrijfsportal-app wordt op uw telefoon geïmplementeerd.

Als u wordt gevraagd om een **serveradres**op te geven, voert u ‘manage.microsoft.com’ in.


## De eerder geïmplementeerde app installeren
Open de bedrijfsportal op het mobiele apparaat, kies **Apps** en installeer vervolgens **Microsoft Skype**.

Zie [Bereid u voor op het registreren van apparaten in Microsoft Intune](/Intune/deploy-use/get-ready-to-enroll-devices-in-microsoft-intune) voor meer informatie over het beheer van mobiele apparaten met Intune.

### Volgende stappen
Gefeliciteerd! U hebt zojuist stap 5 van de procedure voor de *Microsoft Intune-evaluatie* voltooid.

>[!div class="step-by-step"]

>[&larr; **Beleid maken**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)     [**Opties en extra's** &rarr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)  



<!--HONumber=Jul16_HO4-->


