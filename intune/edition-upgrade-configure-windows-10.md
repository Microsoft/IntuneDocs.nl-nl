---
title: Editie-upgrades voor Windows 10 configureren in Intune
titlesuffix: Azure portal
description: Meer informatie over het gebruik van Intune om Windows 10-apparaten die u beheert, bij te werken naar een andere editie.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 40c3ca0207ed81af3212ad2ea04598654cab7198
ms.sourcegitcommit: cf7f7e7c9e9cde5b030cf5fae26a5e8f4d269b0d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Editie-upgrades voor Windows 10 configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik de informatie in dit onderwerp voor informatie over het configureren van een editie-upgradeprofiel voor Windows 10. Met dit profiel kunt u apparaten waarop een van de volgende versies van Windows 10 wordt uitgevoerd automatisch bijwerken naar een andere editie:

- Windows 10 Home
- Windows 10 Holographic
- Windows 10 Mobile


De volgende upgradepaden worden ondersteund:

- Van Windows 10 Pro naar Windows 10 Enterprise
- Van Windows 10 Home naar Windows 10 Education
- Van Windows 10 Mobile naar Windows 10 Mobile Enterprise
- Van Windows 10 Holographic Pro naar Windows 10 Holographic Enterprise


## <a name="before-you-start"></a>Voordat u begint
Voordat u begint met het upgraden van apparaten naar de nieuwste versie, hebt u een van de volgende items nodig:

- Een productcode die geldig is voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Desktop). U kunt gebruikmaken van MAK- (Multiple Activation Keys) of KMS-sleutels (Key Management Server), of een licentiebestand van Microsoft met de licentiegegevens voor het installeren van de nieuwe versie van Windows op alle apparaten waarop het beleid is gericht (voor edities van Windows 10 Mobile en Windows 10 Holographic).
- De Windows 10-apparaten waaraan u het beleid toewijst, moeten worden geregistreerd bij Microsoft Intune. U kunt het versie-upgradebeleid niet gebruiken voor pc’s waarop de Intune-pc-clientsoftware wordt uitgevoerd.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Een apparaatprofiel met apparaatbeperkingsinstellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
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

## <a name="next-steps"></a>Volgende stappen

Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.

>[!NOTE]
>Als u later de beleidstoewijzing verwijdert, wordt de versie van Windows niet teruggezet, maar blijft normaal functioneren.

