---
title: Overzicht van de app-levenscyclus voor Microsoft Intune
description: Meer informatie over de levenscyclus van beheerde apps in Microsoft Intune. De app-levenscyclus omvat het toevoegen, implementeren, configureren, beveiligen en buiten gebruik stellen van apps.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: apps
ms.openlocfilehash: 853873480beb5e95a195e04e251cea9975ce03b4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="overview-of-the-app-lifecycle-in-microsoft-intune"></a>Overzicht van de app-levenscyclus in Microsoft Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

De levenscyclus van de Microsoft Intune-app begint zodra een app wordt toegevoegd. Vervolgens doorloopt de app aanvullende fasen totdat u de app verwijdert. Wanneer u deze fasen begrijpt, weet u alles wat u nodig hebt om aan de slag te gaan met app-beheer in Intune.

![De levenscyclus van de app](./media/app-lifecycle.png "de levenscyclus van de Intune-app")

## <a name="add"></a>Toevoegen

De eerste stap in de implementatie van apps is het toevoegen van de apps die u wilt beheren en toewijzen aan Intune. U kunt met veel verschillende typen apps werken, maar de basisprocedures zijn hetzelfde. Met Intune kunt u verschillende app-typen toevoegen, zoals apps die intern zijn ontwikkeld (line-of-business), apps uit de Store, apps die zijn ingebouwd en apps op het web. Zie [Apps toevoegen aan Microsoft Intune](apps-add.md) voor meer informatie over deze app-typen. 

## <a name="deploy"></a>Implementeer

Nadat u de app aan Intune hebt toegevoegd, kunt u deze [toewijzen aan gebruikers en apparaten die u beheert](apps-deploy.md). In Intune is dit proces gemakkelijk en zodra de app is geïmplementeerd, kunt u [het succes bewaken](apps-monitor.md) van de implementatie vanuit Intune in Azure Portal. Bovendien kunt u in sommige app-stores, zoals die van [Apple](vpp-apps-ios.md) en [Windows](windows-store-for-business.md), bulksgewijs app-licenties voor uw bedrijf kopen. Intune kan gegevens synchroniseren met deze stores zodat u het licentiegebruik voor deze typen apps kunt implementeren en bijhouden vanuit de Intune-beheerconsole.

## <a name="configure"></a>Configureren

Als onderdeel van de app-levenscyclus worden er regelmatig nieuwe versies van apps uitgebracht. Intune biedt hulpprogramma's waarmee u eenvoudig uw geïmplementeerde [apps kunt bijwerken](apps-add.md) naar een nieuwere versie. Daarnaast kunt u voor sommige apps extra functionaliteit configureren:
- Met [beleidsregels voor de configuratie van iOS-apps](app-configuration-policies-use-ios.md) kunt u instellingen opgeven voor compatibele iOS-apps die worden gebruikt wanneer de app wordt uitgevoerd. Voor een app kunnen bijvoorbeeld bepaalde instellingen vereist zijn voor de huisstijl of de naam van de server waarmee verbinding moet worden gemaakt.
- Met de [beleidsregels voor Managed Browser](app-configuration-managed-browser.md) kunt u instellingen configureren voor de Intune Managed Browser die de standaardbrowser van het apparaat vervangt, en kunt u beperkingen instellen voor de websites die uw gebruikers mogen bezoeken.

## <a name="protect"></a>Beveiligen

Intune biedt tal van manieren om de gegevens in uw apps te beveiligen. De belangrijkste methoden zijn:
- [Voorwaardelijke toegang](conditional-access.md), waarmee u toegang regelt tot e-mail en andere services op basis van voorwaarden die u opgeeft. Voorwaarden omvatten apparaattypen of naleving van een [nalevingsbeleid voor apparaten](device-compliance.md) dat u hebt geïmplementeerd.
- [Beleid voor app-beveiliging](app-protection-policy.md) werkt met afzonderlijke apps om de gebruikte bedrijfsgegevens te beveiligen. U kunt bijvoorbeeld beperkingen instellen voor het kopiëren van gegevens tussen onbeheerde apps en de apps die u beheert, of u kunt voorkomen dat apps worden uitgevoerd op apparaten waarop jailbreaking of rooting is uitgevoerd.

## <a name="retire"></a>Buiten gebruik stellen

Waarschijnlijk raken de apps die u hebt geïmplementeerd, uiteindelijk verouderd en moeten deze worden verwijderd. In Intune kunt u gemakkelijk [apps buiten gebruik stellen](device-management.md).

## <a name="next-steps"></a>Volgende stappen:

- Meer informatie over [app-beheer in Microsoft Intune](app-management.md)