---
title: Apparaten - Intune-datawarehouse
titleSuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Devices van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36407bda1f74d0c4601f78cedc2af5426e944fee
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72503414"
---
# <a name="reference-for-devices-entities"></a>Informatie voor apparaatentiteiten

De categorie **Apparaten** bevat entiteiten voor mobiele apparaten waarmee gegevens worden bijgehouden, zoals:

- Apparaattype
- Apparaatregistratie en registratiestatus
- Apparaateigendom
- Apparaatbeheerstatus
- Apparaatlidmaatschap voor Azure AD-status
- Status van inschrijving
- Historische informatie over het apparaat
- Inventarisatie van apps op het apparaat

## <a name="devicetypes"></a>deviceTypes

De entiteit **deviceTypes** vertegenwoordigt het apparaattype waarnaar wordt verwezen door andere datawarehouse-entiteiten. Met het apparaattype wordt doorgaans het model, de fabrikant of een combinatie van beide beschreven.

| Eigenschap  | Beschrijving |
|---------|------------|
| deviceTypeID |Unieke id van het apparaattype |
| deviceTypeKey |Unieke id van het apparaattype in het datawarehouse - surrogaatsleutel |
| deviceTypeName |Apparaattype |

### <a name="example"></a>Voorbeeld

| deviceTypeID  | Naam | Beschrijving |
|---------|------------|--------|
| 0 |Desktop |Windows Desktop-apparaat |
| 1 |WindowsRT |WindowsRT-apparaat |
| 2 |WinMO6 |Windows Mobile 6.0-apparaat |
| 3 |Nokia |Nokia-apparaat |
| 4 |WindowsPhone |Windows Phone-apparaat |
| 5 |Mac |Mac-apparaat |
| 6 |WinCE |Windows CE-apparaat |
| 7 |WinEmbedded |Windows Embedded-apparaat |
| 8 |IPhone |iPhone-apparaat |
| 9 |IPad |iPad-apparaat |
| 10 |IPod |iPod-apparaat |
| 11 |Android |Android-apparaat dat wordt beheerd met Apparaatbeheer |
| 12 |ISocConsumer |iSoc Consumer-apparaat |
| 14 |MacMDM |Mac OS X-apparaat dat wordt beheerd met de ingebouwde MDM-agent |
| 15 |HoloLens |HoloLens-apparaat |
| 16 |SurfaceHub |Surface Hub-apparaat |
| 17 |AndroidForWork |Android-apparaat dat wordt beheerd met de Android-profieleigenaar |
| 100 |Blackberry |Blackberry-apparaat |
| 101 |Palm |Palm-apparaat |
| 255 |Onbekend |Onbekend apparaattype |

## <a name="enrollmentactivities"></a>enrollmentActivities 
De entiteit **enrollmentActivity** geeft de activiteit van een apparaatinschrijving aan.

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
De entiteit **enrollmentEventStatus** geeft het resultaat van een apparaatinschrijving aan.

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
## <a name="ownertypes"></a>ownerTypes

Met de entiteit **enrollmentType** wordt aangegeven of een apparaat bedrijfseigendom of privé-eigendom is of dat het niet bekend is wie de eigenaar is.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| ownerTypeID |Unieke id van het type eigenaar. | |
| ownerTypeKey |Unieke id van het type eigenaar in het datawarehouse - surrogaatsleutel. | |
| ownerTypeName |Vertegenwoordigt het eigenaartype van de apparaten:  <br>Corporate - apparaat is bedrijfseigendom. <br>Personal - apparaat is persoonlijk eigendom (BYOD).  <br>Unknown - er is geen informatie over dit apparaat. |Corporate Personal Unknown |

> [!Note]  
> Bij het maken van dynamische groepen voor apparaten moet u voor de `ownerTypeName` in AzureAD de filterwaarde `deviceOwnership` instellen als `Company`. Zie [Regels voor apparaten](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) voor meer informatie. 

## <a name="managementstates"></a>managementStates

De entiteit **managementStates** verschaft informatie over de status van het apparaat. Informatie kan nuttig zijn wanneer er externe acties zijn toegepast, het apparaat is gekraakt of geroot.

