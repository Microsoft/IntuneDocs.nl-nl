---
title: Wachtwoordcodes van apparaten opnieuw instellen met Microsoft Intune - Azure | Microsoft Docs
description: Verwijder de wachtwoordcode of stel deze opnieuw in met de actie Wachtwoordcode verwijderen op apparaten die u beheert of bewaakt met Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a233c62b76901d9bad00aa6d8b2a8a4dd45dea96
ms.sourcegitcommit: 024cce10a99b12a13f32d3995b69c290743cafb8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2018
ms.locfileid: "39039298"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>De wachtwoordcode van een apparaat opnieuw instellen of verwijderen via Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als u een nieuwe wachtwoordcode wilt maken voor een apparaat, gebruikt u de actie **Wachtwoordcode verwijderen**. Bij deze actie wordt alleen bij het werkprofiel gevraagd een pincode opnieuw in te stellen. Het opnieuw instellen van de pincode van het apparaat wordt niet ondersteund voor Android-werkprofielen.

## <a name="work-profile-pin-reset-supported-platforms"></a>Ondersteunde platforms voor het opnieuw instellen van pincodes voor werkprofielen

- Android-apparaten die zijn ingeschreven met een werkprofiel, versie 8.0 en hoger 
- Android-apparaten met versie 6.0 of lager
- Kioskapparaten voor Android Enterprise
- iOS 
     
## <a name="unsupported-platforms"></a>Niet-ondersteunde platforms

- Android-apparaten die zijn ingeschreven met een werkprofiel, versie 7.0 en lager
- Android-apparaten met versie 7.0 of lager
- macOS
- Windows

## <a name="reset-a-passcode"></a>Een wachtwoordcode opnieuw instellen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten** en selecteer vervolgens **Alle apparaten**.
4. Selecteer een apparaat in de lijst met apparaten die u beheert en kies **...Meer**. Kies vervolgens de externe apparaatactie **Wachtwoordcode verwijderen**.

## <a name="resetting-android-work-profile-passcodes"></a>Wachtwoordcodes voor Android-werkprofielen opnieuw instellen

Ondersteunde Android-werkprofielapparaten ontvangen een nieuw wachtwoord om het beheerde profiel te ontgrendelen of een beheerde gebruikersvraag voor eindgebruikers. 

In het geval van apparaten met Android 8.0-werkprofiel, worden eindgebruikers geïnformeerd om hun wachtwoordcode voor opnieuw instellen te activeren direct nadat de inschrijving is voltooid. De melding wordt weergegeven als een Work-profielwachtwoord is vereist en is ingesteld. Zodra de wachtwoordcode is ingevoerd, wordt de melding verwijderd.

## <a name="resetting-ios-passcodes"></a>iOS-wachtwoordcodes opnieuw instellen

Wachtwoordcodes worden van de iOS-apparaten verwijderd. Als er een nalevingsbeleid voor wachtwoordcodes is ingesteld, wordt de gebruiker gevraagd om een nieuwe wachtwoordcode in te stellen bij Instellingen. 

## <a name="next-steps"></a>Volgende stappen

Als u de status wilt weergeven van de actie die u zojuist hebt uitgevoerd, kiest u in **Apparaten** de optie **Apparaatacties**.
