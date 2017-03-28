---
title: Opleidingsinstellingen configureren in Intune
titleSuffix: Intune Azure preview
description: 'Preview-versie van Intune Azure: lees hoe u met Intune opleidingsinstellingen configureert op de apparaten die u beheert.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 5c73719c4fd2805f91c6af3ba48c39f5d798aaeb
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-education-settings-in-microsoft-intune"></a>Opleidingsinstellingen configureren in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met opleidingsprofielen kunt u gegevens opgeven waarmee de Windows Toets maken-app wordt geconfigureerd, zoals de accountgegevens en de URL voor de toets. Wanneer u de Toets maken-app hebt geconfigureerd, wordt deze geopend met de toets die u hebt opgegeven en kunnen er geen andere apps op het apparaat worden uitgevoerd totdat de toets is voltooid.

Gebruik de informatie in dit onderwerp voor meer informatie over de basisbeginselen voor het configureren van apparaatbeperkingsprofielen en lees vervolgens de aanvullende onderwerpen voor elk platform voor meer apparaatspecifieke informatie.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Een apparaatprofiel maken dat de opleidingsprofielinstellingen bevat

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
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
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.




