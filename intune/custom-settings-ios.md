---
title: Aangepaste instellingen toevoegen aan iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Exporteer iOS-instellingen uit de hulpprogramma's Apple Configurator of Apple Profile Manager en importeer deze instellingen vervolgens in Microsoft Intune. Met deze instellingen kunnen aangepaste instellingen en functies op iOS-apparaten worden gemaakt, gebruikt en beheerd. Dit aangepaste profiel kan vervolgens worden toegewezen aan of worden gedistribueerd naar iOS-apparaten in uw organisatie om een basislijn of standaard te maken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 348a1dbf7b969956bc1ddcfb0f32a994a84e29d4
ms.sourcegitcommit: c969b596ec0fec227484c50f210ba4e159e2e533
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49983105"
---
# <a name="use-custom-settings-for-ios-devices-in-microsoft-intune"></a>Aangepaste instellingen gebruiken voor iOS-apparaten in Microsoft Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw iOS-apparaten toevoegen of maken met behulp van 'aangepaste profielen'. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

Wanneer u iOS-apparaten gebruikt, kunt u op twee manieren aangepaste instellingen opnemen in Intune:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

U kunt met deze hulpprogramma's instellingen exporteren naar een configuratieprofiel. U importeert dit bestand in Intune en wijst het profiel vervolgens toe aan uw iOS-gebruikers en -apparaten. Wanneer het profiel is toegewezen, worden de instellingen gedistribueerd en wordt er ook een basislijn of standaard gemaakt voor iOS in uw organisatie.

In dit artikel wordt beschreven hoe u een aangepast profiel maakt voor iOS-apparaten. Er worden ook enkele richtlijnen vermeld voor het gebruik van Apple Configurator en Apple Profile Manager.

## <a name="before-you-begin"></a>Voordat u begint

- Wanneer u **Apple Configurator** gebruikt om het configuratieprofiel te maken, moet u ervoor zorgen dat de instellingen die u exporteert compatibel zijn met de iOS-versie op de apparaten die u gebruikt. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).

- Wanneer u **Apple Profile Manager** gebruikt, moet u het volgende doen:

  - [Mobile Device Management](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) inschakelen in Profile Manager.
  - [iOS-apparaten](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) toevoegen in Profile Manager.
  - Nadat u een apparaat hebt toegevoegd in Profile Manager, gaat u naar **Onder de bibliotheek** > **Apparaten** > selecteer uw apparaat > **Instellingen**. Voer de algemene instellingen in voor het apparaat.

    Download dit bestand en sla het op. U voert dit bestand in het Intune-profiel in.

  - Zorg ervoor dat de instellingen die u uit Apple Profile Manager exporteert compatibel zijn met de iOS-versie op de apparaten die u gebruikt. Als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen, zoekt u op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten).

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende instellingen in:

    - **Naam**: voer een naam in voor het profiel, zoals `ios custom profile`.
    - **Beschrijving:** voer een beschrijving in voor het profiel.
    - **Platform**: kies **iOS**.
    - **Profieltype**: kies **Aangepast**.

4. Voer in **Aangepaste configuratie** de volgende instellingen in:

    - **Naam voor het aangepaste configuratieprofiel**: voer een naam in voor het beleid. Deze naam wordt weergegeven op het apparaat en in de Intune-status.
    - **Configuratieprofielbestand**: blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator of Apple Profile Manager. Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud**.

5. Selecteer **OK** > **Maken** om het Intune-profiel te maken. Wanneer het profiel is gemaakt, wordt dit weergegeven in de lijst **Apparaatconfiguratie - profielen**.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u [het profiel op macOS-apparaten maakt](custom-settings-macos.md). 