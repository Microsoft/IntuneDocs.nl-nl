---
title: Hoe uw Android-gebruikers apps downloaden
description: Manieren om Android-apps beschikbaar te stellen aan eindgebruikers
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 08/21/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 878e4d0854722d82eab0545cf3a1ba743f2c52db
ms.sourcegitcommit: 2198a39ae48beca5fc74316976bc3fc9db363659
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2018
ms.locfileid: "38224717"
---
# <a name="how-your-android-users-get-their-apps"></a>Hoe uw Android-gebruikers apps downloaden

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Gebruik deze informatie om te begrijpen hoe en waar uw Android-eindgebruikers de apps downloaden die u distribueert via Microsoft Intune. De informatie kan per apparaattype verschillen (native Android-apparaten versus Samsung Knox Standard-apparaten).

## <a name="native-non-samsung-knox-standard-android-devices"></a>Native Android-apparaten (niet-Samsung Knox Standard)

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. Er wordt een melding weergegeven waarop gebruikers vervolgens tikken om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten.|
| Required apps      | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding om de installatie te starten. Nadat de installatie is voltooid, verdwijnt de melding.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten. Nadat de installatie is voltooid, verdwijnt de melding. |

Uw eindgebruikers moeten installatie van onbekende bronnen toestaan om [LOB-apps](lob-apps-android.md) te kunnen installeren. Deze zijn normaal gesproken op twee verschillende plaatsen te vinden:

* **Android 7.1.2 en ouder**: **Instellingen** > **Beveiliging** > **Onbekende bronnen**
* **Android 8.0 en nieuwer**: **Instellingen** > **Apps en meldingen** > **Toegang tot speciale apps** > **Onbekende apps installeren** > **Bedrijfsportal** > **Toestaan van deze bron**

Als dit het geval is, zal de bedrijfsportal-app de eindgebruiker informeren en direct naar de juiste instelling begeleiden. 


## <a name="samsung-knox-standard-android-devices"></a>Samsung Knox Standard Android-apparaten

| App-type | Line-Of-Business (LOB)-apps | Play Store-apps  |
| ------------- |-------------| -----|
| Available apps      | Gebruikers tikken op **Installeren** in de bedrijfsportal. De app wordt geïnstalleerd zonder verdere tussenkomst van de gebruiker. | Gebruikers tikken op de app in de bedrijfsportal en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten.|
| Required apps      | De app wordt geïnstalleerd zonder tussenkomst van de gebruiker.    | Gebruikers krijgen een melding te zien die niet kan worden gesloten en waarin wordt aangegeven dat er een app moet worden geïnstalleerd. Gebruikers tikken op de melding en gaan naar een app-pagina in de Play Store, waar ze de installatie kunnen starten. Nadat de installatie is voltooid, verdwijnt de melding. |

Apps kunnen wel of niet worden beheerd, zoals hieronder wordt beschreven. Het proces van het maken van apps die worden beheerd, is hetzelfde voor alle typen Android-apparaten.

**Beheerde apps**: dit zijn apps die kunnen worden beheerd via beleid. Ze zijn "verpakt" door Intune of gebouwd met de Intune App SDK. Deze apps kunnen worden beheerd door Intune en hierop kan een toepassingsbeleid worden toegepast.

**Niet-beheerde apps**: dit zijn apps die niet kunnen worden beheerd via beleid. Deze zijn niet verpakt door Intune of opgenomen in de Intune App SDK. Het toepassingsbeleid kan niet worden toegepast op deze apps.

### <a name="see-also"></a>Zie ook
[Apps toevoegen met Microsoft Intune](apps-add.md)

[Hoe uw iOS-gebruikers hun apps downloaden](end-user-apps-ios.md)

[Hoe uw Windows-gebruikers apps downloaden](end-user-apps-windows.md)
