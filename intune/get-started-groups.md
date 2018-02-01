---
title: Aan de slag met groepen
titleSuffix: Azure portal
description: Deel gebruikers in groepen in om het beleid en de apps waar ze toegang toe hebben gemakkelijker te beheren.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63a35c04a14ebd79ac55f1dab2680d70008ee0ed
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="get-started-with-groups"></a>Aan de slag met groepen

Groepen worden gebruikt om uw gebruikers te beheren en de toegang van uw medewerkers tot uw zakelijke resources te regelen. Deze resources kunnen deel uitmaken van uw directory of externe resources zijn, zoals SaaS-apps of SharePoint-sites.

Microsoft Intune maakt gebruik van Azure Active Directory (Azure AD) om de toegang tot zakelijke resources te beheren. Deze toegang wordt beheerd met behulp van rollen in de adreslijst. Intune beheert vervolgens deze toegang voor mobiele apparaten, waarmee leden van die groep toegang krijgen tot resources.

## <a name="how-do-i-create-a-group"></a>Hoe maak ik een groep?

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Gebruik **Resources zoeken** om te zoeken naar **Intune**.
3. Selecteer **Groepen** nadat u de blade **Microsoft Intune** hebt geopend.
4. Selecteer de opdracht **Nieuwe groep** op de blade **Gebruikers en groepen – Alle groepen**.
5. Geef op de blade **Groep** waarden op voor **Naam** en **Beschrijving** voor de groep.
6. Stel **Type lidmaatschap** in op **Toegewezen**. Schakel de optie **Office-functies inschakelen** niet in voor de testgroep.
7. Klik op **Maken**.

Als u een groep hebt gemaakt, wordt deze weergegeven in de lijst **Alle groepen**. Als dat niet het geval is, kunt u nogmaals proberen om een groep te maken.

## <a name="next-steps"></a>Volgende stappen

[Aan de slag met beleid](get-started-policies.md) - Maak beleid om te voorkomen dat gebruikers niet-geautoriseerde activiteiten uitvoeren met hun apparaten.

## <a name="learn-more"></a>Meer informatie

* [Registratiebeperkingen in Intune instellen aan de hand van groepen](groups-add.md)
* [Toegang tot zakelijke resources beheren aan de hand van groepen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
