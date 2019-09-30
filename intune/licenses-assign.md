---
title: Microsoft Intune-licenties toewijzen
description: Licenties toewijzen aan gebruikers zodat ze kunnen inschrijven bij Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd8b35fbbff89ca7f4c259e1903f4c9f9a6e3b38
ms.sourcegitcommit: d2989b9992d10d133573d9bc31479659fb7e242c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2019
ms.locfileid: "71238333"
---
# <a name="assign-licenses-to-users-so-they-can-enroll-devices-in-intune"></a>Licenties toewijzen aan gebruikers zodat ze kunnen apparaten inschrijven bij Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

U moet eerst aan elke gebruiker een Intune-licentie toewijzen voordat gebruikers hun apparaten bij Intune kunnen inschrijven, ongeacht of u handmatig gebruikers toevoegt of deze synchroniseert vanuit uw on-premises Active Directory. Zie [Licenties met Intune](licenses.md) voor een lijst met licenties.

## <a name="assign-an-intune-license-in-the-microsoft-365-admin-center"></a>Een Intune-licentie toewijzen in het Microsoft 365-beheercentrum

U kunt het [Microsoft 365-beheercentrum](http://go.microsoft.com/fwlink/p/?LinkId=698854) gebruiken om handmatig cloudgebruikers toe te voegen en licenties toe te wijzen aan zowel cloudgebruikersaccounts als accounts die vanuit uw on-premises Active Directory zijn gesynchroniseerd met Azure AD.

1. Meld u bij het [Microsoft 365-beheercentrum](http://go.microsoft.com/fwlink/p/?LinkId=698854) aan met uw tenantbeheerdersreferenties en selecteer vervolgens **Gebruikers** > **Actieve gebruikers**.

2. Selecteer het gebruikersaccount waaraan u een Intune-gebruikerslicentie wilt toewijzen en selecteer vervolgens **Productlicenties** > **Bewerken**.

3. Zet **Intune** of **Enterprise Mobility + Security** op **Aan** en selecteer **Opslaan**.

   ![Schermafbeelding van het gedeelte Productlicenties in het Microsoft 365-beheercentrum.](./media/office-assign-license.png)

4. Het gebruikersaccount beschikt nu over de benodigde machtigingen om de service te gebruiken en apparaten in te schrijven bij het beheer.

> [!NOTE]
> Gebruikers worden pas weergegeven in de klassieke Intune-portal nadat ze een apparaat hebben ingeschreven met behulp van de Intune-pc-client. U kunt ook een groep gebruikers in één keer bewerken door de optie voor het toevoegen of vervangen van een licentie voor alle geselecteerde gebruikers te selecteren.

## <a name="assign-an-intune-license-by-using-azure-active-directory"></a>Een Intune-licentie toewijzen met behulp van Azure Active Directory

U kunt ook Intune-licenties aan gebruikers toewijzen met behulp van Azure Active Directory. Raadpleeg het artikel [License users in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) (Gebruikers een licentie verlenen via Azure Active Directory) voor meer informatie. 

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Schoolgegevens synchroniseren gebruiken om licenties toe te wijzen aan gebruikers met Intune for Education
Als uw organisatie een onderwijsinstelling is, kunt u met Schoolgegevens synchroniseren(SDS) licenties voor Intune for Education toewijzen aan gesynchroniseerde gebruikers. Kies het selectievakje Intune for Education tijdens het instellen van uw SDS-profiel.  

![Schermafbeelding van de SDS-profielinstelling](./media/i4e-sds-profile-setup-setting.png)

Als u een licentie voor Intune for Education toewijst, zorg er dan voor dat er ook een Intune A Direct-licentie wordt toegewezen.

![Schermafbeelding van het instellen van de productlicentie](./media/i4e-set-licenses.png)

Zie [Overzicht van Schoolgegevens synchroniseren](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91) voor meer informatie over SDS.

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Invloed van gebruikers en apparaatlicenties op toegang tot services
* Elke **gebruiker** aan wie u een gebruikerslicentie voor software toewijst, kan de onlineservices en bijbehorende software (inclusief System Center-software) openen en gebruiken voor het beheren van toepassingen en maximaal 15 MDM-apparaten. De Intune-pc-agent staat 5 fysieke en 1 virtuele machine per gebruikerslicentie toe.
* U kunt los van gebruikerslicenties voor alle apparaten licenties kopen. Apparaatlicenties hoeven niet te worden toegewezen aan de apparaten. Elk apparaat dat toegang heeft tot en gebruikmaakt van de onlineservices en bijbehorende software (inclusief System Center-software) moet een apparaatlicentie hebben.
* Als een apparaat wordt gebruikt door meer dan een gebruiker, is voor elke gebruiker een apparaatlicentie voor de software vereist of is voor alle gebruikers een gebruikerslicentie voor software vereist.

## <a name="understanding-the-type-of-licenses-you-have-purchased"></a>Inzicht in het type licenties dat u hebt aangeschaft

Hoe u Intune hebt aangeschaft, bepaalt de gegevens van uw abonnementen:

- Als u Intune via een Enterprise Agreement hebt aangeschaft, kunt u uw abonnementsgegevens vinden in de portal voor volumelicenties onder **Abonnementen**.
- Als u Intune via een Cloud Solution Provider hebt aangeschaft, kunt u contact opnemen met uw reseller.
- Als u Intune met een CC# of factuur hebt aangeschaft, zijn uw licenties op gebruikers gebaseerd.




## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>PowerShell gebruiken om EMS-gebruikerslicenties selectief te beheren
In organisaties die gebruikmaken van Enterprise Mobility + Security (voorheen Enterprise Mobility Suite) van Microsoft, werken mogelijk gebruikers die alleen Azure Active Directory Premium of Intune-services in het EMS-pakket nodig hebben. Met [Azure Active Directory PowerShell-cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) kunt u één service of een subset van services toewijzen.

Als u selectief gebruikerslicenties voor EMS-services wilt toewijzen, opent u PowerShell als beheerder op een computer waarop de [Azure Active Directory-module voor Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) is geïnstalleerd. U kunt PowerShell installeren op een lokale computer of op de ADFS-server.

U moet een nieuwe licentie-SKU-definitie maken die alleen van toepassing is op de gewenste serviceplannen. Daarvoor schakelt u de plannen uit die u niet wilt toepassen. U kunt bijvoorbeeld een licentie-SKU-definitie maken waarmee geen licentie voor Intune wordt toegewezen. Typ het volgende om een lijst met beschikbare services weer te geven:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

U kunt de volgende opdracht uitvoeren om het Intune-serviceplan uit te sluiten. Met dezelfde methode kunt u een complete beveiligingsgroep uitbreiden. U kunt echter ook gedetailleerdere filters gebruiken.

**Voorbeeld 1**<br>
Maak een nieuwe gebruiker via de opdrachtregel en wijs een EMS-licentie toe zonder het Intune-gedeelte van de licentie in te schakelen:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Controleer met:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Voorbeeld 2**<br>
Schakel het Intune-gedeelte van de EMS-licentie uit voor een gebruiker aan wie al een licentie is toegewezen:

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Controleer met:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
