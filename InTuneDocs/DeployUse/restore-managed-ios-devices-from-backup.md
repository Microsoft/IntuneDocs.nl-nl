---
title: Back-ups van door Intune beheerde iOS-apparaten terugzetten | Microsoft Intune
description: Eindgebruikers helpen bij het opnieuw registreren van hun apparaten na het terugzetten van een back-up.
keywords: terugzetten, beheerd, iOS
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e6bb539c87c4a13a490ba98c016d814bea5c7bbc
ms.openlocfilehash: 6395e50b3e4c06e7363acc136b5ed9eb2ef75abd


---

# Back-ups van door Intune beheerde iOS-apparaten terugzetten

In bepaalde gevallen moet u of een van uw gebruikers een iOS-apparaat herstellen door het terugzetten van een back-up, bijvoorbeeld wanneer een gebruiker een nieuw apparaat krijgt. In dit onderwerp worden de extra stappen beschreven die u mogelijk moet uitvoeren om Intune-beheer in te stellen na het herstellen van het apparaat.

## Een back-up terugzetten op hetzelfde apparaat

Als de back-up wordt teruggezet op hetzelfde apparaat, wordt de registratiestatus van het apparaat ook teruggezet. Er is geen verdere actie nodig.

## Een back-up terugzetten op een ander apparaat

Als de back-up wordt teruggezet op een ander apparaat, wordt de registratiestatus niet automatisch teruggezet op het nieuwe apparaat. Gebruikers moeten de standaardregistratiestappen uitvoeren in de bedrijfsportalapp (versie 2.1.22 of hoger) om [hun iOS-apparaat te registreren in Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

> [!NOTE]
> Als u beleidsregels voor voorwaardelijke toegang hebt geconfigureerd voor uw eindgebruikers, hebben ze pas weer toegang tot hun zakelijke e-mail als hun apparaten opnieuw zijn geregistreerd.

> [!TIP]
> Een voorbeeldbericht voor uw gebruikers kan er als volgt uitzien: Om uw nieuwe apparaat te registreren, moet u gebruikmaken van de bedrijfsportalapp (versie 2.1.22 of hoger). U controleert de versie als volgt: open de bedrijfsportalapp, tik op de knop Menu in de rechterbovenhoek en tik vervolgens op Over. Als u een te lage versie hebt, sluit u de bedrijfsportalapp en opent u de App Store. Tik op de knop Updates in de rechterbenedenhoek en tik vervolgens op de knop voor bijwerken naast de bedrijfsportal in de lijst. Als de update is voltooid, start u de bedrijfsportalapp en [registreer uw iOS-apparaat bij Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

## Bekende problemen met herstellen oplossen

Gebruikers kunnen soms problemen ondervinden als ze hun apparaat hebben hersteld en de bedrijfsportal-app hebben gestart wanneer ze nog werken met versie 2.1.21 of eerder van de bedrijfsportal. Deze problemen kunnen worden aangepakt door de juiste stappen voor de desbetreffende gebruiker uit te voeren.

### Voor gebruikers die alleen hun nieuwe apparaat gaan gebruiken
Start de bedrijfsportal-app en maak de registratie ongedaan door de tegel van het huidige apparaat te selecteren en op de knop __Verwijderen__ te tikken. Na het verwijderen volgt u de standaardstappen voor inschrijving om [een iOS-apparaat in te schrijven in Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).

### Voor gebruikers die zowel hun oude als nieuwe apparaat gaan gebruiken
Schakel cookies uit in Safari door te tikken op __Instellingen__ > __Safari__ > __Geschiedenis- en websitegegevens wissen__. Na het wissen van de gegevens verwijdert u de bedrijfsportal-app en installeert u deze opnieuw, waarna u de standaardstappen voor inschrijving volgt om [een iOS-apparaat in te schrijven in Intune](/Intune/EndUser/enroll-your-device-in-intune-ios).



<!--HONumber=Oct16_HO3-->


