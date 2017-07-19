---
title: Apparaten beheren met Intune
titleSuffix: Intune on Azure
description: Meer informatie over het weergeven van apparaten die u met Intune beheert en de verschillende bewerkingen die u op deze apparaten kunt uitvoeren.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>Wat is Microsoft Intune-apparaatbeheer?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De workload **Apparaten** biedt inzicht in de apparaten die u beheert en geeft u de mogelijkheid om taken op afstand voor deze apparaten uit te voeren. Toegang krijgen tot de workload:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.

U kunt nu de volgende acties uitvoeren:

- [Inventaris van apparaten weergeven](device-inventory.md)
- Externe apparaatacties uitvoeren:
    - [Bedrijfsgegevens verwijderen](device-company-data-remove.md) 
    - [Fabrieksinstellingen terugzetten](device-factory-reset.md)
    - [Vergrendelen op afstand](device-remote-lock.md)
    - [Wachtwoordcode opnieuw instellen](device-passcode-reset.md)
    - [Activeringsvergrendeling overslaan](device-activation-lock-bypass.md)
    - [Nieuwe start](device-fresh-start.md)
    - [Modus Apparaat verloren](device-lost-mode.md)
    - [Apparaat zoeken](device-locate.md)
    - [Opnieuw opstarten](device-restart.md)
    - [Windows 10-pincode opnieuw instellen](device-windows-pin-reset.md)
    - [Beheer op afstand voor Android](device-profile-android-teamviewer.md)


## <a name="support-for-each-device-action"></a>Ondersteuning voor elke apparaatactie

Gebruik de volgende tabel voor informatie over de apparaatplatformen die worden ondersteund door elke actie.

|||||||
|-|-|-|-|-|-|
|Apparaatactie|Windows|Windows Phone|iOS|macOS|Android|
|**Bedrijfsgegevens verwijderen**|Yes|Ja|Ja|Ja|Ja|
|**Fabrieksinstellingen terugzetten**|Windows 8.1 en hoger (geen met EAS beheerde apparaten)|Yes|Ja|Nee|Android for Work wordt niet ondersteund|
|**Verwijderen**|Ja|Ja|Ja|Ja|Yes|
|**Vergrendelen op afstand**|Nee|Windows Phone 8.1 en hoger|Yes|Nee|Yes|
|**Wachtwoordcode opnieuw instellen**|Nee|Windows Phone 8.1 - Windows 10-makersupdate, geen lid van Azure AD-domein, Windows 10-makersupdate en hoger - alles|Ja|Nee|Ouder dan Android 7, Android for Work niet ondersteund|
|**Nieuwe wachtwoordcode** (voor Windows 10-apparaten)|Nee|Windows 10-makersupdate en hoger (lid van Azure AD-domein)|Nee|Nee|Android for Work wordt niet ondersteund|
|**Activeringsvergrendeling overslaan**|Nee|Nee|Alleen apparaten die bedrijfseigendom zijn|Nee|Nee|
|**Modus Apparaat verloren**|Nee|Nee|iOS 9.3 of hoger, onder supervisie, en bedrijfseigendom|Nee|Nee|
|**Apparaat zoeken**|Nee|Nee|Modus Apparaat verloren van iOS 9.3 of hoger, onder supervisie, en bedrijfseigendom|Nee|Nee|
|**Huidige gebruiker afmelden**|Nee|Nee|iOS 9.3 en hoger (alleen gedeelde iPads)|Nee|Nee|
|**Opnieuw opstarten**|Windows 8.1 en hoger|Windows Phone 8.1 en hoger|Nee|Nee|Nee|
|**Nieuwe start**|Windows 10-makersupdate en hoger|Nee|Nee|Nee|Nee|
|**Nieuwe sessie van hulp op afstand**|Nee|Nee|Nee|Nee|Ja|
|**Gebruiker verwijderen**|Nee|Nee|iOS 9.3 en hoger (alleen gedeelde iPads)|Nee|Nee|

## <a name="next-steps"></a>Volgende stappen

- Kies **Apparaatacties** om de status te zien van acties die zijn uitgevoerd op apparaten die u beheert. 
![Apparaatbedreigingen bewaken](./media/monitor-device-actions.png)