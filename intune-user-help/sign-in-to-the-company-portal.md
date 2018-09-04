---
title: Aanmelden bij de bedrijfsportal-app | Microsoft Docs
description: Ontdek hoe u zich kunt aanmelden bij de bedrijfsportal-app op meerdere platformen.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 56f19d0722841e801a0aca0009f2f629a8b90949
ms.sourcegitcommit: 490365fb8b5405f323b4358fb1ec9dfdd9ff2d58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2018
ms.locfileid: "43148811"
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>Hoe meld ik me aan bij de bedrijfsportal-app? <!--User Story 1132123-->

U gebruikt de bedrijfsportal-app om toegang te verkrijgen tot uw bedrijfsresources, zoals e-mail en zakelijke apps. Er zijn in principe twee manieren waarop u zich kunt aanmelden bij de bedrijfsportal:

* Met het e-mailadres van uw werk en het bijbehorende wachtwoord
* Aanmelden vanaf een ander apparaat

Hoewel de volgende afbeeldingen afkomstig zijn uit iOS, is het proces vrijwel identiek voor Android- en Windows-apparaten.

## <a name="signing-in-with-your-email-address-and-password"></a>Aanmelden met uw e-mailadres en wachtwoord

1. Open de bedrijfsportal-app op uw apparaat en tik op **Aanmelden**.

   ![De aanmeldingspagina van de bedrijfsportal met een pictogram van een persoon voor een grafische weergave van een website. Onderaan staan de tekst Toegang krijgen tot bedrijfsresources en deze beveiligen en de knop Aanmelden. Een koppeling onder aan de pagina leidt naar informatie over privacy en cookies van Microsoft.](/intune-user-help/media/cp_ios_aad_signin_after_1804_001.png)

   Hebt u de bedrijfsportal-app nog niet? U vindt hier informatie over het installeren en downloaden van de app voor [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) of [Android](install-the-company-portal-app-android.md).

2. Voer uw **werk- of schoolaccount** in en tik op **Volgende**.

   ![De gebruiker wordt gevraagd alleen een e-mailadres in te voeren in plaats van het e-mailadres en wachtwoord op hetzelfde scherm.](/intune-user-help/media/cp_ios_aad_signin_after_1804_002.png)

3. Voer uw wachtwoord in en tik op **Aanmelden**.

   ![De gebruiker wordt gevraagd om het wachtwoord nadat het e-mailadres is geaccepteerd.](/intune-user-help/media/cp_ios_aad_signin_after_1804_003.png)

4. Zodra de bedrijfsportal uw aanmelding heeft geaccepteerd, wordt u aangemeld en hebt u toegang tot de bedrijfsresources.   

   ![Nadat het verificatieproces is doorlopen, wordt er aangemeld met de bedrijfsportal-app. Hierbij wordt een laadbalk weergegeven.](/intune-user-help/media/cp_ios_aad_signin_after_1804_004.png)

## <a name="signing-in-with-certificate-based-authentication"></a>Aanmelden met verificatie op basis van certificaten

1.  Open de bedrijfsportal-app op uw apparaat.

2.  Voer uw **werk- of schoolaccount** in.

3.  Tik op de koppeling **Aanmelden met een certificaat**.

4.  Tik op **Doorgaan** om het certificaat te gebruiken.

## <a name="signing-in-from-another-device"></a>Aanmelden vanaf een ander apparaat

Als u geen wachtwoord hoeft op te geven om u aan te melden bij uw bedrijfsresources, kunt u een ander apparaat gebruiken om te bevestigen dat u de juiste persoon bent met de juiste toegangsniveaus. Als in uw bedrijf smartcards worden gebruikt om toegang te verkrijgen tot computers, is de kans groot dat u zich met behulp van een ander apparaat moet aanmelden.

1. In plaats van uw e-mailadres in te voeren, selecteert u de koppeling **Aanmelden vanaf een ander apparaat** onder het invoervak voor het e-mailadres.

   ![Op de aanmeldingspagina van de bedrijfsportal wordt de gebruiker gevraagd een e-mailadres in te voeren.  Daaronder staan de knop Volgende en een koppeling naar Aanmelden vanaf een ander apparaat. Bevat ook een koppeling naar Hebt u geen toegang tot uw account? Een koppeling onder aan de pagina leidt naar informatie over privacy en cookies van Microsoft.](/intune-user-help/media/cp_ios_aad_signin_after_1804_005.png)

2. U ontvangt een unieke, eenmalige code om u aan te melden bij de bedrijfsportal.

   ![Hier vindt u instructies om vanaf uw werkcomputer met een unieke wachtwoordcode naar de pagina https://microsoft.com/devicelogin te gaan en de code te gebruiken om u aan te melden.](/intune-user-help/media/cp_ios_aad_signin_after_1804_006.png)

3. Open op het andere apparaat een browser en ga naar [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin) om de code in te voeren.

   ![Een afbeelding van de browser van de gebruiker op de werkcomputer in plaats van de bedrijfsportal-app. Op de weergegeven pagina Apparaataanmelding wordt de gebruiker gevraagd om de code in de bedrijfsportal-app is ontvangen.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Als de code is gecontroleerd op de pagina **Apparaataanmelding**, selecteert u __Doorgaan__ om via de bedrijfsportal te worden aangemeld op uw andere apparaat.

   ![De gebruiker heeft de unieke code ingevoerd in het veld en op de site Apparaataanmelding is gevraagd om te bevestigen dat de Intune bedrijfsportal-app de juiste app is om autorisatie te ontvangen voor aanmelding.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Zodra de code is geverifieerd, kunt u het venster sluiten.

   ![Een bevestigingspagina met de mededeling dat de gebruiker nu is aangemeld bij de bedrijfsportal-app op hun apparaat en dat deze pagina kan worden gesloten.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Op het oorspronkelijke apparaat wordt het aanmeldingsproces gestart via de bedrijfsportal-app.

   ![Nadat het verificatieproces is doorlopen, wordt u aangemeld via de bedrijfsportal-app. Dit proces wordt aangegeven met een voortgangsbalk.](/intune-user-help/media/cp_ios_aad_signin_after_1804_007.png)

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
