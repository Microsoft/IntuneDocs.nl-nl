---
title: Instellingen voor Endpoint Protection configureren in Microsoft Intune - Azure | Microsoft Docs
description: Instellingen voor Endpoint Protection in Microsoft Intune maken wanneer u een profiel voor een macOS- of Windows 10-apparaat maakt.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 5/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
mr.reviewer: karthib
ms.openlocfilehash: c13c5d71d1ff631d7a3c84cd3f62037569757917
ms.sourcegitcommit: bc5e4dff18f5f9b79077a888f8a58dcc490708c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2019
ms.locfileid: "65975765"
---
# <a name="add-endpoint-protection-settings-in-intune"></a>Instellingen voor Endpoint Protection toevoegen in Intune

Met Intune kunt u configuratieprofielen voor apparaten gebruiken voor het beheren van algemene beveiligingsfuncties voor eindpunten op apparaten, waaronder:
- Firewall 
- BitLocker
- Apps toestaan en blokkeren  
- Windows Defender en versleuteling

U kunt bijvoorbeeld een Endpoint Protection-profiel maken waarmee macOS-gebruikers alleen apps uit de Mac App Store kunnen installeren. Of u kunt Windows SmartScreen inschakelen bij het uitvoeren van apps op Windows 10-apparaten.

Lees voordat u een profiel maakt de volgende artikelen door, zodat u precies weet welke instellingen voor de bescherming van eindpunten Intune kan beheren voor elk ondersteund platform: 
   - [macOS-instellingen](endpoint-protection-macos.md)
   - [Windows 10-instellingen](endpoint-protection-windows-10.md)

## <a name="create-a-device-profile-containing-endpoint-protection-settings"></a>Een apparaatprofiel met instellingen voor Endpoint Protection maken

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=20909).
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
4. Geef een **naam** en **beschrijving** op voor het Endpoint Protection-profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de aangepaste instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor apparaatbeperkingsinstellingen:
   - **macOS**
   - **Windows 10 en hoger**
6. Kies **Endpoint Protection** in de vervolgkeuzelijst **Profieltype**. 
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Zie:
   - [macOS-instellingen](endpoint-protection-macos.md)
   - [Windows 10-instellingen](endpoint-protection-windows-10.md)  

8. Nadat u de gewenste instellingen hebt geconfigureerd, selecteert u **Maken** op de pagina **Profiel maken**.

   Het profiel wordt gemaakt en wordt weergegeven op de pagina met de profielenlijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om dit profiel toe te wijzen aan groepen.


## <a name="next-steps"></a>Volgende stappen  

Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om een profiel toe te wijzen aan groepen.
