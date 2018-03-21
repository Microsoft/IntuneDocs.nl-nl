---
title: Android Store-apps toevoegen aan Microsoft Intune
titleSuffix: 
description: Meer informatie over hoe u Android Store-apps toevoegt aan Microsoft Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 87fea551dea1f80ee071fe6b477b84729e000874
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Android Store-apps toevoegen aan Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Voordat u een app toewijst aan een apparaat of een groep gebruikers, moet u de app toevoegen aan Microsoft Intune. Met de volgende stappen kunt u een Android Store-app toevoegen aan Intune via Azure Portal.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies **Mobiele apps** in het deelvenster **Intune**.
4. In de workload **Mobiele apps** kiest u **Apps** in het gedeelte **Beheren**.
5. Kies **Toevoegen** boven de lijst met apps.
6. In het deelvenster **App toevoegen** selecteert u **Android** bij de beschikbare typen **Store-apps**.
7. Selecteer **Configureren** om de volgende app-gegevens te configureren (afhankelijk van de app die u hebt gekozen, zijn sommige waarden in dit deelvenster mogelijk automatisch ingevuld):
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze beschrijving wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **Appstore-URL**: voer voor de app die u wilt maken de URL naar de appstore in.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie** (optioneel): selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Hierdoor kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL** (optioneel): voer de URL in van een website die informatie over deze app bevat (optioneel). Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL** (optioneel): voer de URL in van een website die privacyinformatie over deze app bevat. Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar** (optioneel): voer de naam in van de app-ontwikkelaar.
    - **Eigenaar** (optioneel): voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen** (optioneel): voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Pictogram** (optioneel): upload een pictogram dat aan de app wordt gekoppeld. Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
8. Klik op **OK** wanneer u klaar bent met het opgeven van informatie over de app.
9. Klik op **Toevoegen** om de app toe te voegen.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. 

##<a name="next-steps"></a>Volgende stappen

- [Apps aan groepen toewijzen](apps-deploy.md)