---
title: Apparaten beheren met Microsoft Intune - Azure | Microsoft Docs
description: Bekijk de apparaten die u met Microsoft Intune beheert, exporteer een lijst met apparaten naar de CSV-indeling, bekijk apparaten die zijn gekoppeld aan Azure Active Directory, bekijk een wijzigingenlogboek van acties op het apparaat, gebruik TeamViewer-Connector waarmee IT-beheerders op afstand problemen met Android-apparaten kunnen oplossen en bekijk alle acties die u op uw apparaten kunt uitvoeren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/02/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.openlocfilehash: 3dbf299633239ae16553e9fbc8d411c4aa37cd8a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189274"
---
# <a name="what-is-microsoft-intune-device-management"></a>Wat is Microsoft Intune-apparaatbeheer?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als IT-beheerder moet u ervoor zorgen dat de beheerde apparaten de resources leveren waarmee uw gebruikers hun werk kunnen doen, terwijl u de gegevens beveiligt tegen risico's.

De workload **Apparaten** biedt inzicht in de apparaten die u beheert en geeft u de mogelijkheid om taken op afstand voor deze apparaten uit te voeren.

## <a name="get-to-your-devices"></a>Uw apparaten ophalen

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaten**. Deze weergave bevat gedetailleerde informatie over de afzonderlijke apparaten en wat u kunt ermee kunt doen, inclusief:

   - **Overzicht** bevat een visuele momentopname van de ingeschreven apparaten en laat zien hoeveel apparaten de verschillende platformen gebruiken, waaronder Android, iOS en meer.
   - **Alle apparaten** geeft een lijst weer met de ingeschreven apparaten die u beheert.

     Met de functie **Exporteren** maakt u een CSV-lijst van alle apparaten in stappen van 10.000 (Internet Explorer) of 30.000 (Microsoft Edge, Chrome).

     Selecteer een apparaat om [meer gegevens over het apparaat weer te geven](device-inventory.md), zoals gegevens over de hardware, geïnstalleerde apps en de nalevingsbeleidsstatus.

   - **Azure AD-apparaten** geeft een lijst weer met apparaten die zijn ingeschreven bij, of deel uitmaken van Azure Active Directory (Azure AD). Meer informatie over [Azure AD-apparaatbeheer](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - **Apparaatacties** bevat een geschiedenis van de acties op afstand die zijn uitgevoerd op verschillende apparaten, inclusief de actie, de status ervan, de persoon die de actie heeft gestart en het tijdstip.

     ![Schermafbeelding van acties voor het bewaken van apparaten](./media/monitor-device-actions.png)

   - **Auditlogboeken** bevatten een lijst met activiteiten die een wijziging in Intune genereren. [Auditlogboeken](monitor-audit-logs.md) bevatten meer details.
   - **TeamViewer-connector** is een service waarmee gebruikers van met Intune beheerde Android-apparaten hulp op afstand kunnen krijgen van hun IT-beheerder. Meer informatie over [TeamViewer](device-profile-android-teamviewer.md).
   - **Help en ondersteuning** bevat een snelkoppeling naar tips voor probleemoplossing of het controleren van de status van Intune.

## <a name="available-device-actions"></a>Beschikbare apparaatbedreigingen
De beschikbaarheid van de acties is afhankelijk van het apparaatplatform en de configuratie van het apparaat.

- [Inventaris van apparaten weergeven](device-inventory.md)
- Externe apparaatacties uitvoeren:
    - [Buiten gebruik stellen](devices-wipe.md#retire)
    - [Wissen](devices-wipe.md#wipe)
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

- Selecteer in **Alle apparaten** een apparaat om meer informatie over het apparaat weer te geven.
- Kies **Apparaatacties** om de status te zien van acties die zijn uitgevoerd op apparaten die u beheert.
