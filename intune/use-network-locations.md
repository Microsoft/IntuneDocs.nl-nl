---
title: Android-apparaten binden op netwerklocatie in Microsoft Intune - Azure | Microsoft Docs
description: Maak of configureer netwerklocaties in Microsoft Intune voor Android-apparaten. U kunt apparaten als niet-compatibel markeren op basis van de netwerklocatie van het apparaat. Als het apparaat zich buiten de netwerklocatie begeeft, kunt u de toegang tot bedrijfsresources blokkeren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ayesham
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ad1c633261e4d917cb88793efbac2ff4416dd429
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236684"
---
# <a name="use-locations-network-fence-in-intune"></a>Locaties (netwerkomheining) in Intune gebruiken

Mogelijk wilt u de toegang tot een bedrijfsnetwerk blokkeren als een apparaat zich buiten een locatie begeeft. Met de functie **Locaties** in Intune beschikt u over deze functionaliteit. 

U kunt een nalevingsbeleid maken op basis van de netwerklocatie. Dit staat ook wel bekend als netwerkomheining. Apparaten voldoen pas aan het beleid, en zijn dus compatibel, wanneer ze zijn verbonden met een bedrijfsnetwerk. Dit beleid kan worden gebruikt met beleid voor voorwaardelijke toegang zodat apparaten *alleen* toegang hebben tot bedrijfsresources wanneer het apparaat verbonden is met het bedrijfsnetwerk. Wanneer het apparaat niet verbonden is met het bedrijfsnetwerk, voldoet het niet meer aan het beleid en krijgt het geen toegang meer tot de bedrijfsresources.

Neem het volgende scenario in overweging:

In uw productiefaciliteit gebruiken sommige werknemers Android-apparaten. Een werknemer neemt het Android-apparaat mee buiten de faciliteit of fabriek. U kunt het volgende doen om onbevoegde toegang te voorkomen:

1. Maak een locatie met een IPv4-bereik met de naam **Werkvloer**.
2. Maak een nalevingsbeleid waarbij deze apparaten verbonden moeten zijn met uw bedrijfsnetwerk en wijs dit beleid toe.
3. Als het apparaat zich buiten de productiefaciliteit begeeft, wordt het apparaat als niet-compatibel beschouwd en heeft het geen toegang tot de bedrijfsresources.

U kunt ook [acties voor niet-naleving](#configure-the-actions-for-noncompliance) toevoegen. Wanneer het apparaat weer op de locatie is en zich in de netwerklocatie bevindt, krijgt het weer toegang tot bedrijfsresources.

## <a name="prerequisites"></a>Vereisten

U kunt als volgt een nalevingsbeleid op basis van locatie maken:

- Een netwerklocatie maken als IPv4-netwerkbereiken voor de gatewayserver, DHCP-server en/of DNS-server die de apparaten verbinden
- Het nalevingsbeleid maken dat gebruikmaakt van deze locaties en de actie definieert die wordt ondernomen wanneer het apparaat niet meer verbonden is met de netwerklocatie
- Android-apparaten met versie 6.0 en hoger, met de bijgewerkte bedrijfsportal-app

## <a name="create-a-location"></a>Een locatie maken

1. Selecteer in Intune **Apparaatcompatibiliteit** > **Locaties** > **Maken**.

2. Voer de volgende eigenschappen in:  

   - Vereist. Voer een **naam** in voor de locatie, zoals **Werkvloer** of **Gebouw 44-veilig**.
   - Optioneel. Geef een **IPv4-bereik** op in de CIDR-notatie (Classless Interdomain Routing), zoals `aaa.bbb.ccc.ddd/n`.
   - Optioneel. Voer het adres van de **IPv4-gateway** in, zoals `aaa.bbb.ccc.ddd`.
   - Optioneel. Voer het adres van de **IPv4 DHCP-server** in, zoals `aaa.bbb.ccc.ddd`.
   - Optioneel. Geef een lijst met adressen van **IPv4 DNS-servers** op. Deze instelling maakt gebruik van **subsetkoppeling**. Als de IPv4 DNS-servers op het apparaat subsets zijn van de waarden die zijn gedefinieerd, wordt het apparaat als BINNEN de omheining beschouwd. Voer één adres per regel in, zoals:  
     `aaa.bbb.ccc.ddd`  
     `aaa.bbb.ccc.ddd`
   - Optioneel. Voer een lijst met **DNS-achtervoegsels** in. Deze instelling maakt gebruik van **subsetkoppeling**. Als de DNS-achtervoegsels op het apparaat subsets zijn van de waarden die zijn gedefinieerd, wordt het apparaat als BINNEN de omheining beschouwd. Voer op elke regel één domeinnaam in, zoals:  
     `contoso.com`  
     `contoso.org`

3. U moet vervolgens de wijzigingen **Opslaan**.

## <a name="create-the-location-compliance-policy"></a>Het nalevingsbeleid op basis van locatie maken

Wanneer u het nalevingsbeleid maakt, selecteert u **Android** voor **Platform**. In **Locaties** kunt u een of meer van de netwerklocaties kiezen die u hebt toegevoegd. Deze locaties maken deel uit van de netwerkomheining die u voor uw apparaten maakt.

In [Het nalevingsbeleid op basis van de netwerklocatie maken](compliance-policy-create-android.md#locations) vindt u enkele richtlijnen.

## <a name="configure-the-actions-for-noncompliance"></a>De acties voor niet-naleving configureren

Nadat het nalevingsbeleid is gemaakt, wordt de standaardactie voor niet-naleving op het apparaat toegepast. U kunt meer acties toevoegen. U kunt bijvoorbeeld een actie toevoegen, waarbij een e-mailbericht naar de gebruiker wordt verzonden wanneer het apparaat niet meer voldoet aan de locaties.

In [Acties voor niet-naleving toevoegen](actions-for-noncompliance.md) vindt u enkele richtlijnen.

## <a name="company-portal-app"></a>Bedrijfsportal-app

Wanneer het apparaat verbonden is met uw locaties, wordt het apparaat in de bedrijfsportal-app weergegeven als compatibel. Wanneer het apparaat niet verbonden is met een van uw locaties, wordt het apparaat weergegeven als niet-compatibel.

## <a name="next-steps"></a>Volgende stappen
[Nalevingsbeleid voor apparaten controleren](compliance-policy-monitor.md)  
[Aan de slag met nalevingsbeleid](device-compliance-get-started.md)
