---
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
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 69cf07aa0747448e0ef3384b5b5132e0e76aed45
ms.openlocfilehash: e07053b9b26afacc03e45f2cb104eda6088a1e05


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

[Apparaten in bedrijfseigendom met een IMEI-nummer opgeven](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jun16_HO5-->


