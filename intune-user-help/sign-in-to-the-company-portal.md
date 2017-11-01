---
title: Aanmelden bij de bedrijfsportal-app | Microsoft Docs
description: Ontdek hoe u zich kunt aanmelden bij de bedrijfsportal-app op meerdere platformen.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: caea74745dc58a04c60e780727b318ebdb8ff235
ms.sourcegitcommit: b8d3f8da6d8c2bd5d6140d538193a02d5875aefb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2017
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>Hoe meld ik me aan bij de bedrijfsportal-app? <!--User Story 1132123-->

U gebruikt de bedrijfsportal-app om toegang te verkrijgen tot uw bedrijfsresources, zoals e-mail en zakelijke apps. Er zijn in principe twee manieren waarop u zich kunt aanmelden bij de bedrijfsportal:

* Met het e-mailadres van uw werk en het bijbehorende wachtwoord
* Aanmelden vanaf een ander apparaat

Hoewel de volgende afbeeldingen afkomstig zijn uit iOS, is het proces vrijwel identiek voor Android- en Windows-apparaten.

## <a name="signing-in-with-your-email-address-and-password"></a>Aanmelden met uw e-mailadres en wachtwoord

1. Open de bedrijfsportal-app op uw apparaat en tik op **Aanmelden**.

  ![De aanmeldingspagina van de bedrijfsportal met een pictogram van een persoon voor een grafische weergave van een website. Hieronder staat de knop Aanmelden. Een koppeling onder aan de pagina leidt naar informatie over privacy en cookies van Microsoft.](/intune/media/cp_ios_aad_signin_after_1704_001.png)

  Hebt u de bedrijfsportal-app nog niet? U vindt hier informatie over het installeren en downloaden van de app voor [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) of [Android](install-the-company-portal-app-android.md).

2. Voer uw **werk- of schoolaccount** in.

  ![De gebruiker wordt gevraagd alleen een e-mailadres in te voeren in plaats van het e-mailadres en wachtwoord op hetzelfde scherm.](/intune/media/cp_ios_aad_signin_after_1704_002.png)

3. Wacht even totdat uw e-mailadres is geaccepteerd en voer vervolgens uw wachtwoord in.

  ![De gebruiker wordt gevraagd om het wachtwoord nadat het e-mailadres is geaccepteerd.](/intune/media/cp_ios_aad_signin_after_1704_003.png)

4. Zodra de bedrijfsportal uw aanmelding heeft geaccepteerd, wordt u aangemeld en hebt u toegang tot de bedrijfsresources.   

  ![Nadat het verificatieproces is doorlopen, wordt er aangemeld met de bedrijfsportal-app. Hierbij wordt een laadbalk weergegeven.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

## <a name="signing-in-with-certificate-based-authentication"></a>Aanmelden met verificatie op basis van certificaten

1.  Open de bedrijfsportal-app op uw apparaat.

2.  Voer uw **werk- of schoolaccount** in.

3.  Tik op de koppeling **Aanmelden met een certificaat**.

4.  Tik op **Doorgaan** om het certificaat te gebruiken.

## <a name="signing-in-from-another-device"></a>Aanmelden vanaf een ander apparaat

Als u geen wachtwoord hoeft op te geven om u aan te melden bij uw bedrijfsresources, kunt u een ander apparaat gebruiken om te bevestigen dat u de juiste persoon bent met de juiste toegangsniveaus. Als in uw bedrijf smartcards worden gebruikt om toegang te verkrijgen tot computers, is de kans groot dat u zich met behulp van een ander apparaat moet aanmelden.

1. In plaats van uw e-mailadres in te voeren, selecteert u de koppeling **Aanmelden vanaf een ander apparaat** onder het invoervak voor het e-mailadres.

  ![De aanmeldingspagina van de bedrijfsportal met een pictogram van een persoon voor een grafische weergave van een website. Hieronder staat de knop Aanmelden. Een koppeling onder aan de pagina leidt naar informatie over privacy en cookies van Microsoft.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_001.png)

2. U ontvangt een unieke, eenmalige code om u aan te melden bij de bedrijfsportal.

  ![U vindt hier instructies om naar de pagina aka.ms/devicelogin te gaan met een unieke wachtwoordcode vanaf uw werkcomputer en de code te gebruiken om u aan te melden.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_003.png)

3. Open op het andere apparaat een browser en ga naar [https://aka.ms/devicelogin](https://aka.ms/devicelogin) om de code in te voeren.

  ![Een afbeelding van de browser van de gebruiker op de werkcomputer in plaats van de bedrijfsportal-app. Op de weergegeven pagina Apparaataanmelding wordt de gebruiker gevraagd om de code in de bedrijfsportal-app is ontvangen.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Als de code is gecontroleerd op de pagina **Apparaataanmelding**, selecteert u __Doorgaan__ om via de bedrijfsportal te worden aangemeld op uw andere apparaat.

  ![De gebruiker heeft de unieke code ingevoerd in het veld en op de site Apparaataanmelding is gevraagd om te bevestigen dat de Intune bedrijfsportal-app de juiste app is om autorisatie te ontvangen voor aanmelding.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Zodra de code is geverifieerd, kunt u het venster sluiten.

  ![Een bevestigingspagina met de mededeling dat de gebruiker nu is aangemeld bij de bedrijfsportal-app op hun apparaat en dat deze pagina kan worden gesloten.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Op het oorspronkelijke apparaat wordt het aanmeldingsproces gestart via de bedrijfsportal-app.

  ![Nadat het verificatieproces is doorlopen, wordt u aangemeld via de bedrijfsportal-app. Dit proces wordt aangegeven met een voortgangsbalk.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_007.png)

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Ga naar de [bedrijfsportalwebsite](https://portal.manage.microsoft.com) voor de betreffende contactgegevens.
