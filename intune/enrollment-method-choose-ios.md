---
title: Kiezen hoe u iOS-apparaten registreert in Intune
titleSuffix: Intune on Azure
description: Meer informatie over hoe u het registreren van iOS-apparaten in Microsoft Intune instelt."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="choose-how-to-enroll-ios-and-macos-devices"></a>Kiezen hoe u iOS- en macOS-apparaten inschrijft

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dit onderwerp bevat informatie over de methoden die een IT-beheerder kan gebruiken om inschrijving van iOS-apparaten in Intune in te schakelen.

Gebruik de volgende informatie om te bepalen welke methode u wilt gebruiken voor het registreren van iOS-apparaten. Alle hieronder vermelde methoden, met uitzondering van BYOD, zijn bestemd voor de registratie van apparaten die eigendom van het bedrijf zijn.

**Vereiste:** een [Apple Push Notification Service-certificaat](apple-mdm-push-certificate-get.md).

## <a name="user-owned-ios-devices-byod"></a>iOS-apparaten die het eigendom van gebruikers zijn (BYOD)

Als gebruikers hun eigen BYOD-apparaten (Bring Your Own Device) willen registreren, kunnen zij de bedrijfsportal-app voor iOS uit de App Store downloaden en de registratie-instructies in de app volgen. Na de registratie kunnen gebruikers verbinding maken met het bedrijfsnetwerk, deelnemen aan het domein of Azure Active Directory en toegang tot bedrijfsresources krijgen. Als u BYOD wilt inschakelen, is alleen een [Apple Push Notification-servicecertificaat](apple-mdm-push-certificate-get.md) vereist. U kunt ook de inschrijving blokkeren van iOS-apparaten die het eigendom van de gebruiker zijn. Zie [Beperkingen voor apparaattypen instellen](enrollment-restrictions-set.md) voor instructies.

## <a name="user-owned-macos-devices-byod"></a>macOS-apparaten die het eigendom van gebruikers zijn (BYOD)

U kunt de inschrijving van macOS-apparaten inschakelen. Als u macOS-inschrijving wilt inschakelen, is alleen een [Apple Push Notification-servicecertificaat](apple-mdm-push-certificate-get.md) vereist. Zie [macOS-apparaten inschrijven](./macos-enroll.md) voor meer informatie

## <a name="enrollment-program-with-apple"></a>Inschrijvingsprogramma met Apple uitvoeren
Apple biedt programma's aan voor de aanschaf van apparaten die apparaatinschrijving en beheerinfrastructuur bevatten. Apparaten die via een van deze programma's zijn gekocht, kunt u draadloos bulksgewijs inschrijven door de serienummers van de apparaten toe te wijzen aan de beheerfunctie van Intune.

- **Device Enrollment Program (DEM)**: het apparaatinschrijvingsprogramma van Apple voor organisaties en bedrijven. Zie [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md) (iOS-apparaten registreren met het programma voor apparaatregistratie (DEP)) voor meer informatie.
- **Apple School Manager**: het apparaatinschrijvingsprogramma van Apple voor scholen. Zie [Inschrijving van iOS-apparaten inschakelen met Apple School Manager](apple-school-manager-set-up-ios.md) voor meer informatie.

## <a name="apple-configurator"></a>Apple Configurator

iOS-apparaten kunnen worden ingeschreven door een inschrijvingsprofiel voor bedrijfsapparaten te exporteren en deze mobiele apparaten vervolgens te verbinden met een Mac-computer waarop Apple Configurator wordt uitgevoerd. Apple Configurator ondersteunt twee soorten inschrijvingen:

- **Inschrijving met configuratieassistent** : de fabrieksinstellingen worden hersteld en het apparaat wordt voorbereid voor configuratie door de nieuwe gebruiker. Voor deze methode moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop Apple Configurator wordt uitgevoerd om de registratie vooraf te configureren. Apparaten wordt vervolgens geleverd aan de gebruikers die Configuratieassistent uitvoeren wanneer het apparaat voor het eerst wordt opgestart. Met dit proces wordt het apparaat geconfigureerd met de werk- of schoolreferenties van gebruikers en wordt het registratieproces voltooid. Zie [Enroll iOS devices with Apple Configurator and Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md) (iOS-apparaten registreren met Apple Configurator en Configuratieassistent) voor meer informatie.

- **Directe inschrijving**: maakt een Apple Configurator-compatibel bestand dat tijdens de voorbereiding van het apparaat wordt gebruikt. Het geregistreerde apparaat krijgt niet opnieuw de fabrieksinstellingen en het is niet meer gekoppeld aan de gebruiker. Om apparaten te registreren moet de beheerder een USB-verbinding maken tussen het iOS-apparaat en een Mac-computer waarop Apple Configurator wordt uitgevoerd. Zie [Enroll iOS devices using Apple Configurator Direct Enrollment (iOS-apparaten inschrijven met directe inschrijving via Apple Configurator)](apple-configurator-direct-enroll-ios.md) voor meer informatie.

## <a name="use-the-device-enrollment-program-dep"></a>Het apparaatinschrijvingsprogramma (DEP) gebruiken

DEP implementeert een draadloos inschrijvingsprofiel voor apparaten die zijn gekocht via DEP. Wanneer een gebruiker Configuratieassistent uitvoert op het apparaat wanneer dit voor de eerste keer wordt opgestart, wordt het apparaat ingeschreven bij Intune. Zie [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md) (iOS-apparaten registreren met het programma voor apparaatregistratie (DEP)) voor meer informatie.

## <a name="use-the-device-enrollment-manager-dem"></a>DEM (apparaatinschrijvingsmanager) gebruiken
De apparaatinschrijvingsmanager is een algemeen gebruikersaccount waarmee maximaal 1000 apparaten kunnen worden geregistreerd en beheerd. Met DEM beheerde apparaten hebben geen affiniteit met de gebruikers, zodat het apparaat nooit een eigenaar heeft. U verleent DEM-machtigingen aan Intune-gebruikers om hen deze mogelijkheden te geven. Bij elk apparaat dat door de DEM-gebruiker wordt geregistreerd, wordt een Intune-licentie gebruikt. Zie [Enroll devices using device enrollment manager](device-enrollment-manager-enroll.md) (Apparaten registreren met de apparaatinschrijvingsmanager) voor meer informatie.
