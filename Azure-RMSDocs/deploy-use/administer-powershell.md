---
title: Beheer van Azure Rights Management met Windows PowerShell | Azure RMS
description: 
keywords: 
author: cabailey
manager: mbaldwin
ms.date: 04/28/2016
ms.topic: article
ms.prod: azure
ms.service: rights-management
ms.technology: techgroup-identity
ms.assetid: a890e04a-4b70-41b5-8d5f-3c210a669faa
ms.reviewer: esaggese
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0f355da35dff62ecee111737eb1793ae286dc93e
ms.openlocfilehash: bf1f684bc394ec3a1025f8c9ed3e57d07c598125


---

# Beheer van Azure Rights Management met Windows PowerShell

*Van toepassing op: Azure Rights Management, Office 365*

U kunt Microsoft [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (Azure RMS) activeren met behulp van het [!INCLUDE[o365_2](../includes/o365_2_md.md)]-beheercentrum of de klassieke Azure-portal, maar u kunt hiervoor ook de Windows PowerShell-module voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] (AADRM) gebruiken.

Nadat u [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] hebt geactiveerd, is verder beheer voor de service mogelijk niet vereist. Voor sommige geavanceerde configuratiescenario's moet u wellicht de Windows PowerShell-module voor [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] gebruiken. De volgende tabel bevat enkele van de geavanceerde configuratiescenario's die gebruikmaken van Windows PowerShell. Zie [Azure Rights Management-cmdlets](http://msdn.microsoft.com/library/azure/dn629398.aspx) voor een volledige lijst van de beschikbare cmdlets met meer informatie over elk ervan.

> [!NOTE]
> Zie [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]Windows PowerShell voor Azure Rights Management installeren[ als u de Windows PowerShell-module voor ](install-powershell.md) wilt installeren.

Er is ook een aanvullende Windows PowerShell-module, **RMSProtection**, die zowel Azure RMS als AD RMS ondersteunt. Deze module biedt ondersteuning voor de beveiliging en het opheffen van de beveiliging van meerdere bestanden, zodat u bijvoorbeeld alle bestanden in een map bulksgewijs kunt beveiligen. Zie de sectie [Scriptopties voor supergebruikers](configure-super-users.md#scripting-options-for-super-users) in het artikel [Supergebruikers configureren voor Azure Rights Management en detectieservices of gegevensherstel](configure-super-users.md) voor meer informatie.

|Als u dit wilt doen...|…gebruikt u de volgende cmdlets|
|-------------------|------------------------------|
|Migreren van on-premises Rights Management (AD RMS of Windows RMS) naar [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)].|[Import-AadrmTpd](http://msdn.microsoft.com/library/azure/dn857523.aspx)|
|Verbinding maken of de verbinding verbreken met de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-service voor uw organisatie.|[Connect-AadrmService](http://msdn.microsoft.com/library/azure/dn629415.aspx)<br /><br />[Disconnect-AadrmService](http://msdn.microsoft.com/library/azure/dn629416.aspx)|
|Genereren en beheren van uw eigen tenantsleutel; het BYOK-scenario (Bring Your Own Key).|[Add-AadrmKey](http://msdn.microsoft.com/library/azure/dn629418.aspx)<br /><br />[Get-AadrmKeys](http://msdn.microsoft.com/library/azure/dn629420.aspx)|
|Activeren of deactiveren van de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-service voor uw organisatie.|[Enable-Aadrm](http://msdn.microsoft.com/library/azure/dn629412.aspx)<br /><br />[Disable-Aadrm](http://msdn.microsoft.com/library/azure/dn629422.aspx)|
|In- of uitschakelen van de documenttrackingsite voor Azure Rights Management.|[Disable-AadrmDocumentTrackingFeature](https://msdn.microsoft.com/library/azure/mt548471.aspx)<br /><br />[Enable-AadrmDocumentTrackingFeature](https://msdn.microsoft.com/library/azure/mt548469.aspx)<br /><br />[Get-AadrmDocumentTrackingFeature](https://msdn.microsoft.com/library/azure/mt548470.aspx)|
|Configureren van controlemiddelen voor onboarding voor een gefaseerde implementatie van Azure Rights Management.|[Get-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857522.aspx)<br /><br />[Set-AadrmOnboardingControlPolicy](http://msdn.microsoft.com/library/azure/dn857521.aspx)|
|Maken en beheren van sjablonen voor rechtenbeleid voor uw organisatie.|[Add-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727075.aspx)<br /><br />[Export-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727078.aspx)<br /><br />[Get-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727079.aspx)<br /><br />[Get-AadrmTemplateProperty](http://msdn.microsoft.com/library/azure/dn727081.aspx)<br /><br />[Import-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727077.aspx)<br /><br />[New-AadrmRightsDefinition](http://msdn.microsoft.com/library/azure/dn727080.aspx)<br /><br />[Remove-AadrmTemplate](http://msdn.microsoft.com/library/azure/dn727082.aspx)<br /><br />[Set-AadrmTemplateProperty](http://msdn.microsoft.com/library/azure/dn727076.aspx)|
|Configureren van het maximumaantal dagen dat de inhoud die door uw organisatie wordt beveiligd, toegankelijk is zonder internetverbinding (de geldigheidsperiode van de gebruikerslicentie).|[Get-AadrmMaxUseLicenseValidityTime](https://msdn.microsoft.com/library/azure/dn932062.aspx)<br /><br />[Set-AadrmMaxUseLicenseValidityTime](https://msdn.microsoft.com/library/azure/dn932063.aspx)|
|Beheren van de functie Supergebruiker van [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)] voor uw organisatie.|[Enable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629400.aspx)<br /><br />[Disable-AadrmSuperUserFeature](https://msdn.microsoft.com/library/azure/dn629428.aspx)<br /><br />[Add-AadrmSuperUser](http://msdn.microsoft.com/library/azure/dn629411.aspx)<br /><br />[Get-AadrmSuperUser](https://msdn.microsoft.com/library/azure/dn629408.aspx)<br /><br />[Remove-AadrmSuperUser](https://msdn.microsoft.com/library/azure/dn629405.aspx)<br /><br />[Set-AadrmSuperUserGroup](https://msdn.microsoft.com/library/azure/mt653943.aspx)<br /><br />[Get-AadrmSuperUserGroup](https://msdn.microsoft.com/library/azure/mt653942.aspx)<br /><br />[Clear-AadrmSuperUserGroup](https://msdn.microsoft.com/library/azure/mt653944.aspx)|
|Beheren van gebruikers en groepen die zijn gemachtigd voor het beheer van de [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-service voor uw organisatie.|[Add-AadrmRoleBasedAdministrator](http://msdn.microsoft.com/library/azure/dn629417.aspx)<br /><br />[Get-AadrmRoleBasedAdministrator](https://msdn.microsoft.com/library/azure/dn629407.aspx)<br /><br />[Remove-AadrmRoleBasedAdministrator](https://msdn.microsoft.com/library/azure/dn629424.aspx)|
|Ophalen van een logboek van [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-beheertaken voor uw organisatie.|[Get-AadrmAdminLog](https://msdn.microsoft.com/library/azure/dn629430.aspx)|
|Registreren en analyseren van logboekregistratie voor [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)].|[Get-AadrmUserLog](https://msdn.microsoft.com/library/azure/mt653941.aspx)|
|Weergeven van de huidige [!INCLUDE[aad_rightsmanagement_2](../includes/aad_rightsmanagement_2_md.md)]-serviceconfiguratie voor uw organisatie.|[Get-AadrmConfiguration](http://msdn.microsoft.com/library/azure/dn629410.aspx)|
|Migreren van uw organisatie van [!INCLUDE[aad_rightsmanagement_1](../includes/aad_rightsmanagement_1_md.md)] naar een lokale AD RMS-implementatie.|[Set-AadrmMigrationUrl](https://msdn.microsoft.com/library/azure/dn629429.aspx)<br /><br />[Get-AadrmMigrationUrl](http://msdn.microsoft.com/library/azure/dn629403.aspx)|






<!--HONumber=Jun16_HO4-->


