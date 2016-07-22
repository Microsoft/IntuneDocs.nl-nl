---
title: Intune-licenties beheren met PowerShell | Microsoft Intune
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2847c9af38ae0ddddc8d76d548ae7abddc63e4c1
ms.openlocfilehash: e0eca2ecc9948c7caf15d5df5e6e106428b8b964


---

# Intune-licenties beheren met PowerShell
Voordat gebruikers zich kunnen aanmelden bij de Intune-service of hun apparaten kunnen registreren voor beheer, moet u eerst aan elke gebruiker een licentie voor uw Intune-abonnement toewijzen, zoals is beschreven in [Manage Intune licenses](start-with-a-paid-subscription-to-microsoft-intune-step-4.md) (Intune-licenties beheren). Organisaties die gebruikmaken van Enterprise Mobility Suite van Microsoft, kunnen echter gebruikers hebben die alleen Azure Active Directory Premium of Intune-services in het Enterprise Mobility Suite-pakket nodig hebben. In dat geval kunt u met [Azure Active Directory PowerShell-cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) één service of een subset met services toewijzen. 

Als u selectief gebruikerslicenties voor EMS-services wilt toewijzen, opent u PowerShell als beheerder op een computer waarop de [Azure Active Directory-module voor Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) is geïnstalleerd. U kunt PowerShell installeren op een lokale computer of op de ADFS-server.

U moet een nieuwe licentie-SKU-definitie maken die alleen van toepassing is op de gewenste serviceplannen. Daarvoor schakelt u de plannen uit die u niet wilt toepassen. U kunt bijvoorbeeld een licentie-SKU-definitie maken waarmee geen licentie voor Intune wordt toegewezen. Typ het volgende om een lijst met beschikbare services weer te geven:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

U kunt de volgende opdracht uitvoeren om het Intune-serviceplan uit te sluiten. Met dezelfde methode kunt u een complete beveiligingsgroep uitbreiden. U kunt echter ook gedetailleerdere filters gebruiken. 

**Voorbeeld 1** Een nieuwe gebruiker maken via de opdrachtregel en een Enterprise Mobility Suite-licentie toewijzen zonder het Intune-gedeelte van de licentie in te schakelen:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Controleer met:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Voorbeeld 2** Het Intune-gedeelte van de Enterprise Mobility Suite-licentie uitschakelen voor een gebruiker aan wie al een licentie is toegewezen:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Controleer met:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Volgende stappen
Gefeliciteerd. U hebt zojuist stap 4 van de *Snelstartgids voor Intune* voltooid.
>[!div class="step-by-step"]

>[&larr; **Gebruikers synchroniseren met Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gebruikers en apparaten organiseren** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Jun16_HO4-->


