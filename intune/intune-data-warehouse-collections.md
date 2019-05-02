---
title: Intune-datawarehouse-verzamelingen
titleSuffix: Microsoft Intune
description: De Intune-datawarehouse-verzamelingen bieden informatie met betrekking tot de datawarehouse-API.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29f09230-dc56-43db-b599-d961967bda49
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 00a0bd4936d1ad8ba8dd52f1839e7d42505db60e
ms.sourcegitcommit: 601327125ac8ae912d8159422de8aac7dbdc25f6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/09/2019
ms.locfileid: "59429221"
---
#  <a name="intune-data-warehouse-collections"></a>Intune-datawarehouse-verzamelingen

De volgende Intune-datawarehouse-verzamelingen bevatten de eigenschappen, beschrijvingen en voorbeelden voor de v1.0-verzamelingen van entiteiten voor de datawarehouse-API. 

## <a name="apprevisions"></a>appRevisions
De entiteit **AppRevision** biedt een overzicht van alle versies van apps.

|          Eigenschap          |                                      Beschrijving                                      |                Voorbeeld               |
|:--------------------------:|:-------------------------------------------------------------------------------------:|:------------------------------------:|
| AppKey                     | De unieke id van de app.                                                         | 123                                  |
| ApplicationID              | De unieke id van de app, vergelijkbaar met AppKey, maar dit is een natuurlijke sleutel.        | b66bc706-ffff-7437-0340-032819502773 |
| Revisie                   | De versie zoals vermeld door de beheerder tijdens het uploaden van het binaire bestand.                   | 2                                    |
| Titel                      | De titel van de app.                                                                     | Excel                                |
| Uitgever                  | De uitgever van de app.                                                                 | Microsoft                            |
| UploadState                | De uploadstatus van de app.                                                              | 1                                    |
| AppTypeKey                 | Verwijzing naar AppType, zoals beschreven in de volgende sectie.                            | 1                                    |
| VppProgramTypeKey          | Verwijzing naar VppProgramType, zoals hieronder beschreven.                                        | 30876                                |
| CreationTime               | Het tijdstip waarop deze revisie is gemaakt.                                            | 23-11-2016, 0:00                      |
| ModifiedTime               | De laatste keer dat er iets aan deze revisie is gewijzigd.                            | 23-11-2016, 0:00                      |
| Grootte                       | De grootte van het binaire bestand in bytes.                                                          | 120.392.000                          |
| StartDateInclusiveUTC      | De datum en tijd in UTC waarop deze app-revisie is gemaakt in het datawarehouse.      | 23-11-2016, 0:00                      |
| EndDateExclusiveUTC        | De datum en tijd in UTC waarop deze app-revisie verouderd is geraakt.                        | 23-11-2016, 0:00                      |
| IsCurrent                  | Geeft aan of deze app-versie actueel is of niet aanwezig is in het datawarehouse.         | Waar/onwaar                           |
| RowLastModifiedDateTimeUTC | De datum en tijd in UTC waarop deze app-versie het laatst is gewijzigd in het datawarehouse. | 23-11-2016, 0:00                      |

## <a name="apptypes"></a>AppTypes
De entiteit **appType** vermeldt de installatiebron van een app.

|   Eigenschap  |        Beschrijving        |
|:-----------:|:-------------------------:|
| AppTypeID   | De id voor het type           |
| AppTypeKey  | De surrogaatsleutel voor de sleutel |
| AppTypeName | App-type                  |

### <a name="example"></a>Voorbeeld

| AppTypeID |                Naam               |                     Beschrijving                     |
|:---------:|:---------------------------------:|:---------------------------------------------------:|
| 0         | Android Store-app               | Een Android Store-app.                             |
| 1         | Android LOB-app                 | Een Android Line-Of-Business-app.                  |
| 2         | Beheerde Android Store-app (MAM) | Een Android Store-app die onder beheer staat. |
| 3         | iOS Store-app                   | Een iOS Store-app.                                 |
| 4         | iOS LOB-app                     | Een iOS Line-Of-Business-app.                      |
| 5         | Beheerde iOS Store-app (MAM)     | Een iOS Store-app die onder beheer staat.       |
| 6         | O365 Pro Plus Suite             | De Office 365 Pro Plus Suite voor Windows 10.     |
| 7         | Web-app                         | Een web-app.                                        |
| 8         | Windows Phone 8.1 Store-app     | Een Windows Phone 8.1 Store-app.                    |
| 9         | Windows Store-app               | Een Windows Store-app.                              |
| 10        | Windows LOB-app                | Een Windows AppX Line-Of-Business-app.              |
| 11        | Windows Mobile MSI              | Een MSI Line-Of-Business-app.                      |
| 12        | Windows Phone LOB-app           | Een Windows Phone Line-of-Business-app.             |

## <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities
De volgende tabel geeft een overzicht van de toewijzingsstatus van nalevingsbeleid voor apparaten. In de tabel wordt het aantal apparaten weergegeven dat is gevonden voor elke nalevingsstatus.

|    Eigenschap   |                                                                                      Beschrijving                                                                                     |  Voorbeeld |
|:-------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey       | De datum waarop de samenvatting voor het nalevingsbeleid is gemaakt.                                                                                                                   | 20161204 |
| Onbekend       | Het aantal apparaten dat offline is of om een andere redenen niet kan communiceren met Intune of Azure AD.                                                                           | 5        |
| Niet van toepassing | Het aantal apparaten waarvoor het nalevingsbeleid waarop de beheerder zich richt, niet van toepassing is.                                                                                     | 201      |
| Compliant     | Het aantal apparaten waarop een of meer nalevingsbeleidsregels voor apparaten is toegepast waarop de beheerder zich richt.                                                                        | 4083     |
| Respijtperiode | Aantal apparaten die niet voldoen aan het beleid, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld.                                                                                  | 57       |
| Niet-compatibel  | Het aantal apparaten waarop een of meer nalevingsbeleidsregels niet zijn toegepast waarop de beheerder zich richt of waarvoor de gebruiker niet voldoet aan de beleidsregels waarop de beheerder zich richt. | 43       |
|    Fout      |    Het aantal apparaten dat niet kan communiceren met Intune of Azure AD en een foutbericht heeft geretourneerd.                                                                          |    3     |

## <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities
De volgende tabel geeft een overzicht van de toewijzingsstatus van nalevingsbeleid voor apparaten per beleid en per beleidstype. In de tabel wordt het aantal apparaten weergegeven dat is gevonden in elke nalevingsstatus voor elk toegewezen nalevingsbeleid.

|      Eigenschap     |                                                                                      Beschrijving                                                                                     |  Voorbeeld |
|:-----------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey           | De datum waarop de samenvatting voor het nalevingsbeleid is gemaakt.                                                                                                                   | 20161219 |
| PolicyKey         | Sleutel voor het nalevingsbeleid waarvoor de samenvatting is gemaakt.                                                                                                                   | 10178    |
| PolicyPlatformKey | Sleutel voor het platformtype van het nalevingsbeleid waarvoor de samenvatting is gemaakt.                                                                                            | 5        |
| Onbekend           | Het aantal apparaten dat offline is of om een andere redenen niet kan communiceren met Intune of Azure AD.                                                                           | 13       |
| Niet van toepassing     | Het aantal apparaten waarvoor het nalevingsbeleid waarop de beheerder zich richt, niet van toepassing is.                                                                                     | 3        |
| Compliant         | Het aantal apparaten waarop een of meer nalevingsbeleidsregels voor apparaten is toegepast waarop de beheerder zich richt.                                                                        | 45       |
| Respijtperiode     | Aantal apparaten die niet voldoen aan het beleid, maar zich in de respijtperiode bevindt die door de beheerder is vastgesteld.                                                                                  | 3        |
| Niet-compatibel      | Het aantal apparaten waarop een of meer nalevingsbeleidsregels niet zijn toegepast waarop de beheerder zich richt of waarvoor de gebruiker niet voldoet aan de beleidsregels waarop de beheerder zich richt. | 7        |
| Fout             | Het aantal apparaten dat niet kan communiceren met Intune of Azure AD en een foutbericht heeft geretourneerd.                                                                             | 3        |
## <a name="compliancestates"></a>complianceStates

