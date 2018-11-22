---
title: Mogelijkheden die Intune biedt per inschrijvingsmethode voor Windows-apparaten
titlesuffix: Microsoft Intune
description: Bekijk voor welke mogelijkheden elke inschrijvingsmethode ondersteuning biedt voor Windows-apparaten.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 457acdc212855767687f97f7d03b731f35afad46
ms.sourcegitcommit: 490f68479af814fbea1d9bd222011736fcbb1dd6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/16/2018
ms.locfileid: "51811526"
---
# <a name="capabilities-by-enrollment-method-for-windows-devices"></a>Mogelijkheden per inschrijvingsmethode voor Windows-apparaten
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Met Intune kunt u de apparaten en apps beheren waarvan uw werknemers gebruikmaken en kunt u beheren hoe zij toegang hebben tot uw bedrijfsgegevens. De apparaten moeten eerst worden ingeschreven bij de Intune-service. Er zijn verschillende methoden om de apparaten van uw werknemers te registreren. Voor elke methode gelden andere aanbevolen procedures en mogelijkheden, zoals wordt weergegeven in de onderstaande tabellen.

## <a name="best-practices-by-enrollment-method"></a>Aanbevolen procedures per inschrijvingsmethode
| **Best practices** | **[Neemt deel aan Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Neemt deel aan Azure AD via Autopilot](enrollment-autopilot.md)** |**[Bulk](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Veel gebruikt in EDU|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Apparaten kunnen worden gebruikt als gedeelde apparaten|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Persoonlijke apparaten moeten toegang hebben tot bedrijfsresources|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|
|Self-service voor apps|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|

## <a name="capabilities-by-enrollment-method"></a>Mogelijkheden per inschrijvingsmethode

| **Mogelijkheden** | **[Neemt deel aan Azure AD](windows-enroll.md#enable-windows-10-automatic-enrollment)**|**[Neemt deel aan Azure AD via Autopilot](enrollment-autopilot.md)** |**[Bulk](windows-bulk-enroll.md)**|**[DEM](device-enrollment-manager-enroll.md)** | **[BYOD](device-enrollment.md#bring-your-own-device)** | **[GPO](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
|Voorwaardelijke toegang                                      |![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|
|Gebruikers worden gekoppeld aan apparaten                    |![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|
|Azure AD Premium is vereist                               |![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|
|Apparaten krijgen toegang tot resources met CA-beveiliging             |![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|
|Gebruikers mogen geen beheerder zijn op hun apparaat               |![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Mogelijkheid om de apparaatconfiguratie-ervaring te wijzigen        |![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|
|Mogelijkheid om apparaten in te schrijven zonder tussenkomst van de gebruiker      |![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|
|Mogelijkheid om PowerShell-scripts uit te voeren                       |![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|![X](media/xmark.png)| 
|Biedt ondersteuning voor automatische inschrijving na AD-domeindeelname      |![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|
|Biedt ondersteuning voor automatische inschrijving na hybride Azure AD-deelname|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![X](media/xmark.png)|![Vinkje](media/checkmark.png)|
|Biedt ondersteuning voor automatische inschrijving na Azure AD-deelname       |![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![Vinkje](media/checkmark.png)|![X](media/xmark.png)|

## <a name="next-steps"></a>Volgende stappen

[Inschrijving voor Windows instellen](windows-enroll.md)

