---
title: Apparaten vergrendelen met Microsoft Intune - Azure | Microsoft Docs
description: Gebruik de actie Extern vergrendelen in Microsoft Intune om apparaten te vergrendelen die zijn beveiligd met een pincode of wachtwoord.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45ab6434245c0dd412b2e9d23e394f72871a459a
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31829761"
---
# <a name="remotely-lock-devices-with-intune"></a>Apparaten extern vergrendelen met Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Extern vergrendelen** wordt het apparaat vergrendeld. De eigenaar van het apparaat moet de wachtwoordcode gebruiken om het apparaat te ontgrendelen. U kunt apparaten waarvoor een pincode of wachtwoord is ingesteld extern vergrendelen. Apparaten waarvoor geen pincode of wachtwoord is ingesteld, kunnen niet extern worden vergrendeld.

## <a name="supported-platforms"></a>Ondersteunde platforms

**Externe vergrendeling** wordt ondersteund op de volgende platformen:

- Android
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 en hoger

**Extern vergrendelen** wordt *niet* ondersteund voor:
- Windows 10 Desktop

> [!NOTE]
> Voor macOS-apparaten moet u een zescijferige pincode voor herstel instellen. Als het apparaat is vergrendeld, wordt in **Apparaatoverzicht** de pincode weergegeven totdat een andere apparaatactie wordt verzonden.

## <a name="remote-lock-a-device"></a>Een apparaat vergrendelen op afstand

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** > **Alle apparaten**.
4. Selecteer een apparaat in de lijst met apparaten en selecteer vervolgens de actie **Extern vergrendelen**.

## <a name="next-steps"></a>Volgende stappen

- Als u de status van deze actie wilt bekijken, selecteert u **Microsoft Intune** > **Apparaten** > **Apparaatacties**. 
- Zie [Beschikbare acties](device-management.md) voor een overzicht van meer acties voor het beheren van uw apparaten.
