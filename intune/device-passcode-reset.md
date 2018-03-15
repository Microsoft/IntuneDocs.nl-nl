---
title: Wachtwoordcodes op apparaten opnieuw instellen en verwijderen met Intune
titlesuffix: Azure portal
description: Meer informatie over het opnieuw instellen en verwijderen van de wachtwoordcode op apparaten die u beheert met Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4e1496d24fd9d3bb636a4eab00c254b753210f63
ms.sourcegitcommit: eac89306d1391a6d3ae1179612b0820b19c2baa6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/23/2018
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

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies **Alle apparaten** op de blade **Apparaten**.
5. Selecteer in de lijst van door u beheerde apparaten een apparaat, kies **...Meer** en kies vervolgens de externe actie **Toegangscode verwijderen** voor het apparaat.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt genomen, kiest u op de blade **Apparaten** de optie **Apparaatacties**.
