---
title: Onderwijsinstellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Een lijst met alle onderwijsinstellingen voor Windows 10-apparaten weergeven. Gebruik deze instellingen in een apparaatconfiguratieprofiel met de app Toets maken, kies hoe gebruikers of studenten zich aanmelden, controleer het scherm tijdens de toets, en meer in Intune.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 07/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: kakyker
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7d89f512c06dcfbf6f6ddaba5e17ac9ca6f0becf
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72506802"
---
# <a name="configure-the-take-a-test-app-on-windows-10-devices-using-intune"></a>De app Toets maken configureren op Windows 10-apparaten in Microsoft Intune

Met de app voor het maken van een test kunt u veilig online testen op de Windows 10-apparaten van uw klas beheren. Als u de app voor het maken van een test wilt instellen, moet u een configuratie profiel voor een apparaat in intune maken en de instellingen voor veilige evaluatie configureren. In dit artikel worden de instellingen beschreven die u vindt voor de app een test maken. 

Nadat u het profiel hebt geconfigureerd, wijst u het toe en implementeert u het aan uw studenten. 

In [De app Toets maken in Intune](education-settings-configure.md) vindt u meer informatie over deze functie.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](education-settings-configure.md#create-a-device-profile).

## <a name="take-a-test-settings"></a>Instellingen voor Toets maken
Nadat u een configuratie profiel voor een apparaat hebt gemaakt, gaat u naar **profiel type** en selecteert u **beveiligde evaluatie (onderwijs)** . U vindt de volgende app-instellingen voor testen. 


- **Accounttype**: kies hoe gebruikers zich aanmelden voor de toets. Uw opties zijn:
  - Microsoft Azure Active Directory-account
  - Domeinaccount
  - Lokaal account
  - Lokaal gast account: alleen beschikbaar op apparaten met Windows 10, versie 1903 en hoger.    
- **Gebruikersnaam voor het account**: voer de gebruikersnaam in voor het account dat wordt gebruikt voor de app Toets maken. U kunt accounts in de volgende indeling invoeren:
  - `user@contoso.com`
  - `domain\username`
  - `user@contoso.com`
  - `computerName\username`
- **Account naam**: als u een lokaal gast account type wilt instellen, voert u de naam in van het account dat wordt gebruikt met de app een test maken. De account naam wordt weer gegeven als een tegel in het aanmeldings scherm. Studenten klikken op de tegel om de test te starten.  
- **URL van de toets**: geef de URL op van de toets die de gebruikers moeten afleggen. Zie de [documentatie van Toets maken](https://docs.microsoft.com/education/windows/take-tests-in-windows-10) voor meer informatie over het ophalen van de URL.
- **Printer verbinding**: Kies **vereist** om alleen toegang toe te staan tot de app voor het maken van een test vanaf apparaten die zijn verbonden met een printer. Met deze instelling wordt de afdruk knop van de app ook beschikbaar voor test-takers. **Niet geconfigureerd** staat studenten toe om toegang te krijgen tot de app vanaf apparaten die niet zijn verbonden met een printer.  
- **Schermcontrole**: kies **Toestaan** om de schermactiviteit te controleren terwijl de gebruikers een toets afleggen. Met **Niet geconfigureerd** wordt voorkomen dat u het scherm controleert tijdens de toets.
- **Tekstsuggesties**: kies **Toestaan** zodat mensen die de toets afleggen tekstsuggesties zien. Met **Niet geconfigureerd** worden tekstsuggesties geblokkeerd terwijl gebruikers een toets afleggen.

## <a name="next-steps"></a>Volgende stappen

Zorg ervoor dat u [het profiel toewijst](device-profile-assign.md) en [de status ervan controleert](device-profile-monitor.md).
