---
title: Naslag voor beleidsentiteiten
titleSuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Beleid van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1fe4fabc86e7be647fa161d68fe8a4fe35e9eb6b
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654121"
---
# <a name="reference-for-policy-entities"></a>Naslag voor beleidsentiteiten

De categorie **Beleid** bevat entiteiten voor mobiele apparaten waarmee gegevens worden bijgehouden, zoals:

- Inventarisatie van apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid  
- Aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout per dag  
- Aantal gebruikers met de status Geslaagd, In behandeling, Mislukt of Fout per dag  
- Cumulatief aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout  

## <a name="policies"></a>policies

De entiteit **policy** bevat apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid. U kunt het beleid met MDM (Mobile Device Management) toewijzen aan een groep in uw onderneming.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| policyKey |Een unieke sleutel voor het beleid in het datawarehouse. |123 |
| policyId |Een unieke id van het beleid in het datawarehouse. |b66bc706-ffff-7437-0340-032819502773 |
| policyName |De naam van het beleid. |"Windows 10 Baseline" |
| policyVersion |De versie van het beleid. Wanneer het beleid wordt gewijzigd, wordt er een nieuwere versie gemaakt. |1, 2, 3 |
| isDeleted |Geeft aan of de beleidsrecord is bijgewerkt.  <br>Waar: het beleid heeft een nieuwe record met bijgewerkte velden. <br>Onwaar: de meest recente record voor het beleid. |Waar/onwaar |
| startDateInclusiveUTC |De datum en tijd in UTC waarop het beleid is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| deletedDateUTC |De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar. |11/23/2016 12:00:00 AM |
| rowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop het beleid het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="policytypes"></a>policyTypes

De entiteit **policyType** bevat typen apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid. U kunt het beleid met MDM (Mobile Device Management) toewijzen aan een groep in uw onderneming.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| policyTypeId |Een unieke id van het beleid in het bronsysteem. |123 |
| policyTypeKey |Een unieke id van het beleid in het datawarehouse. |1 |
| policyTypeName |De naam van het beleidstype |Nalevingsbeleid van Windows 10. |

## <a name="device-configuration"></a>Apparaatconfiguratie

De entiteit **deviceConfigurationProfileDeviceActivity** bevat het aantal **apparaten** met de status geslaagd, in behandeling, mislukt of fout per dag. Het aantal weerspiegelt de apparaatconfiguratieprofielen die zijn toegewezen aan de entiteit. Als een **apparaat** bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een apparaat twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de teller Geslaagd met één opgehoogd en wordt het apparaat in de foutstatus geplaatst. De entiteit geeft voor de afgelopen 30 dagen aan hoeveel apparaten op een bepaalde dag een bepaalde status hebben.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| dateKey |De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |20160703 |
| in behandeling |Aantal unieke apparaten met de status In behandeling. |123 |
| geslaagd |Aantal unieke apparaten met de status Geslaagd. |12 |
| fout |Aantal unieke apparaten met de status Fout. |10 |
| mislukt |Aantal unieke apparaten met de status Mislukt. |2 |

De entiteit **deviceConfigurationProfileUserActivity** bevat het aantal **gebruikers** met de status Geslaagd, In behandeling, Mislukt of Fout per dag. Het aantal weerspiegelt de apparaatconfiguratieprofielen die zijn toegewezen aan de entiteit. Als een **gebruiker** bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een gebruiker twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de gebruiker in de foutstatus geplaatst.  De entiteit **deviceConfigurationProfileUserActivity** geeft voor de afgelopen dertig dagen aan hoeveel gebruikers op een bepaalde dag een bepaalde status hebben.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| dateKey |De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |20160703 |
| in behandeling |Aantal unieke gebruikers met de status In behandeling. |123 |
| geslaagd |Aantal unieke gebruikers met de status Geslaagd. |12 |
| fout |Aantal unieke gebruikers met de status Fout. |10 |
| mislukt |Aantal unieke gebruikers met de status Mislukt. |2 |

## <a name="policytypeactivities"></a>policyTypeActivities

De entiteit **policyTypeActivity** bevat het cumulatieve aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout. Deze statuswaarden verwijzen naar een apparaatconfiguratieprofiel, app-configuratieprofiel of nalevingsbeleid per dag.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| dateKey |De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |20160703 |
| policyKey |policyKey, kan worden samengevoegd met policy om de policyName op te halen. |Windows 10 baseline |
| policyTypeKey |Het type beleidssleutel, kan worden samengevoegd met PolicyType om de naam van het beleidstype op te halen. |Windows 10-nalevingsbeleid configureren |
| in behandeling |Aantal unieke apparaten met de status In behandeling. |123 |
| geslaagd |Aantal unieke apparaten met de status Geslaagd. |12 |
| fout |Aantal unieke apparaten met de status Fout. |10 |
| mislukt |Aantal unieke apparaten met de status Mislukt. |2 |

## <a name="compliance-policy"></a>Nalevingsbeleid

De API-naslag voor nalevingsbeleid bevat entiteiten die statusinformatie bieden over nalevingsbeleid dat aan apparaten is toegewezen.

### <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities

