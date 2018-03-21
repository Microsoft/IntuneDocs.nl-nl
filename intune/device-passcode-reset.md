---
title: Wachtwoordcodes van apparaten opnieuw instellen met Microsoft Intune - Azure | Microsoft Docs
description: Verwijder de wachtwoordcode of stel deze opnieuw in met de actie Wachtwoordcode verwijderen op apparaten die u beheert of bewaakt met Intune.
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f23a79bbe72d12750ef642226aefd1e11dcac24
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>De wachtwoordcode van een apparaat opnieuw instellen of verwijderen via Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als u een nieuwe wachtwoordcode wilt maken voor een apparaat, gebruikt u de actie **Wachtwoordcode verwijderen**.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows Phone 8.1 t/m Windows 10-makersupdate, niet gekoppeld aan Azure AD, en Windows 10-makersupdate en hoger
- iOS
- Android-versies ouder dan Android 7

Deze functie wordt **niet** ondersteund op de volgende systemen:

- Windows
- macOS
- Android for Work

## <a name="reset-a-passcode"></a>Een wachtwoordcode opnieuw instellen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Selecteer in de lijst van door u beheerde apparaten een apparaat, kies **...Meer** en kies vervolgens de externe actie **Toegangscode verwijderen** voor het apparaat.

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt uitgevoerd, kiest u in **Apparaten** de optie **Apparaatacties**.
