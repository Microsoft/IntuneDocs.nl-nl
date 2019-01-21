---
title: Apparaten - Intune-datawarehouse
titlesuffix: Microsoft Intune
description: Naslagonderwerp voor de categorie Devices van entiteitverzamelingen in de Intune-datawarehouse-API.
keywords: Intune-datawarehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 3993cb4e7ccbc04ccc1d341a9bd72594948f3262
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297516"
---
# <a name="reference-for-devices-entities"></a>Informatie voor apparaatentiteiten

De categorie **Devices** bevat entiteiten voor mobiele apparaten waarmee gegevens worden bijgehouden, zoals:

  -  Apparaattype
  -  Apparaatregistratie en registratiestatus
  -  Apparaateigendom
  -  Apparaatbeheerstatus
  -  Apparaatlidmaatschap voor Azure AD-status
  -  Status van inschrijving
  -  Historische informatie over het apparaat
  -  Inventarisatie van apps op het apparaat

## <a name="devicetypes"></a>DeviceTypes

De entiteit **DeviceTypes** vertegenwoordigt het apparaattype waarnaar wordt verwezen door andere datawarehouse-entiteiten. Met het apparaattype wordt doorgaans het model, de fabrikant of een combinatie van beide beschreven.

| Eigenschap  | Beschrijving |
|---------|------------|
| DeviceTypeID |Unieke id van het apparaattype |
| DeviceTypeKey |Unieke id van het apparaattype in het datawarehouse - surrogaatsleutel |
| DeviceTypeName |Apparaattype |

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
| 15 |HoloLens |Holo Lens-apparaat |
| 16 |SurfaceHub |Surface Hub-apparaat |
| 17 |AndroidForWork |Android-apparaat dat wordt beheerd met de Android-profieleigenaar |
| 100 |Blackberry |Blackberry-apparaat |
| 101 |Palm |Palm-apparaat |
| 255 |Onbekend |Onbekend apparaattype |

## <a name="clientregistrationstatetypes"></a>ClientRegistrationStateTypes

De entiteit **ClientRegistrationStateTypes** vertegenwoordigt het registratietype waarnaar wordt verwezen door andere datawarehousetabellen.

| Eigenschap  | Beschrijving |
|---------|------------|
| clientRegisterationStateID |Unieke id voor registratiestatus |
| clientRegisterationStateKey |Unieke id van de registratiestatus in het datawarehouse - surrogaatsleutel |
| clientRegisterationStateName |Registratiestatus |

### <a name="example"></a>Voorbeeld

| ClientRegisterationStateID  | Naam | Beschrijving |
|---------|------------|--------|
| 0 |NotRegistered |Niet geregistreerd |
| 1 |SMSIDConflict |Sms-id-conflict |
| 2 |Geregistreerd |Geregistreerd |
| 3 |Revoked |Status betekent dat de client is geblokkeerd door de IT-beheerder en dat de blokkering voor de client kan worden opgeheven. Een apparaat kan ook de status Ingetrokken hebben nadat deze is gewist of buiten gebruik is gesteld. |
| 4 |KeyConflict |Sleutelconflict |
| 5 |ApprovalPending |Goedkeuring in behandeling |
| 6 |ResetCert |Certificaat opnieuw instellen |
| 7 |NotRegisteredPendingEnrollment |Niet geregistreerde, in behandeling zijnde registratie |
| 8 |Onbekend |Onbekende status |

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
| count                         | Het totale aantal inschrijvingsactiviteiten die overeenkomen met de bovenstaande classificaties.  |

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
| UserValidation                  | De gebruiker kan worden gevalideerd. (De gebruiker bestaat niet, ontbrekende licentie)                                           |
| DeviceNotSupported              | Het apparaat wordt niet ondersteund voor Mobile Device Management.                                                         |
| InMaintenance                   | Het account bevindt zich in de onderhoudsmodus.                                                                                    |
| BadRequest                      | De client heeft een aanvraag verzonden die niet wordt begrepen/ondersteund door de service.                                        |
| FeatureNotSupported             | Een of meer functies die worden gebruikt door deze inschrijving, worden niet ondersteund voor dit account.                                        |
| EnrollmentRestrictionsEnforced  | De inschrijving wordt geblokkeerd door de inschrijvingsbeperkingen die door de beheerder zijn geconfigureerd.                                          |
| ClientDisconnected              | Er is een time-out voor de client opgetreden of de inschrijving is afgebroken door de eindgebruiker.                                                        |
| UserAbandonment                 | De inschrijving is afgebroken door de eindgebruiker. (Onboarding is gestart door de eindgebruiker, maar kon niet tijdig worden voltooid)  |

