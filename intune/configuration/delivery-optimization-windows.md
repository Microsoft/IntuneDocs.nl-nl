---
title: Delivery Optimization-instellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer hoe Windows 10-apparaten die u met Intune beheert, gebruikmaken van Delivery Optimization. Maak in Intune een apparaatconfiguratieprofiel om updates van internet te installeren. Kijk ook hoe u bestaande updateringen kunt vervangen door een Delivery Optimization-profiel.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/12/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: kerimh
ms.openlocfilehash: 7d94a2c7e47b3cfcc9f4592faf0a4c2a09a24ac4
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72495237"
---
# <a name="delivery-optimization-settings-in-microsoft-intune"></a>Delivery Optimization-instellingen in Microsoft Intune

Met Intune kunt u instellingen voor Delivery Optimization voor uw Windows 10-apparaten gebruiken om gebruik van bandbreedte te beperken als op die apparaten toepassingen en updates worden gedownload. Delivery Optimization wordt geconfigureerd als onderdeel van uw apparaatconfiguratieprofielen.  

In dit artikel wordt beschreven hoe u instellingen voor Delivery Optimization configureert als onderdeel van een apparaatconfiguratieprofiel. Nadat u een profiel hebt gemaakt, kunt u dat profiel toewijzen aan of implementeren naar uw Windows 10-apparaten. 

Zie [Instellingen voor Delivery Optimization voor Intune](../delivery-optimization-settings.md) voor een lijst met de instellingen voor Delivery Optimization die door Intune worden ondersteund.  

Raadpleeg [Delivery Optimization-updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) in de Windows-documentatie voor meer informatie over Delivery Optimization in Windows 10.  


> [!NOTE]
> **Software-updates – Windows 10-updateringen** worden vervangen door de **Delivery optimization**-instellingen. Bestaande updateringen kunnen worden gewijzigd voor gebruik van de **Delivery Optimization**-instellingen. [Bestaande update-ringen verplaatsen naar Delivery Optimization](#move-existing-update-rings-to-delivery-optimization) (in dit artikel) 
## <a name="create-the-profile"></a>Het profiel maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).

2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.

3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer het platform:  

        - **Windows 10 en hoger**

    - **Profieltype**: Selecteer **Delivery Optimization**.
    - **Instellingen**: Configureer instellingen waarmee u definieert hoe updates en apps moeten worden gedownload. Zie [Instellingen voor Delivery Optimization voor Intune](../delivery-optimization-settings.md) voor meer informatie over beschikbare instellingen.

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en weergegeven in de lijst. Vervolgens moet u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Bestaande updateringen verplaatsen naar Delivery Optimization

Instellingen voor **Delivery Optimization** vervangen de **Software-updates – Windows 10-update-ringen**. Bestaande updateringen kunnen eenvoudig worden gewijzigd voor gebruik van de **Delivery Optimization**-instellingen. Als u dezelfde instellingen wilt behouden wanneer u een Delivery Optimization-profiel maakt, gebruikt u dezelfde *downloadmodus voor Delivery Optimization* en stelt u vervolgens de instellingen in die u al gebruikt. U kunt er echter ook voor kiezen om de instellingen voor Delivery Optimization opnieuw te configureren, zodat u kunt profiteren van de complete reeks aanvullende instellingen die door het Delivery Optimization-profiel kunnen worden beheerd.

1. Een Delivery Optimization-configuratieprofiel maken:

    1. Selecteer in Intune **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
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
1. Wijs dit nieuwe profiel toe aan dezelfde apparaten en gebruikers als de bestaande software-updatering. In [Het profiel toewijzen](device-profile-assign.md) worden de stappen vermeld.

3. Maak de configuratie van de bestaande softwarering ongedaan:
    1. Ga in Intune naar **Software-updates** > Windows 10-updateringen.
    2. Selecteer uw updatering in de lijst.
    3. Stel in de instellingen **Delivery Optimization-downloadmodus** in op **Niet geconfigureerd**.
    4. Kies **OK** > **Opslaan** voor uw wijzigingen.

## <a name="next-steps"></a>Volgende stappen

[Wijs het profiel toe](device-profile-assign.md) en [controleer de status](device-profile-monitor.md) van het profiel.  
Bekijk de [instellingen voor Delivery Optimization](../delivery-optimization-settings.md) voor Intune.
