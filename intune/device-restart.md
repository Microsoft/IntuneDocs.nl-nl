---
title: Apparaten opnieuw opstarten met Microsoft Intune - Azure | Microsoft Docs
description: Gebruik de externe actie Opnieuw opstarten om Windows- en iOS-apparaten opnieuw op te starten met Microsoft Intune in Azure Portal.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b09a4d528a95d682bf12e6610480b1aa1bcbdb83
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31829313"
---
# <a name="remotely-restart-devices-with-intune"></a>Apparaten extern opnieuw opstarten met Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

De apparaatactie **Opnieuw opstarten** zorgt ervoor dat het apparaat dat kiest, opnieuw wordt opgestart. De eigenaar van het apparaat wordt niet op de hoogte gesteld dat het apparaat opnieuw wordt opgestart. Hierdoor kan eventueel werk verloren gaan.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: ondersteund op Windows 8.1 en hoger
- Windows Phone: ondersteund op Windows 8.1 en hoger
- iOS: ondersteund

    > [!Note]  
    > Voor deze opdracht is een apparaat onder supervisie en het vereist toegangsrecht **Apparaatvergrendeling** vereist. Het apparaat wordt onmiddellijk opnieuw opgestart. iOS-apparaten die met een wachtwoordcode zijn vergrendeld, worden na het opnieuw opstarten niet aan een Wi-Fi-netwerk toegevoegd. Nadat het apparaat opnieuw is opgestart, kan het mogelijk niet meer communiceren met de server.
- macOS: niet ondersteund
- Android: niet ondersteund

## <a name="restart-a-device"></a>Apparaten opnieuw opstarten

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** > **Alle apparaten**.
4. Selecteer een apparaat in de lijst met apparaten die u beheert, selecteer **Meer** en selecteer de externe apparaatactie **Opnieuw opstarten**.

## <a name="next-steps"></a>Volgende stappen

- Selecteer **Apparaten** > **Apparaatacties** om de status van de apparaatactie **Opnieuw opstarten** te bekijken.
