---
title: Apparaten opnieuw opstarten met Microsoft Intune - Azure | Microsoft Docs
description: Gebruik de externe actie Opnieuw opstarten om Windows- en iOS-apparaten opnieuw op te starten met Microsoft Intune in Azure Portal.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/21/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 82ebf35d0eb435f2df4e6cf55274808e6fa690f4
ms.sourcegitcommit: af384c46ec8d8def6aa32c3b89947748dc6fd28f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2020
ms.locfileid: "76517538"
---
# <a name="remotely-restart-devices-with-intune"></a>Apparaten extern opnieuw opstarten met Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

De apparaatactie **Opnieuw opstarten** zorgt ervoor dat het apparaat dat kiest, opnieuw wordt opgestart (binnen 5 minuten). De eigenaar van het apparaat wordt niet op de hoogte gesteld dat het apparaat opnieuw wordt opgestart. Hierdoor kan eventueel werk verloren gaan.

## <a name="supported-platforms"></a>Ondersteunde platforms

- Windows: ondersteund op Windows 8.1 en hoger
- Windows Phone: ondersteund op Windows 8.1 en hoger
- Android-kioskapparaten - Ondersteund op Android 7.0 en hoger
- iOS: ondersteund

    > [!Note]  
    > Voor deze opdracht is een apparaat onder supervisie en het vereist toegangsrecht **Apparaatvergrendeling** vereist. Het apparaat wordt onmiddellijk opnieuw opgestart. iOS-apparaten die met een wachtwoordcode zijn vergrendeld, worden na het opnieuw opstarten niet aan een Wi-Fi-netwerk toegevoegd. Nadat het apparaat opnieuw is opgestart, kan het mogelijk niet meer communiceren met de server.
- macOS: niet ondersteund
- Android-apparaten en apparaten met Android- werkprofiel - niet ondersteund

## <a name="restart-a-device"></a>Apparaten opnieuw opstarten

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer **Apparaten** > **Alle apparaten**.
4. Kies een apparaat in de lijst met apparaten die u beheert > **Opnieuw opstarten** > **Ja**.

## <a name="next-steps"></a>Volgende stappen

- Selecteer **Apparaten** > **Apparaatacties** om de status van de apparaatactie **Opnieuw opstarten** te bekijken.
