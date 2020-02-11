---
title: MacOS-Line-Of-Business-apps toevoegen in Microsoft Intune
titleSuffix: ''
description: Hier vindt u meer informatie over het toevoegen van LOB-apps (Line-Of-Business) voor macOS aan Microsoft Intune.
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
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7aa6af751e5ab3e1e3cdff6b1d2e3d6693f65df
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2020
ms.locfileid: "76755167"
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
    > [!IMPORTANT]
    > Zorg ervoor dat het argument `<source_file>` geen spaties bevat voordat u de `IntuneAppUtil`-opdrachten uitvoert.

    - `IntuneAppUtil -h`<br>
    Met deze opdracht worden de gebruiksgegevens voor het hulpprogramma weergegeven.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    Met deze opdracht wordt het *.pkg*-LOB-app-bestand verpakt in een *.itunemac*-bestand.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    Met deze opdracht worden de gedetecteerde parameters en versie voor het gemaakte *.itunemac*-bestand uitgepakt.

## <a name="select-the-app-type"></a>Het app-type selecteren

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apps** > **Alle apps** > **Toevoegen**.
3. Selecteer in het deelvenster **Een app-type selecteren** onder het app-type **Overige** de optie **Line-Of-Business-app**.
4. Klik op **Selecteren**. De stappen **App toevoegen** worden weergegeven.

## <a name="step-1---app-information"></a>Stap 1: App-gegevens

### <a name="select-the-app-package-file"></a>Het app-pakketbestand selecteren

1. Klik in het deelvenster **App toevoegen** op **App-pakketbestand selecteren**. 
2. Selecteer in het deelvenster **App-pakketbestand** de bladerknop. Selecteer vervolgens een macOS-installatiebestand met de extensie *.intunemac*.
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

De app die u hebt gemaakt, wordt weergegeven in de lijst met apps waar u de app kunt toewijzen aan de groepen die u kiest. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

> [!NOTE]
> Als het *.pkg*-bestand meerdere apps of app-installatieprogramma's bevat, wordt met Microsoft Intune alleen gerapporteerd dat de *app* is geïnstalleerd wanneer alle geïnstalleerde apps op het apparaat zijn gedetecteerd.

## <a name="update-a-line-of-business-app"></a>een Line-Of-Business-app bijwerken

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> De Intune-service kan alleen een nieuw *.pkg*-bestand op het apparaat implementeren als u de tekenreeks `version` en `CFBundleVersion` in het *packageinfo*-bestand verhoogt in uw *.pkg*-pakket.

## <a name="next-steps"></a>Volgende stappen

- De app die u hebt gemaakt, wordt weergegeven in de lijst met apps. U kunt deze nu toewijzen aan de gewenste groepen. Zie [Apps aan groepen toewijzen](apps-deploy.md) voor hulp.

- Meer informatie over de manieren waarop u de eigenschappen en de toewijzing van uw app kunt controleren. Zie [App-gegevens en -toewijzingen controleren](apps-monitor.md) voor meer informatie.

- Meer informatie over de context van uw app in Intune. Zie [Overzicht van de levenscycli van apparaten en apps](../fundamentals/device-lifecycle.md) voor meer informatie
