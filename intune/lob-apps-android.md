---
title: Een Android Line-Of-Business-app toevoegen aan Microsoft Intune
titlesuffix: ''
description: Informatie over het toevoegen van een Android Line-Of-Business-app aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 22470356c921eea17e4d2b3d57f796fe51568ee1
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34224480"
---
# <a name="add-an-android-line-of-business-app-to-microsoft-intune"></a>Een Android Line-Of-Business-app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Een LOB-app is een app die u vanaf een app-installatiebestand aan Intune toevoegt. Dit type app wordt doorgaans intern geschreven. De LOB-app wordt door Intune op het apparaat van de gebruiker geïnstalleerd. 

> [!Note]
> Zie voor meer informatie over LOB-apps uit de Google Play for Work-store [Werken met een Line-Of-Business-app vanuit de Google Play for Work-store](apps-add-android-for-work.md?#working-with-a-line-of-business-app-from-the-google-play-for-work-store). 

## <a name="step-1-specify-the-software-setup-file"></a>Stap 1: de locatie van het software-installatiebestand opgeven

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Selecteer **Mobiele apps** in het deelvenster **Intune**.
4. Selecteer **Beheren** > **Apps** in de workload **Mobiele apps**.
5. Selecteer **Toevoegen** boven de lijst met apps.
6. Selecteer in het deelvenster **App toevoegen** de optie **Line-Of-Business-app**.

## <a name="step-2-configure-the-app-package-file"></a>Stap 2: het pakketbestand van de app configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakketbestand**.
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Android-installatiebestand met de extensie **.apk**.
3. Klik op **OK** wanneer u klaar bent.


## <a name="step-3-configure-app-information"></a>Stap 3: de app-gegevens configureren

1. Selecteer **App-gegevens** in het deelvenster **App toevoegen**.
2. Voeg de details voor uw app toe in het deelvenster **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld.
    - **Naam**: voer de naam van de app in zoals deze in de bedrijfsportal wordt weergegeven. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: voer een beschrijving van de app in. De beschrijving wordt weergegeven in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever van de app in.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **App-versie negeren**: stel deze optie in op **Ja** als de app-ontwikkelaar de app automatisch bijwerkt.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Met categorieën kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app (optioneel). Bijvoorbeeld **HR-afdeling**.
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat aan de app is gekoppeld. Het pictogram wordt samen met de app weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Klik op **OK** wanneer u klaar bent.

## <a name="step-4-finish-up"></a>Stap 4: afronden

1. Controleer in het deelvenster **App toevoegen** of de gegevens van uw app juist zijn.
2. Selecteer **Toevoegen** om de app te uploaden naar Intune.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. In de lijst kunt u de app toewijzen aan groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

## <a name="step-5-update-a-line-of-business-app"></a>Stap 5: een Line-Of-Business-app bijwerken

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note]
> De Intune-service kan alleen een nieuw APK-bestand op het apparaat implementeren als u de tekenreeks `android:versionCode` in het bestand AndroidManifest.xml in uw APK-pakket verhoogt.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md).

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](introduction-device-app-lifecycles.md).
