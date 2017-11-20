---
title: Wachtwoordcodes op apparaten opnieuw instellen en verwijderen met Intune
titlesuffix: Azure portal
description: Meer informatie over het opnieuw instellen en verwijderen van de wachtwoordcode op apparaten die u beheert met Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfa94d11f978bbe4d23b6672423c849e1f061986
ms.sourcegitcommit: 474a24ba67f6bf4f00268bf9e4eba52331a6b82d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Wachtwoordcodes opnieuw instellen en verwijderen op apparaten die door Intune worden beheerd


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De begrippen *verwijderen* en *opnieuw* worden in dit artikel door elkaar gebruikt.

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
