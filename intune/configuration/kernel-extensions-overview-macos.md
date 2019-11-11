---
title: Een apparaatprofiel voor macOS kernel Extensions maken met Microsoft Intune-Azure | Microsoft Docs
titleSuffix: ''
description: Een macOS-apparaatprofiel toevoegen of maken en vervolgens de kernel-uitbrei dingen configureren om gebruikers onderdrukking toe te staan, team-ID en een bundel en team-ID toe te voegen in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e69f1b11833da0906aaf831f8bb82b04241e442f
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755185"
---
# <a name="add-macos-kernel-extensions-in-intune"></a>MacOS-kernel-extensies toevoegen in intune

Op macOS-apparaten kunt u functies toevoegen op kernel-niveau. Deze functies hebben toegang tot delen van het besturings systeem waartoe reguliere Program ma's geen toegang hebben. Uw organisatie heeft mogelijk specifieke behoeften of vereisten die niet beschikbaar zijn in een app, een functie van het apparaat, enzovoort. 

Als u kernel-extensies wilt toevoegen die altijd op uw apparaten mogen worden geladen, voegt u ' kernel-extensies ' (KEXT) toe aan Microsoft Intune en implementeert u deze uitbrei dingen vervolgens op uw apparaten.

U hebt bijvoorbeeld een antivirus programma waarmee u uw apparaat kunt scannen op schadelijke inhoud. U kunt de kernel-uitbrei ding voor het virus scan programma toevoegen als een toegestane kernel-uitbrei ding in intune. Vervolgens wijst u de extensie toe aan uw macOS-apparaten.

Met deze functie kunnen beheerders gebruikers toestaan om kernel-extensies te overschrijven, team-id's toe te voegen en specifieke kernel-uitbrei dingen toe te voegen aan intune.

Deze functie is van toepassing op:

- macOS 10.13.2 en hoger

Als u deze functie wilt gebruiken, moeten de apparaten het volgende zijn:

- Inge schreven bij intune met behulp van Apple Device Enrollment Program (DEP). Het [automatisch inschrijven van macOS-apparaten](../enrollment/device-enrollment-program-enroll-macos.md) heeft meer informatie.

  OF

- Inge schreven bij intune met ' door de gebruiker goedgekeurde inschrijving ' (Apple-term). De [wijzigingen voor de kernel-extensies in MacOS High Sierra worden voor bereid](https://support.apple.com/en-us/HT208019) (opent de website van Apple) bevat meer informatie.

Intune maakt gebruik van configuratieprofielen om deze instellingen te maken voor en af te stemmen op de behoeften van uw organisatie. Nadat u deze functies aan een profiel hebt toegevoegd, kunt u het profiel pushen naar en implementeren op macOS-apparaten in uw organisatie.

In dit artikel leest u hoe u een configuratie profiel voor een apparaat maakt met behulp van kernel-uitbrei dingen in intune.

> [!TIP]
> Zie overzicht van de [kernel-extensie](https://developer.apple.com/library/archive/documentation/Darwin/Conceptual/KernelProgramming/Extend/Extend.html) (opent de website van Apple) voor meer informatie over kernel-uitbrei dingen.

## <a name="what-you-need-to-know"></a>Wat u dient te weten

- Niet-ondertekende verouderde kernel-uitbrei dingen kunnen worden toegevoegd.
- Zorg ervoor dat u de juiste team-ID en bundel-ID van de kernel-uitbrei ding opgeeft. InTune valideert niet de waarden die u invoert. Als u onjuiste gegevens invoert, werkt de uitbrei ding niet op het apparaat.

> [!NOTE]
> Apple heeft informatie over ondertekening en notarization vrijgegeven voor alle software. Voor macOS 10.14.5 en nieuwer moeten kernel-uitbrei dingen die via intune zijn geïmplementeerd, niet voldoen aan het notarization-beleid van Apple.
>
> Raadpleeg de volgende bronnen voor meer informatie over dit notarization-beleid en eventuele updates of wijzigingen:
>
> - [Notarizing uw app vóór distributie](https://developer.apple.com/documentation/security/notarizing_your_app_before_distribution) (opent de website van Apple) 
> - De [wijzigingen voor de kernel-extensies in MacOS High Sierra worden voor bereid](https://support.apple.com/en-us/HT208019) (opent de website van Apple)

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij het [micro soft Endpoint Manager-beheer centrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **apparaten** > **configuratie profielen** > **profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving:** voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer **macOS**
    - **Profiel type**: Selecteer **uitbrei dingen**.
    - **Instellingen**: Voer de instellingen in die u wilt configureren. Voor een lijst van alle instellingen en wat ze doen raadpleegt u:

        - [macOS](kernel-extensions-settings-macos.md)

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en in de lijst weergegeven. Zorg ervoor dat u [het profiel toewijst](../device-profile-assign.md) en [de status ervan controleert](../device-profile-monitor.md).

## <a name="next-steps"></a>Volgende stappen

Nadat het profiel is gemaakt, is het klaar om te worden toegewezen. Vervolgens kunt u [het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).
