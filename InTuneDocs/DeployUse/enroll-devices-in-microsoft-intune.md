---
title: Apparaten registreren | Microsoft Intune
description: Mobile Device Management (MDM) maakt gebruik van inschrijving om apparaten onder beheer te brengen en toegang tot resources toe te staan.
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3f28cce75626df1115283dc98547adcb97ee1cb4
ms.openlocfilehash: d880123a9b4d4afd74e9941ce0590f5dae554667


---

# <a name="enroll-devices-for-management-in-intune"></a>Apparaten inschrijven bij Intune voor beheer
U kunt apparaten, waaronder Windows-pc’s, registreren om Mobile Device Management (MDM) met Microsoft Intune mogelijk te maken. In dit onderwerp worden verschillende manieren voor registratie van mobiele apparaten in het Intune-beheer beschreven. De manier waarop u apparaten registreert, is afhankelijk van het apparaattype, het eigendom en het benodigde beheerniveau. Met BYOD-registratie (Bring-Your-Own-Device) kunnen gebruikers hun eigen telefoons, tablets of pc's registreren. Met COD-registratie (apparaten in bedrijfseigendom) zijn beheerscenario's mogelijk, zoals wissen op afstand, gedeelde apparaten of gebruikersaffiniteit voor een apparaat.

Als u [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune) on-premises of gehost in de cloud gebruikt, kunt u een eenvoudig Intune-beheer zonder registratie toepassen. Windows-pc's kunnen ook worden beheerd met [Intune-clientsoftware](#manage-windows-pcs-with-intune).

## <a name="overview-of-device-enrollment-methods"></a>Overzicht van registratiemethoden voor apparaten

De volgende tabel bevat de registratiemethoden van Intune en de ondersteunde mogelijkheden en vereisten van elke methode. De mogelijkheden en vereisten worden hieronder beschreven.

