---
title: MacOS-Line-Of-Business-apps toevoegen in Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over het toevoegen van LOB-apps (Line-Of-Business) voor macOS aan Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aeae231e07ceeee6a54f8f60ec5d53cc96d55be0
ms.sourcegitcommit: 737ad6c675deedfc6009f792023ff95981b06582
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/15/2019
ms.locfileid: "74117878"
---
# <a name="how-to-add-macos-line-of-business-lob-apps-to-microsoft-intune"></a>LOB-apps (Line-Of-Business) voor macOS toevoegen in Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Gebruik de informatie in dit artikel om macOS-Line-Of-Business-apps toe te voegen in Microsoft Intune. U moet een extern hulpprogramma downloaden om uw *.pkg*-bestanden vooraf te verwerken voordat u het LOB-bestand kunt uploaden in Microsoft Intune. Het vooraf verwerken van uw *.pkg*-bestanden moet plaatsvinden op een macOS-apparaat.

> [!NOTE]
> Vanaf de release van macOS Catalina 10.15 moet u voordat u uw apps aan Intune toevoegt controleren of uw macOS LOB-apps gelegaliseerd zijn. Als de ontwikkelaars van uw LOB-apps hun apps niet hebben gelegaliseerd, kunnen de apps niet worden uitgevoerd op de macOS-apparaten van uw gebruikers. Voor meer informatie over hoe u kunt controleren of een app gelegaliseerd is, gaat u naar [Uw macOS-apps legaliseren ter voorbereiding op macOS Catalina](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Notarizing-your-macOS-apps-to-prepare-for-macOS/ba-p/808579).

> [!NOTE]
> Hoewel gebruikers van macOS-apparaten sommige ingebouwde macOS-apps, zoals Stocks en Maps, kunnen verwijderen, kunt u Intune niet gebruiken om deze apps opnieuw te implementeren. Als eindgebruikers deze apps verwijderen, moeten ze naar de appstore gaan en ze handmatig opnieuw installeren.

## <a name="before-your-start"></a>Voordat u begint

U moet een extern hulpprogramma downloaden, het gedownloade hulpprogramma markeren als uitvoerbaar, en uw *.pkg*-bestanden vooraf verwerken met het hulpprogramma, voordat u het LOB-bestand kunt uploaden in Microsoft Intune. Het vooraf verwerken van uw *.pkg*-bestanden moet plaatsvinden op een macOS-apparaat. Gebruik de Intune App Wrapping Tool voor Mac om de Mac-apps in te schakelen om te worden beheerd in Microsoft Intune.

> [!IMPORTANT]
> Het *.pkg*-bestand moet zijn ondertekend met behulp van het certificaat ‘Installatieprogramma voor ontwikkelaars-id’, verkregen via een Apple-ontwikkelaarsaccount. Alleen *.pkg*-bestanden kunnen worden gebruikt om LOB-apps voor macOS te uploaden in Microsoft Intune. Het converteren van andere indelingen, zoals *.dmg* naar *.pkg* wordt niet ondersteund.
>

