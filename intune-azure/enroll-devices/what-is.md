---
title: Wat is Microsoft Intune-apparaatinschrijving?
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: informatie over inschrijving voor iOS, Android en Windows-apparaten.'
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 900883ea9e38342cced195f97693447fafd0e73f
ms.lasthandoff: 02/18/2017


---

# <a name="what-is-device-enrollment"></a>Wat is apparaatinschrijving?
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

In dit onderwerp worden verschillende manieren voor de inschrijving van mobiele apparaten in het Intune-beheer beschreven.

Als u apparaten in Intune inschrijft, zoals Windows-pc's, kunt u deze apparaten beheren. In de Intune-documentatie wordt hiernaar verwezen als Mobile Device Management (MDM). Wanneer apparaten worden ingeschreven als mobiele apparaten (en niet als pc's), krijgen ze een MDM-certificaat, waarmee de apparaten vervolgens kunnen communiceren met de Intune-service.

De manier waarop u apparaten registreert, is afhankelijk van het apparaattype, het eigendom en het benodigde beheerniveau. Met BYOD-registratie (Bring-Your-Own-Device) kunnen gebruikers hun eigen telefoons, tablets of pc's registreren. Met registratie van COD's (Corporate-owned devices, apparaten van bedrijf) zijn beheerscenario's mogelijk zoals automatische registratie, gedeelde apparaten en vooraf geautoriseerde registratievereisten.

