---
title: Web-apps toevoegen aan Intune
titleSuffix: Azure portal
description: Meer informatie over het toevoegen van web-apps aan Intune.
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cfa70879a460826d22eb6fab2e0d08603e567d6e
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Web-apps toevoegen aan Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Voordat u een app kunt beheren en aan uw gebruikers kunt toewijzen, voegt u de app toe aan Intune. Intune biedt ondersteuning voor diverse typen apps, waaronder web-apps.

> [!Note]
> Web-apps worden niet ondersteund op Android for Work-apparaten.

Voer de volgende stappen uit om een app toe te voegen aan Intune als een snelkoppeling naar een app op internet:

1. Meld u aan bij Azure-portal.
2. Gebruik **Meer bronnen** om **Intune** te zoeken en te selecteren.
3. Op de blade **Microsoft Intune** selecteert u **Mobiele apps**.
4. Op de blade **Mobiele apps** selecteert u **Apps**.
5. Selecteer **Toevoegen** boven de lijst met apps. De blade **App toevoegen** wordt weergegeven.
6. Op de blade **App toevoegen** selecteert u het type **Web-app** in de vervolgkeuzelijst **App-type**.
7. Selecteer de optie **Configureren** om de blade **App-gegevens** weer te geven.
8. Voeg op de blade **App-gegevens** de volgende gegevens toe:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal moet worden weergegeven.
    - **Beschrijving**: voer een beschrijving in voor de app. Deze wordt weergegeven voor eindgebruikers in de bedrijfsportal.
    - **Uitgever**: voer de naam in van de uitgever van deze app.
    - **App-URL**: voer de URL in van de website waarop de app wordt gehost die u wilt toewijzen.
    - **Categorie** (optioneel): selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met deze selectie kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Een beheerde browser vereisen om deze koppeling te openen**: wanneer u aan gebruikers een koppeling naar een website of web-app toewijst, kunnen ze deze in de door Intune beheerde browser openen. Deze browser moet op hun apparaat zijn geïnstalleerd.
    - **Logo**: upload een logo dat aan de app is gekoppeld. Dit is het logo dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
9. Wanneer u klaar bent, selecteert u **OK** op de blade **Gegevens toevoegen**.
10. Selecteer vervolgens **Toevoegen** op de blade **App toevoegen**.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.