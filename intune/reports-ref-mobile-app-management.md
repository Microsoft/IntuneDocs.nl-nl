---
title: Mobile App Management (MAM) | Microsoft Docs
description: Naslagonderwerp voor de categorie Mobile App Management van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4951ec43b2abdb52af091b2d1366bd23a9c2ab5b
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/04/2018
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Naslag voor MAM-entiteiten (Mobile Application Management)

De categorie **Mobile App Management** bevat entiteiten voor mobiele apps, zoals:

  -  Apps
  -  exemplaren
  -  Incheckstatus
  -  Algemene status
  -  Beleidsstatus
  -  Status van inschrijving
  -  Platformtypen

## <a name="mamapplication"></a>MamApplication

De entiteit **MamApplication** bevat een lijst met LOB-apps (Line-of-Business) die via Mobile Application Management (MAM) worden beheerd, maar die niet zijn ingeschreven in uw bedrijf.

| Eigenschap | Description | Voorbeeld |
|---------|------------|--------|
| ApplicationKey |De unieke id van de MAM-app in het datawarehouse. |123 |
| ApplicationName |De naam van de MAM-app. |"Word" |
| ApplicationID |De toepassings-ID van de MAM-app. |b66bc706-ffff-7437-0340-032819502773 |
| IsDeleted |Geeft aan of deze MAM-app-record is bijgewerkt. <br>Waar: de MAM-app heeft een nieuwe record met bijgewerkte velden in deze tabel. <br>Onwaar: de meest recente record voor deze MAM-app. |Waar/onwaar |
| StartDateInclusiveUTC |De datum en tijd in UTC waarop deze MAM-app is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| DeletedDateUTC |De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze MAM-app het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="mamapplicationinstance"></a>MamApplicationInstance

De entiteit **MamApplicationInstance** bevat een lijst met beheerde MAM-apps (Mobile Application Management) als zelfstandige exemplaren per gebruiker per apparaat. Alle gebruikers en apparaten die worden vermeld in de entiteit zijn beveiligd, wat inhoudt dat er ten minste één MAM-beleid aan de gebruiker of het apparaat is toegewezen.

| Eigenschap | Description | Voorbeeld |
|---------|------------|--------|
| ApplicationInstanceKey |De unieke id van het MAM-app-exemplaar in het datawarehouse (surrogaatsleutel). |123 |
| UserId |De gebruikers-id van de gebruiker die deze MAM-app heeft geïnstalleerd. |b66bc706-ffff-7437-0340-032819502773 |
| ApplicationInstanceId |De unieke id van het MAM-app-exemplaar, vergelijkbaar met ApplicationInstanceKey, maar de id is een natuurlijke sleutel. |b66bc706-ffff-7437-0340-032819502773 |
| ApplicationID |De toepassings-ID van deze MAM-app |com.microsoft.groupies-daily.<IOS> |
| ApplicationVersion |De toepassingsversie van deze MAM-app. |2 |
| CreatedDate |De datum waarop deze record van het MAM-app-exemplaar is gemaakt. De waarde kan null zijn. |11/23/2016 12:00:00 AM |
| Platform |Het platform van het apparaat waarop deze MAM-app is geïnstalleerd. |2 |
| PlatformVersion |De versie van het platform van het apparaat waarop deze MAM-app is geïnstalleerd. |2.2 |
| SdkVersion |De MAM SDK-versie waarmee deze MAM-app is ingepakt. |3.2 |
| DeviceId |De apparaat-id van het apparaat waarop deze MAM-app is geïnstalleerd. |b66bc706-ffff-7437-0340-032819502773 |
| DeviceName |De apparaatnaam van het apparaat waarop deze MAM-app is geïnstalleerd. |"MijnApparaat" |
| IsDeleted |Geeft aan of de record van dit MAM-app-exemplaar is bijgewerkt. <br>True: het MAM-app-exemplaar heeft een nieuwe record met bijgewerkte velden in deze tabel. <br>Onwaar: de meest recente record voor dit MAM-app-exemplaar. |Waar/onwaar |
| StartDateInclusiveUTC |De datum en tijd in UTC waarop dit MAM-app-exemplaar is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| DeletedDateUTC |De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop dit MAM-app-exemplaar het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="mamcheckin"></a>MamCheckin

De entiteit **MamCheckin** vertegenwoordigt gegevens die worden verzameld wanneer een MAM-app-exemplaar (Mobile Application Management) heeft ingecheckt bij de Intune-service. 

> [!Note]  
> Wanneer een app-exemplaar meerdere keren per dag wordt ingecheckt, wordt dit slechts eenmaal geregistreerd in het datawarehouse.

