---
title: Editie-upgrades voor Windows 10 configureren met Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u Intune kunt gebruiken voor het upgraden van Windows 10-apparaten die u beheert.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 49da713cfe61ce21501e0a8e0f6e0c225b2bc291
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Editie-upgrades voor Windows 10 configureren in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Gebruik de informatie in dit onderwerp voor informatie over het configureren van een editie-upgradeprofiel voor Windows 10. Met dit profiel kunt u apparaten waarop een van de volgende versies van Windows 10 wordt uitgevoerd, automatisch upgraden naar een nieuwere versie:

- Windows 10 Desktop
- Windows 10 Holographic
- Windows 10 Mobile

De volgende upgradepaden worden ondersteund:

- Van Windows 10 Pro naar Windows 10 Enterprise
- Van Windows 10 Home naar Windows 10 Education
- Van Windows 10 Mobile naar Windows 10 Mobile Enterprise
- Van Windows 10 Holographic Pro naar Windows 10 Holographic Enterprise

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint met het upgraden van apparaten naar de nieuwste versie, hebt u een van de volgende items nodig:

- Een productcode die geldig is voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Desktop). U kunt Multi Activation Keys (MAK) of Key Management Server-sleutels (KMS) gebruiken. of een licentiebestand van Microsoft met de licentiegegevens voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Mobile en Windows 10 Holographic).
- De Windows 10-apparaten waarop u zich richt, moeten zijn geregistreerd bij Microsoft Intune. U kunt het versie-upgradebeleid niet gebruiken voor pc’s waarop de Intune-pc-clientsoftware wordt uitgevoerd.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Een apparaatprofiel met apparaatbeperkingsinstellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het editie-upgradeprofiel.
5. Kies in de vervolgkeuzelijst **Platform** de optie **Windows 10 en hoger**.
6. Kies in de vervolgkeuzelijst **Profieltype** de optie **Editie-upgrade**.
7. Configureer de volgende instellingen op de blade **Editie-upgrade**:
    - **Editie waarvoor een upgrade moet worden uitgevoerd**: selecteer in de vervolgkeuzelijst de Windows 10-versie die u wilt upgraden op apparaten.
    - **Versie waarnaar moet worden bijgewerkt**: selecteer in de vervolgkeuzelijst de versie van Windows 10 Desktop, Windows 10 Holographic of Windows 10 Mobile waarnaar u de apparaten uit de doelgroep wilt upgraden.
    - **Productcode**: geef de productcode op die u van Microsoft hebt ontvangen en die kan worden gebruikt om alle beoogde Windows 10 Desktop-apparaten te upgraden.<br>Nadat u een beleid met een productcode hebt gemaakt, kunt u de productcode later niet meer bewerken. Dit komt doordat de code uit veiligheidsoverwegingen wordt verborgen. Als u de productcode wilt wijzigen, moet u de volledige code opnieuw invoeren.
    - **Licentiebestand**: kies **Bladeren** om het licentiebestand te selecteren dat u hebt ontvangen van Microsoft, met daarin licentie-informatie voor de Windows Holographic-editie of Windows 10 Mobile-editie waarnaar u de beoogde apparaten wilt upgraden.
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.


