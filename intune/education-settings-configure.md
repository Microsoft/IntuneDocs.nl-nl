---
title: Intune-onderwijsinstellingen configureren voor Windows 10
titleSuffix: Azure portal
description: Meer informatie over het gebruik van Intune om Windows 10 Education-instellingen te configureren op apparaten die u beheert.
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b50c35dc805d033bd905105c22c4ec287dfaa1b7
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Windows 10 Education-instellingen configureren in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met opleidingsprofielen kunt u gegevens opgeven waarmee de Windows Toets maken-app wordt geconfigureerd, zoals de accountgegevens en de URL voor de toets. Wanneer u de Toets maken-app hebt geconfigureerd, wordt deze geopend met de toets die u hebt opgegeven en kunnen er geen andere apps op het apparaat worden uitgevoerd totdat de toets is voltooid.

Zie [Toetsen maken in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) voor meer informatie over de Toets maken-app.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Een apparaatprofiel maken dat de opleidingsprofielinstellingen bevat

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies op de blade **Intune** de optie **Apparaatconfiguratie**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en **beschrijving** in voor het apparaatbeperkingsprofiel.
5. Selecteer in de vervolgkeuzelijst **Platform** de optie **Windows 10 en hoger**.
6. Kies **Opleidingsprofiel** in de vervolgkeuzelijst **Profieltype**. 
7. Kies Instellingen > Configureren en configureer vervolgens op de blade **Toets maken** het volgende:
    - **Gebruikersnaam voor het account**: voer de gebruikersnaam in voor het account dat wordt gebruikt voor Toets maken. Dit kan een domeinaccount, een AAD-account (Azure Active Directory) of een lokaal account op een computer zijn.
    - **URL van de toets**: geef de URL op van de toets die de gebruikers moeten afleggen. Zie de documentatie van Toets maken voor meer informatie.
    - **Schermcontrole**: geef op of u de schermactiviteiten wilt kunnen controleren terwijl de gebruikers een toets afleggen.
    - **Tekstsuggestie**: tekstsuggesties toestaan of blokkeren terwijl de gebruikers een toets afleggen.
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

## <a name="next-steps"></a>Volgende stappen

Zie [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.



