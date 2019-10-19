---
title: Mobile App Management (MAM)
titleSuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Mobile App Management van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: eb1833a6a54fe0a7f78958e653468921df952b4d
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505696"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Naslag voor MAM-entiteiten (Mobile Application Management)

De categorie **Mobile App Management** bevat entiteiten voor mobiele apps, zoals:

- Apps
- exemplaren
- Incheckstatus
- Algemene status
- Beleidsstatus
- Status van inschrijving
- Platformtypen

## <a name="mamapplications"></a>mamApplications

De entiteit **mamApplication** bevat een lijst met LOB-apps (Line-of-Business) die via Mobile Application Management (MAM) worden beheerd, maar die niet zijn ingeschreven in uw bedrijf.

| Eigenschap | Beschrijving | Voorbeeld |
|---------|------------|--------|
| mamApplicationKey |De unieke id van de MAM-toepassing. | 432 |
| mamApplicationName |De naam van de MAM-toepassing. |Voorbeeldnaam voor de MAM-toepassing |
| mamApplicationId |De toepassings-id van de MAM-toepassing. | 123 |
| isDeleted |Geeft aan of deze MAM-app-record is bijgewerkt. <br>Waar: de MAM-app heeft een nieuwe record met bijgewerkte velden in deze tabel. <br>Onwaar: de meest recente record voor deze MAM-app. |Waar/onwaar |
| startDateInclusiveUTC |De datum en tijd in UTC waarop deze MAM-app is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| deletedDateUTC |De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar. |11/23/2016 12:00:00 AM |
| rowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze MAM-app het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |


## <a name="mamapplicationinstances"></a>mamApplicationInstances

De entiteit **mamApplicationInstance** bevat een lijst met beheerde MAM-apps (Mobile Application Management) als zelfstandige exemplaren per gebruiker per apparaat. Alle gebruikers en apparaten die worden vermeld in de entiteit zijn beveiligd, wat inhoudt dat er ten minste één MAM-beleid aan de gebruiker of het apparaat is toegewezen.


|          Eigenschap          |                                                                                                  Beschrijving                                                                                                  |               Voorbeeld                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   applicationInstanceKey   |                                                               De unieke id van het MAM-app-exemplaar in het datawarehouse (surrogaatsleutel).                                                                |                 123                  |
|           userId           |                                                                              De gebruikers-id van de gebruiker die deze MAM-app heeft geïnstalleerd.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   applicationInstanceId    |                                              De unieke id van het MAM-app-exemplaar, vergelijkbaar met ApplicationInstanceKey, maar de id is een natuurlijke sleutel.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | De toepassings-id van de MAM-toepassing waarvoor dit MAM-toepassingsexemplaar is gemaakt.   | 11/23/2016 12:00:00 AM   |
|     applicationVersion     |                                                                                     De toepassingsversie van deze MAM-app.                                                                                      |                  2                   |
|        createdDate         |                                                                 De datum waarop deze record van het MAM-app-exemplaar is gemaakt. De waarde kan null zijn.                                                                 |        11/23/2016 12:00:00 AM        |
|          platform          |                                                                          Het platform van het apparaat waarop deze MAM-app is geïnstalleerd.                                                                           |                  2                   |
|      platformVersion       |                                                                      De versie van het platform van het apparaat waarop deze MAM-app is geïnstalleerd.                                                                       |                 2.2                  |
|         sdkVersion         |                                                                            De MAM SDK-versie waarmee deze MAM-app is ingepakt.                                                                            |                 3.2                  |
| mamDeviceId | De apparaat-id van het apparaat waaraan het MAM-toepassingsexemplaar is gekoppeld.   | 11/23/2016 12:00:00 AM   |
| mamDeviceType | Het apparaattype van het apparaat waaraan het MAM-toepassingsexemplaar is gekoppeld.   | 11/23/2016 12:00:00 AM   |
| mamDeviceName | De apparaatnaam van het apparaat waaraan het MAM-toepassingsexemplaar is gekoppeld.   | 11/23/2016 12:00:00 AM   |
|         isDeleted          | Geeft aan of de record van dit MAM-app-exemplaar is bijgewerkt. <br>True: het MAM-app-exemplaar heeft een nieuwe record met bijgewerkte velden in deze tabel. <br>Onwaar: de meest recente record voor dit MAM-app-exemplaar. |              Waar/onwaar              |
|   startDateInclusiveUtc    |                                                              De datum en tijd in UTC waarop dit MAM-app-exemplaar is gemaakt in het datawarehouse.                                                               |        11/23/2016 12:00:00 AM        |
|       deletedDateUtc       |                                                                             De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar.                                                                              |        11/23/2016 12:00:00 AM        |
| rowLastModifiedDateTimeUtc |                                                           De datum en tijd in UTC waarop dit MAM-app-exemplaar het laatst is gewijzigd in het datawarehouse.                                                            |        11/23/2016 12:00:00 AM        |