| Eigenschap  | Beschrijving |
|---------|------------|
| managementStateID | Unieke id van de beheerstatus. |
| managementStateKey | Unieke id van de beheerstatus in het datawarehouse - surrogaatsleutel. |
| managementStateName | Hiermee wordt de status aangeduid van de externe actie die op dit apparaat is toegepast. |

### <a name="example"></a>Voorbeeld

| managementStateID  | Naam | Beschrijving |
|---------|------------|--------|
| 0 |Beheerd | Beheerd zonder externe acties in behandeling. |
| 1 |RetirePending | Er is een opdracht voor buiten gebruik stellen in behandeling voor het apparaat. |
| 2 |RetireFailed | De opdracht voor buiten gebruik stellen is mislukt op het apparaat. |
| 3 |WipePending | Er is een wisopdracht in behandeling voor het apparaat. |
| 4 |WipeFailed | De wisopdracht is mislukt op het apparaat. |
| 5 |Niet in orde | Status Niet in orde. |
| 6 |DeletePending | Er is een opdracht tot verwijderen in behandeling voor het apparaat. |
| 7 |RetireIssued | Er is een opdracht voor buiten gebruik stellen gegeven op het apparaat. |
| 8 |WipeIssued | Er is een wisopdracht gegeven. |
| 9 |WipeCanceled | De wisopdracht is geannuleerd. |
| 10 |RetireCanceled | De opdracht voor buiten gebruik stellen is geannuleerd. |
| 11 |Discovered | Het apparaat is onlangs gedetecteerd door Intune. Wanneer er voor de eerste keer wordt ingecheckt, krijgt het de status Beheerd. |

## <a name="managementagenttypes"></a>managementAgentTypes

De entiteit **managementAgentTypes** vertegenwoordigt de agents die worden gebruikt om een apparaat te beheren.

| Eigenschap  | Beschrijving |
|---------|------------|
| managementAgentTypeID | Unieke id van het type beheeragent. |
| managementAgentTypeKey | Unieke id van het type beheeragent in het datawarehouse - surrogaatsleutel. |
| managementAgentTypeName |Hiermee wordt aangegeven wat voor soort agent wordt gebruikt om het apparaat te beheren. |

### <a name="example"></a>Voorbeeld

| ManagementAgentTypeID  | Naam | Beschrijving |
|---------|------------|--------|
| 1 |EAS | Het apparaat wordt beheerd via Exchange Active Sync |
| 2 |MDM | Het apparaat wordt beheerd met behulp van een MDM-agent |
| 3 |EasMdm | Het apparaat wordt beheerd door zowel Exchange Active Sync als een MDM-agent |
| 4 |IntuneClient | Het apparaat wordt beheerd door de Intune-PC-agent |
| 5 |EasIntuneClient | Het apparaat wordt beheerd door zowel Exchange Active Sync als de Intune-PC-agent |
| 8 |ConfigManagerClient | Het apparaat wordt beheerd door de System Center Configuration Manager-agent |
| 16 |Onbekend | Onbekend type beheeragent |

## <a name="devices"></a>devices

Met de entiteit **devices** worden alle geregistreerde apparaten voor beheer en de bijbehorende eigenschappen weergegeven.

