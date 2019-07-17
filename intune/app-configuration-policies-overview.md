---
title: App-configuratiebeleid voor Microsoft Intune
titleSuffix: ''
description: Informatie over het gebruik van app-configuratiebeleid op een iOS- of Android-apparaat in Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/08/2019
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
ms.openlocfilehash: 1e5ddf39a201f1a70f997e03f0b65706853adefa
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885123"
---
# <a name="app-configuration-policies-for-microsoft-intune"></a>App-configuratiebeleid voor Microsoft Intune

Gebruik een app-configuratiebeleid in Microsoft Intune om configuratie-instellingen te leveren voor een iOS- of Android-app. Met deze configuratie-instellingen kan een app worden aangepast met een in de sector gangbare benadering voor appconfiguratie en -beheer. De instellingen van het configuratiebeleid worden gebruikt wanneer de app deze controleert, doorgaans bij de eerste keer dat de app wordt uitgevoerd.

U kunt een app-configuratiebeleid toewijzen aan een groep gebruikers en apparaten met een combinatie van toewijzingen voor opnemen en uitsluiten. Zodra u een appconfiguratiebeleid hebt toegevoegd, kunt u de toewijzingen voor het appconfiguratiebeleid instellen. Wanner u de toewijzingen voor het beleid instelt, kunt u ervoor kiezen de groep gebruikers voor wie het beleid van toepassing is op te nemen of uit te sluiten. Als u ervoor kiest een of meer groepen op te nemen, kunt u specifieke groepen selecteren waarvoor u ingebouwde groepen wilt opnemen of selecteren. Ingebouwde groepen zijn **Alle gebruikers**, **Alle apparaten** en **Alle gebruikers + alle apparaten**.

Het is bijvoorbeeld mogelijk dat u een van de volgende details moet opgeven voor een app-configuratie-instelling:

- Een aangepast poortnummer
- Taalinstellingen
- Beveiligingsinstellingen
- Huisstijlinstellingen, zoals een bedrijfslogo

Als gebruikers in plaats daarvan deze instellingen opgeven, is het mogelijk dat ze daarbij een fout maken, wat de werkbelasting van uw helpdesk zou kunnen verhogen en de acceptatie van nieuwe apps kan vertragen.

Het configuratiebeleid voor apps kan ervoor zorgen dat problemen met de instelling van apps worden voorkomen doordat u configuratie-instellingen kunt toewijzen aan een beleid dat aan gebruikers is toegewezen, voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen.

De configuratie-instellingen worden gebruikt wanneer de app deze controleert. Normaal gesproken controleert een app de configuratie-instellingen de eerste keer dat de app wordt uitgevoerd door de gebruiker.

U hebt twee opties voor het gebruik van app-configuraties met Intune:
- **Beheerde apparaten**: het apparaat wordt beheerd door Intune als MDM-provider (Mobile Device Management).
- **Beheerde apps**: een app wordt beheerd zonder apparaatinschrijving.

> [!NOTE]
> Als Microsoft Intune-beheerder kunt u bepalen welke gebruikersaccounts worden toegevoegd aan Microsoft Office-toepassingen op beheerde apparaten. U kunt de toegang beperken tot uitsluitend toegestane gebruikersaccounts van de organisatie, en persoonlijke accounts blokkeren op ingeschreven apparaten. De app-configuratie wordt verwerkt op de ondersteunende toepassingen, en niet-goedgekeurde accounts worden verwijderd en geblokkeerd.

## <a name="apps-that-support-app-configuration"></a>Apps die app-configuratie ondersteunen

### <a name="managed-devices"></a>Beheerde apparaten
U kunt de app-configuratiebeleidsregels voor apps gebruiken die hiervoor ondersteuning bieden. Ter ondersteuning van app-configuratie in Intune moeten apps zijn geschreven voor het ondersteunen van het gebruik van app-configuraties, zoals is gedefinieerd door de [Appconfig-community](https://www.appconfig.org/members). Neem contact op met de leverancier van de app voor informatie.

### <a name="managed-apps"></a>Managed apps
U kunt uw line-of-business-apps voorbereiden door de Intune App SDK in de app te integreren, of door de app in te pakken, nadat deze is ontwikkeld. Met de Intune App SDK voor iOS en Android kan uw app worden ingeschakeld voor Intune-configuratiebeleid voor app-beveiliging. Deze streeft ernaar om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo klein mogelijk te maken. Zie het [overzicht van de Intune App SDK](app-sdk.md) voor meer informatie.

## <a name="graph-api-support-for-app-configuration"></a>Graph API-ondersteuning voor app-configuratie

U kunt bovendien Graph API gebruiken om app-configuratietaken uit te voeren. Zie het Engelstalige [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

### <a name="managed-devices"></a>Beheerde apparaten

- Informatie over het gebruik van app-configuratie met uw iOS-apparaten.  Raadpleeg [App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen](app-configuration-policies-use-ios.md).
- Informatie over het gebruik van app-configuratie met uw Android-apparaten.  Zie [ App-configuratiebeleidsregels voor beheerde Android-apparaten](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Managed apps

- Informatie over het gebruik van app-configuratie met beheerde apps. Zie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).
