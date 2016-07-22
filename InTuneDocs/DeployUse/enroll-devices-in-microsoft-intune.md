---
# required metadata

title: Apparaten registreren | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: damionw
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apparaten inschrijven bij Intune voor beheer
Mobile Device Management (MDM) van Microsoft Intune maakt gebruik van inschrijving om apparaten onder beheer te brengen en toegang tot bronnen toe te staan. De manier waarop u apparaten inschrijft, is afhankelijk van het apparaattype, het eigendom en het benodigde beheerniveau. 'Bring your own device'-scenario’s (BYOD-scenario’s) en scenario’s met apparaten die bedrijfseigendom zijn (COD, company-owned device), vereisen een inschrijvingsproces. Organisaties die Exchange ActiveSync gebruiken, lokaal of gehost in de cloud, kunnen lichter beheer zonder inschrijvingsvereisten toepassen. Windows-pc's kunnen ook worden beheerd met Intune-clientsoftware.

###  Ondersteunde apparaatplatformen

Met Intune kunnen de volgende apparaatplatformen worden beheerd:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Apparaatinschrijving inschakelen  
 Dankzij inschrijving kunnen gebruikers toegang krijgen tot bedrijfsbronnen op hun eigen apparaten en kan de beheerder ervoor zorgen dat die apparaten de beleidsregels naleven die de bedrijfsbronnen beveiligen. Dit is de beste manier om met Intune 'Bring Your Own Device'-scenario's te ondersteunen. De beheerder moet inschrijving in de Intune-console inschakelen, waarvoor mogelijk het maken van een vertrouwensrelatie met het apparaat is vereist en licenties aan gebruikers moeten worden toegewezen. Het apparaat wordt vervolgens ingeschreven, meestal door gebruikers die de referenties voor hun werk- of schoolaccount invoeren. Het apparaat ontvangt vervolgens beleid van Intune en krijgt toegang tot bronnen.

[Apparaten inschrijven in Intune voorbereiden](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Apparaten inschrijven die bedrijfseigendom zijn
Apparaten die bedrijfseigendom (COD) zijn, kunnen met de Intune-console worden beheerd. iOS-apparaten kunnen rechtstreeks via de hulpprogramma's van Apple worden ingeschreven. Alle typen apparaten kunnen worden ingeschreven door een beheerder of manager die de apparaatinschrijvingsbeheerder gebruikt. Apparaten met een IMEI-nummer kunnen ook worden geïdentificeerd en getagd als bedrijfseigendom om COD-scenario's mogelijk te maken.

[Apparaten inschrijven die bedrijfseigendom zijn](manage-corporate-owned-devices.md)

## Mobile Device Management met Exchange ActiveSync en Intune
Mobiele apparaten die niet zijn ingeschreven maar die met Exchange ActiveSync (EAS) verbinding maken, kunnen met behulp van MDM EAS-beleid door Intune worden beheerd. Intune gebruikt een Exchange-connector om met EAS te communiceren, zowel op locatie als in de cloud.



[Mobile Device Management met Exchange ActiveSync en Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Windows-pc's met Intune beheren  
U kunt Microsoft Intune ook gebruiken om Windows-pc's te beheren met de Intune-clientsoftware voor Windows-pc’s. Pc's die door de Intune-client worden beheerd, kunnen:

 - Software- en hardware-inventarisatierapporten maken
 - Bureaubladtoepassingen installeren (bijvoorbeeld .exe en .msi-bestanden)
 - Firewall-instellingen

Computers die door Intune-clientsoftware worden beheerd, kunnen niet selectief worden gewist of buiten gebruik worden gesteld, en kunnen geen gebruik maken van de talloze Intune-beheerfuncties, zoals voorwaardelijke toegang, VPN- en Wi-Fi-instellingen, of de implementatie van certificaten en e-mailconfiguraties.

[Windows-pc's met Intune beheren](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=Jun16_HO2-->