|      Eigenschap      |                       Beschrijving                      |
|:------------------:|:------------------------------------------------------:|
| complianceStatus   | Status van naleving van apparaten met mdmStatusKey       |
| complianceStateKey | Nalevingssleutel die overeenkomt met het apparaat en de nalevingsstatus |
| complianceStateID  | De id die overeenkomt met deze nalevingsstatus                |

### <a name="example"></a>Voorbeeld

|  complianceStatus  |                       Beschrijving                      |
|:------------------:|:------------------------------------------------------:|
|    Onbekend         |    Onbekend.                                                                        |
|    Compliant       |    Voldoet aan het beleid.                                                                      |
|    Noncompliant    |       Apparaat voldoet niet aan het beleid en heeft geen toegang tot bedrijfsresources.             |
|    Conflict        |    Conflict met andere regels.                                                      |
|    Fout           |       Fout.                                                                       |
|    ConfigManager   |    Beheerd door Configuration Manager.                                                      |
|    Respijtperiode   |       Apparaat voldoet niet aan het beleid, maar heeft nog steeds toegang tot bedrijfsbronnen          |

## <a name="dates"></a>dates
De entiteit **date** vertegenwoordigt datums waarnaar wordt verwezen door meerdere datawarehouse-entiteiten.

|     Eigenschap    |                       Beschrijving                      |    Voorbeeld    |
|:---------------:|:------------------------------------------------------:|:-------------:|
| DateKey         | Unieke id voor deze datum in het datawarehouse. | 20160703      |
| FullDate        | Deze datum wordt weergegeven in de volledige datum-/tijdnotatie.        | 3-7-2016, 0:00 |
| DayOfWeek       | Dag van week                                            | 1             |
| DayOfMonth      | Dag van maand                                           | 3             |
| DayOfYear       | Dag van jaar                                            | 185           |
| WeekOfYear      | Week van jaar                                           | 28            |
| MonthOfYear     | Maand van jaar                                      | 7             |
| CalendarQuarter | Kalenderkwartaal                                       | 3             |
| CalendarYear    | Kalenderjaar                                          | 2016          |
| DateKey         | Unieke id voor deze datum in het datawarehouse. | 20160703      |
| FullDate        | Deze datum wordt weergegeven in de volledige datum-/tijdnotatie.        | 3-7-2016, 0:00 |
| DayOfWeek       | Dag van week                                            | 1             |
| DayOfMonth      | Dag van maand                                           | 3             |
| DayOfYear       | Dag van jaar                                            | 185           |
| WeekOfYear      | Week van jaar                                           | 28            |
| MonthOfYear     | Maand van jaar                                      | 7             |
| CalendarQuarter | Kalenderkwartaal                                       | 3             |
| CalendarYear    | Kalenderjaar                                          | 2016          |

## <a name="devicecategories"></a>deviceCategories

|      Eigenschap      |                                    Beschrijving                                   |                Voorbeeld               |
|:------------------:|:--------------------------------------------------------------------------------:|:------------------------------------:|
| deviceCategoryID   | De unieke id voor de apparaatcategorie.                                       | fb415ba2-7c08-41f6-a5e5-685b50da2c4c |
| deviceCategoryKey  | Unieke id van de apparaatcategorie in het datawarehouse - surrogaatsleutel. | 1                                    |
| deviceCategoryName | Weergavenaam voor de apparaatcategorie.                                            | Smartphones                          |

## <a name="deviceconfigurationprofiledeviceactivities"></a>deviceConfigurationProfileDeviceActivities
De entiteit **DeviceConfigurationProfileDeviceActivity** bevat het aantal apparaten met de status geslaagd, in behandeling, mislukt of fout per dag. Het aantal weerspiegelt de apparaatconfiguratieprofielen die zijn toegewezen aan de entiteit. Als een apparaat bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een apparaat twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de teller Geslaagd met één opgehoogd en wordt het apparaat in de foutstatus geplaatst. De entiteit geeft voor de afgelopen 30 dagen aan hoeveel apparaten op een bepaalde dag een bepaalde status hebben.

|  Eigenschap |                                          Beschrijving                                          |  Voorbeeld |
|:---------:|:---------------------------------------------------------------------------------------------:|:--------:|
| DateKey   | De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. | 20160703 |
| In behandeling   | Aantal unieke apparaten met de status In behandeling.                                                    | 123      |
| Geslaagd | Aantal unieke apparaten met de status Geslaagd.                                                    | 12       |
| Fout     | Aantal unieke apparaten met de status Fout.                                                      | 10       |
| Mislukt    | Aantal unieke apparaten met de status Mislukt.                                                     | 2        |

## <a name="deviceconfigurationprofileuseractivities"></a>deviceConfigurationProfileUserActivities 
De entiteit **DeviceConfigurationProfileUserActivity** bevat het aantal gebruikers met de status Geslaagd, In behandeling, Mislukt of Fout per dag. Het aantal weerspiegelt de apparaatconfiguratieprofielen die zijn toegewezen aan de entiteit. Als een gebruiker bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een gebruiker twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de gebruiker in de foutstatus geplaatst. De entiteit **DeviceConfigurationProfileUserActivity** geeft voor de afgelopen dertig dagen aan hoeveel gebruikers op een bepaalde dag een bepaalde status hebben. 

| Eigenschap  | Beschrijving  | Voorbeeld  |
|------------|----------------------------------------------------------------------------------------------|-----------|
| DateKey  | De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse.  | 20160703  |
| In behandeling  | Aantal unieke gebruikers met de status In behandeling.  | 123  |
| Geslaagd  | Aantal unieke gebruikers met de status Geslaagd.  | 12  |
| Fout  | Aantal unieke gebruikers met de status Fout.  | 10  |
| Mislukt  | Aantal unieke gebruikers met de status Mislukt.  | 2  |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

|          Eigenschap          |                                                                                      Beschrijving                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DateKey                    | Verwijzing naar datumtabel waarmee de dag wordt aangegeven.                                                                                                                                          |
| DeviceKey                  | Unieke id van het apparaat in het datawarehouse - surrogaatsleutel. Dit is een verwijzing naar de apparaattabel die de Intune-apparaat-id bevat.                               |
| DeviceName                 | Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten. |
| DeviceRegistrationStateKey | Sleutel van het kenmerk voor de apparaatregistratiestatus voor dit apparaat.                                                                                                                    |
| OwnerTypeKey               | Sleutel van het kenmerk voor het type eigenaar voor dit apparaat: zakelijk, persoonlijk of onbekend.                                                                                                  |
| ManagementStateKey         | Sleutel van de aan dit apparaat gekoppelde beheerstatus, waarmee de laatste status van een externe actie wordt aangegeven of dat het apparaat is gekraakt of geroot.                                                |
| AzureADRegistered          | Of het apparaat is geregistreerd bij Azure Active Directory.                                                                                                                             |
| ComplianceStateKey         | Een sleutel voor de ComplianceState.                                                                                                                                                            |
| OSVersion                  | Versie besturingssysteem.                                                                                                                                                                          |
| JailBroken                 | Of het apparaat jailbroken of geroot is.                                                                                                                                         |
| DeviceCategoryKey          | Sleutel van het kenmerk voor de apparaatcategorie voor dit apparaat.                                                                                                                                    |
## <a name="deviceregistrationstates"></a>deviceRegistrationStates
De entiteit **DeviceRegistrationState** vertegenwoordigt het registratietype waarnaar wordt verwezen door andere datawarehouse-verzamelingen. 

