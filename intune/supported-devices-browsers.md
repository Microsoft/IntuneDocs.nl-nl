---
title: Ondersteunde apparaten - Microsoft Intune
description: Een lijst met ondersteunde apparaatplatformen en browsers voor het beheer van Intune-apparaten
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/22/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4cfdf6a8aab1bda15015f85b1fb8f364e6a0edfa
ms.sourcegitcommit: 29ee35da2864b25f4432d2423b285014c77040af
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/23/2017
---
# <a name="supported-devices-and-browsers"></a>Ondersteunde apparaten en browsers

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Dit artikel is bedoeld voor systeembeheerders die verantwoordelijk zijn voor het beheer van apparaten in de onderneming. Zie [Werk gedaan krijgen met beheerde apparaten](/intune-user-help/company-portal-frequently-asked-questions) voor meer informatie over de installatie van Intune op uw telefoon.

Bekijk de volgende vereisten voordat u Microsoft Intune instelt:

- [Ondersteunde apparaten en computers](#intune-supported-devices)
- [Een overzicht van ondersteunde webbrowsers voor Intune](#intune-supported-web-browsers)

Maak uzelf ook vertrouwd met het [bandbreedtegebruik van het Intune-netwerk](network-bandwidth-use.md) ([klassieke portal](/intune-classic/get-started/network-bandwidth-use)).

## <a name="intune-supported-devices"></a>Ondersteunde apparaten voor Intune

U kunt de volgende apparaten beheren met Intune Mobile Device Management:

[!INCLUDE[mdm-supported-devices](./includes/mdm-supported-devices.md)]

Intune kan niet worden gebruikt voor het beheren van Windows Server-besturingssystemen.

### <a name="windows-pc-software-client"></a>Softwareclient voor Windows-pc's

Een [Intune-softwareclient](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) kan als een alternatieve registratiemethode worden geïmplementeerd en geïnstalleerd op Windows-pc's. Deze functionaliteit is alleen beschikbaar voor de klassieke Intune-portal. U kunt de Intune-softwareclient gebruiken om pc's met Windows 7 en hoger te beheren, met uitzondering van Windows 10 Home.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Door Intune ondersteunde webbrowsers

Voor de verschillende beheertaken moet u een van de volgende beheerwebsites gebruiken.

- [Office 365-portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure Portal](https://portal.azure.com/)

De volgende browsers worden ondersteund voor deze portals:
- Microsoft Edge (meest recente versie)
- Microsoft Internet Explorer 11
- Safari (meest recente versie, alleen Mac)
- Chrome (meest recente versie)
- Firefox (meest recente versie)

### <a name="intune-classic-portal"></a>Klassieke Intune-portal

De Intune-functies die alleen kunnen worden gebruikt in combinatie met de klassiek versie van Intune, zoals Intune PC-softwareclient en de integratie met Mobile Threat Defense-partners, zijn alleen beschikbaar in de klassieke Intune-portal (https://manage.microsoft.com). De klassieke Intune-portal vereist ondersteuning van de Silverlight-browser.

De volgende Silverlight-browsers ondersteunen de Intune-console:
- Internet Explorer 10 of hoger
- Google Chrome (versies voorafgaand aan versie 42)
- Mozilla Firefox met Silverlight ingeschakeld [Meer informatie](https://go.microsoft.com/fwlink/?linkid=836872)

> [!Note]
> Microsoft Edge en mobiele browsers worden niet ondersteund voor de klassieke Intune-portal, omdat ze geen ondersteuning bieden voor [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Alleen gebruikers met servicebeheerdersmachtigingen en tenantbeheerders met de rol Algemene beheerder kunnen zich bij deze portal aanmelden. Voor toegang tot de beheerconsole moet uw account een licentie voor het gebruik van Intune en de aanmeldingsstatus **Toegestaan** hebben.
