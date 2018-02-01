---
title: Hoe uw iOS-gebruikers hun apps downloaden
description: Manieren om Windows-apps beschikbaar te stellen voor eindgebruikers
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 31bb6cf7d118e121a5a8d8a74f92c2b3cf5da7bc
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-your-ios-users-get-their-apps"></a>Hoe uw iOS-gebruikers hun apps downloaden

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Gebruik deze informatie om te begrijpen hoe en waar uw eindgebruikers de apps downloaden die u distribueert via Microsoft Intune.

**Vereiste apps**: apps die door de beheerder worden vereist en die op het apparaat worden geïnstalleerd met minimale tussenkomst van de gebruiker, afhankelijk van het platform.

**Beschikbare apps**: apps die zijn opgegeven in de lijst van de bedrijfsportal-app en die een gebruiker optioneel kan installeren.

**Beheerde apps** zijn apps die kunnen worden beheerd via beleid en die zijn 'verpakt' door Intune of zijn gebouwd met de Intune App Software Development Kit (SDK). Deze apps kunnen worden beheerd door Intune en hierop kan app-beveiligingsbeleid worden toegepast.

**Niet-beheerde apps**: apps die niet kunnen worden beheerd via beleid en die niet zijn verpakt door Intune of waarin de Intune App SDK niet is opgenomen. Het toepassingsbeleid kan niet worden toegepast op deze apps.

Het wordt door Apple verboden om LOB- (Line-Of-Business) en beheerde App Store-apps in de bedrijfsportal-app te vermelden. Dit probleem wordt omzeild doordat gebruikers met tegels in de bedrijfsportal-app voor iOS op één locatie (de bedrijfsportalwebsite) naar verschillende weergaven worden verwezen voor alle apps.

Geregistreerde gebruikers krijgen hun apps door te tikken op de volgende tegels op het scherm Apps van de bedrijfsportal-app:

- **Alle apps** verwijst naar een lijst met alle apps op het tabblad ALLE van de [bedrijfsportalwebsite](https://portal.manage.microsoft.com).

- Gebruikers gaan met **Aanbevolen apps** naar het tabblad AANBEVOLEN van de bedrijfsportalwebsite.

- **Categorieën** verwijst naar het tabblad CATEGORIEËN van de bedrijfsportalwebsite.


![Scherm iOS-bedrijfsportal-apps](./media/ios-cp-app-main-apps-screen.png)

In [Apps toevoegen voor geregistreerde apparaten](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md) leest u hoe u apps toevoegt en ze in deze tegels plaatst.

### <a name="see-also"></a>Zie ook
[Hoe uw Android-gebruikers apps downloaden](end-user-apps-android.md)

[Hoe uw Windows-gebruikers apps downloaden](end-user-apps-windows.md)
