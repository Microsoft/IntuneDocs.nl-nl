---
title: Naslag voor toepassingsentiteiten
titlesuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Toepassing van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4928badbd72e3f04262aad844625c6522e86cc5f
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238367"
---
# <a name="reference-for-application-entities"></a>Naslag voor toepassingsentiteiten

De categorie **Toepassing** bevat entiteiten voor mobiele apparaten waarmee gegevens worden bijgehouden, zoals:

  -  Versies van een app
  -  Installatiebron van een app
  -  Type ontwikkelaars die een app hebben gemaakt
  -  Beheerde softwaretypen voor een app, bijvoorbeeld **sidecar** of **desktop**
  -  VPP-status (Volume Purchasing Program) van een app

## <a name="apprevision"></a>AppRevision

De entiteit **AppRevision** bevat een overzicht van alle versies van apps.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| AppKey |De unieke id van de app. |123 |
| ApplicationID |De unieke id van de app, vergelijkbaar met AppKey, maar dit is een natuurlijke sleutel |b66bc706-ffff-7437-0340-032819502773 |
| Revisie |De versie zoals vermeld door de beheerder tijdens het uploaden van het binaire bestand. |2 |
| Titel |De titel van de app. |Excel |
| Uitgever |De uitgever van de app. |Microsoft |
| UploadState |De uploadstatus van de app. |1 |
| AppTypeKey |Verwijzing naar AppType zoals beschreven in de volgende sectie | |
| VppProgramTypeKey |Verwijzing naar VppProgramType zoals hieronder beschreven. | |
| CreationTime |Het tijdstip waarop deze revisie is gemaakt. |11/23/2016 12:00:00 AM |
| ModifiedTime |De laatste keer dat er iets aan deze revisie is gewijzigd. |11/23/2016 12:00:00 AM |
| Grootte |De grootte van het binaire bestand. | |
| StartDateInclusiveUTC |De datum en tijd in UTC waarop deze app-revisie is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| EndDateExclusiveUTC |De datum en tijd in UTC waarop deze app-revisie verouderd is geraakt. |11/23/2016 12:00:00 AM |
| IsCurrent |Geeft aan of deze app-versie actueel is of niet aanwezig is in het datawarehouse. |Waar/onwaar |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze app-versie het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="apptypes"></a>AppTypes

De entiteit **AppTypes** vermeldt de installatiebron van een app.

| Eigenschap  | Beschrijving |
|---------|------------|
| AppTypeID |De id voor het type |
| AppTypeKey |De surrogaatsleutel voor de sleutel |
| AppTypeName |App-type |

### <a name="example"></a>Voorbeeld

| AppTypeID  | Naam | Beschrijving |
|---------|------------|--------|
| 0 |Android Store-app | Een Android Store-app. |
| 1 |Android LOB-app | Een Android Line-Of-Business-app. |
| 2 |Beheerde Android Store-app (MAM) | Een Android Store-app die onder beheer staat. |
| 3 |iOS Store-app | Een iOS Store-app. |
| 4 |iOS LOB-app | Een iOS Line-Of-Business-app. |
| 5 |Beheerde iOS Store-app (MAM) | Een iOS Store-app die onder beheer staat. |
| 6 |O365 Pro Plus Suite | De Office 365 Pro Plus Suite voor Windows 10. |
| 7 |Web-app | Een web-app. |
| 8 |Windows Phone 8.1 Store-app | Een Windows Phone 8.1 Store-app. |
| 9 |Windows Store-app | Een Windows Store-app. |
| 10 |Windows LOB-app | Een Windows AppX Line-Of-Business-app. |
| 11 |Windows Mobile MSI | Een MSI Line-Of-Business-app. |
| 12 |Windows Phone LOB-app | Een Windows Phone Line-of-Business-app. |


## <a name="vppprogramtypes"></a>VppProgramTypes

De entiteit **VppProgramTypes** bevat een lijst van mogelijke VPP-programmatypen voor een app.

| Eigenschap  | Beschrijving |
|---------|------------|
| VppProgramTypeID | De id voor het type. |
| VppProgramTypeKey | De surrogaatsleutel voor de sleutel. |
| VppProgramTypeName | Het type VPP-programma. |

### <a name="example"></a>Voorbeeld

| VppProgramID  | Naam | Beschrijving |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Het VPP-programma van Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Nog niet beschikbaar | Standaardwaarde, Geen VPP. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | VPP-programma van Apple. |



## <a name="applicationinventory"></a>ApplicationInventory

Met de entiteit **ApplicationInventory** worden de toepassingen weergegeven die zich op het moment van de inventarisatieverzameling op het apparaat bevinden.

| Eigenschap  | Beschrijving |
|---------|------------|
| DeviceKey | Dit is een verwijzing naar de tabel Device die de Intune-apparaat-id bevat. |
| DateKey | Verwijzing naar datumtabel waarmee de dag van de inventarisatie wordt aangegeven. |
| ApplicationName | De toepassingsnaam. |
| ApplicationVersion | Versie van de toepassing. |
| BundleSize | De grootte van de app in bytes. |

## <a name="mobileappinstallstate"></a>MobileAppInstallState

De entiteit **MobileAppInstallState** vertegenwoordigt de installatiestatus van een mobiele toepassing nadat deze is toegewezen aan een groep apparaten, gebruikers of beide.

| Eigenschap | Beschrijving |
|---|---|
| AppInstallStateKey | De unieke id van de installatiestatus van de app voor uw account. |
| AppInstallState | Enum-waarde van de installatiestatus van de app. |
| AppInstallStateName | Naam van de installatiestatus van de app. |

## <a name="mobileappdeviceuserinstallstatus"></a>MobileAppDeviceUserInstallStatus

De **MobileAppDeviceUserInstallStatus** toont de installatiestatus van een mobiele app voor een bepaald apparaat en een bepaalde gebruiker.


|      Eigenschap      |                                                         Beschrijving                                                         |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------|
|      DateKey       |                                  Sleutel van de datum waarop de installatiestatus van de app werd vastgelegd.                                  |
|       AppKey       |                             Sleutel van de mobiele app die wordt gebruikt om een exemplaar van AppRevision te identificeren.                              |
|     DeviceKey      |                              Sleutel van een doelapparaat die wordt gebruikt om een exemplaar van Device te identificeren.                               |
|      UserKey       |                                Sleutel van een doelgebruiker die wordt gebruikt om een exemplaar van User te identificeren.                                 |
| AppInstallStateKey |                     Sleutel van de installatiestatus van de app die wordt gebruikt om een exemplaar van MobileAppInstallState te identificeren.                     |
|     ErrorCode      | De foutcode geretourneerd door het app-installatieprogramma, het mobiele platform of de service met betrekking tot de installatie van de app. |

