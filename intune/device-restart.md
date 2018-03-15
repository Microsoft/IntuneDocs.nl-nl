---
title: Apparaten extern opnieuw opstarten met Intune
titlesuffix: Azure portal
description: Meer informatie over het op afstand opnieuw opstarten van apparaten met de actie voor het opnieuw opstarten van apparaten.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ab2bf622211c1a81ca9732aabebea43b5b0dcc4
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
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

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies **Alle apparaten** op de blade **Apparaten**.
5. Kies in de lijst met apparaten die u beheert, een apparaat, kies **...Meer** en kies vervolgens de externe apparaatactie **Opnieuw opstarten**.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten** de optie **Apparaatacties**.
