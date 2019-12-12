---
title: Naslag voor toepassingsentiteiten
titleSuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Toepassing van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4a8fa34673340e4adca7b64707d8c79d4808460
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74290947"
---
# <a name="reference-for-application-entities"></a>Naslag voor toepassingsentiteiten

De categorie **Toepassing** bevat entiteiten voor apparaten waarmee gegevens worden bijgehouden, zoals:

- Versies van een app
- Installatiebron van een app
- Type ontwikkelaars die een app hebben gemaakt
- Beheerde softwaretypen voor een app, bijvoorbeeld **sidecar** of **desktop**
- VPP-status (Volume Purchasing Program) van een app

## <a name="apprevisions"></a>appRevisions

De entiteit **AppRevision** biedt een overzicht van alle versies van apps.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| appKey |De unieke id van de app. |123 |
| applicationId |De unieke id van de app, vergelijkbaar met AppKey, maar dit is een natuurlijke sleutel |b66bc706-ffff-7437-0340-032819502773 |
| revision |De versie zoals vermeld door de beheerder tijdens het uploaden van het binaire bestand. |2 |
| title |De titel van de app. |Excel |
| publisher |De uitgever van de app. |Microsoft |
| uploadState |De uploadstatus van de app. |1 |
| appTypeKey |Verwijzing naar AppType zoals beschreven in de volgende sectie | |
| vppProgramTypeKey |Verwijzing naar VppProgramType zoals hieronder beschreven. | |
| creationTime |Het tijdstip waarop deze revisie is gemaakt. |11/23/2016 12:00:00 AM |
| modifiedTime |De laatste keer dat er iets aan deze revisie is gewijzigd. |11/23/2016 12:00:00 AM |
| grootte |De grootte van het binaire bestand. | |
| startDateInclusiveUTC |De datum en tijd in UTC waarop deze app-revisie is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| endDateExclusiveUTC |De datum en tijd in UTC waarop deze app-revisie verouderd is geraakt. |11/23/2016 12:00:00 AM |
| IsCurrent |Geeft aan of deze app-versie actueel is of niet aanwezig is in het datawarehouse. |Waar/onwaar |
| rowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze app-versie het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="apptypes"></a>AppTypes

De entiteit **appType** vermeldt de installatiebron van een app.

| Eigenschap  | Beschrijving |
|---------|------------|
| appTypeID |De id voor het type |
| appTypeKey |De surrogaatsleutel voor de sleutel |
| appTypeName |App-type |

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


## <a name="vppprogramtypes"></a>vppProgramTypes

De entiteit **vppProgramTypes** bevat een lijst van mogelijke VPP-programmatypen voor een app.

| Eigenschap  | Beschrijving |
|---------|------------|
| vppProgramTypeID | De id voor het type. |
| vppProgramTypeKey | De surrogaatsleutel voor de sleutel. |
| vppProgramTypeName | Het type VPP-programma. |

### <a name="example"></a>Voorbeeld

| VppProgramID  | Naam | Beschrijving |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Het VPP-programma van Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Nog niet beschikbaar | Standaardwaarde, Geen VPP. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | VPP-programma van Apple. |



## <a name="applicationinventories"></a>applicationInventories

Met de entiteit **applicationInventory** worden de toepassingen weergegeven die zich op het moment van de inventarisatieverzameling op het apparaat bevinden.

| Eigenschap  | Beschrijving |
|---------|------------|
| deviceKey | Dit is een verwijzing naar de tabel Device die de Intune-apparaat-id bevat. |
| dateKey | Verwijzing naar datumtabel waarmee de dag van de inventarisatie wordt aangegeven. |
| applicationName | De toepassingsnaam. |
| applicationVersion | Versie van de toepassing. |
| bundleSize | De grootte van de app in bytes. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates

De entiteit **mobileAppInstallState** vertegenwoordigt de installatiestatus van een mobiele toepassing nadat deze is toegewezen aan een groep apparaten, gebruikers of beide.

| Eigenschap | Beschrijving |
|---|---|
| appInstallStateKey | De unieke id van de installatiestatus van de app voor uw account. |
| appInstallState | Enum-waarde van de installatiestatus van de app. |
| appInstallStateName | Naam van de installatiestatus van de app. |



