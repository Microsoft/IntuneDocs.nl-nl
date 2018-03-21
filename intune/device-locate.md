---
title: Verloren iOS-apparaten zoeken met Microsoft Intune - Azure | Microsoft Docs
description: Zoek of lokaliseer verloren of gestolen iOS-apparaten met de functie Apparaat zoeken in Microsoft Intune. Met de actie Apparaat zoeken krijgt u ook informatie over de beveiliging en privacy.
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4bc51ef7f9af9cc97fd4c11408a1857679aee665
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Verloren of gestolen iOS-apparaten zoeken met Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik de actie **Apparaat zoeken** om de locatie van een verloren of gestolen iOS-apparaat op een kaart weer te geven. Het apparaat moet een iOS-apparaat in bedrijfseigendom zijn, dat via het apparaatinschrijvingsprogramma (DEP) is ingeschreven en waarop de supervisiemodus is ingeschakeld. Voordat u deze actie gebruikt, zorgt u ervoor dat voor het apparaat de [modus Apparaat verloren](device-lost-mode.md) is ingeschakeld.

## <a name="supported-platforms"></a>Ondersteunde platforms

- iOS 9.3 en hoger

Deze functie wordt **niet** ondersteund op de volgende systemen: 
- Windows
- Windows Phone
- macOS
- Android

## <a name="locate-a-lost-or-stolen-device"></a>Verloren of gestolen apparaten lokaliseren

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Kies in de lijst met apparaten die u beheert, een iOS-apparaat, kies **...Meer** en kies vervolgens de externe apparaatactie **Apparaat zoeken**.
5. Wanneer het apparaat is gevonden, wordt de locatie weergegeven in **Apparaat zoeken**.
    ![Apparaat zoeken met behulp van Intune in Azure](./media/locate-device.png)

>[!NOTE]
>De afstand die u op de kaart kunt inzoomen, is om privacyredenen beperkt.

## <a name="security-and-privacy-information-for-lost-mode-and-locate-device-actions"></a>Beveiligings- en privacygegevens voor de modus Apparaat verloren en de actie Apparaat zoeken
- Er wordt geen locatie-informatie over het apparaat verzonden naar Intune voordat u deze actie hebt ingeschakeld.
- Wanneer u de actie Apparaat zoeken gebruikt, worden de lengte- en breedtegraadcoördinaten van het apparaat verzonden naar Intune en weergegeven in Azure Portal.
- De gegevens worden gedurende 24 uur opgeslagen, waarna ze worden verwijderd. U kunt de locatiegegevens niet handmatig verwijderen.
- De locatiegegevens worden versleuteld terwijl ze zijn opgeslagen en terwijl ze worden verzonden.
- Bij het configureren van de modus Apparaat verloren kunt u een bericht opstellen dat moet worden weergegeven op het vergrendelingsscherm. Zorg ervoor dat u in dit bericht specifieke informatie typt zodat de persoon die het apparaat vindt, weet wat er moet gebeuren om het apparaat te retourneren.

## <a name="next-steps"></a>Volgende stappen

Als u de inschakelingsstatus van Apparaat zoeken wilt bekijken, opent u **Apparaten** en selecteert u **Apparaatacties**.
