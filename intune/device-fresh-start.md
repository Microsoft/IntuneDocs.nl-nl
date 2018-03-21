---
title: Windows 10-apparaten met Microsoft Intune opnieuw instellen - Azure | Microsoft Docs
description: "Gebruik Nieuwe start om apps op Windows 10-pc's te verwijderen met behulp van Microsoft Intune, waaronder vooraf geïnstalleerde apps van OEM's. Inhoud uit de basismap kan worden behouden als is ingesteld dat gebruikersgegevens behouden moeten blijven."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d17c9dc11791f32f0c2c1e7faa88966c112fc6a5
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Nieuwe start gebruiken om Windows 10-apparaten opnieuw in te stellen met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Nieuwe start** worden alle apps verwijderd die op Windows 10-pc's met de makersupdate zijn geïnstalleerd. Daarna wordt de pc automatisch bijgewerkt naar de nieuwste versie van Windows.

Met deze actie worden vooraf geïnstalleerde apps (OEM-apps) verwijderd die normaliter op nieuwe pc's staan. Als u de inhoud uit de basismap van de gebruiker wilt behouden en alleen apps en instellingen wilt verwijderen, gebruikt u de instelling `if user data is retained`.

> [!IMPORTANT]
> Met Nieuwe start wordt het apparaat uitgeschreven bij Intune. Het apparaat blijft echter nog wel gekoppeld in Azure Active Directory.

## <a name="use-fresh-start"></a>Nieuwe start gebruiken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Kies in de lijst met apparaten die u beheert een Windows 10-desktopapparaat en selecteer vervolgens **Nieuwe start**.

## <a name="next-steps"></a>Volgende stappen

Als u de status van deze actie wilt bekijken, selecteert u **Apparaatacties** (**Microsoft Intune** > **Apparaten**).