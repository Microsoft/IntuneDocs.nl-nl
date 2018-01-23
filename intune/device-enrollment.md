---
title: Wat is Microsoft Intune-apparaatinschrijving?
titlesuffix: Azure portal
description: Meer informatie over registratie voor iOS, Android en Windows-apparaten.
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 12/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dc0105bb786d8b1e569b11898b0d3757feba406a
ms.sourcegitcommit: a55a7119a15836b6941fdd5b32b9076139093693
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2018
---
# <a name="what-is-device-enrollment"></a>Wat is apparaatinschrijving?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met Intune kunt u de apparaten en apps beheren waarvan uw werknemers gebruikmaken en kunt u beheren hoe zij toegang hebben tot uw bedrijfsgegevens. Om gebruik te kunnen maken van MDM (Mobile Device Management), moeten de apparaten eerst worden geregistreerd bij de Intune-service. Wanneer een apparaat is geregistreerd, wordt een MDM-certificaat voor het apparaat uitgegeven. Dit certificaat wordt gebruikt om te communiceren met de Intune-service.

Zoals u in de volgende tabellen ziet, zijn er verschillende methoden om de apparaten van uw werknemers te registreren. Elke methode is afhankelijk van het eigendom van het apparaat (persoonlijk of zakelijk), het apparaattype (iOS, Windows, Android), en de beheervereisten (opnieuw instellen, affiniteit, vergrendelen).

## <a name="ios-enrollment-methods"></a>iOS-registratiemethoden

