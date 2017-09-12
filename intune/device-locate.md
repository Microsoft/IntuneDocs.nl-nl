---
title: Verloren iOS-apparaat zoeken met Intune
titlesuffix: Azure portal
description: Meer informatie over hoe verloren of gestolen iOS-apparaten kunt zoeken met Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1d38906ef14a97043dc97ff9149cd602cd4de120
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Verloren of gestolen iOS-apparaten zoeken met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Apparaat zoeken** geeft u de locatie van een verloren of gestolen iOS-apparaat op een kaart weer. Het apparaat moet een iOS-apparaat in bedrijfseigendom zijn, dat via DEP is ingeschreven en waarop de supervisiemodus is ingeschakeld. Voordat u deze actie gebruikt, moet op het apparaat de modus [Apparaat verloren](/intune-azure/manage-devices/lost-mode.md) zijn ingeschakeld.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: niet ondersteund
- Windows Phone: niet ondersteund
- iOS: ondersteund op iOS 9.3 of hoger (in modus Apparaat verloren), onder supervisie, en bedrijfseigendom
- macOS: niet ondersteund
- Android: niet ondersteund

## <a name="how-to-locate-a-lost-or-stolen-device"></a>Apparaten lokaliseren die vermist worden of gestolen zijn

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een iOS-apparaat en kies vervolgens de externe aparaatactie **Apparaat zoeken**.
6. Als het apparaat is gevonden, wordt de locatie weergegeven op de blade **Apparaat zoeken**.
    ![De blade Apparaat zoeken](./media/locate-device.png)

>[!NOTE]
>De afstand die u op de kaart kunt inzoomen, is om privacyredenen beperkt.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Beveiligings- en privacygegevens voor de acties modus Apparaat verloren en Apparaat zoeken
- Er wordt geen locatie-informatie over het apparaat verzonden naar Intune voordat u deze actie hebt ingeschakeld.
- Wanneer u de actie Apparaat zoeken gebruikt, worden de lengte- en breedtegraadcoördinaten van het apparaat verzonden naar Intune en weergegeven in Azure Portal.
- De gegevens worden gedurende 24 uur opgeslagen, waarna ze worden verwijderd. U kunt de locatiegegevens niet handmatig verwijderen.
- De locatiegegevens worden versleuteld terwijl ze zijn opgeslagen en terwijl ze worden verzonden.
- Wanneer u de modus Apparaat verloren configureert, kunt u voor het bericht dat wordt weergegeven op het vergrendelingsscherm, het beste informatie opgeven op basis waarvan het apparaat kan worden teruggegeven.


## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.