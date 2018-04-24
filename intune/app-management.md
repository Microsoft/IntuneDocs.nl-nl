---
title: Wat is appbeheer in Microsoft Intune?
titlesuffix: ''
description: Meer informatie over de basisbeginselen van appbeheer met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 86cb0dfb67e81a7abbdc8f38dcbf5539b9855adb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="what-is-microsoft-intune-app-management"></a>Wat is Microsoft Intune-appbeheer?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met Microsoft Intune kunt u, als IT-beheerder, de mobiele apps beheren die de werknemers van uw bedrijf gebruiken. Deze functionaliteit is een aanvulling op het beheren van apparaten en beschermen van gegevens. Als onderdeel van deze functionaliteit is het een van uw prioriteiten om ervoor te zorgen dat uw eindgebruikers toegang hebben tot de apps die ze nodig hebben voor hun werk. Dit kan om de volgende redenen een uitdaging zijn:
- Er is een breed scala aan apparaatplatformen en app-typen.
- U moet apps wellicht op zowel bedrijfsapparaten als de eigen apparaten van gebruikers beheren.
- U moet ervoor zorgen dat uw netwerk en uw gegevens beveiligd blijven.

Verder wilt u misschien apps toewijzen en beheren op apparaten die niet bij Intune zijn geregistreerd.

Intune biedt een scala aan mogelijkheden om u te helpen de benodigde apps op de gekozen apparaten te krijgen. De volgende tabel bevat een samenvatting van de mogelijkheden voor app-beheer. Onder de tabel vindt u meer informatie over Microsoft Intune in de Azure-portal.

## <a name="app-management-capabilities-by-platform"></a>App-beheermogelijkheden per platform

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Apps toevoegen en aan apparaten en gebruikers toewijzen|Ja|Ja|Ja|Ja|
|Toewijzen van apps aan apparaten die niet zijn geregistreerd met Intune|Ja|Ja|Nee|Nee|
|Beleidsregels voor app-configuratie gebruiken om het opstartgedrag van apps te beheren|Nee|Ja|Nee|Nee|
|Gebruik beleid voor de inrichting van mobiele apps om verlopen apps te vernieuwen|Nee|Ja|Nee|Nee|
|Bedrijfsgegevens in apps beveiligen met app-beveiligingsbeleid|Ja|Ja|Nee|Nee<sup>1</sup>|
|Alleen zakelijke gegevens verwijderen uit een geïnstalleerde app (App selectief wissen)|Ja|Ja|Ja|Ja|
|App-toewijzingen controleren|Ja|Ja|Ja|Ja|
|Apps die in een app-winkel zijn gekocht via een volume-aankoopprogramma, toewijzen en bijhouden|Nee|Nee|Nee|Ja|
|Verplichte installatie van apps op apparaten (Vereist)<sup>2</sup>|Ja|Ja|Ja|Ja|
|Optionele installatie op apparaten via de bedrijfsportal (Beschikbare installatie)|Ja|Ja|Ja|Ja|
|Installatiesnelkoppeling naar een app op het web (webkoppeling)|Ja|Ja|Ja|Ja|
|Interne apps (Line-Of-Business-apps)|Ja|Ja|Nee|Ja|
|Apps uit een store|Ja|Ja|Ja|Ja|
|Apps bijwerken|Ja|Ja|Ja|Ja|

<sup>1</sup> U kunt gebruikmaken van [Windows Information Protection](windows-information-protection-configure.md) om apps op apparaten met Windows 10 te beveiligen.

<sup>2</sup>Alleen van toepassing op apparaten die worden beheerd door Intune.

## <a name="how-to-get-started"></a>Aan de slag

U vindt de meeste dingen die op apps betrekking hebben in de workload **Mobiele apps** die als volgt toegankelijk is:

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Mobiele apps** op de blade **Intune**.

    ![De workload Mobiele apps](./media/apps-workload.png)

De onderstaande informatie komt overeen met de beschikbare opties in de blade **Mobiele apps**.

### <a name="manage"></a>Manage
- **Apps**: selecteer deze optie als u de apps die uw werknemers gebruiken, wilt toevoegen, weergeven, toewijzen en bewaken. Zie de volgende artikelen voor meer informatie:
    - [Apps toevoegen](apps-add.md)
    - [Apps toewijzen](apps-deploy.md)
    - [Apps controleren](apps-monitor.md)
- **App-configuratiebeleid**: hiermee kunt u instellingen opgeven die mogelijk vereist zijn wanneer een gebruiker een app uitvoert. Zie de volgende artikelen voor meer informatie:
    - [App-configuratiebeleidsregels voor Intune](app-configuration-policies-overview.md)
        - [Beleid voor de configuratie van iOS-apps](app-configuration-policies-use-ios.md)
        - [Beleid voor de configuratie van Android-apps](app-configuration-policies-use-android.md)
