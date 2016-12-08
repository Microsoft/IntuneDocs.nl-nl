---
title: Hoe uw iOS-gebruikers hun apps downloaden | Microsoft Intune
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
translationtype: Human Translation
ms.sourcegitcommit: 738b6bedcefbfd8bf0fa7bde5b86c79293af527e
ms.openlocfilehash: 3ba0a5cda91164761c4576df935c54390bc78f8c


---


# <a name="how-your-ios-users-get-their-apps"></a>Hoe uw iOS-gebruikers hun apps downloaden

Gebruik deze informatie om te begrijpen hoe en waar uw eindgebruikers de apps downloaden die u distribueert via Microsoft Intune.

**Vereiste apps**: apps die door de beheerder worden vereist en die op het apparaat worden geïnstalleerd met minimale tussenkomst van de gebruiker, afhankelijk van het platform.

**Beschikbare apps**: apps die zijn opgegeven in de lijst van de bedrijfsportalapp en die een gebruiker optioneel kan installeren.

**Beheerde apps**: apps die kunnen worden beheerd via beleid en die zijn 'ingepakt' door Intune of met de Intune Mobile Application Management (MAM) Software Development Kit (SDK) zijn gebouwd. These apps can be managed by Intune, and application policies can be applied to them.

**Niet-beheerde apps**: apps die niet kunnen worden beheerd via beleid en die niet zijn ingepakt door Intune of waarin de Intune MAM SDK niet is opgenomen. Het toepassingsbeleid kan niet worden toegepast op deze apps.

Het wordt door Apple verboden om LOB- (Line-Of-Business) en beheerde App Store-apps in de bedrijfsportalapp te vermelden. Dit probleem wordt omzeild doordat gebruikers met tegels in de bedrijfsportalapp voor iOS op één locatie (de bedrijfsportal-website) naar verschillende weergaven worden verwezen voor alle apps.

Geregistreerde gebruikers krijgen hun apps door te tikken op de volgende tegels op het scherm Apps van de bedrijfsportal-app:

- **Alle apps** verwijst naar een lijst met alle apps op het tabblad ALLE van de [bedrijfsportalwebsite](http://portal.manage.microsoft.com).

- Gebruikers gaan met **Aanbevolen apps** naar het tabblad AANBEVOLEN van de bedrijfsportalwebsite.

- **Categorieën** verwijst naar het tabblad CATEGORIEËN van de bedrijfsportalwebsite.

 
![Scherm iOS-bedrijfsportal-apps](./media/ios-cp-app-main-apps-screen.png)

In [Apps toevoegen voor geregistreerde apparaten](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md) leest u hoe u apps toevoegt en ze in deze tegels plaatst.

### <a name="see-also"></a>Zie tevens
[Hoe uw Android-gebruikers apps downloaden](how-your-android-users-get-their-apps.md)

[Hoe uw Windows-gebruikers apps downloaden](how-your-windows-users-get-their-apps.md)



<!--HONumber=Nov16_HO1-->


