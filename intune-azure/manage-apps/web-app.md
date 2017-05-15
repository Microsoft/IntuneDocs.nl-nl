---
title: Web-apps toevoegen aan Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over het toevoegen van web-apps aan Intune.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: a9748a0ad6b9bbe10e36ba133ba74edb6aa6e09a
ms.openlocfilehash: 4b6e8d72085edc3de41b7dcdb4fe5b09f5561601
ms.contentlocale: nl-nl
ms.lasthandoff: 05/05/2017

---

# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Web-apps toevoegen aan Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
4. Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies **App-gegevens** op de blade **App toevoegen**.
7. Configureer de volgende gegevens op de blade **App bewerken**. Klik wanneer u klaar bent op **Toevoegen**:
    - **App-URL**: voer de URL in van de website waarop de app wordt gehost die u wilt toewijzen.
    - **App-naam**: voer de naam van de app in zoals deze in de bedrijfsportal zal worden weergegeven.
    - **App-beschrijving**: voer een beschrijving in voor de app. Deze wordt weergegeven voor eindgebruikers in de bedrijfsportal.
    - **Uitgever**: voer de naam in van de uitgever van deze app.
    - **Categorie (optioneel)**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Hierdoor kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Een beheerde browser vereisen om deze koppeling te openen**: wanneer u aan gebruikers een koppeling naar een website of web-app toewijst, kunnen ze deze alleen in de door Intune beheerde browser openen. Deze browser moet op hun apparaat zijn geïnstalleerd.
    - **Pictogram uploaden**: upload het pictogram dat aan de app wordt gekoppeld. Dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
8. Wanneer u klaar bent, kiest u **Opslaan** op de blade **App toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](/intune-azure/manage-apps/deploy-apps) voor hulp.