- **Wissen**: geeft aan of het apparaat moet worden gewist voordat gebruikers het apparaat kunnen inschrijven. 'Wissen' betekent dat de fabrieksinstellingen van het apparaat worden teruggezet, waardoor alle gegevens worden verwijderd. Zie [Apparaten buiten gebruik stellen](retire-devices-from-microsoft-intune-management.md) voor meer informatie.
- **Affiniteit**: apparaten worden aan gebruikers gekoppeld. Dit is vereist voor Mobile Application Management (MAM) en voorwaardelijke toegang tot bedrijfsgegevens. Zie [Gebruikersaffiniteit](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices) voor meer informatie.
- **Vergrendelen**: dit voorkomt dat gebruikers het apparaat uit het beheer kunnen verwijderen. Voor iOS-apparaten is de supervisiemodus vereist voor vergrendeling. Zie [Vergrendelen op afstand](retire-devices-from-microsoft-intune-management.md#block-access-a-device) voor meer informatie.

**iOS-registratiemethoden**

| **Methode** |  **Wissen vereist?** |    **Affiniteit**    |   **Vergrendelen** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nee|    Ja |   Nee | [Meer informatie](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Nee |Nee |Nee  | [Meer informatie](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Ja |   Optioneel |  Optioneel|[Meer informatie](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Yes |   Optioneel |  Nee| [Meer informatie](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB-Direct](#usb-direct)**| Nee |    Nee  | Nee|[Meer informatie](ios-direct-enrollment-in-microsoft-intune.md)|

**Windows-registratiemethoden**

| **Methode** |  **Wissen vereist?** |    **Affiniteit**    |   **Vergrendelen** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Yes|   Ja |   Nee | [Meer informatie](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Nee |Nee |Nee  |[Meer informatie](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Android-registratiemethoden**

| **Methode** |  **Wissen vereist?** |    **Affiniteit**    |   **Vergrendelen** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nee|    Ja |   Nee | [Meer informatie](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Nee |Nee |Nee  |[Meer informatie](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Zie [Kiezen hoe u apparaten registreert](/intune/get-started/choose-how-to-enroll-devices1) voor een reeks vragen die u helpen de juiste methode te vinden.

## <a name="byod"></a>BYOD
'Bring-Your-Own-Device'-gebruikers installeren de bedrijfsportal-app en registreren hun apparaat. Hiermee kunnen gebruikers verbinding maken met het bedrijfsnetwerk en deelnemen aan het domein of Azure Active Directory. Voor de meeste platformen moet u BYOD-registratie inschakelen voor veel COD-scenario’s. Zie [Vereisten voor apparaatregistratie](prerequisites-for-enrollment.md) voor meer informatie. ([Terug naar de tabel](#overview-of-device-enrollment-methods))

## <a name="corporate-owned-devices"></a>Apparaten in bedrijfseigendom
Apparaten die bedrijfseigendom (COD) zijn, kunnen met de Intune-console worden beheerd. iOS-apparaten kunnen rechtstreeks met de hulpprogramma's van Apple worden ingeschreven. Alle typen apparaten kunnen worden ingeschreven door een beheerder of manager die de apparaatinschrijvingsbeheerder gebruikt. Apparaten met een IMEI-nummer kunnen ook worden geïdentificeerd en getagd als bedrijfseigendom om COD-scenario's mogelijk te maken.

Zie [Apparaten inschrijven die bedrijfseigendom zijn](manage-corporate-owned-devices.md) voor meer informatie.

### <a name="dem"></a>DEM
Het apparaatregistratiebeheer is een speciaal Intune-account voor registratie en beheer van meerdere apparaten in bedrijfseigendom. Beheerders kunnen de bedrijfsportal installeren en veel apparaten zonder gebruiker registreren. Meer informatie over [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Met DEP-beheer (Device Enrollment Program) van Apple kunt u beleid maken en 'draadloos' implementeren op iOS-apparaten die met DEP worden gekocht en beheerd. Het apparaat wordt geregistreerd wanneer de gebruiker het apparaat de eerste keer inschakelt en de iOS-configuratieassistent uitvoert. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:
  - Vergrendelde registratie
  - Voorwaardelijke toegang
  - Jailbreakdetectie
  - Beheer van mobiele toepassingen

Meer informatie over [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB-SA
Door USB verbonden apparaten van het bedrijf worden voorbereid met Intune-beleid. Voor registratie met de configuratieassistent maakt de beheerder een Intune-beleid en exporteert het naar Apple Configurator. De beheerder moet elk apparaat handmatig registreren. Gebruikers ontvangen hun apparaten en voeren Configuratieassistent uit om hun apparaat te registreren. Deze methode ondersteunt de modus **iOS onder supervisie** die zorgt voor:
  - Voorwaardelijke toegang
  - Jailbreakdetectie
  - Beheer van mobiele toepassingen

Meer informatie over [Setup Assistant enrollment with Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (Registratie met Configuratieassistent met Apple Configurator). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB-Direct
Voor rechtstreekse registratie maakt de beheerder een Intune-beleid en exporteert het naar Apple Configurator. Via USB aangesloten apparaten van het bedrijf worden direct geregistreerd zonder dat de fabrieksinstellingen hoeven worden hersteld. De beheerder moet elk apparaat handmatig registreren. De apparaten worden beheerd als apparaten zonder gebruiker. Ze zijn niet vergrendeld of onder supervisie en kunnen geen voorwaardelijke toegang, jailbreakdetectie en beheer van mobiele toepassingen ondersteunen. Meer informatie over [directe registratie met Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md). ([Terug naar de tabel](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Mobile Device Management met Exchange ActiveSync en Intune
Mobiele apparaten die niet zijn ingeschreven maar die met Exchange ActiveSync (EAS) verbinding maken, kunnen met behulp van MDM EAS-beleid door Intune worden beheerd. Intune gebruikt een Exchange-connector om met EAS te communiceren, on-premises of in de cloud.

Zie [Mobile Device Management met Exchange ActiveSync en Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md) voor meer informatie.


## <a name="windows-pc-management-with-intune"></a>Windows pc-beheer met Intune  
U kunt Microsoft Intune ook gebruiken om Windows-pc's te beheren met de Intune-clientsoftware. Pc's die met de Intune-client worden beheerd, kunnen:

 - Software- en hardware-inventarisatierapporten maken
 - Bureaubladtoepassingen installeren (bijvoorbeeld .exe en .msi-bestanden)
 - Firewall-instellingen beheren

Pc’s die worden beheerd met de Intune-clientsoftware kunnen niet volledig worden gewist, maar de optie voor selectief wissen is wel beschikbaar. Pc’s die met de Intune-softwareclient worden beheerd, kunnen geen gebruik maken van de vele Intune-beheerfuncties, zoals voorwaardelijke toegang, VPN- en Wi-Fi-instellingen, of de implementatie van certificaten en e-mailconfiguraties.

Zie [Windows-pc’s met Intune beheren](manage-windows-pcs-with-microsoft-intune.md) voor meer informatie.

## <a name="supported-device-platforms"></a>Ondersteunde apparaatplatformen

Met Intune kunnen de volgende apparaatplatformen worden beheerd:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Volgende stappen
- [Vereisten voor apparaatregistratie](prerequisites-for-enrollment.md)
- [Apparaten in bedrijfseigendom beheren](manage-corporate-owned-devices.md)
- [Ondersteunde mobiele apparaten en computers](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Nov16_HO3-->


