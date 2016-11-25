---
title: iOS-apparaten in bedrijfseigendom inschrijven | Microsoft Intune
description: iOS-apparaten in bedrijfseigendom inschrijven met het Apple Device Enrollment Program (DEP) of Apple Configurator
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 00ca6ea06aa63646d6ede6337f8e70d1ab956c5f
ms.openlocfilehash: cfc97f4ed931a5c7dc5b38eafd0a2d081bc30975


---

# <a name="enroll-corporate-owned-ios-devices-in-microsoft-intune"></a>iOS-apparaten in bedrijfseigendom inschrijven in Microsoft Intune
Microsoft Intune ondersteunt de inschrijving van iOS-apparaten van het bedrijf met behulp van het Device Enrollment Program (DEP) van Apple of het hulpprogramma [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) dat op een Mac-computer wordt uitgevoerd.

**Vereiste:** een [Apple Push Notification Service-certificaat](set-up-ios-and-mac-management-with-microsoft-intune.md).

U kunt zakelijke iOS-apparaten op drie manieren inschrijven: via Apple Configurator, DEP of de bedrijfsportal.

## <a name="use-apple-configurator"></a>Apple Configurator gebruiken

iOS-apparaten kunnen worden ingeschreven door een inschrijvingsprofiel voor bedrijfsapparaten te exporteren en deze mobiele apparaten vervolgens te verbinden met een Mac-computer waarop Apple Configurator wordt uitgevoerd. Apple Configurator ondersteunt twee soorten inschrijvingen:

- **Inschrijving met configuratieassistent** : de fabrieksinstellingen worden hersteld en het apparaat wordt voorbereid voor configuratie door de nieuwe gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) wordt uitgevoerd om de registratie vooraf te configureren. Apparaten wordt vervolgens geleverd aan de gebruikers die het Configuratieassistent-proces uitvoeren. Met dit proces wordt het apparaat geconfigureerd met hun werk- of schoolreferenties en wordt het registratieproces voltooid. Zie [ iOS-apparaten inschrijven met Apple Configurator en Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md) voor meer informatie.

- **Directe inschrijving**: maakt een Apple Configurator-compatibel bestand dat tijdens de voorbereiding van het apparaat wordt gebruikt. Het ingeschreven apparaat krijgt niet opnieuw de fabrieksinstellingen, maar is niet meer gekoppeld aan de gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) wordt uitgevoerd, om het apparaat in te schrijven. Zie [Enroll iOS devices using Apple Configurator Direct Enrollment (iOS-apparaten inschrijven met directe inschrijving via Apple Configurator)](ios-direct-enrollment-in-microsoft-intune.md) voor meer informatie.

## <a name="use-the-device-enrollment-program-dep"></a>Het apparaatinschrijvingsprogramma (DEP) gebruiken
DEP implementeert een draadloos inschrijvingsprofiel voor apparaten die zijn gekocht via DEP. Wanneer een gebruiker Configuratieassistent op het apparaat uitvoert, wordt het apparaat ingeschreven bij Intune.  Gebruikers kunnen de inschrijving niet opheffen wanneer de apparaten zijn ingeschreven via DEP. Zie [Het Device Enrollment Program implementeren op iOS-apparaten](ios-device-enrollment-program-in-microsoft-intune.md) voor meer informatie.

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Apparaten die zijn geregistreerd via de bedrijfsportal op DEP of Apple Configurator gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij een aantal extra stappen uitvoeren om de Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.

Gebruikersaffiniteit is vereist voor de ondersteuning van het volgende:
  - MAM-apps (Mobile Application Management)
  - Voorwaardelijke toegang tot e-mail en bedrijfsgegevens
  - Bedrijfsportal-app

**iOS-apparaten in bedrijfseigendom inschrijven met gebruikersaffiniteit**
1. Wanneer gebruikers hun apparaat inschakelen, wordt ze gevraagd de Configuratieassistent te voltooien. Tijdens de installatie wordt er naar de referenties van de gebruikers gevraagd. Ze moeten de referenties (de unieke naam of de UPN) van het Intune-abonnement gebruiken.

2. Tijdens de installatie wordt er naar de Apple-id van de gebruikers gevraagd. Er moet een Apple-id worden opgegeven zodat de bedrijfsportal op het apparaat kan worden geïnstalleerd. Ze kunnen ook de id in het iOS-instellingenmenu opgeven nadat de installatie is voltooid.

3. Nadat het instellen is voltooid, moet de bedrijfsportal-app op het iOS-apparaat worden geïnstalleerd vanuit de App Store.

4. De gebruiker kan zich nu aanmelden bij de bedrijfsportal met behulp van de UPN die is gebruikt bij het instellen van het apparaat.

5. Na het aanmelden wordt de gebruiker gevraagd het apparaat te registreren. De eerste stap is het identificeren van het apparaat. De app geeft een lijst met iOS-apparaten weer die al voor het bedrijf zijn ingeschreven en zijn toegewezen aan het Intune-account van de eindgebruiker. De gebruiker moet het desbetreffende apparaat kiezen.

  Als dit apparaat nog niet voor het bedrijf is ingeschreven, moeten ze **nieuw apparaat** kiezen om door te gaan met de standaardinschrijving.

6. Op het volgende scherm moet de gebruiker het serienummer van het nieuwe apparaat bevestigen. De gebruiker kan op de koppeling **Bevestig het serienummer** tikken om de app Instellingen te starten, waarmee het serienummer wordt geverifieerd. De gebruiker moet vervolgens de laatste vier tekens van het serienummer invoeren in de bedrijfsportal-app.

  Met deze stap wordt gecontroleerd of het apparaat het bedrijfsapparaat is dat is ingeschreven in Intune. Als het serienummer op het apparaat niet overeenkomt, is het verkeerde apparaat geselecteerd. De gebruiker moet teruggaan naar het vorige scherm en een ander apparaat selecteren.

7. Wanneer het serienummer is geverifieerd, wordt de gebruiker door de bedrijfsportal-app omgeleid naar de website van de bedrijfsportal om de inschrijving te voltooien. Vervolgens wordt de gebruiker gevraagd om terug te keren naar de app.

8. De inschrijving is nu voltooid. De gebruiker kan dit apparaat nu gebruiken met de volledige set mogelijkheden.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Over beheerde bedrijfsapparaten zonder gebruikersaffiniteit

Apparaten die zijn geconfigureerd zonder gebruikersaffiniteit bieden geen ondersteuning voor de bedrijfsportal. De app moet niet op deze apparaten worden geïnstalleerd. De bedrijfsportal is bedoeld voor gebruikers met zakelijke referenties die toegang tot persoonlijke bedrijfsresources (bijvoorbeeld e-mail) nodig hebben. Apparaten die zijn ingeschreven zonder gebruikersaffiniteit zijn niet bedoeld voor gebruik met een specifieke gebruikersaanmelding. Kiosks, verkooppunten (POS) of apparaten met gedeelde hulpmiddelen zijn typische gebruiksvoorbeelden van apparaten die zonder gebruikersaffiniteit worden ingeschreven.

Als gebruikersaffiniteit vereist is, moet **Gebruikersaffiniteit** in het inschrijvingsprofiel van het apparaat zijn geselecteerd voordat het apparaat wordt ingeschreven. Als u de status van de affiniteit op een apparaat wilt wijzigen, moet u het apparaat buiten gebruik stellen en opnieuw inschrijven.



### <a name="see-also"></a>Zie tevens
[Vereisten voor het registreren van apparaten in Microsoft Intune](prerequisites-for-enrollment.md)



<!--HONumber=Nov16_HO3-->


