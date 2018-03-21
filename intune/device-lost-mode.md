---
title: De modus Apparaat verloren voor iOS-apparaten activeren met Microsoft Intune - Azure | Microsoft Docs
description: Activeer of open de modus Apparaat verloren om met Microsoft Intune een bericht in te stellen voor weergave op het vergrendelingsscherm van een verloren of gestolen iOS-apparaat. U ontvangt ook meer informatie over beveiliging en privacy wanneer u de modus Apparaat verloren gebruikt.
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47d6314dfaed546e5b4cff7f93a5540ba512bde9
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="enable-lost-mode-on-ios-devices-with-intune"></a>De modus Apparaat verloren inschakelen op iOS-apparaten met Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Apparaat verloren** schakelt u de modus voor verloren apparaten in op verloren of gestolen iOS-apparaten. Met deze modus kunt u een bericht en een telefoonnummer opgeven die op het vergrendelingsscherm van het apparaat worden weergeven. Als u de modus Apparaat verloren apparaat wilt gebruiken, moet het apparaat in een iOS-apparaat in bedrijfseigendom zijn waarop de supervisiemodus is ingeschakeld.

## <a name="supported-platforms"></a>Ondersteunde platforms

- iOS 9.3 en hoger

Deze functie wordt **niet** ondersteund op: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="enable-lost-mode"></a>De modus Apparaat verloren inschakelen

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Kies in de lijst met apparaten die u beheert, een iOS-apparaat, kies **...Meer**en kies vervolgens de externe actie **Modus Apparaat verloren**.
5. In de **modus Apparaat verloren** schakelt u deze functie in. Voer vervolgens het weer te geven bericht in en voeg het telefoonnummer van de contactpersoon toe.
6. Selecteer **OK** om uw wijzigingen op te slaan.

Wanneer u de modus Apparaat verloren inschakelt, wordt het gebruik van het apparaat volledig geblokkeerd. De gebruiker krijgt pas weer toegang tot het apparaat als de modus Apparaat verloren is uitgeschakeld. Als de modus Apparaat verloren is ingeschakeld, kunt u de actie [Apparaat zoeken](device-locate.md) gebruiken om het apparaat te zoeken.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Beveiligings- en privacygegevens voor de acties modus Apparaat verloren en Apparaat zoeken
- Er wordt geen locatie-informatie over het apparaat verzonden naar Intune voordat u deze actie hebt ingeschakeld.
- Wanneer u de actie Apparaat zoeken gebruikt, worden de lengte- en breedtegraadcoördinaten van het apparaat verzonden naar Intune en weergegeven in Azure Portal.
- De gegevens worden gedurende 24 uur opgeslagen, waarna ze worden verwijderd. U kunt de locatiegegevens niet handmatig verwijderen.
- De locatiegegevens worden versleuteld terwijl ze zijn opgeslagen en terwijl ze worden verzonden.
- In het bericht dat u invoert voor weergave op het vergrendelingsscherm moet u ook specifieke informatie opgeven voor het retourneren van het apparaat.

## <a name="next-steps"></a>Volgende stappen

Als u de inschakelingsstatus van de modus Apparaat verloren wilt bekijken, opent u **Apparaten** en selecteert u **Apparaatacties**.