---
title: Gegevensverzameling in Intune
description: Lees informatie over het verzamelen van persoonlijke gegevens in Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1171740-936d-46a5-af37-f418bd6fa63e
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08066c0742ad4ad02f907e55cc84eb65068c9b99
ms.sourcegitcommit: c9725ddae6c0f82a491de27c87f240254d32716b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/13/2019
ms.locfileid: "70986428"
---
# <a name="data-collection-in-intune"></a>Gegevensverzameling in Intune

Wanneer gebruikers hun zakelijke of persoonlijke apparaten registreren met Intune, verzamelt en deelt Intune bepaalde persoonlijke gegevens. Intune verzamelt persoonlijke gegevens van de volgende bronnen:

- Het gebruik van de beheerder van Intune in Azure Portal.
- Apparaten van eindgebruikers (wanneer ze zich inschrijven voor Intune-beheer en tijdens het gebruik).
- Klantaccounts bij de services van derden (volgens de instructies van de beheerder).
- Diagnostische gegevens, prestatiegegevens en gebruiksgegevens.

Van deze bronnen verzamelt Intune gegevens die in de volgende drie categorieën vallen: [geïdentificeerd](#identified-data), [gepseudonimiseerd](#pseudonymized-data) en [geaggregeerd](#aggregated-data).

> [!NOTE]
> We verkopen gegevens die door onze service worden verzameld om geen enkele reden aan externe partijen.

## <a name="identified-data"></a>Geïdentificeerde gegevens

De meeste persoonlijke gegevens die door Intune worden verzameld, zijn geïdentificeerde gegevens. Deze gegevens zijn gekoppeld aan een gebruiker, apparaat of toepassing en zijn essentieel voor de aard van het beheer. Geïdentificeerde gegevens worden gebruikt voor het beheren van het apparaat en de toepassingen van een gebruiker, en voor het inrichten van de Intune-service.

Geïdentificeerde gegevens die door Intune worden verzameld, omvatten mogelijk, maar zijn niet beperkt tot: 

- Gebruikersgegevens
  - Weergaven van de eigenaar van de naam/gebruiker (de in Azure geregistreerde naam van de gebruiker, zoals aangegeven door de AzureUserID)
  - User principal name of e-mailadres
  - Identificaties van externe gebruikers (zoals Apple ID)
- Hardware-inventarisatiegegevens
  - Apparaatnaam
  - Fabrikant
  - Besturingssysteem
  - Serienummer
  - IMEI-nummer
  - Het IP-adres
  - Wi-Fi MacAddress
  - ICCID
  - Telefoonnummer
- Informatie uit auditlogboeken, waaronder gegevens over de volgende activiteiten
  - Manage
  - Maken
  - Bijwerken (bewerken)
  - Verwijderen
  - Toewijzen
  - Externe taken
- Ondersteuningsinformatie
  - Contactgegevens (naam, telefoonnummer, e-mailadres)
  - E-mailwisselingen met Microsoft Ondersteuning en leden van het product- en/of kwaliteitsverbeteringsteam
- Informatie over toegangsbeheer (Intune gebruikt deze gegevens voor het beheren van toegang tot administratieve rollen en functies via functies als [Op rollen gebaseerd toegangsbeheer](role-based-access-control.md)).
  - Statische verificators (wachtwoord van de klant)
  - Privacysleutels voor certificaten 
- Beheer- en accountgegevens
  - Voornaam en achternaam van de gebruiker met beheerdersrechten
  - Naam van de gebruiker met beheerdersrechten
  - UPN (e-mail)
  - Telefoonnummer
  - E-mailadres van accounteigenaar
  - Active Directory-id van de IT-beheerder van elke klant
  - Betalingsgegevens voor klantfacturering
  - Abonnementssleutel
- Toepassingsinventaris, zoals
  - app-naam
  - Versie
  - app-id
  - grootte
  - installatielocatie
  - Inventarisgegevens van toepassingen worden alleen verzameld wanneer deze door de beheerder zijn gemarkeerd als een apparaat in bedrijfseigendom of wanneer de functie voor compatibele apps is ingeschakeld.  
- Tenant-id's van derden, zoals de Apple ID. 

## <a name="pseudonymized-data"></a>Gepseudonimiseerde gegevens

Gepseudonimiseerde gegevens zijn gekoppeld aan een unieke id, doorgaans een nummer dat is gegenereerd door het systeem waarmee niet zelfstandig een individu kan worden geïdentificeerd, maar dat wordt gebruikt voor de levering van bedrijfsservices aan gebruikers. 

Gepseudonimiseerde gegevens die door Intune worden verzameld, omvatten mogelijk, maar zijn niet beperkt tot: 

- Diagnostische gegevens, prestatiegegevens en gebruiksgegevens die zijn gekoppeld aan een gebruiker en/of apparaat
  - Het aantal keer dat een functie wordt gebruikt
  - De opdrachten die door de functie worden geleverd
  - De reactietijd van een service
  - Succespercentages van installaties en andere processen
  - Toepassingsfouten van de Intune-bedrijfsportal
  - Gebruikers- en apparaat-id's
  - Id's voor verwijzing, correlatie en beheerdoeleinden 
- Gegevens van apparaten die niet zijn gekoppeld aan een apparaat of gebruiker (als deze gegevens zijn gekoppeld aan een apparaat of gebruiker, worden deze gegevens behandeld als geïdentificeerde gegevens)
  - Intune-apparaat-id
  - Apparaat-id van Azure Active Directory
  - Intune-apparaatbeheer-id
  - Tenant-id
  - Account-id
  - EAS-apparaat-id
  - Platformspecifieke id's
  - Apple ID voor iOS-apparaten
  - MAC-adres voor Mac-apparaten
  - Windows-id voor Windows-apparaten
- Beheerde toepassingsgegevens
  - Beheerde toepassing-id
  - Apparaatlabel van beheerde toepassing
  - Intune-apparaatbeheer-id
  - Apparaat-id van Azure Active Directory
  - Versleutelingssleutels

## <a name="aggregated-data"></a>Geaggregeerde gegevens

Geaggregeerde gegevens worden gebruikt voor het inrichten en verbeteren van de Intune-service. 

Geaggregeerde gegevens die door Intune worden verzameld, zijn mogelijk, maar niet beperkt tot: 

- Beheerdersgebruiksgegevens van alle Intune-tenants (bijvoorbeeld beheerdersbesturingselementen die zijn geselecteerd voor de communicatie met de beheerconsole)
- Gegevens van het tenantaccount (deze gegevens zijn beschikbaar via de blade van Intune)
  - Aantal ingeschreven apparaten of gebruikers
  - Aantal geïdentificeerde apparaatplatformen  
  - Aantal geïnstalleerde apparaten
  - installedDeviceCount: het aantal apparaten waarop de toepassing is geïnstalleerd.
  - notApplicableDeviceCount: het aantal apparaten waarvoor de toepassing niet van toepassing is.
  - notInstalledDeviceCount: het aantal apparaten waarvoor de toepassing van toepassing is, maar waarop de installatie niet is uitgevoerd.
  - pendingInstallDeviceCount: het aantal apparaten waarvoor de toepassing van toepassing is en waarvoor de installatie in behandeling is.

## <a name="next-steps"></a>Volgende stappen

Meer informatie over hoe Intune persoonlijke gegevens [opslaat en verwerkt](privacy-data-store-process.md), en [deelt](privacy-data-secure-share.md). 
