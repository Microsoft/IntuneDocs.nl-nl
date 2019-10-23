---
title: Een Android Line-Of-Business-app toevoegen aan Microsoft Intune
description: Hier vindt u meer informatie over het toevoegen van een LOB-app (Line-Of-Business) voor Android aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a4c1f3d8b6b7edbf51ca2aaa681909e6c220de3c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507227"
---
# <a name="add-an-android-line-of-business-app-to-microsoft-intune"></a>Een Android Line-Of-Business-app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Een LOB-app is een app die u vanaf een app-installatiebestand aan Intune toevoegt. Dit type app wordt doorgaans intern geschreven. De LOB-app wordt door Intune op het apparaat van de gebruiker geïnstalleerd. 

> [!Note]
> Zie [Privé-LOB-apps in de beheerde Google Play Store publiceren met de Google-console voor ontwikkelaars](apps-add-android-for-work.md?#managed-google-play-private-lob-app-publishing-using-the-google-developer-console) voor meer informatie over LOB-apps en de Google Play-console voor ontwikkelaars. 

> [!Note]
> Zie [Beheerde Google Play-apps toevoegen aan Android Enterprise-apparaten met Intune](apps-add-android-for-work.md) voor Android for Work-apparaten. 

## <a name="step-1-specify-the-software-setup-file"></a>Stap 1: locatie van het software-installatiebestand opgeven

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecteer in het deelvenster **Intune** de optie **Client-apps**.
3. Selecteer in de workload **Client-apps** de optie **Beheren** > **Apps**.
4. Selecteer **Toevoegen** boven de lijst met apps.
5. Selecteer in het deelvenster **App toevoegen** de optie **Line-Of-Business-app**.

## <a name="step-2-configure-the-app-package-file"></a>Stap 2: app-pakketbestand configureren

1. Selecteer in het deelvenster **App toevoegen** de optie **App-pakketbestand**.
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een Android-installatiebestand met de extensie **.apk**.
3. Klik op **OK** wanneer u klaar bent.

## <a name="step-3-configure-app-information"></a>Stap 3: App-gegevens configureren

1. Selecteer **App-gegevens** in het deelvenster **App toevoegen**.
2. Voeg de details voor uw app toe in het deelvenster **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld.
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
3. Klik op **OK** wanneer u klaar bent.

## <a name="step-4-finish-up"></a>Stap 4: Voltooien

1. Controleer in het deelvenster **App toevoegen** of de gegevens van uw app juist zijn.
2. Selecteer **Toevoegen** om de app te uploaden naar Intune.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. In de lijst kunt u de app toewijzen aan groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

## <a name="step-5-update-a-line-of-business-app"></a>Stap 5: een Line-Of-Business-app bijwerken

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

Als **Apps van externe bronnen controleren** is ingeschakeld op het Android-apparaat, wordt de gebruiker gevraagd om de update te installeren. Anders wordt de update automatisch geïnstalleerd.

> [!Note]
> De Intune-service kan alleen een nieuw APK-bestand op het apparaat implementeren als u de tekenreeks `android:versionCode` in het bestand AndroidManifest.xml in uw APK-pakket verhoogt.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md).

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](../fundamentals/device-lifecycle.md).
