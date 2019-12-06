---
title: Apparaten versleutelen met de versleutelingsmethode die wordt ondersteund op platforms
titleSuffix: Microsoft Intune
description: Versleutel apparaten met ingebouwde versleutelingsmethoden zoals BitLocker of FileVault, en beheer de herstelsleutels voor deze versleutelde apparaten vanuit de Intune-portal.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 13d6a2b9cdc8596c7f5cf81218377754e9412be1
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390347"
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

Als u FileVault wilt configureren, maakt u een [apparaatconfiguratieprofiel](../configuration/device-profile-create.md) voor Endpoint Protection voor het macOS-platform. De FileVault-instellingen vormen een eigen instellingencategorie in Endpoint Protection voor macOS.

Wanneer u een beleid hebt gemaakt voor het met FileVault versleutelen van apparaten, wordt het beleid in twee fasen toegepast op apparaten. In eerste instantie wordt het apparaat voorbereid zodat Intune kan worden gebruikt voor het ophalen van en het maken van back-ups van de herstelsleutel. Dit heet ook wel 'escrow'. Wanneer er een escrow-sleutel is gemaakt, kan worden gestart met de schijfversleuteling.

![FileVault-instellingen](./media/encrypt-devices/filevault-settings.png)

Voor meer informatie over de FileVault-instelling die u met Intune kunt beheren, ziet u [FileVault](endpoint-protection-macos.md#filevault) in het Intune-artikel over Endpoint Protection-instellingen voor macOS.

### <a name="how-to-configure-macos-filevault"></a>FileVault voor macOS configureren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.

3. Stel de volgende opties in:

   - Platform: macOS
   - Profieltype: Endpoint Protection

4. Selecteer **Instellingen** > **FileVault**.

5. Bij *FileVault* selecteert u **Inschakelen**.

6. Bij *Herstelsleuteltype* wordt alleen de optie **Persoonlijke sleutel** ondersteund.

   Overweeg een bericht toe te voegen om eindgebruikers te helpen bij het ophalen van de herstelsleutel voor hun apparaat. Deze informatie kan nuttig zijn voor uw eindgebruikers wanneer u de instelling voor wijziging van persoonlijke herstelsleutels gebruikt. Met deze instelling kan periodiek automatisch een nieuwe herstelsleutel voor een apparaat worden gegenereerd.

   Bijvoorbeeld: Als u een verloren of onlangs vernieuwde herstelsleutel wilt ophalen, meldt u zich aan op de website van de Intune-bedrijfsportal. Dit kan vanaf elk apparaat. Ga in de portal naar *Apparaten* en selecteer het apparaat waarvoor FileVault is ingeschakeld. Selecteer dan *Herstelsleutel ophalen*. De huidige herstelsleutel wordt weergegeven.

7. Configureer de overige [FileVault-instellingen](endpoint-protection-macos.md#filevault) zodanig dat er aan de vereisten van uw bedrijf wordt voldaan. Selecteer vervolgens **OK**.

   > [!IMPORTANT]
   > Er is een bekend probleem wanneer de instelling **Vraag bij afmelden uitschakelen** is ingesteld op *Inschakelen*. Als deze optie is ingesteld op *Ingeschakeld*, moet de instelling voor **Toegestaan aantal keren voor overslaan** worden ingesteld op een waarde en niet worden ingesteld op *Niet geconfigureerd*. Als de optie is ingesteld op *Niet geconfigureerd*, mislukt het profiel op het apparaat. In dit scenario wordt gemeld dat het een **Overzicht profielstatus** betreft met de status **Fout**, zonder nadere informatie.
   >
   > Als **Vraag bij afmelden uitschakelen** is ingesteld op *Niet geconfigureerd*, kan **Toegestaan aantal keren voor overslaan** zijn ingesteld op *Niet geconfigureerd* of op een waarde.
   >
   > Dit probleem wordt opgelost in een toekomstige update.

8. Voltooi de configuratie van de aanvullende instellingen en sla het profiel op.  

### <a name="manage-filevault"></a>FileVault beheren

Wanneer Intune een macOS-apparaat versleutelt met FileVault, kunt u de FileVault-herstelsleutels bekijken en beheren tijdens het bekijken van het Intune-[versleutelingsrapport](encryption-monitor.md).

Nadat Intune een macOS-apparaat versleutelt met FileVault, kunt u op elk apparaat de persoonlijke herstelsleutel van het apparaat bekijken in de online bedrijfsportal. Kies in de online bedrijfsportal het versleutelde macOS-apparaat en kies vervolgens 'Herstelsleutel ophalen' als externe actie.

## <a name="bitlocker-encryption-for-windows-10"></a>BitLocker-versleuteling voor Windows 10

Gebruik Intune om BitLocker-stationsversleuteling te configureren op apparaten waarop Windows 10 wordt uitgevoerd. Gebruik vervolgens het Intune-versleutelingsrapport om de versleutelingsgegevens voor deze apparaten te bekijken. U hebt ook toegang tot voor BitLocker belangrijke informatie over uw apparaten, zoals te zien is in Azure Active Directory (Azure AD).

BitLocker is beschikbaar op apparaten met **Windows 10 of hoger**.

Configureer BitLocker bij het maken van een [apparaatconfiguratieprofiel](../configuration/device-profile-create.md) voor Endpoint Protection in Windows 10 of op een nieuwer platform. De BitLocker-instellingen bevinden zich in de categorie Windows-versleutelingsinstellingen voor Windows 10 Endpoint Protection.

![BitLocker-instellingen](./media/encrypt-devices/bitlocker-settings.png)

### <a name="how-to-configure-windows-10-bitlocker"></a>BitLocker configureren voor Windows 10

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.

3. Stel de volgende opties in:

   - Platform: Windows 10 en hoger
   - Profieltype: Endpoint Protection

4. Selecteer **Instellingen** > **Windows-versleuteling**.

5. Configureer de instellingen van BitLocker zodat er aan de vereisten van uw bedrijf wordt voldaan. Selecteer dan **OK**.

6. Voltooi de configuratie van de aanvullende instellingen en sla het profiel op.

### <a name="manage-bitlocker"></a>BitLocker beheren

Wanneer Intune een Windows 10-apparaat versleutelt met BitLocker, kunt u de BitLocker-herstelsleutels bekijken en ophalen tijdens het bekijken van het Intune-[versleutelingsrapport](encryption-monitor.md).

### <a name="rotate-bitlocker-recovery-keys"></a>BitLocker-herstelsleutels roteren

U kunt een Intune-apparaatactie gebruiken om de BitLocker-herstelsleutel van een apparaat met Windows 10 versie 1909 of hoger op afstand te roteren.

#### <a name="prerequisites"></a>Vereisten

Apparaten moeten voldoen aan de volgende vereisten om rotatie van de BitLocker-herstelsleutel te ondersteunen:

- Op de apparaten moet Windows 10 versie 1909 of hoger aanwezig zijn

- Op aan Azure AD gekoppelde apparaten en aan Hybrid gekoppelde apparaten moet ondersteuning voor het roteren van sleutels zijn ingeschakeld:

  - **Clientgestuurde rotatie van herstelwachtwoorden**

  Deze instelling vindt u onder *Windows-versleuteling* als onderdeel van een configuratiebeleid voor Endpoint Protection in Windows 10.
  
#### <a name="to-rotate-the-bitlocker-recovery-key"></a>De BitLocker-herstelsleutel roteren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Alle apparaten**.

3. Selecteer een apparaat in de lijst met apparaten die u beheert, selecteer **Meer** en selecteer de externe apparaatactie **BitLocker-sleutelrotatie**.

## <a name="next-steps"></a>Volgende stappen

Een [nalevingsbeleid voor apparaten](compliance-policy-create-windows.md) maken.

U kunt op basis van het versleutelingsrapport de volgende zaken beheren:

- [BitLocker-herstelsleutels](encryption-monitor.md#bitlocker-recovery-keys)
- [FileVault-herstelsleutels](encryption-monitor.md#filevault-recovery-keys)

Bekijk welke versleutelingsinstellingen u met Intune kunt configureren voor:

- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)
- [FileVault](endpoint-protection-macos.md#filevault)
