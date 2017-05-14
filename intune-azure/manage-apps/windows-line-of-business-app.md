---
title: Windows Line-Of-Business-apps toevoegen aan Intune | Microsoft Docs
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over het toevoegen van Windows Line-Of-Business-apps aan Intune.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 3758df744311392528be01c826527c2a9d879975
ms.openlocfilehash: deafb0a37609b957a0cd4fa0880eeb5ff40314bc
ms.contentlocale: nl-nl
ms.lasthandoff: 05/10/2017

---

# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Windows Line-Of-Business-apps (LOB) toevoegen aan Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Stap 1: de locatie van het software-installatiebestand opgeven

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
4. Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies **Line-Of-Business-app** in de blade **App toevoegen**.

## <a name="step-2---configure-the-app-package-file"></a>Stap 2: het pakketbestand van de app configureren

1. Kies **Installatiebestand** op de blade **App toevoegen**.
2. Klik op de blade **Installatiebestand** op de bladerknop en selecteer een Windows-installatiebestand met de extensie **.msi** (andere typen installatiebestanden worden niet ondersteund).
3. Als u klaar bent, kiest u **OK**.


## <a name="step-3---configure-app-information"></a>Stap 3: de app-gegevens configureren

1. Kies **Installatiebestand** op de blade **App toevoegen**.
2. Configureer de volgende gegevens op de blade **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden op deze blade mogelijk automatisch ingevuld:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Hierdoor kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). Deze URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Opdrachtregelargumenten**: voer eventueel opdrachtregelargumenten in die u wilt toepassen op het MSI-bestand wanneer dit wordt uitgevoerd, bijvoorbeeld **/q**.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat aan de app wordt gekoppeld. Dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Als u klaar bent, kiest u **OK**.

## <a name="step-4---finish-up"></a>Stap 4: afronden

1. Controleer op de blade **App toevoegen** of de gegevens die u hebt geconfigureerd correct zijn.
2. Kies **Toevoegen** om de app te uploaden naar Intune.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](deploy-apps.md) voor hulp.

