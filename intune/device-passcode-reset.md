---
title: De wachtwoordcode van een apparaat opnieuw instellen met Intune
titlesuffix: Azure portal
description: Meer informatie over het opnieuw instellen van de wachtwoordcode op apparaten die u beheert met Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0446db40b829e92b681294ecc497a2c475480fac
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/01/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>De wachtwoordcode opnieuw instellen op apparaten die worden beheerd met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De actie **Toegangscode verwijderen** genereert een nieuwe toegangscode voor het apparaat die wordt weergegeven op de blade <*apparaatnaam*> **Overzicht**.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: niet ondersteund
- Windows Phone: ondersteund op Windows Phone 8.1 tot en met Windows 10 Creators Update, geen lid van Azure AD-domein, Windows 10 Creators Update en hoger
- iOS: ondersteund
- macOS: niet ondersteund
- Android: ondersteund op eerdere Android-versies dan Android 7. Android for Work wordt niet ondersteund.

## <a name="how-to-reset-a-passcode"></a>Een wachtwoordcode opnieuw instellen

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst van door u beheerde apparaten een apparaat, en kies vervolgens de externe actie **Toegangscode verwijderen** voor het apparaat.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten en groepen** de optie **Apparaatacties**.
