---
title: Hoe uw Android-gebruikers apps downloaden
description: Manieren om Android-apps beschikbaar te stellen aan eindgebruikers
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4f0364750edf2e97e2b621c27fb25bea8e0f537c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="how-your-android-users-get-their-apps"></a>Hoe uw Android-gebruikers apps downloaden

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Gebruik deze informatie om te begrijpen hoe en waar uw Android-eindgebruikers de apps downloaden die u distribueert via Microsoft Intune. De informatie kan per apparaattype verschillen (native Android-apparaten versus Samsung Knox Standard-apparaten).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Native Android-apparaten (niet-Samsung Knox Standard)

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. Er wordt een melding weergegeven waarop gebruikers vervolgens tikken om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten.|
| Required apps      | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten. Nadat de installatie is voltooid, verdwijnt de melding. |

## <a name="samsung-knox-standard-android-devices"></a>Samsung Knox Standard Android-apparaten

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. De app wordt geïnstalleerd zonder verdere tussenkomst van de gebruiker. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten.|
| Required apps      | De app wordt geïnstalleerd zonder tussenkomst van de gebruiker.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten. Nadat de installatie is voltooid, verdwijnt de melding. |

Apps kunnen wel of niet worden beheerd, zoals hieronder wordt beschreven. Het proces van het maken van apps die worden beheerd, is hetzelfde voor alle typen Android-apparaten.

**Beheerde apps**: dit zijn apps die kunnen worden beheerd via beleid. Deze zijn verpakt door Intune of gebouwd met de Intune Mobile Application Management (MAM) Software Development Kit (SDK). Deze apps kunnen worden beheerd door Intune en hierop kan een toepassingsbeleid worden toegepast.

**Niet-beheerde apps**: dit zijn apps die niet kunnen worden beheerd via beleid. Deze zijn niet verpakt door Intune of opgenomen in de Intune MAM SDK. Het toepassingsbeleid kan niet worden toegepast op deze apps.

### <a name="see-also"></a>Zie tevens
[Apps toevoegen met Microsoft Intune](apps-add.md)

[Hoe uw iOS-gebruikers hun apps downloaden](end-user-apps-ios.md)

[Hoe uw Windows-gebruikers apps downloaden](end-user-apps-windows.md)
