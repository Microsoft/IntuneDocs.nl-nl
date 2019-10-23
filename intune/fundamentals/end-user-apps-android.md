---
title: Hoe uw Android-gebruikers apps downloaden
description: Manieren om Android-apps beschikbaar te stellen aan eindgebruikers
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: fc5362df560d2e93bf5cd7a6cdc32a441d97d05c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505434"
---
# <a name="how-your-android-users-get-their-apps"></a>Hoe uw Android-gebruikers apps downloaden

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Dit artikel bevat informatie om te begrijpen hoe en waar uw Android-eindgebruikers de apps downloaden die u distribueert via Microsoft Intune. De informatie kan per apparaattype verschillen (native Android-apparaten versus Samsung Knox Standard-apparaten).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Native Android-apparaten (niet-Samsung Knox Standard)

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. Er wordt een melding weergegeven waarop gebruikers vervolgens tikken om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store. Daar starten zij de installatie.|
| Required apps      | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store. Daar starten zij de installatie. Nadat de installatie is voltooid, verdwijnt de melding. |

Uw eindgebruikers moeten installatie van onbekende bronnen toestaan om [LOB-apps](../apps/lob-apps-android.md) te kunnen installeren. Deze instelling is normaal gesproken op twee verschillende plaatsen te vinden:

* **Android 7.1.2 en lager**: **Instellingen** > **Beveiliging** > **Onbekende bronnen**
* **Android 8.0 en hoger**: **Instellingen** > **Apps en meldingen** > **Toegang tot speciale apps** > **Onbekende apps installeren** > **Bedrijfsportal** > **Toestaan van deze bron**

Als dit het geval is, zal de bedrijfsportal-app de eindgebruiker informeren en direct naar de juiste instelling begeleiden. 

## <a name="samsung-knox-standard-android-devices"></a>Samsung Knox Standard Android-apparaten

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. De app wordt geïnstalleerd zonder verdere tussenkomst van de gebruiker. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store. Daar starten zij de installatie.|
| Required apps      | De app wordt geïnstalleerd zonder tussenkomst van de gebruiker.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store. Daar starten zij de installatie. Nadat de installatie is voltooid, verdwijnt de melding. |

Apps kunnen wel of niet worden beheerd, zoals hieronder wordt beschreven. Het proces van het maken van apps die worden beheerd, is hetzelfde voor alle typen Android-apparaten.

**Beheerde apps**: dit zijn apps die worden beheerd via beleid. Ze zijn "verpakt" door Intune of gebouwd met de Intune App SDK. Deze apps kunnen worden beheerd door Intune en hierop kan een toepassingsbeleid worden toegepast.

**Niet-beheerde apps**: dit zijn apps die niet worden beheerd via beleid. Deze zijn niet verpakt door Intune of opgenomen in de Intune App SDK. Het toepassingsbeleid kan niet worden toegepast op deze apps.

## <a name="zebra-devices-with-zebra-mobility-extensions"></a>Zebra-apparaten met Zebra-mobiliteitsextensies

Intune maakt gebruik van de toolkit voor Zebra-mobiliteitsextensies (MX) om op de achtergrond apps te installeren op Zebra-apparaten die worden beheerd door de apparaatbeheerder. Met deze functie kunt u apps implementeren en bijwerken op Zebra-apparaten zonder tussenkomst van de gebruiker. Als de MX-versie op uw apparaat 4.2 of lager is, worden apps niet op de achtergrond geïnstalleerd. Zie [Full MX Feature matrix](http://techdocs.zebra.com/mx/compatibility/) op de website van Zebra voor meer informatie.

LOB-apps die worden geïmplementeerd op Zebra-apparaten, moeten worden geïnstalleerd vanaf een openbare locatie op het apparaat. Het app-pakket (.apk) is mogelijk toegankelijk voor andere apps en services die ook toegang hebben tot de openbare opslag op het apparaat. Normaal gesproken blijft deze toegang beperkt tot een klein tijdvenster tussen de voltooiing van het downloaden van de app en het begin van de installatie. In dit tijdvenster is een timing-aanval mogelijk. Zo kan een APK-pakket gedurende dit tijdvenster worden gewijzigd. Met Intune wordt de tijd dat een APK-bestand zich in openbare opslag bevindt, beperkt tot een minimum en wordt voorkomen dat niet-ondertekende apps worden geïnstalleerd. Om het beveiligingsrisico te minimaliseren, moet u ervoor zorgen dat de APK-bestanden die u uploadt, geen gevoelige informatie bevatten.

## <a name="see-also"></a>Zie tevens

[Apps toevoegen met Microsoft Intune](../apps/apps-add.md)

[Hoe uw iOS-gebruikers hun apps downloaden](end-user-apps-ios.md)

[Hoe uw Windows-gebruikers apps downloaden](end-user-apps-windows.md)
