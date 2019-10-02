---
title: App-configuratiebeleid voor Microsoft Intune
titleSuffix: ''
description: Informatie over het gebruik van app-configuratiebeleid op een iOS- of Android-apparaat in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af81552942805bed07e818d6005231e9305b3460
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71725787"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>App-configuratiebeleid voor Microsoft Intune

Door App-configuratiebeleid kunnen problemen met app-instellingen worden voorkomen doordat u configuratie-instellingen kunt toewijzen aan beleid dat aan eindgebruikers wordt toegewezen voordat ze de app uitvoeren. De instellingen worden vervolgens automatisch verstrekt wanneer de app wordt geconfigureerd op het apparaat van eindgebruikers. Eindgebruikers hoeven zelf geen actie te ondernemen. De configuratie-instellingen zijn uniek voor elke app. 

U kunt app-configuratiebeleid maken en gebruiken om configuratie-instellingen te verstrekken voor zowel iOS- als Android-apps. Met deze configuratie-instellingen kan een app worden aangepast met behulp van app-configuratie en -beheer. De configuratiebeleidsinstellingen worden gebruikt wanneer deze instellingen in de app worden gecontroleerd, doorgaans als de app voor het eerst wordt uitgevoerd. 

Het is bijvoorbeeld mogelijk dat u een van de volgende details moet opgeven voor een app-configuratie-instelling:

- Een aangepast poortnummer
- Taalinstellingen
- Beveiligingsinstellingen
- Huisstijlinstellingen, zoals een bedrijfslogo

Als deze instellingen in plaats daarvan door eindgebruikers zouden kunnen worden ingevoerd, zouden ze daarbij fouten kunnen maken. Met App-configuratiebeleid kan de consistentie in een onderneming toenemen en het aantal telefoontjes naar de helpdesk worden beperkt van eindgebruikers die proberen de instellingen zelf te configureren. Door gebruik te maken van app-configuratiebeleid kunnen apps eenvoudiger en sneller worden geaccepteerd.

De beschikbare configuratieparameters worden uiteindelijk bepaald door de ontwikkelaars van de app. De documentatie van de leverancier van de toepassing moet worden gecontroleerd om te zien of een app configuratie ondersteunt en welke configuraties beschikbaar zijn. Voor sommige toepassingen worden de beschikbare configuratie-instellingen door Intune bepaald. 

