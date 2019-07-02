---
title: MacOS kernel-extensies-apparaatprofiel maken met Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: Toevoegen of een macOS-apparaatprofiel maken en configureer vervolgens kernel-extensies te overschrijven van de gebruiker toestaan, team-id en een team en de bundel-id toevoegen in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fd2e03c09cb2bed49ee7607283bf63e2c3ae67da
ms.sourcegitcommit: 256952cac44bc6289156489b6622fdc1a3c9c889
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2019
ms.locfileid: "67403903"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>Kernel-extensies voor macOS toevoegen in Intune

Op macOS-apparaten, kunt u functies toevoegen op het kernel-niveau. Deze functies toegang krijgen tot de onderdelen van het besturingssysteem die geen toegang normale programma's tot. Uw organisatie heeft specifieke behoeften of vereisten die niet beschikbaar zijn in een app, een functie apparaat, enzovoort. 

Als u wilt toevoegen de kernel-uitbreidingen die altijd zijn toegestaan op uw apparaten laden, toevoegen 'kernel uitbreidingen' (KEXT) in Microsoft Intune, en vervolgens implementeert u deze uitbreidingen op uw apparaten.

U hebt bijvoorbeeld een antivirusprogramma scannen van uw apparaat op schadelijke inhoud. U kunt deze virussen worden gescand kernel-extensie van het programma als een uitbreiding van de toegestane kernel in Intune toevoegen. Vervolgens 'toewijzen' de extensie aan uw macOS-apparaten.

Met deze functie kunnen beheerders kunnen toestaan dat gebruikers om op te heffen kernel-extensies, team-id's toevoegen en specifieke kernel-extensies toevoegen in Intune.

Deze functie is van toepassing op:

- macOS 10.13.2 en hoger

Deze functie wilt gebruiken, moeten apparaten:

- Geregistreerd bij Intune met behulp van Apple Device Enrollment Program (DEP). [MacOS-apparaten automatisch inschrijven](device-enrollment-program-enroll-macos.md) bevat meer informatie.

  OF

- Ingeschreven in Intune met 'gebruiker goedgekeurd inschrijving' (termijn van Apple). [Voorbereiden voor wijzigingen in de kernel-extensies in macOS High Sierra](https://support.apple.com/en-us/HT208019) (opent u de website van Apple) bevat meer informatie.

Intune maakt gebruik van configuratieprofielen om deze instellingen te maken voor en af te stemmen op de behoeften van uw organisatie. Nadat u deze functies aan een profiel hebt toegevoegd, kunt u het profiel pushen naar en implementeren op macOS-apparaten in uw organisatie.

Dit artikel laat u het maken van een apparaatconfiguratieprofiel met behulp kernel-extensies in Intune.

> [!TIP]
> Zie voor meer informatie over extensies kernel [kernel-extensieoverzicht](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (opent u de website van Apple).

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- Niet-ondertekende verouderde kernel uitbreidingen kunnen worden toegevoegd.
- Zorg dat het juiste team-id invoeren en bundel-ID van de kernel-extensie. Intune valideert niet de waarden die u invoert. Als u de juiste informatie invoert, werkt de extensie niet op het apparaat.

> [!NOTE]
> Apple informatie met betrekking tot ondertekenen en notarization voor alle software die is uitgebracht. In macOS 10.14.5 en hoger, kernel-uitbreidingen die zijn geïmplementeerd via Intune hoeft te voldoen aan de Apple notarization beleid.
>
> Zie voor meer informatie in dit beleid notarization en eventuele updates of wijzigingen in de volgende bronnen:
>
>  - [Uw app voor distributie notarizing](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (opent u de website van Apple) 
>  - [Voorbereiden voor wijzigingen in de kernel-extensies in macOS High Sierra](https://support.apple.com/en-us/HT208019) (opent u de website van Apple)

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving:** voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer **macOS**
    - **Profieltype**: Selecteer **extensies**.
    - **Instellingen**: Voer de instellingen in die u wilt configureren. Voor een lijst van alle instellingen en wat ze doen raadpleegt u:

        - [macOS](kernel-extensions-settings-macos.md)

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en in de lijst weergegeven. Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](device-profile-monitor.md).

## <a name="next-steps"></a>Volgende stappen

Nadat het profiel is gemaakt, is het klaar om te worden toegewezen. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
