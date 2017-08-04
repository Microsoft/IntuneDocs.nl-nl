---
title: Aan de slag met apps
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 71093f8ac17fc6d6938f5c263a40204f89419726
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="getting-started-with-apps"></a>Aan de slag met apps

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune ondersteunt een aantal verschillende manieren om apps te implementeren op apparaten die bedrijfseigendom zijn:

* **Software-installatieprogramma's**: u uploadt een uitvoerbaar bestand dat wordt gedownload naar de apparaten van gebruikers
* __Externe koppelingen__: voor een app in een openbare App Store of voor een web-app
* **Beheerde apps**: voor iOS-apparaten waarvoor u extra Mobile Application Management wilt toepassen op apps die beschikbaar zijn in de App Store

U kiest voor een van de snellere methoden voor het implementeren van een toepassing als u een app uit een openbare App Store toewijst.

__Hoe wijs ik een app uit een openbare App Store toe?__

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Gebruik **Resources zoeken** om te zoeken naar **Intune**.
3. Selecteer **Mobile Apps** en selecteer daarna **Apps**.
4. Selecteer **Toevoegen** en kies **iOS Store-app** bij **Type app**.
5. Gebruik het tekstvak om te zoeken naar een app die u wilt toewijzen aan het apparaat. Kies de app en selecteer vervolgens **OK**.
6. Selecteer **App-gegevens** op de blade **App toevoegen** en vul vervolgens alle gegevens van de app in. U kunt andere, optionele gegevens toevoegen om de app beter te organiseren. Zo kunt u waarden opgeven voor **Eigenaar**, **Opmerkingen**, **Ontwikkelaar** en **Privacy-URL**. Via deze URL kunnen gebruikers het privacybeleid van uw bedrijf weergeven.
7. Vergeet niet om Ja te selecteren voor de optie Deze weergeven als aanbevolen app in de bedrijfsportal, en selecteer vervolgens OK.
8. Selecteer **Toevoegen** om de app toe te voegen. U ziet nu de pagina **Overzicht** van de app. Kies **Toewijzingen** en klik vervolgens op **Groepen selecteren** om de app toe te wijzen aan uw testgroep. Selecteer **Beschikbaar** zodat de app kan worden gedownload. De app moet nu worden weergegeven bij **Aanbevolen app** op uw testapparaat.