> [!NOTE]
> In de beheerde Google Play Store worden apps die configuratie ondersteunen als zodanig gemarkeerd:
> 
> ![Schermopname van een geconfigureerde app](./media/app-configuration-policies-overview/configured-app.png)
>
> U krijgt alleen apps van de [Beheerde Google Play Store](https://play.google.com/work) te zien, niet van de [Google Play Store](https://play.google.com/store/apps), wanneer u Beheerde apparaten gebruikt als het registratietype voor Android-apparaten. Apps van de Beheerde Google Play Store, ook bekend als Android for work (AfW) en Android Enterprise, zijn de apps in het werkprofiel die de app-versies bevatten die app-configuratie ondersteunen.

U kunt app-configuratiebeleid toewijzen aan een groep eindgebruikers en apparaten door een combinatie van [toewijzingen voor opnemen en uitsluiten](apps-inc-exl-assignments.md) te gebruiken. Zodra u een appconfiguratiebeleid hebt toegevoegd, kunt u de toewijzingen voor het appconfiguratiebeleid instellen. Wanner u de toewijzingen voor het beleid instelt, kunt u ervoor kiezen de [groepen](../fundamentals/groups-add.md) eindgebruikers op wie het beleid van toepassing is op te nemen of uit te sluiten. Als u ervoor kiest een of meer groepen op te nemen, kunt u specifieke groepen selecteren waarvoor u ingebouwde groepen wilt opnemen of selecteren. Ingebouwde groepen zijn **Alle gebruikers**, **Alle apparaten** en **Alle gebruikers + alle apparaten**.

U hebt twee opties voor het gebruik van app-configuratiebeleid met Intune:
- **Beheerde apparaten**: het apparaat wordt beheerd door Intune als MDM-provider (Mobile Device Management). De app moet zodanig zijn ontworpen dat deze ondersteuning biedt voor app-configuratie.
- **Beheerde apps**: een app die is ontwikkeld om de Intune App SDK te integreren. Dit is bekend als Mobile Application Management zonder registratie ([MAM-WE](app-management.md#mobile-application-management-mam-basics)). U kunt ook een app inpakken om de Intune App SDK te implementeren en te ondersteunen. Zie [Line-Of-Business-apps voor app-beveiligingsbeleid voorbereiden](../developer/apps-prepare-mobile-application-management.md) voor meer informatie over het inpakken van apps.

    > [!NOTE]
    > In door Intune beheerde apps wordt de status van App-configuratiebeleid van Intune gecontroleerd volgens een interval van 30 minuten wanneer deze zijn geïmplementeerd in combinatie met App-beveiliging van Intune. Als App-beveiliging van Intune niet aan de gebruiker is toegewezen, wordt de interval voor het controleren van App-configuratiebeleid van Intune ingesteld op 720 minuten.

## <a name="apps-that-support-app-configuration"></a>Apps die app-configuratie ondersteunen

### <a name="managed-devices"></a>Beheerde apparaten
U kunt app-configuratiebeleid gebruiken voor apps die hiervoor ondersteuning bieden. Apps bieden alleen ondersteuning voor app-configuratie van Intune als deze zodanig zijn geschreven dat ze app-configuraties ondersteunen, zoals is gedefinieerd door het besturingssysteem. Neem contact op met de leverancier van de app voor meer informatie over welke app-configuratiesleutels worden ondersteund.

### <a name="managed-apps"></a>Managed apps
U kunt uw Line-Of-Business-apps voorbereiden door de [Intune App SDK](../developer/app-sdk.md) in de app te integreren of door de app nadat deze is ontwikkeld in te pakken met behulp van de [Intune App Wrapping Tool](../developer/apps-prepare-mobile-application-management.md). In de Intune App SDK wordt ernaar gestreefd om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo laag mogelijk te houden. Zie het [overzicht van de Intune App SDK](../developer/app-sdk.md) voor meer informatie. Zie [Line-Of-Business-apps voorbereiden voor app-beveiligingsbeleid](../developer/apps-prepare-mobile-application-management.md#feature-comparison) voor een vergelijking tussen de Intune App SDK en de Intune App Wrapping tool.

Als u **Beheerde apps** selecteert als het **Type apparaatregistratie**, verwijst dat gewoonlijk naar apps die zijn geconfigureerd via Intune-configuratiebeleid op een apparaat dat niet is geregistreerd bij Apparaatbeheer, terwijl **Beheerde apparaten** van toepassing zijn op apps die zijn geïmplementeerd via het MDM-kanaal en dus door Intune worden beheerd. Selecteer de gewenste keuze op basis van deze beschrijvingen. 

![Type apparaatregistratie](./media/app-configuration-policies-overview/device-enrollment-type.png)

> [!NOTE]
> Voor apps met meerdere identiteiten, zoals Microsoft Outlook, kunnen gebruikersvoorkeuren worden overwogen. Zo worden voor het Postvak IN met prioriteit de gebruikersinstellingen gerespecteerd en wordt de configuratie ervan niet gewijzigd. Met andere parameters kunt u bepalen of een gebruiker de instelling wel of niet kan wijzigen. Zie [Configuratie-instellingen voor de Outlook-app voor iOS en Android implementeren](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) voor meer informatie.

## <a name="validate-the-applied-app-configuration-policy"></a>Het toegepaste app-configuratiebeleid valideren

U kunt op de volgende drie manieren het app-configuratiebeleid valideren:

   1. Zichtbaar op het apparaat. Vertoont de doel-app het gedrag dat is toegepast in App-configuratiebeleid?
   2. Via diagnostische logboeken (zie de sectie Diagnostische logboeken hieronder).
   3. In de Intune-Portal. In de sectie **Controleren** van een beleidsregel is de relevante status te zien:

      ![Eerste schermopname van de installatiestatus van het apparaat](./media/app-configuration-policies-overview/device-install-status-1.png)

      ![Tweede schermopname van de installatiestatus van het apparaat](./media/app-configuration-policies-overview/device-install-status-2.png)

      Onder **Intune** -> **Apparaten** -> **Alle apparaten** worden verder met de optie **App-configuratie**  aan de linkerkant van het scherm alle toegewezen beleidsregels en de status ervan weergegeven:

      ![Schermopname van de app-configuratie](./media/app-configuration-policies-overview/app-configuration.png)

## <a name="graph-api-support-for-app-configuration"></a>Graph API-ondersteuning voor app-configuratie

U kunt Graph API gebruiken om app-configuratietaken uit te voeren. Zie het Engelstalige [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) voor meer informatie.

## <a name="troubleshooting"></a>Probleemoplossing

### <a name="using-logs-to-show-a-configuration-parameter"></a>Logboeken gebruiken om een configuratieparameter weer te geven
Wanneer in de logboeken een configuratieparameter wordt weergegeven die van toepassing is maar niet lijkt te werken, is er mogelijk een probleem met de configuratie-implementatie van de app-ontwikkelaar. Als u eerst contact opneemt met de app-ontwikkelaar of de kennisdatabase van de app-ontwikkelaar raadpleegt, kunt u zich mogelijk een ondersteuningsgesprek met Microsoft besparen. Als het een probleem betreft met de manier waarop de configuratie wordt verwerkt in een app, moet dit probleem worden opgelost in een toekomstige bijgewerkte versie van die app.

## <a name="next-steps"></a>Volgende stappen

### <a name="managed-devices"></a>Beheerde apparaten

- Informatie over het gebruik van app-configuratie met uw iOS-apparaten.  Raadpleeg [App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen](app-configuration-policies-use-ios.md).
- Informatie over het gebruik van app-configuratie met uw Android-apparaten.  Zie [ App-configuratiebeleidsregels voor beheerde Android-apparaten](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Managed apps

- Informatie over het gebruik van app-configuratie met beheerde apps. Zie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).
