---
title: Beleidsinstellingen voor het upgraden van Windows-versies
description: Leer hoe u met Intune automatisch Windows 10-apparaten kunt bijwerken naar een andere versie.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 04/14/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99c0ef47ad8f143ef9bd1d6dbfff9c94fb154007
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a>Beleidsinstellingen in Microsoft Intune voor upgrades van de Windows-editie

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Met het **Beleid voor editie-upgrades** van Microsoft Intune kunt u apparaten waarop een van de volgende edities van Windows 10 wordt uitgevoerd automatisch bijwerken naar een nieuwere editie:
* Windows 10 Desktop
* Windows 10 Holographic
* Windows 10 Mobile

De volgende upgradepaden worden ondersteund:
- Van Windows 10 Pro naar Windows 10 Enterprise
- Van Windows 10 Home naar Windows 10 Education
- Van Windows 10 Mobile naar Windows 10 Mobile Enterprise
- Van Windows 10 Holographic Pro naar Windows 10 Holographic Enterprise

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint met het upgraden van apparaten naar de nieuwste versie, hebt u een van de volgende items nodig:
* Een productcode die geldig is voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Desktop). U kunt Multi Activation Keys (MAK) of Key Management Server-sleutels (KMS) gebruiken.
**of** Een licentiebestand van Microsoft met de licentiegegevens voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Mobile en Windows 10 Holographic).
* De Windows 10-apparaten waarop u zich richt, moeten zijn geregistreerd bij Microsoft Intune. U kunt het versie-upgradebeleid niet gebruiken voor pc’s waarop de Intune-pc-clientsoftware wordt uitgevoerd.

## <a name="edition-upgrade-policy-settings"></a>Beleidsinstellingen voor editie-upgrades

|Naam van de instelling|Details|
|-|-|
|**Naam**|Geef een naam op voor het beleid voor editie-upgrades.|
|**Beschrijving**|Geef eventueel een beschrijving op voor het beleid, zodat u dit kunt herkennen in de Intune-console.
|**Editie bijwerken naar**|Selecteer in de vervolgkeuzelijst de versie van Windows 10 Desktop, Windows 10 Holographic of Windows 10 Mobile waarnaar u de apparaten uit de doelgroep wilt bijwerken.
|**Productcode**|Geef de productcode op die u van Microsoft hebt ontvangen en die kan worden gebruikt om van alle beoogde Windows 10 Desktop-apparaten een upgrade uit te voeren.<br>Nadat u een beleid met een productcode hebt gemaakt, kunt u de productcode later niet meer bewerken. Dit komt doordat de code uit veiligheidsoverwegingen wordt verborgen. Als u de productcode wilt wijzigen, moet u de volledige code opnieuw invoeren.
|**Licentiebestand**|Kies **Bladeren** om het licentiebestand te selecteren dat u hebt ontvangen van Microsoft, met daarin licentie-informatie voor de Windows Holographic-editie of Windows 10 Mobile-editie waarnaar u de beoogde apparaten wilt upgraden.

### <a name="see-also"></a>Zie ook
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
