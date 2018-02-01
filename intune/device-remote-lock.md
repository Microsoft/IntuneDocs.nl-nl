---
title: Beheerde apparaten extern vergrendelen met Intune
titlesuffix: Azure portal
description: Meer informatie over het gebruik van Intune om apparaten die u beheert, op afstand te vergrendelen.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecd7fa03b35e91b5a77906858fb251348796704d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Beheerde apparaten extern vergrendelen met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met **Extern vergrendelen** wordt het geselecteerde apparaat vergrendeld. De eigenaar van het apparaat moet de wachtwoordcode gebruiken om het apparaat te ontgrendelen. U kunt alleen een apparaat vergrendelen dat op afstand is vergrendeld met een pincode of een wachtwoord.

## <a name="supported-platforms"></a>Ondersteunde platforms

Externe vergrendeling wordt ondersteund op de volgende platformen:

|Platform|Ondersteuningsstatus|
|---|---|
|Android|Ja|
|iOS|Ja|
|macOS|Ja|
|Windows 10|Ja|
|Windows 10 Mobile|Ja|
|Windows Phone|Ja, voor Windows Phone 8.1 of hoger|

> [!NOTE]  
> Voor macOS-apparaten moet u een zescijferige pincode voor herstel instellen. Als het apparaat is vergrendeld, toont de blade **Apparaatoverzicht** de pincode totdat een andere apparaatactie wordt verzonden.

## <a name="how-to-remote-lock-a-device"></a>Een apparaat op afstand vergrendelen

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een apparaat en kies vervolgens de externe apparaatactie **Extern vergrendelen**.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.
