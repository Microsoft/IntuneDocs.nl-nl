---
title: Beheeropties voor Windows-pc's vergelijken
description: iOS-apparaten in bedrijfseigendom inschrijven met het Apple Device Enrollment Program (DEP) of Apple Configurator
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 068a73bb-e6b3-44a6-8f6e-4cf7d455bbf3
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8f6de91724db10ef64e2c1fd6eee6101c6eac79a
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="compare-managing-windows-pcs-as-computers-or-mobile-devices"></a>Het beheer van Windows-pc's als computers of mobiele apparaten vergelijken

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Organisaties kunnen Microsoft Intune gebruiken voor het beheren van Windows-pc's als mobiele apparaten met Mobile Device Management (MDM) of als computers met de Intune-softwareclient.  Microsoft adviseert klanten om indien mogelijk de MDM-beheeroplossing te gebruiken. Als u wilt weten wat de verschillen zijn tussen deze opties, kunt u het volgende diagram bekijken waarin de twee beheeropties worden vergeleken.

|**Mogelijkheid/Scenario** |**Windows als computer**<br>Intune-softwareclient | **Windows als mobiel apparaat**<br>MDM |
|--------------|-------------------------------|-------------------------------|
|**Besturingssystemen** |Windows 10, Windows 8+, Windows 7, Windows Vista | Windows 10+ |
|**Intune Portal-ondersteuning** |[Silverlight-console](https://manage.microsoft.com)|[Azure Portal](https://portal.azure.com) |
|**Voorwaardelijke toegang**|Niet beschikbaar|Beschikbaar <br>[Wat is voorwaardelijke toegang?](https://docs.microsoft.com/intune-azure/conditional-access/what-is-conditional-access)|
|**Bulkinschrijving**|Niet beschikbaar|Beschikbaar <br>[Bulkinschrijving voor Windows-apparaten](https://docs.microsoft.com/intune-azure/enroll-devices/bulk-enroll-windows)|
|**Apparaatprofielen**|Niet beschikbaar|Beschikbaar <br>[Wat zijn Microsoft Intune-apparaatprofielen?](https://docs.microsoft.com/intune-azure/configure-devices/what-are-device-profiles)|
|**Inschrijving zonder agent**|Niet beschikbaar |Beschikbaar<br>[Windows-apparaten inschrijven](https://docs.microsoft.com/intune-azure/enroll-devices/enroll-windows-devices)|
|**Beheer van software-updates**| Windows-updates en updates voor Microsoft-apps<br>[Windows-pc's up-to-date houden met software-updates](https://docs.microsoft.com/intune/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)|Microsoft Store voor Bedrijven voor Windows 10-updates en updates voor Microsoft-apps<br> [Instellingen voor Windows Update voor bedrijven configureren](https://docs.microsoft.com/intune-azure/configure-devices/how-to-configure-windows-update-for-business) |
|**Softwarelicentiebeheer**|Beschikbaar <br>[Licentieovereenkomsten voor Windows-pc-software beheren](https://docs.microsoft.com/intune/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)|Microsoft Store voor Bedrijven (alleen .appx-apps)<br>[Apps beheren die zijn aangeschaft in Microsoft Store voor Bedrijven](https://docs.microsoft.com/intune-azure/manage-apps/wsfb-apps)|
|**Inventaris**|Beschikbaar <br>[Hardware- en software-inventaris voor Windows-pc's weergeven](https://docs.microsoft.com/intune/deploy-use/view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune)|Beschikbaar <br>[App-gegevens controleren](https://docs.microsoft.com/intune/apps-monitor)<br>[Wat is apparaatbeheer](https://docs.microsoft.com/intune/device-management)|
|**Windows-firewallbeleid**|Beschikbaar <br>[Windows-pc's beschermen met Windows Firewall-beleid](https://docs.microsoft.com/intune/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune) |Niet beschikbaar|
|**Antimalwarebeveiliging**|Endpoint Protection<br>[Voor een betere beveiliging van Windows-pc's zorgen met Endpoint Protection](https://docs.microsoft.com/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)|Windows Defender<br>[Windows Defender-instellingen](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-windows-10#windows-defender-settings)|
|**Hulp op afstand** |TeamViewer<br>[Hulp op afstand voor Windows-pc's aanvragen en bieden](https://docs.microsoft.com/intune/deploy-use/request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune)|Niet beschikbaar |
|**App-implementatie** | Niet beschikbaar voor Microsoft Store voor Bedrijven,<br>alleen .exe, .appx, en .msi die uit meerdere bestanden bestaat<br>[Apps toevoegen voor Windows-pc's met de Intune-softwareclient ](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)|Beschikbaar voor Microsoft Store-apps en Line-Of-Business-apps<br>[Windows Store-apps toevoegen](https://docs.microsoft.com/intune/store-apps-windows)<br>[Windows-Line-Of-Business (LOB)-apps toevoegen](https://docs.microsoft.com/intune/lob-apps-windows)|
|**App-beveiliging**|Niet beschikbaar|Beschikbaar <br>[Wat zijn beleidsregels voor de beveiliging van apps?](https://docs.microsoft.com/intune-azure/manage-apps/what-is-app-protection-policy)|
|**Health Attestation**|Niet beschikbaar|Beschikbaar|


### <a name="advantages-of-mdm-windows-pc-management"></a>Voordelen van MDM-beheer voor Windows-pc's
Het beheer van Windows-pc's met het moderne Mobile Device Management heeft de volgende voordelen:
- **Schaalbaarheid**: MDM-beheer kan worden opgeschaald voor Intune-cloudbeheer. De Intune-softwareclient is beperkt tot 7000 pc's.
- **Eenvoud**: maakt gebruik van moderne beheermogelijkheden van het besturingssysteem zonder afhankelijk te zijn van een gedownloade softwareclient
- **Consistentie**: uw Windows-pc's worden beheerd zoals alle andere mobiele apparaten in uw organisatie
<!-- - **Cloud optimization** - -->
