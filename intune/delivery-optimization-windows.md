---
title: Delivery Optimization-instellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer hoe software-updates worden geleverd bij uw apparaten met behulp van de Delivery Optimization-cloudservices die beschikbaar zijn met Windows 10-apparaten en latere apparaten. Maak in Intune een apparaatconfiguratieprofiel om updates van internet te installeren. Kijk ook hoe u bestaande updateringen kunt vervangen door een Delivery Optimization-profiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a59cab5f709897e064b315193b292cb46dc2f2e
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831544"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Delivery Optimization-instellingen voor Windows 10-apparaten (en nieuwer) in Microsoft Intune

> [!NOTE]
> **Software-updates – Windows 10-updateringen** worden vervangen door de **Delivery optimization**-instellingen. Bestaande updateringen kunnen worden gewijzigd voor gebruik van de **Delivery Optimization**-instellingen. In [Bestaande updateringen verplaatsen naar Delivery Optimization](#move-existing-update-rings-to-delivery-optimization) (in dit artikel) worden de stappen vermeld. 


Deze functie is van toepassing op het volgende platform:

- Windows 10 en hoger

In dit artikel worden alle Delivery Optimization-instellingen vermeld en beschreven die u kunt configureren voor Windows 10-apparaten. Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel, en vervolgens toegewezen aan of geïmplementeerd op uw apparaten met behulp van Microsoft Intune.

[Delivery Optimization-updates](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) is een fantastische bron voor meer informatie over Delivery Optimization in Windows 10.

## <a name="create-the-profile"></a>Het profiel maken

1. Selecteer in [Azure Portal](https://portal.azure.com) de optie **Alle services** > filter op **Intune** > selecteer **Intune**.

2. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.

3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer het platform:  

        - **Windows 10 en hoger**

    - **Profieltype**: Selecteer **Delivery Optimization**.
    - **Instellingen**: Kies hoe u de updates wilt downloaden. Uw opties zijn: 

        - **Niet geconfigureerd**: Eindgebruikers werken hun apparaten op hun eigen manier bij, bijvoorbeeld via de instellingen voor **Windows Updates** of **Delivery Optimization** die beschikbaar zijn in het besturingssysteem.
        - **Alleen HTTP, geen peering**: Ontvang updates alleen via internet. Ontvang geen updates van andere computers in het netwerk (peering of peer-to-peer genoemd).
        - **HTTP gemengd met peering achter dezelfde NAT**: Ontvang updates via internet en van andere computers in het netwerk. 
        - **HTTP gemengd met peering in een privégroep**: Peering komt voor op apparaten op dezelfde Active Directory-site (indien deze bestaat) of in hetzelfde domein. Als deze optie is geselecteerd, vindt peering plaats voor de IP-adressen van uw NAT’s (Network Address Translation).
        - **HTTP met internetpeering**: Ontvang updates via internet en van andere computers in het netwerk.
        - **Eenvoudige downloadmodus zonder peering**: Ontvang updates via internet, rechtstreeks van de update-eigenaar, bijvoorbeeld Microsoft. Er wordt geen verbinding gemaakt met de Delivery Optimization-cloudservices.
        - **Bypass-modus**: Gebruik BITS (Background Intelligent Transfer Service) om updates op te halen. Gebruik Delivery Optimization niet.

4. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en weergegeven in de lijst. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

## <a name="move-existing-update-rings-to-delivery-optimization"></a>Bestaande updateringen verplaatsen naar Delivery Optimization

**Software-updates – Windows 10-updateringen** worden vervangen door de **Delivery optimization**-instellingen. Bestaande updateringen kunnen eenvoudig worden gewijzigd voor gebruik van de **Delivery Optimization**-instellingen. Stappen:

1. Een Delivery Optimization-configuratieprofiel maken:

    1. Selecteer in Intune **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
    2. Voer de volgende eigenschappen in:

        - **Naam**: Voer een beschrijvende naam in voor het nieuwe profiel.
        - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
        - **Platform**: Kies **Windows 10 en hoger**.
        - **Profieltype**: Selecteer **Delivery Optimization**.
        - **Instellingen**: Kies voor **Delivery Optimization-downloadmodus** dezelfde modus als wordt gebruikt voor de bestaande updatering. Uw opties zijn:
            - **Niet geconfigureerd**
            - **Alleen HTTP, geen peering**
            - **HTTP gemengd met peering achter dezelfde NAT**
            - **HTTP gemengd met peering in een privégroep**
            - **HTTP met internetpeering**
            - **Eenvoudige downloadmodus zonder peering**
            - **Bypass-modus**

2. Wijs dit nieuwe profiel toe aan dezelfde apparaten en gebruikers als de bestaande software-updatering. In [Het profiel toewijzen](device-profile-assign.md) worden de stappen vermeld.

3. Maak de configuratie van de bestaande softwarering ongedaan:
    1. Ga in Intune naar **Software-updates** > Windows 10-updateringen.
    2. Selecteer uw updatering in de lijst.
    3. Stel in de instellingen **Delivery Optimization-downloadmodus** in op **Niet geconfigureerd**.
    4. Kies **OK** > **Opslaan** voor uw wijzigingen.

## <a name="next-steps"></a>Volgende stappen

[Wijs het profiel toe](device-profile-assign.md) en [controleer de status](device-profile-monitor.md) van het profiel.