- **App-beveiligingsbeleid**: hiermee kunt u instellingen aan een app koppelen om de bedrijfsgegevens te beveiligen die in de app worden gebruikt. U kunt bijvoorbeeld de mogelijkheden van een app om met andere apps te communiceren beperken of vereisen dat de gebruiker een pincode voor toegang tot een bedrijfsapp invoert. Zie het volgende artikel voor meer informatie:
    - [App-beveiligingsbeleid](app-protection-policies.md)
- **App selectief wissen**: alleen zakelijke gegevens verwijderen van een gebruikersapparaat dat u selecteert. Zie het volgende artikel voor meer informatie:
    - [App selectief wissen](apps-selective-wipe.md)
- **iOS-app-inrichtingsprofiel**: iOS-apps hebben een inrichtingsprofiel en code die zijn ondertekend met een certificaat. Wanneer het certificaat is verlopen, kan de app niet meer worden uitgevoerd. Intune biedt u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen toe te wijzen aan apparaten met apps die bijna zijn verlopen. Zie het volgende artikel voor meer informatie:
    - [Inrichtingsprofielen voor iOS-apps](app-provisioning-profile-ios.md)

Zie [Apps beheren](app-management.md) voor meer informatie.

### <a name="monitor"></a>Monitor
- **App-licenties**: apps die in de app-stores zijn gekocht via een volume-aankoopprogramma weergeven, toewijzen en bewaken. Zie de volgende artikelen voor meer informatie:
    - [iOS-apps die zijn gekocht via het volume-aankoopprogramma (VPP)](vpp-apps-ios.md)
    - [Microsoft Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](windows-store-for-business.md)
- **Gevonden apps**: hier worden alle apps weergegeven die zijn toegewezen door Intune en op een apparaat zijn geïnstalleerd.
- **Installatiestatus van de app**: hier wordt de status weergegeven van een app-toewijzing die u hebt gemaakt.
- **Status van de app-beveiliging**: hier wordt de status weergegeven van een app-beveiligingsbeleid voor een gebruiker die u selecteert.
- **Auditlogboeken**: hier worden activiteiten door alle IT-beheerders voor de Intune-app weergegeven.

Zie [Apps bewaken](apps-monitor.md) voor meer informatie.

### <a name="setup"></a>Setup
- **VPP-tokens voor iOS**: voor het toepassen en weergeven van uw VPP-licenties (Volume Purchase Program) voor iOS.
    - [iOS-apps die zijn gekocht via het volume-aankoopprogramma](vpp-apps-ios.md)
- **Windows Enterprise-certificaat**: voor het toepassen of weergeven van de status van een certificaat voor ondertekening van programmacode die wordt gebruikt voor het distribueren van LOB-apps naar uw beheerde Windows-apparaten.
- **Windows Symantec-certificaat**: voor het toepassen of weergeven van een Symantec-certificaat voor ondertekening van programmacode die nodig is voor het distribueren van XAP- en WP8.x-appx-bestanden naar Windows 10 Mobile-apparaten.
- **Microsoft Store voor Bedrijven**: integratie met Microsoft Store voor Bedrijven instellen. Nadat u dit hebt gedaan, kunt u gekochte toepassingen synchroniseren met Intune, deze toewijzen en uw licentiegebruik bijhouden. Zie het volgende artikel voor meer informatie:
    - [Microsoft Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](windows-store-for-business.md)
- **Windows-sleutels voor extern laden**: u kunt een Windows-sleutel voor extern laden toevoegen die kan worden gebruikt om een app rechtstreeks te installeren op apparaten in plaats van de app te publiceren en downloaden vanuit de Windows Store. Zie het volgende artikel voor meer informatie:
    - [Een Windows-app extern laden](app-sideload-windows.md)
- **Aangepaste stijl van de bedrijfsportal**: u kunt de bedrijfsportal aanpassen aan de huisstijl van uw bedrijf. Zie het volgende artikel voor meer informatie:
    - [Bedrijfsportal configureren](company-portal-app.md)
- **App-categorieën**: voor het toevoegen, vastmaken en verwijderen van namen van app-categorieën.
- **Android for Work**: voor het goedkeuren en synchroniseren van de apps die u hebt goedgekeurd voor uw onderneming. Zie het volgende artikel voor meer informatie:
    - [Android for Work-apps](apps-add-android-for-work.md)

### <a name="help-and-support"></a>Help en ondersteuning
- **Help en ondersteuning**: problemen oplossen, ondersteuning aanvragen of de status van Intune weergeven. Zie het volgende artikel voor meer informatie:
    - [Problemen oplossen](help-desk-operators.md)

## <a name="next-steps"></a>Volgende stappen

- [Een app toevoegen aan Microsoft Intune](apps-add.md)
