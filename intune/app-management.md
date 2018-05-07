---
title: Wat is appbeheer in Microsoft Intune?
titlesuffix: ''
description: Meer informatie over de basisbeginselen van appbeheer met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/11/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bc73c3637fc166bead7fd27b52aea2193995a26
ms.sourcegitcommit: 2162ed46d939b4a9b85fa4e7e9943f2fb5948f1e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2018
---
# <a name="what-is-microsoft-intune-app-management"></a>Wat is Microsoft Intune-appbeheer?


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

U kunt, als IT-beheerder, Microsoft Intune gebruiken om de mobiele apps te beheren die de werknemers van uw bedrijf gebruiken. Deze functionaliteit is een aanvulling op het beheren van apparaten en beschermen van gegevens. Een van de prioriteiten van een beheerder is om ervoor te zorgen dat eindgebruikers toegang hebben tot de apps die ze nodig hebben voor hun werk. Dit doel kan om de volgende redenen een uitdaging zijn:
- Er is een breed scala aan apparaatplatformen en app-typen.
- U moet apps wellicht op zowel bedrijfsapparaten als de persoonlijke apparaten van gebruikers beheren.
- U moet ervoor zorgen dat uw netwerk en uw gegevens beveiligd blijven.

Verder wilt u misschien apps toewijzen en beheren op apparaten die niet bij Intune zijn geregistreerd.

Intune biedt een scala aan mogelijkheden om u te helpen de benodigde apps op de apparaten te krijgen waarop u deze wilt uitvoeren. De volgende tabel bevat een samenvatting van de mogelijkheden voor appbeheer: 

## <a name="app-management-capabilities-by-platform"></a>App-beheermogelijkheden per platform

||||||
|-|-|-|-|-|
| |Android|iOS|Windows Phone 8.1|Windows 10|
|Apps toevoegen en aan apparaten en gebruikers toewijzen|Ja|Ja|Ja|Ja|
|Toewijzen van apps aan apparaten die niet zijn geregistreerd met Intune|Ja|Ja|Nee|Nee|
|Beleidsregels voor app-configuratie gebruiken om het opstartgedrag van apps te beheren|Nee|Ja|Nee|Nee|
|Gebruik beleid voor de inrichting van mobiele apps om verlopen apps te vernieuwen|Nee|Ja|Nee|Nee|
|Bedrijfsgegevens in apps beveiligen met app-beveiligingsbeleid|Ja|Ja|Nee|Nee<sup>1</sup>|
|Alleen zakelijke gegevens verwijderen uit een geïnstalleerde app (app selectief wissen)|Ja|Ja|Ja|Ja|
|App-toewijzingen controleren|Ja|Ja|Ja|Ja|
|Apps die in een app-winkel zijn gekocht via een volume-aankoopprogramma, toewijzen en bijhouden|Nee|Nee|Nee|Ja|
|Verplichte installatie van apps op apparaten (vereist)<sup>2</sup>|Ja|Ja|Ja|Ja|
|Optionele installatie op apparaten via de bedrijfsportal (beschikbare installatie)|Ja|Ja|Ja|Ja|
|Installatiesnelkoppeling naar een app op het web (webkoppeling)|Ja|Ja|Ja|Ja|
|Interne apps (Line-Of-Business-apps)|Ja|Ja|Nee|Ja|
|Apps uit een store|Ja|Ja|Ja|Ja|
|Apps bijwerken|Ja|Ja|Ja|Ja|

<sup>1</sup> U kunt gebruikmaken van [Windows Information Protection](windows-information-protection-configure.md) om apps op apparaten met Windows 10 te beveiligen.

<sup>2</sup> Alleen van toepassing op apparaten die worden beheerd door Intune.

## <a name="get-started"></a>Aan de slag

U vindt de meeste app-gerelateerde informatie in de workload **Mobiele apps** die als volgt toegankelijk is:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**.  
    Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer in het deelvenster **Microsoft Intune** de optie **Mobiele apps**.

    ![Het workloaddeelvenster Mobiele apps](./media/apps-workload.png)

De volgende vier secties beschrijven de beschikbare opties in het deelvenster **Mobiele apps**.

### <a name="manage"></a>Manage
- **Apps**: selecteer deze optie als u de apps die uw werknemers gebruiken, wilt toevoegen, weergeven, toewijzen en bewaken. Zie voor meer informatie:
    - [Apps toevoegen](apps-add.md).
    - [Apps toewijzen](apps-deploy.md).
    - [Apps controleren](apps-monitor.md).
- **App-configuratiebeleid**: selecteer deze optie om instellingen op te geven die mogelijk vereist zijn wanneer een gebruiker een app uitvoert. Zie voor meer informatie:
    - [App-configuratiebeleidsregels voor Intune](app-configuration-policies-overview.md).
        - [Beleid voor de configuratie van iOS-apps](app-configuration-policies-use-ios.md).
        - [Beleid voor de configuratie van Android-apps](app-configuration-policies-use-android.md).
