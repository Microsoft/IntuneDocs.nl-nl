---
title: Mogelijkheden die Intune biedt per inschrijvingsmethode voor Windows-apparaten
titlesuffix: Microsoft Intune
description: Mogelijkheden per inschrijvingsmethode voor Windows-apparaten.
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
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa71461b136243262146502adc0f7b925b345a0b
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55839325"
---
# <a name="intune-enrollment-method-capabilities-for-windows-devices"></a>Mogelijkheden die Intune biedt per inschrijvingsmethode voor Windows-apparaten
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Er zijn verschillende methoden om de apparaten van uw werknemers te registreren in Intune. Voor elke methode gelden andere aanbevolen procedures en mogelijkheden, zoals wordt weergegeven in de onderstaande tabellen.

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

