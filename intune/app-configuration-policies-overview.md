---
title: App-configuratiebeleid voor Microsoft Intune
titlesuffix: ''
description: Informatie over het gebruik van app-configuratiebeleid op een iOS- of Android-apparaat in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 06/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c04d2d8fa2e302c4d11760d3660a0a67e8b3695
ms.sourcegitcommit: b47fad133ef8ef1eb65484463431c6c53f6a638a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2018
ms.locfileid: "35291543"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>App-configuratiebeleid voor Microsoft Intune

Gebruik een app-configuratiebeleid in Microsoft Intune om configuratie-instellingen te leveren voor een iOS- of Android-app. Met deze configuratie-instellingen kan een app worden aangepast. U wijst dit configuratiebeleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een configuratiebeleid aan een app en wijst u de app vervolgens toe. De instellingen van het configuratiebeleid worden gebruikt wanneer de app deze controleert, doorgaans bij de eerste keer dat de app wordt uitgevoerd.

U kunt een app-configuratiebeleid toewijzen aan een groep gebruikers en apparaten met een combinatie van toewijzingen voor opnemen en uitsluiten. Zodra u een appconfiguratiebeleid hebt toegevoegd, kunt u de toewijzingen voor het appconfiguratiebeleid instellen. Wanner u de toewijzingen voor het beleid instelt, kunt u ervoor kiezen de groep gebruikers voor wie het beleid van toepassing is op te nemen of uit te sluiten. Als u ervoor kiest een of meer groepen op te nemen, kunt u specifieke groepen selecteren waarvoor u ingebouwde groepen wilt opnemen of selecteren. Ingebouwde groepen zijn **Alle gebruikers**, **Alle apparaten** en **Alle gebruikers + alle apparaten**.

Het is bijvoorbeeld mogelijk dat u een van de volgende details moet opgeven voor een app:

- Een aangepast poortnummer
- Taalinstellingen
- Beveiligingsinstellingen
- Huisstijlinstellingen, zoals een bedrijfslogo

Als gebruikers deze instellingen niet correct opgeven, kan dit de werkbelasting van uw helpdesk verhogen en de acceptatie van nieuwe apps vertragen.

Het configuratiebeleid voor apps kan ervoor zorgen dat deze problemen worden voorkomen doordat u deze instellingen bij gebruikers in een beleid kunt toewijzen voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen.

De configuratie-instellingen worden gebruikt wanneer de app deze controleert. Normaal gesproken controleert een app de configuratie-instellingen de eerste keer dat de app wordt uitgevoerd door de gebruiker.

U hebt twee opties voor het gebruik van app-configuraties met Intune:
 - **Beheerde apparaten**: het apparaat wordt beheerd door Intune als MDM-provider (Mobile Device Management).
 - **Beheerde apps**: een app wordt beheerd zonder apparaatinschrijving.

## <a name="apps-that-support-app-configuration"></a>Apps die app-configuratie ondersteunen

U kunt de app-configuratiebeleidsregels voor apps gebruiken die hiervoor ondersteuning bieden. Ter ondersteuning van app-configuratie in Intune moeten apps zijn geschreven voor het ondersteunen van het gebruik van app-configuraties. Neem contact op met de leverancier van de app voor informatie.

U kunt uw line-of-business-apps voorbereiden door de Intune App SDK in de app te integreren, of door de app in te pakken, nadat deze is ontwikkeld. Met de Intune App SDK voor iOS en Android kan uw app worden ingeschakeld voor Intune-app-configuratiebeleid. Deze streeft ernaar om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo klein mogelijk te maken. Zie het [overzicht van de Intune App SDK](app-sdk.md) voor meer informatie.

## <a name="graph-api-support-for-app-configuration"></a>Graph API-ondersteuning voor app-configuratie

U kunt bovendien Graph API gebruiken om app-configuratietaken uit te voeren. Zie het Engelstalige [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

### <a name="managed-devices"></a>Beheerde apparaten

 - Informatie over het gebruik van app-configuratie met uw iOS-apparaten.  Zie [ App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen](app-configuration-policies-use-ios.md).
 - Informatie over het gebruik van app-configuratie met uw Android-apparaten.  Zie [ App-configuratiebeleidsregels voor beheerde Android-apparaten](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Managed apps

 - Informatie over het gebruik van app-configuratie met beheerde apps. Zie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).
