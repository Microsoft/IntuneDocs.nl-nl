---
title: De wachtwoordcode opnieuw instellen op de website van de bedrijfsportal | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fa3255b-9d1e-42d5-bd8b-70963dcf2d86
searchScope:
- User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 111cbc1aa2dd9c537a7f5581d0dd6f2e75d8c7f3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-reset-your-device-passcode-from-the-company-portal-website"></a>De wachtwoordcode van uw apparaat opnieuw instellen op de website van de bedrijfsportal

Als u de pincode of het wachtwoord van het apparaat dat u bij Intune hebt geregistreerd, bent vergeten, kunt u de [website van de bedrijfsportal](https://portal.manage.microsoft.com#HelpDeskDialog) gebruiken om de pincode of het wachtwoord opnieuw in te stellen. Met de website van de bedrijfsportal kunt u computers en apparaten beheren die u hebt geregistreerd in Intune en waarop u de meeste taken kunt uitvoeren die u ook met uw bedrijfsportal-app kunt uitvoeren.

> [!NOTE]
> Het is mogelijk dat u de knop Wachtwoordcode opnieuw instellen niet ziet op de website van de bedrijfsportal als u een geregistreerd apparaat gebruikt dat bedrijfseigendom is. In dat geval neemt u contact op met het ondersteuningsteam van het bedrijf om de wachtwoordcode opnieuw in te stellen.

Ga als volgt te werk om uw wachtwoordcode opnieuw in te stellen:

1.  Op de [Bedrijfsportal-website ](https://portal.manage.microsoft.com#HelpDeskDialog) tikt u op de knop __Menu__ ![Een kleine afbeelding van de knop Menu, drie horizontale, parallelle balken.](/intune/media/CP_hamburger_menu.png) en selecteert u vervolgens __Mijn apparaten__.

2. Op de pagina __Mijn apparaten__ selecteert u de naam van het apparaat waarvan u de wachtwoordcode opnieuw wilt instellen.

  ![Een schermafbeelding van de pagina Mijn apparaat met een paar onbekende apparaten boven de koptekst die vraagt naar het inschrijven van niet-vermelde apparaten of het identificeren van ongeïdentificeerde apparaten.](./media/macOS_enroll_002_tap_here_banner.png)

3.  Het apparaat wordt in een pop-upvenster geopend. Selecteer de knop **Wachtwoordcode opnieuw instellen** .

    ![Alle opties voor een geselecteerd apparaat op de Bedrijfsportalwebsite, zoals Naam wijzigen, Verwijderen, Apparaat opnieuw instellen, Wachtwoordcode opnieuw instellen en Extern vergrendelen. ](./media/iwp-screen-with-all-options.png)

4.  Een koptekst wordt weergegeven waarin u wordt gevraagd te bevestigen dat u uw wachtwoordcode opnieuw wilt instellen en dat het apparaat u afmeldt nadat dit is gebeurd. Vervolgens moet u 5 minuten wachten voordat u zich opnieuw kunt aanmelden.

  ![De koptekst van het opnieuw instellen van de wachtwoordcode met de waarschuwing over het opnieuw instellen van de wachtwoordcode van het apparaat en hoe de gebruiker wordt afgemeld. De knoppen voor invoer van de gebruiker zijn Afmelden en Annuleren.](./media/iwp-reset-passcode-popup.png)

5.  Selecteer **Afmelden** en u ontvangt een laatste bericht waarin u wordt verteld over het verwijderen van de wachtwoordcode van het apparaat. Als u het apparaat niet bij u hebt, verwijder de wachtwoordcode dan niet, omdat iedereen die fysieke toegang heeft tot het apparaat dan toegang heeft tot de meeste gegevens erop - persoonlijke zowel als zakelijke. 

  ![De tweede koptekst van het opnieuw instellen van de wachtwoordcode met de waarschuwing over het opnieuw instellen van de wachtwoordcode van het apparaat en hoe de wachtwoordcode wordt verwijderd van het apparaat. Het geeft ook aan hoe u een nieuwe wachtwoordcode in kunt stellen door naar apparaatinstellingen te gaan.](./media/iwp-reset-passcode-2nd-popup.png)

  Verschillende apparaten hebben verschillende soorten wachtwoordcodes.

  **Android**: de bestaande wachtwoordcode wordt verwijderd en er wordt een tijdelijke wachtwoordcode gemaakt die bestaat uit letters en cijfers. 
  
  > [!NOTE]
  > Het is niet mogelijk om wachtwoordcodes voor apparaten met Android 7.0 en hoger opnieuw in te stellen. U moet de fabrieksinstellingen van deze apparaten terugzetten als u de wachtwoordcode bent vergeten.

  **iOS**: de bestaande wachtwoordcode wordt verwijderd en er wordt geen tijdelijke wachtwoordcode gemaakt. Als u de Touch ID-vingerafdrukscanner gebruikt om toegang te krijgen tot uw apparaat of voor het doen van aankopen, moet u deze opnieuw instellen.

  **Windows 10 Mobile**: de bestaande wachtwoordcode wordt verwijderd en er wordt een tijdelijke wachtwoordcode gemaakt die bestaat uit letters en cijfers. Windows Hello-gezichtsherkenning wordt nog steeds ondersteund, dus u kunt deze gewoon gebruiken om u aan te melden.
    
  **Windows Phone 8.1**: de bestaande wachtwoordcode wordt verwijderd en er wordt een tijdelijke wachtwoordcode gemaakt die bestaat uit cijfers.

  Voor Android en Windows-apparaten wordt het tijdelijke wachtwoord weergegeven in de **Apparaatdetails**. 

6.  Ontgrendel uw apparaat en stel vervolgens een nieuwe wachtwoordcode in of wijzig de tijdelijke wachtwoordcode door op uw apparaat naar **Instellingen** te gaan.

Als u een melding wilt zien die bevestigt dat uw wachtwoord opnieuw is ingesteld, klikt u op de meldingsvlag boven aan de website van de bedrijfsportal.

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of de contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog).