|           Eigenschap          |                                     Beschrijving                                     |
|:---------------------------:|:-----------------------------------------------------------------------------------:|
| deviceRegistrationStateID   | Unieke id voor registratiestatus                                            |
| deviceRegistrationStateKey  | Unieke id van de registratiestatus in het datawarehouse - surrogaatsleutel |
| deviceRegistrationStateName | Registratiestatus                                                                  |
|    NotRegistered                     |    Niet geregistreerd                                                                                                                                                                  |
|    Geregistreerd                        |       Geregistreerd                                                                                                                                                                   |
|    Revoked                           |       Status betekent dat de client is geblokkeerd door de IT-beheerder en dat de blokkering voor de client kan worden opgeheven. Een apparaat kan ook de status Ingetrokken hebben nadat deze is gewist of buiten gebruik is gesteld.        |
|    KeyConflict                       |    Sleutelconflict                                                                                                                                                                    |
|    ApprovalPending                   |    Goedkeuring in behandeling                                                                                                                                                                |
|    CertificateReset                  |    Certificaat opnieuw instellen                                                                                                                                                               |
|    NotRegisteredPendingEnrollment    |    Niet geregistreerde, in behandeling zijnde registratie                                                                                                                                               |
|    Onbekend                           |    Onbekende status                                                                                                                                                                   |

## <a name="devices"></a>devices
Met de entiteit **devices** worden alle geregistreerde apparaten voor beheer en de bijbehorende eigenschappen weergegeven.

|          Eigenschap          |                                                                                       Beschrijving                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DeviceKey                  | Unieke id van het apparaat in het datawarehouse - surrogaatsleutel.                                                                                                               |
| DeviceId                   | Unieke id van het apparaat.                                                                                                                                                     |
| DeviceName                 | Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten. |
| DeviceTypeKey              | Sleutel van het kenmerk voor het apparaattype voor dit apparaat.                                                                                                                                    |
| DeviceRegistrationState    | Sleutel van het kenmerk voor de clientregistratiestatus voor dit apparaat.                                                                                                                      |
| OwnerTypeKey               | Sleutel van het kenmerk voor het type eigenaar voor dit apparaat: zakelijk, persoonlijk of onbekend.                                                                                                    |
| EnrolledDateTime           | De datum en tijd waarop het apparaat is ingeschreven.                                                                                                                                         |
| LastSyncDateTime           | Laatste bekende keer dat een apparaat is ingecheckt bij Intune.                                                                                                                                              |
| ManagementAgentKey         | Sleutel van de beheeragent die is gekoppeld aan dit apparaat.                                                                                                                             |
| ManagementStateKey         | Sleutel van de aan dit apparaat gekoppelde beheerstatus waarmee de laatste status van een externe actie wordt aangegeven of dat het apparaat is gekraakt of geroot.                                                |
| AzureADDeviceId            | De Azure-apparaat-id voor dit apparaat.                                                                                                                                                  |
| AzureADRegistered          | Of het apparaat is geregistreerd bij Azure Active Directory.                                                                                                                             |
| DeviceCategoryKey          | Sleutel van de categorie die is gekoppeld aan dit apparaat.                                                                                                                                     |
| DeviceEnrollmentType       | Sleutel van het registratietype dat is gekoppeld aan dit apparaat (geeft de registratiemethode aan).                                                                                             |
| ComplianceStateKey         | Sleutel van de Nalevingsstatus die is gekoppeld aan dit apparaat.                                                                                                                             |
| OSVersion                  | Versie van het besturingssysteem van het apparaat.                                                                                                                                                |
| EasDeviceId                | De Exchange ActiveSync-id van het apparaat.                                                                                                                                                  |
| SerialNumber               | SerialNumber                                                                                                                                                                           |
| UserId                     | De unieke id voor de gebruiker die is gekoppeld aan het apparaat.                                                                                                                           |
| RowLastModifiedDateTimeUTC | De datum en tijd in UTC waarop dit apparaat het laatst is gewijzigd in het datawarehouse.                                                                                                       |
| Fabrikant               | Fabrikant van het apparaat                                                                                                                                                             |
| Model                      | Model van het apparaat                                                                                                                                                                    |
| OperatingSystem            | Het besturingssysteem van het apparaat. Windows, iOS, enzovoort.                                                                                                                                   |
| IsDeleted                  | Binaire code om weer te geven of het apparaat is verwijderd of niet.                                                                                                                                 |
| AndroidSecurityPatchLevel  | Niveau Android-beveiligingspatch                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | De supervisiestatus van het apparaat                                                                                                                                                               |
| FreeStorageSpaceInBytes    | Beschikbare opslag in bytes.                                                                                                                                                                 |
| TotalStorageSpaceInBytes   | Totale opslag in bytes.                                                                                                                                                                |
| EncryptionState            | De versleutelingsstatus van het apparaat.                                                                                                                                                      |
| SubscriberCarrier          | Provider van abonnee van het apparaat                                                                                                                                                       |
| PhoneNumber                | Telefoonnummer van het apparaat                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| CellularTechnology         | Mobiele telefoontechnologie van het apparaat                                                                                                                                                    |
| WiFiMacAddress             | MAC-adres Wi-Fi                                                                                                                                                                              |


## <a name="devicetypes"></a>deviceTypes
De entiteit **deviceTypes** vertegenwoordigt het apparaattype waarnaar wordt verwezen door andere datawarehouse-entiteiten. Met het apparaattype wordt doorgaans het model, de fabrikant of een combinatie van beide beschreven.

|    Eigenschap    |                                  Beschrijving                                 |
|:--------------:|:----------------------------------------------------------------------------:|
| DeviceTypeID   | Unieke id van het apparaattype                                       |
| DeviceTypeKey  | Unieke id van het apparaattype in het datawarehouse - surrogaatsleutel |
| DeviceTypeName | Apparaattype                                                                |

### <a name="example"></a>Voorbeeld

| deviceTypeID |        Naam       |                      Beschrijving                      |
|:------------:|:-----------------:|:-----------------------------------------------------:|
| -1           | Niet beschikbaar   | Het apparaattype is niet beschikbaar.                     |
| 0            | Desktop           | Windows Desktop-apparaat                              |
| 1            | Windows           | Windows-apparaat                                      |
| 2            | WinMO6            | Windows Mobile 6.0-apparaat                           |
| 3            | Nokia             | Nokia-apparaat                                        |
| 4            | WindowsPhone      | Windows Phone-apparaat                                |
| 5            | Mac               | Mac-apparaat                                          |
| 6            | WinCE             | Windows CE-apparaat                                   |
| 7            | WinEmbedded       | Windows Embedded-apparaat                             |
| 8            | IPhone            | iPhone-apparaat                                       |
| 9            | IPad              | iPad-apparaat                                         |
| 10           | IPod              | iPod-apparaat                                         |
| 11           | Android           | Android-apparaat dat wordt beheerd met Apparaatbeheer   |
| 12           | ISocConsumer      | iSoc Consumer-apparaat                                |
| 13           | Unix              | UNIX-apparaat                                         |
| 14           | MacMDM            | Mac OS X-apparaat dat wordt beheerd met de ingebouwde MDM-agent |
| 15           | HoloLens          | HoloLens-apparaat                                       |
| 16           | SurfaceHub        | Surface Hub-apparaat                                  |
| 17           | AndroidForWork    | Android-apparaat dat wordt beheerd met de Android-profieleigenaar  |
| 18           | AndroidEnterprise | Android Enterprise-apparaat                          |
| 100          | Blackberry        | Blackberry-apparaat                                   |
| 101          | Palm              | Palm-apparaat                                         |
| 255          | Onbekend           | Onbekend apparaattype                                 |

## <a name="deviceenrollmenttypes"></a>deviceEnrollmentTypes
De entiteit **deviceEnrollmentType** geeft aan hoe een apparaat is geregistreerd. Met het registratietype wordt de registratiemethode vastgelegd. In de voorbeelden ziet u de verschillende registratietypen en hun betekenis.

|         Eigenschap         |                                    Beschrijving                                    |
|:------------------------:|:---------------------------------------------------------------------------------:|
| deviceEnrollmentTypeID   | Unieke id van het registratietype.                                       |
| deviceEnrollmentTypeKey  | Unieke id van het registratietype in het datawarehouse - surrogaatsleutel. |
| deviceEnrollmentTypeName | Naam inschrijvingstype.                                                           |

### <a name="example"></a>Voorbeeld

