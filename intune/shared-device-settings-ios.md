---
title: Vergrendelingsscherm van iOS-apparaten aanpassen met Microsoft Intune - Azure | Microsoft Docs
titlesuffix: ''
description: Lees welke Microsoft Intune-instellingen u kunt gebruiken voor het weergeven van informatie op het vergrendelingsscherm van een iOS-apparaat door gedeelde apparaatconfiguratie-instellingen voor iOS te gebruiken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 9f4d75d795421c761398f349c324b498fd21ca01
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203073"
---
# <a name="add-custom-messages-to-lock-screen-and-login-window-on-ios-devices-using-microsoft-intune"></a>Aangepaste berichten met Microsoft Intune toevoegen aan het vergrendelingsscherm en aanmeldingsvenster van iOS-apparaten

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel kunt u lezen welke Intune-instellingen u kunt gebruiken om informatie in het vergrendelingsscherm en het aanmeldingsvenster van iOS-apparaten weer te geven. 

Gebruik deze instellingen om een aangepast bericht of aangepaste tekst in het aanmeldingsvenster en vergrendelingsscherm weer te geven. U kunt bijvoorbeeld een bericht weergeven met de tekst 'Indien gevonden, graag contact opnemen met...' en informatie over de assettag.

Deze instellingen bieden ondersteuning voor apparaten onder supervisie waarop iOS 9.3 of hoger wordt uitgevoerd.

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Geef een **Naam** en **Beschrijving** op voor het profiel.
4. Selecteer voor **Platform** de optie **iOS**. Selecteer voor **Profieltype**, de optie **Apparaatfuncties**.
5. Ga naar **Instellingen** en selecteer **Bericht voor vergrendelingsscherm (alleen onder supervisie)**. Configureer de volgende instellingen:

    - **Informatie over de assettag**: Voer informatie over de assettag van het apparaat in. Voer bijvoorbeeld `123xyz` in.

        De tekst die u opgeeft, wordt weergegeven in het aanmeldingsvenster en het vergrendelingsscherm van het apparaat.

    - **Voetnoot voor vergrendelingsscherm**: Voer een opmerking in waarmee u het apparaat wellicht kunt terugkrijgen als het verloren of gestolen is. U kunt in het veld elke gewenste tekst invoeren. Voer bijvoorbeeld iets in zoals `If found, call Contoso at ...`.

    Apparaattokens kunnen ook worden gebruikt om apparaatspecifieke informatie aan deze velden toe te voegen. Als u bijvoorbeeld het serienummer wilt weergeven, voert u `Serial Number: {{serialnumber}}` in. De tekst die in het vergrendelingsscherm wordt weergegeven, is vergelijkbaar met `Serial Number 123456789ABC`. Wanneer u variabelen opgeeft, moet u ervoor zorgen dat u accolades `{{ }}` gebruikt. [App-configuratietokens](app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat een lijst met variabelen die kunnen worden gebruikt. U kunt ook `deviceName` of een andere apparaatspecifieke waarde gebruiken.

6. Wanneer u klaar bent, selecteert u **OK** > **OK** > **Maken**. Uw profiel wordt weergegeven in de lijst.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