Als u Exchange ActiveSync on-premises of gehost in de cloud gebruikt, kunt u een eenvoudig Intune-beheer zonder registratie toepassen (binnenkort volgt meer informatie). U kunt Windows-pc's beheren als mobiele apparaten. Dit is de aanbevolen methode die hieronder wordt beschreven. U kunt ze ook beheren als pc's met behulp van [Intune-clientsoftware](https://docs.microsoft.com/intune/deploy-use/manage-windows-pcs-with-microsoft-intune).


## <a name="overview-of-device-enrollment-methods"></a>Overzicht van registratiemethoden voor apparaten

De volgende tabel bevat de registratiemethoden van Intune en de ondersteunde mogelijkheden en vereisten van elke methode. De mogelijkheden en vereisten worden hieronder beschreven. In de tabel worden de volgende termen gebruikt:

- **Wissen**: geeft aan of het apparaat moet worden gewist voordat gebruikers het apparaat kunnen inschrijven. 'Wissen' betekent dat de fabrieksinstellingen van het apparaat worden teruggezet, waardoor alle gegevens worden verwijderd. Zie voor meer informatie [Volledig of selectief wissen gebruiken](/intune-azure/manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune).
- **Affiniteit**: apparaten worden aan gebruikers gekoppeld. Dit is vereist voor Mobile Application Management (MAM) en voorwaardelijke toegang tot bedrijfsgegevens. Zie [Gebruikersaffiniteit](enroll-ios-devices-using-device-enrollment-program.md) voor meer informatie.
- **Vergrendeling** - geeft aan of gebruikers wordt verhinderd hun apparaten uit te schrijven voor beheer. Gebruikers kunnen hun apparaten op alle platforms uitschrijven via de bedrijfsportal-app. Ze kunnen niet de eigen menu’s van het besturingssysteem gebruiken om apparaten uit te schrijven.


**iOS-registratiemethoden**

| **Methode** |    **Wissen vereist?** |    **Affiniteit**    |    **Vergrendelen** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nee|    Ja |    Nee | Meer informatie binnenkort beschikbaar|
|**[DEM](#dem)**|    Nee |Nee |Nee    | [Meer informatie](enroll-ios-devices-using-device-enrollment-program.md)|
|**[DEP](#dep)**|    Ja |    Optioneel |    Optioneel|[Meer informatie](enroll-ios-devices-using-device-enrollment-program.md)|
|**[USB-SA](#usb-sa)**|    Yes |    Optioneel |    Nee| [Meer informatie](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)|
|**[USB-Direct](#usb-direct)**|    Nee |    Nee    | Nee|[Meer informatie](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)|



**Windows-registratiemethoden**

| **Methode** |    **Wissen vereist?** |    **Affiniteit**    |    **Vergrendelen** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Yes|    Ja |    Nee | Meer informatie binnenkort beschikbaar|
|**[DEM](#dem)**|    Nee |Nee |Nee    |[Meer informatie](enroll-devices-using-device-enrollment-manager.md)|

**Android-registratiemethoden**

| **Methode** |    **Wissen vereist?** |    **Affiniteit**    |    **Vergrendelen** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nee|    Ja |    Nee | Meer informatie binnenkort beschikbaar|
|**[DEM](#dem)**|    Nee |Nee |Nee    |[Meer informatie](enroll-ios-devices-using-device-enrollment-program.md)|


## <a name="byod"></a>BYOD
'Bring-Your-Own-Device'-gebruikers installeren de bedrijfsportal-app en registreren hun apparaat. Hiermee kunnen gebruikers verbinding maken met het bedrijfsnetwerk en deelnemen aan het domein of Azure Active Directory. Voor de meeste platformen moet u BYOD-registratie inschakelen voor veel COD-scenario’s. U kunt de inschrijving blokkeren van iOS- en Android-apparaten die het eigendom van de gebruiker zijn. Zie [Beperkingen voor apparaattypen instellen](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions) voor instructies.

## <a name="corporate-owned-devices"></a>Apparaten in bedrijfseigendom
Apparaten in bedrijfseigendom (COD) kunnen met de Azure Portal worden beheerd. iOS-apparaten kunnen rechtstreeks met de hulpprogramma's van Apple worden ingeschreven. Alle typen apparaten kunnen worden ingeschreven door een beheerder of manager die de apparaatinschrijvingsbeheerder gebruikt. Apparaten met een IMEI-nummer kunnen ook worden geïdentificeerd en getagd als bedrijfseigendom om COD-scenario's mogelijk te maken.

### <a name="dem"></a>DEM
De apparaatinschrijvingsmanager (DEM) is een speciaal gebruikersaccount voor registratie en beheer van meerdere apparaten in bedrijfseigendom. Beheerders kunnen de bedrijfsportal installeren en veel apparaten zonder gebruiker registreren. Meer informatie over [DEM](enroll-devices-using-device-enrollment-manager.md). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Met DEP-beheer (Device Enrollment Program) van Apple kunt u beleid maken en 'draadloos' implementeren op iOS-apparaten die met DEP worden gekocht en beheerd. Het apparaat wordt geregistreerd wanneer de gebruiker het apparaat de eerste keer inschakelt en de iOS-configuratieassistent uitvoert. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:

  -    Vergrendelde registratie
  -    Kioskmodus en andere geavanceerde configuraties en beperkingen

Zie voor meer informatie over de iOS-inschrijving:

- [Kiezen hoe u iOS-apparaten registreert](choose-ios-enrollment-method.md)
- [iOS-apparaten inschrijven met het Device Enrollment Program](enroll-ios-devices-using-device-enrollment-program.md)
- [Terug naar bovenstaande tabel](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB-SA
IT-beheerders gebruiken Apple Configurator, via USB, om elk apparaat van het bedrijf handmatig voor te bereiden voor registratie met behulp van Configuratieassistent. De IT-beheerder maakt een registratiebeleid en exporteert het beleid naar Apple Configurator. Wanneer gebruikers hun apparaat ontvangen, wordt hun gevraagd om Configuratieassistent uit te voeren om het apparaat in te schrijven. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:
  -    Vergrendelde registratie
  -    Kioskmodus en andere geavanceerde configuraties en beperkingen

Zie voor meer informatie over de iOS-inschrijving:

- [Kiezen hoe u iOS-apparaten registreert](choose-ios-enrollment-method.md)
- [iOS-apparaten inschrijven met Configurator en Configuratieassistent](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)

### <a name="usb-direct"></a>USB-Direct
Voor directe registratie moet de beheerder elk apparaat handmatig registreren door een registratiebeleid te maken en dit te exporteren naar Apple Configurator. Via USB aangesloten apparaten van het bedrijf worden direct geregistreerd zonder dat de fabrieksinstellingen hoeven worden hersteld. De apparaten worden beheerd als apparaten zonder gebruiker. Ze zijn niet vergrendeld of onder supervisie en kunnen geen voorwaardelijke toegang, jailbreakdetectie en beheer van mobiele toepassingen ondersteunen.

Zie voor meer informatie over de iOS-inschrijving:

- [Kiezen hoe u iOS-apparaten registreert](choose-ios-enrollment-method.md)
- [iOS-apparaten inschrijven met Configurator en directe inschrijving](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Mobile Device Management met Exchange ActiveSync en Intune
Mobiele apparaten die niet zijn ingeschreven maar die met Exchange ActiveSync (EAS) verbinding maken, kunnen met behulp van MDM EAS-beleid door Intune worden beheerd. Intune gebruikt een Exchange-connector om met EAS te communiceren, on-premises of in de cloud. Meer informatie is binnenkort beschikbaar.


## <a name="windows-pc-management-with-intune"></a>Windows pc-beheer met Intune  
U kunt Microsoft Intune ook gebruiken om Windows-pc's te beheren met de Intune-clientsoftware. Pc's die met de Intune-client worden beheerd, kunnen:

 - Software- en hardware-inventarisatierapporten maken
 - Bureaubladtoepassingen installeren (bijvoorbeeld .exe en .msi-bestanden)
 - Firewall-instellingen beheren

Pc’s die worden beheerd met de Intune-clientsoftware kunnen niet volledig worden gewist, maar de optie voor selectief wissen is wel beschikbaar. Pc’s die met de Intune-softwareclient worden beheerd, kunnen geen gebruik maken van de vele Intune-beheerfuncties, zoals voorwaardelijke toegang, VPN- en Wi-Fi-instellingen, of de implementatie van certificaten en e-mailconfiguraties. Meer informatie is binnenkort beschikbaar.

## <a name="supported-device-platforms-and-browsers"></a>Ondersteunde apparaatplatformen en browsers

Zie [Ondersteunde apparaten en browsers voor Intune](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers)

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Mobiele apparaten opschonen na de verloopdatum van het MDM-certificaat

Het MDM-certificaat wordt automatisch vernieuwd wanneer mobiele apparaten communiceren met de Intune-service. Als mobiele apparaten (niet-pc's) worden gewist of een bepaalde tijd niet kunnen communiceren met de Intune-service, wordt het MDM-certificaat niet vernieuwd. Het apparaat wordt 180 dagen nadat het MDM-certificaat is verlopen verwijderd uit de Azure Portal.

