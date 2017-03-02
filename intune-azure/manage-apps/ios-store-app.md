---
title: iOS Store-apps toevoegen aan Intune | Intune Azure Preview | Microsoft Docs
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over het toevoegen van iOS Store-apps aan Intune.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: 6026c942aea906e7e730152e6e92797ec5775bc3
ms.lasthandoff: 02/16/2017

---

# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS Store-apps toevoegen aan Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---search-for-the-app-in-the-store"></a>Stap 1: de app in de Store zoeken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
4. Kies **Beheren** > Apps in de workload **Mobiele apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies **Zoeken in de App Store** op de blade **App toevoegen**.
7. Geef op de blade **Apple App Store** de naam (of een gedeelte van de naam) op in het zoekvak. De Store wordt doorzocht met Intune, waarna een lijst met relevante resultaten wordt geretourneerd.
8. Kies de gewenste app in de lijst en klik op **OK**.

## <a name="step-2---configure-app-information"></a>Stap 2: de app-gegevens configureren

1. Kies **App-gegevens** op de blade **App toevoegen**.
2. Configureer de volgende gegevens op de blade **App bewerken**. Klik wanneer u klaar bent op **Toevoegen**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden op deze blade mogelijk automatisch ingevuld:
- **App-naam**: voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **App-beschrijving**: voer een beschrijving in voor de app. Deze wordt weergegeven voor gebruikers in de bedrijfsportal.
- **Uitgever**: voer de naam van de uitgever of de app in.
- **App Store URL** (URL van App Store): voer voor de app die u wilt maken de URL naar de App Store in.
- **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
- **Categorie** (optioneel). Selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Hierdoor kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
- **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
- **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
- **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
- **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
- **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).
- **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
- **Pictogram uploaden**: upload het pictogram dat aan de app wordt gekoppeld. Dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Wanneer u klaar bent, kiest u **Opslaan** op de blade **App toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](/intune-azure/manage-apps/deploy-apps) voor hulp.
