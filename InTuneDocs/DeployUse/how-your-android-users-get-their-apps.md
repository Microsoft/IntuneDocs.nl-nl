---
title: Hoe uw Android-gebruikers hun apps downloaden | Microsoft Intune
description: Manieren om Android-apps beschikbaar te stellen aan eindgebruikers
keywords: 
author: Staciebarker
ms.author: stabar
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 627914b2ac877c1b5ff5bc95f7f2098ab8988250
ms.openlocfilehash: 98e712fb852c89c1d092b87482f30ada33010a33


---


# Hoe uw Android-gebruikers apps downloaden
Gebruik deze informatie om te begrijpen hoe en waar uw Android-eindgebruikers de apps downloaden die u distribueert via Microsoft Intune. De informatie kan per apparaattype verschillen (native Android-apparaten versus Samsung Knox-apparaten).

## Native Android-apparaten (niet-Samsung Knox)

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. Er wordt een melding weergegeven waarop gebruikers vervolgens tikken om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten.|
| Required apps      | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten. Nadat de installatie is voltooid, verdwijnt de melding. |

## Samsung Knox Android-apparaten

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. De app wordt geïnstalleerd zonder verdere tussenkomst van de gebruiker. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten.|
| Required apps      | De app wordt geïnstalleerd zonder tussenkomst van de gebruiker.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten. Nadat de installatie is voltooid, verdwijnt de melding. |

Apps kunnen wel of niet worden beheerd, zoals hieronder wordt beschreven. Het proces van het maken van apps die worden beheerd, is hetzelfde voor alle typen Android-apparaten.

**Beheerde apps**: dit zijn apps die kunnen worden beheerd via beleid. Deze zijn ingepakt door Intune of gebouwd met de Intune Mobile Application Management (MAM) Software Development Kit (SDK). Deze apps kunnen worden beheerd door Intune en hierop kan een toepassingsbeleid worden toegepast.

**Niet-beheerde apps**: dit zijn apps die niet kunnen worden beheerd via beleid. Deze zijn niet ingepakt door Intune of opgenomen in de Intune MAM SDK. Het toepassingsbeleid kan niet worden toegepast op deze apps.

### Zie tevens
[Apps toevoegen met Microsoft Intune](/intune/deploy-use/add-apps)

[Hoe uw iOS-gebruikers hun apps downloaden](how-your-ios-users-get-their-apps.md)

[Hoe uw Windows-gebruikers hun apps downloaden](how-your-windows-users-get-their-apps.md)



<!--HONumber=Oct16_HO2-->


