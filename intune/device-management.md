---
title: Apparaten beheren met Intune
titleSuffix: Intune on Azure
description: Meer informatie over het weergeven van apparaten die u met Intune beheert en de verschillende bewerkingen die u op deze apparaten kunt uitvoeren.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b034e144aa43d239874b484acb2a40be12aff7c
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Wat is Microsoft Intune-apparaatbeheer?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als IT-beheerder moet u ervoor zorgen dat de beheerde apparaten de bronnen leveren waarmee uw eindgebruikers hun werk kunnen doen, terwijl u die gegevens beveiligt tegen risico’s.

De workload **Apparaten** biedt inzicht in de apparaten die u beheert en geeft u de mogelijkheid om taken op afstand voor deze apparaten uit te voeren. Toegang krijgen tot de workload:

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies in **Intune** de optie **Apparaten**.
4. U kunt informatie over apparaten weergeven en de vermelde acties voor externe apparaten als volgt uitvoeren:
    - **Overzicht**: een momentopname van de ingeschreven apparaten die u kunt beheren.
    - **Alle apparaten**: een lijst met de ingeschreven apparaten die u beheert. Kies **Filter** of **Kolommen** om de weergegeven informatie te verfijnen. Selecteer een apparaat om [de inventaris van het apparaat weer te geven](device-inventory.md).
    - **Azure AD-apparaten**: een lijst met apparaten die zijn ingeschreven bij, of deel uitmaken van Azure Active Directory (AD). Meer informatie over [Azure AD-apparaatbeheer](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
    - **Apparaatacties**: een geschiedenis van de acties op afstand die zijn uitgevoerd op het apparaat, inclusief de actie, de status ervan, de persoon die de actie heeft gestart en het tijdstip.

    ![Apparaatacties bewaken](./media/monitor-device-actions.png)

    - **TeamViewer**: met de TeamViewer-service kunnen gebruikers van met Intune beheerde Android-apparaten hulp op afstand krijgen van hun IT-beheerder. Meer informatie over [TeamViewer](device-profile-android-teamviewer.md).

## <a name="available-device-actions"></a>Beschikbare apparaatbedreigingen
De beschikbaarheid van de acties is afhankelijk van het apparaatplatform en de configuratie van het apparaat.

- [Inventaris van apparaten weergeven](device-inventory.md)
- Externe apparaatacties uitvoeren:
    - [Bedrijfsgegevens verwijderen](devices-wipe.md#remove-company-data)
    - [Fabrieksinstellingen terugzetten](devices-wipe.md#factory-reset)
    - [Vergrendelen op afstand](device-remote-lock.md)
    - [Wachtwoordcode opnieuw instellen](device-passcode-reset.md)
    - [Activeringsvergrendeling overslaan](device-activation-lock-bypass.md) (alleen iOS)
    - [Nieuwe start](device-fresh-start.md) (alleen Windows)
    - [Modus Apparaat verloren](device-lost-mode.md) (alleen iOS)
    - [Apparaat zoeken](device-locate.md) (alleen iOS)
    - [Opnieuw starten](device-restart.md) (alleen Windows)
    - [Windows 10-pincode opnieuw instellen](device-windows-pin-reset.md)
    - [Beheer op afstand voor Android](device-profile-android-teamviewer.md)
    - [Apparaat synchroniseren](device-sync.md)


## <a name="next-steps"></a>Volgende stappen

- Kies **Apparaatacties** om de status te zien van acties die zijn uitgevoerd op apparaten die u beheert.