## <a name="enrollmentfailurereasons"></a>enrollmentFailureReasons  
De entiteit **EnrollmentFailureReason** geeft een meer gedetailleerde reden voor een apparaatinschrijvingsfout binnen een bepaalde foutcategorie.  

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
| EnrollmentOnboardingIssue        | Intune MDM-instantie (Mobile Device Management) is nog niet geconfigureerd.                                                                                                                                 |
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

## <a name="enrollmenttypes"></a>EnrollmentTypes

De entiteit **EnrollmentTypes** geeft aan hoe een apparaat is geregistreerd. Met het registratietype wordt de registratiemethode vastgelegd. In de voorbeelden ziet u de verschillende registratietypen en hun betekenis.

| Eigenschap  | Beschrijving |
|---------|------------|
| managementStateID |Unieke id van de beheerstatus. |
| managementStateKey |Unieke id van de beheerstatus in het datawarehouse - surrogaatsleutel. |
| managementStateName |Hiermee wordt de status aangeduid van de externe actie die op dit apparaat is toegepast. |

### <a name="example"></a>Voorbeeld

| enrollmentTypeID  | Naam | Beschrijving |
|---------|------------|--------|
| 0 |Onbekend |Registratietype is niet verzameld |
| 1 |UserEnrollment |Door de gebruiker geïnitieerde registratie |
| 2 |DeviceEnrollment |Apparaatregistratie met profiel zonder gebruiker |
| 3 |DeviceEnrollmentWithUDA |Apparaatregistratie met UDA-profiel. |
| 4 |AzureDomainJoined |Door de gebruiker geïnitieerde apparaatregistratie via Azure Active Directory |
| 5 |UserEnrollmentWithServiceAccount |Door de gebruiker geïnitieerde registratie via serviceaccount |
| 6 |DepDeviceEnrollment |DEP-apparaatregistratie met profiel zonder gebruiker |
| 7 |DepDeviceEnrollmentWithUDA |DEP-apparaatregistratie met UDA-profiel |
| 8 |AutoEnrollment |Gecombineerde DRS- en MDM-registratie voor BYOD-scenario |

## <a name="ownertypes"></a>OwnerTypes

Met de entiteit **EnrollmentTypes** wordt aangegeven of een apparaat bedrijfseigendom of privé-eigendom is of dat het niet bekend is wie de eigenaar is.

| Eigenschap  | Beschrijving | Voorbeeld |
|---------|------------|--------|
| ownerTypeID |Unieke id van het type eigenaar. | |
| ownerTypeKey |Unieke id van het type eigenaar in het datawarehouse - surrogaatsleutel. | |
| ownerTypeName |Vertegenwoordigt het eigenaartype van de apparaten:  <br>Company - apparaat is bedrijfseigendom. <br>Personal - apparaat is persoonlijk eigendom (BYOD).  <br>Unknown - er is geen informatie over dit apparaat. |Company Personal Unknown |

## <a name="mdmstatuses"></a>MdmStatuses

Met de entiteit **MdmStatuses** wordt de nalevingsstatus van het apparaat aangegeven.

| Eigenschap  | Beschrijving |
|---------|------------|
| MdmStatusID |Unieke id van de nalevingsstatus |
| MdmStatusKey |Unieke id van de nalevingsstatus in het datawarehouse - surrogaatsleutel | 
| ComplianceStatus |Nalevingsstatus van het apparaat; moet een van de waarden uit de onderstaande tabel hebben | 


### <a name="example"></a>Voorbeeld

