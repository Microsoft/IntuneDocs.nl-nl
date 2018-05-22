---
title: Windows Phone 8.1 Store-apps toevoegen aan Microsoft Intune
titleSuffix: ''
description: Meer informatie over hoe u Windows Phone 8.1 Store-apps toevoegt aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e8b3e34e72775061dcc3b40f60e75243972cedd2
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
---
# <a name="add-windows-phone-81-store-apps-to-microsoft-intune"></a>Windows Phone 8.1 Store-apps toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Voordat u een app toewijst aan een apparaat of een groep gebruikers, moet u de app toevoegen aan Microsoft Intune. 

## <a name="add-an-app-to-intune"></a>Een app toevoegen aan Intune
Met de volgende stappen kunt u een Windows Phone 8.1 Store-app toevoegen aan Intune via Azure Portal:

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**.  
    Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Mobiele apps** in het deelvenster **Intune**.
4. Selecteer **Apps** in het werkbelastingvenster **Mobiele apps** onder **Beheren**.
5. Selecteer **Toevoegen** in het deelvenster **Apps**.
6. Selecteer in het deelvenster **App toevoegen** een **App-type** van **Windows Phone 8.1** en kies **App-informatie**.
7. Voeg in het deelvenster **App-gegevens** de app-gegevens toe. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. Zorg ervoor dat u alleen unieke app-namen gebruikt. Als u twee dezelfde app-namen gebruikt, wordt voor gebruikers slechts één naam in de bedrijfsportal weergegeven.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever van de app in.
    - **URL App Store**: typ de URL naar de App Store voor de app die u wilt maken.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: selecteer deze instelling om het app-pakket prominent weer te geven op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld *HR-afdeling* (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
    - **Pictogram**: upload een pictogram dat aan de app wordt gekoppeld (optioneel). Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
8. Selecteer **OK**.
9. Selecteer **Toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
