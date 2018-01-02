---
title: Overzicht van de app-levenscyclus voor Intune
description: Meer informatie over de levenscyclus van door Intune beheerde apps; van het toevoegen tot het moment waarop ze buiten gebruik worden gesteld.
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e50e3af525be48bf058dd32bfb7b93508d500a3
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/08/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Overzicht van de app-levenscyclus

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

De levenscyclus van de Intune-app begint zodra een app wordt toegevoegd. Vervolgens doorloopt de app aanvullende fasen totdat u de app verwijdert.

![De levenscyclus van de app](./media/app-lifecycle.png "de levenscyclus van de Intune-app")

## <a name="add"></a>Toevoegen

De eerste stap in de implementatie van apps is het toevoegen van de apps die u wilt beheren en toewijzen aan Intune. U kunt met veel verschillende typen apps werken, maar de basisprocedures zijn hetzelfde. Met Intune kunt u apps toevoegen voor zowel [geregistreerde apparaten](apps-add.md) ([klassieke portal](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) als [Windows-pc's die u beheert met de Intune-clientsoftware](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

## <a name="deploy"></a>Implementeren

Nadat u de app aan Intune hebt toegevoegd, kunt u deze [toewijzen aan gebruikers en apparaten die u beheert](apps-deploy.md) ([klassieke portal](/intune-classic/deploy-use/deploy-apps)). In Intune is dit proces gemakkelijk en zodra de app is geïmplementeerd, kunt u [het succes bewaken](apps-monitor.md) ([klassieke portal](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)) van de implementatie vanuit de Intune-beheerconsole. Bovendien kunt u in sommige app stores, zoals die van [Apple](vpp-apps-ios.md) ([klassieke portal](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) en [Windows](windows-store-for-business.md) ([klassieke portal](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)), bulksgewijs app-licenties voor uw bedrijf kopen. Intune kan gegevens synchroniseren met deze stores zodat u het licentiegebruik voor deze typen apps kunt implementeren en bijhouden vanuit de Intune-beheerconsole.

## <a name="configure"></a>Configureren

Als onderdeel van de app-levenscyclus worden er regelmatig nieuwe versies van apps uitgebracht. Intune biedt hulpprogramma's waarmee u eenvoudig uw geïmplementeerde [apps kunt bijwerken](apps-add.md) ([klassieke portal](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) naar een nieuwere versie. Daarnaast kunt u voor sommige apps extra functionaliteit configureren:
- Met [beleidsregels voor de configuratie van iOS-apps](app-configuration-policies-use-ios.md) ([klassieke portal](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)) kunt u instellingen opgeven voor compatibele iOS-apps die worden gebruikt wanneer de app wordt uitgevoerd. Voor een app kunnen bijvoorbeeld bepaalde instellingen vereist zijn voor de huisstijl of de naam van de server waarmee verbinding wordt gemaakt.
- Met de [beleidsregels voor Managed Browser](app-configuration-managed-browser.md) ([klassieke portal](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)) kunt u instellingen configureren voor de Intune Managed Browser die de standaardbrowser van het apparaat vervangt, en kunt u beperkingen instellen voor de websites die uw gebruikers mogen bezoeken.

## <a name="protect"></a>Beveiligen

Intune biedt tal van manieren om de gegevens in uw apps te beveiligen. De belangrijkste methoden zijn:
- [Voorwaardelijke toegang](conditional-access.md) ([klassieke portal](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)): hiermee regelt u de toegang tot e-mail en andere services op basis van voorwaarden die u opgeeft. Voorwaarden omvatten apparaattypen of naleving van een [nalevingsbeleid voor apparaten](device-compliance.md) ([klassieke portal](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)) dat u hebt geïmplementeerd.
- [Beleid voor app-beveiliging](app-protection-policy.md) ([klassieke portal](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) werkt met afzonderlijke apps om de gebruikte bedrijfsgegevens te beveiligen. U kunt bijvoorbeeld beperkingen instellen voor het kopiëren van gegevens tussen onbeheerde apps en de apps die u beheert, of u kunt voorkomen dat apps worden uitgevoerd op apparaten waarop jailbreaking of rooting is uitgevoerd.

## <a name="retire"></a>Buiten gebruik stellen

Waarschijnlijk raken de apps die u hebt geïmplementeerd, uiteindelijk verouderd en moeten deze worden verwijderd. In Intune kunt u gemakkelijk [apps buiten gebruik stellen](device-management.md) ([klassieke portal](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
