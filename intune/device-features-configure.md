---
title: iOS- of macOS-apparaatprofielen maken met Microsoft Intune - Azure | Microsoft Docs
description: Een iOS- of macOS-apparaatprofiel toevoegen of maken en vervolgens instellingen voor AirPrint, de indeling van het startscherm, app-meldingen, gedeelde apparaten, eenmalige aanmelding en het filteren van webinhoud in Microsoft Intune configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1a5c85c936e49c277b54b542f372f97b247d6a37
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373809"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Instellingen van apparaatfuncties voor iOS of macOS toevoegen in Intune

Intune bevat veel functies en instellingen waarmee beheerders iOS en macOS-apparaten kunnen beheren. Beheerders kunnen bijvoorbeeld het volgende:

- Gebruikers toegang toestaan tot de AirPrint-printers in uw netwerk
- Apps en mappen toevoegen aan het startscherm, inclusief het toevoegen van nieuwe pagina's
- Kiezen of en hoe app-meldingen worden weergegeven
- Het vergrendelingsscherm configureren voor weergave van een bericht of de inventaristag, met name voor gedeelde apparaten
- Gebruikers beveiligde eenmalige aanmelding bieden om referenties tussen apps te kunnen delen
- Websites filteren waarop grof taalgebruik wordt gebruikt en specifieke websites toestaan of blokkeren

Deze functies zijn beschikbaar in Intune en kunnen worden geconfigureerd door de beheerder. Intune maakt gebruik van configuratieprofielen om deze instellingen te maken voor en af te stemmen op de behoeften van uw organisatie. Nadat u deze functies aan een profiel hebt toegevoegd, kunt u het profiel pushen naar en implementeren op iOS- en macOS-apparaten in uw organisatie.

In dit artikel wordt beschreven hoe u een apparaatconfiguratieprofiel maakt. U ziet ook de beschikbare instellingen voor [iOS](ios-device-features-settings.md)- en [macOS](macos-device-features-settings.md)-apparaten.

## <a name="create-a-device-profile"></a>Een apparaatprofiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer uw platform:
        - **iOS**
        - **macOS**
    - **Profieltype**: Selecteer **Apparaatfuncties**.
    - **Instellingen**: Voer de instellingen in die u wilt configureren. Voor een lijst van alle instellingen en wat ze doen raadpleegt u:

        - [iOS](ios-device-features-settings.md)
        - [macOS](macos-device-features-settings.md)

4. Wanneer u klaar bent, selecteert u **OK** en kiest u **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en in de lijst weergegeven. Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](device-profile-monitor.md).

## <a name="next-steps"></a>Volgende stappen

Nadat het profiel is gemaakt, is het klaar om te worden toegewezen. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Bekijk alle instellingen voor apparaatfuncties voor [iOS](ios-device-features-settings.md)- en [macOS](macos-device-features-settings.md)-apparaten.
