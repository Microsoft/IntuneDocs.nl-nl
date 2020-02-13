---
title: Delivery Optimization-instellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer hoe Windows 10-apparaten die u met Intune beheert, gebruikmaken van Delivery Optimization. Maak in Intune een apparaatconfiguratieprofiel om updates van internet te installeren. Kijk ook hoe u bestaande updateringen kunt vervangen door een Delivery Optimization-profiel.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/10/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 9fb4aab6b02c6ad6a5d2f18ca9d15beafc12d58a
ms.sourcegitcommit: e1ff157f692983b49bdd6e20cc9d0f93c3b3733c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124806"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Delivery Optimization-instellingen in Microsoft Intune

Met Intune gebruikt u instellingen voor Delivery Optimization voor uw Windows 10-apparaten om gebruik van bandbreedte te beperken als op die apparaten toepassingen en updates worden gedownload. Configureer Delivery Optimization als onderdeel van uw apparaatconfiguratieprofielen.  

In dit artikel wordt beschreven hoe u instellingen voor Delivery Optimization configureert als onderdeel van een apparaatconfiguratieprofiel. Nadat u een profiel hebt gemaakt, kunt u dat profiel toewijzen aan of implementeren naar uw Windows 10-apparaten. 

Zie [Instellingen voor Delivery Optimization voor Intune](../delivery-optimization-settings.md) voor een lijst met de instellingen voor Delivery Optimization die door Intune worden ondersteund.  

Raadpleeg [Delivery Optimization-updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) in de Windows-documentatie voor meer informatie over Delivery Optimization in Windows 10.  

## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.

3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies **Windows 10 en hoger**.
    - **Profieltype**: Selecteer **Delivery Optimization**.

4. Kies **Instellingen** > **Configureren** en definieer hoe updates en apps moeten worden gedownload. Zie [Instellingen voor Delivery Optimization voor Intune](../delivery-optimization-settings.md) voor meer informatie over beschikbare instellingen.

5. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en weergegeven in de lijst. Vervolgens moet u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

<!-- ## Move existing update rings to delivery optimization

**Delivery optimization** settings replace **Software updates – Windows 10 Update Rings**. Your existing update rings can be easily changed to use the **Delivery optimization** settings. To maintain the same settings when you create a delivery optimization profile, use the same *Delivery optimization download mode* and then set the same settings as you already use. However, you can choose to reconfigure delivery optimization settings to take advantage of the full range of addition settings that the Delivery Optimization profile can manage. 
-->

## <a name="remove-delivery-optimization-from-windows-10-update-rings"></a>Delivery Optimization verwijderen uit Windows 10-updateringen

Delivery Optimization is eerder geconfigureerd als onderdeel van software-updateringen. Met ingang van februari 2019 worden de instellingen voor Delivery Optimization geconfigureerd als onderdeel van een configuratieprofiel voor een Delivery Optimization-profiel. Dit omvat extra instellingen die meer invloed hebben dan de levering van software-updates op apparaten. Als dat nog niet is gebeurd, verwijdert u de Delivery Optimization-instelling uit uw update-ringen door deze in te stellen op *Niet geconfigureerd*. Gebruik vervolgens een Delivery Optimization-profiel om het grotere aantal beschikbare opties te beheren.

1. Een configuratieprofiel voor een Delivery Optimization voor een apparaat maken:

    1. Selecteer in het Microsoft Endpoint Manager-beheercentrum de opties **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
    2. Voer de volgende eigenschappen in:

        - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
        - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
        - **Platform**: Kies **Windows 10 en hoger**.
        - **Profieltype**: Selecteer **Delivery Optimization**.
        - **Instellingen**: Als **downloadmodus voor Delivery Optimization** kiest u dezelfde modus die door de bestaande software-update-ring wordt gebruikt, tenzij u de instellingen die u op uw apparaten toepast, wilt wijzigen. Uw opties zijn:
            - **Niet geconfigureerd**
            - **Alleen HTTP, geen peering**
            - **HTTP gemengd met peering achter dezelfde NAT**
            - **HTTP gemengd met peering in een privégroep**
            - **HTTP met internetpeering**
            - **Eenvoudige downloadmodus zonder peering**
            - **Bypass-modus**
    3. Configureer eventuele extra instellingen die u wilt beheren.

2. Wijs dit nieuwe profiel toe aan dezelfde apparaten en gebruikers als de bestaande software-updatering. In [Het profiel toewijzen](device-profile-assign.md) worden de stappen vermeld.

3. Maak de configuratie van de bestaande softwarering ongedaan:
    1. Ga in het Microsoft Endpoint Manager-beheercentrum naar **Software-updates** > Windows 10-updateringen.
    2. Selecteer uw updatering in de lijst.
    3. Stel in de instellingen **Delivery Optimization-downloadmodus** in op **Niet geconfigureerd**.
    4. Kies **OK** > **Opslaan** voor uw wijzigingen.

## <a name="next-steps"></a>Volgende stappen

[Wijs het profiel toe](device-profile-assign.md) en [controleer de status](device-profile-monitor.md) van het profiel.  
Bekijk de [instellingen voor Delivery Optimization](../delivery-optimization-settings.md) voor Intune.
