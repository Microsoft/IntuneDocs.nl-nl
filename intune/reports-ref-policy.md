---
title: Naslag voor beleidsentiteiten
titleSuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Beleid van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4f66cc3a10711b137e081fab98445d73108748a9
ms.sourcegitcommit: 63b55e81122e5c15893302b109ae137c30855b55
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2019
ms.locfileid: "67713161"
---
# <a name="reference-for-policy-entities"></a>Naslag voor beleidsentiteiten

De categorie **Beleid** bevat entiteiten voor mobiele apparaten waarmee gegevens worden bijgehouden, zoals:

  - Inventarisatie van apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid  
  - Aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout per dag  
  - Aantal gebruikers met de status Geslaagd, In behandeling, Mislukt of Fout per dag  
  - Cumulatief aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout  

## <a name="policy"></a>Beleid

De entiteit **Policy** bevat apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid. U kunt het beleid met MDM (Mobile Device Management) toewijzen aan een groep in uw onderneming.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| PolicyKey |Een unieke sleutel voor het beleid in het datawarehouse. |123 |
| PolicyId |Een unieke id van het beleid in het datawarehouse. |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |De naam van het beleid. |"Windows 10 Baseline" |
| PolicyVersion |De versie van het beleid. Wanneer het beleid wordt gewijzigd, wordt er een nieuwere versie gemaakt. |1, 2, 3 |
| IsDeleted |Geeft aan of de beleidsrecord is bijgewerkt.  <br>Waar: het beleid heeft een nieuwe record met bijgewerkte velden. <br>Onwaar: de meest recente record voor het beleid. |Waar/onwaar |
| StartDateInclusiveUTC |De datum en tijd in UTC waarop het beleid is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| DeletedDateUTC |De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop het beleid het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="policytype"></a>PolicyType

De entiteit **PolicyType** bevat typen apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid. U kunt het beleid met MDM (Mobile Device Management) toewijzen aan een groep in uw onderneming.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| PolicyTypeId |Een unieke id van het beleid in het bronsysteem. |123 |
| PolicyTypeKey |Een unieke id van het beleid in het datawarehouse. |1 |
| PolicyTypeName |De naam van het beleidstype |Nalevingsbeleid van Windows 10. |

## <a name="deviceconfiguration"></a>DeviceConfiguration

De entiteit **DeviceConfigurationProfileDeviceActivity** bevat het aantal **apparaten** met de status geslaagd, in behandeling, mislukt of fout per dag. Het aantal weerspiegelt de apparaatconfiguratieprofielen die zijn toegewezen aan de entiteit. Als een **apparaat** bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een apparaat twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de teller Geslaagd met één opgehoogd en wordt het apparaat in de foutstatus geplaatst. De entiteit geeft voor de afgelopen 30 dagen aan hoeveel apparaten op een bepaalde dag een bepaalde status hebben.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| DateKey |De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |20160703 |
| In behandeling |Aantal unieke apparaten met de status In behandeling. |123 |
| Geslaagd |Aantal unieke apparaten met de status Geslaagd. |12 |
| Fout |Aantal unieke apparaten met de status Fout. |10 |
| Mislukt |Aantal unieke apparaten met de status Mislukt. |2 |

De entiteit **DeviceConfigurationProfileUserActivity** bevat het aantal **gebruikers** met de status Geslaagd, In behandeling, Mislukt of Fout per dag. Het aantal weerspiegelt de apparaatconfiguratieprofielen die zijn toegewezen aan de entiteit. Als een **gebruiker** bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een gebruiker twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de gebruiker in de foutstatus geplaatst.  De entiteit **DeviceConfigurationProfileUserActivity** geeft voor de afgelopen dertig dagen aan hoeveel gebruikers op een bepaalde dag een bepaalde status hebben.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| DateKey |De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |20160703 |
| In behandeling |Aantal unieke gebruikers met de status In behandeling. |123 |
| Geslaagd |Aantal unieke gebruikers met de status Geslaagd. |12 |
| Fout |Aantal unieke gebruikers met de status Fout. |10 |
| Mislukt |Aantal unieke gebruikers met de status Mislukt. |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

De entiteit **PolicyTypeActivity** bevat het cumulatieve aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout. Deze statuswaarden verwijzen naar een apparaatconfiguratieprofiel, app-configuratieprofiel of nalevingsbeleid per dag.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| DateKey |De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |20160703 |
| PolicyKey |Beleidssleutel, kan worden samengevoegd met Policy om de naam van het beleid op te halen. |Windows 10 baseline |
| PolicyTypeKey |Het type beleidssleutel, kan worden samengevoegd met PolicyType om de naam van het beleidstype op te halen. |Windows 10-nalevingsbeleid configureren |
| In behandeling |Aantal unieke apparaten met de status In behandeling. |123 |
| Geslaagd |Aantal unieke apparaten met de status Geslaagd. |12 |
| Fout |Aantal unieke apparaten met de status Fout. |10 |
| Mislukt |Aantal unieke apparaten met de status Mislukt. |2 |

## <a name="compliance-policy"></a>Nalevingsbeleid

De API-naslag voor nalevingsbeleid bevat entiteiten die statusinformatie bieden over nalevingsbeleid dat aan apparaten is toegewezen.

### <a name="compliancepolicystatusdeviceactivities"></a>CompliancePolicyStatusDeviceActivities

