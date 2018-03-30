---
title: Windows Phone Line-Of-Business-apps toevoegen aan Microsoft Intune
titlesuffix: ''
description: In dit onderwerp vindt u meer informatie over het toevoegen van Windows Phone-Line-Of-Business-apps (LOB) aan Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4053c2f932f6101397deb6bf0c3a142fa713aec4
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a>Windows Phone Line-Of-Business-apps (LOB) toevoegen aan Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik de informatie in dit artikel om Windows Phone Line-Of-Business-apps aan Microsoft Intune toe te voegen. Een LOB-app is een app die u vanaf een app-installatiebestand aan Intune toevoegt. Deze app-typen worden doorgaans intern ontwikkeld. De LOB-app wordt door Intune op het apparaat van de gebruiker geïnstalleerd. 

## <a name="step-1---specify-the-software-setup-file"></a>Stap 1: de locatie van het software-installatiebestand opgeven

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies **Mobiele apps** in het deelvenster **Intune**.
4. Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies in het deelvenster **App toevoegen** de optie **Line-Of-Business-app**.

## <a name="step-2---configure-the-app-package-file"></a>Stap 2: het pakketbestand van de app configureren

1. Kies in het deelvenster **App toevoegen** het bestand **App-pakket**.
2. Klik in het bestandsdeelvester **App-pakket** op de bladerknop en selecteer een Windows Phone-installatiebestand met de extensie **.xap**.
3. Als u klaar bent, kiest u **OK**.


## <a name="step-3---configure-app-information"></a>Stap 3: de app-gegevens configureren

1. Kies in het deelvenster **App toevoegen** het bestand **App-pakket**.
2. Configureer de app-gegevens in het deelvenster **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld:
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving in voor de app. De beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **App-versie negeren**: stel deze optie in op **Ja** als de app automatisch wordt bijgewerkt door de app-ontwikkelaar.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Door gebruik te maken van categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat aan de app is gekoppeld. Dit pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Als u klaar bent, kiest u **OK**.

## <a name="step-4---finish-up"></a>Stap 4: afronden

1. Controleer in het deelvenster **App toevoegen** of de gegevens die u hebt geconfigureerd correct zijn.
2. Kies **Toevoegen** om de app te uploaden naar Intune.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md) voor meer informatie.

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](introduction-device-app-lifecycles.md) voor meer informatie
