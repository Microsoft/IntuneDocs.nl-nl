---
title: Hoe uw iOS-gebruikers hun apps downloaden
description: Manieren om Windows-apps beschikbaar te stellen voor eindgebruikers
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0061d4ecd8d71f8b7363193e36b838741aa56a92
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="how-your-ios-users-get-their-apps"></a>Hoe uw iOS-gebruikers hun apps downloaden

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Gebruik deze informatie om te begrijpen hoe en waar uw eindgebruikers de apps downloaden die u distribueert via Microsoft Intune.

**Vereiste apps**: apps die door de beheerder worden vereist en die op het apparaat worden geïnstalleerd met minimale tussenkomst van de gebruiker, afhankelijk van het platform.

**Beschikbare apps**: apps die zijn opgegeven in de lijst van de bedrijfsportal-app en die een gebruiker optioneel kan installeren.

**Beheerde apps**: apps die kunnen worden beheerd via beleid en die zijn 'verpakt' door Intune of met de Intune Mobile Application Management (MAM) Software Development Kit (SDK) zijn gebouwd. Deze apps kunnen worden beheerd door Intune en hierop kan een toepassingsbeleid worden toegepast.

**Niet-beheerde apps**: apps die niet kunnen worden beheerd via beleid en die niet zijn verpakt door Intune of waarin de Intune MAM SDK niet is opgenomen. Het toepassingsbeleid kan niet worden toegepast op deze apps.

Het wordt door Apple verboden om LOB- (Line-Of-Business) en beheerde App Store-apps in de bedrijfsportal-app te vermelden. Dit probleem wordt omzeild doordat gebruikers met tegels in de bedrijfsportal-app voor iOS op één locatie (de bedrijfsportalwebsite) naar verschillende weergaven worden verwezen voor alle apps.

Geregistreerde gebruikers krijgen hun apps door te tikken op de volgende tegels op het scherm Apps van de bedrijfsportal-app:

- **Alle apps** verwijst naar een lijst met alle apps op het tabblad ALLE van de [bedrijfsportalwebsite](https://portal.manage.microsoft.com).

- Gebruikers gaan met **Aanbevolen apps** naar het tabblad AANBEVOLEN van de bedrijfsportalwebsite.

- **Categorieën** verwijst naar het tabblad CATEGORIEËN van de bedrijfsportalwebsite.


![Scherm iOS-bedrijfsportal-apps](./media/ios-cp-app-main-apps-screen.png)

In [Apps toevoegen voor geregistreerde apparaten](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md) leest u hoe u apps toevoegt en ze in deze tegels plaatst.

### <a name="see-also"></a>Zie tevens
[Hoe uw Android-gebruikers apps downloaden](end-user-apps-android.md)

[Hoe uw Windows-gebruikers apps downloaden](end-user-apps-windows.md)
