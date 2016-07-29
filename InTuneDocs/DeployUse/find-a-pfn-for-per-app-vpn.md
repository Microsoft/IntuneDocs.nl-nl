---
title: Een Package Family Name (PFN) voor VPN per app zoeken |Microsoft Intune
description: Een PFN zoeken, zodat u VPN per app kunt configureren.
keywords: 
author: nbigman
manager: angrobe
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9a124663a80bb477d0312faa0fb43e4457ba8246
ms.openlocfilehash: 0bbb8aef7929ac09ef5f6a5a466d66b5df03e921


---

# Een Package Family Name (PFN) voor de configuratie van VPN per app zoeken

Er zijn twee manieren om een PFN te zoeken, zodat u VPN per app kunt configureren.

## Een PFN zoeken voor een app die is geïnstalleerd op een Windows 10-computer

Als de app waarmee u werkt, al is geïnstalleerd op een Windows 10-computer, kunt u de PowerShell-cmdlet [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) gebruiken om de PFN op te halen.

De syntaxis voor Get-AppxPackage is:

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> Opmerking: mogelijk moet u PowerShell uitvoeren als een beheerder om de PFN op te halen.

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



## Een PFN zoeken als de niet op een computer is geïnstalleerd

1.  Ga naar https://www.microsoft.com/nl-nl/store/apps.
2.  Typ de naam van de app in de zoekbalk. In het voorbeeld wordt gezocht naar OneNote.
3.  Klik op de koppeling naar de app. De URL die u opent heeft een reeks letters aan het eind. In het voorbeeld ziet de URL er als volgt uit:
`https://www.microsoft.com/en-us/store/apps/onenote/9wzdncrfhvjl`
4.  Plak de URL `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata` in een ander tabblad en vervang `<app id>` door de app-id die u hebt verkregen via https://www.microsoft.com/nl-nl/store/apps (reeks letters aan het einde van de URL in stap 3). In het voorbeeld voor OneNote plakt u het volgende: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.

In Edge wordt de gewenste informatie weergegeven. In Internet Explorer klikt u op **Openen** om de informatie weer te geven. De PFN-waarde wordt weergegeven op de eerste regel. De resultaten voor het voorbeeld zien er als volgt uit:


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`



<!--HONumber=Jul16_HO4-->


