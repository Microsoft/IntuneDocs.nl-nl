---
title: Kiezen hoe u iOS-apparaten registreert in Intune
titlesuffix: Microsoft Intune
description: Het registreren van iOS-apparaten in Microsoft Intune instellen.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 602c4c1da553215ad222a7e593531fdd879c996c
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="enroll-ios-devices-in-intune"></a>iOS-apparaten registreren bij Intune

Intune maakt Mobile Device Management (MDM) mogelijk voor iPads en iPhones en geeft gebruikers toegang tot zakelijke e-mail en apps.

Als Intune-beheerder kunt u registratie inschakelen voor iOS-apparaten. U kunt gebruikers toestaan persoonlijke apparaten te registreren. Dit wordt ook wel BYOD-registratie (‘Bring Your Own Device’) genoemd. U kunt ook de registratie van apparaten in bedrijfseigendom inschakelen.

## <a name="prerequisites-for-ios-enrollment"></a>Vereisten voor iOS-registratie
Voordat u de registratie van iOS-apparaten kunt inschakelen, moet u de volgende stappen uitvoeren:
- [Intune instellen](setup-steps.md): hiermee stelt u de Intune-infrastructuur in. Voor apparaatinschrijving is met name het [instellen van uw MDM-instantie](mdm-authority-set.md) van belang.
- [Een Apple MDM-pushcertificaat ophalen](apple-mdm-push-certificate-get.md): Apple vereist een certificaat voor het inschakelen van het beheer van iOS- en macOS-apparaten.

## <a name="user-owned-ios-devices-byod"></a>iOS-apparaten die het eigendom van gebruikers zijn (BYOD)

U kunt gebruikers hun persoonlijke apparaten laten inschrijven voor Intune-beheer, wat 'Bring Your Own Device' of BYOD wordt genoemd. Zodra u aan de vereisten hebt voldaan en gebruikerslicenties hebt toegewezen, kunnen ze in de App Store de Intune-bedrijfsportal-app downloaden en in de app de inschrijvingsinstructies volgen.

## <a name="company-owned-ios-devices"></a>iOS-apparaten die bedrijfseigendom zijn
Voor organisaties die apparaten voor hun gebruikers aanschaffen, ondersteunt Intune de volgende inschrijvingsmethoden voor iOS-apparaten die bedrijfseigendom zijn:

- Device Enrollment Program (DEP) van Apple
- Apple School Manager
- Inschrijving via Apple Configurator Setup Assistant
- Directe inschrijving via Apple Configurator

U kunt iOS-apparaten die bedrijfseigendom zijn ook inschrijven met een [Apparaatinschrijvingsmanager](device-enrollment-manager-enroll.md)-account.

