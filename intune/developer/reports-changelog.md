---
title: Wijzigingenlogboek Intune-datawarehouse
titleSuffix: Microsoft Intune
description: In dit onderwerp vindt u een overzicht van de wijzigingen voor de Microsoft Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9740eed3ab727d76a9af4e46642d8279b310fd9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490521"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Wijzigingenlogboek voor de API van Intune-datawarehouse

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Houd updates voor Intune-datawarehouse bij.

## <a name="1903-part-2"></a>1903 (deel 2)
_Uitgebracht in april 2019_

### <a name="beta-changes"></a>Bètawijzigingen

De volgende tabel bevat de recentelijk verwijderde verzamelingen en de vervangende verzamelingen in het Intune-datawarehouse.

|    Verzameling                          |    Wijziging     |    Aanvullende informatie                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    mobileAppDeviceUserInstallStatus    |    Verwijderd    |    Gebruik in plaats daarvan [mobileAppInstallStatusCounts](intune-data-warehouse-collections.md#mobileappinstallstatuscounts).                                                                                                                                                                                                                                                                     |
|    enrollmentTypes                     |    Verwijderd    |    Gebruik in plaats daarvan [deviceEnrollmentTypes](intune-data-warehouse-collections.md#deviceenrollmenttypes).                                                                                                                                                                                                                                                                                      |
|    mdmStatuses                         |    Verwijderd    |    Gebruik in plaats daarvan [complianceStates](intune-data-warehouse-collections.md#compliancestates).                                                                                                                                                                                                                                                                                               |
|    WorkPlaceJoinStateTypes             |    Verwijderd    |    Gebruik in plaats daarvan de eigenschap `azureAdRegistered` in de verzamelingen [devices](intune-data-warehouse-collections.md#devices) en [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories).                                                                                                                                                                                                             |
|    clientRegistrationStateTypes        |    Verwijderd    |    Gebruik in plaats daarvan [deviceRegistrationStates](intune-data-warehouse-collections.md#deviceregistrationstates).                                                                                                                                                                                                                                                                             |
|    currentUser                         |    Verwijderd    |    Gebruik in plaats daarvan de verzameling [users](intune-data-warehouse-collections.md#users).                                                                                                                                                                                                                                                                                                      |
|    mdmDeviceInventoryHistories         |    Verwijderd    |    Veel van de eigenschappen waren redundant of zijn nu te vinden in de verzamelingen [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) of [devices](intune-data-warehouse-collections.md#devices). Alle **mdmDeviceInventoryHistories**-eigenschappen die niet worden vermeld bij deze twee verzamelingen zijn niet meer beschikbaar. Zie hieronder voor meer informatie.    |

De volgende tabel bevat de oude eigenschappen die voorheen te vinden waren in de verzameling **mdmDeviceInventoryHistories** en de wijziging/vervanging. Alle eigenschappen die aanwezig waren in **mdmDeviceInventoryHistories**, maar niet hieronder worden vermeld, zijn verwijderd.

|    Oude eigenschap                |    Wijziging/vervanging                                                           |
|--------------------------------|---------------------------------------------------------------------------------|
|    cellularTechnology          |    cellularTechnology in de verzameling devices                                     |
|    deviceClientId              |    deviceid in de verzameling devices                                               |
|    deviceManufacturer          |    manufacturer in de verzameling devices                                           |
|    deviceModel                 |    model in de verzameling devices                                                  |
|    deviceName                  |    deviceName in de verzameling devices                                             |
|    deviceOsPlatform            |    deviceTypeKey in de verzameling devices                                          |
|    deviceOsVersion             |    osVersion in de verzameling devicePropertyHistories                              |
|    deviceType                  |    deviceTypeKey in de verzameling devices, verwijzend naar de verzameling deviceTypes    |
|    encryptionState             |    De eigenschap encryptionState in de verzameling devices                           |
|    exchangeActiveSyncId        |    De eigenschap easDeviceId in de verzameling devices                               |
|    exchangeDeviceId            |    easDeviceId in de verzameling devices                                            |
|    imei                        |    imei in de verzameling devices                                                   |
|    isSupervised                |    De eigenschap isSupervised in de verzameling devices                              |
|    jailBroken                  |    jailBroken in de verzameling devicePropertyHistories                             |
|    meid                        |    De eigenschap meid in de verzameling devices                                      |
|    oem                         |    manufacturer in de verzameling devices                                           |
|    osName                      |    deviceTypeKey in de verzameling devices, verwijzend naar de verzameling deviceTypes    |
|    phoneNumber                 |    phoneNumber in de verzameling devices                                            |
|    platformType                |    model in de verzameling devices                                                  |
|    product                     |    deviceTypeKey in de verzameling devices                                          |
|    productVersion              |    osVersion in de verzameling devicePropertyHistories                              |
|    serialNumber                |    serialNumber in de verzameling devices                                           |
|    storageFree                 |    De eigenschap freeStorageSpaceInBytes in de verzameling devices                   |
|    storageTotal                |    De eigenschap totalStorageSpaceInBytes in de verzameling devices                |
|    subscriberCarrierNetwork    |    De eigenschap subscriberCarrier in de verzameling devices                         |
|    wifimac                     |    wiFiMacAddress in de verzameling devices                                         |

De volgende tabel bevat wijzigingen in de eigenschappen in de verzameling [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories): 

|    Oude eigenschap                  |    Wijziging/vervanging                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, verwijzend naar de verzameling deviceCategories       |
|    certExpirationDate            |    Verwijderd                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime in de verzameling devices                           |
|    deviceTypeKey                 |    deviceTypeKey in de verzameling devices                              |
|    easID                         |    easDeviceId in de verzameling devices                                |
|    enrolledByUser                |    userId in de verzameling devices                                     |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey in de verzameling devices                    |
|    graphDeviceIsCompliant        |    Verwijderd                                                          |
|    graphDeviceIsManaged          |    Verwijderd                                                          |
|    lastContact                   |    lastSyncDateTime in de verzameling devices                           |
|    lastContactNotification       |    Verwijderd                                                          |
|    lastContactWorkplaceJoin      |    Verwijderd                                                          |
|    lastExchangeStatusUtc         |    Verwijderd                                                          |
|    lastModifiedDateTimeUTC       |    Verwijderd                                                          |
|    lastPolicyUpdateUtc           |    Verwijderd                                                          |
|    managementAgentKey            |    managementStateKey                                               |
|    manufacturer                  |    manufacturer in de verzameling devices                               |
|    mdmStatusKey                  |    complianceStateKey, verwijzend naar de verzameling complianceStates    |
|    model                         |    model in de verzameling devices                                      |
|    osFamily                      |    operatingSystem in de verzameling devices                            |
|    osRevisionNumber              |    osVersion in de verzameling devices                                  |
|    processorArchitecture         |    Verwijderd                                                          |
|    referenceId                   |    azureAdDeviceId in de verzameling devices                            |
|    serialNumber                  |    serialNumber in de verzameling devices                               |
|    workPlaceJoinStateKey         |    azureAdRegistered                                                |

De volgende tabel bevat wijzigingen in de eigenschappen in de verzameling [devices](intune-data-warehouse-collections.md#devices): 

|    Oude eigenschap                  |    Wijziging/vervanging                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, verwijzend naar de verzameling deviceCategories       |
|    certExpirationDate            |    Verwijderd                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime                                                 |
|    easId                         |    easDeviceId                                                      |
|    enrolledByUser                |    userId                                                           |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey                                          |
|    graphDeviceIsCompliant        |    Verwijderd                                                          |
|    graphDeviceIsManaged          |    Verwijderd                                                          |
|    lastContact                   |    lastSyncDateTime                                                 |
|    lastContactNotification       |    Verwijderd                                                          |
|    lastContactWorkplaceJoin      |    Verwijderd                                                          |
|    lastExchangeStatusUtc         |    Verwijderd                                                          |
|    lastPolicyUpdateUtc           |    Verwijderd                                                          |
|    mdmStatusKey                  |    complianceStateKey, verwijzend naar de verzameling complianceStates    |
|    osFamily                      |    operatingSystem                                                  |
|    processorArchitecture         |    Verwijderd                                                          |
|    referenceId                   |    azureAdDeviceId                                                  |
|    workPlaceJoinStateKey         |    azureAdRegistered                                                |

De volgende tabel bevat wijzigingen in de eigenschappen in de verzameling [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities): 

|    Oude eigenschap         |    Wijziging/vervanging         |
|-------------------------|-------------------------------|
|    enrollmentTypeKey    |    deviceEnrollmentTypeKey    |

De volgende tabel bevat wijzigingen in de eigenschappen in de verzameling [mamApplications](intune-data-warehouse-collections.md#mamapplications): 

|    Oude eigenschap       |    Wijziging/vervanging    |
|-----------------------|--------------------------|
|    applicationKey     |    mamApplicationKey     |
|    applicationName    |    mamApplicationName    |
|    applicationId      |    mamApplicationId      |

De volgende tabel bevat wijzigingen in de eigenschappen in de verzameling [mamApplicationsInstances](intune-data-warehouse-collections.md#mamapplicationinstances): 

|    Oude eigenschap     |    Wijziging/vervanging    |
|---------------------|--------------------------|
|    applicationId    |    mamApplicationId      |
|    deviceId         |    mamDeviceId           |
|    deviceType       |    mamDeviceType         |
|    deviceName       |    mamDeviceName         |

De volgende tabel bevat wijzigingen in de eigenschappen in de verzameling [mamCheckins](intune-data-warehouse-collections.md#mamcheckins): 

|    Oude eigenschap      |    Wijziging/vervanging    |
|----------------------|--------------------------|
|    applicationKey    |    mamApplicationKey     |

De volgende tabel bevat wijzigingen in de eigenschappen in de verzameling [users](intune-data-warehouse-collections.md#users): 

|    Oude eigenschap             |    Wijziging/vervanging    |
|-----------------------------|--------------------------|
|    startDateInclusiveUtc    |    Verwijderd               |
|    endDateInclusiveUtc      |    Verwijderd               |
|    IsCurrent                |    Verwijderd               |

## <a name="1903"></a>1903
_Uitgebracht in maart 2019_

### <a name="v10-changes-reflecting-back-to-beta"></a>Wijzigingen in V1.0 worden doorgevoerd in de bètaversie
Toen V1.0 voor het eerst werd uitgebracht in 1808, verschilde deze op belangrijke punten van de bètaversie-API. In 1903 zullen deze wijzigingen in de bètaversie-API worden doorgevoerd. Als u belangrijke rapporten hebt die gebruikmaken van de bètaversie-API, wordt u ten zeerste aangeraden deze rapporten over te zetten naar V1.0 om wijzigingen te voorkomen die fouten veroorzaken. Raadpleeg [API-versiegegevens](../reports-api-url.md) voor meer informatie over de datawarehouse-API-versies en achterwaartse compatibiliteit. 

## <a name="1902"></a>1902 
_Uitgebracht februari 2019_

### <a name="power-bi-compliance-app"></a>Power BI-compatibiliteit-app 

Krijg toegang tot uw Intune-datawarehouse in Power BI Online met behulp van de [Intune-compatibiliteit-app (datawarehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Met deze Power BI-app kunt u nu vooraf gemaakte rapporten openen en delen zonder iets te hoeven instellen en zonder uw webbrowser te verlaten. 

> [!NOTE]
> Er zijn twee aanvullende filters die u kunt toepassen op de app Intune Compliance.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Aanvullende filters toevoegen aan de app Intune Compliance
1. Open de app [Intune Compliance (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) in uw webbrowser.
2. Klik op **Niet-conforme apparaten** en selecteer **Niet-conform** in het filter **complianceStatus**. 
3. Klik op **Onbekende apparaten** en selecteer **Nog niet beschikbaar** in het filter **complianceStatus**. 

## <a name="1812"></a>1812 
_Vrijgegeven in december 2018_

### <a name="enrollment-activities-collection-released-to-v10"></a>Enrollment Activities Collection v1.0 is vrijgegeven 

Enrollment Activities Collection v1.0 is nu beschikbaar. U kunt deze verzameling gebruiken om inzicht te krijgen in het aantal mislukte inschrijvingen en de trends in uw omgeving. Zie [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities), [enrollmentEventStatuses](intune-data-warehouse-collections.md#enrollmenteventstatuses), [enrollmentFailureCategories](intune-data-warehouse-collections.md#enrollmentfailurecategories) en [enrollmentFailureReasons](intune-data-warehouse-collections.md#enrollmentfailurereasons) voor meer informatie.

## <a name="1808"></a>1808
_Uitgebracht: augustus 2018_

### <a name="v10-collections"></a>Verzamelingen v1.0  

U kunt nu versie v1.0 van een Intune-datawarehouse gebruiken door de queryparameter `api-version=v1.0` in te stellen. Updates voor verzamelingen in het datawarehouse zijn additief van aard en veroorzaken geen problemen voor bestaande scenario's.

### <a name="enrollment-activities-collection-released-to-beta"></a>Enrollment Activities Collection is nu beschikbaar als bètaversie

De nieuwe verzameling `Enrollment Activities` is vrijgegeven als beta. U kunt deze verzameling gebruiken om inzicht te krijgen in hoe uw inschrijving verloopt, door de meest voorkomende fouten weer te geven. 


## <a name="1805"></a>1805
_Uitgebracht: mei 2018_

### <a name="correction-to-device-count-in-devices-collection"></a>Correctie van het aantal apparaten in de verzameling **Apparaten** 

Er is een correctie toegepast voor de verzameling **Apparaten**, waardoor het totaalaantal apparaten dat op het kenmerk `isDeleted` wordt gefilterd, lager kan zijn. Deze verlaging is het resultaat van de correctie en is geen fout. Voor meer informatie met betrekking tot de verzameling **Apparaten**, raadpleegt u [Verwijzing voor apparaatentiteiten](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Uitgebracht in januari 2018_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Intune Datawarehouse-verificatie enkel voor toepassing <!-- 1867540 -->

U kunt een toepassing instellen met behulp van Azure Active Directory (Azure AD) en verifiëren bij Intune Datawarehouse. Zie voor meer informatie [Intune-datawarehouse-verificatie enkel voor toepassing](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Azure AD en Intune-referentievereisten <!-- 2077525 -->

- Intune-licenties hoeven niet meer te worden toegewezen aan de gebruiker bij het openen van het Intune-datawarehouse (met inbegrip van de API).
- De Intune-rolnaam is veranderd van **Rapporten** in **Intune-datawarehouse**. 

    Zie [Azure AD en Intune-referentievereisten](reports-api-url.md#azure-ad-and-intune-credential-requirements) voor meer informatie.

### <a name="odata-query-options----2077711---"></a>OData-queryopties <!-- 2077711 -->

U kunt <code>$select</code> gebruiken als OData-queryparameter. De huidige versie ondersteunt de volgende OData-queryparameters: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> en <code>$top</code>. Zie [OData-queryopties](reports-api-url.md#odata-query-options) voor meer informatie.

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Nieuwe entiteiten in het Data Warehouse-gegevensmodel <!-- 2077804 -->

- De entiteit [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md) is toegevoegd. De **MobileAppDeviceUserInstallStatus** toont de installatiestatus van een mobiele app voor een bepaald apparaat en een bepaalde gebruiker.
- De entiteit [**MobileAppInstallStates**](reports-ref-application.md#mobileappinstallstates) is toegevoegd. De entiteit **MobileAppInstallState** vertegenwoordigt de installatiestatus van een mobiele toepassing nadat deze is toegewezen aan een groep apparaten, gebruikers of beide. 

## <a name="1710"></a>1710
_Uitgebracht: november 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>De nieuwe entiteitverzameling Huidige gebruiker is beperkt tot gegevens van actieve gebruikers <!-- 1544273 -->

De entiteitverzameling **Gebruiker** bevat alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming. Deze records bevatten gebruikersstatussen gedurende de periode van gegevensverzameling, ook als de gebruiker is verwijderd. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

Daarentegen bevat de nieuwe entiteitverzameling **Huidige gebruiker** alleen gebruikers die niet zijn verwijderd. De entiteitverzameling **Huidige gebruiker** bevat alleen gebruikers die momenteel actief zijn. Zie [Naslaginformatie voor huidige gebruikersentiteit](../reports-ref-current-user.md) voor informatie over de entiteitverzameling **Huidige gebruiker**.

## <a name="1709"></a>1709
_Uitgebracht: oktober 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Verzameling voor koppelingsentiteit voor gebruikersapparaten toegevoegd aan het Intune-datawarehouse-gegevensmodel <!-- 1187917 -->

U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten. Het gegevensmodel is toegankelijk via het Power BI-bestand (PBIX) dat wordt opgehaald op de datawarehouse-pagina in Intune, via het OData-eindpunt of door een aangepaste client te ontwikkelen. Zie de [Gebruikersapparaatkoppelingen](reports-ref-user-device.md) voor meer informatie.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Nieuwe entiteiten in het Data Warehouse-gegevensmodel <!-- 1479526 --><!-- -->

- De entiteit [ **UserDeviceAssociation**](reports-ref-user-device.md) is toegevoegd. **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie. U kunt rapporten en gegevensvisualisaties maken met behulp van de informatie over de gebruikersapparaatkoppelingen; deze koppelen verzamelingen over gebruikers en apparaten.  
- De entiteit [ **IntuneManagementExtension**](reports-ref-intunemanagementextension.md) is toegevoegd. **IntuneManagementExtension** bevat entiteiten voor mobiele apparaten die informatie bijhouden, zoals de versie en de status van de installatie.

## <a name="next-steps"></a>Volgende stappen
- Ontdek [wat er elke week nieuw is in Intune](../fundamentals/whats-new.md). U vindt hier ook informatie over toekomstige wijzigingen, belangrijke kennisgevingen betreffende de service en informatie over oudere releases.
- Lees het [Microsoft Intune-blog](https://go.microsoft.com/fwlink/?LinkID=273882).
