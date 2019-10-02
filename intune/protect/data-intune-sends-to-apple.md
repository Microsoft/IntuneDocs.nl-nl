---
title: Gegevens die Intune naar Apple verzendt
titleSuffix: Microsoft Intune
description: Lijst met gegevens die door Intune worden verzonden naar Apple.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b204a956-18ec-11e8-accf-0ed5f89f718b
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bbd0f0cafdf6de6b067e1350ce4c61e0980660d2
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722511"
---
# <a name="data-intune-sends-to-apple"></a>Gegevens die Intune naar Apple verzendt

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Als een van de volgende Apple-services wordt ingeschakeld op een apparaat, maakt Microsoft Intune verbinding met Apple en worden er gebruikers- en apparaatgegevens gedeeld met Apple: 

- [Apple Device Enrollment Program (DEP)](../enrollment/device-enrollment-program-enroll-ios.md)
- [Apple MDM-pushcertificaat (APNS)](../enrollment/apple-mdm-push-certificate-get.md)
- [Apple School Manager (ASM)](https://docs.microsoft.com/schooldatasync/apple-school-manager-integration-with-intune-for-education-and-school-data-sync)
- [Apple Volume Purchase Program (VPP)](../apps/vpp-apps-ios.md)

Voordat Microsoft Intune verbinding kan maken, moet u een Apple-account maken voor elk van de Apple-services.

In de volgende tabel staat welke gegevens Microsoft Intune vanaf een apparaat verzendt naar de ingeschakelde Apple-services. 

| Service | Gegevens die worden verzonden naar Apple | Gebruikt voor |
|---|---| ---|
| [APNS](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Token, PushMagic | Als de server het apparaat accepteert, pusht het apparaat zelf een apparaattoken naar de server. De server moet deze token gebruiken om pushmeldingen naar het apparaat te verzenden. Dit incheckbericht bevat ook een PushMagic-tekenreeks. De server moet deze tekenreeks onthouden en deze insluiten in alle pushmeldingen die naar het apparaat worden verzonden. |
| [ASM/DEP](https://developer.apple.com/library/content/documentation/Miscellaneous/Reference/MobileDeviceManagementProtocolRef/3-MDM_Protocol/MDM_Protocol.html#//apple_ref/doc/uid/TP40017387-CH3-SW2) | Servertoken | Pushmelding met apparaattoken, gebruikt voor verificatie met de Apple-service. |
| ASM/DEP | servernaam | Een herleidbare naam voor de MDM-server. |
| ASM/DEP | server_uuid | Een server-id die door het systeem is gegenereerd. |
| ASM/DEP | admin_id | De Apple-id van de persoon die de tokens heeft gegenereerd die nu worden gebruikt. |
| ASM/DEP | org_name | De naam van de organisatie. |
| ASM/DEP | org_email | Het e-mailadres van de organisatie. |
| ASM/DEP | org_phone | Het telefoonnummer van de organisatie. |
| ASM/DEP | org_address | Het adres van de organisatie. |
| ASM/DEP | org_id | De DEP-klant-id. Deze sleutel is alleen beschikbaar in protocol versie 3 en hoger. |
| ASM/DEP | serial_number | Het serienummer van het apparaat (tekenreeks). |
| ASM/DEP | model | De naam van het model (tekenreeks). |
| ASM/DEP | description | Een beschrijving van het apparaat (tekenreeks). |
| ASM/DEP | asset_tag | De inventaristag van het apparaat (tekenreeks). |
| ASM/DEP | profile_status | De status van de profielinstallatie. Mogelijke waarden: **empty**, **assigned**, **pushed** of **removed**. |
| ASM/DEP | profile_uuid | De unieke id van het toegewezen profiel. |
| ASM/DEP | device_assigned_by | Het e-mailadres van de persoon die het apparaat heeft toegewezen. |
| ASM/DEP | os | Het besturingssysteem van het apparaat: iOS, OSX of tvOS. Deze sleutel is geldig in X-Server-Protocol-Version 2 en hoger. |
| ASM/DEP | device_family | De Apple-productfamilie van het apparaat: iPhone, iPad, iPod, Mac of AppleTV. Deze sleutel is geldig in X-Server-Protocol-Version 2 en hoger. |
| ASM/DEP | profile_name | Tekenreeks. Een leesbare naam voor het profiel. |
| ASM/DEP | support_phone_number | Optioneel. Tekenreeks. Een ondersteuningstelefoonnummer voor de organisatie. |
| ASM/DEP | support_email_address | Optioneel. Tekenreeks. Een ondersteuningse-mailadres voor de organisatie. Deze sleutel is geldig in X-Server-Protocol-Version 2 en hoger. |
| ASM/DEP | afdeling | Optioneel. Tekenreeks. De door de gebruiker gedefinieerde afdeling of de locatienaam. |
| ASM/DEP | devices | Matrix met tekenreeksen met serienummers van apparaten. (Mag leeg zijn.) |
| VPP | Intune UserId guid | GUID gegenereerd door Intune. |
| VPP | Managed AppleId UPN | De Apple-id die is opgegeven door de beheerder tijdens het configureren van de VPP-tokenverbinding met Apple. |
| VPP | Serienummer | Het serienummer van het beheerde apparaat. |

Als u geen Apple-services meer wilt gebruiken met Microsoft Intune en u de gegevens wilt verwijderen, moet u zowel De Microsoft Intune Apple-token uitschakelen als uw Apple-account verwijderen. In uw Apple-account vindt u meer informatie over accountbeheer.


