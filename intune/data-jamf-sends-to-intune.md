---
title: Gegevens die Jamf Pro verzendt naar Intune | Microsoft Intune
description: Lijst met gegevens die door Jamf Pro worden verzonden naar Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 22d81c768fb7f80498da483421f8b358d59ab8c2
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233230"
---
# <a name="data-jamf-pro-sends-to-intune"></a>Gegevens die Jamf Pro verzendt naar Intune

Wanneer u [Jamf Pro](https://www.jamf.com) gebruikt voor het beheren van de Macs van uw eindgebruikers, legt Jamf Pro inventarisinformatie vast over beheerde macOS-apparaten. Jamf Pro geeft de volgende informatie door aan Intune:

* Id Azure AD-apparaat
* Status van de JAMF-inventaris (inventarisstatus van een computer die tijdens de afgelopen 24 uur is ingecheckt bij Jamf Pro)
* Versie besturingssysteem
* Id Azure AD-gebruiker
* Versleuteld (FileVault 2)
* Poortwachterstatus
* Wachtwoord: minimum aantal tekensets
* Wachtwoordverlooptijd (dagen)
* Type wachtwoord: eenvoudig, alfanumeriek of onbekend
* Automatische aanmelding voorkomen
* Vereiste lengte van de wachtwoordcode
* Wachtwoord: aantal eerdere wachtwoorden dat niet opnieuw mag worden gebruikt
* Beveiliging systeemintegriteit
* Tijd laatste check-in
* Type architectuur
* Beschikbare RAM-sleuven
* Capaciteit van de accu
* Opstart-ROM
* Bussnelheid
* Cachegrootte
* Apparaatnaam
* Lid van domein
* Jamf-id
* MAC-adres
* Merk
* Model
* Model-id
* NIC-snelheid
* Aantal kernen
* Aantal processors
* Besturingssysteem
* Platform
* Processorsnelheid
* Type processor
* Secundair MAC-adres
* Serienummer
* SMC-versie
* Totaal RAM
* udid
* E-mailadres gebruiker


U kunt een door Jamf beheerd apparaat verwijderen uit de Intune-console door in de weergave **Alle apparaten** **Verwijderen** te selecteren. Bulkverwijdering van apparaten kan worden ingeschakeld door meerdere apparaten te selecteren en op **Verwijderen** te klikken.

U vindt meer informatie over [het verwijderen van door Jamf beheerde apparaten in de Jamf Pro-documenten](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). U kunt ook een ondersteuningsticket indienen met [Jamf-ondersteuning](https://www.jamf.com/support/) voor meer informatie. 

