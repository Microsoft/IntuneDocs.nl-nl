---
title: Kiezen hoe u Windows-apparaten registreert in Intune
titlesuffix: Azure portal
description: Meer informatie over hoe u het registreren van Windows-apparaten in Microsoft Intune instelt."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bcdaa30df09313d3eda96410b6b394f1a0029d3
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/04/2018
---
# <a name="enroll-ios-devices-in-intune"></a>iOS-apparaten registreren bij Intune

Intune maakt Mobile Device Management (MDM) mogelijk voor iPads en iPhones en geeft gebruikers toegang tot zakelijke e-mail en apps.

Als Intune-beheerder kunt u registratie inschakelen voor iOS-apparaten. U kunt gebruikers toestaan persoonlijke apparaten te registreren. Dit wordt ook wel BYOD-registratie (‘Bring Your Own Device’) genoemd. U kunt ook de registratie van apparaten in bedrijfseigendom inschakelen.

## <a name="prerequisites-for-ios-enrollment"></a>Vereisten voor iOS-registratie
Voordat u de registratie van iOS-apparaten kunt inschakelen, moet u de volgende stappen uitvoeren:
- [Intune instellen](setup-steps.md): hiermee stelt u de Intune-infrastructuur in. Voor apparaatinschrijving is met name het [instellen van uw MDM-instantie](mdm-authority-set.md) van belang.
- [Een Apple MDM-pushcertificaat ophalen](apple-mdm-push-certificate-get.md): Apple vereist een certificaat voor het inschakelen van het beheer van iOS- en macOS-apparaten.

## <a name="user-owned-ios-devices-byod"></a>iOS-apparaten die het eigendom van gebruikers zijn (BYOD)

U kunt gebruikers hun persoonlijke apparaten laten inschrijven voor Intune-beheer, wat 'Bring Your Own Device' of BYOD wordt genoemd. Zodra u aan de vereisten hebt voldaan en gebruikerslicenties hebt toegewezen, kunnen ze in de App Store de iOS-bedrijfsportal-app downloaden en in de app de inschrijvingsinstructies volgen.

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