| enrollmentTypeID |                Naam                |                                        Beschrijving                                       |
|:----------------:|:----------------------------------:|:----------------------------------------------------------------------------------------:|
| 0                | Onbekend                            | Registratietype is niet verzameld                                                      |
| 1                | UserEnrollment                     | Door gebruiker geactiveerde registratie via BYOD-kanaal.                                           |
| 2                | DeviceEnrollmentManager            | Gebruikersregistratie met een apparaatinschrijvingsmanageraccount.                              |
| 3                | AppleBulkWithUser                  | Apple-bulkinschrijving met gebruikersinteractie. (DEP, Apple Configurator)                   |
| 4                | AppleBulkWithoutUser               | Apple-bulkinschrijving zonder gebruikersinteractie.   (DEP, Apple Configurator, Mobile Config) |
| 5                | WindowsAzureADJoin                 | Windows 10 Azure AD-inschrijving.                                                                |
| 6                | WindowsBulkUserless                | Windows 10-bulkinschrijving via ICD met certificaat.                               |
| 7                | WindowsAutoEnrollment              | Automatische inschrijving voor Windows 10.   (Werkaccount toevoegen)                                    |
| 8                | WindowsBulkAzureDomainJoin         | Bulksgewijze Azure AD-inschrijving in Windows 10.                                                           |
| 9                | WindowsCoManagement                | Co-beheer voor Windows 10, geactiveerd door AutoPilot of Groepsbeleid.                       |
| 10               | WindowsAzureADJoinsUsingDeviceAuth | Azure AD-inschrijvingen in Windows 10 met behulp van apparaatverificatie.                                            |

## <a name="enrollmentactivities"></a>enrollmentActivities 
De entiteit **EnrollmentActivity** geeft de activiteit van een apparaatinschrijving aan.

| Eigenschap                      | Beschrijving                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | De sleutel van de datum waarop deze inschrijvingsactiviteit is geregistreerd.               |
| deviceEnrollmentTypeKey       | De sleutel van het type inschrijving.                                        |
| deviceTypeKey                 | De sleutel van het type apparaat.                                                |
| enrollmentEventStatusKey      | De sleutel van de status waarmee wordt aangegeven of het inschrijven is geslaagd of mislukt.    |
| enrollmentFailureCategoryKey  | De sleutel van de categorie van de mislukte inschrijving (als de inschrijving is mislukt).        |
| enrollmentFailureReasonKey    | De sleutel van de reden voor het mislukken van de inschrijving (als de inschrijving is mislukt).          |
| osVersion                     | De versie van het besturingssysteem van het apparaat.                               |
| count                         | Het totale aantal inschrijvingsactiviteiten dat overeenkomt met de bovenstaande classificaties.  |

## <a name="enrollmenteventstatuses"></a>enrollmentEventStatuses 
De entiteit **EnrollmentEventStatus** geeft het resultaat van een apparaatinschrijving aan.

| Eigenschap                   | Beschrijving                                                                       |
|----------------------------|-----------------------------------------------------------------------------------|
| enrollmentEventStatusKey   | De unieke id van de inschrijvingsstatus in het datawarehouse (surrogaatsleutel)  |
| enrollmentEventStatusName  | De naam van de inschrijvingsstatus. Zie de onderstaande voorbeelden.                            |

### <a name="example"></a>Voorbeeld

| enrollmentEventStatusName  | Beschrijving                            |
|----------------------------|----------------------------------------|
| Geslaagd                    | Een geslaagde apparaatinschrijving         |
| Mislukt                     | Een mislukte apparaatinschrijving             |
| Niet beschikbaar              | De inschrijvingsstatus is onbekend.  |

## <a name="enrollmentfailurecategories"></a>enrollmentFailureCategories 
De entiteit **EnrollmentFailureCategory** geeft aan waarom een apparaatinschrijving is mislukt. 

| Eigenschap                       | Beschrijving                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| enrollmentFailureCategoryKey   | De unieke id van de categorie van de mislukte inschrijving in het datawarehouse (surrogaatsleutel)  |
| enrollmentFailureCategoryName  | De naam van de categorie van de mislukte inschrijving. Zie de onderstaande voorbeelden.                            |

### <a name="example"></a>Voorbeeld

| enrollmentFailureCategoryName   | Beschrijving                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------|
| Niet van toepassing                  | De categorie van de mislukte inschrijving is niet van toepassing.                                                            |
| Niet beschikbaar                   | De categorie van de mislukte inschrijving is niet beschikbaar.                                                             |
| Onbekend                         | Onbekende fout.                                                                                                |
| Verificatie                  | Verificatie mislukt.                                                                                        |
| Autorisatie                   | De aanroep is geverifieerd, maar niet geautoriseerd om in te schrijven.                                                         |
| AccountValidation               | Kan het account niet valideren voor inschrijving. (Account geblokkeerd, inschrijving niet ingeschakeld)                      |
| UserValidation                  | De gebruiker kan niet worden gevalideerd. (De gebruiker bestaat niet, ontbrekende licentie)                                           |
| DeviceNotSupported              | Het apparaat wordt niet ondersteund voor Mobile Device Management.                                                         |
| InMaintenance                   | Het account bevindt zich in de onderhoudsmodus.                                                                                    |
| BadRequest                      | De client heeft een aanvraag verzonden die niet wordt begrepen/ondersteund door de service.                                        |
| FeatureNotSupported             | Een of meer functies die worden gebruikt door deze inschrijving, worden niet ondersteund voor dit account.                                        |
| EnrollmentRestrictionsEnforced  | De inschrijving wordt geblokkeerd door de inschrijvingsbeperkingen die door de beheerder zijn geconfigureerd.                                          |
| ClientDisconnected              | Er is een time-out voor de client opgetreden of de inschrijving is afgebroken door de eindgebruiker.                                                        |
| UserAbandonment                 | De inschrijving is afgebroken door de eindgebruiker. (Onboarding is gestart door de eindgebruiker, maar kon niet tijdig worden voltooid)  |

## <a name="enrollmentfailurereasons"></a>enrollmentFailureReasons  
De entiteit **EnrollmentFailureReason** geeft een meer gedetailleerde redenen voor een apparaatinschrijvingsfout binnen een bepaalde foutcategorie.  

| Eigenschap                     | Beschrijving                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------|
| enrollmentFailureReasonKey   | De unieke id van de reden van de mislukte inschrijving in het datawarehouse (surrogaatsleutel)  |
| enrollmentFailureReasonName  | De naam van de inschrijvingsfoutoorzaak. Zie de onderstaande voorbeelden.                            |

### <a name="example"></a>Voorbeeld

| enrollmentFailureReasonName      | Beschrijving                                                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Niet van toepassing                   | De reden van de mislukte inschrijving is niet van toepassing.                                                                                                                                                       |
| Niet beschikbaar                    | De reden van de mislukte inschrijving is niet beschikbaar.                                                                                                                                                        |
| Onbekend                          | Onbekende fout.                                                                                                                                                                                         |
| UserNotLicensed                  | Kan de gebruiker niet vinden in Intune of de gebruiker heeft geen geldige licentie.                                                                                                                                     |
| UserUnknown                      | De gebruiker is niet bekend bij Intune.                                                                                                                                                                           |
| BulkAlreadyEnrolledDevice        | Slechts één gebruiker kan een apparaat inschrijven. Dit apparaat is eerder ingeschreven door een andere gebruiker.                                                                                                                |
| EnrollmentOnboardingIssue        | De Intune MDM-instantie (Mobile Device Management) is nog niet geconfigureerd.                                                                                                                                 |
| AppleChallengeIssue              | De installatie van het iOS-beheerprofiel is vertraagd of mislukt.                                                                                                                                         |
| AppleOnboardingIssue             | Een Apple MDM-pushcertificaat is vereist om in te schrijven bij Intune.                                                                                                                                       |
| DeviceCap                        | De gebruiker probeert meer apparaten in te schrijven dan maximaal is toegestaan.                                                                                                                                        |
| AuthenticationRequirementNotMet  | Deze aanvraag kan niet door de Intune-inschrijvingsservice worden geautoriseerd.                                                                                                                                            |
| UnsupportedDeviceType            | Dit apparaat voldoet niet aan de minimumvereisten voor Intune-inschrijving.                                                                                                                                  |
| EnrollmentCriteriaNotMet         | Kan dit apparaat niet inschrijven vanwege een geconfigureerde regel om de inschrijving te beperken.                                                                                                                          |
| BulkDeviceNotPreregistered       | Kan de id voor internationale mobiele apparatuur (IMEI) of het serienummer van het apparaat niet vinden.  Zonder deze id worden apparaten herkend als apparaten in persoonlijk eigendom die momenteel zijn geblokkeerd.  |
| FeatureNotSupported              | De gebruiker probeert een functie te gebruiken die nog niet is vrijgegeven voor alle klanten of die niet compatibel is met uw Intune-configuratie.                                                            |
| UserAbandonment                  | De inschrijving is afgebroken door de eindgebruiker. (Onboarding is gestart door de eindgebruiker, maar kon niet tijdig worden voltooid)                                                                                           |
| APNSCertificateExpired           | Apple-apparaten kunnen niet worden beheerd met een verlopen Apple MDM-pushcertificaat.                                                                                                                            |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions
De **IntuneManagementExtension** bevat een lijst met dagelijkse **IntuneManagementExtension**-statussen voor elk apparaat met Windows 10. De gegevens voor de afgelopen 60 dagen worden bewaard.