De volgende tabel geeft een overzicht van de toewijzingsstatus van nalevingsbeleid voor apparaten. In de tabel wordt het aantal apparaten weergegeven dat is gevonden voor elke nalevingsstatus.


|Eigenschap     |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|dateKey  |De datum waarop de samenvatting voor het nalevingsbeleid is gemaakt.|20161204 |
|unknown  |Het aantal apparaten dat offline is of om een andere redenen niet kan communiceren met Intune of Azure AD. |5|
|notApplicable      |Het aantal apparaten waarvoor het nalevingsbeleid waarop de beheerder zich richt, niet van toepassing is.|201 |
|compliant      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels voor apparaten is toegepast waarop de beheerder zich richt. |4083 |
|inGracePeriod      |Aantal apparaten dat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld. |57|
|nonCompliant      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels niet zijn toegepast waarop de beheerder zich richt of waarvoor de gebruiker niet voldoet aan de beleidsregels waarop de beheerder zich richt.|43 |
|fout      |Het aantal apparaten dat niet kan communiceren met Intune of Azure AD en een foutbericht heeft geretourneerd. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities 

De volgende tabel geeft een overzicht van de toewijzingsstatus van nalevingsbeleid voor apparaten per beleid en per beleidstype. In de tabel wordt het aantal apparaten weergegeven dat is gevonden in elke nalevingsstatus voor elk toegewezen nalevingsbeleid.



|Eigenschap  |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|dateKey  |De datum waarop de samenvatting voor het nalevingsbeleid is gemaakt.|20161219|
|policyKey     |Sleutel voor het nalevingsbeleid waarvoor de samenvatting is gemaakt. |10178 |
|policyPlatformKey      |Sleutel voor het platformtype van het nalevingsbeleid waarvoor de samenvatting is gemaakt.|5|
|unknown     |Het aantal apparaten dat offline is of om een andere redenen niet kan communiceren met Intune of Azure AD.|13|
|notApplicable     |Het aantal apparaten waarvoor het nalevingsbeleid waarop de beheerder zich richt, niet van toepassing is.|3|
|compliant      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels voor apparaten is toegepast waarop de beheerder zich richt. |45|
|inGracePeriod      |Aantal apparaten dat niet compatibel is, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld. |3|
|nonCompliant      |Het aantal apparaten waarop een of meer nalevingsbeleidsregels niet zijn toegepast waarop de beheerder zich richt of waarvoor de gebruiker niet voldoet aan de beleidsregels waarop de beheerder zich richt.|7|
|fout      |Het aantal apparaten dat niet kan communiceren met Intune of Azure AD en een foutbericht heeft geretourneerd. |3|

### <a name="policyplatformtypes"></a>policyPlatformTypes

De volgende tabel bevat de platformtypen van alle toegewezen beleidsregels. De platformtypen van beleidsregels die nooit zijn toegewezen aan apparaten worden niet in deze tabel vermeld.


|Eigenschap  |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|policyPlatformTypeKey      |De unieke sleutel voor het platformtype van het beleid. |20170519 |
|policyPlatformTypeId      |De unieke id voor het platformtype van het beleid.|1|
|policyPlatformTypeName      |De naam van het platformtype van het beleid.|AndroidForWork |

### <a name="policydeviceactivities"></a>policyDeviceActivities

In de volgende tabel wordt het aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout per dag weergegeven. Het aantal weerspiegelt de gegevens per beleidstypeprofiel. Als een apparaat bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een apparaat twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de teller Geslaagd met één opgehoogd en wordt het apparaat in de foutstatus geplaatst. De entiteit policyDeviceActivity geeft voor de afgelopen 30 dagen aan hoeveel apparaten op een bepaalde dag een bepaalde status hebben.

|Eigenschap  |Beschrijving  |Voorbeeld  |
|---------|---------|---------|
|dateKey|De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse.|20160703|
|in behandeling|Aantal unieke apparaten met de status In behandeling.|123|
|Geslaagd|Aantal unieke apparaten met de status Geslaagd.|12|
|policyKey|policyKey, kan worden samengevoegd met policy om de policyName op te halen.|Windows 10 baseline|
|fout|Aantal unieke apparaten met de status Fout.|10|
|mislukt|Aantal unieke apparaten met de status Mislukt.|2|

### <a name="policyuseractivities"></a>policyUserActivities

In de volgende tabel wordt het aantal gebruikers met de status Geslaagd, In behandeling, Mislukt of Fout per dag weergegeven. Het aantal weerspiegelt de gegevens per beleidstypeprofiel. Als een gebruiker bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een gebruiker twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de gebruiker in de foutstatus geplaatst. De entiteit PolicyUserActivity geeft voor de afgelopen 30 dagen aan hoeveel gebruikers op een bepaalde dag een bepaalde status hebben.


| Eigenschap  |                                         Beschrijving                                         |       Voorbeeld       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  dateKey  | De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. |      20160703       |
|  in behandeling  |                         Aantal unieke apparaten met de status In behandeling.                          |         123         |
| geslaagd |                         Aantal unieke apparaten met de status Geslaagd.                          |         12          |
| policyKey |                 policyKey, kan worden samengevoegd met policy om de policyName op te halen.                 | Windows 10 baseline |
|   fout   |                          Aantal unieke apparaten met de status Fout.                           |         10          |