|          Eigenschap          |                                                                                       Beschrijving                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| deviceKey                  | Unieke id van het apparaat in het datawarehouse - surrogaatsleutel.                                                                                                               |
| deviceId                   | Unieke id van het apparaat.                                                                                                                                                     |
| deviceName                 | Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten. |
| deviceTypeKey              | Sleutel van het kenmerk voor het apparaattype voor dit apparaat.                                                                                                                                    |
| deviceRegistrationState    | Sleutel van het kenmerk voor de clientregistratiestatus voor dit apparaat.                                                                                                                      |
| ownerTypeKey               | Sleutel van het kenmerk voor het type eigenaar voor dit apparaat: zakelijk, persoonlijk of onbekend.                                                                                                    |
| enrolledDateTime           | De datum en tijd waarop het apparaat is ingeschreven.                                                                                                                                         |
| lastSyncDateTime           | Laatste bekende keer dat een apparaat is ingecheckt bij Intune.                                                                                                                                              |
| managementAgentKey         | Sleutel van de beheeragent die is gekoppeld aan dit apparaat.                                                                                                                             |
| managementStateKey         | Sleutel van de aan dit apparaat gekoppelde beheerstatus waarmee de laatste status van een externe actie wordt aangegeven of dat het apparaat is gekraakt of geroot.                                                |
| azureADDeviceId            | De Azure-apparaat-id voor dit apparaat.                                                                                                                                                  |
| azureADRegistered          | Of het apparaat is geregistreerd bij Azure Active Directory.                                                                                                                             |
| deviceCategoryKey          | Sleutel van de categorie die is gekoppeld aan dit apparaat.                                                                                                                                     |
| deviceEnrollmentType       | Sleutel van het registratietype dat is gekoppeld aan dit apparaat (geeft de registratiemethode aan).                                                                                             |
| complianceStateKey         | Sleutel van de Nalevingsstatus die is gekoppeld aan dit apparaat.                                                                                                                             |
| osVersion                  | Versie van het besturingssysteem van het apparaat.                                                                                                                                                |
| easDeviceId                | De Exchange ActiveSync-id van het apparaat.                                                                                                                                                  |
| serialNumber               | SerialNumber                                                                                                                                                                           |
| userId                     | De unieke id voor de gebruiker die is gekoppeld aan het apparaat.                                                                                                                           |
| rowLastModifiedDateTimeUTC | De datum en tijd in UTC waarop dit apparaat het laatst is gewijzigd in het datawarehouse.                                                                                                       |
| manufacturer               | Fabrikant van het apparaat                                                                                                                                                             |
| model                      | Model van het apparaat                                                                                                                                                                    |
| operatingSystem            | Het besturingssysteem van het apparaat. Windows, iOS, enzovoort.                                                                                                                                   |
| isDeleted                  | Binaire code om weer te geven of het apparaat is verwijderd of niet.                                                                                                                                 |
| androidSecurityPatchLevel  | Niveau Android-beveiligingspatch                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | De supervisiestatus van het apparaat                                                                                                                                                               |
| freeStorageSpaceInBytes    | Beschikbare opslag in bytes.                                                                                                                                                                 |
| totalStorageSpaceInBytes   | Totale opslag in bytes.                                                                                                                                                                |
| encryptionState            | De versleutelingsstatus van het apparaat.                                                                                                                                                      |
| subscriberCarrier          | Provider van abonnee van het apparaat                                                                                                                                                       |
| phoneNumber                | Telefoonnummer van het apparaat                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| cellularTechnology         | Mobiele telefoontechnologie van het apparaat                                                                                                                                                    |
| WiFiMacAddress             | MAC-adres Wi-Fi                                                                                                                                                                              |
| ICCD                       | Geïntegreerde circuit kaart-id                                                                                                                                                     |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

De entiteit **devicePropertyHistory** heeft dezelfde eigenschappen als de apparatentabel en dagelijkse momentopnamen van elke apparaatrecord per dag voor de afgelopen 90 dagen. De kolom DateKey geeft de dag voor elke rij aan.

|          Eigenschap          |                                                                                      Beschrijving                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| dateKey                    | Verwijzing naar datumtabel waarmee de dag wordt aangegeven.                                                                                                                                          |
| deviceKey                  | Unieke id van het apparaat in het datawarehouse - surrogaatsleutel. Dit is een verwijzing naar de apparaattabel die de Intune-apparaat-id bevat.                               |
| deviceName                 | Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten. |
| deviceRegistrationStateKey | Sleutel van het kenmerk voor de apparaatregistratiestatus voor dit apparaat.                                                                                                                    |
| ownerTypeKey               | Sleutel van het kenmerk voor het type eigenaar voor dit apparaat: zakelijk, persoonlijk of onbekend.                                                                                                  |
| managementStateKey         | Sleutel van de aan dit apparaat gekoppelde beheerstatus, waarmee de laatste status van een externe actie wordt aangegeven of dat het apparaat is gekraakt of geroot.                                                |
| azureADRegistered          | Of het apparaat is geregistreerd bij Azure Active Directory.                                                                                                                             |
| complianceStateKey         | Een sleutel voor de ComplianceState.                                                                                                                                                            |
| OSVersion                  | Versie besturingssysteem.                                                                                                                                                                          |
| jailBroken                 | Of het apparaat jailbroken of geroot is.                                                                                                                                         |
| deviceCategoryKey          | Sleutel van het kenmerk voor de apparaatcategorie voor dit apparaat. 