|       Eigenschap      |                          Beschrijving                          | Voorbeeld |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| DateKey             | De unieke id van de datum.                                | 123     |
| TenantKey           | De unieke id van de tenant.                              | 456     |
| DeviceKey           | Unieke id van het apparaat.                              | 789     |
| ExtensionVersionKey | De unieke id van de IntuneManagementExtension-versie. | 1       |
| ExtensionStateKey   | Unieke id van de status.                            | 2       |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates
De **IntuneManagementExtensionHealthState** bevat een lijst van alle mogelijke statussen van de **IntuneManagementExtension**.

|      Eigenschap     |                   Beschrijving                  | Voorbeeld |
|:-----------------:|:----------------------------------------------:|:-------:|
| ExtensionStateKey | Unieke id van de status.           | 2       |
| ExtensionState    | De status van een IntuneManagementExtension. | In orde |

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions
De entiteit **IntuneManagementExtensionVersion** bevat een lijst van alle versies die worden gebruikt door **IntuneManagementExtension**.

|       Eigenschap      |                          Beschrijving                          | Voorbeeld |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| ExtensionVersionKey | De unieke id van de IntuneManagementExtension-versie. | 1       |
| ExtensionVersion    | Het versienummer, bestaande uit vier cijfers.                                   | 1.0.2.0 |

## <a name="mamapplications"></a>MamApplications

De entiteit **MamApplication** bevat een lijst met LOB-apps (Line-of-Business) die via Mobile Application Management (MAM) worden beheerd, maar die niet zijn ingeschreven in uw bedrijf.

| Eigenschap | Beschrijving | Voorbeeld |
|---------|------------|--------|
| mamApplicationKey |De unieke id van de MAM-toepassing. | 432 |
| mamApplicationName |Naam van de MAM-toepassing. |De naam van het voorbeeld voor MAM-toepassing |
| mamApplicationId |De toepassings-ID van de MAM-app. | 123 |
| IsDeleted |Geeft aan of deze MAM-app-record is bijgewerkt. <br>Waar: de MAM-app heeft een nieuwe record met bijgewerkte velden in deze tabel. <br>Onwaar: de meest recente record voor deze MAM-app. |Waar/onwaar |
| StartDateInclusiveUTC |De datum en tijd in UTC waarop deze MAM-app is gemaakt in het datawarehouse. |11/23/2016 12:00:00 AM |
| DeletedDateUTC |De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar. |11/23/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze MAM-app het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |


## <a name="mamapplicationinstances"></a>MamApplicationInstances

De entiteit **MamApplicationInstance** bevat een lijst met beheerde MAM-apps (Mobile Application Management) als zelfstandige exemplaren per gebruiker per apparaat. Alle gebruikers en apparaten die worden vermeld in de entiteit zijn beveiligd, wat inhoudt dat er ten minste één MAM-beleid aan de gebruiker of het apparaat is toegewezen.


|          Eigenschap          |                                                                                                  Beschrijving                                                                                                  |               Voorbeeld                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   ApplicationInstanceKey   |                                                               De unieke id van het MAM-app-exemplaar in het datawarehouse (surrogaatsleutel).                                                                |                 123                  |
|           UserId           |                                                                              De gebruikers-id van de gebruiker die deze MAM-app heeft geïnstalleerd.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              De unieke id van het MAM-app-exemplaar, vergelijkbaar met ApplicationInstanceKey, maar de id is een natuurlijke sleutel.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | Toepassings-Id van de Mam-toepassing waarvoor deze Mam-toepassing-exemplaar is gemaakt.   | 11/23/2016 12:00:00 AM   |
|     ApplicationVersion     |                                                                                     De toepassingsversie van deze MAM-app.                                                                                      |                  2                   |
|        CreatedDate         |                                                                 De datum waarop deze record van het MAM-app-exemplaar is gemaakt. De waarde kan null zijn.                                                                 |        11/23/2016 12:00:00 AM        |
|          Platform          |                                                                          Het platform van het apparaat waarop deze MAM-app is geïnstalleerd.                                                                           |                  2                   |
|      PlatformVersion       |                                                                      De versie van het platform van het apparaat waarop deze MAM-app is geïnstalleerd.                                                                       |                 2.2                  |
|         SdkVersion         |                                                                            De MAM SDK-versie waarmee deze MAM-app is ingepakt.                                                                            |                 3.2                  |
| mamDeviceId | Apparaat-Id van het apparaat waarmee MAM-toepassing-exemplaar is gekoppeld.   | 11/23/2016 12:00:00 AM   |
| mamDeviceType | Apparaattype van het apparaat waarmee MAM-toepassing-exemplaar is gekoppeld.   | 11/23/2016 12:00:00 AM   |
| mamDeviceName | De apparaatnaam van het apparaat waarmee MAM-toepassing-exemplaar is gekoppeld.   | 11/23/2016 12:00:00 AM   |
|         IsDeleted          | Geeft aan of de record van dit MAM-app-exemplaar is bijgewerkt. <br>True: het MAM-app-exemplaar heeft een nieuwe record met bijgewerkte velden in deze tabel. <br>Onwaar: de meest recente record voor dit MAM-app-exemplaar. |              Waar/onwaar              |
|   StartDateInclusiveUTC    |                                                              De datum en tijd in UTC waarop dit MAM-app-exemplaar is gemaakt in het datawarehouse.                                                               |        11/23/2016 12:00:00 AM        |
|       DeletedDateUTC       |                                                                             De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar.                                                                              |        11/23/2016 12:00:00 AM        |
| RowLastModifiedDateTimeUTC |                                                           De datum en tijd in UTC waarop dit MAM-app-exemplaar het laatst is gewijzigd in het datawarehouse.                                                            |        11/23/2016 12:00:00 AM        |

## <a name="mamcheckins"></a>MamCheckins

De entiteit **MamCheckin** vertegenwoordigt gegevens die worden verzameld wanneer een MAM-app-exemplaar (Mobile Application Management) heeft ingecheckt bij de Intune-service. 

> [!Note]  
> Wanneer een app-exemplaar meerdere keren per dag wordt ingecheckt, wordt dit slechts eenmaal geregistreerd in het datawarehouse.

