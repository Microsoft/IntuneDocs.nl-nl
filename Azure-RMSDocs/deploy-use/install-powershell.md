---
title: Windows PowerShell voor Azure Rights Management installeren | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: 0d665ed6-b1de-4d63-854a-bc57c1c49844
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: 590148218fdd10e88ba764b2dc523a2213e2c8bb


---

# Windows PowerShell voor Azure Rights Management installeren

*Van toepassing op: Azure Rights Management, Office 365*

Gebruik de volgende informatie bij het installeren van Windows PowerShell voor Microsoft [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (Azure RMS).

U kunt deze Windows PowerShell-module gebruiken voor het beheer van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] vanaf de opdrachtregel. Gebruik daarvoor een computer met een internetverbinding die voldoet aan de vereisten die worden vermeld in het volgende gedeelte. Windows PowerShell voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] biedt ondersteuning voor het uitvoeren van scripts voor automatisering en is mogelijk vereist in situaties met geavanceerde configuratie. Voor meer informatie over de beheertaken en configuraties waarvoor de module ondersteuning biedt, raadpleegt u [Beheer van Azure Rights Management met Windows PowerShell](administer-powershell.md).

## Vereisten
Deze tabel bevat de vereisten voor het installeren en gebruiken van Windows PowerShell voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)].

|Vereiste|Meer informatie|
|---------------|--------------------|
|Een versie van Windows die ondersteuning biedt voor de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-beheermodule|Controleer de lijst met ondersteunde besturingssystemen in de sectie **Systeemvereisten** van de [-downloadpagina voor het beheerprogramma voor Azure Rights Management](http://go.microsoft.com/fwlink/?LinkId=257721).|
|Minimaal vereiste versie van Windows PowerShell: 2.0|Ondersteuning voor de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-beheermodule wordt geboden vanaf Windows PowerShell 2.0.<br /><br />Standaard worden de meeste Windows-besturingssystemen geïnstalleerd met ten minste versie 2.0 van Windows PowerShell. Als u Windows PowerShell 2.0 wilt installeren, raadpleegt u [Windows PowerShell 2.0 installeren](http://msdn.microsoft.com/library/ff637750.aspx).<br /><br />Tip: als u wilt controleren welke versie van Windows PowerShell u gebruikt, typt u **$PSVersionTable** tijdens een Windows PowerShell-sessie.|
|De minimaal vereiste versie van Microsoft .NET Framework: 4.5<br /><br />Opmerking: deze versie van Microsoft .NET Framework is inbegrepen bij de nieuwere besturingssystemen. U hoeft deze dus alleen handmatig te installeren als uw clientbesturingssysteem ouder is dan Windows 8.0 of als uw serverbesturingsysteem ouder is dan Windows Server 2012.|Als de minimaal vereiste versie van Microsoft .NET Framework nog niet is geïnstalleerd, kunt u [Microsoft .NET Framework 4.5](http://www.microsoft.com/download/details.aspx?id=30653) downloaden.<br /><br />Deze versie van Microsoft .NET Framework is minimaal vereist voor enkele van de klassen waar de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-beheermodule gebruik van maakt.|
|Microsoft Online Services-aanmeldhulp 7.0|De Microsoft Online Services-aanmeldhulp is vereist voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]-verificatie.<br /><br />Voor meer informatie raadpleegt u [Downloadcentrum: Microsoft Online Services-assistent voor IT-professionals RTW](http://www.microsoft.com/en-us/download/details.aspx?id=41950).|

## De Rights Management-beheermodule installeren

1.  Ga naar het Microsoft Downloadcentrum en download het [beheerprogramma voor Azure Rights Management](https://go.microsoft.com/fwlink/?LinkId=257721), dat de [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]-beheermodule voor Windows PowerShell bevat.

2.  In de lokale map waarnaar u het [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-installatiebestand hebt gedownload, dubbelklikt u op het uitvoerbare bestand dat u voor uw platform hebt gedownload (WindowsAzureADRightsManagementAdministration_x64 of WindowsAzureADRightsManagementAdministration_x86.exe) om de Azure AD Rights Management-installatiewizard te starten.

3.  Voltooi de wizard.

Windows PowerShell voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] wordt nu geïnstalleerd.

## Volgende stappen
Als u wilt bekijken welke cmdlets er beschikbaar zijn, start u Windows PowerShell met de optie **Als beheerder uitvoeren** en typt u het volgende:

```
Get-Command -Module aadrm
```
Gebruik de opdracht `the Get-Help <cmdlet_name>` om de Help voor een bepaalde cmdlet te bekijken.

Meer informatie:

-   Volledige lijst met beschikbare cmdlets: [Azure Rights Management-cmdlets](https://msdn.microsoft.com/library/windowsazure/dn629398.aspx)

-   Lijst met de belangrijkste configuratiescenario's die ondersteuning bieden voor Windows PowerShell: [Beheer van Azure Rights Management met Windows PowerShell](administer-powershell.md)

Voordat u opdrachten kunt uitvoeren voor het configureren van de [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)]-service, moet u verbinding maken met de service via de cmdlet [Connect-AadrmService](https://msdn.microsoft.com/library/windowsazure/dn629415.aspx). Wanneer u klaar bent met het uitvoeren van de gewenste configuratieopdrachten, verbreekt u de verbinding met de service via de cmdlet [Disconnect-AadrmService](https://msdn.microsoft.com/library/windowsazure/dn629416.aspx).

> [!NOTE]
> Als u [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] nog niet hebt geactiveerd, kunt u dit doen nadat u verbinding hebt gemaakt met de service via de cmdlet [Enable-Aadrm](https://msdn.microsoft.com/library/windowsazure/dn629412.aspx).

## Zie ook
[Beheer van Azure Rights Management met Windows PowerShell](administer-powershell.md)



<!--HONumber=Jul16_HO3-->


