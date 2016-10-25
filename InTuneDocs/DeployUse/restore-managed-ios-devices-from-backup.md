---
title: Back-ups van door Intune beheerde iOS-apparaten terugzetten | Microsoft Intune
description: Eindgebruikers helpen bij het opnieuw registreren van hun apparaten na het terugzetten van een back-up.
keywords: 
author: barlanmsft
manager: angrobe
ms.date: 10/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 612b0954a81de1ee8d4a1e96c7440239437dec14
ms.openlocfilehash: 5fc4423f8fd0c5829be5fe6c96949e126991e430


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



<!--HONumber=Oct16_HO2-->