| MdmStatusID  | ComplianceStatus | Beschrijving |
|---------|------------|--------|
| 0 |Onbekend |De nalevingsstatus van het apparaat is onbekend. |
| 1 |Compliant |Het apparaat voldoet aan het nalevingsbeleid. |
| 2 |Noncompliant |Het apparaat is niet compatibel. |
| 3 |Conflict |De nalevingsstatus van het apparaat heeft een conflict veroorzaakt. |
| 4 |Fout |Er is een fout opgetreden bij het lezen van de nalevingsstatus van het apparaat. |


## <a name="managementstates"></a>ManagementStates

De entiteit **ManagementStates** verschaft informatie over de status van het apparaat. Informatie kan nuttig zijn wanneer er externe acties zijn toegepast, het apparaat is gekraakt of geroot.

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

## <a name="workplacejoinstatetypes"></a>WorkPlaceJoinStateTypes

De entiteit **WorkPlaceJoinStateTypes** vertegenwoordigt de Active Directory Workplace Join-status van het apparaat.  De registratiewerkstroom kan een of meer certificaten gebruiken om te controleren of verifiëren. Wanneer een apparaat voor WorkPlace wordt geregistreerd, worden deze certificaten gebruikt om het apparaat en de gebruiker te valideren. De uitgifte van certificaten is beschikbaar via een SCEP-server (Simple Certificate Enrollment Point). De waarden in de entiteit geven de verschillende statussen aan die een apparaat kan hebben terwijl het dit proces doorloopt. Sommige van deze statussen omvatten het mislukken van toevoeging aan WorkPlace doordat de uitgifte van een vereist certificaat (van een SCEP-server) mislukt. Als een apparaat deze werkstroom nooit heeft doorlopen, wordt de waarde ingesteld op Onbekend.

| Eigenschap  | Beschrijving |
|---------|------------|
| WorkPlaceJoinStateID | Unieke id van de status van toevoeging aan de werkplek |
| WorkPlaceJoinStateKey | Unieke id van de status van toevoeging aan de werkplek in het datawarehouse - surrogaatsleutel |
| WorkPlaceJoinStateName | Status van toevoeging aan de werkplek |

### <a name="example"></a>Voorbeeld

| workPlaceJoinStateID  | Naam | Beschrijving |
|---------|------------|--------|
| 0 |Onbekend |Als een apparaat niet is toegevoegd aan een werkplek, heeft het de status Onbekend |
| 1 |Geslaagd |Is toegevoegd aan de werkplek |
| 2 |FailureToGetScepMetadata |Ophalen van SCEP-metagegevens is mislukt |
| 3 |FailureToGetScepChallenge |Ophalen van SCEP-vraag is mislukt |
| 4 |DeviceFailureToInstallScepCommand |Installatie van SCEP-opdracht op apparaat is mislukt |
| 5 |DeviceFailureToGetCertificate |Apparaat kan certificaat niet ophalen via SCEP |
| 6 |DeviceScepPending |Status In behandeling; apparaat voert SCEP nog uit |
| 7 |DeviceScepFailed |Apparaat kan certificaat niet installeren via SCEP |
| 8 |AADValidationFailed |Kan niet valideren of apparaat bestaat in AAD |

## <a name="managementagenttypes"></a>ManagementAgentTypes

De entiteit **ManagementAgentTypes** vertegenwoordigt de agents die worden gebruikt om een apparaat te beheren.

| Eigenschap  | Beschrijving |
|---------|------------|
| ManagementAgentTypeID | Unieke id van het type beheeragent. |
| ManagementAgentTypeKey | Unieke id van het type beheeragent in het datawarehouse - surrogaatsleutel. |
| ManagementAgentTypeName |Hiermee wordt aangegeven wat voor soort agent wordt gebruikt om het apparaat te beheren. |

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

## <a name="devices"></a>Apparaten

Met de entiteit **Devices** worden alle geregistreerde apparaten voor beheer en de bijbehorende eigenschappen weergegeven.

