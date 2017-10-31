---
title: iOS Store-apps toevoegen aan Microsoft Intune| Microsoft Docs
titlesuffix: Azure portal
description: Meer informatie over het toevoegen van iOS Store-apps aan Intune.
keywords: Intune
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4c5d18f217659c9be59c116670fbf92a6d1b2ab4
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2017
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>iOS Store-apps toevoegen aan Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Gebruik de informatie in dit onderwerp om iOS Store-apps in Intune toe te voegen.

>[!NOTE]
>Hoewel gebruikers van iOS-apparaten sommige van de ingebouwde iOS-apps, zoals Stocks en Maps, kunnen verwijderen, kunt u Intune niet gebruiken om die apps opnieuw te implementeren. Als eindgebruikers deze apps verwijderen, moeten ze naar de appstore gaan en ze handmatig opnieuw installeren.

## <a name="before-you-start"></a>Voordat u begint

U kunt alleen apps toewijzen met deze methode als ze gratis in de App Store verkrijgbaar zijn. Als u betaalde apps wilt toewijzen met Intune, kunt u overwegen de [Volume Purchase Program-app voor iOS](vpp-apps-ios.md) te gebruiken.


## <a name="step-1---search-for-the-app-in-the-store"></a>Stap 1: de app in de Store zoeken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
4. Kies **Beheren** > Apps in de workload **Mobiele apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies **Zoeken in de App Store** op de blade **App toevoegen**.
7. Selecteer in de blade **Apple App Store** het land voor de App Store.
8. Typ de naam (of een deel daarvan) in het zoekvak. De Store wordt doorzocht met Intune, waarna een lijst met relevante resultaten wordt weergegeven.
9. Kies de gewenste app in de lijst en klik op **OK**.

## <a name="step-2---configure-app-information"></a>Stap 2: de app-gegevens configureren

1. Kies **App-gegevens** op de blade **App toevoegen**.
2. Configureer de app-gegevens op de blade **App bewerken**. Klik wanneer u klaar bent op **Toevoegen**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden op deze blade mogelijk automatisch ingevuld:
- **Naam**: typ de naam van de app die u wilt weergeven in de bedrijfsportal. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
- **Beschrijving**: typ een beschrijving voor de app die u wilt weergeven voor gebruikers in de bedrijfsportal.
- **Uitgever**: typ de naam van de uitgever van de app.
- **URL App Store**: typ de URL naar de App Store voor de app die u wilt maken.
- **Land/regio App Store**: selecteer het land voor de App Store.
- **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. De app wordt niet geïnstalleerd op een apparaat met een oudere versie van het besturingssysteem.
- **Toepasselijk apparaattype**: kies de apparaten waarop de app kan worden geïnstalleerd in de lijst.
- **Categorie** (optioneel). Selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
- **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
- **Informatie-URL**: typ de URL van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
- **Privacy-URL**: typ de URL van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
- **Ontwikkelaar**: typ de naam van de app-ontwikkelaar (optioneel). Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
- **Eigenaar**: typ de naam van de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).  Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
- **Opmerkingen**: typ de opmerkingen die u aan deze app wilt koppelen. Dit veld is alleen zichtbaar voor beheerders en niet voor eindgebruikers.
- **Logo**: upload een pictogram dat aan de app is gekoppeld. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Wanneer u klaar bent, kiest u **OK** op de blade **App toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.
