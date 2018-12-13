---
title: Delivery Optimization-instellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Configureer hoe software-updates worden geleverd bij uw apparaten met behulp van de Delivery Optimization-cloudservices die beschikbaar zijn met Windows 10-apparaten en latere apparaten. Maak in Intune een apparaatconfiguratieprofiel om updates van internet te installeren. Kijk ook hoe u bestaande updateringen kunt vervangen door een Delivery Optimization-profiel.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36cfb5ac05b2d69b5c7349f4ebc6054848a08fc8
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2018
ms.locfileid: "52730399"
---
# <a name="windows-10-and-newer-delivery-optimization-settings-in-microsoft-intune"></a>Delivery Optimization-instellingen voor Windows 10-apparaten (en nieuwer) in Microsoft Intune

In dit artikel worden alle Delivery Optimization-instellingen vermeld en beschreven die u kunt configureren voor Windows 10-apparaten. Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel, en vervolgens toegewezen aan of geïmplementeerd op uw apparaten met behulp van Microsoft Intune.

## <a name="settings"></a>Instellingen

**Delivery Optimization-downloadmodus**: kies hoe updates worden geleverd bij uw apparaten. Uw opties zijn:

- **Niet geconfigureerd**: eindgebruikers werken hun apparaten op hun eigen manier bij, bijvoorbeeld via de instellingen voor **Windows Updates** of **Delivery Optimization** die beschikbaar zijn met het besturingssysteem.
- **Alleen HTTP, geen peering**: ontvang alleen updates via internet. Ontvang geen updates van andere computers in het netwerk (peering of peer-to-peer genoemd).
- **HTTP met peers achter hetzelfde NAT HTTP met peers in een privégroep**: ontvang updates via internet en van andere computers in het netwerk. Peering komt voor op apparaten op dezelfde Active Directory-site (indien deze bestaat) of in hetzelfde domein. Als deze optie is geselecteerd, vindt peering plaats voor de IP-adressen van uw NAT’s (Network Address Translation).
- **HTTP met internetpeering**: ontvang updates via internet en van andere computers in het netwerk.
- **Eenvoudige downloadmodus zonder peering**: ontvangt updates via internet, rechtstreeks van de update-eigenaar, bijvoorbeeld Microsoft. Er wordt geen verbinding gemaakt met de Delivery Optimization-cloudservices.
- **Bypass-modus**: gebruik BITS-bandbreedtebeperking (Background Intelligent Transfer Service) om updates op te halen. Gebruik Delivery Optimization niet.

## <a name="move-from-existing-update-rings-to-delivery-optimization"></a>Verplaatsen van bestaande updateringen naar Delivery Optimization

**Software-updates – Windows 10-updateringen** worden vervangen door de **Delivery optimization**-instellingen. Bestaande updateringen kunnen eenvoudig worden gewijzigd voor gebruik van de **Delivery Optimization**-instellingen. Stappen:

1. Een Delivery Optimization-configuratieprofiel maken:

    1. Selecteer in Intune **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
    2. Geef een **Naam** en **Beschrijving** op voor het profiel.
    3. Kies bij **Platform** de optie **Windows 10 en hoger**. Kies bij **Profieltype** de optie **Delivery Optimization**.
    4. Selecteer **Instellingen**. Kies voor **Delivery Optimization-downloadmodus** dezelfde modus als wordt gebruikt voor de bestaande updatering. Uw opties zijn:
        - **Niet geconfigureerd**
        - **Alleen HTTP, geen peering**
        - **HTTP met peers achter hetzelfde NAT HTTP met peers in een privégroep**
        - **HTTP met internetpeering**
        - **Eenvoudige downloadmodus zonder peering**
        - **Bypass-modus**

2. Wijs dit nieuwe profiel toe aan dezelfde apparaten en gebruikers als de bestaande software-updatering. In [Het profiel toewijzen](device-profile-assign.md) worden de stappen vermeld.

3. Maak de configuratie van de bestaande softwarering ongedaan:
    1. Ga in Intune naar **Software-updates** > Windows 10-updateringen.
    2. Selecteer uw updatering in de lijst.
    3. Stel in de Instellingen de **Delivery Optimization-downloadmodus** in op **Niet geconfigureerd**.
    4. Kies **OK** > **Opslaan** voor uw wijzigingen.

## <a name="next-steps"></a>Volgende stappen

[Wijs het profiel toe](device-profile-assign.md) en [controleer de status](device-profile-monitor.md) van het profiel.