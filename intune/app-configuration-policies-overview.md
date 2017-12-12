---
title: App-configuratiebeleidsregels voor Intune | Microsoft Docs
titlesuffix: Azure portal
description: Informatie over het gebruik van app-configuratiebeleidsregels voor Intune.
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 727bf031a9e8a4c761d8d7b0c1d2737398a0fb7e
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/08/2017
---
# <a name="app-configuration-policies-for-intune"></a>App-configuratiebeleidsregels voor Intune

Voorzien in instellingen wanneer gebruikers een iOS- of Android-app uitvoeren met app-configuratiebeleidsregels in Microsoft Intune. Een app kan gebruikers bijvoorbeeld verplichten het volgende op te geven:

- Een aangepast poortnummer.
- Taalinstellingen.
- Beveiligingsinstellingen.
- Huisstijlinstellingen, zoals een bedrijfslogo.

Als gebruikers deze instellingen niet correct opgeven, kan dit de werkbelasting van uw helpdesk verhogen en de acceptatie van nieuwe apps vertragen.

Het configuratiebeleid voor apps kan ervoor zorgen dat deze problemen worden voorkomen doordat u deze instellingen bij gebruikers in een beleid kunt toewijzen voordat de gebruikers de app uitvoeren. De instellingen worden vervolgens automatisch aangeleverd, en de gebruikers hoeven geen enkele actie te ondernemen.

U wijst dit beleid niet rechtstreeks toe aan gebruikers en apparaten. In plaats daarvan koppelt u een beleid aan een app en wijst u vervolgens de app toe. De beleidsinstellingen worden gebruikt wanneer de app deze controleert (doorgaans de eerste keer dat de app wordt uitgevoerd).

U hebt twee opties voor het gebruik van app-configuraties met Intune:
 - **Beheerde apparaten**  
   Het apparaat wordt beheerd door Intune als MDM-provider (Mobile Device Management).
 - **Beheerde apps**  
   Een app wordt beheerd zonder apparaatinschrijving.

## <a name="apps-that-support-app-configuration"></a>Apps die app-configuratie ondersteunen

U kunt de app-configuratiebeleidsregels voor apps gebruiken die hiervoor ondersteuning bieden. Ter ondersteuning van app-configuratie in Intune moeten apps zijn geschreven voor het ondersteunen van het gebruik van app-configuraties. Neem contact op met de leverancier van de app voor informatie.

U kunt uw line-of-business-apps voorbereiden door de Intune App SDK in de app te integreren, of door de app in te pakken, nadat deze is ontwikkeld. Met de Intune App SDK voor iOS en Android kan uw app worden in geschakeld voor Intune-beleid voor app-beveiliging. Deze streeft ernaar om het aantal door de app-ontwikkelaar vereiste codewijzigingen zo klein mogelijk te maken. Zie het [overzicht van de Intune App SDK](app-sdk.md) voor meer informatie.

## <a name="graph-api-support-for-app-configuration"></a>Graph API-ondersteuning voor app-configuratie

U kunt bovendien Graph API gebruiken om app-configuratietaken uit te voeren. Zie het Engelstalige [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create) voor meer informatie.

## <a name="next-steps"></a>Volgende stappen

### <a name="managed-devices"></a>Beheerde apparaten

 - Informatie over het gebruik van app-configuratie met uw iOS-apparaten.  Zie [ App-configuratiebeleidsregels voor beheerde iOS-apparaten toevoegen](app-configuration-policies-use-ios.md).
 - Informatie over het gebruik van app-configuratie met uw Android-apparaten.  Zie [ App-configuratiebeleidsregels voor beheerde Android-apparaten](app-configuration-policies-use-android.md).

### <a name="managed-apps"></a>Managed apps

 - Informatie over het gebruik van app-configuratie met beheerde apps. Zie [App-configuratiebeleidsregels toevoegen voor beheerde apps zonder apparaatinschrijving](app-configuration-policies-managed-app.md).