| Eigenschap | Beschrijving | Voorbeeld |
|---------|------------|--------|
| DateKey |De datum waarop het inchecken van de MAM-app is vastgelegd in het datawarehouse. | 20160703 |
| ApplicationInstanceKey |De sleutel van het app-exemplaar dat is gekoppeld aan het inchecken van deze MAM-app. | 123 |
| UserKey |De sleutel van de gebruiker die is gekoppeld aan het inchecken van deze MAM-app. | 4323 |
| mamApplicationKey |Toepassing sleutel van de toepassing die is gekoppeld aan MAM-toepassing check-in. | 432 |
| DeviceHealthKey |De sleutel van de apparaatstatus die is gekoppeld aan het inchecken van deze MAM-app. | 321 |
| PlatformKey |Het platform van het apparaat dat is gekoppeld aan het inchecken van deze MAM-app. |123 |
| LastCheckInDate |De datum en tijd waarop deze MAM-app het laatst is ingecheckt. De waarde kan null zijn. |11/23/2016 12:00:00 AM |

## <a name="mamdevicehealths"></a>MamDeviceHealths

De entiteit **MamDeviceHealth** vertegenwoordigt apparaten waarop MAM-beleid (Mobile Application Management) is geïmplementeerd, zelfs als ze opengebroken zijn.

| Eigenschap | Beschrijving | Voorbeeld |
|---------|------------|--------|
| DeviceHealthKey |De unieke id van het apparaat en de bijbehorende status in het datawarehouse (surrogaatsleutel). |123 |
| DeviceHealth |De unieke id van het apparaat en de bijbehorende status, vergelijkbaar met DeviceHealthKey, maar de id is een natuurlijke sleutel. |b66bc706-ffff-7777-0340-032819502773 |
| DeviceHealthName |De status van het apparaat. <br>Niet beschikbaar: er is geen informatie over dit apparaat. <br>Goed: apparaat is niet opengebroken. <br>Slecht: apparaat is opengebroken. |Niet beschikbaar Goed Slecht |
| RowLastModifiedDateTimeUTC |De datum en tijd in UTC waarop deze specifieke MAM-apparaatstatus het laatst is gewijzigd in het datawarehouse. |11/23/2016 12:00:00 AM |

## <a name="mamplatforms"></a>MamPlatforms

De entiteit **MamPlatform** bevat de platformnamen en -typen waarop een MAM-app (Mobile Application Management) is geïnstalleerd.


|          Eigenschap          |                                    Beschrijving                                    |                         Voorbeeld                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        PlatformKey         |     De unieke id van het platform in het datawarehouse (surrogaatsleutel).      |                           123                           |
|          Platform          | De unieke id van de platform, vergelijkbaar met PlatformKey, maar het is een natuurlijke sleutel. |                           123                           |
|        PlatformName        |                                   De naam van het platform                                   | Niet beschikbaar <br>Geen <br>Windows <br>iOS <br>Android. |
| RowLastModifiedDateTimeUTC | De datum en tijd in UTC waarop dit platform het laatst is gewijzigd in het datawarehouse.  |                 11/23/2016 12:00:00 AM                  |

## <a name="managementagenttypes"></a>managementAgentTypes
De entiteit **ManagementAgentTypes** vertegenwoordigt de agents die worden gebruikt om een apparaat te beheren.

|         Eigenschap        |                                       Beschrijving                                       |
|:-----------------------:|:---------------------------------------------------------------------------------------:|
| ManagementAgentTypeID   | Unieke id van het type beheeragent.                                         |
| ManagementAgentTypeKey  | Unieke id van het type beheeragent in het datawarehouse - surrogaatsleutel. |
| ManagementAgentTypeName | Hiermee wordt aangegeven wat voor soort agent wordt gebruikt om het apparaat te beheren.                              |

### <a name="example"></a>Voorbeeld

| ManagementAgentTypeID |                Naam               |                                  Beschrijving                                 |
|:---------------------:|:---------------------------------:|:----------------------------------------------------------------------------:|
| 1                     | EAS                               | Het apparaat wordt beheerd via Exchange Active Sync                         |
| 2                     | MDM                               | Het apparaat wordt beheerd met behulp van een MDM-agent                                   |
| 3                     | EasMdm                            | Het apparaat wordt beheerd door zowel Exchange Active Sync als een MDM-agent        |
| 4                     | IntuneClient                      | Het apparaat wordt beheerd door de Intune-PC-agent                               |
| 5                     | EasIntuneClient                   | Het apparaat wordt beheerd door zowel Exchange Active Sync als de Intune-PC-agent |
| 8                     | ConfigManagerClient               | Het apparaat wordt beheerd door de System Center Configuration Manager-agent     |
| 10                    | ConfigurationManagerClientMdm     | Het apparaat wordt beheerd door Configuration Manager en MDM.                    |
| 11                    | ConfigurationManagerCLientMdmEas  | Het apparaat wordt beheerd door Configuration Manager, MDM en Exchange Active Sync.               |
| 16                    | Onbekend                           | Onbekend type beheeragent                                              |
| 32                    | Jamf                              | De apparaatkenmerken worden van Jamf opgehaald.                               |
| 64                    | GoogleCloudDevicePolicyController |  Het apparaat wordt beheerd door Google's CloudDPC.                                 |

## <a name="managementstates"></a>managementStates
De entiteit **ManagementState** verschaft informatie over de status van het apparaat. Informatie kan nuttig zijn wanneer er externe acties zijn toegepast, het apparaat is gekraakt of geroot.

|       Eigenschap      |                                     Beschrijving                                    |
|:-------------------:|:----------------------------------------------------------------------------------:|
| managementStateID   | Unieke id van de beheerstatus.                                       |
| managementStateKey  | Unieke id van de beheerstatus in het datawarehouse - surrogaatsleutel. |
| managementStateName | Hiermee wordt de status aangeduid van de externe actie die op dit apparaat is toegepast.                 |

### <a name="example"></a>Voorbeeld

| managementStateID |      Naam      |                                                   Beschrijving                                                   |
|:-----------------:|:--------------:|:---------------------------------------------------------------------------------------------------------------:|
| 0                 | Beheerd        | Beheerd zonder externe acties in behandeling.                                                                       |
| 1                 | RetirePending  | Er is een opdracht voor buiten gebruik stellen in behandeling voor het apparaat.                                                             |
| 2                 | RetireFailed   | De opdracht voor buiten gebruik stellen is mislukt op het apparaat.                                                                      |
| 3                 | WipePending    | Er is een wisopdracht in behandeling voor het apparaat.                                                               |
| 4                 | WipeFailed     | De wisopdracht is mislukt op het apparaat.                                                                        |
| 5                 | Niet in orde      | Status Niet in orde.                                                                                              |
| 6                 | DeletePending  | Er is een opdracht tot verwijderen in behandeling voor het apparaat.                                                             |
| 7                 | RetireIssued   | Er is een opdracht voor buiten gebruik stellen gegeven op het apparaat.                                                               |
| 8                 | WipeIssued     | Er is een wisopdracht gegeven.                                                                               |
| 9                 | WipeCanceled   | De wisopdracht is geannuleerd.                                                                               |
| 10                | RetireCanceled | De opdracht voor buiten gebruik stellen is geannuleerd.                                                                             |
| 11                | Discovered     | Het apparaat is onlangs gedetecteerd door Intune. Wanneer er voor de eerste keer wordt ingecheckt, krijgt het de status Beheerd. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates
De entiteit MobileAppInstallState vertegenwoordigt de installatiestatus van een mobiele toepassing nadat deze is toegewezen aan een groep apparaten, gebruikers of beide.

|       Eigenschap      |                        Beschrijving                       |
|:-------------------:|:--------------------------------------------------------:|
| AppInstallStateKey  | De unieke id van de installatiestatus van de app voor uw account. |
| AppInstallState     | Enum-waarde van de installatiestatus van de app.                     |
| AppInstallStateName | Naam van de installatiestatus van de app.                           |

## <a name="mobileappinstallstatuscounts"></a>mobileAppInstallStatusCounts
Vertegenwoordigt de installatiestatus van een mobiele app voor een bepaald doelapparaattype met behulp van Mobile Application Management via Microsoft Intune.

