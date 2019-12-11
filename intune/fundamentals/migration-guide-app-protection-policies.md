---
title: Beveiligingsbeleid voor apps configureren tijdens migratie
titleSuffix: Microsoft Intune
description: In dit artikel wordt beschreven welke stappen u moet uitvoeren om het beveiligingsbeleid voor apps te configureren bij een Microsoft Intune-migratie.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8fab3ea722e94f2613a0fb1e474a16ecb5971569
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72585269"
---
# <a name="configure-app-protection-policies-optional"></a>Beveiligingsbeleid voor apps configureren (optioneel)


Met beveiligingsbeleid voor apps kunt u:
* apps versleutelen
* een pincode definiëren wanneer de app wordt geopend
* apps op jailbroken of geroote apparaten en veel andere beveiligingen blokkeren.

Als de telefoon van de gebruiker zoekraakt of gestolen is, kunt u op selectieve wijze de bedrijfsgegevens op afstand wissen terwijl de persoonlijke gegevens intact worden gelaten.

Met het beveiligingsbeleid voor apps wordt beveiliging toegepast op appniveau en apparaten hoeven hiervoor niet te worden ingeschreven. U kunt het gebruiken bij apparaten die bij Intune zijn geregistreerd of waarvoor dat niet geldt. Bovendien kunt u het gebruiken bij apparaten die zijn ingeschreven bij een externe MDM-provider.

## <a name="app-protection-policies-with-lob-apps"></a>Beveiligingsbeleid voor apps bij LOB-apps

U kunt het beveiligingsbeleid voor mobiele apps ook uitbreiden naar uw LOB-apps (Line-Of-Business) door gebruik te maken van de [Microsoft Intune App SDK](../developer/app-sdk-get-started.md) of de Microsoft Intune App Wrapping Tool voor zowel iOS- als Android-platforms. Raadpleeg [App Wrapping Tool voor iOS](../developer/app-wrapper-prepare-ios.md) en [App Wrapping Tool voor Android](./../developer/app-wrapper-prepare-android.md) voor meer informatie. Raadpleeg ook [LOB-apps voorbereiden voor app-beveiliging](../developer/apps-prepare-mobile-application-management.md).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Hoe draagt het beveiligingsbeleid voor apps bij aan de migratie?

Bij de migratie moeten apparaten worden verwijderd bij de voorgaande MDM-provider en geregistreerd bij Intune. U moet hiervoor een planning maken en uw eindgebruikers aanmoedigen om bij de voorgaande MDM-provider weg te gaan en hun apparaten direct in te schrijven bij Intune. Het kan echter voorkomen dat gebruikers tijdens de migratie vertraging oplopen bij de inschrijving en dat hun apparaten door geen van beide MDM-providers worden beheerd.

Tijdens deze periode is uw organisatie kwetsbaarder voor de diefstal van apparaten en het verlies van bedrijfsgegevens als de toegang tot bedrijfsresources nog steeds is toegestaan. Het kan ook leiden tot productiviteitsverlaging als de toegang tot bedrijfsbronnen is geblokkeerd.

Met Intune kunnen bedrijfsgegevens tijdens de migratie worden beveiligd zodat uw bedrijfsgegevens nog steeds worden beveiligd, ook al is er geen beheer meer op apparaatniveau.

Wanneer u voorwaardelijke toegang in de oude MDM-provider uitschakelt, kunnen gebruikers nog steeds productief zijn terwijl u ze opneemt in Intune.

## <a name="task-list-for-app-protection-policies"></a>Takenlijst voor het beveiligingsbeleid voor apps

- [App-beveiligingsbeleid maken en toewijzen](~/apps/app-protection-policies.md)

## <a name="next-steps"></a>Volgende stappen

[Speciale overwegingen bij migratie](migration-guide-considerations.md)
