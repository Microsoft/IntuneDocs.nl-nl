---
title: App-beveiligingsbeleid controleren
titleSuffix: Microsoft Intune
description: Controleer de status van naleving van Mobile App Management-beleid in Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 282666de444e9da0dd5e406cb45cdf1b9e66c1b2
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
ms.locfileid: "31833151"
---
# <a name="how-to-monitor-app-protection-policies"></a>App-beveiligingsbeleid controleren
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

**Als u zich niet in Azure Portal bevindt**, wordt in dit onderwerp uitgelegd hoe u een [app-beveiligingsbeleid kunt maken](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) in de klassieke Intune-portal.


U kunt de nalevingsstatus van het MAM-beleid dat u hebt toegepast op gebruikers controleren in het deelvenster Intune-app-beveiliging in de [Azure-portal](https://portal.azure.com). U vindt er informatie over de gebruikers waarop het MAM-beleid van toepassing is, de nalevingsstatus en mogelijke problemen die uw gebruikers ervaren.

Er zijn drie verschillende plaatsen waar u de nalevingsstatus kunt bewaken:

-   Samenvattingsweergave

-   Detailweergave

-   Rapportageweergave

## <a name="summary-view"></a>Samenvattingsweergave

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Bewaking en beheer**.
3. Kies **Mobiele apps** in het deelvenster **Intune**.
4. Kies **Controleren** > **Status van de app-beveiliging** in de workload **Mobiele apps** om de samenvattingsweergave te openen:

![De tegel Samenvatting in het deelvenster Intune Mobile Application Management](./media/app-protection-user-status-summary.png)

-   **Gebruikers**: het totale aantal gebruikers in uw bedrijf dat een app gebruikt die is gekoppeld aan een beleid binnen een werkcontext.

-   **BEHEERD DOOR BELEID**: het aantal gebruikers dat een app heeft gebruikt en waaraan een beleid is toegewezen in een werkcontext.

-   **GEEN BELEID**: het aantal gebruikers dat een app gebruikt en waarop geen beleid van toepassing is in een werkcontext. U kunt overwegen deze gebruikers toe te voegen aan het beleid.
    > [!NOTE]
    > Als u meerdere beleidsregels per platform hebt, wordt een gebruiker beschouwd als te worden beheerd door beleid als er ten minste één beleidsregel aan hem of haar is toegewezen.

- **Gemarkeerde gebruikers:** het aantal gebruikers dat problemen ondervindt. Momenteel worden onder **Gemarkeerde gebruikers** alleen gebruikers met gekraakte apparaten gerapporteerd.


## <a name="detailed-view"></a>Detailweergave
U kunt de gedetailleerde weergave van de samenvatting openen door de tegel **Gebruikersstatus** (afhankelijk van het besturingssysteem van het apparaat) en de tegel **Gemarkeerde gebruikers** te kiezen.

### <a name="user-status"></a>Gebruikersstatus
U kunt zoeken naar een afzonderlijke gebruiker en de nalevingsstatus voor deze gebruiker controleren. Het deelvenster **App-rapportage** bevat de volgende informatie voor de geselecteerde gebruiker:
- Apparaten die zijn gekoppeld aan het gebruikersaccount

- Apps met een MAM-beleid op het apparaat

- Status:

  - **Ingeschakeld**: het beleid is geïmplementeerd voor de gebruiker en de app is minstens eenmaal in de werkcontext gebruikt.

  - **Niet ingeschakeld**: het beleid is geïmplementeerd voor de gebruiker, maar de app is sindsdien niet gebruikt in de werkcontext.

>[!NOTE]
> Als het MAM-beleid niet is toegepast op de gebruikers waarnaar u hebt gezocht, wordt in een bericht gemeld dat er geen MAM-beleid wordt toegepast op de gebruikers.

Ga als volgt te werk om de rapportage voor een gebruiker te bekijken:

1.  Voor het selecteren van een gebruiker selecteert u de tegel **Samenvatting**.

    ![Schermafbeelding van de tegel Samenvatting in de blade Intune Mobile Application Management, Instellingen](./media/MAM-reporting-6.png)

2. Kies in het geopende deelvenster **App-rapportage** de optie **Gebruiker selecteren** om een Azure Active Directory-gebruiker te zoeken.

    ![Schermafbeelding van de optie Gebruiker selecteren in het deelvenster App-rapportage](./media/MAM-reporting-2.png)

3. Selecteer de gebruiker uit de lijst. U kunt de details van de nalevingsstatus voor die gebruiker bekijken.

### <a name="flagged-users"></a>Gemarkeerde gebruikers
De gedetailleerde weergave bevat het foutbericht, de app die werd geopend toen de fout is opgetreden, het besturingssysteem van het apparaat dat is beïnvloed en een tijdstempel.

## <a name="reporting-view"></a>Rapportageweergave

U vindt er dezelfde rapporten als in de gedetailleerde weergave en aanvullende rapporten voor hulp bij de compatibiliteitsstatus van het MAM-beleid:

![Schermopname van 2 rapporten die beschikbaar zijn in het deelvenster Instellingen](./media/MAM-reporting-7.png)

-   **Gebruikersrapport over app-beveiliging:** biedt dezelfde informatie als de informatie die u kunt vinden in het rapport **Gebruikersstatus** onder de sectie Gedetailleerde weergave hierboven.

-   **App-rapport over app-beveiliging:** biedt twee verschillende statussen over app-beveiliging die beheerders kunnen selecteren voordat ze het rapport genereren. De statussen kunnen worden beveiligd of juist niet.

    -   Gebruikersstatus voor beheerde MAM-activiteit (beveiligd): in dit rapport staat de activiteit van elke beheerde MAM-app, vermeld per gebruiker.

        -   Hierin staan alle apps waarin MAM-beleid wordt toegepast voor elke gebruiker én de status van elke app tijdens het inchecken ten opzichte van het MAM-beleid, of elke app waarop MAM-beleid is toegepast, maar die nooit is ingecheckt.
<br></br>
    -   Gebruikersstatus voor niet-beheerde MAM-activiteit (niet beveiligd): in dit rapport staat de activiteit van apps met MAM-beleid die momenteel niet wordt beheerd, vermeld per gebruiker. Dit kan in de volgende gevallen plaatsvinden:

        -   De apps worden gebruikt door een gebruiker of een app waarop momenteel geen MAM-beleid wordt toegepast.

        -   Alle apps zijn ingecheckt, maar er wordt geen MAM-beleid op toegepast.

![Schermopname van de blade App-rapportage van een gebruiker met een tabel met details voor 3 geregistreerde apps](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Tabelgroepering

Zodra de gegevens voor het **gebruikersrapport van de app-beveiliging** worden weergegeven, kunt u gegevens als volgt samenvoegen:

- **Validatieresultaat:** de gegevens worden gegroepeerd op de beveiligingsstatus van apps. Het resultaat kan fout, waarschuwing of geslaagd zijn.
- **App-naam:** de gegevens worden gegroepeerd op apps (de naam van de werkelijke app). Het resultaat kan fout, waarschuwing of geslaagd zijn.

## <a name="export-app-protection-activities-to-csv"></a>App-beveiligingsactiviteiten exporteren naar CSV

U kunt alle beveiligingsactiviteiten voor apps exporteren naar één CSV-bestand. Dit kan nuttig zijn voor het analyseren van alle app-beveiligingsstatussen die door de gebruikers zijn gerapporteerd.

Volg deze stappen voor het genereren van het app-beveiligingsrapport:

1. Kies in het deelvenster Intune Mobile Application Management de optie **App-beveiligingsrapport**.

    ![Schermafbeelding van de downloadlink App-beveiliging in het deelvenster Intune Mobile Application Management](./media/app-protection-report-csv-2.png)

2. Kies Ja om uw rapport op te slaan, kies vervolgens Opslaan als en selecteer de map waarin u het rapport wilt opslaan.

    ![Schermopname van het bevestigingsvak Rapport opslaan](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Zie tevens
[Gegevensoverdracht tussen iOS-apps beheren](data-transfer-between-apps-manage-ios.md)

* [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
* [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)