De volgende tabel geeft een overzicht van de toewijzingsstatus van nalevingsbeleid voor apparaten. In de tabel wordt het aantal apparaten weergegeven dat is gevonden voor elke nalevingsstatus.


|Eigenschap     |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|DateKey  |De datum waarop de samenvatting voor het nalevingsbeleid is gemaakt.|20161204 |
|Onbekend  |Het aantal apparaten dat offline is of om een andere redenen niet kan communiceren met Intune of Azure AD. |5|
|Niet van toepassing      |Het aantal apparaten waarvoor het nalevingsbeleid waarop de beheerder zich richt, niet van toepassing is.|201 |
|Compliant      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels voor apparaten is toegepast waarop de beheerder zich richt. |4083 |
|InGracePeriod      |Aantal apparaten dat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld. |57|
|Niet-compatibel      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels niet zijn toegepast waarop de beheerder zich richt of waarvoor de gebruiker niet voldoet aan de beleidsregels waarop de beheerder zich richt.|43 |
|Fout      |Het aantal apparaten dat niet kan communiceren met Intune of Azure AD en een foutbericht heeft geretourneerd. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>CompliancePolicyStatusDevicePerPolicyActivities 

De volgende tabel geeft een overzicht van de toewijzingsstatus van nalevingsbeleid voor apparaten per beleid en per beleidstype. In de tabel wordt het aantal apparaten weergegeven dat is gevonden in elke nalevingsstatus voor elk toegewezen nalevingsbeleid.



|Eigenschap  |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|DateKey  |De datum waarop de samenvatting voor het nalevingsbeleid is gemaakt.|20161219|
|PolicyKey     |Sleutel voor het nalevingsbeleid waarvoor de samenvatting is gemaakt. |10178 |
|PolicyPlatformKey      |Sleutel voor het platformtype van het nalevingsbeleid waarvoor de samenvatting is gemaakt.|5|
|Onbekend     |Het aantal apparaten dat offline is of om een andere redenen niet kan communiceren met Intune of Azure AD.|13|
|Niet van toepassing     |Het aantal apparaten waarvoor het nalevingsbeleid waarop de beheerder zich richt, niet van toepassing is.|3|
|Compliant      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels voor apparaten is toegepast waarop de beheerder zich richt. |45|
|Respijtperiode      |Aantal apparaten dat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld. |3|
|Niet-compatibel      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels niet zijn toegepast waarop de beheerder zich richt of waarvoor de gebruiker niet voldoet aan de beleidsregels waarop de beheerder zich richt.|7|
|Fout      |Het aantal apparaten dat niet kan communiceren met Intune of Azure AD en een foutbericht heeft geretourneerd. |3|

### <a name="policyplatformtypes"></a>PolicyPlatformTypes

De volgende tabel bevat de platformtypen van alle toegewezen beleidsregels. De platformtypen van beleidsregels die nooit zijn toegewezen aan apparaten worden niet in deze tabel vermeld.


|Eigenschap  |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|PolicyPlatformTypeKey      |De unieke sleutel voor het platformtype van het beleid. |20170519 |
|PolicyPlatformTypeId      |De unieke id voor het platformtype van het beleid.|1|
|PolicyPlatformTypeName      |De naam van het platformtype van het beleid.|AndroidForWork |

### <a name="policydeviceactivity"></a>PolicyDeviceActivity

In de volgende tabel wordt het aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout per dag weergegeven. Het aantal weerspiegelt de gegevens per beleidstypeprofiel. Als een apparaat bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een apparaat twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de teller Geslaagd met één opgehoogd en wordt het apparaat in de foutstatus geplaatst. De entiteit PolicyDeviceActivity geeft voor de afgelopen 30 dagen aan hoeveel apparaten op een bepaalde dag een bepaalde status hebben.

|Eigenschap  |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|DateKey|De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse.|20160703|
|In behandeling|Aantal unieke apparaten met de status In behandeling.|123|
|Geslaagd|Aantal unieke apparaten met de status Geslaagd.|12|
PolicyKey|Beleidssleutel, kan worden samengevoegd met Policy om de naam van het beleid op te halen.|Windows 10 baseline|
|Fout|Aantal unieke apparaten met de status Fout.|10|
|Mislukt|Aantal unieke apparaten met de status Mislukt.|2|

### <a name="policyuseractivity"></a>PolicyUserActivity 

In de volgende tabel wordt het aantal gebruikers met de status Geslaagd, In behandeling, Mislukt of Fout per dag weergegeven. Het aantal weerspiegelt de gegevens per beleidstypeprofiel. Als een gebruiker bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een gebruiker twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de gebruiker in de foutstatus geplaatst. De entiteit PolicyUserActivity geeft voor de afgelopen 30 dagen aan hoeveel gebruikers op een bepaalde dag een bepaalde status hebben.


| Eigenschap  |                                         Beschrijving                                         |       Voorbeeld       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  DateKey  | De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |      20160703       |
|  In behandeling  |                         Aantal unieke apparaten met de status In behandeling.                          |         123         |
| Geslaagd |                         Aantal unieke apparaten met de status Geslaagd.                          |         12          |
| PolicyKey |                Beleidssleutel, kan worden samengevoegd met Policy om de naam van het beleid op te halen.                 | Windows 10 baseline |
|   Fout   |                          Aantal unieke apparaten met de status Fout.                           |         10          |

