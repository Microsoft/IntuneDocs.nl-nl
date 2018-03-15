---
title: Windows Line-Of-Business-apps toevoegen aan Microsoft Intune
titlesuffix: 
description: Meer informatie over hoe u Windows Line-Of-Business-apps (LOB) toevoegt aan Microsoft Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/16/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b687b71f9d264364ff758fdd46b0739465c16865
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Windows Line-Of-Business-apps (LOB) toevoegen aan Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Een LOB-app is een app die u vanaf een app-installatiebestand toevoegt. Deze app-typen worden doorgaans intern ontwikkeld. De volgende stappen bevatten instructies waarmee u een Windows LOB-app kunt toevoegen aan Microsoft Intune.

## <a name="step-1---specify-the-software-setup-file"></a>Stap 1: de locatie van het software-installatiebestand opgeven

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** + **Intune**.
3. Kies **Apps beheren** op de blade **Intune**.
4. Kies **Beheren** > **Apps** in de workload **Mobiele apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies **Line-Of-Business-app** in de blade **App toevoegen**.

## <a name="step-2---configure-the-app-package-file"></a>Stap 2: het pakketbestand van de app configureren

1. Kies **Installatiebestand** op de blade **App toevoegen**.
2. Klik op de bestandsblade **App-pakket** op de bladerknop en selecteer een Windows-installatiebestand met de extensie **.msi**, **.appx** of **.appxbundle**.
3. Als u klaar bent, kiest u **OK**.


## <a name="step-3---configure-app-information"></a>Stap 3: de app-gegevens configureren

1. Kies **Installatiebestand** op de blade **App toevoegen**.
2. Configureer op de blade **App-gegevens** de volgende informatie (mogelijk is een deel van de waarden in deze blade automatisch ingevuld):
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving in voor de app. De beschrijving wordt voor gebruikers weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Door apps in te delen in categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over de app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over de app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Opdrachtregelargumenten**: voer eventueel opdrachtregelargumenten in die u wilt toepassen op het MSI-bestand wanneer dit wordt uitgevoerd, bijvoorbeeld **/q**.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat aan de app is gekoppeld. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Als u klaar bent, kiest u **OK**.

## <a name="step-4---finish-up"></a>Stap 4: afronden

1. Controleer op de blade **App toevoegen** of u de app-gegevens correct hebt geconfigureerd.
2. Kies **Toevoegen** om de app te uploaden naar Intune.

## <a name="step-5---update-a-line-of-business-app"></a>Stap 5: een Line-Of-Business-app bijwerken

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="configuring-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Een mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren

U kunt een bekende mobiele MSI-app die automatisch wordt bijgewerkt configureren om de versiecontrole te negeren. Sommige op MSI-installer gebaseerde apps worden automatisch bijgewerkt door de app-ontwikkelaar. Voor deze automatisch bijgewerkte MSI-apps kunt u de instelling **App-versie negeren** in de blade **App-informatie** configureren. Wanneer deze instelling op **Ja** staat, dwingt Microsoft Intune de app-versie die is geïnstalleerd op de Windows-client niet af. Met deze functie kunt u voorkomen dat er een racevoorwaarde optreedt. Dit type racevoorwaarde kan bijvoorbeeld optreden wanneer de app die automatisch wordt bijgewerkt door de app-ontwikkelaar ook wordt bijgewerkt door Intune. Er kan door beide worden geprobeerd om een versie van de app op een Windows-client af te dwingen, waardoor een conflict kan ontstaan.

## <a name="next-steps"></a>Volgende stappen

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md) voor meer informatie.

Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](introduction-device-app-lifecycles.md) voor meer informatie