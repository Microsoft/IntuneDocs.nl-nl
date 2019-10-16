---
title: Besturingssystemen en browsers die worden ondersteund door Microsoft Intune
titleSuffix: ''
description: Een lijst met ondersteunde apparaatplatformen en browsers voor het beheer van Intune-apparaten
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5d1ac59c-a885-4276-8576-f3cf81c2d268
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d2777f2caabc24a457fc407b3e47facb1f6fc3c
ms.sourcegitcommit: 45d7c76e760c5117bf134fb57f7e248e5b6c4ad5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2019
ms.locfileid: "72314607"
---
# <a name="supported-operating-systems-and-browsers-in-intune"></a>Ondersteunde besturingssystemen en browsers in Intune

Bestudeer, voordat u Microsoft Intune instelt, de ondersteunde besturingssystemen en browsers.

Raadpleeg voor hulp bij de installatie van Intune op uw apparaat [Beheerde apparaten gebruiken om werk gedaan te krijgen](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions) en [Bandbreedtegebruik](network-bandwidth-use.md).

Voor meer informatie over ondersteuning door de configuratie-serviceprovider, gaat u naar de [referentie van de configuratie-serviceprovider](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="intune-supported-operating-systems"></a>Besturingssystemen die door Intune worden ondersteund

U kunt apparaten met de volgende besturingssystemen beheren:

[!INCLUDE [mdm-supported-devices](../../intune-classic/includes/mdm-supported-devices.md)]

### <a name="supported-samsung-knox-standard-devices"></a>Ondersteunde Samsung Knox Standard-apparaten

Via de bedrijfsportal-app wordt de Samsung Knox-activering alleen uitgevoerd tijdens MDM-inschrijving als het apparaat wordt weergegeven in de [lijst met ondersteunde Knox-apparaten](https://www.samsungknox.com/knox-supported-devices/knox-workspace), ter vermijding van fouten bij de Knox-activering, waardoor MDM-inschrijving niet mogelijk is. Apparaten die geen ondersteuning bieden voor Samsung Knox-activering, worden geregistreerd als standaard-Android-apparaten. Bepaalde modelnummers van Samsung-apparaten bieden ondersteuning voor Knox, andere niet. Controleer de KNOX-compatibiliteit bij de verkoper van uw apparaat voordat u Samsung-apparaten koopt en implementeert.

> [!NOTE]
> Voor het registreren van Samsung Knox-apparaten moet u wellicht [toegang tot Samsung-servers inschakelen](https://support.samsungknox.com/hc/articles/115013833108-Our-corporate-devices-are-behind-a-firewall-How-do-I-enable-Knox-Workspace-devices-to-contact-Samsung-servers). 

De volgende lijst van Samsung-apparaatmodellen bieden geen ondersteuning voor Knox. Deze zijn geregistreerd als systeemeigen Android-apparaten door de bedrijfsportal-app voor Android:

| **Apparaatnaam** | **Apparaatmodelnummers** |
| --- | --- |
| Galaxy Avant | SM-G386T |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W |
| Galaxy S6 Edge | 404SC |
| Galaxy Tab A 7.0&quot; | SM-T280<br>SM-T285 |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116<br>SM-T210<br>SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |


### <a name="windows-pc-software-client"></a>Softwareclient voor Windows-pc's

Een [Intune-softwareclient](../manage-windows-pcs-with-microsoft-intune.md) kan als een alternatieve registratiemethode worden geïmplementeerd en geïnstalleerd op Windows-pc's. Deze functionaliteit is alleen beschikbaar voor de klassieke Intune-portal. U kunt de Intune-softwareclient gebruiken om pc's met Windows 7 en hoger te beheren, met uitzondering van Windows 10 Home.

<!--  ### Exchange ActiveSync management

You can manage [Exchange ActiveSync devices](../enrollment/device-enrollment.md#mobile-device-management-with-exchange-activesync-and-intune) from the Intune console. This option provides a limited set of management capabilities when compared to the other methods. See [Capabilities of built-in Mobile Device Management in Office 365](https://support.office.com/article/Capabilities-of-built-in-Mobile-Device-Management-for-Office-365-a1da44e5-7475-4992-be91-9ccec25905b0) for a list of supported devices.  -->

## <a name="intune-supported-web-browsers"></a>Door Intune ondersteunde webbrowsers

Voor de verschillende beheertaken moet u een van de volgende beheerwebsites gebruiken.

- [Microsoft 365-beheercentrum](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Azure Portal](https://portal.azure.com/)

De volgende browsers worden ondersteund voor deze portals:
- Microsoft Edge (meest recente versie)
- Microsoft Internet Explorer 11
- Safari (meest recente versie, alleen Mac)
- Chrome (meest recente versie)
- Firefox (meest recente versie)




### <a name="intune-classic-portal"></a>Klassieke Intune-portal

De klassieke Intune-portal wordt alleen gebruikt voor het beheren van apparaten die zijn ingeschreven bij de Intune-softwareclient voor pc's (https://manage.microsoft.com). De klassieke Intune-portal vereist ondersteuning van de Silverlight-browser.

De volgende Silverlight-browsers ondersteunen de Intune-console:
- Internet Explorer 10 of hoger
- Google Chrome (versies voorafgaand aan versie 42)
- Mozilla Firefox met Silverlight ingeschakeld (versies vóór versie 56)

> [!Note]
> Microsoft Edge en mobiele browsers worden niet ondersteund voor de klassieke Intune-portal, omdat ze geen ondersteuning bieden voor [Microsoft Silverlight](https://msdn.microsoft.com/library/cc838158(v=vs.95).aspx).

Alleen gebruikers met servicebeheerdersmachtigingen en tenantbeheerders met de rol Algemene beheerder kunnen zich bij deze portal aanmelden. Voor toegang tot de beheerconsole moet uw account een licentie voor het gebruik van Intune en de aanmeldingsstatus **Toegestaan** hebben.
