---
title: Instellingen voor Endpoint Protection configureren in Microsoft Intune - Azure | Microsoft Docs
description: Instellingen voor Endpoint Protection in Microsoft Intune maken wanneer u een profiel voor een macOS- of Windows 10-apparaat maakt.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 3/27/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: add75e252c8d49025ac01832e5fb12afea9ede67
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57398559"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Instellingen voor Endpoint Protection toevoegen in Intune

Met Endpoint Protection kunt u verschillende beveiligingsfuncties op uw apparaten beheren, zoals de firewall, BitLocker, het toestaan en blokkeren van apps, Windows Defender en versleuteling. U kunt deze instellingen in Microsoft Intune configureren met apparaatprofielen.

U kunt bijvoorbeeld een Endpoint Protection-profiel maken waarmee macOS-gebruikers alleen apps uit de Mac App Store kunnen installeren. Of u kunt Windows SmartScreen inschakelen bij het uitvoeren van apps op Windows 10-apparaten.

In dit artikel leest u hoe een profiel maakt. Selecteer vervolgens uw apparaatplatform voor meer informatie over de beschikbare instellingen.

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Een apparaatprofiel met instellingen voor Endpoint Protection maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
4. Geef een **naam** en **beschrijving** op voor het Endpoint Protection-profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor apparaatbeperkingsinstellingen:
   - **macOS**
   - **Windows 10 en hoger**
6. Kies **Endpoint Protection** in de vervolgkeuzelijst **Profieltype**. 
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
   - [macOS-instellingen](endpoint-protection-macos.md)
   - [Windows 10-instellingen](endpoint-protection-windows-10.md)
8. Als u klaar bent, gaat u terug naar de pagina **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de pagina met de profielenlijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om dit profiel toe te wijzen aan groepen.

## <a name="next-steps"></a>Volgende stappen
Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om een profiel toe te wijzen aan groepen.
