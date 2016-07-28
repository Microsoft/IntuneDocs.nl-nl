---
title: Apparaten in bedrijfseigendom beheren | Microsoft Intune
description: Apparaten in bedrijfseigendom (COD) kunnen op verschillende manieren worden beheerd, afhankelijk van het apparaat en hoe dit apparaat is aangeschaft, en de behoeften van de organisatie.
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ac7d52c0ad3e37e517b60d448a94849c0f4b30
ms.openlocfilehash: 6cf620a96b39540c8b7ca618936af1367971bb8f


---

# Apparaten in bedrijfseigendom registreren met Microsoft Intune
Apparaten in organisatie- of bedrijfseigendom kunnen op verschillende manieren worden geregistreerd voor beheer door Intune, afhankelijk van het apparaat, hoe dit apparaat is aangeschaft en wat de behoeften van de organisatie zijn.

## iOS-apparaten in bedrijfseigendom
Deze registratiemethoden zijn geschikt voor CYOD-scenario's (Choose Your Own Device), waarbij de organisatie de apparaten koopt voor gebruikers, maar het beheer van de apparaten bij de organisatie blijft. Als uw organisatie iOS-apparaten heeft aangeschaft, kunt u deze vooraf registreren, zodat een apparaat wordt beheerd vanaf de eerste keer dat de gebruiker het inschakelt. Intune ondersteunt registratie via het [Device Enrollment Program (DEP) van Apple](ios-device-enrollment-program-in-microsoft-intune.md) of met behulp van het hulpprogramma Apple Configurator, dat wordt uitgevoerd op een Mac-computer voor [directe](ios-direct-enrollment-in-microsoft-intune.md) registratie of registratie met de [Configuratieassistent](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[iOS-apparaten van het bedrijf inschrijven](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Apparaatinschrijvingsmanager
Organisaties kunnen Intune gebruiken voor het beheer van een groot aantal mobiele apparaten met één gebruikersaccount (een zogenaamd apparaatregistratiebeheeraccount). Nadat een apparaatregistratiebeheeraccount is gemaakt, kan dit account door een beheerder worden gebruikt om meer apparaten te registreren dan de vijf apparaten die standaard zijn toegestaan voor reguliere gebruikers. De registratie van apparaten via apparaatregistratiebeheer werkt alleen voor apparaten die niet worden gebruikt door een specifieke gebruiker. Dergelijke apparaten zijn bijvoorbeeld geschikt voor gebruik in een verkooppunt of met utiliteitsapps, maar niet voor gebruikers die toegang nodig hebben tot e-mail of bedrijfsbronnen.

[Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsbeheerder](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Windows 10-desktops in bedrijfseigendom inschrijven

Als uw organisatie Azure Active Directory Premium (AADP) of Enterprise Management-pakket (EMS) heeft, kunt u [Windows 10 Enterprise inschrijven](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview). Deze worden automatisch gemarkeerd als 'bedrijfseigendom' wanneer gebruikers hun werk- of schoolaccount toevoegen.

## Apparaten identificeren als bedrijfseigendom

Apparaten in bedrijfseigendom zijn opgenomen als **Zakelijk**  onder **Eigendom** in een lijst met apparaten. Apparaten kunnen op de volgende manieren worden geïdentificeerd als bedrijfseigendom:

 - [Ingeschreven met apparaatregistratiebeheer (DEM)](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Ingeschreven met het Apple-[apparaatregistratieprogramma (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) of [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)
 - [Apparaten labelen met IMEI-nummers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [Windows 10-apparaten inschrijven via Azure Active Directory/Enterprise Management-pakket](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### IMEI (International Mobile Equipment Identity)

Een uniek IMEI-nummer (International Mobile Equipment Identity) is voor veel fabrikanten van mobiele apparaten een algemene apparaateigenschap. Intune-beheerders kunnen IMEI-nummers importeren voor apparaten die eigendom zijn van het bedrijf. Wanneer het apparaat wordt beheerd met Intune, wordt het gelabeld als apparaat in bedrijfseigendom.

[Apparaten in bedrijfseigendom met een IMEI-nummer opgeven](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO3-->