| Eigenschap | Description | Voorbeeld |
|---------|------------|--------|
| DateKey |De datum waarop het inchecken van de MAM-app is vastgelegd in het datawarehouse. | 20160703 |
| ApplicationInstanceKey |De sleutel van het app-exemplaar dat is gekoppeld aan het inchecken van deze MAM-app. |5/2/1900 12:00:00 AM |
| UserKey |De sleutel van de gebruiker die is gekoppeld aan het inchecken van deze MAM-app. |1/12/1900 12:00:00 AM |
| ApplicationKey |De sleutel van de MAM-app die is ingecheckt. |1/10/1900 12:00:00 AM |
| DeviceHealthKey |De sleutel van de apparaatstatus die is gekoppeld aan het inchecken van deze MAM-app. |1/2/1900 12:00:00 AM |
| PlatformKey |Het platform van het apparaat dat is gekoppeld aan het inchecken van deze MAM-app. |1/1/1900 12:00:00 AM |
| EffectiveAppliedPolicyKey |Het effectief toegepaste beleid dat is gekoppeld aan de MAM-app die is ingecheckt. Een effectief toegepast beleid is het resultaat van het samenvoegen van alle beleidsregels die relevant zijn voor een bepaalde app en gebruiker. |5/2/1900 12:00:00 AM |
| LastCheckInDate |De datum en tijd waarop deze MAM-app het laatst is ingecheckt. De waarde kan null zijn. |11/23/2016 12:00:00 AM |

## <a name="mamdevicehealth"></a>MamDeviceHealth

De entiteit **MamDeviceHealth** vertegenwoordigt apparaten waarop MAM-beleid (Mobile Application Management) is geïmplementeerd, zelfs als ze opengebroken zijn.

| Eigenschap | Description | Voorbeeld |
|---------|------------|--------|
| DeviceHealthKey |De unieke id van het apparaat en de bijbehorende status in het datawarehouse (surrogaatsleutel). |1/1/1900 12:00:00 AM |
| DeviceHealth |De unieke id van het apparaat en de bijbehorende status, vergelijkbaar met DeviceHealthKey, maar de id is een natuurlijke sleutel. |1/1/1900 12:00:00 AM |
| DeviceHealthName |De status van het apparaat. <br>Niet beschikbaar: er is geen informatie over dit apparaat. <br>Goed: apparaat is niet opengebroken. <br>Slecht: apparaat is opengebroken. |Niet beschikbaar Goed Slecht |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze specifieke MAM-apparaatstatus het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="mameffectivepolicy"></a>MamEffectivePolicy

De entiteit **MamEffectivePolicy** bevat een lijst van alle effectieve MAM-beleidsregels (Mobile Application Management) die zijn toegepast in uw organisatie. Een effectief toegepast beleid is het resultaat van het samenvoegen van alle beleidsregels die relevant zijn voor een bepaalde app en gebruiker.

| Eigenschap | Description | Voorbeeld |
|---------|------------|--------|
| EffectivePolicyKey |De unieke id van het effectieve MAM-beleid in het datawarehouse. |2 |
| RealPolicyKey |De unieke id van het MAM-beleid dat is opgesteld door de IT-professional. |1 |
| RowCreatedDateTimeUtc |De datum en tijd in UTC waarop dit effectieve MAM-beleid is gemaakt in het datawarehouse |11/23/2016 12:00:00 AM |

## <a name="mamglobalapplication"></a>MamGlobalApplication

De entiteit **MamGlobalApplication** bevat een lijst met Store-apps die via Mobile Application Management (MAM) worden beheerd, maar die niet zijn ingeschreven in uw bedrijf.

| Eigenschap | Description | Voorbeeld |
|---------|------------|--------|
| ApplicationKey |De unieke id van de Store-app in het datawarehouse, ook wel de surrogaatsleutel genoemd |123 |
| ApplicationID |De unieke id van de Store-app. De id is vergelijkbaar met ApplicationKey, maar het is een natuurlijke sleutel. |com.microsoft.skydrive.<ios> |
| ApplicationName |De algemene naam van de MAM-toepassing |Skydrive |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze algemene MAM-toepassing het laatst is gewijzigd in het datawarehouse |11/23/2016 12:00:00 AM |

## <a name="mamplatform"></a>MamPlatform

De entiteit **MamPlatform** bevat de platformnamen en -typen waarop een MAM-app (Mobile Application Management) is geïnstalleerd.

| Eigenschap | Description | Voorbeeld |
|---------|------------|--------|
| PlatformKey |De unieke id van het platform in het datawarehouse (surrogaatsleutel). |123 |
| Platform |De unieke id van de platform, vergelijkbaar met PlatformKey, maar het is een natuurlijke sleutel. |123 |
| PlatformName |De naam van het platform |Niet beschikbaar <br>Geen <br>Windows <br>iOS <br>Android. |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop dit platform het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |
