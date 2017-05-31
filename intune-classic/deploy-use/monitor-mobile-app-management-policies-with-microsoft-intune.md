---
title: MAM-beleid bewaken met Microsoft Intune | Microsoft Docs
description: U kunt bekijken hoeveel gebruikers het beleid hebben en hier op inzoomen om meer inzicht te verkrijgen.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: d80632aceaa675f08eb4b23ce59e3bcabb72b4d0
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="monitor-app-protection-policies-with-microsoft-intune"></a>App-beveiligingsbeleid bewaken met Microsoft Intune
U kunt de nalevingsstatus van het app-beveiligingsbeleid bewaken dat u hebt toegepast op gebruikers. U vindt er informatie over de gebruikers waarop het app-beveiligingsbeleid van toepassing is, de nalevingsstatus en mogelijke problemen die uw gebruikers ervaren.

Er zijn drie verschillende plaatsen waar u de nalevingsstatus kunt bewaken:

-   Samenvattingsweergave

-   Detailweergave

-   Rapportageweergave

## <a name="summary-view"></a>Samenvattingsweergave

Volg de drie onderstaande stappen om de samenvattingsweergave te openen:

1. Ga naar [Azure Portal](https://portal.azure.com) en voer uw referenties in.
2. Kies **Meer services** en typ **Intune** in het filtertekstvak.
3. Kies **Intune-app-beveiliging**.

Op de blade **Intune Mobile Application Management** ziet u een samenvatting van de nalevingsstatus:

![De tegel Samenvatting op het tabblad Intune Mobile Application Management](../media/mam-azure-portal-user-status-summary.png)

-   **Gebruikers:** het totale aantal gebruikers in uw bedrijf dat gebruikmaakt van de apps die zijn gekoppeld aan het beleid.

-   **BEHEERD DOOR BELEID**: het aantal gebruikers dat ten minste een van de apps in de werkcontext heeft gebruikt.

-   **GEEN BELEID:** het aantal gebruikers dat gebruikmaakt van de apps die zijn gekoppeld aan het beleid, maar op wie het beleid niet is gericht. U kunt overwegen deze gebruikers toe te voegen aan het beleid.

- **Gemarkeerde gebruikers:** het aantal gebruikers dat problemen ondervindt. Momenteel worden onder **Gemarkeerde gebruikers** alleen gebruikers met gekraakte apparaten gerapporteerd.


## <a name="detailed-view"></a>Detailweergave
U kunt de gedetailleerde weergave van de samenvatting openen door de tegel **Gebruikersstatus** (afhankelijk van het besturingssysteem van het apparaat) en de tegel **Gemarkeerde gebruikers** te kiezen.

### <a name="user-status"></a>Gebruikersstatus
U kunt zoeken naar een afzonderlijke gebruiker en de nalevingsstatus voor deze gebruiker controleren. De blade **App-rapportage** bevat de volgende informatie voor de geselecteerde gebruiker:
- Apparaten die zijn gekoppeld aan het gebruikersaccount

- Apps met een app-beveiligingsbeleid op het apparaat

- Status:

  - **Ingeschakeld**: het beleid is geïmplementeerd voor de gebruiker en de app is minstens eenmaal in de werkcontext gebruikt.

  - **Niet ingeschakeld**: het beleid is geïmplementeerd voor de gebruiker, maar de app is sindsdien niet gebruikt in de werkcontext.

>[!NOTE]
> Als het app-beveilgingsbeleid niet op de gebruikers waarnaar u hebt gezocht is toegepast, wordt in een bericht gemeld dat er geen app-beveiligingsbeleid wordt toegepast op de gebruikers.

Ga als volgt te werk om de rapportage voor een gebruiker te bekijken:

1.  Voor het selecteren van een gebruiker selecteert u de tegel **Samenvatting**.

    ![Schermopname 3](../media/MAM-reporting-6.png)

2. Kies op de geopende blade **App-rapportage** de optie **Gebruiker selecteren** om een Azure Active Directory-gebruiker te zoeken.

    ![De gebruikersoptie op de blade App-rapportage selecteren](../media/MAM-reporting-2.png)

3. Selecteer de gebruiker uit de lijst. U ziet de details van de nalevingsstatus voor die gebruiker.

### <a name="flagged-users"></a>Gemarkeerde gebruikers
De gedetailleerde weergave bevat het foutbericht, de app die werd geopend toen de fout is opgetreden, het besturingssysteem van het apparaat dat is beïnvloed en een tijdstempel.

## <a name="reporting-view"></a>Rapportageweergave

U vindt er dezelfde rapporten als in de gedetailleerde weergave en aanvullende rapporten voor hulp bij de compatibiliteitsstatus van het app-beveiligingsbeleid:

![Schermopname 4](../media/MAM-reporting-7.png)

-   **Gebruikersrapport over app-beveiliging:** biedt dezelfde informatie als de informatie die u kunt vinden in het rapport **Gebruikersstatus** onder de sectie Gedetailleerde weergave hierboven.

-   **App-rapport over app-beveiliging:** biedt twee verschillende statussen over app-beveiliging die beheerders kunnen selecteren voordat ze het rapport genereren. De statussen kunnen worden beveiligd of juist niet.

    -   Gebruikersstatus voor beheerde MAM-activiteit (beveiligd): in dit rapport staat de activiteit van elke beheerde MAM-app, vermeld per gebruiker.

        -   Hierin staan alle apps waarin app-beveiligingsbeleid wordt toegepast voor elke gebruiker én de status van elke app tijdens het inchecken ten opzichte van het app-beveiligingsbeleid, of elke app waarop app-beveiligingsbeleid is toegepast, maar die nooit is ingecheckt.
<br></br>
    -   Gebruikersstatus voor niet-beheerde MAM-activiteit (niet beveiligd): in dit rapport staat de activiteit van apps met MAM-beleid die momenteel niet wordt beheerd, vermeld per gebruiker. Dit kan in de volgende gevallen plaatsvinden:

        -   De apps worden gebruikt door een gebruiker of een app waarop momenteel geen app-beveiligingsbeleid wordt toegepast.

        -   Alle apps zijn ingecheckt, maar er wordt geen app-beveiligingsbeleid op toegepast.

![Schermopname 2](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Tabelgroepering

Zodra de gegevens voor het **gebruikersrapport van de app-beveiliging** worden weergegeven, kunt u gegevens als volgt samenvoegen:

- **Validatieresultaat:** de gegevens worden gegroepeerd op de beveiligingsstatus van apps. Het resultaat kan fout, waarschuwing of geslaagd zijn.
- **App-naam:** de gegevens worden gegroepeerd op apps (de naam van de werkelijke app). Het resultaat kan fout, waarschuwing of geslaagd zijn.

## <a name="export-app-protection-activities-to-csv"></a>App-beveiligingsactiviteiten exporteren naar CSV

U kunt alle beveiligingsactiviteiten voor apps exporteren naar één CSV-bestand. Dit kan nuttig zijn voor het analyseren van alle app-beveiligingsstatussen die door de gebruikers zijn gerapporteerd.

Volg deze stappen voor het genereren van het app-beveiligingsrapport:

1. Kies in de blade Intune Mobile Application Management de optie App-beveiligingsrapport.

    ![Schermopname 6](../media/app-protection-report-csv-2.png)

2. Kies Ja om uw rapport op te slaan, kies vervolgens Opslaan als en selecteer de map waarin u het rapport wilt opslaan.

    ![Schermopname 7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Zie tevens
[Gegevensoverdracht tussen iOS-apps beheren](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](user-experience-for-mam-enabled-android-apps-with-microsoft-intune.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](user-experience-for-mam-enabled-ios-apps-with-microsoft-intune.md)