| Eigenschap  | Beschrijving |
|---------|------------|
| DeviceKey | Unieke id van het apparaat in het datawarehouse - surrogaatsleutel. |
| DeviceId | Unieke id van het apparaat. |
| DeviceName | Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten. |
| DeviceTypeKey | Sleutel van het kenmerk voor het apparaattype voor dit apparaat. |
| ClientRegisterationStateKey | Sleutel van het kenmerk voor de clientregistratiestatus voor dit apparaat. |
| OwnerTypeKey | Sleutel van het kenmerk voor het type eigenaar voor dit apparaat: zakelijk, persoonlijk of onbekend. |
| objectSourceKey | Negeer deze kolom. |
| CreatedDate | Datum waarop het apparaat is geregistreerd. |
| LastContact | Laatste bekende keer dat een apparaat is ingecheckt met Intune. |
| LastContactNotification | Laatste keer dat Intune heeft gemeld dat het apparaat moest worden ingecheckt met Intune. |
| LastContactWorkplaceJoin | De tijdstempel die de laatste bekende Workplace Join-status voor dit apparaat aangeeft. |
| ManagementAgentKey | Sleutel van de beheeragent die is gekoppeld aan dit apparaat. |
| ManagementStateKey | Sleutel van de aan dit apparaat gekoppelde beheerstatus waarmee de laatste status van een externe actie wordt aangegeven of dat het apparaat is gekraakt of geroot. |
| ReferenceId | De apparaat-id in Azure Active Directory. |
| WorkPlaceJoinStateKey | Sleutel van de status van de werkplektoevoeging van dit apparaat. |
| CategoryId | Negeer deze kolom. |
| EnrollmentTypeKey | Sleutel van het registratietype dat is gekoppeld aan dit apparaat (geeft de registratiemethode aan). |
| CertExpirationDate | Vervaldatum van het MDM-beheercertificaat. |
| MdmStatusKey | Een sleutel voor MdmStatus. |
| OSFamily | Type besturingssysteem (Windows, iOS, Android, enzovoort) |
| OSVersion | Besturingssysteemversie |
| OSMajorVersion | Onderdeel primaire versie van de besturingssysteemversie (major.minor.build.revision). |
| OSMinorVersion | Onderdeel secundaire versie van de besturingssysteemversie (major.minor.build.revision). |
| OSBuildNumber | Onderdeel buildversie van de besturingssysteemversie (major.minor.build.revision). |
| OSRevisionNumber | Onderdeel revisieversie van de besturingssysteemversie (major.minor.build.revision). |
| EasID | De EAS-id van dit apparaat, als het apparaat wordt beheerd door Exchange Active Sync. |
| GraphDeviceIsManaged | De laatste beheerstatus die met Intune is ingesteld in Azure AD. |
| GraphDeviceIsCompliant | De laatste nalevingsstatus die met Intune is ingesteld in Azure AD. |
| SerialNumber | Serienummer van het apparaat, indien beschikbaar. |
| EnrolledByUser | De id van de gebruiker die dit apparaat heeft geregistreerd die verwijst naar de kolom userId in de tabel User. |
| RowLastModifiedDateTimeUTC | Laatste keer dat deze record is gewijzigd. |
| ProcessorArchitecture | Processorarchitectuur. |
| DeviceAction | Laatste apparaatactie waarvoor opdracht is gegeven; voor nu negeren. |
| Fabrikant | Fabrikant van het apparaat. |
| Model | Model van het apparaat. |
| LastPolicyUpdateUtc | Tijdstip waarop het beleid voor het laatst op het apparaat is bijgewerkt. |
| LastExchangeStatusUtc | Laatste keer dat het apparaat is gesynchroniseerd met Exchange. |
| IsDeleted | Ingesteld op True als het apparaat niet meer wordt beheerd door Intune. De laatst bekende status blijft behouden. |
| AndroidSecurityPatchLevel |De datum van de meest recente beveiligingspatch van het apparaat. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

De entiteit **DevicePropertyHistory** heeft dezelfde eigenschappen als de apparatentabel en dagelijkse momentopnamen van elke apparaatrecord per dag voor de afgelopen 90 dagen. De kolom DateKey geeft de dag voor elke rij aan.

