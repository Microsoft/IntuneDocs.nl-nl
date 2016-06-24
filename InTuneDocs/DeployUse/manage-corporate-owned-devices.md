---
# required metadata

title: Apparaten in bedrijfseigendom beheren | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apparaten in bedrijfseigendom registreren met Microsoft Intune
Apparaten in organisatie- of bedrijfseigendom kunnen op verschillende manieren worden geregistreerd voor beheer door Intune, afhankelijk van het apparaat, hoe dit apparaat is aangeschaft en wat de behoeften van de organisatie zijn.

## iOS-apparaten in bedrijfseigendom
Deze registratiemethoden zijn geschikt voor CYOD-scenario's (Choose Your Own Device), waarbij de organisatie de apparaten koopt voor gebruikers, maar het beheer van de apparaten bij de organisatie blijft. Als uw organisatie iOS-apparaten heeft aangeschaft, kunt u deze vooraf registreren, zodat een apparaat wordt beheerd vanaf de eerste keer dat de gebruiker het inschakelt. Intune ondersteunt registratie via het [Device Enrollment Program (DEP) van Apple](ios-device-enrollment-program-in-microsoft-intune.md) of met behulp van het hulpprogramma Apple Configurator, dat wordt uitgevoerd op een Mac-computer voor [directe](ios-direct-enrollment-in-microsoft-intune.md) registratie of registratie met de [Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[iOS-apparaten van het bedrijf inschrijven](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Apparaatinschrijvingsmanager
Organisaties kunnen Intune gebruiken voor het beheer van een groot aantal mobiele apparaten met één gebruikersaccount (een zogenaamd apparaatregistratiebeheeraccount). Nadat een apparaatregistratiebeheeraccount is gemaakt, kan dit account door een beheerder worden gebruikt om meer apparaten te registreren dan de vijf apparaten die standaard zijn toegestaan voor reguliere gebruikers. De registratie van apparaten via apparaatregistratiebeheer werkt alleen voor apparaten die niet worden gebruikt door een specifieke gebruiker. Dergelijke apparaten zijn bijvoorbeeld geschikt voor gebruik in een verkooppunt of met utiliteitsapps, maar niet voor gebruikers die toegang nodig hebben tot e-mail of bedrijfsbronnen.

[Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## IMEI (International Mobile Equipment Identity)
Een uniek IMEI-nummer (International Mobile Equipment Identity) is voor veel fabrikanten van mobiele apparaten een algemene apparaateigenschap. Intune-beheerders kunnen IMEI-nummers importeren voor apparaten die eigendom zijn van het bedrijf. Wanneer het apparaat wordt beheerd met Intune, kan het worden gelabeld als apparaat in bedrijfseigendom zodat het juiste beleid erop wordt toegepast.

[Apparaten in bedrijfseigendom met een IMEI-nummer opgeven](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Overzicht van registratiemethoden voor apparaten in bedrijfseigendom

De volgende tabel bevat registratiemethoden voor apparaten in bedrijfseigendom met hun voordelen.

**iOS-registratiemethoden**

| **Methode** |  **[Reset](#Reset)** |   **[Affiniteit](#Affinity)**   |   **[Vergrendeld](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nee|    Ja |   Nee |
|**[DEM](#DEM)**|   Nee |Nee |Nee  |
|**[DEP](#DEP)**|   Ja |   Opt |   Opt|
|**[USB-SA](#USB-SA)**| Ja |   Opt |   Nee|
|**[USB-Direct](#USB-Direct)**| Nee |    Nee  | Nee|

**Windows- en Android-registratiemethoden**

| **Methode** |  **[Wissen](#Wipe)** | **[Gebruiker](#User)**   |   **[Vergrendeld](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[BYOD](#BYOD)** | Nee|    Ja |   Nee |
|**[DEM](#DEM)**|   Nee |Nee |Nee  |

**Registratiemethoden voor apparaten in bedrijfseigendom**

### BYOD
Bring Your Own Device. Gebruikers installeren de bedrijfsportal-app en registreren hun apparaat. Als een apparaat met de bedrijfsportal wordt geregistreerd, wordt het apparaat toegevoegd aan de werkplek. Voor de registratie van iOS-apparaten met de bedrijfsportal is een Apple-id vereist. BYOD vereist geen aanvullende configuratie voor apparaten in bedrijfseigendom. Zie de stappen voor het [instellen van apparaatbeheer](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md). ([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))

### DEM
Apparaatregistratiebeheer. De beheerder maakt DEM-accounts. Beheerders kunnen vervolgens Bedrijfsportal installeren en veel apparaten zonder gebruiker registreren. Meer informatie over [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Apple Device Enrollment Program. De beheerder maakt en implementeert het beleid draadloos op iOS-apparaten die zijn gekocht en beheerd met DEP. Het apparaat wordt geregistreerd wanneer iOS-Configuratieassistent wordt uitgevoerd. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:
  - Vergrendelde registratie
  - Voorwaardelijke toegang
  - Jailbreakdetectie
  - Beheer van mobiele toepassingen

Meer informatie over [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))

### USB-SA
Door USB verbonden registratie met Configuratieassistent. De beheerder maakt een Intune-beleid en exporteert het beleid naar Apple Configurator. Door USB verbonden apparaten worden voorbereid met Intune-beleid. De beheerder moet elk apparaat handmatig registreren. Gebruikers ontvangen hun apparaten en voeren Configuratieassistent uit om hun apparaat te registreren. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:
  - Vergrendelde registratie
  - Voorwaardelijke toegang
  - Jailbreakdetectie
  - Beheer van mobiele toepassingen

Meer informatie over [Setup Assistant enrollment with Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (Registratie met Configuratieassistent met Apple Configurator). ([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))

### USB-Direct
Directe registratie. De beheerder maakt een Intune-beleid en exporteert het beleid naar Apple Configurator. Door USB verbonden apparaten worden direct geregistreerd zonder dat de fabrieksinstellingen hoeven worden hersteld. De beheerder moet elk apparaat handmatig registreren. De apparaten worden beheerd als apparaten zonder gebruiker. Ze zijn niet vergrendeld of onder supervisie en kunnen geen voorwaardelijke toegang, jailbreakdetectie en beheer van mobiele toepassingen ondersteunen. Meer informatie over [directe registratie met Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))

**Gedrag voor mobiele apparaten in bedrijfseigendom**

### Reset
Hiermee geeft u op of bij registratie van het apparaat de fabrieksinstellingen moeten worden hersteld, of alle gegevens van het apparaat moeten worden verwijderd en of de oorspronkelijke staat van het apparaat moet worden hersteld.
([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))

### Affiniteit
Hiermee geeft u op of de registratiemethode ondersteuning biedt voor Gebruikersaffiniteit waarmee een apparaat met een specifieke gebruiker wordt verbonden. Opt-apparaten kunnen worden geregistreerd met of zonder gebruikersaffiniteit. Gebruikersaffiniteit is vereist voor de ondersteuning van het volgende:
  - MAM-apps (Mobile Application Management)
  - Voorwaardelijke toegang tot e-mail en bedrijfsgegevens
  - Bedrijfsportal-app

([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))

### Vergrendelen
Hiermee geeft u op of het apparaat kan worden vergrendeld om te voorkomen dat de gebruiker het Intune-beleid verwijdert en dus het apparaat niet meer wordt beheerd. Voor iOS-apparaten vereist vergrendeling van het apparaat dat de modus Onder supervisie actief is.
([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods)) ([Terug naar de tabel](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO1-->


