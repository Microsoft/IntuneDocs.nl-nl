---
title: Android Store-apps aan Microsoft Intune toevoegen
titleSuffix: ''
description: Informatie over hoe u Android Store-apps uit de Google Play-store toevoegt aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/22/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e6b9f6a9303e53652959639193633cdcc00dfb99
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755082"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Android Store-apps aan Microsoft Intune toevoegen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Voordat u een app toewijst aan een apparaat of een groep gebruikers, moet u de app toevoegen aan Microsoft Intune. 

## <a name="add-an-app"></a>Een app toevoegen

Met de volgende stappen kunt u een Android Store-app toevoegen aan Intune via Azure Portal:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder de beschikbare typen **Store-app** de optie **Android Store-app**.
4. Klik op **Selecteren**.<br>
   De stappen **App toevoegen** worden weergegeven.
5. Als u de **App-gegevens** wilt configureren voor de Android-app, gaat u naar de [Google Play store](https://play.google.com/store) en zoekt u naar de app die u wilt implementeren. Geef de app-pagina weer en noteer de details van de app. 
6. Voeg in het deelvenster **App-gegevens** de app-gegevens toe:
    - **Naam**: Voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. Zorg ervoor dat u alleen unieke app-namen gebruikt. Als u twee dezelfde app-namen gebruikt, wordt voor gebruikers slechts één naam in de bedrijfsportal weergegeven.
    - **Beschrijving**: Voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **URL App Store**: Voer de app store-URL in van de app die u wilt maken. Gebruik de URL van de app-pagina wanneer de details van de app worden weergegeven in de Store. 
    - **Minimumversie van het besturingssysteem**: Selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie**: Selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om het app-pakket prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers naar apps bladeren. Is van toepassing op apps die zijn geïmplementeerd met de intentie Beschikbaar.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: Voer een naam in voor de eigenaar van deze app, bijvoorbeeld *Hr-afdeling* (optioneel).
    - **Opmerkingen**: Voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
    - **Logo**: Upload een pictogram dat u aan de app wilt koppelen (optioneel). Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
7. Klik op **Volgende** om de pagina **Bereiktags** weer te geven.
8. Klik op **Bereiktags selecteren** om desgewenst bereiktags toe te voegen voor de app. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) en bereiktags gebruiken voor gedistribueerde IT](~/fundamentals/scope-tags.md) voor meer informatie.
9. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.
10. Selecteer de groepstoewijzingen voor de app. Zie [Groepen toevoegen om gebruikers en apparaten te organiseren](~/fundamentals/groups-add.md) voor meer informatie. 
11. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven. Controleer de waarden en instellingen die u hebt ingevoerd voor de app.
12. Klik als u klaar bent op **Maken** om de app toe te voegen aan Intune.

De blade **Overzicht** van de app die u hebt gemaakt, wordt weergegeven.

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
