---
title: Een gebruiker met Microsoft Intune verwijderen van een iOS-apparaat
titlesuffix: ''
description: Lees hier meer over het verwijderen van een gebruiker van een gedeeld iOS-apparaat met Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c00e026a6877097abd266a7ed800500a0f467123
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55851352"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Een gebruiker verwijderen van een gedeeld iOS-apparaat


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met de actie **Gebruiker verwijderen** kunt u een gebruiker verwijderen uit de lokale cache op een gedeeld iPad-apparaat. Het iPad-apparaat moet met behulp van een [iOS-opleidingsprofiel](education-settings-configure-ios.md) worden ingesteld voor het beheren van de iOS-app Classroom. 

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: niet ondersteund
- Windows Phone: niet ondersteund
- iOS: ondersteund op iOS 9.3 en hoger (alleen gedeelde iPads)
- macOS: niet ondersteund
- Android: niet ondersteund

## <a name="remove-a-user"></a>Een gebruiker verwijderen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Apparaten** in het deelvenster **Intune**.
4. Selecteer **Alle apparaten** in het deelvenster **Apparaten**.
5. Kies een iOS-apparaat in de lijst met apparaten die u beheert.
6. Selecteer **Gebruikers** in het deelvenster voor het apparaat.
7. Klik in de lijst met de rechtermuisknop op de gebruiker die u wilt verwijderen en kies vervolgens **Gebruiker verwijderen**.

## <a name="next-steps"></a>Volgende stappen

- Selecteer **Apparaten** > **Apparaatacties** om de status van de apparaatactie **Gebruiker verwijderen** te bekijken.
