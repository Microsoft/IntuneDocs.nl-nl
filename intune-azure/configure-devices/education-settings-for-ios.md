---
title: Intune-onderwijsinstellingen configureren voor iOS
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over de instellingen die u kunt gebruiken om onderwijsinstellingen op iOS-apparaten te configureren.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 44c427f8-0f22-43c2-8c29-e0f9fa533b1f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8d801c0b264e95348f55b1d4046c00e43ead5d10
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-intune-education-settings-for-ios-devices-in-intune-azure-preview"></a>Intune-onderwijsinstellingen voor iOS-apparaten configureren in Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="create-a-device-profile-containing-ios-education-settings"></a>Een apparaatprofiel met iOS-onderwijsinstellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het editie-upgradeprofiel.
5. Kies **iOS** in de vervolgkeuzelijst **Platform**.
6. Kies **Onderwijs** in de vervolgkeuzelijst **Profieltype**.
7. Selecteer het volgende op de blade **Onderwijs**:
    - **Basiscertificaatbestand voor docent**
    - **PKCS12-/PFX-profiel voor docent**
    - **Basiscertificaatbestand voor student**
    - **PKCS12-/PFX-profiel voor student**
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.

