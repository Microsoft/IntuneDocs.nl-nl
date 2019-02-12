---
title: Een groep maken in Microsoft Intune
titleSuffix: ''
description: Deel gebruikers in groepen in om het beleid en de apps waar ze toegang toe hebben gemakkelijker te beheren.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8b7e187bb182db0491e055ce3af3833d82e578de
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842402"
---
# <a name="create-a-group-to-manage-your-users-and-data-access"></a>Een groep maken om uw gebruikers en de toegang tot gegevens te beheren

Groepen worden gebruikt om uw gebruikers te beheren en de toegang van uw medewerkers tot uw zakelijke resources te regelen. Deze resources kunnen deel uitmaken van uw directory of externe resources zijn, zoals SaaS-apps of SharePoint-sites.

Microsoft Intune maakt gebruik van Azure Active Directory (Azure AD) om de toegang tot zakelijke resources te beheren. Deze toegang wordt beheerd met behulp van rollen in de adreslijst. Intune beheert vervolgens deze toegang voor mobiele apparaten, waarmee leden van die groep toegang krijgen tot resources.

## <a name="how-do-i-create-a-group"></a>Hoe maak ik een groep?

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Groepen** nadat u het deelvenster **Microsoft Intune** hebt geopend.
4. In het deelvenster **Gebruikers en groepen - Alle groepen** selecteert u de opdracht **Nieuwe groep**.
5. In het deelvenster **Groep** kiest u een **groepstype**.
5. Geef een **naam** en **beschrijving** op voor de groep.
6. Stel **Type lidmaatschap** in op **Toegewezen**. Schakel de optie **Office-functies inschakelen** niet in voor de testgroep.
7. Selecteer **leden** voor de groep.
7. Klik op **Maken**.

Als u een groep hebt gemaakt, wordt deze weergegeven in de lijst **Alle groepen**. Als dat niet het geval is, kunt u nogmaals proberen om een groep te maken.

## <a name="next-steps"></a>Volgende stappen

[Aan de slag met beleid](get-started-policies.md) - Maak beleid om te voorkomen dat gebruikers niet-geautoriseerde activiteiten uitvoeren met hun apparaten.

## <a name="learn-more"></a>Meer informatie

* [Registratiebeperkingen in Intune instellen aan de hand van groepen](groups-add.md)
* [Toegang tot zakelijke resources beheren aan de hand van groepen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
