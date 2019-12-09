---
title: Een Windows Phone Line-Of-Business-app toevoegen aan Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over het toevoegen van Windows Phone Line-Of-Business-apps (LOB) met Microsoft Intune.
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
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: dd8025c18ef10580eb16883727bf08a316989d2e
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563530"
---
# <a name="add-a-windows-phone-line-of-business-app-to-microsoft-intune"></a>Een Windows Phone Line-Of-Business-app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gebruik de informatie in dit artikel om een Windows Phone LOB-app (Line-Of-Business) aan Microsoft Intune toe te voegen. Een LOB-app is een app die u vanaf een app-installatiebestand aan Intune toevoegt. Dit type app wordt doorgaans intern geschreven. De LOB-app wordt door Intune op het apparaat van de gebruiker geïnstalleerd. 

## <a name="step-1-specify-the-software-setup-file"></a>Stap 1: locatie van het software-installatiebestand opgeven

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **App toevoegen** de optie **Line-Of-Business-app** als het **app-type**.

## <a name="step-2-configure-the-app-package-file"></a>Stap 2: app-pakketbestand configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakketbestand**.
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Windows Phone-installatiebestand met de extensie **.axp**.
3. Klik op **OK** wanneer u klaar bent.


## <a name="step-3-configure-app-information"></a>Stap 3: App-gegevens configureren

1. Selecteer **App-gegevens** in het deelvenster **App toevoegen**.
2. Configureer de app-gegevens in het deelvenster **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: Voer een beschrijving in voor de app. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: Voer de naam van de uitgever van de app in.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: Geef de app prominent weer op de hoofdpagina van de bedrijfsportal wanneer gebruikers door apps bladeren.
    - **Informatie-URL**: Voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: (optioneel) Voer de URL in van een website die privacyinformatie over deze app bevat. De URL wordt weergegeven in de bedrijfsportal.
    - **Ontwikkelaar**: Voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat u aan de app wilt koppelen. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Klik op **OK** wanneer u klaar bent.

## <a name="step-4-finish-up"></a>Stap 4: Voltooien

1. Controleer in het deelvenster **App toevoegen** of de gegevens die u hebt geconfigureerd correct zijn.
2. Selecteer **Toevoegen** om de app te uploaden naar Intune.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md).

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](../fundamentals/device-lifecycle.md).
