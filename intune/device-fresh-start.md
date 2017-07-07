---
title: Windows 10-apparaten opnieuw instellen met Intune
titleSuffix: Intune on Azure
description: Meer informatie over het gebruik van Nieuwe start om Windows 10-pc's opnieuw in te stellen met Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 590472c0ab9f0103d72730b8ab01dc324c852a7a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Nieuwe start gebruiken om Windows 10-apparaten opnieuw in te stellen met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Nieuw start** verwijdert u alle apps die zijn geïnstalleerd op een computer met Windows 10 met de makersupdate. De computer wordt vervolgens automatisch bijgewerkt naar de nieuwste versie van Windows.
U kunt dit gebruiken om vooraf geïnstalleerde OEM-apps te verwijderen die vaak op nieuwe computers staan. U kunt configureren of de gebruikersgegevens bewaard blijven wanneer u deze actie uitvoert. In dit geval worden apps en instellingen verwijderd, maar de inhoud van de basismap Gebruikers blijft bewaard.

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een Windows 10-desktopapparaat en kies vervolgens de externe apparaatactie **Nieuwe start**.

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.

