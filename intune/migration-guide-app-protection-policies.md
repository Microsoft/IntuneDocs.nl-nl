---
title: Beveiligingsbeleid voor apps configureren bij een Intune-migratie
description: In dit artikel wordt beschreven welke stappen u moet uitvoeren om het beveiligingsbeleid voor apps te configureren bij een Intune-migratie.
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: d3c176b84a8555de245a1f4014c39885e50ab21d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="configure-app-protection-policies-optional"></a>Beveiligingsbeleid voor apps configureren (optioneel)


Met beveiligingsbeleid voor apps kunt u:
* apps versleutelen
* een pincode definiëren wanneer de app wordt geopend
* apps op jailbroken of geroote apparaten en veel andere beveiligingen blokkeren.

Als de telefoon van de gebruiker zoekraakt of gestolen is, kunt u op selectieve wijze de bedrijfsgegevens op afstand wissen terwijl de persoonlijke gegevens intact worden gelaten.

Met het beveiligingsbeleid voor apps wordt beveiliging toegepast op appniveau en apparaten hoeven hiervoor niet te worden ingeschreven. U kunt het gebruiken bij apparaten die bij Intune zijn geregistreerd of waarvoor dat niet geldt. Bovendien kunt u het gebruiken bij apparaten die zijn ingeschreven bij een externe MDM-provider.

## <a name="app-protection-policies-with-lob-apps"></a>Beveiligingsbeleid voor apps bij LOB-apps

U kunt het beveiligingsbeleid voor mobiele apps ook uitbreiden naar uw LOB-apps (line-of-business) door gebruik te maken van de [Microsoft Intune App SDK](app-sdk-get-started.md) of de Microsoft Intune App Wrapping Tool voor zowel het [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True)- als [Android](https://www.microsoft.com/download/details.aspx?id=47267)-platform.

## <a name="how-do-app-protection-policies-help-during-migration"></a>Hoe draagt het beveiligingsbeleid voor apps bij aan de migratie?

Bij de migratie moeten apparaten worden verwijderd bij de voorgaande MDM-provider en geregistreerd bij Intune. U moet hiervoor een planning maken en uw eindgebruikers aanmoedigen om bij de voorgaande MDM-provider weg te gaan en hun apparaten direct in te schrijven bij Intune. Het kan echter voorkomen dat gebruikers tijdens de migratie vertraging oplopen bij de inschrijving en dat hun apparaten door geen van beide MDM-providers worden beheerd.

Tijdens deze periode is uw organisatie kwetsbaarder voor de diefstal van apparaten en het verlies van bedrijfsgegevens als de toegang tot bedrijfsresources nog steeds is toegestaan. Het kan ook leiden tot productiviteitsverlaging als de toegang tot bedrijfsbronnen is geblokkeerd.

Met Intune kunnen bedrijfsgegevens tijdens de migratie worden beveiligd zodat uw bedrijfsgegevens nog steeds worden beveiligd, ook al is er geen beheer meer op apparaatniveau.

Wanneer u voorwaardelijke toegang in de oude MDM-provider uitschakelt, kunnen gebruikers nog steeds productief zijn terwijl u ze opneemt in Intune.

## <a name="task-list-for-app-protection-policies"></a>Takenlijst voor het beveiligingsbeleid voor apps

1. [Een beveiligingsbeleid voor apps maken](app-protection-policies.md#create-an-app-protection-policy)
2. [Een beleid implementeren](app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a>Volgende stappen

[Speciale overwegingen bij migratie](migration-guide-considerations.md)
