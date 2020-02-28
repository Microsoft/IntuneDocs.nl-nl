---
title: Aangepaste instellingen toevoegen aan iOS-/iPadOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Exporteer iOS-/iPadOS-instellingen uit de hulpprogramma's Apple Configurator of Apple Profile Manager en importeer deze instellingen vervolgens in Microsoft Intune. Met deze instellingen kunnen aangepaste instellingen en functies op iOS-/iPadOS-apparaten worden gemaakt, gebruikt en beheerd. Dit aangepaste profiel kan vervolgens worden toegewezen aan of worden gedistribueerd naar iOS-/iPadOS-apparaten in uw organisatie om een basislijn of standaard te maken.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a5dbb56a20d778a0fffc9abde1bc6ce80eb0add
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77513109"
---
# <a name="use-custom-settings-for-ios-and-ipados-devices-in-microsoft-intune"></a>Aangepaste instellingen gebruiken voor iOS-/iPadOS-apparaten in Microsoft Intune

Met Microsoft Intune kunt u aangepaste instellingen voor uw iOS-/iPadOS-apparaten toevoegen of maken met behulp van aangepaste profielen. Aangepaste profielen zijn een functie in Intune. Ze zijn ontworpen om apparaatinstellingen en -functies toe te voegen die niet in Intune zijn ingebouwd.

Wanneer u iOS-/iPadOS-apparaten gebruikt, kunt u op twee manieren aangepaste instellingen opnemen in Intune:

- [Apple Configurator](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12)
- [Apple Profile Manager](https://support.apple.com/profile-manager)

U kunt met deze hulpprogramma's instellingen exporteren naar een configuratieprofiel. U importeert dit bestand in Intune en wijst het profiel vervolgens toe aan uw iOS-/iPadOS-gebruikers en -apparaten. Zodra het profiel is toegewezen, worden de instellingen gedistribueerd. Ze vormen ook een basislijn of standaard voor iOS/iPadOS in uw organisatie.

Dit artikel biedt richtlijnen voor het gebruik van Apple Configurator en Apple Profile Manager. Ook worden de eigenschappen beschreven die u kunt configureren.

## <a name="before-you-begin"></a>Voordat u begint

[Maak het profiel](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- Wanneer u **Apple Configurator** gebruikt om het configuratieprofiel te maken, moet u ervoor zorgen dat de instellingen die u exporteert, compatibel zijn met de iOS-/iPadOS-versie op de apparaten. Zoek op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten) als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen.

- Wanneer u **Apple Profile Manager** gebruikt, moet u het volgende doen:

  - Schakel [Mobile Device Management](https://help.apple.com/serverapp/mac/5.7/#/apd05B9B761-D390-4A75-9251-E9AD29A61D0C) in Profile Manager in.
  - [iOS-/iPadOS-apparaten](https://help.apple.com/profilemanager/mac/5.7/#/pm9onzap1984) toevoegen in Profile Manager.
  - Nadat u een apparaat hebt toegevoegd in Profile Manager, gaat u naar **Onder de bibliotheek** > **Apparaten** > selecteer uw apparaat > **Instellingen**. Voer de algemene instellingen in voor het apparaat.

    Download dit bestand en sla het op. U voert dit bestand in het Intune-profiel in.

  - Zorg ervoor dat de instellingen die u uit Apple Profile Manager exporteert, compatibel zijn met de iOS-/iPadOS-versie op de apparaten. Zoek op de [Apple Developer](https://developer.apple.com/)-website naar **Configuration Profile Reference** (naslag voor configuratieprofielen) en **Mobile Device Management Protocol Reference** (naslag voor beheerprotocol voor mobiele apparaten) als u meer wilt weten over het oplossen van problemen bij incompatibele instellingen.

## <a name="custom-configuration-profile-settings"></a>Aangepaste configuratieprofielinstellingen

- **Naam van het aangepaste configuratieprofiel**: Geef een naam op voor het beleid. Deze naam wordt weergegeven op het apparaat en in de Intune-status.
- **Configuratieprofielbestand**: Blader naar het configuratieprofiel dat u hebt gemaakt met Apple Configurator of Apple Profile Manager. De maximale bestandsgrootte is 1.000.000 bytes (net iets minder dan 1 MB). Het bestand dat u hebt geïmporteerd, wordt weergegeven in het gebied **Bestandsinhoud**.

  U kunt ook apparaattokens toevoegen aan uw aangepaste configuratiebestanden. Apparaattokens worden gebruikt om apparaatspecifieke informatie toe te voegen. Als u bijvoorbeeld het serienummer wilt weergeven, voert u `{{serialnumber}}` in. Op het apparaat wordt tekst weergegeven die lijkt op `123456789ABC`, wat uniek is voor elk apparaat. Wanneer u variabelen opgeeft, moet u ervoor zorgen dat u accolades `{{ }}` gebruikt. [App-configuratietokens](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat een lijst met variabelen die kunnen worden gebruikt. U kunt ook `deviceid` of een andere apparaatspecifieke waarde gebruiken.

  > [!NOTE]
  > Variabelen worden niet gevalideerd in de gebruikersinterface en zijn hoofdlettergevoelig. Hierdoor ziet u mogelijk profielen die met onjuiste invoer zijn opgeslagen. Als u bijvoorbeeld `{{DeviceID}}` invoert in plaats van `{{deviceid}}`, wordt de letterlijke tekenreeks weergegeven in plaats van de unieke id van het apparaat. Zorg dat u de juiste informatie invoert.

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens [wijst u het profiel toe](device-profile-assign.md).

Bekijk hoe u [het profiel op macOS-apparaten maakt](custom-settings-macos.md). 