| Eigenschap  | Beschrijving |
|---------|------------|
| DateKey |Verwijzing naar datumtabel waarmee de dag wordt aangegeven. |
| DeviceKey |Unieke id van het apparaat in het datawarehouse - surrogaatsleutel. Dit is een verwijzing naar de tabel Device die de Intune-apparaat-id bevat. |
| DeviceName |Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten. |
| DeviceTypeKey |Sleutel van het kenmerk voor het apparaattype voor dit apparaat. |
| ClientRegisterationStateKey |Sleutel van het kenmerk voor de clientregistratiestatus voor dit apparaat. |
| OwnerTypeKey |Sleutel van het kenmerk voor het type eigenaar voor dit apparaat: zakelijk, persoonlijk of onbekend. |
| objectSourceKey |Negeer deze kolom. |
| CreatedDate |Datum waarop het apparaat is geregistreerd. |
| LastContact |Laatste bekende keer dat een apparaat is ingecheckt met Intune. |
| LastContactNotification |Laatste keer dat Intune heeft gemeld dat het apparaat moest worden ingecheckt met Intune. |
| LastContactWorkplaceJoin |De tijdstempel die de laatste bekende Workplace Join-status voor dit apparaat aangeeft. |
| ManagementAgentKey |Sleutel van de beheeragent die is gekoppeld aan dit apparaat. |
| ManagementStateKey |Sleutel van de aan dit apparaat gekoppelde beheerstatus waarmee de laatste status van een externe actie wordt aangegeven of dat het apparaat is gekraakt of geroot. |
| ReferenceId |De apparaat-id in Azure Active Directory. |
| WorkPlaceJoinStateKey |Sleutel van de status van de werkplektoevoeging van dit apparaat. |
| CategoryId |Negeer deze kolom. |
| EnrollmentTypeKey |Sleutel van het registratietype dat is gekoppeld aan dit apparaat (geeft de registratiemethode aan). |
| CertExpirationDate |Vervaldatum van het MDM-beheercertificaat. |
| MdmStatusKey |Een sleutel voor MdmStatus. |
| OSFamily |Type besturingssysteem (Windows, iOS, Android, enzovoort) |
| OSVersion |Versie besturingssysteem. |
| OSMajorVersion |Onderdeel primaire versie van de besturingssysteemversie (major.minor.build.revision). |
| OSMinorVersion |Onderdeel secundaire versie van de besturingssysteemversie (major.minor.build.revision). |
| OSBuildNumber |Onderdeel buildversie van de besturingssysteemversie (major.minor.build.revision). |
| OSRevisionNumber |Onderdeel revisieversie van de besturingssysteemversie (major.minor.build.revision). |
| EasID |De EAS-id van dit apparaat, als het apparaat wordt beheerd door Exchange Active Sync. |
| GraphDeviceIsManaged |De laatste beheerstatus die met Intune is ingesteld in Azure AD. |
| GraphDeviceIsCompliant |De laatste nalevingsstatus die met Intune is ingesteld in Azure AD. |
| SerialNumber |Serienummer van het apparaat, indien beschikbaar. |
| EnrolledByUser |De id van de gebruiker die dit apparaat heeft geregistreerd die verwijst naar de kolom userId in de tabel User. |
| RowLastModifiedDateTimeUTC |Laatste keer dat deze record is gewijzigd. |
| ProcessorArchitecture |Processorarchitectuur. |
| DeviceAction |Laatste apparaatactie waarvoor opdracht is gegeven; voor nu negeren. |
| Fabrikant |Fabrikant van het apparaat. |
| Model |Model van het apparaat. |
| LastPolicyUpdateUtc |Tijdstip waarop het beleid voor het laatst op het apparaat is bijgewerkt. |
| LastExchangeStatusUtc |Laatste keer dat het apparaat is gesynchroniseerd met Exchange. |

## <a name="mdmdeviceinventoryhistories"></a>MdmDeviceInventoryHistories

