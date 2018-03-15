---
title: Windows 10-apparaten opnieuw instellen met Intune
titlesuffix: Azure portal
description: Meer informatie over het gebruik van Nieuwe start om Windows 10-pc's opnieuw in te stellen met Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c45d3e47c90ca7739b3aa6eee1bf31d787a82264
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/23/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Nieuwe start gebruiken om Windows 10-apparaten opnieuw in te stellen met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Nieuw start** verwijdert u alle apps die zijn geïnstalleerd op een computer met Windows 10 met de makersupdate. De computer wordt vervolgens automatisch bijgewerkt naar de nieuwste versie van Windows.
Met deze actie verwijdert u vooraf geïnstalleerde OEM-apps die vaak op nieuwe pc's staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert. In dit geval worden apps en instellingen verwijderd, maar de inhoud van de basismap Gebruikers blijft bewaard.

## <a name="how-to-use-fresh-start"></a>Nieuwe start gebruiken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies **Apparaten** in het deelvenster **Intune**.
4. Kies **Alle apparaten** in het deelvenster **Apparaten**.
5. Kies in de lijst met apparaten die u beheert, een Windows 10-desktopapparaat en kies vervolgens de externe apparaatactie **Nieuwe start**.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u in het deelvenster **Apparaten** de optie **Apparaatacties**.

