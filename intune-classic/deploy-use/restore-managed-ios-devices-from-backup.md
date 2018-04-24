---
title: Back-ups van door Intune beheerde iOS-apparaten terugzetten
description: Eindgebruikers helpen bij het opnieuw registreren van hun apparaten na het terugzetten van een back-up.
keywords: terugzetten, beheerd, iOS
author: lenewsad
ms.author: lanewsad
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2c2a35a7faa022ab2b9b095d4a08075e1c338c70
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="restore-intune-managed-ios-devices-from-backup"></a>Back-ups van door Intune beheerde iOS-apparaten terugzetten

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

In bepaalde gevallen moet u of een van uw gebruikers een iOS-apparaat herstellen door het terugzetten van een back-up, bijvoorbeeld wanneer een gebruiker een nieuw apparaat krijgt. In dit onderwerp worden de extra stappen beschreven die u mogelijk moet uitvoeren om Intune-beheer in te stellen na het herstellen van het apparaat.

## <a name="restoring-backups-onto-the-same-device"></a>Een back-up terugzetten op hetzelfde apparaat

Als de back-up wordt teruggezet op hetzelfde apparaat, wordt de registratiestatus van het apparaat ook teruggezet. Er is geen verdere actie nodig.

## <a name="restoring-backups-onto-different-devices"></a>Een back-up terugzetten op een ander apparaat

Als de back-up wordt teruggezet op een ander apparaat, wordt de registratiestatus niet automatisch teruggezet op het nieuwe apparaat. Gebruikers moeten de standaardregistratiestappen uitvoeren in de bedrijfsportal-app (versie 2.1.22 of hoger) om [hun iOS-apparaat te registreren in Intune](/intune-user-help/enroll-your-device-in-intune-ios).

> [!NOTE]
> Als u beleidsregels voor voorwaardelijke toegang hebt geconfigureerd voor uw eindgebruikers, hebben ze pas weer toegang tot hun zakelijke e-mail als hun apparaten opnieuw zijn geregistreerd.

> [!TIP]
> Een voorbeeldbericht voor uw gebruikers kan er als volgt uitzien: Om uw nieuwe apparaat te registreren, moet u gebruikmaken van de bedrijfsportal-app (versie 2.1.22 of hoger). U controleert de versie als volgt: open de bedrijfsportal-app, tik op de knop Menu in de rechterbovenhoek en tik vervolgens op Over. Als u een te lage versie hebt, sluit u de bedrijfsportal-app en opent u de App Store. Tik op de knop Updates in de rechterbenedenhoek en tik vervolgens op de knop voor bijwerken naast de bedrijfsportal in de lijst. Als de update is voltooid, start u de bedrijfsportal-app en [registreer uw iOS-apparaat bij Intune](/intune-user-help/enroll-your-device-in-intune-ios).

## <a name="resolving-known-issues-with-restores"></a>Bekende problemen met herstellen oplossen

Gebruikers kunnen soms problemen ondervinden als ze hun apparaat hebben hersteld en de bedrijfsportal-app hebben gestart wanneer ze nog werken met versie 2.1.21 of eerder van de bedrijfsportal. Deze problemen kunnen worden aangepakt door de juiste stappen voor de desbetreffende gebruiker uit te voeren.

### <a name="for-users-who-will-only-use-their-new-device"></a>Voor gebruikers die alleen hun nieuwe apparaat gaan gebruiken
Start de bedrijfsportal-app en maak de registratie ongedaan door de tegel van het huidige apparaat te selecteren en op de knop __Verwijderen__ te tikken. Na het verwijderen volgt u de standaardstappen voor inschrijving om [een iOS-apparaat in te schrijven in Intune](/intune-user-help/enroll-your-device-in-intune-ios).

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a>Voor gebruikers die zowel hun oude als nieuwe apparaat gaan gebruiken
Schakel cookies uit in Safari door te tikken op __Instellingen__ > __Safari__ > __Geschiedenis- en websitegegevens wissen__. Na het wissen van de gegevens verwijdert u de bedrijfsportal-app en installeert u deze opnieuw, waarna u de standaardstappen voor inschrijving volgt om [een iOS-apparaat in te schrijven in Intune](/intune-user-help/enroll-your-device-in-intune-ios).
