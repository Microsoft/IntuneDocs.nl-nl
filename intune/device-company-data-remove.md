---
title: Bedrijfsgegevens van apparaten met Intune verwijderen
titleSuffix: Intune on Azure
description: Meer informatie over hoe u alleen bedrijfsgegevens verwijdert van apparaten die u beheert met Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8074d6e7cc0a061a6708f8c8bfae1a4dfcb6daa3
ms.sourcegitcommit: 10e3ab2aeb79a1fb2243bef2748ccc003fdd4cc7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Bedrijfsgegevens verwijderen van apparaten die worden beheerd met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met de apparaatactie **Bedrijfsgegevens verwijderen** verwijdert u alleen bedrijfsgegevens van apparaten die worden beheerd met Intune. Persoonlijke gegevens worden met deze actie niet van het apparaat verwijderd. Na verwijdering wordt het apparaat niet langer beheerd door Intune en kunnen er geen bedrijfsresources meer worden geopend.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: ondersteund (niet ondersteund op Windows-apparaten die lid zijn van het Azure Active Directory-domein)
- Windows Phone: ondersteund
- iOS: ondersteund
- Mac OS: ondersteund
- Android: ondersteund

## <a name="how-to-remove-company-data"></a>Bedrijfsgegevens verwijderen

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een apparaat en kies vervolgens de externe apparaatactie **Bedrijfsgegevens verwijderen**.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.
