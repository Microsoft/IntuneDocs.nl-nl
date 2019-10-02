---
title: Supervisiemodus voor iOS inschakelen met Microsoft Intune
titleSuffix: ''
description: Meer informatie over het inschakelen van de supervisiemodus voor iOS met Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8190814-07f0-42d8-9b3a-87c67dd2b7ed
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 79e6ba1541a516b36ae4bd02cf9f60f1a12c8896
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728439"
---
# <a name="turn-on-ios-supervised-mode"></a>Supervisiemodus voor iOS inschakelen


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met de supervisiemodus voor Apple iOS beschikken beheerders over meer opties voor het beheer van Apple-apparaten, wat handig is voor apparaten in bedrijfseigendom die op schaal zijn geïmplementeerd. U kunt bijvoorbeeld AirDrop beperken of voorkomen dat gebruikers de naam van het apparaat kunnen wijzigen. Zie [iOS-apparaatbeperkingsinstellingen in Intune](../configuration/device-restrictions-ios.md) voor een lijst met instellingen waarvoor de supervisiemodus is vereist.

Intune ondersteunt de supervisiemodus als onderdeel van het [Device Enrollment Program (DEP)](../enrollment/device-enrollment-program-enroll-ios.md) van Apple.

Zie [Informatie over payloadinstellingen](http://help.apple.com/configurator/mac/2.4/#/cad5370d089) van Apple voor een lijst met besturingselementen van Apple waarvoor supervisie is vereist.

## <a name="turn-on-supervised-mode-during-enrollment"></a>De supervisiemodus inschakelen tijdens de inschrijving

In Intune kunt u de supervisiemodus voor apparaten inschakelen wanneer u [een Apple-inschrijvingsprofiel maakt in DEP](../enrollment/device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile). Schakel onder **Instellingen voor apparaatbeheer** het selectievakje **Onder supervisie** in.

## <a name="turn-on-supervised-mode-after-enrollment"></a>De supervisiemodus inschakelen na de inschrijving

Na de registratie kan de supervisiemodus alleen worden ingeschakeld door een iOS-apparaat op een Mac aan te sluiten en [Apple Configurator te gebruiken](../enrollment/apple-configurator-enroll-ios.md) (hiermee wordt het apparaat opnieuw ingesteld). U kunt een apparaat niet na de inschrijving voor de supervisiemodus in Intune configureren.

## <a name="identify-a-supervised-device"></a>Een apparaat onder supervisie identificeren

Als u wilt zien of een apparaat onder supervisie is, controleert u het vergrendelingsscherm of de pagina **Info**:
- Op het vergrendelingsscherm van het apparaat verschijnt de melding **Deze iPhone wordt beheerd door <Bedrijfsnaam>.**
- Op de pagina **Info** van het apparaat verschijnt de melding **Deze iPhone is onder supervisie. <Bedrijfsnaam> kan uw internetverkeer bijhouden en de locatie van dit apparaat bepalen.**

## <a name="next-steps"></a>Volgende stappen

Zie [Wat is Microsoft Intune-apparaatbeheer?](device-management.md) voor meer opties voor apparaatbeheer.
