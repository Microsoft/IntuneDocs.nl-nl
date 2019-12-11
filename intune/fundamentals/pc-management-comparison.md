---
title: Beheeropties voor Windows-pc's vergelijken
titleSuffix: Microsoft Intune
description: iOS-apparaten in bedrijfseigendom inschrijven met het Apple Device Enrollment Program (DEP) of Apple Configurator.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/13/2018
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: d8fd53e9d12dd38639d204e214aea03d733e584b
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059203"
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Het beheer van Windows-pc's als computers of mobiele apparaten vergelijken

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Organisaties kunnen Microsoft Intune gebruiken voor het beheren van Windows-pc's als mobiele apparaten met Mobile Device Management (MDM) of als computers met de Intune-softwareclient.  Microsoft adviseert klanten om indien mogelijk de MDM-beheeroplossing te gebruiken. Als u wilt weten wat de verschillen zijn tussen deze opties, kunt u het volgende diagram bekijken waarin de twee beheeropties worden vergeleken.

|**Mogelijkheid/Scenario** |**Windows als computer**<br>Intune-softwareclient | **Windows als mobiel apparaat**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Besturingssystemen** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Intune Portal-ondersteuning** |[Silverlight-console](https://manage.microsoft.com)|[Azure Portal](https://portal.azure.com) |
|**Voorwaardelijke toegang**|Niet beschikbaar|Beschikbaar <br>[Wat is voorwaardelijke toegang?](../protect/conditional-access.md)|
|**Bulkinschrijving**|Niet beschikbaar|Beschikbaar <br>[Bulkinschrijving voor Windows-apparaten](../enrollment/windows-bulk-enroll.md)|
|**Apparaatprofielen**|Niet beschikbaar|Beschikbaar <br>[Wat zijn Microsoft Intune-apparaatprofielen?](../configuration/device-profiles.md)|
|**Inschrijving zonder agent**|Niet beschikbaar |Beschikbaar<br>[Windows-apparaten inschrijven](../enrollment/windows-enroll.md)|
|**Beheer van software-updates**| Windows-updates en updates voor Microsoft-apps<br>[Windows-pc's up-to-date houden met software-updates](../keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md)|Microsoft Store voor Bedrijven voor Windows 10-updates en updates voor Microsoft-apps<br> [Instellingen voor Windows Update voor bedrijven configureren](../protect/windows-update-for-business-configure.md) |
|**Softwarelicentiebeheer**|Beschikbaar <br>[Licentieovereenkomsten voor Windows-pc-software beheren](../manage-license-agreements-for-windows-pc-software-in-microsoft-intune.md)|Microsoft Store voor Bedrijven (alleen .appx-apps)<br>[Apps beheren die zijn aangeschaft in Microsoft Store voor Bedrijven](../apps/windows-store-for-business.md)|
|**Inventaris**|Beschikbaar <br>[Hardware- en software-inventaris voor Windows-pc's weergeven](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md)|Beschikbaar <br>[App-gegevens controleren](../apps/apps-monitor.md)<br>[Wat is apparaatbeheer](../remote-actions/device-management.md)|
|**Windows-firewallbeleid**|Beschikbaar <br>[Windows-pc's beschermen met Windows Firewall-beleid](../help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) |Beschikbaar <br>[Micro soft Defender firewall](../protect/endpoint-protection-windows-10.md#microsoft-defender-firewall)|
|**Antimalwarebeveiliging**|Endpoint Protection<br>[Voor een betere beveiliging van Windows-pc's zorgen met Endpoint Protection](../help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md)|Microsoft Defender<br>[Micro soft Defender inschakelen](../protect/advanced-threat-protection.md)|
|**Hulp op afstand** |TeamViewer<br>[Hulp op afstand voor Windows-pc's aanvragen en bieden](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md)|TeamViewer<br> [TeamViewer gebruiken voor het extern beheren van Intune-apparaten](../remote-actions/teamviewer-support.md) |
|**App-implementatie** | Niet beschikbaar voor Microsoft Store voor Bedrijven,<br>alleen .exe, .appx, en .msi die uit meerdere bestanden bestaat<br>[Apps toevoegen voor Windows-pc's met de Intune-softwareclient ](add-apps-for-windows-pcs-in-microsoft-intune.md)|Beschikbaar voor Microsoft Store-apps en Line-Of-Business-apps<br>[Windows Store-apps toevoegen](../apps/store-apps-windows.md)<br>[Windows-Line-Of-Business (LOB)-apps toevoegen](../apps/lob-apps-windows.md)|
|**App-beveiliging**|Niet beschikbaar|Beschikbaar <br>[Wat zijn beleidsregels voor de beveiliging van apps?](../apps/app-protection-policy.md)|
|**Health Attestation**|Niet beschikbaar|Beschikbaar|


## <a name="advantages-of-mdm-windows-pc-management"></a>Voordelen van MDM-beheer voor Windows-pc's
Het beheer van Windows-pc's met het moderne Mobile Device Management heeft de volgende voordelen:
- **Schaalbaarheid**: MDM-beheer kan worden opgeschaald voor Intune-cloudbeheer. De Intune-softwareclient is beperkt tot 7000 pc's.
- **Eenvoud**: maakt gebruik van moderne beheermogelijkheden van het besturingssysteem zonder afhankelijk te zijn van een gedownloade softwareclient
- **Consistentie**: uw Windows-pc's worden beheerd zoals alle andere mobiele apparaten in uw organisatie
<!-- - **Cloud optimization** - -->
