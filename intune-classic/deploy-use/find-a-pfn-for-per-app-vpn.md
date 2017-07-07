---
title: Een familienaam van een pakket (PFN) zoeken voor VPN per app
description: Een PFN zoeken, zodat u VPN per app kunt configureren.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: eea3b9e2888f07399c8cda1e81ae8a5318d02d42
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a>Een Package Family Name (PFN) voor de configuratie van VPN per app zoeken

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Er zijn twee manieren om een PFN te zoeken, zodat u een VPN per app kunt instellen.

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a>Een PFN zoeken voor een app die is geïnstalleerd op een Windows 10-computer

Als de app waarmee u werkt, al is geïnstalleerd op een Windows 10-computer, kunt u de PowerShell-cmdlet [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) gebruiken om de PFN op te halen.

De syntaxis voor Get-AppxPackage is:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
Mogelijk moet u PowerShell uitvoeren als een beheerder om de PFN op te halen.

Als u bijvoorbeeld informatie wilt ophalen over alle universele apps die op uw computer zijn geïnstalleerd, gebruikt u `Get-AppxPackage`.

Voor informatie over een app waarvan u de naam of een deel van de naam weet, gebruikt u `Get-AppxPackage *<app_name>`. Als u niet zeker weet wat de volledige naam van de app is, kunt u het jokerteken gebruiken. Als u bijvoorbeeld informatie voor OneNote wilt ophalen, gebruikt u `Get-AppxPackage *OneNote`.


Hier vindt u de informatie die is opgehaald voor OneNote:

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a>Een PFN zoeken als de niet op een computer is geïnstalleerd

1.  Ga naar https://www.microsoft.com/store/apps.
2.  Typ de naam van de app in de zoekbalk. In het voorbeeld wordt gezocht naar OneNote.
3.  Kies de koppeling naar de app. U ziet dat de URL een reeks letters heeft aan het eind. In het voorbeeld ziet de URL er als volgt uit: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.
4.  Plak de volgende URL in een ander tabblad: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`. Vervang `<app id>` door de app-id die u hebt verkregen via https://www.microsoft.com/store/apps: de reeks letters aan het eind van de URL in stap 3. In het voorbeeld voor OneNote plakt u het volgende: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

In Microsoft Edge wordt de gewenste informatie weergegeven. In Internet Explorer moet u **Openen** kiezen om de informatie weer te geven. De PFN-waarde wordt weergegeven op de eerste regel. Hier zijn de resultaten voor het voorbeeld:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
