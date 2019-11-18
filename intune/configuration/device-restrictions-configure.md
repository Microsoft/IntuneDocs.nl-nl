---
title: Apparaatfuncties beperken met behulp van beleid in Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel toevoegen om functies op Android-, macOS-, iOS-, iPadOS-, Windows Phone- en Windows 10-apparaten in Microsoft Intune te beperken
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cfa640d5858479b5f98009e92f005312966f536a
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73755278"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Apparaatbeperkingsinstellingen configureren in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune bevat beleidsregels voor apparaatbeperkingen waarmee beheerders Android-, iOS-, macOS-en Windows-apparaten kunnen beheren. Met deze beperkingen kunt u een breed scala aan instellingen en functies beheren voor het beveiligen van de resources van uw organisatie. Beheerders kunnen bijvoorbeeld het volgende:

- Het gebruik van de camera van het apparaat toestaan of blokkeren
- Toegang beheren tot Google Play, app-stores, documenten weergeven en gamen
- Ingebouwde apps blokkeren of een lijst maken met apps die zijn toegestaan of verboden
- Het maken van een back-up van bestanden naar cloud- en opslagaccounts toestaan of voorkomen
- De minimale wachtwoordlengte instellen en eenvoudige wachtwoorden blokkeren

Deze functies zijn beschikbaar in Intune en kunnen worden geconfigureerd door de beheerder. Intune maakt gebruik van configuratieprofielen om deze instellingen te maken voor en af te stemmen op de behoeften van uw organisatie. Nadat u deze functies aan een profiel hebt toegevoegd, kunt u het profiel pushen naar en implementeren op apparaten in uw organisatie.

In dit artikel wordt beschreven hoe u een apparaatbeperkingsprofiel maakt. U kunt ook alle beschikbare instellingen voor de verschillende platformen zien.

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het beleid. Geef uw beleid een naam zodat u het later eenvoudig kunt identificeren. Een goede beleidsnaam is bijvoorbeeld **iOS: Camera op apparaten blokkeren**.
    - **Beschrijving**: Voer een beschrijving in voor het beleid. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies het platform van uw apparaten. Uw opties zijn:  

        - **Android**
        - **Android Enterprise**
        - **iOS/iPadOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 en hoger**
        - **Windows 10 en hoger**

    - **Profieltype**: Selecteer **Apparaatbeperkingen**.

        Als u een apparaatbeperkingsprofiel wilt maken voor Windows 10 Team-apparaten, zoals Surface Hub, kiest u **Apparaatbeperkingen (Windows 10 Team)** .

4. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Kies uw platform voor gedetailleerde instellingen:

    - [Android-instellingen](../device-restrictions-android.md)
    - [Instellingen voor Android Enterprise](../device-restrictions-android-for-work.md)
    - [Instellingen voor iOS/iPadOS](device-restrictions-ios.md)
    - [macOS-instellingen](device-restrictions-macos.md)
    - [Windows Phone 8.1-instellingen](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Windows 10-instellingen](device-restrictions-windows-10.md)
    - [Windows 10 Team-instellingen](device-restrictions-windows-10-teams.md)
    - [Instellingen van Windows Holographic for Business](device-restrictions-windows-holographic.md)

5. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en weergegeven in de lijst met profielen.

## <a name="next-steps"></a>Volgende stappen

Nadat het profiel is gemaakt, is het klaar om te worden toegewezen. Vervolgens kunt u [het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/device-restrictions-configure/disable-android-camera.png)

-->
