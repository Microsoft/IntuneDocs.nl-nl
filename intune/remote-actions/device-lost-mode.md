---
title: De modus Apparaat verloren voor iOS-apparaten activeren met Microsoft Intune - Azure | Microsoft Docs
description: Activeer of open de modus Apparaat verloren om met Microsoft Intune een bericht in te stellen voor weergave op het vergrendelingsscherm van een verloren of gestolen iOS-apparaat. U ontvangt ook meer informatie over beveiliging en privacy wanneer u de modus Apparaat verloren gebruikt.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 34a4c8adeef7e8b28c90ad38579f0f9ac7c4784d
ms.sourcegitcommit: 807ab3e35f4d9ffa18655410b7d61e5e772ab348
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057531"
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>De modus Apparaat verloren inschakelen op iOS-apparaten met Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met de apparaatactie **Apparaat verloren** schakelt u de modus voor verloren apparaten in op verloren of gestolen iOS-apparaten. Met deze modus kunt u een bericht en een telefoonnummer opgeven die op het vergrendelingsscherm van het apparaat worden weergeven. Als u de modus Apparaat verloren apparaat wilt gebruiken, moet het apparaat in een iOS-apparaat in bedrijfseigendom zijn waarop de supervisiemodus is ingeschakeld.

## <a name="supported-platforms"></a>Ondersteunde platforms

- iOS 9.3 en hoger

Deze functie wordt niet ondersteund op: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>De modus Apparaat verloren inschakelen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Kies in de lijst met door u beheerde apparaten een iOS-apparaat en kies vervolgens de externe actie **Modus apparaat verloren (alleen onder toezicht)** .
5. Selecteer in de **Modus apparaat verloren** de optie **Inschakelen**.
6. Typ in het **Weergegeven bericht op het vergrendelingsscherm** een bericht dat moet worden weergegeven op het vergrendelingsscherm van het apparaat.
7. Geef eventueel een telefoonnummer op in het vak **Weergegeven telefoonnummer**.
6. Selecteer **OK** om uw wijzigingen op te slaan.

Wanneer u de modus Apparaat verloren inschakelt, wordt het gebruik van het apparaat volledig geblokkeerd. De gebruiker krijgt pas weer toegang tot het apparaat als de modus Apparaat verloren is uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de actie [Apparaat zoeken](device-locate.md) gebruiken om het apparaat te zoeken.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Beveiligings- en privacygegevens voor de acties modus Apparaat verloren en Apparaat zoeken
- Er wordt geen locatie-informatie over het apparaat verzonden naar Intune voordat u deze actie hebt ingeschakeld.
- Wanneer u de actie Apparaat zoeken gebruikt, worden de lengte- en breedtegraadcoördinaten van het apparaat verzonden naar Intune en weergegeven in Azure Portal.
- De gegevens worden gedurende 24 uur opgeslagen, waarna ze worden verwijderd. U kunt de locatiegegevens niet handmatig verwijderen.
- De locatiegegevens worden versleuteld terwijl ze zijn opgeslagen en terwijl ze worden verzonden.
- In het bericht dat u invoert voor weergave op het vergrendelingsscherm, moet u ook specifieke informatie opgeven voor het retourneren van het apparaat.

## <a name="next-steps"></a>Volgende stappen

Als u de inschakelingsstatus van de modus Apparaat verloren wilt bekijken, opent u **Apparaten** en selecteert u **Apparaatacties**.
