---
title: Wat is Microsoft Intune-apparaatinschrijving?
titleSuffix: Intune on Azure
description: Meer informatie over registratie voor iOS, Android en Windows-apparaten.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 927e2f21aad4ff39c9351bef68eb510e93410c37
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="what-is-device-enrollment"></a>Wat is apparaatinschrijving?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In dit onderwerp worden verschillende manieren voor de inschrijving van mobiele apparaten in het Intune-beheer beschreven.

Als u apparaten in Intune inschrijft, kunt u deze apparaten beheren. In de Intune-documentatie wordt hiernaar verwezen als Mobile Device Management (MDM). Wanneer apparaten worden ingeschreven in Intune, krijgen ze een MDM-certificaat, waarmee de apparaten vervolgens kunnen communiceren met de Intune-service.

De manier waarop u apparaten registreert, is afhankelijk van het apparaattype, het eigendom en het benodigde beheerniveau. Met BYOD-registratie (Bring-Your-Own-Device) kunnen gebruikers hun eigen telefoons, tablets of pc's registreren. Met registratie van COD's (Corporate-owned devices, apparaten van bedrijf) zijn beheerscenario's mogelijk zoals automatische registratie, gedeelde apparaten en vooraf geautoriseerde registratievereisten.

Als u Exchange ActiveSync on-premises of gehost in de cloud gebruikt, kunt u een eenvoudig Intune-beheer zonder registratie toepassen (binnenkort volgt meer informatie). U kunt Windows-pc's beheren als mobiele apparaten. Dit is de aanbevolen methode die hieronder wordt beschreven.


## <a name="overview-of-device-enrollment-methods"></a>Overzicht van registratiemethoden voor apparaten

De volgende tabel biedt een overzicht van registratiemethoden voor Intune. De mogelijkheden en vereisten worden hieronder beschreven.
**Legenda**

- **Opnieuw instellen vereist**: het apparaat wordt tijdens de registratie teruggezet naar de fabrieksinstellingen.
- **Gebruikersaffiniteit**: apparaten worden aan gebruikers gekoppeld. Zie [Gebruikersaffiniteit](device-enrollment-program-enroll-ios.md) voor meer informatie.
- **Vergrendeld**: voorkomt dat gebruikers de registratie van apparaten ongedaan maken.

**iOS-registratiemethoden**

| **Methode** |  **Opnieuw instellen vereist** |    **Gebruikersaffiniteit**   |   **Vergrendeld** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nee|    Ja |   Nee | [Meer informatie](./apple-mdm-push-certificate-get.md)|
|**[DEM](#dem)**|   Nee |Nee |Nee  | [Meer informatie](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|   Ja |   Optioneel |  Optioneel|[Meer informatie](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Yes |   Optioneel |  Nee| [Meer informatie](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB-Direct](#usb-direct)**| Nee |    Nee  | Nee|[Meer informatie](./apple-configurator-direct-enroll-ios.md)|

**Windows-registratiemethoden**

| **Methode** |  **Opnieuw instellen vereist** |    **Gebruikersaffiniteit**   |   **Vergrendeld** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nee |   Ja |   Nee | [Meer informatie](windows-enroll.md)|
|**[DEM](#dem)**|   Nee |Nee |Nee  |[Meer informatie](device-enrollment-manager-enroll.md)|
|**Automatisch inschrijven** | Nee |Ja |Nee | [Meer informatie](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Bulkregistratie** |Nee |Nee |Nee | [Meer informatie](./windows-bulk-enroll.md) |

**Android-registratiemethoden**

| **Methode** |  **Opnieuw instellen vereist** |    **Gebruikersaffiniteit**   |   **Vergrendeld** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nee|    Ja |   Nee | [Meer informatie](./android-enroll.md)|
|**[DEM](#dem)**|   Nee |Nee |Nee  |[Meer informatie](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Nee | Ja | Nee| [Meer informatie](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="byod"></a>BYOD
BYOD-gebruikers (Bring-Your-Own-Device) installeren en gebruiken de bedrijfsportal-app om hun apparaten te registreren. Met dit programma hebben gebruikers toegang tot de bedrijfsresources als e-mail.

## <a name="corporate-owned-devices"></a>Apparaten in bedrijfseigendom
De volgende registratiescenario's hebben betrekking op apparaten in bedrijfseigendom (COD). iOS-apparaten kunnen rechtstreeks met de hulpprogramma's van Apple worden ingeschreven. Alle typen apparaten kunnen worden ingeschreven door een beheerder of manager die de apparaatinschrijvingsbeheerder gebruikt. Apparaten met een IMEI-nummer kunnen ook worden geïdentificeerd en getagd als bedrijfseigendom om COD-scenario's mogelijk te maken.

### <a name="dem"></a>DEM
De apparaatinschrijvingsmanager (DEM) is een speciaal gebruikersaccount voor registratie en beheer van meerdere apparaten in bedrijfseigendom. Beheerders kunnen de bedrijfsportal installeren en veel apparaten zonder gebruiker registreren. Meer informatie over [DEM](./device-enrollment-manager-enroll.md).

### <a name="dep"></a>DEP
Met DEP-beheer (Device Enrollment Program) van Apple kunt u beleid maken en 'draadloos' implementeren op iOS-apparaten die met DEP worden gekocht en beheerd. Het apparaat wordt geregistreerd wanneer de gebruiker het apparaat de eerste keer inschakelt en de iOS-configuratieassistent uitvoert. Deze methode ondersteunt de modus **iOS onder supervisie**, die zorgt voor de volgende functionaliteit:

  - Vergrendelde registratie
  - Kioskmodus en andere geavanceerde configuraties en beperkingen

Meer informatie over de iOS DEP-registratie:

- [Kiezen hoe u iOS-apparaten registreert](enrollment-method-choose-ios.md)
- [iOS-apparaten inschrijven met het Device Enrollment Program](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB-SA
IT-beheerders gebruiken Apple Configurator, via USB, om elk apparaat van het bedrijf handmatig voor te bereiden voor registratie met behulp van de Configuratieassistent. De IT-beheerder maakt een registratiebeleid en exporteert het beleid naar Apple Configurator. Wanneer gebruikers hun apparaat ontvangen, wordt hun gevraagd om Configuratieassistent uit te voeren om het apparaat in te schrijven. Deze methode ondersteunt de modus **iOS onder supervisie**, die zorgt voor de volgende functies:
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

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.
