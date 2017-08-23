---
title: iOS-modus voor een verloren apparaat activeren met Intune
titleSuffix: Intune on Azure
description: Meer informatie over het gebruik van Intune om de modus Apparaat verloren voor verloren of gestolen iOS-apparaten te activeren.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5ed792011de9109dd415ba2fac3c9428e955e5e7
ms.sourcegitcommit: 2ed8d1c39d4b3e3282111f1d758afb3a50f19f8f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>De modus Apparaat verloren activeren op iOS-apparaten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Apparaat verloren** schakelt u de modus voor verloren apparaten in op verloren of gestolen iOS-apparaten. Met deze modus kunt u een bericht en een telefoonnummer opgeven die op het vergrendelingsscherm van het apparaat worden weergeven.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: niet ondersteund
- Windows Phone: niet ondersteund
- iOS: ondersteund op iOS 9.3 of hoger, onder supervisie, en bedrijfseigendom
- macOS: niet ondersteund
- Android: niet ondersteund

## <a name="how-to-activate-lost-mode"></a>De modus Apparaat verloren activeren

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een iOS-apparaat en kies vervolgens de externe actie **Modus Apparaat verloren**.
6. Schakel op de blade **Modus Apparaat verloren** de modus Apparaat verloren in. Voer vervolgens het weer te geven bericht in en eventueel een telefoonnummer van de contactpersoon.
7. Klik op **OK**.

Wanneer u de modus Apparaat verloren inschakelt, wordt het gebruik van het apparaat volledig geblokkeerd. De gebruiker krijgt pas weer toegang tot het apparaat als de modus Apparaat verloren is uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de bewerking **Apparaat zoeken** uitvoeren om te weten te komen waar het apparaat is.
Als u de modus Apparaat verloren apparaat wilt gebruiken, moet het apparaat in een iOS-apparaat in bedrijfseigendom zijn waarop de supervisiemodus is ingeschakeld.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Beveiligings- en privacygegevens voor de acties modus Apparaat verloren en Apparaat zoeken
- Er wordt geen locatie-informatie over het apparaat verzonden naar Intune voordat u deze actie hebt ingeschakeld.
- Wanneer u de actie Apparaat zoeken gebruikt, worden de lengte- en breedtegraadcoördinaten van het apparaat verzonden naar Intune en weergegeven in Azure Portal.
- De gegevens worden gedurende 24 uur opgeslagen, waarna ze worden verwijderd. U kunt de locatiegegevens niet handmatig verwijderen.
- De locatiegegevens worden versleuteld terwijl ze zijn opgeslagen en terwijl ze worden verzonden.
- U wordt aangeraden het bericht dat wordt weergegeven op het vergrendelingsscherm, van informatie te voorzien, op basis waarvan het apparaat kan worden teruggegeven.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.