1. Download de [Intune App Wrapping Tool voor Mac](https://github.com/msintuneappsdk/intune-app-wrapping-tool-mac).

    > [!NOTE]
    > De  **Intune App Wrapping Tool voor Mac** moet worden uitgevoerd op een macOS-computer. 

2. Markeer het gedownloade hulpprogramma als een uitvoerbaar bestand:
   - Start de terminal-app.
   - Wijzig de directory in de locatie waar `IntuneAppUtil` zich bevindt.
   - Voer de volgende opdracht uit om het hulpprogramma uitvoerbaar te maken:<br> 
       `chmod +x IntuneAppUtil`

3. Gebruik de opdracht `IntuneAppUtil` in de **Intune App Wrapping Tool voor Mac** om het *.pkg*-LOB-app-bestand te verpakken vanuit een *.intunemac*-bestand.<br>

    Voorbeeldopdrachten om te gebruiken voor de Microsoft Intune App Wrapping Tool voor macOS:
    
    - `IntuneAppUtil -h`<br>
    Met deze opdracht worden de gebruiksgegevens voor het hulpprogramma weergegeven.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    Met deze opdracht wordt het *.pkg*-LOB-app-bestand verpakt in een *.itunemac*-bestand.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    Met deze opdracht worden de gedetecteerde parameters en versie voor het gemaakte *.itunemac*-bestand uitgepakt.

## <a name="step-1---specify-the-software-setup-file"></a>Stap 1: de locatie van het software-installatiebestand opgeven

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Client-apps**.
4. Kies **Beheren** > **Apps** in de workload **Client-apps**.
5. Kies **Toevoegen** boven de lijst met apps.
6. Kies **Line-Of-Business-app** in het deelvenster **App toevoegen**.

## <a name="step-2---configure-the-app-package-file"></a>Stap 2: het pakketbestand van de app configureren

1. Kies **App-pakketbestand** in het deelvenster **App toevoegen**.
2. Klik in het deelvenster **App-pakketbestand** op de knop Bladeren en selecteer een macOS-installatiebestand met de extensie *.intunemac*.
3. Als u klaar bent, kiest u **OK**.


## <a name="step-3---configure-app-information"></a>Stap 3: de app-gegevens configureren

1. Kies **App-informatie** in het deelvenster **App toevoegen**.
2. Voeg de details voor uw app toe in het deelvenster **App-gegevens**. Afhankelijk van de app die u hebt gekozen, worden bepaalde waarden in het deelvenster mogelijk automatisch ingevuld:
    - **Naam**: geef de naam van de app op die u wilt weergeven in de bedrijfsportal. Zorg ervoor dat alle app-namen die u gebruikt, uniek zijn. Als dezelfde app-naam twee keer voorkomt, wordt slechts één van de apps weergegeven voor gebruikers in de bedrijfsportal.
    - **Beschrijving**: typ een beschrijving voor de app die u wilt weergeven voor gebruikers in de bedrijfsportal.
    - **Uitgever**: voer de naam van de uitgever of de app in.
    - **Minimumversie van het besturingssysteem**: selecteer in de lijst de minimumversie van het besturingssysteem waarin de app kan worden geïnstalleerd. Als u de app toewijst aan een apparaat met een lager besturingssysteem, wordt de app niet geïnstalleerd.
    - **Categorie**: selecteer een of meer van de ingebouwde app-categorieën of selecteer een categorie die u hebt gemaakt. Hiermee kunnen gebruikers de app gemakkelijker vinden wanneer ze door de bedrijfsportal bladeren.
    - **Deze weergeven als aanbevolen app in de bedrijfsportal**: hiermee wordt de app duidelijk zichtbaar op de startpagina van de bedrijfsportal wanneer gebruikers naar apps zoeken.
    - **Informatie-URL**: voer de URL in van een website die informatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Privacy-URL**: voer de URL in van een website die privacyinformatie over deze app bevat (optioneel). De URL wordt weergegeven voor gebruikers in de bedrijfsportal.
    - **Ontwikkelaar**: voer de naam in van de app-ontwikkelaar (optioneel).
    - **Eigenaar**: voer een naam in voor de eigenaar van deze app, bijvoorbeeld **HR-afdeling** (optioneel).
    - **Opmerkingen**: voer de opmerkingen in die u aan deze app wilt koppelen.
    - **Logo**: upload een pictogram dat aan de app is gekoppeld. Dit is het pictogram dat samen met de app wordt weergegeven wanneer gebruikers door de bedrijfsportal bladeren.
3. Als u klaar bent, kiest u **OK**.

## <a name="step-4---finish-up"></a>Stap 4: afronden

1. Controleer in het deelvenster **App toevoegen** of de gegevens voor uw app juist zijn.
2. Kies **Toevoegen** om de app te uploaden naar Intune.

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

> [!NOTE]
> Als het *.pkg*-bestand meerdere apps of app-installatieprogramma's bevat, wordt met Microsoft Intune alleen gerapporteerd dat de *app* is geïnstalleerd wanneer alle geïnstalleerde apps op het apparaat zijn gedetecteerd.

## <a name="step-5---update-a-line-of-business-app"></a>Stap 5: een Line-Of-Business-app bijwerken

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> De Intune-service kan alleen een nieuw *.pkg*-bestand op het apparaat implementeren als u de tekenreeks `version` en `CFBundleVersion` in het *packageinfo*-bestand verhoogt in uw *.pkg*-pakket.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md) voor meer informatie.

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](../fundamentals/device-lifecycle.md) voor meer informatie
