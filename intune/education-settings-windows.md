---
title: Onderwijsinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Een lijst met alle onderwijsinstellingen voor Windows 10-apparaten weergeven. Gebruik deze instellingen in een apparaatconfiguratieprofiel met de app Toets maken, kies hoe gebruikers of studenten zich aanmelden, controleer het scherm tijdens de toets, en meer in Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae26d35a50ffd2b5b40f262ddebeab8d53d87223
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846686"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>De app Toets maken configureren op Windows 10-apparaten in Microsoft Intune

In dit artikel komt u meer te weten over de Microsoft Intune-onderwijsinstellingen voor de app Toets maken die u kunt configureren op apparaten met Windows 10 en hoger. Met behulp van deze app, kunnen studenten zich aanmelden bij een apparaat en een toets maken.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel, en vervolgens toegewezen aan of geïmplementeerd op uw apparaten met behulp van Microsoft Intune.

In [De app Toets maken in Intune](education-settings-configure.md) vindt u meer informatie over deze functie.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Instellingen voor Toets maken

- **Accounttype**: kies hoe gebruikers zich aanmelden voor de toets. Uw opties zijn:
  - Microsoft Azure Active Directory-account
  - Domeinaccount
  - Lokaal account
- **Gebruikersnaam voor account**: voer de gebruikersnaam in voor het account dat wordt gebruikt voor de app Toets maken. U kunt accounts in de volgende indeling invoeren:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **URL van de toets**: geef de URL op van de toets die de gebruikers moeten afleggen. Zie de [documentatie van Toets maken](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) voor meer informatie over het ophalen van de URL.
- **Schermcontrole**: kies **Toestaan** om de schermactiviteiten te controleren terwijl de gebruikers een toets afleggen. Met **Niet geconfigureerd** wordt voorkomen dat u het scherm controleert tijdens de toets.
- **Tekstsuggestie**: kies **Toestaan** om makers van de toets toe te staan tekstsuggesties te zien. Met **Niet geconfigureerd** worden tekstsuggesties geblokkeerd terwijl gebruikers een toets afleggen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt mogelijk nog niets. Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](device-profile-monitor.md).
