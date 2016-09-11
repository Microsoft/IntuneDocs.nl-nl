---
title: iOS-apparaten in bedrijfseigendom inschrijven | Microsoft Intune
description: iOS-apparaten in bedrijfseigendom inschrijven met het Apple Device Enrollment Program (DEP) of Apple Configurator
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9b7b8f6e5182e228458f5ea75e804a638f1e2a2b
ms.openlocfilehash: ca05e94e72269c11db24b667f1d113c794cd8b23


---

# iOS-apparaten in bedrijfseigendom inschrijven in Microsoft Intune
Microsoft Intune ondersteunt de inschrijving van iOS-apparaten van het bedrijf met behulp van het Device Enrollment Program (DEP) van Apple of het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) dat op een Mac-computer wordt uitgevoerd.

**Vereiste:** [Apple Push Notification Service-certificaat](set-up-ios-and-mac-management-with-microsoft-intune.md)

U kunt iOS-apparaten in bedrijfseigendom op drie manieren inschrijven:

-   **Apple Configurator** - iOS-apparaten kunnen worden ingeschreven door een inschrijvingsprofiel voor bedrijfsapparaten te exporteren en deze mobiele apparaten vervolgens te verbinden met een Mac-computer waarop Apple Configurator wordt uitgevoerd. Apple Configurator ondersteunt twee soorten inschrijvingen:

    - **Inschrijving met configuratieassistent** : de fabrieksinstellingen worden hersteld en het apparaat wordt voorbereid voor configuratie door de nieuwe gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) wordt uitgevoerd om de registratie vooraf te configureren. De apparaten worden vervolgens afgeleverd bij hun gebruikers, die Configuratieassistent uitvoeren. Hierbij wordt het apparaat geconfigureerd met de referenties voor hun werk- of schoolaccount en de inschrijving wordt voltooid. [iOS-apparaten inschrijven met Apple Configurator en Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Directe inschrijving**: maakt een Apple Configurator-compatibel bestand dat tijdens de voorbereiding van het apparaat wordt gebruikt. Het ingeschreven apparaat krijgt niet opnieuw de fabrieksinstellingen, maar is niet meer gekoppeld aan de gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) wordt uitgevoerd, om het apparaat in te schrijven. [iOS-apparaten inschrijven met een directe inschrijving van Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Device Enrollment Program (DEP)**: implementeert een draadloos inschrijvingsprofiel op apparaten die via het Device Enrollment Program van Apple zijn aangeschaft. Wanneer de gebruiker Configuratieassistent op het apparaat uitvoert, wordt het apparaat ingeschreven bij Intune.  Gebruikers kunnen de inschrijving niet opheffen, wanneer de apparaten zijn ingeschreven via DEP. [Het Device Enrollment Program implementeren op iOS-apparaten](ios-device-enrollment-program-in-microsoft-intune.md)

## Apparaten die zijn geregistreerd via de bedrijfsportal op DEP of Apple Configurator gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij een aantal extra stappen uitvoeren om de Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.

iOS-apparaten in bedrijfseigendom inschrijven met gebruikersaffiniteit
1. Wanneer gebruikers hun apparaat inschakelen, wordt ze gevraagd de Configuratieassistent te voltooien. Tijdens de installatie wordt er naar de referenties van de gebruikers gevraagd. Ze moeten de referenties (de unieke naam of de UPN) van het Intune-abonnement gebruiken.

2. Tijdens de installatie wordt er naar de Apple-id van de gebruikers gevraagd. Er moet een Apple-id worden opgegeven zodat de bedrijfsportal op het apparaat kan worden geïnstalleerd. Een Apple-id kan ook worden opgegeven nadat het instellen in de iOS-instellingen is voltooid.

3. Nadat het instellen is voltooid, moet de bedrijfsportal-app worden geïnstalleerd vanuit de App Store, bijvoorbeeld Bedrijfsportal-app.

4. De gebruiker kan zich nu aanmelden bij de bedrijfsportal met behulp van de UPN die is gebruikt bij het instellen van het apparaat.

5. Na het aanmelden wordt de gebruiker gevraagd het apparaat te registreren. De eerste stap is het identificeren van het apparaat. De app geeft een lijst met iOS-apparaten weer die al voor het bedrijf zijn ingeschreven en zijn toegewezen aan het Intune-account van de eindgebruiker. Kies het desbetreffende apparaat.

  Als dit apparaat nog niet voor het bedrijf is ingeschreven, selecteert u 'nieuw apparaat' om door te gaan met de standaardinschrijving.

6. Op het volgende scherm moet de gebruiker het serienummer van het nieuwe apparaat bevestigen. De gebruiker kan op de koppeling Bevestig het serienummer tikken om de app Instellingen te starten, waarmee het serienummer wordt geverifieerd. De gebruiker moet vervolgens de laatste 4 tekens van het serienummer invoeren in de bedrijfsportal-app.

  Met deze stap wordt gecontroleerd of het apparaat het bedrijfsapparaat is dat is ingeschreven in Intune. Als het serienummer op het apparaat niet overeenkomt, is het verkeerde apparaat geselecteerd. Ga terug naar het vorige scherm en selecteer een ander apparaat.

7. Wanneer het serienummer is geverifieerd, wordt de gebruiker door de bedrijfsportal-app omgeleid naar de website van de bedrijfsportal om de inschrijving te voltooien. Vervolgens wordt de gebruiker gevraagd om terug te keren naar de app.

8. De inschrijving is nu voltooid. U kunt dit apparaat nu gebruiken met de volledige set mogelijkheden.

### Over beheerde bedrijfsapparaten zonder gebruikersaffiniteit

Apparaten die zijn geconfigureerd zonder gebruikersaffiniteit bieden geen ondersteuning voor de bedrijfsportal. Installeer de app niet op deze apparaten. De bedrijfsportal is bedoeld voor gebruikers met zakelijke referenties die toegang tot persoonlijke bedrijfsresources (bijvoorbeeld e-mail) nodig hebben. Apparaten die zijn ingeschreven zonder gebruikersaffiniteit zijn niet bedoeld voor gebruik met een specifieke gebruikersaanmelding. Kiosks, verkooppunten (POS) of gedeelde hulpmiddelen zijn typische gebruiksvoorbeelden van apparaten die zonder gebruikersaffiniteit worden ingeschreven. Als gebruikersaffiniteit vereist is, moet Gebruikersaffiniteit in het inschrijvingsprofiel van het apparaat zijn geselecteerd voordat het apparaat wordt ingeschreven. Als u de status van de affiniteit op een apparaat wilt wijzigen, moet u het apparaat buiten gebruik stellen en opnieuw inschrijven.



### Zie tevens
[Bereid u voor op het registreren van apparaten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


