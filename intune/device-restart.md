---
title: Apparaten extern opnieuw opstarten met Intune
titlesuffix: Azure portal
description: Meer informatie over het op afstand opnieuw opstarten van apparaten met de actie voor het opnieuw opstarten van apparaten.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dde251482dd951200e5c1a7f19749ee863cd71b4
ms.sourcegitcommit: 520eb7712625e129b781e2f2b9fe16f9b9f3d08a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2017
---
# <a name="remotely-restart-devices-with-intune"></a>Apparaten extern opnieuw opstarten met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De apparaatactie **Opnieuw opstarten** zorgt ervoor dat het apparaat dat kiest, opnieuw wordt opgestart. De eigenaar van het apparaat wordt niet op de hoogte gesteld dat het apparaat opnieuw wordt opgestart. Hierdoor kan eventueel werk verloren gaan.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: ondersteund op Windows 8.1 en hoger
- Windows Phone: ondersteund op Windows 8.1 en hoger
- iOS: ondersteund

    > [!Note]  
    > Deze opdracht vereist toegangsrechten tot apparaten onder supervisie en **Apparaatvergrendeling**. Het apparaat wordt onmiddellijk opnieuw opgestart. Met een toegangscode vergrendelde iOS-apparaten wordt niet opnieuw verbonden met een Wi-Fi-netwerk na opnieuw te zijn opgestart; na opnieuw te zijn opgestart kunnen deze mogelijk niet communiceren met de server.
- macOS: niet ondersteund
- Android: niet ondersteund

## <a name="how-to-restart-a-device"></a>Apparaten opnieuw opstarten

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een apparaat en kies vervolgens de externe apparaatactie **Opnieuw opstarten**.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.
