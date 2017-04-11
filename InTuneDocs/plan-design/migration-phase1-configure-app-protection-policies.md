---
title: Beveiligingsbeleid voor apps configureren bij een Intune-migratie | Microsoft Docs
description: In dit artikel wordt beschreven welke stappen u moet uitvoeren om het beveiligingsbeleid voor apps te configureren bij een Intune-migratie.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 35543604ed68393e859517e32f5186247be001df
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>Fase 1: beveiligingsbeleid voor apps configureren (optioneel)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Met het beveiligingsbeleid voor apps kunt u vele beveiligingsmaatregelen treffen, zoals apps versleutelen, een pincode definiëren wanneer de app is geopend en verhinderen dat apps worden uitgevoerd op gejailbreakte of geroote apparaten. Als de telefoon van de gebruiker zoekgeraakt of gestolen is, kunt u met behulp van het beveiligingsbeleid voor mobiele apps op selectieve wijze de bedrijfsgegevens op afstand wissen terwijl de persoonlijke gegevens intact worden gelaten.

Met het beveiligingsbeleid voor apps wordt beveiliging toegepast op appniveau en apparaten hoeven hiervoor niet te worden ingeschreven. Het kan worden gebruikt bij apparaten die bij Intune zijn ingeschreven of waarvoor dat niet geldt. Bovendien kan het worden gebruikt bij apparaten die zijn ingeschreven bij een externe MDM-provider.

## <a name="app-protection-policies-with-lob-apps"></a>Beveiligingsbeleid voor apps bij LOB-apps

U kunt het beveiligingsbeleid voor mobiele apps ook uitbreiden naar uw LOB-apps (line-of-business) door gebruik te maken van de [Microsoft Intune App SDK](https://docs.microsoft.com/intune/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) of de Microsoft Intune App Wrapping Tool voor zowel het [IOS](https://www.microsoft.com/en-us/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True)- als [Android](https://www.microsoft.com/en-us/download/details.aspx?id=47267)-platform.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Hoe draagt het beveiligingsbeleid voor apps bij aan de migratie?

Bij de migratie moeten apparaten worden verwijderd bij de voorgaande MDM-provider en moeten ze worden ingeschreven bij Intune. U moet hiervoor een planning maken en uw eindgebruikers aanmoedigen om bij de voorgaande MDM-provider weg te gaan en hun apparaten direct in te schrijven bij Intune. Het kan echter voorkomen dat gebruikers tijdens de migratie vertraging oplopen bij de inschrijving en dat hun apparaten door geen van beide MDM-providers worden beheerd.

Tijdens deze periode is uw organisatie kwetsbaarder voor de diefstal van apparaten en het verlies van bedrijfsgegevens als de toegang tot bedrijfsresources nog steeds is toegestaan en/of verlies van de gebruikersproductiviteit als de toegang tot bedrijfsresources is geblokkeerd.

Met Intune kunnen bedrijfsgegevens tijdens de migratie worden beveiligd zodat uw bedrijfsgegevens nog steeds worden beveiligd, ook al is er geen beheer meer op apparaatniveau.

Wanneer u voorwaardelijke toegang in de oude MDM-provider uitschakelt, kunnen gebruikers nog steeds productief zijn terwijl u ze opneemt in Intune.

## <a name="task-list-for-app-protection-policies"></a>Takenlijst voor het beveiligingsbeleid voor apps

-   Taak 1: meer informatie over [de voorbereiding voor het configureren van het beveiligingsbeleid voor mobiele apps](https://docs.microsoft.com/en-us/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

-   Taak 2: meer informatie over [het maken en implementeren van het beveiligingsbeleid voor mobiele apps](https://docs.microsoft.com/en-us/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="next-steps"></a>Volgende stappen 

[Fase 1: speciale overwegingen bij migraties](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