De entiteit **MdmDeviceInventoryHistories** bevat dagelijkse momentopnamen van inventarisgegevens voor MDM-beheerde apparaten voor de afgelopen 90 dagen. De kolom DateKey geeft de dag voor de rij aan. Bepaalde eigenschappen zijn mogelijk niet van toepassing of zijn ingevuld. Raadpleeg deze pagina voor meer informatie. Zie [Inzicht in uw apparaten met inventarisaties in Microsoft Intune](device-inventory.md) voor meer informatie.

| Eigenschap  | Beschrijving |
|---------|------------|
| DateKey | Verwijzing naar datumtabel waarmee de dag wordt aangegeven. |
| DeviceKey |Unieke id van het apparaat in het datawarehouse - surrogaatsleutel. Dit is een verwijzing naar de tabel Device die de Intune-apparaat-id bevat. |
| DeviceModel |Model van het apparaat. |
| Besturingssysteem |Besturingssysteem van het apparaat. |
| DeviceName |Naam van het apparaat op platforms waarop het benoemen van een apparaat is toegestaan. Op andere platforms maakt Intune een naam op basis van andere eigenschappen. Dit kenmerk is niet beschikbaar voor alle apparaten. |
| SoftwareVersion |In de meeste gevallen is dit de versie van het besturingssysteem, behalve bij Apple-platforms waarbij dit verschilt van de versie van het besturingssysteem. |
| Imei |IMEI-nummer |
| HardwareInventoryTimeUtc |De eerste keer dat er een inventarisatie voor dit apparaat is gerapporteerd. |
| InventoryModifiedTimeUtc |De laatste keer dat de inventarisatie is opgeslagen toen deze momentopname werd gemaakt. |
| InventoryReportingTimeUtc |De laatste keer dat de inventaris is verzameld voor dit apparaat. |
| ExchangeActiveSyncId |Exchange ActiveSync-apparaat-id. |
| ComputerSystemDescription |Systeembeschrijving. |
| ComputerSystemName |Systeemnaam. |
| ComputerSystemManufacturer |Fabrikant van het systeem. |
| ComputerSystemModel |Systeemmodel. |
| UserName |Gebruikersnaam. |
| OSType |Type besturingssysteem. |
| OSCaption |Besturingssysteembijschrift. |
| OSName |Naam van besturingssysteem. |
| OSManufacturer |Fabrikant van het besturingssysteem. |
| OSProductSuite |Besturingssysteemproductsuite. |
| OSProductType |Besturingssysteemproducttype. |
| Landinstellingen |Landinstellingen van besturingssysteem. |
| PhysicalMemoryCapacity |Capaciteit van het fysieke geheugen (in bytes). |
| PhysicalMemoryRemovable |Fysiek verwisselbaar geheugen (in bytes). |
| SystemEnclosureChassisTypesInnerText |Hiermee wordt het systeemchassistype voor dit apparaat gedefinieerd. De getallen geven de volgende waarden aan:  <br>0 of leeg = onbekend   <br>1 = het is een desktop   <br>2 = het is een laptop  <br>3 = het is een werkstation  <br>4 = het is een bedrijfsserver  <br>100 = het is een telefoon  <br>101 = het is een tablet  <br>102/103 = het is een ander, onbekend type mobiel apparaat |
| SystemEnclosureModel |Model systeembehuizing. |
| SystemEnclosureSerialNumber |Serienummer systeembehuizing. |
| NetworkAdapterConfigurationText |Configuratietekst van netwerkadapter. |
| MacAddress |MAC-adres. |
| SmsID |Intune-apparaat-id. |
| CertExpiry |Vervaldatum van het MDM-beheercertificaat. |
| DeviceClientAgentVersion |Versie van clientagent. |
| DeviceClientID |Apparaatclient-id. |
| SerialNumber |Serienummer. |
| DeviceManufacturer |Apparaatfabrikant. |
| DMVersion |DM-versie. |
| FirmwareVersion |Firmwareversie. |
| HardwareVersion |Hardwareversie. |
| PlatformType |Platformtype. |
| ProcessorLevel |Processorniveau. |
| ProcessorRevision |Processorrevisie. |
| Product |Product. |
| ProductVersion |Productversie. |
| OEM |Original Equipment Manufacturer. |
| DeviceBuildVersion |Buildversie van apparaat. |
| Meid |MEID (Mobile Equipment Identifier). |
| PhoneNumber |Telefoonnummer. |
| SubscriberCarrierNetwork |Netwerknaam van telefoonprovider. |
| CellularTechnology |Netwerktype van telefoonprovider (CDMA/GSM). |
| Imsi |IMSI-nummer. |
| JailBroken |Waar als het apparaat is gekraakt of geroot. |
| IsActivationLockEnabled |Waar als de activeringsvergrendeling is ingeschakeld |
| DeviceType |Apparaattype |
| IsSupervised |Onder supervisie |
| DeviceDisplayNumberOfColors |Aantal kleuren van apparaatscherm |
| HorizontalResolution |Horizontale schermresolutie van apparaat |
| VerticalResolution |Verticale schermresolutie van apparaat |
| StorageFree |Beschikbare opslag (in bytes) |
| StorageTotal |Totale opslag (in bytes) |
| ProgramFree |Beschikbaar programmageheugen (in bytes) |
| ProgramTotal |Totaal programmageheugen (in bytes) |
| RemovableStorageFree |Beschikbare verwisselbare opslag (in bytes) |
| RemovableStorageTotal |Totale verwisselbare opslag (in bytes) |
| DeviceMemoryDeviceCapacity |Geheugencapaciteit van apparaat |
| DeviceMemoryAvailableDeviceCapacity |Beschikbare geheugencapaciteit van apparaat |
| DeviceOSVersion |Versie besturingssysteem |
| DeviceOSPlatform |Besturingssysteemplatform |
| DeviceOSLanguage |Taal van besturingssysteem |
| PasswordMaxAttemptsBeforeWipe |Maximaal aantal toegestane wachtwoordpogingen voordat het apparaat wordt gewist |
| PasswordMinComplexChars |Minimaal aantal complexe tekens dat vereist is in het wachtwoord |
| PasswordMinLength |Minimaal vereiste lengte van wachtwoord |
| PasswordHistory |Wachtwoord - minimale geschiedenis van wachtwoorden die niet zijn geaccepteerd |
| PasswordEnabled |Wachtwoord - ingeschakeld? |
| PasswordExpiration |Wachtwoord - vervaldatum. |
| AllowRecoveryPassword |Wachtwoordherstel toestaan. |
| PasswordAutoLockTimeout |Wachtwoord - time-out voor automatische vergrendeling. |
| PasswordType |Wachtwoordtype. |
| BacklightACTimeout |Time-out voor achtergrondverlichting indien aangesloten op netstroom. |
| BacklightBatTimeout |Time-out voor achtergrondverlichting bij accu. |
| PowerBackupPercent |Stroompercentage. |
| BatteryPercent |Resterend percentage accu. |
| PlatformID |Platform-id. |
| ExchangeDeviceID |Exchange-apparaat-id. |
| SmsProcessorDescription |Beschrijving van de processor. |
| OwnerEmailAddress |E-mailadres van de eigenaar. |
| DeviceOSName |Naam van besturingssysteem. |
| WifiMac |Mac-adres van Wi-Fi. |
| EthernetMac |MAC-adres van ethernet. |
| RequireEncryption |Hiermee wordt aangegeven of het apparaat al of niet is versleuteld. |
| ActivationLockBypassCode |Code voor het overslaan van de activeringsvergrendeling. |

## <a name="applicationinventory"></a>ApplicationInventory

Met de entiteit **ApplicationInventory** worden de apps weergegeven die zich op het moment van de inventarisatieverzameling op het apparaat bevinden.


|      Eigenschap      |                       Beschrijving                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Een verwijzing naar de apparatentabel.               |
|   ApplicationKey   | ? (overgenomen van ExchangeDeviceService\DeviceApplication). |
|  ApplicationName   | ? (overgenomen van ExchangeDeviceService\DeviceApplication). |
| ApplicationVersion | ? (overgenomen van ExchangeDeviceService\DeviceApplication). |
|     BundleSize     | ? (overgenomen van ExchangeDeviceService\DeviceApplication). |

