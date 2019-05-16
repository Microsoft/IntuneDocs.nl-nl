---
title: Naam van een Windows-apparaat wijzigen met Microsoft Intune - Azure | Microsoft Docs
description: Wijzig de naam van een Windows-apparaat met behulp van Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8dfdc3641d583fc045346034ee8543feff1e7cbf
ms.sourcegitcommit: 1144247aa7f042eb1b99d8fd8dd17b909eae38c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2019
ms.locfileid: "59567098"
---
# <a name="rename-a-windows-device-in-intune"></a>Naam van een Windows-apparaat wijzigen in Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de actie **Naam van apparaat wijzigen** kunt u de naam wijzigen van een Windows-apparaat dat bedrijfseigendom is, en dat is ingeschreven bij Intune. De naam van het apparaat wordt gewijzigd in Intune en op het apparaat. 

Deze functie biedt momenteel geen ondersteuning voor de naamwijziging van hybride Azure AD Windows-apparaten.

## <a name="rename-a-device"></a>De naam van een apparaat wijzigen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Kies **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Kies **Apparaten** > **Alle apparaten** > kies een Windows-apparaat > **Meer** > **Naam van apparaat wijzigen**.
4. Typ op de blade **Naam van apparaat wijzigen** de nieuwe naam in het tekstvak. U kunt letters, cijfers en afbreekstreepjes gebruiken. De naam moet minstens één letter of afbreekstreepje bevatten.
5. Als u het apparaat opnieuw wilt opstarten nadat u de naam ervan hebt gewijzigd, kiest u naast **Opnieuw opstarten na het wijzigen van de naam** de optie **Ja**.
6. Kies **Naam wijzigen**.



## <a name="next-steps"></a>Volgende stappen

Ga naar de pagina **Overzicht** voor het apparaat om de status van de actie **Naam wijzigen** te zien.
