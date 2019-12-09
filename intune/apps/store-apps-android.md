---
title: Android Store-apps aan Microsoft Intune toevoegen
titleSuffix: ''
description: Informatie over hoe u Android Store-apps uit de Google Play-store toevoegt aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
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
ms.openlocfilehash: ec800064d109cca42878c79ade6777de9b782015
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563508"
---
# <a name="add-android-store-apps-to-microsoft-intune"></a>Android Store-apps aan Microsoft Intune toevoegen

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Voordat u een app toewijst aan een apparaat of een groep gebruikers, moet u de app toevoegen aan Microsoft Intune. 

## <a name="add-an-app"></a>Een app toevoegen

Met de volgende stappen kunt u een Android Store-app toevoegen aan Intune via Azure Portal:

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. In het deelvenster **App toevoegen** selecteert u **Android** bij de beschikbare typen **Store-apps**.
4. Als u de app-gegevens wilt configureren, selecteert u **Configureren** en geeft u de volgende informatie op. Voor Android-apps gaat u naar de [Google Play Store](https://play.google.com/store) en zoekt u de app die u wilt implementeren. Selecteer de app en noteer de app-gegevens. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden mogelijk automatisch ingevuld.
    - **Naam**: Voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven. Zorg ervoor dat u alleen unieke app-namen gebruikt. Als u twee dezelfde app-namen gebruikt, wordt voor gebruikers slechts één naam in de bedrijfsportal weergegeven.
    - **Beschrijving**: Voer een beschrijving in voor de app. Deze beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **URL App Store**: Voer de app store-URL in van de app die u wilt maken.
    - **Minimumversie van het besturingssysteem**: Selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie**: Selecteer een of meer ingebouwde app-categorieën of een categorie die u hebt gemaakt (optioneel). Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Selecteer deze optie om het app-pakket prominent weer te geven op de hoofdpagina van de bedrijfsportal wanneer gebruikers naar apps bladeren. Is van toepassing op apps die zijn geïmplementeerd met de intentie Beschikbaar.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: Voer een naam in voor de eigenaar van deze app, bijvoorbeeld *Hr-afdeling* (optioneel).
    - **Opmerkingen**: Voer de opmerkingen in die u aan deze app wilt koppelen (optioneel).
    - **Logo**: Upload een pictogram dat u aan de app wilt koppelen (optioneel). Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
5. Selecteer **OK**.
6. Selecteer **Toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u selecteert. 

## <a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)