|      Eigenschap      |                                                          Beschrijving                                                          |
|:------------------:|:-----------------------------------------------------------------------------------------------------------------------------:|
| DateKey            | Sleutel van de datum waarop de installatiestatus van de app werd vastgelegd.                                                                     |
| AppKey             | Sleutel van de mobiele app die wordt gebruikt om een exemplaar van AppRevision te identificeren.                                                          |
| DeviceTypeKey      | Sleutel van het apparaattype dat is gekoppeld aan de mobiele toepassing.                                                              |
| AppInstallStateKey | Sleutel van de installatiestatus van de app die wordt gebruikt om een exemplaar van MobileAppInstallState te identificeren.                                         |
| ErrorCode          | De foutcode geretourneerd door het app-installatieprogramma, het mobiele platform of de service met betrekking tot de installatie van de app. |
| Aantal              | Totaalaantal.                                                                                                                  |

## <a name="ownertypes"></a>ownerTypes
Met de entiteit **ownerType** wordt aangegeven of een apparaat bedrijfseigendom of privé-eigendom is of dat niet bekend is wie de eigenaar is.

|    Eigenschap   |                                                                                     Beschrijving                                                                                    |           Voorbeeld          |
|:-------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------:|
| ownerTypeID   | Unieke id van het type eigenaar.                                                                                                                                               |                            |
| ownerTypeKey  | Unieke id van het type eigenaar in het datawarehouse - surrogaatsleutel.                                                                                                       |                            |
| ownerTypeName | Hiermee wordt het type eigenaar van de apparaten voorgesteld: Corporate - apparaat is eigendom van de onderneming.  Personal - apparaat is persoonlijk eigendom (BYOD).   Unknown - er is geen informatie over dit apparaat. | Zakelijke persoonlijke onbekend |

