---
title: Windows 10-apparaten upgraden of S-modus gebruiken op deze apparaten - Microsoft Intune - Azure | Microsoft Docs
description: Gebruik Microsoft Intune om Windows 10-apparaten te upgraden naar een andere editie of om de S-modus in te schakelen. Beheerders kunnen een apparaatconfiguratieprofiel gebruiken om Windows 10 Professional naar Windows 10 Enterprise te upgraden en om de S-modus in of uit te schakelen. Zie de ondersteunde upgradepaden voor Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic en Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b206cfca048416b1e859e9230f037e1158d46ec
ms.sourcegitcommit: 25e17a1d002ee1faa49bb89648eb59373528539f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2019
ms.locfileid: "59566630"
---
# <a name="upgrade-windows-10-editions-or-enable-s-mode-on-devices-using-microsoft-intune"></a>Upgrade Windows 10-edities of schakel op apparaten de S-modus in met behulp van Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als onderdeel van uw MDM-oplossing (mobile device management) is het raadzaam uw Windows 10-apparaten te upgraden. U kunt bijvoorbeeld uw Windows 10 Professional-apparaten naar Windows 10 Enterprise upgraden. Of u kunt S-mobiel inschakelen, zodat apparaten alleen apps uit de Microsoft Store uitvoeren.

[Windows 10 S-modus](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) is ontworpen voor beveiliging en prestaties. Als op uw apparaten alleen apps uit de Microsoft Store worden uitgevoerd, kunt u de S-modus gebruiken om uw apparaten veilig te houden. Als uw apparaten apps gebruiken die niet beschikbaar zijn in de Microsoft Store, dan schakelt u de S-modus uit. Het uitschakelen van de S-modus werkt maar één keer. En zodra u de S-modus hebt uitgeschakeld, kunt u niet terug naar Windows 10 S-modus.

Deze functie is van toepassing op:

- Windows 10 en hoger
- Windows 10 1809 of hoger voor de S-modus
- Windows Holographic for Business

Deze functies zijn beschikbaar in Intune en kunnen worden geconfigureerd door de beheerder. Intune maakt gebruik van configuratieprofielen om deze instellingen te maken voor en af te stemmen op de behoeften van uw organisatie. Nadat u deze functies aan een profiel hebt toegevoegd, kunt u het profiel pushen naar en implementeren op Windows 10-apparaten in uw organisatie. Wanneer u het profiel implementeert, wordt door Intune een upgrade van de apparaten uitgevoerd of de S-modus ingeschakeld.

Dit artikel vermeldt de ondersteunde upgradepaden en laat zien hoe het apparaatconfiguratieprofiel wordt gemaakt. U kunt tevens alle beschikbare upgrade-instellingen en S-modusinstellingen voor [Windows 10](edition-upgrade-windows-settings.md) bekijken.

> [!NOTE]
> Als u de beleidstoewijzing later verwijdert, wordt de versie van Windows op het apparaat niet teruggezet. Het apparaat blijft normaal functioneren.

## <a name="prerequisites"></a>Vereisten

Controleer voor u apparaten upgradet of u aan de volgende vereisten voldoet:

- Een geldige productcode om de bijgewerkte Windows-versie te installeren op alle apparaten waarop het beleid is gericht (voor versies van Windows 10 Desktop). U kunt Multi Activation Keys (MAK) of Key Management Server-sleutels (KMS) gebruiken.
- Voor edities van Windows 10 Mobile en Windows 10 Holographic kunt u een licentiebestand van Microsoft gebruiken. Het licentiebestand bevat de licentiegegevens voor het installeren van de bijgewerkte versie op alle apparaten waarop het beleid is gericht.
- De Windows 10-apparaten waaraan u het beleid toewijst, worden geregistreerd bij Microsoft Intune. U kunt het editie-upgradebeleid niet gebruiken voor pc’s waarop de Intune-pc-clientsoftware wordt uitgevoerd.

## <a name="supported-upgrade-paths"></a>Ondersteunde upgradepaden

In de volgende tabel staan de ondersteunde upgradepaden voor het upgradeprofiel van de Windows 10-versie.

| Upgrade van | Upgrade naar |
|---|---|
| Windows 10 Pro | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education |
| Windows 10 Pro N | Windows 10 Education N <br/>Windows 10 Enterprise N <br/>Windows 10 Pro Education N | 
| Windows 10 Pro Education | Windows 10 Education | 
| Windows 10 Pro Education N | Windows 10 Education N |
| Windows 10 Cloud | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro <br/>Windows 10 Pro Education | 
| Windows 10 Cloud N | Windows 10 Education N <br/>Windows 10 Enterprise N <br/>Windows 10 Pro N <br/>Windows 10 Pro Education N | 
| Windows 10 Enterprise | Windows 10 Education | 
| Windows 10 Enterprise N | Windows 10 Education N | 
| Windows 10 Core | Windows 10 Education <br/>Windows 10 Enterprise <br/>Windows 10 Pro Education | 
| Windows 10 Core N | Windows 10 Education N <br/>Windows 10 Enterprise N <br/>Windows 10 Pro Education N | 
| Windows 10 Holographic | Windows 10 Holographic for Business |
| Windows 10 Mobile | Windows 10 Mobile Enterprise |

<!--The following table provides information about the supported upgrade paths for Windows 10 editions in this policy:

![supported](./media/check_grn.png)  (X) = not supported    
![unsupported](./media/x_blk.png)    (green checkmark) = supported    

|Upgrade from edition\Upgrade to edition|Education|Education N|Pro Education|Pro Education N|Enterprise|Enterprise N|Professional|Professional N|Mobile Enterprise|Holographic for Business|
|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|--------|
|Pro|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Pro Education N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Cloud N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Enterprise N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)   |![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Core N|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|
|Mobile|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png)|![unsupported](./media/x_blk.png)|
|Holographic|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![unsupported](./media/x_blk.png)|![supported](./media/check_grn.png) -->

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel. Voer bijvoorbeeld iets als `Windows 10 edition upgrade profile` of `Windows 10 switch off S mode` in.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer het platform:  

        - **Windows 10 en hoger**

    - **Profieltype**: Selecteer **Editie-upgrade**.
    - **Instellingen**: Voer de instellingen in die u wilt configureren. Voor een lijst van alle instellingen en wat ze doen raadpleegt u:

        - [Windows 10-upgrade en S-modus](edition-upgrade-windows-settings.md)
        - [Windows Holographic for Business](holographic-upgrade.md)

4. Selecteer **OK** > **Maken** om uw wijzigingen op te slaan. 

Het profiel wordt gemaakt en in de lijst weergegeven. Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](device-profile-monitor.md).

## <a name="next-steps"></a>Volgende stappen

Nadat het profiel is gemaakt, is het klaar om te worden toegewezen. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Bekijk de instellingen voor upgrades en S-modus voor apparaten met [Windows 10](edition-upgrade-windows-settings.md) en [Windows Holographic for Business](holographic-upgrade.md).
