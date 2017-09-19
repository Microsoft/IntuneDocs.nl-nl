---
title: Windows 10-apparaten opnieuw instellen met Intune
titlesuffix: Azure portal
description: Meer informatie over het gebruik van Nieuwe start om Windows 10-pc's opnieuw in te stellen met Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff6198cb42d5c96ed4e4c4e0009a8bbd6f6a0dec
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Nieuwe start gebruiken om Windows 10-apparaten opnieuw in te stellen met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Nieuw start** verwijdert u alle apps die zijn geïnstalleerd op een computer met Windows 10 met de makersupdate. De computer wordt vervolgens automatisch bijgewerkt naar de nieuwste versie van Windows.
U kunt dit gebruiken om vooraf geïnstalleerde OEM-apps te verwijderen die vaak op nieuwe computers staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert. In dit geval worden apps en instellingen verwijderd, maar de inhoud van de basismap Gebruikers blijft bewaard.

## <a name="how-to-use-fresh-start"></a>Nieuwe start gebruiken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een Windows 10-desktopapparaat en kies vervolgens de externe apparaatactie **Nieuwe start**.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.