## <a name="device-enrollment-program"></a>Programma voor apparaatinschrijving
Organisaties kunnen nu iOS-apparaten aanschaffen via het Device Enrollment Program (DEP) van Apple. Met DEP kunt u een registratieprofiel draadloos implementeren om apparaten voor beheer in te schrijven. Meer informatie over het [Device Enrollment Program](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager is een programma voor het aanschaffen en inschrijven van apparaten voor scholen. Net zoals bij DEP kunt u een profiel implementeren om apparaten in te schrijven voor beheer. Meer informatie over [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
U kunt iOS-apparaten inschrijven met Apple Configurator op een Mac-computer. Ter voorbereiding daarop sluit u de apparaten aan via USB en installeert u een inschrijvingsprofiel. U kunt apparaten op twee manieren inschrijven met Apple Configurator:
- Inschrijving met iOS-configuratieassistent: met dit proces wordt het apparaat teruggezet naar de fabrieksinstellingen, wordt het apparaat voorbereid voor uitvoering van Configuratieassistent en worden de bedrijfsbeleidsregels voor de nieuwe gebruiker van het apparaat geïnstalleerd.
- Directe inschrijving: met dit proces wordt het apparaat niet teruggezet naar de fabrieksinstellingen en wordt het apparaat met een vooraf gedefinieerd beleid geregistreerd. Deze methode is geschikt voor apparaten zonder gebruikersaffiniteit.

Meer informatie over [Apple Configurator-inschrijving](apple-configurator-setup-assistant-enroll-ios.md).

## <a name="use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices"></a>Apparaten die zijn geregistreerd via de bedrijfsportal op DEP of Apple Configurator gebruiken

Op apparaten die zijn geconfigureerd met gebruikersaffiniteit kan de bedrijfsportal-app worden geïnstalleerd en uitgevoerd om apps te downloaden en apparaten te beheren. Nadat gebruikers hun apparaten hebben ontvangen, moeten zij een aantal extra stappen uitvoeren om de Configuratieassistent te voltooien en de bedrijfsportal-app te installeren.

Gebruikersaffiniteit is vereist voor de ondersteuning van het volgende:
  - MAM-apps (Mobile Application Management)
  - Voorwaardelijke toegang tot e-mail en bedrijfsgegevens
  - Bedrijfsportal-app

**iOS-apparaten in bedrijfseigendom inschrijven met gebruikersaffiniteit**
1. Wanneer gebruikers hun apparaat inschakelen, wordt ze gevraagd de Configuratieassistent te voltooien. Tijdens de installatie wordt er naar de referenties van de gebruikers gevraagd. Ze moeten de referenties (de unieke naam of de UPN) van het Intune-abonnement gebruiken.

2. Tijdens de installatie wordt er naar de Apple ID van de gebruikers gevraagd. Er moet een Apple ID worden opgegeven zodat de bedrijfsportal op het apparaat kan worden geïnstalleerd. Ze kunnen ook de id in het iOS-instellingenmenu opgeven nadat de installatie is voltooid.

3. Nadat het instellen is voltooid, moet de bedrijfsportal-app op het iOS-apparaat worden geïnstalleerd vanuit de App Store.

4. De gebruiker kan zich nu aanmelden bij de bedrijfsportal met behulp van de UPN die is gebruikt bij het instellen van het apparaat.

5. Na het aanmelden wordt de gebruiker gevraagd het apparaat te registreren. De eerste stap is het identificeren van het apparaat. De app geeft een lijst met iOS-apparaten weer die al voor het bedrijf zijn ingeschreven en zijn toegewezen aan het Intune-account van de eindgebruiker. De gebruiker moet het desbetreffende apparaat kiezen.

  Als dit apparaat nog niet voor het bedrijf is ingeschreven, moeten ze **nieuw apparaat** kiezen om door te gaan met de standaardinschrijving.

6. Op het volgende scherm moet de gebruiker het serienummer van het nieuwe apparaat bevestigen. De gebruiker kan op de koppeling **Bevestig het serienummer** tikken om instructies weer te geven voor gebruik van de app Instellingen, waarmee het serienummer wordt geverifieerd. De gebruiker moet vervolgens de laatste vier tekens van het serienummer invoeren in de bedrijfsportal-app.

  Met deze stap wordt gecontroleerd of het apparaat het bedrijfsapparaat is dat is ingeschreven in Intune. Als het serienummer op het apparaat niet overeenkomt, is het verkeerde apparaat geselecteerd. De gebruiker moet teruggaan naar het vorige scherm en een ander apparaat selecteren.

7. Wanneer het serienummer is geverifieerd, wordt de gebruiker door de bedrijfsportal-app omgeleid naar de website van de bedrijfsportal om de inschrijving te voltooien. Vervolgens wordt de gebruiker gevraagd om terug te keren naar de app.

8. De inschrijving is nu voltooid. De gebruiker kan dit apparaat nu gebruiken met de volledige set mogelijkheden.

### <a name="about-corporate-owned-managed-devices-with-no-user-affinity"></a>Over beheerde bedrijfsapparaten zonder gebruikersaffiniteit

Apparaten die zijn geconfigureerd zonder gebruikersaffiniteit bieden geen ondersteuning voor de bedrijfsportal. De app moet niet op deze apparaten worden geïnstalleerd. De bedrijfsportal is bedoeld voor gebruikers met zakelijke referenties die toegang tot persoonlijke bedrijfsresources (bijvoorbeeld e-mail) nodig hebben. Apparaten die zijn ingeschreven zonder gebruikersaffiniteit zijn niet bedoeld voor gebruik met een specifieke gebruikersaanmelding. Kiosks, verkooppunten (POS) of apparaten met gedeelde hulpmiddelen zijn typische gebruiksvoorbeelden van apparaten die zonder gebruikersaffiniteit worden ingeschreven.

Als gebruikersaffiniteit vereist is, moet **Gebruikersaffiniteit** in het inschrijvingsprofiel van het apparaat zijn geselecteerd voordat het apparaat wordt ingeschreven. Als u de status van de affiniteit op een apparaat wilt wijzigen, moet u het apparaat buiten gebruik stellen en opnieuw inschrijven.