- **App-beveiligingsbeleid**: selecteer deze optie om instellingen aan een app te koppelen om de bedrijfsgegevens te beveiligen die in de app worden gebruikt. U kunt bijvoorbeeld de mogelijkheden van een app om met andere apps te communiceren beperken of u kunt vereisen dat de gebruiker een pincode voor toegang tot een bedrijfsapp invoert. Zie voor meer informatie:
    - [Beleid voor app-beveiliging](app-protection-policies.md).
- **App selectief wissen**: selecteer deze optie om alleen bedrijfsgegevens van een geselecteerd gebruikersapparaat te verwijderen. Zie voor meer informatie:
    - [App selectief wissen](apps-selective-wipe.md).
- **Inrichtingsprofielen voor iOS-app**: iOS-apps hebben een inrichtingsprofiel en code die zijn ondertekend met een certificaat. Wanneer het certificaat is verlopen, kan de app niet meer worden uitgevoerd. Intune biedt u de hulpmiddelen om proactief een nieuw beleid voor inrichtingsprofielen toe te wijzen aan apparaten met apps die bijna zijn verlopen. Zie voor meer informatie:
    - [Inrichtingsprofielen voor iOS-apps](app-provisioning-profile-ios.md).

Zie [Apps beheren](app-management.md) voor meer informatie over deze sectie.

### <a name="monitor"></a>Monitor
- **App-licenties**: apps die in de app-stores zijn gekocht via een volume-aankoopprogramma weergeven, toewijzen en bewaken. Zie voor meer informatie:
    - [iOS-apps die zijn gekocht via het volume-aankoopprogramma (VPP)](vpp-apps-ios.md).
    - [Microsoft Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](windows-store-for-business.md).
- **Gevonden apps**: hier worden alle apps weergegeven die zijn toegewezen door Intune en op een apparaat zijn geïnstalleerd.
- **Installatiestatus van de app**: hier wordt de status weergegeven van een app-toewijzing die u hebt gemaakt.
- **Status van de app-beveiliging**: hier wordt de status weergegeven van een app-beveiligingsbeleid voor een gebruiker die u selecteert.
- **Auditlogboeken**: hier worden activiteiten door alle IT-beheerders voor de Intune-app weergegeven.

Zie [Apps bewaken](apps-monitor.md) voor meer informatie over deze sectie.

### <a name="set-up"></a>instellen
- **VPP-tokens voor iOS**: voor het toepassen en weergeven van uw VPP-licenties (Volume Purchase Program) voor iOS. Zie voor meer informatie:
    - [iOS-apps die zijn gekocht via het volume-aankoopprogramma](vpp-apps-ios.md)
- **Windows Enterprise-certificaat**: voor het toepassen of weergeven van de status van een certificaat voor ondertekening van programmacode die wordt gebruikt voor het distribueren van LOB-apps naar uw beheerde Windows-apparaten.
- **Windows Symantec-certificaat**: voor het toepassen of weergeven van een Symantec-certificaat voor ondertekening van programmacode die nodig is voor het distribueren van XAP- en WP8.x-appx-bestanden naar Windows 10 Mobile-apparaten.
- **Microsoft Store voor Bedrijven**: integratie met Microsoft Store voor Bedrijven instellen. Nadat u dit hebt gedaan, kunt u gekochte toepassingen synchroniseren met Intune, deze toewijzen en uw licentiegebruik bijhouden. Zie voor meer informatie:
    - [Microsoft Store voor Bedrijven-apps die via het volume-aankoopprogramma zijn gekocht](windows-store-for-business.md).
- **Windows-sleutels voor extern laden**: u kunt een Windows-sleutel voor extern laden toevoegen die kan worden gebruikt om een app rechtstreeks te installeren op apparaten in plaats van de app te publiceren en downloaden vanuit de Windows Store. Zie voor meer informatie:
    - [Side-loading van een Windows-app uitvoeren](app-sideload-windows.md).
- **Aangepaste stijl van de bedrijfsportal**: u kunt de bedrijfsportal aanpassen aan de huisstijl van uw bedrijf. Zie voor meer informatie:
    - [Bedrijfsportal configureren](company-portal-app.md).
- **App-categorieën**: voor het toevoegen, vastmaken en verwijderen van namen van app-categorieën.
- **Android for Work**: voor het goedkeuren en synchroniseren van de apps die u hebt goedgekeurd voor uw onderneming. Zie voor meer informatie:
    - [Android for Work-apps](apps-add-android-for-work.md).

### <a name="help-and-support"></a>Help en ondersteuning
- **Help en ondersteuning**: problemen oplossen, ondersteuning aanvragen of de status van Intune weergeven. Zie voor meer informatie:
    - [Problemen oplossen](help-desk-operators.md).

## <a name="next-steps"></a>Volgende stappen

- [Een app toevoegen aan Microsoft Intune](apps-add.md)
