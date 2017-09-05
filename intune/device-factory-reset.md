---
title: Apparaten met Intune terugzetten op de fabrieksinstellingen
titleSuffix: Intune on Azure
description: Meer Informatie over het terugzetten van de fabrieksinstellingen voor apparaten die u beheert met Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8eff9b53-eef2-4c50-8aee-556bc49d69f2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fd7273d6c5f75a675d7b01df4225a96fd3a5f821
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2017
---
# <a name="reset-intune-managed-devices-to-factory-settings"></a>Met Intune beheerde apparaten terugzetten op de fabrieksinstellingen


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als u de **fabrieksinstellingen** teruggezet, worden de standaardinstellingen van het apparaat hersteld. Het apparaat wordt niet meer beheerd door Intune en de bedrijfsgegevens en persoonlijke gegevens worden verwijderd. U kunt deze actie niet ongedaan maken.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: ondersteund op Windows 8.1 en hoger (niet op met EAS beheerde apparaten)
- Windows Phone: ondersteund
- iOS: ondersteund
- macOS: niet ondersteund
- Android: ondersteund (Android for Work wordt niet ondersteund)

## <a name="how-to-reset-a-device-to-factory-settings"></a>Apparaten terugzetten naar de fabrieksinstellingen

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een apparaat en kies vervolgens de externe apparaatactie **Fabrieksinstellingen**.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.
