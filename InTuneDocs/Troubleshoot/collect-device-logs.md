---
title: Apparaatlogboeken verzamelen | Microsoft Intune
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 06/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ac5c66f57194a84580aa495a58e5281683aa1cca
ms.openlocfilehash: 4fc08fcea6cea897b9ddc3d0c00f2d83069f639d


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



<!--HONumber=Jun16_HO4-->


