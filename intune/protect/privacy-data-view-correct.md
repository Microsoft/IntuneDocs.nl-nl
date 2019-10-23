---
title: Persoonlijke gegevens weergeven en corrigeren
titleSuffix: Microsoft Intune
description: Informatie over het weergeven en corrigeren van persoonlijke gegevens.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 1ba77bc7-505e-4eca-a49e-dcdaa75d0043
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 913bf3103254abdd73913e0efc81da3a38ca991b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504252"
---
# <a name="view-and-correct-personal-data"></a>Persoonlijke gegevens weergeven en corrigeren

Intune-beheerders kunnen bepaalde persoonlijke gegevens weergeven op basis van de toegangsmachtigingen, maar alleen eindgebruikers kunnen de persoonlijke gegevens op hun apparaat wijzigen.

[!INCLUDE [GDPR-related guidance](../includes/gdpr-dsr-and-stp-note.md)]


## <a name="view-personal-data"></a>Persoonlijke gegevens weergeven

Beheerders kunnen persoonlijke gegevens van de eindgebruiker in verschillende blades in de gebruikersinterface van Intune zien. In de volgende artikelen wordt uitgelegd waartoe informatiebeheerders wel en geen toegang hebben:
- In [Apparaatdetails weergeven](../remote-actions/device-inventory.md) in Intune wordt uitgelegd hoe u de details van een apparaat van een eindgebruiker kunt weergeven.
- In [App-gegevens en -toewijzingen controleren](../apps/apps-monitor.md) wordt uitgelegd hoe u details over geïnstalleerde apps op een apparaat van een eindgebruiker kunt weergeven.
- Het artikel [Welke gegevens kan mijn bedrijf zien wanneer ik mijn apparaat inschrijf?](https://docs.microsoft.com/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) bevat een lijst met gegevens voor eindgebruikers van alle gegevens die hun bedrijf wel en niet kunnen zien. U kunt uw gebruikers het best vertellen wat voor soort gegevens u verzamelt en waarom u die wilt verzamelen. Dit artikel kan de eerste stap in die transparantie zijn.

### <a name="who-can-view-the-data"></a>Wie kan de gegevens bekijken?

Microsoft gebruikt strikte besturingselementen om de toegang tot klantgegevens te beheren en kent het laagste toegangsniveau toe dat is vereist om belangrijke taken te voltooien. De toegang wordt ingetrokken zodra deze niet meer nodig is. 

U kunt de toegang tot persoonlijke gegevens van eindgebruikers beveiligen en beheren met op rollen gebaseerd toegangsbeheer (RBAC). Zie [RBAC met Microsoft Intune](../fundamentals/role-based-access-control.md) voor meer informatie.

U vindt meer informatie over de Microsoft-procedures voor gegevens in de voorwaarden voor onlineservices en de [privacyverklaring van Microsoft Online Services](https://go.microsoft.com/fwlink/p/?linkid=131004&clcid=0x409). 

## <a name="correct-end-user-personal-data"></a>Persoonlijke gegevens van eindgebruikers corrigeren

Beheerders kunnen specifieke informatie over apparaten of apps niet bijwerken. Als eindgebruikers persoonlijke gegevens willen corrigeren (zoals de naam van het apparaat), moeten ze dit direct op hun apparaat doen. De wijzigingen worden de volgende keer dat ze verbinding maken met Intune gesynchroniseerd.


## <a name="next-steps"></a>Volgende stappen

Ontdek hoe u persoonlijke gegevens in Intune kunt [controleren, exporteren of verwijderen](privacy-data-audit-export-delete.md).
