---
title: Hoe uw Android-gebruikers hun apps downloaden | Microsoft Intune
description: Manieren om Android-apps beschikbaar te stellen aan eindgebruikers
keywords: 
author: Staciebarker
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
ms.sourcegitcommit: 300df17fd5844589a1e81552d2d590aee5615897
ms.openlocfilehash: 90f50d14fac0e335f3b7c5e0825b0bb243b7a532


---


# Hoe uw Android-gebruikers hun apps downloaden
Gebruik deze informatie om te begrijpen hoe en waar uw Android-eindgebruikers de apps downloaden die u distribueert via Microsoft Intune. De informatie voor native Android-apparaten kan afwijken van die voor Samsung Knox-apparaten.

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

**Beheerde apps**: apps die kunnen worden beheerd via beleid en die zijn ingepakt door Intune of met de Intune Mobile Application Management (MAM) Software Development Kit (SDK) zijn gebouwd. These apps can be managed by Intune, and application policies can be applied to them.

**Niet-beheerde apps**: apps die kunnen worden beheerd via beleid en die niet zijn ingepakt in Intune of waarin de Intune MAM SDK niet is opgenomen. Het toepassingsbeleid kan niet worden toegepast op deze apps.

### Zie tevens
[Apps toevoegen met Microsoft Intune](/intune/deploy-use/add-apps)
[Hoe uw iOS-gebruikers hun apps ophalen](how-your-ios-users-get-their-apps.md)
[Hoe uw Windows-gebruikers hun apps ophalen](how-your-windows-users-get-their-apps.md)



<!--HONumber=Jul16_HO4-->


