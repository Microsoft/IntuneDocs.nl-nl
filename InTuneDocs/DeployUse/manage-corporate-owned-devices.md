---
# required metadata

title: Apparaten in bedrijfseigendom beheren met Microsoft Intune | Microsoft Intune
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

# Apparaten in bedrijfseigendom inschrijven in Microsoft Intune
Apparaten in organisatie- of bedrijfseigendom (COD) kunnen op verschillende manieren worden beheerd, afhankelijk van het apparaat en hoe dit apparaat is aangeschaft.

## iOS-apparaten in bedrijfseigendom
Deze inschrijvingsmethoden zijn geschikt voor CYOD-scenario‘s (Choose Your Own Device), waarbij de organisatie de apparaten koopt voor gebruikers, maar het beheer van de apparaten bij de organisatie blijft. Als uw organisatie iOS-apparaten heeft aangeschaft, kunt u deze vooraf inschrijven, zodat een apparaat wordt beheerd vanaf de eerste keer dat de gebruiker het inschakelt. Intune ondersteunt inschrijving via het [Device Enrollment Program (DEP) van Apple](ios-device-enrollment-program-in-microsoft-intune.md) of met behulp van het hulpprogramma Apple Configurator, dat wordt uitgevoerd op een Mac-computer voor [directe](ios-direct-enrollment-in-microsoft-intune.md) inschrijving of inschrijving met de [Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[iOS-apparaten in bedrijfseigendom inschrijven](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Apparaatinschrijvingsmanager
Organisaties kunnen Intune gebruiken voor het beheren van een groot aantal mobiele apparaten met één gebruikersaccount (een zogenaamd apparaatinschrijvingsmanageraccount. Na het maken van een apparaatinschrijvingsmanageraccount kan dit account door een manager worden gebruikt om meer apparaten in te schrijven dan de vijf apparaten die standaard zijn toegestaan voor reguliere gebruikers. Het inschrijven van apparaten via een apparaatinschrijvingsmanageraccount werkt alleen voor apparaten die niet worden gebruikt door een specifieke gebruiker. Dergelijke apparaten zijn bijvoorbeeld geschikt voor gebruik in een verkooppunt of met hulpprogramma-apps, maar niet voor gebruikers die toegang nodig hebben tot e-mail of bedrijfsresources.

[Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsmanager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Apparaten in bedrijfseigendom met een IMEI-nummer opgeven
Een uniek IMEI-nummer (IMEI staat voor International Mobile Equipment Identity) is voor veel fabrikanten van mobiele apparaten een algemene apparaateigenschap. Intune-beheerders kunnen IMEI-nummers importeren voor apparaten die eigendom zijn van het bedrijf. Wanneer het apparaat wordt beheerd met Intune, kan het worden gemarkeerd als apparaat in bedrijfseigendom en het juiste beleid erop worden toegepast.

[Apparaten in bedrijfseigendom met een IMEI-nummer opgeven](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)


<!--HONumber=May16_HO1-->


