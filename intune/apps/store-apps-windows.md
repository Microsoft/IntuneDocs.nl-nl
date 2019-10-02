---
title: Microsoft Store-apps toevoegen aan Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u Microsoft Store (Windows Store)-apps toevoegt aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e42924ba4a00b0bb4c4da6de3dbac5c3879966aa
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2019
ms.locfileid: "71724513"
---
# <a name="add-microsoft-store-apps-to-microsoft-intune"></a>Microsoft Store-apps toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Voordat u apps kunt toewijzen, controleren, configureren of beveiligen, moet u ze aan Intune toevoegen. 

## <a name="add-an-app-to-intune"></a>Een app toevoegen aan Intune
U kunt op de volgende manier een Microsoft Store-app toevoegen aan Intune:

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
4. Selecteer in het workloaddeelvenster **Client-apps** onder **Beheren** de optie **Apps**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. Kies in het deelvenster **App toevoegen** een **app-type** van **Windows** en kies **App-gegevens**.
7. Voeg in het deelvenster **App-gegevens** de app-gegevens toe. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld:
    - **Naam**: Voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. Zorg ervoor dat u alleen unieke app-namen gebruikt. Als u twee dezelfde app-namen gebruikt, wordt voor gebruikers slechts één naam in de bedrijfsportal weergegeven.
    - **Beschrijving**: Voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **URL App Store**: typ de URL naar de App Store voor de app die u wilt maken.
    - **Categorie**: Selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om het app-pakket prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers naar apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: Voer een naam in voor de eigenaar van deze app, bijvoorbeeld *Hr-afdeling* (optioneel).
    - **Opmerkingen**: Voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
    - **Logo**: Upload een pictogram dat u aan de app wilt koppelen (optioneel). Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
8. Selecteer **OK**.
9. Selecteer **Toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. Apps uit de Microsoft Store kunnen alleen worden toegewezen aan groepen met het toewijzingstype **Beschikbaar voor ingeschreven apparaten** (gebruikers installeren de app vanuit de bedrijfsportal-app of -website).

## <a name="next-steps"></a>Volgende stappen
- [Apps aan groepen toewijzen](apps-deploy.md)
