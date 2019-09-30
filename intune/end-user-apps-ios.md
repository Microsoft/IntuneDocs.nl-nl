---
title: Hoe uw iOS-gebruikers hun apps downloaden
description: Manieren om Windows-apps beschikbaar te stellen voor eindgebruikers
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/07/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8f069405d75b196c26c9c844e0d0a4bd57299199
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/19/2019
ms.locfileid: "71239308"
---
# <a name="how-your-ios-users-get-their-apps"></a>Hoe uw iOS-gebruikers hun apps downloaden

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Gebruik deze informatie om te begrijpen hoe en waar uw eindgebruikers de apps downloaden die u distribueert via Microsoft Intune.

**Vereiste apps**: apps die door de beheerder worden vereist en die op het apparaat worden geïnstalleerd met minimale tussenkomst van de gebruiker, afhankelijk van het platform.

**Beschikbare apps**: apps die zijn opgegeven in de lijst van de bedrijfsportal-app en die een gebruiker optioneel kan installeren.

**Beheerde apps** zijn apps die kunnen worden beheerd via beleid en die zijn 'verpakt' door Intune of zijn gebouwd met de Intune App Software Development Kit (SDK). Deze apps kunnen worden beheerd door Intune en hierop kan app-beveiligingsbeleid worden toegepast.

**Niet-beheerde apps**: apps die gebruikers kunnen downloaden uit de iOS App Store die niet zijn geïntegreerd met de Intune App SDK. Intune heeft geen controle over de distributie, het beheer of het selectief wissen van deze apps.  

Het wordt door Apple verboden om LOB- (Line-Of-Business) en beheerde App Store-apps in de bedrijfsportal-app te vermelden. Dit probleem wordt omzeild doordat gebruikers met tegels in de bedrijfsportal-app voor iOS op één locatie (de bedrijfsportalwebsite) naar verschillende weergaven worden verwezen voor alle apps.

Geregistreerde gebruikers krijgen hun apps door te tikken op de volgende tegels op het scherm Apps van de bedrijfsportal-app:

- **Alle apps** verwijst naar een lijst met alle apps op het tabblad ALLE van de [bedrijfsportalwebsite](https://portal.manage.microsoft.com).

- Gebruikers gaan met **Aanbevolen apps** naar het tabblad AANBEVOLEN van de bedrijfsportalwebsite.

- **Categorieën** verwijst naar het tabblad CATEGORIEËN van de bedrijfsportalwebsite.


![Scherm iOS-bedrijfsportal-apps](./media/ios-cp-app-main-apps-screen.png)

Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor informatie over het toevoegen van apps.

## <a name="see-also"></a>Zie tevens
[Hoe uw Android-gebruikers apps downloaden](end-user-apps-android.md)

[Hoe uw Windows-gebruikers apps downloaden](end-user-apps-windows.md)
