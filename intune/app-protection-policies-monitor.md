---
title: App-beveiligingsbeleid controleren
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt beschreven hoe u de nalevingsstatus van Mobile App Management-beleid in Intune bewaakt.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2d8c34f1947a0abaa4cdf0bbcd65dcf31e4c11ff
ms.sourcegitcommit: 93286c22426dcb59191a99e3cf2af4ff6ff16522
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2019
ms.locfileid: "59566786"
---
# <a name="how-to-monitor-app-protection-policies"></a>App-beveiligingsbeleid controleren
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

U kunt de nalevingsstatus van het MAM-beleid bewaken dat u hebt toegepast op gebruikers vanuit het venster Intune-app-beveiliging in de [Azure-portal](https://portal.azure.com). Bovendien vindt u informatie over de gebruikers die te maken hebben met MAM-beleid, de nalevingsstatus van MAM-beleid en problemen waarmee uw gebruikers mogelijk hebben te maken.

Er zijn drie verschillende plaatsen waar u de nalevingsstatus van MAM-beleid kunt bewaken:
-   Samenvattingsweergave
-   Detailweergave
-   Rapportageweergave

> [!NOTE]
> Zie [Instructies voor het maken en toewijzen van beveiligingsbeleid voor apps?](app-protection-policies.md) voor meer informatie over het maken van app-beveiligingsbeleid.

## <a name="summary-view"></a>Samenvattingsweergave

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Client-apps**.
4. Kies in de workload **Client-apps** de optie **Status van de app-beveiliging** van de sectie**Controleren** om de samenvattingsweergave te bekijken:

![De tegel Samenvatting in het deelvenster Intune Mobile Application Management](./media/app-protection-user-status-summary.png)

- **Toegewezen gebruikers**: Het totale aantal toegewezen gebruikers in uw bedrijf dat van een app gebruikmaakt die is gekoppeld aan een beleid in een werkcontext en wordt beveiligd en in licentie wordt gegeven, evenals de toegewezen gebruikers die onbeveiligd en niet-gelicentieerd zijn.
- **Gemarkeerde gebruikers**: het aantal gebruikers dat problemen ondervindt. Gekraakte (iOS) en geroote (Android) apparaten worden onder **Gemarkeerde gebruikers** gerapporteerd. Gebruikers met apparaten die zijn gemarkeerd door de controle Google SafetyNet-apparaatattestation (indien ingeschakeld door de IT-beheerder) worden hier gerapporteerd. 
- **Gebruikersstatus voor iOS** en **Gebruikersstatus voor Android**: Het aantal gebruikers dat een app heeft gebruikt en waaraan een beleid is toegewezen in een werkcontext voor het betreffende platform. Deze informatie toont het aantal gebruikers dat wordt beheerd door het beleid, evenals het aantal gebruikers dat gebruikmaakt van een app waarop geen beleid in een werkcontext is gericht. U kunt overwegen deze gebruikers toe te voegen aan het beleid.
- **Beste beschermde iOS-apps**: Op basis van de meestgebruikte iOS-apps geeft deze informatie het aantal beschermde en onbeschermde iOS-apps weer.
- **Beste beschermde Android-apps**: Op basis van de meestgebruikte Android-apps geeft deze informatie het aantal beschermde en onbeschermde Android-apps weer.
- **Beste geconfigureerde iOS-apps zonder inschrijving**: Op basis van de meestgebruikte iOS-apps voor niet-ingeschreven apparaten geeft deze informatie het aantal geconfigureerde iOS-apps weer.
- **Beste geconfigureerde Android-apps zonder inschrijving**: Op basis van de meestgebruikte Android-apps voor niet-ingeschreven apparaten geeft deze informatie het aantal geconfigureerde Android-apps weer.

    > [!NOTE]
    > Als u meerdere beleidsregels per platform hebt, wordt een gebruiker beschouwd als te worden beheerd door beleid als er ten minste één beleidsregel aan hem of haar is toegewezen.

## <a name="detailed-view"></a>Detailweergave
U kunt de gedetailleerde weergave van de samenvatting openen door de tegel **Gebruikersstatus** (afhankelijk van het besturingssysteem van het apparaat) en de tegel **Gemarkeerde gebruikers** te kiezen.

### <a name="user-status"></a>Gebruikersstatus
U kunt zoeken naar een afzonderlijke gebruiker en de nalevingsstatus voor deze gebruiker controleren. Het deelvenster **App-rapportage** bevat de volgende informatie voor de geselecteerde gebruiker:
- **Pictogram**: Geeft aan of de status van de app actueel is.
- **App-naam**: De naam van de app.
- **Apparaatnaam**: Apparaten die zijn gekoppeld aan het account van de gebruiker.
- **Apparaattype**: Het type apparaat of besturingssysteem dat het apparaat uitvoert.
- **Beleid**: Het beleid dat is gekoppeld aan de app.
- **Status**:
  - **Ingecheckt**: het beleid is geïmplementeerd voor de gebruiker en de app is minstens eenmaal in de werkcontext gebruikt.
  - **Niet ingecheckt**: het beleid is geïmplementeerd voor de gebruiker, maar de app is sindsdien niet gebruikt in de werkcontext.
- **Laatste synchronisatie**: Wanneer het apparaat voor het laatst is gesynchroniseerd.

>[!NOTE]
> Als het MAM-beleid niet is toegepast op de gebruikers waarnaar u hebt gezocht, wordt in een bericht gemeld dat er geen MAM-beleid wordt toegepast op de gebruikers.

Ga als volgt te werk om de rapportage voor een gebruiker te bekijken:

1.  Voor het selecteren van een gebruiker selecteert u de tegel **Gebruikersstatus**.

    ![Schermopname van de tegel Samenvatting van Mobile Application Management van Intune](./media/MAM-reporting-6.png)

2. Kies in het geopende deelvenster **App-rapportage** de optie **Gebruiker selecteren** om een Azure Active Directory-gebruiker te zoeken.

    ![Schermopname van de optie Gebruiker selecteren in het deelvenster App-rapportage](./media/MAM-reporting-2.png)

3. Selecteer de gebruiker uit de lijst. U kunt de details van de nalevingsstatus voor die gebruiker bekijken.

### <a name="flagged-users"></a>Gemarkeerde gebruikers
De gedetailleerde weergave bevat het foutbericht, de app die werd geopend toen de fout is opgetreden, het besturingssysteem van het apparaat dat is beïnvloed en een tijdstempel. Gebruikers met apparaten die zijn gemarkeerd door de controle Google SafetyNet-apparaatattestation worden hier gerapporteerd met de reden dat zij door Google zijn gerapporteerd.

## <a name="reporting-view"></a>Rapportageweergave

U vindt dezelfde rapporten bovenaan de blade **App-beveiligingsstatus**.

> [!NOTE]
> Intune biedt aanvullende velden voor apparaatrapporten, waaronder de registratie-id van de app, de Android-fabrikant, het model, de versie van de beveiligingspatch en het iOS-model. In Intune zijn deze velden beschikbaar door **Client-apps** > **App-beveiligingsstatus** te selecteren en vervolgens **App-beveiligingsrapport: iOS, Android** te kiezen. Bovendien helpen deze parameters u de lijst **Toestaan** te configureren voor de apparaatfabrikant (Android), evenals de lijst **Toestaan** voor het apparaatmodel (Android en iOS) en de versie-instellingen van de minimale Android-beveiligingspatch. 

Aanvullende rapporten zijn beschikbaar om u te helpen bij de compatibiliteitsstatus van de MAM-beleid. Als u deze rapporten wilt weergeven, selecteert u **Client-apps** > **App-beveiligingsstatus** > **Rapporten**. 

De blade **Rapporten** biedt verschillende rapporten op basis van de gebruiker en de app, waaronder de volgende:


- **Gebruikersrapport**: Dit rapport biedt dezelfde informatie als de informatie die u vindt in het rapport **Gebruikersstatus** onder de sectie [Gedetailleerde weergave](app-protection-policies-monitor.md#detailed-view) hierboven.

- **App-rapport**: In dit rapport worden niet alleen het platform en de app geselecteerd, maar vindt u twee verschillende statussen voor appbescherming die u kunt selecteren voordat u het rapport genereert. De statussen zijn **Beveiligd** of **Niet-beveiligd**.

    -   Gebruikersstatus voor beheerde MAM-activiteit (**Beveiligd**): in dit rapport staat de activiteit van elke beheerde MAM-app, vermeld per gebruiker. Hierin staan alle apps waarin MAM-beleid wordt toegepast voor elke gebruiker én de status van elke app tijdens het inchecken ten opzichte van het MAM-beleid, of elke app waarop MAM-beleid is toegepast, maar die nooit is ingecheckt.
    -   Gebruikersstatus voor niet-beheerde MAM-activiteit (**Niet-beveiligd**): in dit rapport staat de activiteit van apps met MAM-beleid die momenteel niet wordt beheerd, vermeld per gebruiker. Dit kan in de volgende gevallen plaatsvinden:
        -   De apps worden gebruikt door een gebruiker of een app waarop momenteel geen MAM-beleid wordt toegepast.
        -   Alle apps zijn ingecheckt, maar er wordt geen MAM-beleid op toegepast.

        ![Schermopname van de blade App-rapportage van een gebruiker met details voor drie apps](./media/MAM-reporting-4.png)

- **Rapport over gebruikersconfiguratie**: Op basis van een geselecteerde gebruiker biedt dit rapport details over appconfiguraties de gebruikers heeft ontvangen.
- **Appconfiguratierapport**: Op basis van het geselecteerde platform en de app, biedt dit rapport informatie over welke gebruikers configuraties hebben ontvangen voor de geselecteerde app.
- **App Learning-rapport voor Windows Information Protection**: In dit rapport staan welke apps beleidsgrenzen proberen te overschrijden.
- **Website Learning-rapport voor Windows Information Protection**: In dit rapport staan welke websites beleidsgrenzen proberen te overschrijden.

## <a name="table-grouping"></a>Tabelgroepering

Nadat de gegevens voor het **gebruikersrapport van de app-beveiliging** worden weergegeven, kunt u gegevens als volgt samenvoegen:

- **Validatieresultaat:** de gegevens worden gegroepeerd op de beveiligingsstatus van apps. Het resultaat kan fout, waarschuwing of geslaagd zijn.
- **App-naam:** de gegevens worden gegroepeerd op apps (de daadwerkelijke app-naam). Het resultaat kan fout, waarschuwing of geslaagd zijn.

## <a name="export-app-protection-activities-to-csv"></a>App-beveiligingsactiviteiten exporteren naar CSV

U kunt alle beveiligingsactiviteiten voor apps exporteren naar één *.csv*-bestand. Dit kan nuttig zijn voor het analyseren van alle app-beveiligingsstatussen die door de gebruikers zijn gerapporteerd.

Volg deze stappen voor het genereren van het app-beveiligingsrapport:

1. Kies in het deelvenster Intune Mobile Application Management de optie **App-beveiligingsrapport**.

    ![Schermopname van de downloadkoppeling voor app-beveiliging](./media/app-protection-report-csv-2.png)

2. Kies **Ja** om uw rapport op te slaan, kies vervolgens **Opslaan als** en selecteer de map waarin u het rapport wilt opslaan.

    ![Schermopname van het bevestigingsvak Rapport opslaan](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Zie tevens
- [Gegevensoverdracht tussen iOS-apps beheren](data-transfer-between-apps-manage-ios.md)
- [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-android.md)
- [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](app-protection-enabled-apps-ios.md)
