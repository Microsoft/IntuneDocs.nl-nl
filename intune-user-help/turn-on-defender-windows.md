---
title: Windows Defender inschakelen | Microsoft Docs
description: Ontdek hoe u Windows Defender kunt inschakelen voor toegang tot bedrijfsresources.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/08/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: d16dd2de-3ed5-474f-a04b-36dcd350162c
searchScope:
- User help
ROBOTS: ''
ms.reviewer: shburbid
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3e8fd6941a94a24dd3b6bf98daf6adc9a47f9fa7
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72501937"
---
# <a name="turn-on-windows-defender-to-access-company-resources"></a>Windows Defender inschakelen voor toegang tot bedrijfsresources

Uw werk of school wilt er zeker van zijn dat apparaten die toegang hebben tot hun resources, beveiligd zijn. Er zijn bepaalde manieren waarop ze [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx), de ingebouwde beveiliging voor schadelijke software in Windows, kunnen gebruiken.

Er zijn enkele instellingen die u mogelijk moet wijzigen in Windows Defender om toegangsproblemen op te lossen. Voor deze stappen moet u mogelijk naar een aantal verschillende plaatsen op uw computer gaan.

## <a name="turn-on-windows-defender"></a>Windows Defender inschakelen

1. Ga naar **Start** en open **Configuratiescherm**.
2. Open **Beheerprogramma's** > **Groepsbeleid bewerken**. Hiermee opent u de **Editor voor lokaal groepsbeleid** in een nieuw venster.
3. Open **Computerconfiguratie** > **Beheersjablonen** > **Windows-onderdelen**  >  **Windows Defender Antivirus**. De instelling **Windows Defender Antivirus uitschakelen** bevindt zich onder de mappen van andere instellingen. 
4. Open **Windows Defender Antivirus uitschakelen** en zorg ervoor dat deze optie is ingesteld op **Uitgeschakeld** of **Niet geconfigureerd**.

## <a name="turn-on-real-time-protection"></a>Realtime-beveiliging inschakelen

Controleer of realtime-beveiliging is ingeschakeld door te gaan naar **Start** en te zoeken op **Windows Defender Security Center**. Selecteer **Virus and threat protection settings** (Virus- en dreigingsinstellingen) en zorg dat zowel **Real-timebeveiliging** als **Cloud-beveiliging** is ingesteld op **Aan** . Als deze opties niet worden niet weergegeven, moet u de volgende stappen uitvoeren:

1. Ga naar **Start** en open **Configuratiescherm**.
2. Open **Beheerprogramma's** > **Groepsbeleid bewerken**. Hiermee opent u de **Editor voor lokaal groepsbeleid** in een nieuw venster.
3. Open **Computerconfiguratie** > **Beheersjablonen** > **Windows-onderdelen**  >  **Windows Defender Security Center** > **Virus and threat protection** (Beveiliging tegen virussen en dreigingen).
4. Open de instelling **Virus and threat protection gebied (Beveiliging tegen virussen en dreigingen)** en stel deze optie in op **Uitgeschakeld**.

## <a name="update-your-antivirus-definitions"></a>Uw antivirus-definities bijwerken

Controleer of uw antivirus-definities zijn bijgewerkt door te gaan naar **Start** en te zoeken op **Windows Defender Security Center**. Selecteer **Beveiligingsupdates** en **Controleren op updates** om ervoor te zorgen dat uw apparaat is beveiligd tegen virussen. Als deze optie niet wordt weergegeven, volgt u de stappen in [Realtime-beveiliging inschakelen](turn-on-defender-windows.md#turn-on-real-time-protection)

Nog hulp nodig? Neem contact op met het ondersteuningsteam van uw bedrijf. Controleer of hun contactgegevens beschikbaar zijn op de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980).
