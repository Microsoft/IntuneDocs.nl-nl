---
title: Verloren iOS-apparaten zoeken met Microsoft Intune - Azure | Microsoft Docs
description: Verloren of gestolen iOS-apparaten zoeken met behulp van de functie Apparaat zoeken in Microsoft Intune. Ontvang meer informatie over beveiliging en privacy wanneer u de actie Apparaat zoeken gebruikt.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/24/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4e3ab83c282c1e97e80a783f569410253bdf7d42
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727945"
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Verloren of gestolen iOS-apparaten zoeken met Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gebruik de actie **Apparaat zoeken** om de locatie van een verloren of gestolen iOS-apparaat op een kaart weer te geven. Het apparaat moet in de supervisiemodus staan. Voordat u deze actie gebruikt, zorgt u ervoor dat voor het apparaat de [modus Apparaat verloren](device-lost-mode.md) is ingeschakeld.

## <a name="supported-platforms"></a>Ondersteunde platforms

- iOS 9.3 en hoger

Deze functie wordt niet ondersteund op de volgende systemen: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Verloren of gestolen apparaten lokaliseren

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Kies een iOS-apparaat in de lijst met apparaten die u beheert en kies **...Meer**. Kies vervolgens de externe actie **Apparaat zoeken**.
5. Wanneer het apparaat is gevonden, wordt de locatie weergegeven in **Apparaat zoeken**.
    ![Schermopname van Apparaat zoeken met behulp van Intune in Azure](./media/device-locate/locate-device.png)


## <a name="activate-lost-mode-sound-alert-on-an-ios-device"></a>Geluidssignaal voor de modus Apparaat verloren activeren op een iOS-apparaat

Als iemand een iOS 9.3-apparaat of later heeft verloren, kunt u het apparaat extern activeren om een geluidssignaal af te spelen zodat de gebruiker het apparaat kan vinden. Het apparaat moet de [modus Apparaat verloren](device-lost-mode.md) hebben.

Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de opties **Apparaten** > **Alle apparaten** > selecteer een iOS-apparaat > **Overzicht** > **Meer** > **Afspelen in de modus Apparaat verloren (alleen onder supervisie)** .

Het geluid wordt afgespeeld totdat de gebruiker het geluid uitschakelt op het apparaat of totdat het apparaat niet meer de modus Apparaat verloren heeft.


## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Beveiligings- en privacygegevens voor de modus Apparaat verloren en de actie Apparaat zoeken
- Er wordt geen locatie-informatie over het apparaat verzonden naar Intune voordat u deze actie hebt ingeschakeld.
- Wanneer u de actie Apparaat zoeken gebruikt, kunnen de lengte- en breedtegraadcoördinaten van het apparaat worden opgehaald met de Graph API.
- De gegevens worden gedurende 24 uur opgeslagen, waarna ze worden verwijderd. U kunt de locatiegegevens niet handmatig verwijderen.
- De locatiegegevens worden versleuteld terwijl ze zijn opgeslagen en terwijl ze worden verzonden.
- Bij het configureren van de modus Apparaat verloren kunt u een bericht opstellen dat moet worden weergegeven op het vergrendelingsscherm. Zorg ervoor dat u in dit bericht specifieke informatie typt zodat de persoon die het apparaat vindt, weet wat er moet gebeuren om het apparaat te retourneren.

## <a name="next-steps"></a>Volgende stappen

Als u de inschakelingsstatus van Apparaat zoeken wilt bekijken, opent u **Apparaten** en selecteert u **Apparaatacties**.
