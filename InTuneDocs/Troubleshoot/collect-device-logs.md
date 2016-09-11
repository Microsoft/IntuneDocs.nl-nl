---
title: Apparaatlogboeken verzamelen | Microsoft Intune
description: 
keywords: 
author: Nbigman
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3233346702cf6de968abb251e885dc208d7720c
ms.openlocfilehash: 183888119325568c857240a038740898a630a696


---

# Apparaatlogboeken

Het is mogelijk dat u in het kader van uw probleemoplossingsinspanningen ook logboeken van gebruikersapparaten wilt verzamelen. De instructies voor het verzamelen van deze logboeken worden hier beschreven. Normaal gesproken hebt u toegang tot het apparaat nodig of moet u de gebruiker vragen de logboeken te verzamelen en naar u te verzenden.

### Locatie van het logboek van Android
De Android-logboeken bevinden zich in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. De gebruiker kan uw de logboeken ook via e-mail verzenden, zoals wordt beschreven in [Logboeken met diagnostische gegevens over Android naar de IT-beheerder verzenden via e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android).

### iOS-logboeken

De gebruiker kan u registratiefouten verzenden, zoals wordt beschreven in [iOS-registratiefouten verzenden naar de IT-beheerder](/intune/enduser/send-errors-to-your-it-admin-ios).

### Mac-apparaten met OS X

1. Open de app **Console**.
2. Kies onder **BESTANDEN** de optie **system.log**.
3. Kies in de menubalk boven aan het scherm **Bestand** > **Een kopie opslaan als...** en sla het bestand op.

### Windows Phone

In de **Windows Phone-bedrijfsportal** moet de gebruiker **...** kiezen om het menu te openen en vervolgens **Logboeken verzenden** kiezen. Deze optie is zowel voor- als nadat u zich bij de portal hebt aangemeld.

### Windows

Voor de Windows-bedrijfsportal bevinden de logboeken zich in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Sep16_HO2-->


