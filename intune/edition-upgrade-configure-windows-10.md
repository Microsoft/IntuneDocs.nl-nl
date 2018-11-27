---
title: Windows 10-apparaten upgraden of S-modus gebruiken op deze apparaten met Microsoft Intune - Azure | Microsoft Docs
description: Een apparaatprofiel maken in Microsoft Intune om Windows 10-apparaten te upgraden naar andere edities. U kunt bijvoorbeeld een upgrade van Windows 10 Professional naar Windows 10 Enterprise uitvoeren. U kunt ook de S-modus op een apparaat in- of uitschakelen met behulp van het configuratieprofiel. Zie ook de ondersteunde upgradepaden voor Windows 10 Pro, N Edition, Education, Cloud, Enterprise, Core, Holographic en Mobile.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: eb44647e50e406b9ef5052c576660c9b7eebf6dd
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189755"
---
# <a name="use-a-configuration-profile-to-upgrade-windows-10-or-switch-from-s-mode-in-intune"></a>Een configuratieprofiel gebruiken om Windows 10 te upgraden of vanuit de S-modus over te schakelen in Intune
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Configureer een upgradeprofiel in Intune om apparaten waarop een versie van Windows 10 wordt uitgevoerd automatisch te upgraden naar een andere versie. Zie ook de ondersteunde upgradepaden.

## <a name="before-you-begin"></a>Voordat u begint
Voordat u apparaten gaat upgraden naar de nieuwste versie, moet u aan de volgende vereisten voldoen:

- Een geldige productcode om de bijgewerkte Windows-versie te installeren op alle apparaten waarop het beleid is gericht (voor versies van Windows 10 Desktop). U kunt Multi Activation Keys (MAK) of Key Management Server-sleutels (KMS) gebruiken. Voor edities van Windows 10 Mobile en Windows 10 Holographic kunt u een licentiebestand van Microsoft gebruiken met de licentiegegevens voor het installeren van de bijgewerkte versie van Windows op alle apparaten waarop het beleid is gericht.
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


<!-- Testing a new table on 3/5/18 

The following lists provide the supported upgrade paths for the Windows 10 edition upgrade profile. The Windows 10 edition to upgrade to is in bold followed by the list of supported editions that you can upgrade from:

**Windows 10 Education**
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 10 Cloud
- Windows 10 Enterprise
- Windows 10 Core
    
**Windows 10 Education N edition**    
- Windows 10 Pro N edition
- Windows 10 Pro Education N edition
- Windows 10 Cloud N edition
- Windows 10 Enterprise N edition
- Windows 10 Core N edition
    
**Windows 10 Enterprise**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Enterprise N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition
    
**Windows 10 Pro**
- Windows 10 Cloud
    
**Windows 10 Pro N edition**
- Windows 10 Cloud N edition
    
**Windows 10 Pro Education**
- Windows 10 Pro
- Windows 10 Cloud
- Windows 10 Core
    
**Windows 10 Pro Education N edition**
- Windows 10 Pro N edition
- Windows 10 Cloud N edition
- Windows 10 Core N edition

**Windows 10 Holographic for Business**
- Windows 10 Holographic

**Windows 10 Mobile Enterprise**
- Windows 10 Mobile -->

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

## <a name="upgrade-the-edition"></a>De editie bijwerken

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Geef een **Naam** en **Beschrijving** op voor het profiel. Voer bijvoorbeeld iets in zoals `Windows 10 edition upgrade`
4. Voor **Platform** selecteert u **Windows 10 en hoger**.
5. Selecteer voor **Profieltype** de optie **Editie-upgrade**.
6. Voer de volgende instellingen in de eigenschappen van **Editie-upgrade** in:

   - **Editie om naar te upgraden**: selecteer de Windows 10-editie waarnaar u upgradet. De apparaten waarop dit beleid is gericht, worden geüpgraded naar de door u gekozen editie.
   - **Productsleutel**: voer de productsleutel in die u hebt ontvangen van Microsoft. Nadat u het beleid met de productcode hebt gemaakt, kan de sleutel niet worden bijgewerkt en wordt deze uit veiligheidsoverwegingen verborgen. Als u de productcode wilt wijzigen, voert u de volledige code opnieuw in.
   - **Licentiebestand**: voor **Windows 10 Holographic for Business** of **Windows 10 Mobile-editie** kiest u **Bladeren** om het licentiebestand te selecteren dat u hebt ontvangen van Microsoft. Dit licentiebestand bevat licentiegegevens over de edities waarnaar u de desbetreffende apparaten upgradet.

7. Selecteer **OK** om uw wijzigingen op te slaan. Selecteer **Maken** om het profiel te maken.

## <a name="switch-out-of-s-mode"></a>De S-modus uitschakelen

[Windows 10 S-modus](https://support.microsoft.com/help/4456067/windows-10-switch-out-of-s-mode) is ontworpen voor beveiliging en prestaties. Als op uw apparaten alleen apps uit de Microsoft Store worden uitgevoerd, kunt u de S-modus gebruiken om uw apparaten veilig te houden. Als u op uw apparaten apps nodig hebt die niet beschikbaar zijn in de Microsoft Store, dan schakelt u de S-modus uit. Het uitschakelen van de S-modus werkt maar één keer. En zodra u de S-modus hebt uitgeschakeld, kunt u niet terug naar Windows 10 S-modus.

In de volgende stappen ziet u hoe u een profiel maakt voor besturing van de S-modus op apparaten met Windows 10 (1809 of later).

1. Selecteer in [Azure Portal](https://portal.azure.com) **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
3. Geef een **Naam** en **Beschrijving** op voor het profiel. Voer bijvoorbeeld iets in zoals `Windows 10 switch off S mode`
4. Voor **Platform** selecteert u **Windows 10 en hoger**.
5. Selecteer voor **Profieltype** de optie **Editie-upgrade**.
6. Selecteer **Modusschakelaar (alleen in Windows Insider)** en stel de eigenschap **De S-modus uitschakelen** in. Uw opties zijn:

    - **Geen configuratie**: een apparaat met de S-modus blijft in de S-modus. Een eindgebruiker kan de S-modus op het apparaat uitschakelen.
    - **In de S-modus blijven**: hierdoor kan de eindgebruiker de S-modus op het apparaat niet uitschakelen.
    - **Schakelaar**: hiermee wordt de S-modus op het apparaat uitgeschakeld.

7. Selecteer **OK** om uw wijzigingen op te slaan. Selecteer **Maken** om het profiel te maken.

Het profiel wordt gemaakt en wordt weergegeven in de profielen.

## <a name="next-steps"></a>Volgende stappen

[Wij dit profiel](device-profile-assign.md) toe aan uw groepen.

>[!NOTE]
>Als u de beleidstoewijzing later verwijdert, wordt de versie van Windows op het apparaat niet teruggezet, maar blijft deze normaal functioneren.
