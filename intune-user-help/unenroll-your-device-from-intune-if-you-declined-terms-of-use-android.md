---
title: Uw apparaat uit beheer verwijderen als u de gebruiksvoorwaarden hebt afgewezen | Microsoft Docs
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: dbf35b77c843b4dc084916b2c283b6c66d5f066d
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849230"
---
# <a name="remove-your-device-from-management-if-you-declined-terms-of-use"></a>Uw apparaat uit beheer verwijderen als u de gebruiksvoorwaarden hebt afgewezen

Als u de gebruiksvoorwaarden tijdens het aanmelden bij de bedrijfsportal-app hebt geweigerd, kunt u zich niet meer aanmelden bij de bedrijfsportal-app en moet u de instructies in deze tijdelijke oplossing gebruiken om uw apparaat uit Intune te verwijderen.

Wanneer u de bedrijfsportal-app op uw apparaat verwijdert, wordt uw apparaat ook uit Intune verwijderd. Uw apparaat heeft niet langer toegang tot bedrijfsbronnen. Zie [Wat gebeurt er wanneer u de registratie van uw apparaat bij Intune ongedaan maakt?](what-happens-if-you-unenroll-your-device-from-intune-android.md) voor meer informatie over wat er gebeurt als u uw apparaat uit het beheer verwijdert.

Voordat u de bedrijfsportal-app kunt verwijderen, moet u naar de instelling **Apparaatbeheerders** gaan en **Bedrijfsportal** uitschakelen. De stappen kunnen enigszins verschillen afhankelijk van het Android-apparaat dat u gebruikt.

## <a name="removing-the-device-from-the-company-portal-app"></a>Het apparaat verwijderen uit de bedrijfsportal-app

U kunt uw apparaat als volgt uit Intune verwijderen en de bedrijfsportal-app verwijderen:

1.  Ga naar**Instelling** &gt; **Beveiliging&amp; Schermvergrendeling** &gt; **Apparaatbeheerders**.

    Wanneer u deze stap uitvoert, wordt de registratie van uw apparaat onmiddellijk ongedaan gemaakt.

2.  Schakel het selectievakje of de optie bij **Bedrijfsportal** uit.

    U kunt nu de bedrijfsportal-app verwijderen.

## <a name="removing-data-collected-by-the-company-portal-app"></a>Gegevens verwijderen die door de bedrijfsportal-app zijn verzameld

U kunt als volgt alle gegevens verwijderen die de bedrijfsportal-app voor Android op uw apparaat opslaat:

  - Wis appgegevens in Toepassingen -> Klik op app- -> knop Gegevens wissen
  - Verwijder de map \storage\internal storage\Android\data\com.microsoft.windowsintune.companyportal


Nog hulp nodig? Neem contact op met het ondersteuningsteam van het bedrijf (zie de [bedrijfsportalwebsite](https://go.microsoft.com/fwlink/?linkid=2010980) voor contactgegevens) of stuur een e-mail naar het <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-team</a>.
