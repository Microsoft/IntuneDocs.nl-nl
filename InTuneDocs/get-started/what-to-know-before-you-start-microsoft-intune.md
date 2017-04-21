---
title: Ondersteunde apparaten - Microsoft Intune | Microsoft Docs
description: Een lijst met ondersteunde apparaatplatformen en browsers voor het beheer van Intune-apparaten
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: 0fa045d31125ba0d67f19bb46aa2728ae9bbcc93
ms.lasthandoff: 04/14/2017


---

# <a name="supported-devices-and-browsers"></a>Ondersteunde apparaten en browsers

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Dit artikel is bedoeld voor systeembeheerders die verantwoordelijk zijn voor het beheer van apparaten in de onderneming. Zie [Werk gedaan krijgen met beheerde apparaten](https://docs.microsoft.com/intune/enduser/company-portal-frequently-asked-questions) voor meer informatie over de installatie van Intune op uw telefoon.

Bekijk de volgende vereisten voordat u Microsoft Intune instelt:

- [Ondersteunde apparaten en computers](#intune-supported-devices)
- [Een overzicht van ondersteunde webbrowsers voor Intune](#intune-supported-web-browsers)

Maak uzelf ook vertrouwd met het [bandbreedtegebruik van het Intune-netwerk](network-bandwidth-use.md).

## <a name="intune-supported-devices"></a>Ondersteunde apparaten voor Intune

U kunt de volgende apparaten beheren met Intune Mobile Device Management:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Intune kan niet worden gebruikt voor het beheren van Windows Server-besturingssystemen.

Intune-apparaatbeheer biedt [deze mogelijkheden](mobile-device-management-capabilities-in-microsoft-intune.md).

### <a name="windows-pc-software-client"></a>Softwareclient voor Windows-pc's

Een [Intune-softwareclient](/intune/deploy-use/manage-windows-pcs-with-microsoft-intune) kan als een alternatieve registratiemethode worden geïmplementeerd en geïnstalleerd op Windows-pc's. U kunt de Intune-softwareclient gebruiken om pc's met Windows 7 en hoger te beheren, met uitzondering van Windows 10 Home. Als u pc‘s beheert met de clientsoftware, kunt u gebruikmaken van de [volgende mogelijkheden](windows-pc-management-capabilities-in-microsoft-intune.md).

### <a name="exchange-activesync-management"></a>Exchange ActiveSync-beheer

U kunt [Exchange ActiveSync-apparaten](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) via de Intune-console. Deze optie biedt een beperkt set beheermogelijkheden in vergelijking met de andere methoden. Zie [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) (Mogelijkheden van ingebouwd Mobile Device Management in Office 365) voor een overzicht van ondersteunde apparaten.

## <a name="intune-supported-web-browsers"></a>Door Intune ondersteunde webbrowsers

Voor de verschillende beheertaken moet u een van de volgende beheerwebsites gebruiken.

- [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Microsoft Intune-beheerdersconsole](https://admin.manage.microsoft.com/)

|Intune-functie |Ondersteunde browsers|
|---------|---------|
|**Intune-beheerconsole**     |  Internet Explorer 10 of hoger<br /><br />Google Chrome (versies voorafgaand aan versie 42)<br /><br />Mozilla Firefox met Silverlight ingeschakeld<br />**Opmerking:** Mozilla biedt vanaf maart 2017 geen ondersteuning meer voor Silverlight. [Meer informatie](https://go.microsoft.com/fwlink/?linkid=836872). |
|**Office 365-beheerportal**     |Alle browsers, inclusief mobiele browsers en beheerde browsers  |
|**Bedrijfsportalwebsite**     |**Op mobiele apparaten:** gebruik de standaardwebbrowser voor elk ondersteund platform   <br /><br />**Op Windows-pc's:** Internet Explorer 10 of hoger, of Microsoft Edge<br /><br />**Mac OS X 10.9 of hoger:** Apple Safari    |

> [!Note]
> Microsoft Edge en mobiele browsers worden niet ondersteund voor de beheerconsole omdat ze geen ondersteuning bieden voor [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx). De Intune-console zal op een gegeven moment geen ondersteuning meer bieden voor Silverlight. Uiteindelijk worden alle Intune-functies voor het beheer van mobiele apparaten en toepassingen [beschikbaar gesteld in de nieuwe Microsoft Azure-portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).


Alleen gebruikers met servicebeheerdersmachtigingen en tenantbeheerders met de rol Algemene beheerder kunnen zich bij deze portal aanmelden. Voor toegang tot de beheerconsole moet uw account een licentie voor het gebruik van Intune en de aanmeldingsstatus **Toegestaan** hebben.

>[!div class="step-by-step"]

>[**Netwerken** &rarr;](network-bandwidth-use.md)  

