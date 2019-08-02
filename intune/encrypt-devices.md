---
title: Apparaten in Microsoft Intune versleutelen met behulp van de door platforms ondersteunde versleutelingsmethoden
titleSuffix: Microsoft Intune
description: Versleutel apparaten met ingebouwde versleutelingsmethoden zoals BitLocker of FileVault, en beheer de herstelsleutels voor deze versleutelde apparaten vanuit de Intune-portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/25/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 3f37b9b0bc16572cc86cbf79be616c7f395aa784
ms.sourcegitcommit: 2bce5e43956b6a5244a518caa618f97f93b4f727
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/24/2019
ms.locfileid: "68467446"
---
# <a name="use-device-encryption-with-intune"></a>Apparaatversleuteling gebruiken met Intune  

U kunt Intune gebruiken om de versleuteling van de ingebouwde schijf of het station van een apparaat te beheren voor het beschermen van de gegevens op uw apparaten.  

Configureer schijfversleuteling als onderdeel van een apparaatconfiguratieprofiel voor Endpoint Protection. De volgende platforms en versleutelingstechnologieën worden ondersteund door Intune:  
- macOS: FileVault   
- Windows 10 en hoger: BitLocker  

Intune biedt ook een ingebouwd [versleutelingsrapport](encryption-monitor.md) met informatie over de versleutelingsstatus van apparaten, voor alle beheerde apparaten.  

## <a name="filevault-encryption-for-macos"></a>FileVault-versleuteling voor macOS  

Gebruik Intune om FileVault-schijfversleuteling te configureren op apparaten waarop macOS wordt uitgevoerd. Gebruik vervolgens het Intune-versleutelingsrapport voor het weergeven van de versleutelingsgegevens voor deze apparaten en voor het beheren van herstelsleutels voor met FileVault versleutelde apparaten.  

FileVault is een programma voor de versleuteling van volledige schijven. Het programma wordt geleverd bij macOS. U kunt Intune gebruiken om FileVault te configureren op apparaten waarop **macOS 10.13 of hoger** wordt uitgevoerd.  

Als u FileVault wilt configureren, maakt u een [apparaatconfiguratieprofiel](device-profile-create.md) voor Endpoint Protection voor het macOS-platform. De FileVault-instellingen vormen een eigen instellingencategorie in Endpoint Protection voor macOS.  

Wanneer u een beleid hebt gemaakt voor het met FileVault versleutelen van apparaten, wordt het beleid in twee fasen toegepast op apparaten. In eerste instantie wordt het apparaat voorbereid zodat Intune kan worden gebruikt voor het ophalen van en het maken van back-ups van de herstelsleutel. Dit heet ook wel 'escrow'. Wanneer er een escrow-sleutel is gemaakt, kan worden gestart met de schijfversleuteling.

![FileVault-instellingen](./media/encrypt-devices/filevault-settings.png)

Voor meer informatie over de FileVault-instelling die u met Intune kunt beheren, ziet u [FileVault](endpoint-protection-macos.md#filevault) in het Intune-artikel over Endpoint Protection-instellingen voor macOS.  

### <a name="how-to-configure-macos-filevault"></a>FileVault voor macOS configureren 

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en ga naar **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.  

2. Stel de volgende opties in:  

   - Platform: macOS  
   - Profieltype: Endpoint Protection  

3. Selecteer **Instellingen** > **FileVault**.  

4. Bij *FileVault* selecteert u **Inschakelen**.  

5. Bij *Herstelsleuteltype* wordt alleen de optie **Persoonlijke sleutel** ondersteund.  

   Overweeg een bericht toe te voegen om eindgebruikers te helpen bij het ophalen van de herstelsleutel voor hun apparaat. Deze informatie kan nuttig zijn voor uw eindgebruikers wanneer u de instelling voor wijziging van persoonlijke herstelsleutels gebruikt. Met deze instelling kan periodiek automatisch een nieuwe herstelsleutel voor een apparaat worden gegenereerd.  

   Bijvoorbeeld: Als u een verloren of onlangs vernieuwde herstelsleutel wilt ophalen, meldt u zich aan op de website van de Intune-bedrijfsportal. Dit kan vanaf elk apparaat. Ga in de portal naar *Apparaten* en selecteer het apparaat waarvoor FileVault is ingeschakeld. Selecteer dan *Herstelsleutel ophalen*. De huidige herstelsleutel wordt weergegeven.  

6. Configureer de overige [FileVault-instellingen](endpoint-protection-macos.md#filevault) zodanig dat er aan de vereisten van uw bedrijf wordt voldaan. Selecteer vervolgens **OK**.  

7. Voltooi de configuratie van de aanvullende instellingen en sla het profiel op.  

### <a name="manage-filevault"></a>FileVault beheren  

Wanneer Intune een macOS-apparaat versleutelt met FileVault, kunt u de FileVault-herstelsleutels bekijken en beheren tijdens het bekijken van het Intune-[versleutelingsrapport](encryption-monitor.md).  

## <a name="bitlocker-encryption-for-windows-10"></a>BitLocker-versleuteling voor Windows 10  

Gebruik Intune om BitLocker-stationsversleuteling te configureren op apparaten waarop Windows 10 wordt uitgevoerd. Gebruik vervolgens het Intune-versleutelingsrapport om de versleutelingsgegevens voor deze apparaten te bekijken. U hebt ook toegang tot voor BitLocker belangrijke informatie over uw apparaten, zoals te zien is in Azure Active Directory (Azure AD).  

BitLocker is beschikbaar op apparaten met **Windows 10 of hoger**.  

Configureer BitLocker bij het maken van een [apparaatconfiguratieprofiel](device-profile-create.md) voor Endpoint Protection in Windows 10 of op een nieuwer platform. De BitLocker-instellingen bevinden zich in de categorie Windows-versleutelingsinstellingen voor Windows 10 Endpoint Protection.    

![BitLocker-instellingen](./media/encrypt-devices/bitlocker-settings.png) 

### <a name="how-to-configure-windows-10-bitlocker"></a>BitLocker configureren voor Windows 10  

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) en ga naar Apparaatconfiguratie > Profielen > Profiel maken.  

2. Stel de volgende opties in:  
   - Platform: Windows 10 en hoger  
   - Profieltype: Endpoint Protection  

3. Selecteer **Instellingen** > **Windows-versleuteling**.

4. Configureer de instellingen van BitLocker zodat er aan de vereisten van uw bedrijf wordt voldaan. Selecteer dan **OK**.  

5. Voltooi de configuratie van de aanvullende instellingen en sla het profiel op.  

### <a name="manage-bitlocker"></a>BitLocker beheren  

Wanneer Intune een Windows 10-apparaat versleutelt met BitLocker, kunt u de BitLocker-herstelsleutels bekijken en ophalen tijdens het bekijken van het Intune-[versleutelingsrapport](encryption-monitor.md).  

## <a name="next-steps"></a>Volgende stappen  

Een [nalevingsbeleid voor apparaten](compliance-policy-create-windows.md) maken  

U kunt op basis van het versleutelingsrapport de volgende zaken beheren:  
- [BitLocker-herstelsleutels](encryption-monitor.md#bitlocker-recovery-keys)
- [FileVault-herstelsleutels](encryption-monitor.md#filevault-recovery-keys)

Bekijk welke versleutelingsinstellingen u met Intune kunt configureren voor:  
- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)  
- [FileVault](endpoint-protection-macos.md#filevault)  
 
 
