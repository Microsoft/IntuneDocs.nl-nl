---
# required metadata

title: PowerShell-referentie voor aangepaste sjablonen | Azure RMS
description:
keywords:
author: cabailey
manager: mbaldwin
ms.date: 05/20/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 30ee2f77-ce16-4113-bcda-6089131849ec

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---



# PowerShell-referentie voor aangepaste sjablonen

*Van toepassing op: Azure Rights Management, Office 365*

Alles wat u kunt doen in de klassieke Azure-portal om sjablonen te maken en beheren, kunt u met behulp van PowerShell doen vanaf de opdrachtregel. U kunt bovendien sjablonen exporteren en importeren, zodat u ze kunt kopiëren tussen tenants of bulksgewijze bewerkingen van complexe eigenschappen in sjablonen kunt uitvoeren, zoals het opgeven van meertalige namen en beschrijvingen.

U kunt met exporteren en importeren ook back-up- en herstelbewerkingen voor uw aangepaste sjablonen uitvoeren. Het wordt aanbevolen regelmatig back-ups van uw aangepaste sjablonen te maken zodat u, als u een onbedoelde wijziging maakt, gemakkelijk kunt terugkeren naar een eerdere versie.

> [!IMPORTANT] Als u Windows PowerShell wilt gebruiken om sjablonen voor het Azure RMS-rechtenbeleid te maken en beheren, hebt u ten minste versie 2.0.0.0 van de [Windows PowerShell-module voor Azure RMS](http://go.microsoft.com/fwlink/?LinkId=257721) nodig.
> 
> Als u deze PowerShell-module eerder hebt geïnstalleerd, voert u de volgende opdracht uit in een PowerShell-venster om het versienummer te controleren: `(Get-Module aadrm -ListAvailable).Version`

Zie [Windows PowerShell voor Azure Rights Management](install-powershell.md) voor installatie-instructies.

De cmdlets die ondersteuning bieden om sjablonen te maken en beheren:

-   [Add-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727075.aspx)

-   [Export-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727078.aspx)

-   [Get-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727079.aspx)

-   [Get-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727081.aspx)

-   [Import-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727077.aspx)

-   [New-AadrmRightsDefinition](https://msdn.microsoft.com/library/azure/dn727080.aspx)

-   [Remove-AadrmTemplate](https://msdn.microsoft.com/library/azure/dn727082.aspx)

-   [Set-AadrmTemplateProperty](https://msdn.microsoft.com/library/azure/dn727076.aspx)



## Zie ook
[Aangepaste sjablonen configureren voor Azure Rights Management](configure-custom-templates.md)

<!--HONumber=May16_HO3-->


