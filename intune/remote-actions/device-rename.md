---
title: Naam van een apparaat wijzigen met Microsoft Intune - Azure | Microsoft Docs
description: Wijzig de naam van een apparaat met behulp van Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35fae5ea1b3294772db4f4db51179892e08ed5d1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728504"
---
# <a name="rename-a-device-in-intune"></a>Naam van een apparaat wijzigen in Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met de actie **Naam van apparaat wijzigen** kunt u de naam wijzigen van een apparaat dat is ingeschreven bij Intune. De naam van het apparaat wordt gewijzigd in Intune en op het apparaat.

U kunt de namen van de volgende typen apparaten wijzigen:
- Windows-apparaat in bedrijfseigendom 
- iOS-apparaat onder supervisie
- MacOS 10-apparaat in bedrijfseigendom

Deze functie biedt momenteel geen ondersteuning voor de naamwijziging van hybride Azure AD Windows-apparaten.

## <a name="rename-a-device"></a>De naam van een apparaat wijzigen

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies **Apparaten** > **Alle apparaten** > kies een apparaat > **Meer** > **Naam van apparaat wijzigen**.
4. Typ op de blade **Naam van apparaat wijzigen** de nieuwe naam in het tekstvak. U kunt letters, cijfers en afbreekstreepjes gebruiken. De naam moet minstens één letter of afbreekstreepje bevatten.
5. Als u het apparaat opnieuw wilt opstarten nadat u de naam ervan hebt gewijzigd, kiest u naast **Opnieuw opstarten na het wijzigen van de naam** de optie **Ja**.
6. Kies **Naam wijzigen**.



## <a name="next-steps"></a>Volgende stappen

Ga naar de pagina **Overzicht** voor het apparaat om de status van de actie **Naam wijzigen** te zien.
