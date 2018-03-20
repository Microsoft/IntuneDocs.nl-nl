---
title: Gegevens die Intune naar Google verzendt
titleSuffix: Microsoft Intune
description: Lijst met gegevens die door Intune worden verzonden naar Google.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a5c3bec4-18ed-11e8-accf-0ed5f89f718b
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63f1b07d13daad7512dff8e53f9acbafa7bffdd3
ms.sourcegitcommit: e30fb2375fb79f67e5c1e4ed7b2c21fb9ca80c59
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/17/2018
---
# <a name="data-intune-sends-to-google"></a>Gegevens die Intune naar Google verzendt

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Android-apparaatbeheer is ingeschakeld op een apparaat, maakt Microsoft Intune verbinding met Google en worden er gebruikers- en apparaatgegevens gedeeld met Google. Voordat Microsoft Intune verbinding kan maken, moet u een Google-account maken.

De volgende tabel bevat de gegevens die Microsoft Intune naar Google verzendt wanneer apparaatbeheer op een apparaat wordt ingeschakeld:


| Gegevens die worden verzonden naar Google | Details | Gebruikt voor | Voorbeeld |
|:---:|:---:|:---:|:---:|
| EnterpriseId | Afkomstig van Google bij het koppelen van uw Gmail-account aan Intune. | Primaire id, gebruikt om communicatie mogelijk te maken tussen Intune en Google.  Deze communicatie gaat over het instellen van beleid, het beheer van apparaten en het koppelen van Android-apparaten aan Intune (of het opheffen van de koppeling). | Unieke id. Voorbeeldnotatie: LC04eik8a6 |
| Hoofdtekst beleid | Afkomstig uit Intune; ontstaan bij het opslaan van een nieuwe app of een nieuw configuratiebeleid. | Beleidsregels toepassen op apparaten. | Dit is een verzameling van alle geconfigureerde instellingen voor een toepassing of configuratiebeleid. Dit kan klantinformatie bevatten als dit wordt geleverd als onderdeel van een beleid, zoals netwerknamen, toepassingsnamen en app-specifieke instellingen. |
| Apparaatgegevens | Bij apparaten in een werkprofielscenario moeten die apparaten eerst worden ingeschreven bij Intune. Bij apparaten in een beheerde-apparatenscenario moeten die apparaten eerst worden ingeschreven bij Google. | Er worden tussen Intune en Google apparaatgegevens gedeeld voor verschillende acties, zoals het toepassen van beleid, het beheren van het apparaat en algemene rapportage. | **De unieke id die de apparaatnaam vertegenwoordigt.** Voorbeeld: enterprises/LC04ebru7b/devices/3592d971168f9ae4<br>**De unieke id die de gebruikersnaam vertegenwoordigt.** Voorbeeld: Enterprises/LC04ebru7b/users/116838519924207449711<br>**Apparaatstatus.** Voorbeelden: Actief, Uitgeschakeld, Wordt ingericht.<br>**Nalevingsstatussen.** Voorbeelden: Instelling wordt niet ondersteund, Vereiste apps ontbreken<br>**Software-informatie.** Voorbeelden: softwareversies en patchniveau.<br>**Netwerkinformatie.** Voorbeelden: IMEI, MEID, WifiMacAddress<br>**Apparaatinstellingen.** Voorbeelden: informatie over de versleutelingsniveaus en of op apparaten onbekende apps zijn toegestaan.<br> Hieronder vindt u een voorbeeld van een JSON-bericht. |
| newPassword | Afkomstig uit Intune. | De wachtwoordcode van het apparaat wordt opnieuw ingesteld. | De tekenreeks die het nieuwe wachtwoord vertegenwoordigt. |
| Google-gebruiker | Google | Het werkprofiel beheren in werkprofielscenario's (BYOD). | De unieke id die het gekoppelde Gmail-account vertegenwoordigt. Voorbeeld: 114223373813435875042 |
| Toepassingsgegevens | Afkomstig uit Intune, bij het opslaan van toepassingsbeleid. |  | Tekenreeks voor naam van toepassing. Voorbeeld: app:com.microsoft.windowsintune.companyportal |
| Zakelijk serviceaccount | Afkomstig van Google, op verzoek van Intune. | Wordt gebruikt voor verificatie tussen Intune en Google, speciaal voor transacties waar deze klant bij is betrokken. | Er zijn verschillende onderdelen:<br> **Ondernemings-id**: eerder beschreven.<br>**UPN**: gegenereerde UPN, gebruikt voor verificatie namens de klant.<br>Voorbeeld: w49d77900526190e26708c31c9e8a0@pfwp-commicrosoftonedfmdm2.google.com.iam.gserviceaccount.com<br>**Sleutel**: op basis van Base64 versleutelde blob, gebruikt in verificatieaanvragen en versleuteld opgeslagen in de service. De blob ziet er als volgt uit:<br> De unieke id die de sleutel van de klant vertegenwoordigt<br>Voorbeeld: a70d4d53eefbd781ce7ad6a6495c65eb15e74f1f |

