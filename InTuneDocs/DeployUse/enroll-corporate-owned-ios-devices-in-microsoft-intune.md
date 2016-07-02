---
title: iOS-apparaten in bedrijfseigendom inschrijven in Microsoft Intune | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ROBOTS: noindex,nofollow
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 48359b44bec9ac3e1c9510debc01d2cf8abf6d2b


---

# iOS-apparaten in bedrijfseigendom inschrijven in Microsoft Intune
Microsoft Intune ondersteunt de inschrijving van iOS-apparaten van het bedrijf met behulp van het Device Enrollment Program (DEP) van Apple of het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) dat op een Mac-computer wordt uitgevoerd.

U kunt iOS-apparaten in bedrijfseigendom op drie manieren inschrijven:

-   **Inschrijving met configuratieassistent** : de fabrieksinstellingen worden hersteld en het apparaat wordt voorbereid voor configuratie door de nieuwe gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop Apple Configurator wordt uitgevoerd om de inschrijving vooraf te configureren. De apparaten worden vervolgens afgeleverd bij hun gebruikers, die Configuratieassistent uitvoeren. Hierbij wordt het apparaat geconfigureerd met de referenties voor hun werk- of schoolaccount en de inschrijving wordt voltooid. [iOS-apparaten inschrijven met Apple Configurator en Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md)

-   **Directe inschrijving**: maakt een Apple Configurator-compatibel bestand dat tijdens de voorbereiding van het apparaat wordt gebruikt. Het ingeschreven apparaat krijgt niet opnieuw de fabrieksinstellingen, maar is niet meer gekoppeld aan de gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop Apple Configurator wordt uitgevoerd, om het apparaat in te schrijven. [iOS-apparaten inschrijven met een directe inschrijving van Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)**: implementeert een draadloos inschrijvingsprofiel op apparaten die via het Device Enrollment Program van Apple zijn aangeschaft. Wanneer de gebruiker Configuratieassistent op het apparaat uitvoert, wordt het apparaat ingeschreven bij Intune.  Gebruikers kunnen de inschrijving niet opheffen, wanneer de apparaten zijn ingeschreven via DEP. [Het Device Enrollment Program implementeren op iOS-apparaten](ios-device-enrollment-program-in-microsoft-intune.md)




### Zie tevens
[Bereid u voor op het registreren van apparaten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


