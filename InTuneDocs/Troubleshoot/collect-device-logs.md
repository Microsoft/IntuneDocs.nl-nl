---
title: Apparaatlogboeken verzamelen | Microsoft Intune
description: Informatie over het verzamelen van logboeken van uw beheerde apparaten.
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 19b0b502d2c8c261947c461f27a0e8153df5b186
ms.openlocfilehash: 1e65c1fa25e273ba03218f79ebeff611138e8013


---

# <a name="device-logs"></a>Apparaatlogboeken

Het is mogelijk dat u in het kader van uw probleemoplossingsinspanningen ook logboeken van gebruikersapparaten wilt verzamelen. De instructies voor het verzamelen van deze logboeken worden hier beschreven. Normaal gesproken hebt u toegang tot het apparaat nodig of moet u de gebruiker vragen de logboeken te verzamelen en naar u te verzenden.

### <a name="android-logs"></a>Android-logboeken
De Android-logboeken bevinden zich in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*. 

Soms zijn de bestanden niet zichtbaar, met name op nieuwere Android-apparaten. Als dit het geval is, moeten uw gebruikers de bedrijfsportal-app voor Android openen, naar **Instellingen** gaan, **Logboeken kopiëren** kiezen en vervolgens hun apparaat opnieuw opstarten. 

Zie de volgende artikelen voor meer informatie over hoe uw gebruikers u gegevenslogboeken kunnen sturen:

- [Uitgebreide logboekregistratie gebruiken zodat de IT-beheerder problemen met het apparaat kan oplossen](/intune/enduser/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): beschrijft hoe gebruikers uitgebreide logboekregistratie kunnen inschakelen, waardoor automatisch al hun gegevenslogboeken naar u worden verzonden. Uitgebreide logboekregistratie is standaard ingeschakeld.

- [Android-logboeken met diagnostische gegevens naar de IT-beheerder verzenden via e-mail](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android) 

- [Logboeken met diagnostische gegevens naar de IT-beheerder verzenden met een USB-kabel](/intune/enduser/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a>iOS-logboeken

Gebruikers kunnen u registratiefouten verzenden, zoals wordt beschreven in [iOS-registratiefouten verzenden naar de IT-beheerder](/intune/enduser/send-errors-to-your-it-admin-ios).

### <a name="mac-os-x-logs"></a>Mac OS X-logboeken

1. Open de app **Console**.
2. Kies onder **BESTANDEN** de optie **system.log**.
3. Kies in de menubalk boven aan het scherm **Bestand** > **Een kopie opslaan als...** en sla het bestand op.

### <a name="windows-phone"></a>Windows Phone

In de Windows Phone-bedrijfsportal-app kiezen gebruikers de **...** om het menu te openen en vervolgens **Logboeken verzenden** kiezen. Deze optie is beschikbaar zowel voor- als nadat u zich bij de bedrijfsportal-app hebt aangemeld.

### <a name="windows"></a>Windows

Voor de Windows-bedrijfsportal bevinden de logboeken zich in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.



<!--HONumber=Nov16_HO2-->