> [!Note]  
> Voor de `ownerTypeName` filter in AzureAD bij het maken van dynamische groepen voor apparaten, moet u de waarde `deviceOwnership` als `Company`. Zie voor meer informatie, [regels voor apparaten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="policies"></a>policies
De entiteit **Policy** bevat apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid. U kunt het beleid met MDM (Mobile Device Management) toewijzen aan een groep in uw onderneming.

|          Eigenschap          |                                                                       Beschrijving                                                                      |                Voorbeeld               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| PolicyKey                  | Een unieke sleutel voor het beleid in het datawarehouse.                                                                                              | 123                                  |
| PolicyId                   | Een unieke id van het beleid in het datawarehouse.                                                                                                 | b66bc706-ffff-7437-0340-032819502773 |
| PolicyName                 | De naam van het beleid.                                                                                                                                    | "Windows 10 Baseline"                |
| PolicyVersion              | De versie van het beleid. Wanneer het beleid wordt gewijzigd, wordt er een nieuwere versie gemaakt.                                                             | 1, 2, 3                              |
| IsDeleted                  | Geeft aan of de beleidsrecord is bijgewerkt.  Waar: het beleid heeft een nieuwe record met bijgewerkte velden.  Onwaar: de meest recente record voor het beleid. | Waar/onwaar                           |
| StartDateInclusiveUTC      | De datum en tijd in UTC waarop het beleid is gemaakt in het datawarehouse.                                                                              | 23-11-2016, 0:00                      |
| DeletedDateUTC             | De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar.                                                                                                   | 23-11-2016, 0:00                      |
| RowLastModifiedDateTimeUTC | De datum en tijd in UTC waarop het beleid het laatst is gewijzigd in het datawarehouse.                                                                        | 23-11-2016, 0:00                      |

## <a name="policydeviceactivities"></a>policyDeviceActivities
In de volgende tabel wordt het aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout per dag weergegeven. Het aantal weerspiegelt de gegevens per beleidstypeprofiel. Als een apparaat bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een apparaat twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de teller Geslaagd met één opgehoogd en wordt het apparaat in de foutstatus geplaatst. De entiteit **policyDeviceActivity** geeft voor de afgelopen 30 dagen aan hoeveel apparaten op een bepaalde dag een bepaalde status hebben.

|  Eigenschap |                                           Beschrijving                                           |        Voorbeeld        |
|:---------:|:-----------------------------------------------------------------------------------------------:|:---------------------:|
| DateKey   | De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. | 20160703              |
| In behandeling   | Aantal unieke apparaten met de status In behandeling.                                                    | 123                   |
| Geslaagd | Aantal unieke apparaten met de status Geslaagd.                                                    | 12                    |
| PolicyKey | Beleidssleutel, kan worden samengevoegd met Policy om de naam van het beleid op te halen.                                  | Windows 10-basislijn |
| Fout     | Aantal unieke apparaten met de status Fout.                                                      | 10                    |
| Mislukt    | Aantal unieke apparaten met de status Mislukt.                                                     | 2                     |

## <a name="policyplatformtypes"></a>policyPlatformTypes

|        Eigenschap        |                      Beschrijving                      |     Voorbeeld    |
|:----------------------:|:-----------------------------------------------------:|:--------------:|
| PolicyPlatformTypeKey  | De unieke sleutel voor het platformtype van het beleid.        | 20170519       |
| PolicyPlatformTypeId   | De unieke id voor het platformtype van het beleid. | 1              |
| PolicyPlatformTypeName | De naam van het platformtype van het beleid.              | AndroidForWork |

## <a name="policytypeactivities"></a>policyTypeActivities
De entiteit **PolicyTypeActivity** bevat het cumulatieve aantal apparaten met de status Geslaagd, In behandeling, Mislukt of Fout. Deze statuswaarden verwijzen naar een apparaatconfiguratieprofiel, app-configuratieprofiel of nalevingsbeleid per dag.

|    Eigenschap   |                                          Beschrijving                                          |           Voorbeeld           |
|:-------------:|:---------------------------------------------------------------------------------------------:|:---------------------------:|
| DateKey       | De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. | 20160703                    |
| PolicyKey     | Beleidssleutel, kan worden samengevoegd met Policy om de naam van het beleid op te halen.                                | Windows 10 baseline         |
| PolicyTypeKey | Het type beleidssleutel, kan worden samengevoegd met PolicyType om de naam van het beleidstype op te halen.             | Windows 10-nalevingsbeleid configureren |
| In behandeling       | Aantal unieke apparaten met de status In behandeling.                                                    | 123                         |
| Geslaagd     | Aantal unieke apparaten met de status Geslaagd.                                                    | 12                          |
| Fout         | Aantal unieke apparaten met de status Fout.                                                      | 10                          |
| Mislukt        | Aantal unieke apparaten met de status Mislukt.                                                     | 2                           |

## <a name="policytypes"></a>policyTypes
De entiteit **PolicyType** bevat typen apparaatconfiguratieprofielen, app-configuratieprofielen en nalevingsbeleid. U kunt het beleid met MDM (Mobile Device Management) toewijzen aan een groep in uw onderneming.

|    Eigenschap    |                       Beschrijving                      |            Voorbeeld            |
|:--------------:|:------------------------------------------------------:|:-----------------------------:|
| PolicyTypeId   | Een unieke id van het beleid in het bronsysteem.  | 123                           |
| PolicyTypeKey  | Een unieke id van het beleid in het datawarehouse. | 1                             |
| PolicyTypeName | De naam van het beleidstype                               | Nalevingsbeleid van Windows 10. |

## <a name="policyuseractivities"></a>policyUserActivities
In de volgende tabel wordt het aantal gebruikers met de status Geslaagd, In behandeling, Mislukt of Fout per dag weergegeven. Het aantal weerspiegelt de gegevens per beleidstypeprofiel. Als een gebruiker bijvoorbeeld voor alle toegewezen beleidsregels de status Geslaagd heeft, wordt de teller voor die status met één opgehoogd voor die dag. Als aan een gebruiker twee profielen zijn toegewezen, één met de status Geslaagd en het andere profiel met de status Fout, wordt de gebruiker in de foutstatus geplaatst. De entiteit **PolicyUserActivity** geeft voor de afgelopen 30 dagen aan hoeveel gebruikers op een bepaalde dag een bepaalde status hebben.

|  Eigenschap |                                          Beschrijving                                          |       Voorbeeld       |
|:---------:|:---------------------------------------------------------------------------------------------:|:-------------------:|
| DateKey   | De datum waarop het inchecken van het apparaatconfiguratieprofiel is vastgelegd in het datawarehouse. | 20160703            |
| In behandeling   | Aantal unieke apparaten met de status In behandeling.                                                    | 123                 |
| Geslaagd | Aantal unieke apparaten met de status Geslaagd.                                                    | 12                  |
| PolicyKey | Beleidssleutel, kan worden samengevoegd met Policy om de naam van het beleid op te halen.                                | Windows 10 baseline |
| Fout     | Aantal unieke apparaten met de status Fout.                                                      | 10                  |

## <a name="termsandconditions"></a>termsAndConditions
De entiteit **termsAndConditions** vertegenwoordigt de metagegevens en inhoud van een set Gebruikersvoorwaarden. De inhoud van de gebruikersvoorwaarden wordt aan gebruikers weergegeven bij hun eerste poging tot inschrijven bij Intune en vervolgens na bewerkingen waarvoor een beheerder re-acceptatie vereist. Op deze manier kunnen beheerders bepalingen communiceren waarmee een gebruiker moet instemmen om apparaten in te schrijven bij Intune.

|    Eigenschap        |    Beschrijving    |    Voorbeeld        |
|----------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------|
|    termsAndConditionsKey    |    Een sleutel die overeenkomt met een vermelding in de verzameling 'userTermsAndConditionsAcceptances'    |    123    |
|    termsAndCondidionsId    |    De id voor deze gebruikersvoorwaardenvermelding    |    276edcb7-7440-4339-b6c5-8b6fc556fee6    |
|    termsAndConditionsVersion    |    De versie van deze gebruikersvoorwaardenvermelding    |    1    |
|    name    |    De naam van deze gebruikersvoorwaardenvermelding.        |    Intune-gebruiksvoorwaarden     |
|    description    |    De beschrijving voor deze voorwaarden.     |         |
|    title    |    De titel voor deze voorwaarden.     |    Bedrijfsbeleid voor apparaatbeheer        |
|    summaryOfTerms    |    De samenvatting van de voorwaarden die aan de gebruiker worden gepresenteerd.     |    Ik ga akkoord met de voorwaarden.    |
|    termsAndConditionsBodyText    |    De hoofdtekst voor deze voorwaarden.       |    *Apparaatversleuteling*: pincode van 6 cijfers afdwingen    |
|    isDeleted    |    De waarde True of false om aan te duiden of deze waarde is verwijderd.     |    False    |
|    startDateInclusiveUTC    |    De begindatum van deze voorwaarden.     |    23-08-2018, 4:01:34 AM    |
|    endDateEclusiveUTC    |    De einddatum van deze voorwaarden.     |    31-12-9999 12:00:00 AM    |

## <a name="userdeviceassociations"></a>userDeviceAssociations
De entiteit **UserDeviceAssociation** bevat gebruikersapparaatkoppelingen in uw organisatie.

|        Naam        |                                             Beschrijving                                            |     Voorbeeld     |
|:------------------:|:--------------------------------------------------------------------------------------------------:|:---------------:|
| UserKey            | Een unieke id van gebruiker in het datawarehouse.   (surrogaatsleutel).                            | 123             |
| DeviceKey          | Een unieke id van het apparaat in het datawarehouse.                                             | 123             |
| CreatedDateTimeUTC | De datum en tijd wanneer de gebruikersapparaatkoppeling is gemaakt. Hiervoor wordt de UTC-notatie gebruikt.                     | 23-11-2016, 0:00 |
| IsDeleted          | Geeft aan dat de gebruiker het apparaat heeft uitgeschreven en dat de koppeling niet meer actueel is. | Waar/onwaar      |
| EndedDateTimeUTC   | De datum en tijd in UTC waarop IsDeleted is gewijzigd in Waar.                                               | 23-6-2017, 0:00  |

## <a name="users"></a>gebruikers
De entiteit **user** bevat een lijst van alle Azure Active Directory-gebruikers (Azure AD) met toegewezen licenties in uw onderneming.

De entiteitverzameling **user** bevat gebruikersgegevens. Deze records bevatten gebruikersstatussen gedurende de periode van gegevensverzameling, ook als de gebruiker is verwijderd. Een gebruiker kan bijvoorbeeld worden toegevoegd aan Intune en vervolgens ergens gedurende de afgelopen maand zijn verwijderd. Ook al is deze gebruiker niet aanwezig op het moment dat het rapport wordt gegenereerd, toch zijn de gebruiker en de status aanwezig in de gegevens van de vorige maand. U kunt een rapport maken dat de duur van de historische aanwezigheid van de gebruiker in uw gegevens weergeeft.

|          Eigenschap          |                                                                                                           Beschrijving                                                                                                          |                Voorbeeld               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | De unieke id van de gebruiker in het datawarehouse - surrogaatsleutel.                                                                                                                                                         | 123                                  |
| UserId                     | De unieke id van de gebruiker, vergelijkbaar met UserKey, maar dit is een natuurlijke sleutel.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | Het e-mailadres van de gebruiker.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | De UPN (user principal name) van de gebruiker.                                                                                                                                                                                               | John@constoso.com                    |
| DisplayName                | De weergavenaam van de gebruiker.                                                                                                                                                                                                      | Jan                                 |
| IntuneLicensed             | Geeft aan of deze gebruiker een licentie heeft voor Intune                                                                                                                                                                              | Waar/onwaar                           |
| IsDeleted                  | Geeft aan of alle licenties van de gebruiker zijn verlopen en of de gebruiker daarom uit Intune werd verwijderd. Deze markering verandert niet voor één record. In plaats daarvan wordt er een nieuwe record gemaakt voor een nieuwe gebruikersstatus. | Waar/onwaar                           |
| RowLastModifiedDateTimeUTC | De datum en tijd in UTC waarop de record het laatst is gewijzigd in het datawarehouse                                                                                                                                                 | 23-11-2016, 0:00                      |

## <a name="usertermsandconditionsacceptances"></a>userTermsAndConditionsAcceptances
De entiteit **userTermsAndConditionsAcceptance** vertegenwoordigt de acceptatiestatus van een bepaalde set voorwaarden door een bepaalde gebruiker. Gebruikers moeten de meest recente versie van de voorwaarden accepteren om toegang te behouden tot de bedrijfsportal.

|    Eigenschap    |    Beschrijving    |    Voorbeeld    |
|-------------------------------|--------------------------------------------------------------------------------|----------------------------|
|    dateKey    |    Een sleutel die overeenkomt met de datumwaarden in de verzameling 'dates'.     |    20180823    |
|    userKey    |    Een gebruikerssleutel toegewezen aan een gebruiker in de verzameling 'users'.     |    20000    |
|    termsAndConditionsKey    |    Een sleutel die overeenkomt met een vermelding in de verzameling 'termsAndConditions'    |    1    |
|    acceptedDateTimeUTC    |    De tijd dat de gebruiker deze voorwaarden heeft geaccepteerd    |    23-08-2018, 4:01:34 AM    |
|    lastModifiedDateTimeUTC    |    De laatste keer dat deze vermelding is gewijzigd.     |    23-08-2018, 4:01:34 AM    |

## <a name="vppprogramtypes"></a>vppProgramTypes 
De entiteit **vppProgramTypes** bevat een lijst van mogelijke VPP-programmatypen voor een app.

|      Eigenschap      |          Beschrijving         |
|:------------------:|:----------------------------:|
| VppProgramTypeID   | De id voor het type.           |
| VppProgramTypeKey  | De surrogaatsleutel voor de sleutel. |
| VppProgramTypeName | Het type VPP-programma.          |

### <a name="example"></a>Voorbeeld

|             VppProgramID             |         Naam        | Beschrijving                |
|:------------------------------------:|:-------------------:|----------------------------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft           | Het VPP-programma van Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Nog niet beschikbaar | Standaardwaarde, geen VPP.   |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple               | VPP-programma van Apple.     |

## <a name="next-steps"></a>Volgende stappen

Zie het artikel [Datawarehouse-gegevensmodel](https://docs.microsoft.com/intune/reports-ref-data-model) voor meer informatie over het Intune-datawarehouse.

