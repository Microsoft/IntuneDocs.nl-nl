---
title: Gegevens die Apple verzendt naar Intune
titleSuffix: Microsoft Intune
description: Lijst met gegevens die door Apple worden verzonden naar Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: cf27fdb8-f408-425c-9a7c-146de1534425
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4362983bbcdb78f82ce7b16f675c6f61fbefd1e1
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57396319"
---
# <a name="data-apple-sends-to-intune"></a>Gegevens die Apple verzendt naar Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als een van de volgende Apple-services wordt ingeschakeld op een apparaat, maakt Microsoft Intune verbinding met Apple om gebruikers- en apparaatgegevens te delen:

- [Apple Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md)
- [Apple MDM-pushcertificaat (APNs)](apple-mdm-push-certificate-get.md)
- [Apple School Manager (ASM)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Apple Volume Purchase Program (VPP)](vpp-apps-ios.md)

Voordat Microsoft Intune verbinding kan maken, moet u een Apple-account maken voor elk van de Apple-services.

De volgende tabel bevat de gegevens die een Apple-apparaat naar Intune verzendt. [Intune verzendt ook gegevens naar Apple](data-intune-sends-to-apple.md). 

| Service | Bericht | Gegevens die worden verzonden naar Intune | Gebruikt voor |
|:---:|:---:|:---:| ---|
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | MessageType | Het berichttype: verifiëren. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | Onderwerp | Het onderwerp waarnaar het apparaat luistert. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | MesUDID | De UDID van het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | OSVersion | De versie van het besturingssysteem van het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | BuildVersion | De buildversie van het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | ProductName | De productnaam van het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | SerialNumber | Het serienummer van het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | IMEI | De IMEI-id (International Mobile Station Equipment) van het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Authenticate | MEID | De MEID (Mobile Equipment Identifier) van het apparaat |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Onderwerp | Het onderwerp waarnaar het apparaat luistert. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | udid | De UDID van het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | Token | Het pushtoken voor het apparaat. De server moet dit bijgewerkte token gebruiken bij het verzenden van pushmeldingen naar het apparaat. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | PushMagic | De magic-tekenreeks die moet worden opgenomen in de pushmelding.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | UnlockToken | Een gegevens-blob die kan worden gebruikt om het apparaat te ontgrendelen. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | TokenUpdate | AwaitingConfiguration | Indien ingesteld op 'true', wacht het apparaat op een DeviceConfigured MDM-opdracht voordat u doorgaat met de Setup-assistent.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Checkout | MessageType | Het berichttype: uitchecken. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Checkout | Onderwerp | Het onderwerp waarnaar het apparaat luistert. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Checkout | udid | De UDID van het apparaat |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protocol | Status | Status.  |
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protocol | udid |De UDID van het apparaat.  |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protocol | CommandUUID | UUID van de opdracht waarvoor deze reactie is. |
| [APNs](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | MDM Protocol | ErrorChain | Matrix van woordenlijsten die de keten van fouten vertegenwoordigt die zijn opgetreden.  |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Serienummer | Het serienummer van het apparaat. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | model | De modelnaam van het apparaat. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Beschrijving | Een beschrijving van het apparaat. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Kleur | De kleur van het apparaat. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Asset tag | De inventaristag van het apparaat. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Profile status | De status van de profielinstallatie. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Profile UUID | De UUID van het toegewezen profiel. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Profile assign time | Een tijdstempel in ISO 8601-notatie die aangeeft wanneer een profiel is toegewezen aan het apparaat. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Profile push time | Een tijdstempel in ISO 8601-notatie die aangeeft wanneer een profiel naar het apparaat is gepusht.|
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Device assigned date | Een tijdstempel in ISO 8601-notatie die aangeeft wanneer het apparaat is geregistreerd bij het Device Enrollment Program. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Device assigned by | Het e-mailadres van de persoon die het apparaat heeft toegewezen. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Besturingssysteem | Het besturingssysteem van het apparaat. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Enrollment Program token | Device family | De Apple-productfamilie van het apparaat. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | Apple User ID | Een gebruikers-id die is gegenereerd door Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | application description | De beschrijving van een VPP-toepassing. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | application icon | De URL van een door Apple gehost pictogram voor een VPP-app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | Application Id | Apple-toepassings-id, ook wel bekend als adamsId. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | application name | De naam van een VPP-toepassing. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | assignedCount | Het aantal toegewezen licenties voor een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | availableCount | Het aantal licenties waarvan de toewijzing ongedaan is gemaakt voor een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | bundleId | De bundel-id van een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | auteursrecht | De auteursrechtinformatie van een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | CountryCode | De landcode van een VPP-programma. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | deviceAssignable | Apple retourneert 'true' als de beheerder een apparaatlicentie voor een app kan toewijzen. Als dat niet het geval is, wordt 'false' geretourneerd. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | facilitatorMemberId | De lid-id van een VPP-accountfacilitator.  |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | genres | De genres van een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | Intune UserId guid | De GUID die is gegenereerd door Intune. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | isIrrevocable | Apple retourneert 'true' als de licentie niet kan worden ingetrokken. Als deze kan worden ingetrokken, wordt 'false' geretourneerd. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | License Id | De id die wordt gegenereerd door Apple voor het identificeren van een bepaalde licentie. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | Locatie | De locatie die is opgeslagen in de VPP-configuratiegegevens van Apple. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | Managed AppleId UPN | Het e-mailadres van de Apple-id voor de gebruiker, de beheerder en het facilitatorlid. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | OrganizationId | De door Apple toegewezen organisatie-id. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | pricingParam | Het Apple-prijstype voor een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | productType | Het producttype van een VPP-toepassing. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | retiredCount | Het aantal ingetrokken licenties voor een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | totalCount | Het totale aantal aangeschafte licenties voor een app. |
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | URL | De URL naar de iTunes Store van een app.|
| [VPP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/5-Web_Service_Protocol_VPP/webservice.html#//apple_ref/doc/uid/TP40017387-CH8-SW1) | Apple VPP Token | User Status | De gebruikersstatus in Apple VPP-programma's. |


Als u geen Apple-services meer wilt gebruiken met Microsoft Intune en u de gegevens wilt verwijderen, moet u zowel De Microsoft Intune Apple-token uitschakelen als uw Apple-account verwijderen. In uw Apple-account vindt u meer informatie over accountbeheer.


