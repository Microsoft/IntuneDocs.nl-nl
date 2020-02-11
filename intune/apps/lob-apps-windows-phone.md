---
title: Een Windows Phone Line-Of-Business-app toevoegen aan Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over het toevoegen van Windows Phone Line-Of-Business-apps (LOB) met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/23/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 328bafc2a55191c203263911ceaac9b520eb07f5
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755150"
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Een Windows Phone Line-Of-Business-app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gebruik de informatie in dit artikel om een Windows Phone LOB-app (Line-Of-Business) aan Microsoft Intune toe te voegen. Een LOB-app is een app die u vanaf een app-installatiebestand aan Intune toevoegt. Dit type app wordt doorgaans intern geschreven. De LOB-app wordt door Intune op het apparaat van de gebruiker geïnstalleerd. 

## <a name="select-the-app-type"></a>Het app-type selecteren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder het app-type **Overige** de optie **Line-Of-Business-app**.
4. Klik op **Selecteren**. De stappen **App toevoegen** worden weergegeven.

## <a name="step-1---app-information"></a>Stap 1: App-gegevens

### <a name="select-the-app-package-file"></a>Het app-pakketbestand selecteren

1. Klik in het deelvenster **App toevoegen** op **App-pakketbestand selecteren**. 
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Windows Phone-installatiebestand met de extensie **.axp**.
   De details van de app worden weergegeven.
3. Wanneer u klaar bent, selecteert u **OK** in het deelvenster **App-pakketbestand** om de app toe te voegen.

### <a name="set-app-information"></a>App-gegevens instellen

1. Voeg de details voor uw app toe op de pagina **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving van de app in. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Geef de app prominent weer op de hoofdpagina van de bedrijfsportal wanneer gebruikers door apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat u aan de app wilt koppelen. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
2. Klik op **Volgende** om de pagina **Bereiktags** weer te geven.

## <a name="step-2---select-scope-tags-optional"></a>Stap 2: Bereiktags selecteren (optioneel)
U kunt bereiktags gebruiken om te bepalen wie er informatie over client-apps mag bekijken in Intune. Zie [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md) (Op rollen gebaseerd toegangsbeheer en bereiktags gebruiken voor gedistribueerde IT) voor uitgebreide informatie over bereiktags.

1. Klik op **Bereiktags selecteren** om desgewenst bereiktags toe te voegen voor de app. 
2. Klik op **Volgende** om de pagina **Toewijzingen** weer te geven.

## <a name="step-3---assignments"></a>Stap 3: Toewijzingen

1. Selecteer de groepstoewijzingen **Vereist**, **Beschikbaar voor ingeschreven apparaten** of **Verwijderen** voor de app. Zie [Groepen toevoegen om gebruikers en apparaten in te delen](~/fundamentals/groups-add.md) en [Apps toewijzen aan groepen met Microsoft Intune](apps-deploy.md) voor meer informatie.
2. Klik op **Volgende** om naar de pagina **Controleren en maken** weer te geven. 

## <a name="step-4---review--create"></a>Stap 4: beoordelen en maken

1. Controleer de waarden en instellingen die u hebt ingevoerd voor de app.
2. Klik als u klaar bent op **Maken** om de app toe te voegen aan Intune.

    De blade **Overzicht** voor de Line-Of-Business-app wordt weergegeven.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. In de lijst, kunt u de apps toewijzen aan groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md).

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](../fundamentals/device-lifecycle.md).