| **Methode** |  **Opnieuw instellen vereist** |    [**Gebruikersaffiniteit**](device-enrollment-program-enroll-ios.md#create-an-apple-enrollment-profile) |   **Vergrendeld** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
| | Apparaten worden tijdens de registratie teruggezet naar de fabrieksinstellingen. |  Hiermee wordt elk apparaat aan een gebruiker gekoppeld.| Gebruikers kunnen apparaten niet uitschrijven.  | |
|**[BYOD](#bring-your-own-device)** | Nee|   Ja |   Nee | [Meer informatie](./apple-mdm-push-certificate-get.md)|
|**[DEM](#device-enrollment-manager)**| Nee |Nee |Nee  | [Meer informatie](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#apple-device-enrollment-program)**|   Ja |   Optioneel |  Optioneel|[Meer informatie](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Ja |   Optioneel |  Nee| [Meer informatie](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Nee |    Nee  | Nee|[Meer informatie](./apple-configurator-direct-enroll-ios.md)|

## <a name="windows-enrollment-methods"></a>Windows-registratiemethoden

| **Methode** |  **Opnieuw instellen vereist** |    **Gebruikersaffiniteit**   |   **Vergrendeld** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Nee |  Ja |   Nee | [Meer informatie](windows-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Nee |Nee |Nee  |[Meer informatie](device-enrollment-manager-enroll.md)|
|**Automatisch inschrijven** | Nee |Ja |Nee | [Meer informatie](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Bulkregistratie** |Nee |Nee |Nee | [Meer informatie](./windows-bulk-enroll.md) |

## <a name="android-enrollment-methods"></a>Android-registratiemethoden

| **Methode** |  **Opnieuw instellen vereist** |    **Gebruikersaffiniteit**   |   **Vergrendeld** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#bring-your-own-device)** | Nee|   Ja |   Nee | [Meer informatie](./android-enroll.md)|
|**[DEM](#device-enrollment-manager)**| Nee |Nee |Nee  |[Meer informatie](./device-enrollment-manager-enroll.md)|
|**Android for Work**| Nee | Ja | Nee| [Meer informatie](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="bring-your-own-device"></a>Bring Your Own Device
BYOD-apparaten (Bring Your Own Devices) zijn persoonlijke telefoons, tablets en pc's. BYOD-gebruikers gebruiken de bedrijfsportal-app om hun apparaten te registreren. Met dit programma hebben gebruikers toegang tot de bedrijfsresources als e-mail.

## <a name="corporate-owned-device"></a>Apparaat in bedrijfseigendom
Apparaten in bedrijfseigendom (COD) zijn telefoons, tablets, en pc's die eigendom zijn van de organisatie en gedistribueerd worden naar de werknemers. Met registratie van COD's zijn scenario's mogelijk zoals automatische registratie, gedeelde apparaten en vooraf geautoriseerde registratievereisten. Een veelgebruikte manier voor de registratie van COD's is dat een beheerder of manager DEM (apparaatinschrijvingsmanager) gebruikt. iOS-apparaten kunnen rechtstreeks met de DEP-hulpprogramma's (Device Enrollment Program) van Apple worden ingeschreven. Apparaten met een IMEI-nummer kunnen ook worden geïdentificeerd en getagd als bedrijfseigendom.

### <a name="device-enrollment-manager"></a>Apparaatinschrijvingsmanager
De apparaatinschrijvingsmanager (DEM) is een speciaal gebruikersaccount voor registratie en beheer van meerdere apparaten in bedrijfseigendom. Beheerders kunnen de bedrijfsportal installeren en veel apparaten zonder gebruiker registreren. Meer informatie over [DEM](./device-enrollment-manager-enroll.md).

### <a name="apple-device-enrollment-program"></a>Apple Device Enrollment Program
Met DEP-beheer (Device Enrollment Program) van Apple kunt u beleid maken en 'draadloos' implementeren op iOS-apparaten die met DEP worden gekocht en beheerd. Het apparaat wordt geregistreerd wanneer de gebruiker het apparaat de eerste keer inschakelt en de iOS-configuratieassistent uitvoert. Deze methode ondersteunt de supervisiemodus voor iOS, waarmee een apparaat kan worden geconfigureerd met een specifieke functionaliteit.

Meer informatie over de iOS DEP-registratie:

- [Kiezen hoe u iOS-apparaten registreert](ios-enroll.md)
- [iOS-apparaten inschrijven met het Device Enrollment Program](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### <a name="usb-sa"></a>USB-SA
IT-beheerders gebruiken Apple Configurator, via USB, om elk apparaat van het bedrijf handmatig voor te bereiden voor registratie met behulp van de Configuratieassistent. De IT-beheerder maakt een registratiebeleid en exporteert het beleid naar Apple Configurator. Wanneer gebruikers hun apparaat ontvangen, wordt hun gevraagd om Configuratieassistent uit te voeren om het apparaat in te schrijven. Deze methode ondersteunt de modus **iOS onder supervisie**, waarmee de volgende functies worden ingeschakeld:
  - Vergrendelde registratie
  - Kioskmodus en andere geavanceerde configuraties en beperkingen

Meer informatie over de registratie van de iOS Apple Configurator met Configuratieassistent:

- [Kiezen hoe u iOS-apparaten registreert](enrollment-method-choose-ios.md)
- [iOS-apparaten inschrijven met Configurator en Configuratieassistent](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB-Direct
Voor directe registratie moet de beheerder elk apparaat handmatig registreren door een registratiebeleid te maken en dit te exporteren naar Apple Configurator. Via USB aangesloten apparaten van het bedrijf worden direct geregistreerd zonder dat de fabrieksinstellingen hoeven worden hersteld. De apparaten worden beheerd als apparaten zonder gebruiker. Ze zijn niet vergrendeld of onder supervisie en kunnen geen voorwaardelijke toegang, jailbreakdetectie en beheer van mobiele toepassingen ondersteunen.

Zie voor meer informatie over de iOS-inschrijving:

- [Kiezen hoe u iOS-apparaten registreert](enrollment-method-choose-ios.md)
- [iOS-apparaten inschrijven met Configurator en directe inschrijving](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Mobile Device Management met Exchange ActiveSync en Intune
Mobiele apparaten die niet zijn ingeschreven maar die met Exchange ActiveSync (EAS) verbinding maken, kunnen met behulp van MDM EAS-beleid door Intune worden beheerd. Intune gebruikt een Exchange-connector om met EAS te communiceren, on-premises of in de cloud. Meer informatie is binnenkort beschikbaar.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobiele apparaten opschonen na de verloopdatum van het MDM-certificaat

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd.Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.