## <a name="mamcheckins"></a>mamCheckins

De entiteit **mamCheckin** vertegenwoordigt gegevens die worden verzameld wanneer een MAM-app-exemplaar (Mobile Application Management) heeft ingecheckt bij de Intune-service. 

> [!Note]  
> Wanneer een app-exemplaar meerdere keren per dag wordt ingecheckt, wordt dit slechts eenmaal geregistreerd in het datawarehouse.

| Eigenschap | Beschrijving | Voorbeeld |
|---------|------------|--------|
| dateKey |De datum waarop het inchecken van de MAM-app is vastgelegd in het datawarehouse. | 20160703 |
| applicationInstanceKey |De sleutel van het app-exemplaar dat is gekoppeld aan het inchecken van deze MAM-app. | 123 |
| userKey |De sleutel van de gebruiker die is gekoppeld aan het inchecken van deze MAM-app. | 4323 |
| mamApplicationKey |De toepassingssleutel van de toepassing waaraan de MAM-toepassingcheck-in is gekoppeld. | 432 |
| deviceHealthKey |De sleutel van de apparaatstatus die is gekoppeld aan het inchecken van deze MAM-app. | 321 |
| platformKey |Het platform van het apparaat dat is gekoppeld aan het inchecken van deze MAM-app. |123 |
| effectiveAppliedPolicyKey |Het effectief toegepaste beleid dat is gekoppeld aan de MAM-app die is ingecheckt. Een effectief toegepast beleid is het resultaat van het samenvoegen van alle beleidsregels die relevant zijn voor een bepaalde app en gebruiker. | 322 |
| pastCheckInDate |De datum en tijd waarop deze MAM-app het laatst is ingecheckt. De waarde kan null zijn. |11/23/2016 12:00:00 AM |


## <a name="mamdevicehealth"></a>mamDeviceHealth

De entiteit **mamDeviceHealth** vertegenwoordigt apparaten waarop MAM-beleid (Mobile Application Management) is geïmplementeerd, zelfs als ze opengebroken zijn.

| Eigenschap | Beschrijving | Voorbeeld |
|---------|------------|--------|
| deviceHealthKey |De unieke id van het apparaat en de bijbehorende status in het datawarehouse (surrogaatsleutel). |123 |
| deviceHealth |De unieke id van het apparaat en de bijbehorende status, vergelijkbaar met DeviceHealthKey, maar de id is een natuurlijke sleutel. |b66bc706-ffff-7777-0340-032819502773 |
| deviceHealthName |De status van het apparaat. <br>Niet beschikbaar: er is geen informatie over dit apparaat. <br>Goed: apparaat is niet opengebroken. <br>Slecht: apparaat is opengebroken. |Niet beschikbaar Goed Slecht |
| rowLastModifiedDateTimeUtc |De datum en tijd in UTC waarop deze specifieke MAM-apparaatstatus het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="mameffectivepolicies"></a>mamEffectivePolicies

De entiteit **mamEffectivePolicy** bevat een lijst van alle effectieve MAM-beleidsregels (Mobile Application Management) die zijn toegepast in uw organisatie. Een effectief toegepast beleid is het resultaat van het samenvoegen van alle beleidsregels die relevant zijn voor een bepaalde app en gebruiker.

| Eigenschap | Beschrijving | Voorbeeld |
|---------|------------|--------|
| effectivePolicyKey |De unieke id van het effectieve MAM-beleid in het datawarehouse. |2 |
| realPolicyKey |De unieke id van het MAM-beleid dat is opgesteld door de IT-professional. |1 |
| rowCreatedDateTimeUtc |De datum en tijd in UTC waarop dit effectieve MAM-beleid is gemaakt in het datawarehouse |11/23/2016 12:00:00 AM |

## <a name="mamplatforms"></a>mamPlatforms

De entiteit **mamPlatform** bevat de platformnamen en -typen waarop een MAM-app (Mobile Application Management) is geïnstalleerd.


|          Eigenschap          |                                    Beschrijving                                    |                         Voorbeeld                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        platformKey         |     De unieke id van het platform in het datawarehouse (surrogaatsleutel).      |                           123                           |
|          platform          | De unieke id van de platform, vergelijkbaar met PlatformKey, maar het is een natuurlijke sleutel. |                           123                           |
|        platformName        |                                   De naam van het platform                                   | Niet beschikbaar <br>Geen <br>Windows <br>iOS <br>Android. |
| rowLastModifiedDateTimeUtc | De datum en tijd in UTC waarop dit platform het laatst is gewijzigd in het datawarehouse.  |                 11/23/2016 12:00:00 AM                  |