**Voorbeeld van apparaatgegevens**

Een voorbeeld van een JSON-apparaatbericht van Google:



```
'{
  "name": "enterprises/LC02dhxx1r/devices/3195483be017acdc",
  "userId": "114223373813435875042",
  "adminType": "DEVICE_OWNER",
  "state": "ACTIVE",
  "appliedState": "ACTIVE",
  "policyCompliant": true,
  "enrollmentTime": "2017-10-06T15:17:41.702Z",
  "lastStatusReportTime": "2017-10-06T15:18:10.325Z",
  "lastPolicyComplianceReportTime": "2017-10-06T15:18:11.665Z",
  "lastPolicySyncTime": "2017-10-06T15:18:07.852Z",
  "appliedPolicyVersion": "2",
  "apiLevel": 26,
  "enrollmentTokenData": "brew 30 day token",
  "enrollmentTokenId": "yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs",
  "softwareInfo": {
    "androidVersion": "8.0.0",
    "cloudDpcVersionCode": 55314,
    "cloudDpcVersionName": "bv00553-rc14",
    "androidBuildNumber": "OPR4.170623.009",
    "deviceKernelVersion": "3.10.73-ga51b1600b7f8",
    "bootloaderVersion": "BHZ21c",
    "androidBuildTime": "2017-08-28T18:57:48Z",
    "securityPatchLevel": "2017-10-05",
    "androidBuildType": "user",
    "buildUser": "android-build"
  },
  "hardwareInfo": {
    "brand": "google",
    "hardware": "bullhead",
    "deviceBasebandVersion": "M8994F-2.6.39.3.03",
    "manufacturer": "LGE",
    "serialNumber": "01ed07873b3c20cd",
    "model": "Nexus 5X",
    "batteryShutdownTemperatures": [60.0],
    "batteryThrottlingTemperatures": [-3.4028235E38],
    "cpuShutdownTemperatures": [115.0, 115.0, 115.0, 115.0, 115.0, 115.0],
    "cpuThrottlingTemperatures": [60.0, 60.0, 60.0, 60.0, 60.0, 60.0],
    "gpuShutdownTemperatures": [-3.4028235E38],
    "gpuThrottlingTemperatures": [-3.4028235E38],
    "skinShutdownTemperatures": [-3.4028235E38],
    "skinThrottlingTemperatures": [37.0]
  },
  "displays": [{
    "name": "Built-in Screen",
    "refreshRate": 60,
    "state": "ON",
    "width": 1080,
    "height": 1920,
    "density": 420
  }],
  "appliedPolicyName": "enterprises/LC02dhxx1r/policies/default",
  "networkInfo": {
    "imei": "353626070676775",
    "wifiMacAddress": "02:00:00:00:00:00"
  },
  "memoryInfo": {
    "totalRam": "1902936064",
    "totalInternalStorage": "3169611776"
  },
  "memoryEvents": [{
    "eventType": "EXTERNAL_STORAGE_DETECTED",
    "createTime": "2017-10-06T15:18:09.959Z",
    "byteCount": "26720919552"
  }],
  "powerManagementEvents": [{
    "eventType": "BATTERY_LEVEL_COLLECTED",
    "createTime": "2017-10-06T15:18:09.939Z",
    "batteryLevel": 95.0
  }],
  "userName": "enterprises/LC02dhxx1r/users/114223373813435875042",
  "enrollmentTokenName": "enterprises/LC02dhxx1r/enrollmentTokens/yXdtW0_0L7c7Yo9DtRhEfPi3PcMqTorF3V1bTAw_eRs"
}'
```

Als u Android-apparaten niet meer wilt beheren met Microsoft Intune en u de gegevens wilt verwijderen, moet u zowel het Android-apparaatbeheer via Microsoft Intune uitschakelen als uw Google-account verwijderen. In uw Google-account vindt u meer informatie over accountbeheer.


