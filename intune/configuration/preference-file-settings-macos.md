---
title: Instellingen voor voorkeursbestand toevoegen aan macOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Voeg een XML-of plist-bestand toe dat belang rijke informatie over uw app bevat. Gebruik een voorkeurs bestand voor het configureren van een configuratie profiel voor een apparaat om belang rijke informatie in het eigenschappen lijst bestand te wijzigen en toe te wijzen aan uw macOS-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d226a5b8ee448b7b168a03fe6b8a1c63bc1be432
ms.sourcegitcommit: 8f56220e7cafc5bc43135940575a9acb5afde730
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/09/2020
ms.locfileid: "75827782"
---
# <a name="add-a-property-list-file-to-macos-devices-using-microsoft-intune"></a>Een eigenschappen lijst bestand toevoegen aan macOS-apparaten met behulp van Microsoft Intune

Met Microsoft Intune kunt u een eigenschappen lijst bestand (. plist) toevoegen voor macOS-apparaten of apps op macOS-apparaten.

Deze functie is van toepassing op:

- macOS-apparaten met 10.7 en hoger

Eigenschappen lijst bestanden bevatten doorgaans informatie over macOS-toepassingen. Zie [informatie over eigenschappen lijst bestanden](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) (Apple-website) en [aangepaste Payload-instellingen](https://support.apple.com/guide/mdm/custom-mdm9abbdbe7/1/web/1)voor meer informatie.

In dit artikel vindt u een overzicht en een beschrijving van de verschillende instellingen van eigenschappen lijst bestanden die u aan macOS-apparaten kunt toevoegen. Als onderdeel van uw Mobile Device Management-oplossing (MDM) kunt u deze instellingen gebruiken om de app-bundel-ID (`com.company.application`) toe te voegen en het. plist-bestand toe te voegen.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw macOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Maak het profiel](device-profile-create.md).

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- Deze instellingen worden niet gevalideerd. Zorg ervoor dat u uw wijzigingen test voordat u het profiel aan uw apparaten toewijst.
- Als u niet zeker weet hoe u een app-sleutel moet invoeren, wijzigt u de instelling in de app. Controleer vervolgens het voorkeurs bestand van de app met behulp van [Xcode](https://developer.apple.com/xcode/) om te zien hoe de instelling is geconfigureerd. Apple raadt aan om niet-beheer bare instellingen te verwijderen met Xcode voordat u het bestand importeert.
- Er zijn slechts enkele apps die met beheerde voor keuren werken. u kunt mogelijk niet alle instellingen beheren.
- Zorg ervoor dat u eigenschappen lijst bestanden uploadt die de kanaal instellingen van het apparaat hebben, niet de instellingen van het gebruikers kanaal. Eigenschappen lijst bestanden doel het hele apparaat.

## <a name="preference-file"></a>Voorkeursbestand

- **Naam van voorkeurs domein**: lijst met eigenschappen bestanden worden meestal gebruikt voor webbrowsers (micro soft Edge), [micro soft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-mac)en aangepaste apps. Wanneer u een voorkeurs domein maakt, wordt er ook een bundel-ID gemaakt. Voer de bundel-ID in, zoals `com.company.application`. Voer bijvoorbeeld `com.Contoso.applicationName`, `com.Microsoft.Edge` of `com.microsoft.wdav` in.
- **Bestand met eigenschappen lijst**: Selecteer het eigenschappen lijst bestand dat aan uw app is gekoppeld. Controleer of het een `.plist`-of `.xml`-bestand is. Upload bijvoorbeeld een `YourApp-Manifest.plist`-of `YourApp-Manifest.xml` bestand.
- **Bestands inhoud**: de belangrijkste informatie in het eigenschappen lijst bestand wordt weer gegeven. Als u de sleutel informatie wilt wijzigen, opent u het lijst bestand in een andere editor en uploadt u het bestand opnieuw in intune.

Zorg ervoor dat het bestand correct is geformatteerd. Het bestand mag alleen sleutel-waardeparen bevatten en mag niet worden ingepakt in `<dict>`-, `<plist>`-of `<xml>`-Tags. Het bestand met de eigenschappen lijst moet er bijvoorbeeld als volgt uitzien:

```xml
<key>SomeKey</key>
<string>someString</string>
<key>AnotherKey</key>
<false/>
...
```

Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. Het profiel wordt gemaakt en weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Zie [instellingen voor micro soft Edge-beleid configureren in macOS](https://docs.microsoft.com/deployedge/configure-microsoft-edge-on-mac)voor meer informatie over voorkeurs bestanden voor micro soft Edge.
