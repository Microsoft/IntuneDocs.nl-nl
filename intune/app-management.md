---
title: Wat is app-beheer?
titleSuffix: Intune on Azure
description: Gebruik dit onderwerp voor meer informatie over de basisbeginselen van app-beheer met Microsoft Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c05b2257fe03cd23ad5ba71a3fee217cd4802650
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2017
---
# <a name="what-is-microsoft-intune-app-management"></a>Wat is Microsoft Intune-appbeheer?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Als IT-beheerder is het uw taak ervoor te zorgen dat eindgebruikers toegang hebben tot de apps die ze nodig hebben voor hun werk. Dit kan om de volgende redenen een uitdaging zijn:
- Er is een breed scala aan apparaatplatformen en app-typen.
- U moet mogelijk apps op bedrijfsapparaten en op de eigen apparaten van gebruikers beheren.
- U moet ervoor zorgen dat uw netwerk en uw gegevens beveiligd blijven.

Verder wilt u misschien apps toewijzen en beheren op apparaten die niet met Intune zijn geregistreerd.

Intune biedt een scala aan mogelijkheden om u te helpen de benodigde apps op de gekozen apparaten te krijgen.

## <a name="app-management-capabilities-by-platform"></a>App-beheermogelijkheden per platform

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Apps toevoegen en aan apparaten en gebruikers toewijzen|Yes|Ja|Ja|Ja|
|Toewijzen van apps aan apparaten die niet zijn geregistreerd met Intune|Ja|Ja|Nee|Nee|
|Beleidsregels voor app-configuratie gebruiken om het opstartgedrag van apps te beheren|Nee|Ja|Nee|Nee|
|Gebruik beleid voor de inrichting van mobiele apps om verlopen apps te vernieuwen|Nee|Ja|Nee|Nee|
|Bedrijfsgegevens in apps beveiligen met app-beveiligingsbeleid|Yes|Ja|Nee|Nee<sup>1</sup>|
|Alleen zakelijke gegevens verwijderen uit een geïnstalleerde app (App selectief wissen)|Yes|Ja|Ja|Yes|
|App-toewijzingen controleren|Ja|Ja|Ja|Yes|
|Apps die in een app-winkel zijn gekocht via een volume-aankoopprogramma, toewijzen en bijhouden|Nee|Nee|Nee|Yes|
|Verplichte installatie van apps op apparaten (Vereist)<sup>2</sup>|Ja|Ja|Ja|Yes|
|Optionele installatie op apparaten via de bedrijfsportal (Beschikbare installatie)|Yes|Ja|Ja|Yes|
|Installatiesnelkoppeling naar een app op het web (Web Clip)|Yes|Ja|Ja|Yes|
|Interne apps (Line-Of-Business-apps)|Yes|Ja|Nee|Nee|
|Apps uit een store|Yes|Ja|Ja|Yes|
|Apps bijwerken|Ja|Ja|Ja|Yes|

<sup>1</sup> U kunt gebruikmaken van [Windows Information Protection](windows-information-protection-configure.md) om apps op apparaten met Windows 10 te beveiligen.

<sup>2</sup>Alleen van toepassing op apparaten die worden beheerd door Intune.

## <a name="how-to-get-started"></a>Aan de slag

U vindt de meeste dingen die op apps betrekking hebben in de workload **Mobiele apps** die als volgt toegankelijk is:

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Mobiele apps** op de blade **Intune**.

    ![De workload Mobiele apps](./media/apps-workload.png)

### <a name="manage"></a>Manage
- **Apps**: in dit knooppunt kunt u de meeste apps toevoegen, toewijzen en bewaken.
    - [Apps toevoegen](apps-add.md)
    - [Apps toewijzen](apps-deploy.md)
    - [Apps bewaken](apps-monitor.md)
- **App-configuratiebeleid**: hiermee kunt u instellingen opgeven die mogelijk vereist zijn wanneer een gebruiker een app uitvoert.
    - [Beleid voor de configuratie van iOS-apps](app-configuration-policies-use-ios.md)
    - [Beleid voor de configuratie van Android-apps](app-configuration-policies-use-android.md)
- **App-beveiligingsbeleid**: hiermee kunt u instellingen aan een app koppelen om de bedrijfsgegevens te beveiligen die in de app worden gebruikt. U kunt bijvoorbeeld de mogelijkheden van een app om met andere apps te communiceren beperken of vereisen dat de gebruiker een pincode voor toegang tot een bedrijfsapp invoert.
    - [App-beveiligingsbeleid](app-protection-policies.md)
- **App selectief wissen**: alleen zakelijke gegevens verwijderen van een gebruikersapparaat dat u selecteert.
    - [App selectief wissen](apps-selective-wipe.md)
- **iOS-inrichtingsprofiel**: iOS-apps hebben een inrichtingsprofiel en code die is ondertekend met een certificaat. Wanneer het certificaat is verlopen, kan de app niet meer worden uitgevoerd. Intune biedt u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen toe te wijzen aan apparaten met apps die bijna zijn verlopen.
    - [Inrichtingsprofielen voor iOS-apps](app-provisioning-profile-ios.md)

### <a name="monitor"></a>Monitor
- **Apps met licenties**: apps die in de app-stores zijn gekocht via een volume-aankoopprogramma weergeven, toewijzen en bewaken.
    - [Microsoft Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](windows-store-for-business.md)
- **Gevonden apps**: hier worden alle apps weergegeven die zijn toegewezen door Intune en op een apparaat zijn geïnstalleerd.
- **Installatiestatus van de app**: hier wordt de status weergegeven van een app-toewijzing die u hebt gemaakt.
- **Status van de app-beveiliging**: hier wordt de status weergegeven van een app-beveiligingsbeleid voor een gebruiker die u selecteert.

Zie [Apps bewaken](apps-monitor.md) voor meer informatie

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **Microsoft Store voor Bedrijven**: integratie met Microsoft Store voor Bedrijven instellen. Nadat u dit hebt gedaan, kunt u gekochte toepassingen synchroniseren met Intune, deze toewijzen en uw licentiegebruik bijhouden.
    - [Microsoft Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](windows-store-for-business.md)
- **Aangepaste stijl van de bedrijfsportal**: u kunt de bedrijfsportal aanpassen aan de huisstijl van uw bedrijf.
    - [Bedrijfsportal configureren](company-portal-app.md)
