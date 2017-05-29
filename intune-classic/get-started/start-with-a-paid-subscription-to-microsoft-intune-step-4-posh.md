---
title: Intune-licenties beheren met PowerShell | Microsoft Docs
description: Intune-licenties beheren met PowerShell
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 211b1aba54924204a7e2d33301824f9d7eb9c030
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="manage-intune-licenses-using-powershell"></a>Intune-licenties beheren met PowerShell

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

In dit onderwerp wordt aan beheerders uitgelegd hoe ze PowerShell kunnen gebruiken voor het beheren van Intune-gebruikerslicenties.

Voordat gebruikers zich kunnen aanmelden bij de Intune-service of hun apparaten kunnen registreren voor beheer, moet u eerst aan elke gebruiker een licentie voor uw Intune-abonnement toewijzen, zoals is beschreven in [Manage Intune licenses](start-with-a-paid-subscription-to-microsoft-intune-step-4.md) (Intune-licenties beheren). Echter, in organisaties die gebruikmaken van Enterprise Mobility + Security van Microsoft, werken mogelijk gebruikers die alleen Azure Active Directory Premium of Intune-services in het EMS-pakket nodig hebben. Met [Azure Active Directory PowerShell-cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) kunt u één service of een subset van services toewijzen.

Als u selectief gebruikerslicenties voor EMS-services wilt toewijzen, opent u PowerShell als beheerder op een computer waarop de [Azure Active Directory-module voor Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) is geïnstalleerd. U kunt PowerShell installeren op een lokale computer of op de ADFS-server.

U moet een nieuwe licentie-SKU-definitie maken die alleen van toepassing is op de gewenste serviceplannen. Daarvoor schakelt u de plannen uit die u niet wilt toepassen. U kunt bijvoorbeeld een licentie-SKU-definitie maken waarmee geen licentie voor Intune wordt toegewezen. Typ het volgende om een lijst met beschikbare services weer te geven:

    (Get-MsolAccountSku | Where {$\_.SkuPartNumber -eq "EMS"}).ServiceStatus

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

### <a name="next-steps"></a>Volgende stappen
Gefeliciteerd. U hebt zojuist stap 4 van de *Snelstartgids voor Intune* voltooid.
>[!div class="step-by-step"]

>[&larr; **Gebruikers synchroniseren met Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Gebruikers en apparaten organiseren** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  

