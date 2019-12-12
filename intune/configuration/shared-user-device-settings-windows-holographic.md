---
title: Instellingen voor gedeelde apparaten met Windows Holographic for Business in Microsoft Intune - Azure | Microsoft Docs
description: Voeg in Microsoft Intune Windows Holographic for Business toe en gebruik dit voor het configureren voor apparaten die worden gedeeld of door meerdere gebruikers worden gebruikt. Bekijk een lijst met alle accountbeheerinstellingen en wat deze betekenen op de apparaten, inclusief Microsoft HoloLens.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9c89712539d4e5bd78cc317af2af396f8ca7006
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72492217"
---
# <a name="windows-holographic-for-business-settings-to-manage-shared-devices-using-intune"></a>Windows Holographic for Business-instellingen voor het beheren van gedeelde apparaten met Intune

Apparaten met Windows Holographic for Business, zoals de Microsoft HoloLens, kunnen door meerdere gebruikers worden gebruikt. Apparaten met meerdere gebruikers worden ook wel gedeelde apparaten genoemd. Deze maken deel uit van MDM-oplossingen (Mobile Device Management).

Met Microsoft Intune kunnen gebruikers zich met een gastaccount aanmelden op deze gedeelde apparaten. Tijdens het gebruik van deze apparaten hebben ze alleen toegang tot de functies die u inschakelt.

In dit artikel worden beschreven welke instellingen u in een Windows Holographic for Business-apparaatconfiguratieprofiel kunt gebruiken. Wanneer het profiel in Intune is gemaakt, implementeert u het of wijst u het toe aan apparaatgroepen in uw organisatie. U kunt dit profiel ook toewijzen aan een apparaatgroep met verschillende typen apparaten en besturingssysteemversies.

Zie [Control access, accounts, and power features on shared PC or multi-user devices](shared-user-device-settings.md) (Toegang, accounts en energiefuncties beheren voor gedeelde pc's en apparaten met meerdere gebruikers) voor meer informatie over deze Intune-functie. Zie [AccountManagement CSP](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp) (CSP voor accountbeheer) voor meer informatie over de Windows-CSP.

## <a name="before-your-begin"></a>Voordat u begint

[Maak het profiel](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Instellingen voor gedeelde apparaat voor meerdere gebruikers

> [!NOTE]
> Apparaten met Windows Holographic for Business, met inbegrip van de Microsoft HoloLens, ondersteunen alleen de **accountbeheer**instellingen. Als u andere instellingen in Intune configureert, inclusief de **modus Gedeelde pc**, heeft dit geen invloed op deze apparaten.

- **Accountbeheer**: kies **Inschakelen** om lokale accounts die zijn gemaakt door gasten en accounts in AD en Azure AD automatisch te verwijderen. Wanneer een gebruiker zich afmeldt op het apparaat of wanneer er systeemonderhoud wordt uitgevoerd, worden deze accounts verwijderd. Als deze optie is ingeschakeld, stelt u ook de volgende zaken in:
  - **Accountverwijdering**: Kies wanneer accounts worden verwijderd: **Bij drempelwaarde opslagruimte**, **Bij drempelwaarde opslagruimte en inactiviteit** of **Direct na afmelding**. Voer ook in:
    - **Drempelwaarde verwijderen starten(%)** : Voer een percentage van de schijfruimte in (0-100). Als de totale schijf-/opslagruimte lager is dan de ingevoerde waarde, worden de accounts in de cache verwijderd. Er worden doorlopend accounts verwijderd om schijfruimte terug te winnen. De accounts die het langst inactief zijn, worden als eerste verwijderd.
    - **Drempelwaarde verwijderen stoppen(%)** : Voer een percentage van de schijfruimte in (0-100). Als de totale schijf-/opslagruimte hetzelfde is als de ingevoerde waarde, wordt gestopt met verwijderen.

  Schakel deze optie **uit** om de lokale, AD- en Azure AD-accounts die zijn gemaakt door gasten te behouden.

  > [!NOTE]
  > Microsoft HoloLens-apparaten ondersteunen alleen de **accountbeheer**instellingen.

## <a name="next-steps"></a>Volgende stappen

- [Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).
- Bekijk de instellingen voor [Windows 10 en hoger](shared-user-device-settings-windows.md).
