---
title: App-beveiligingsbeleid controleren
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt beschreven hoe u app-beveiligingsbeleid in Intune bewaakt.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/09/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 805a1b1145c6b177c83de17de5a2df3efb7380da
ms.sourcegitcommit: 60ed93682a21860e9d99ba1592ede120477f2b4d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2019
ms.locfileid: "72379783"
---
# <a name="how-to-monitor-app-protection-policies"></a>App-beveiligingsbeleid controleren
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U kunt de nalevingsstatus van het MAM-beleid bewaken dat u hebt toegepast op gebruikers vanuit het venster Intune-app-beveiliging in de [Azure-portal](https://portal.azure.com). Bovendien vindt u informatie over de gebruikers die te maken hebben met MAM-beleid, de nalevingsstatus van MAM-beleid en problemen waarmee uw gebruikers mogelijk hebben te maken.

Er zijn drie verschillende plaatsen waar u app-beveiligingsbeleid kunt bewaken:
- Samenvattingsweergave
- Detailweergave
- Rapportageweergave

> [!NOTE]
> Zie [App-beveiligingsbeleid maken en toewijzen](app-protection-policies.md) voor meer informatie.

De bewaarperiode voor app-beveiligingsgegevens is 90 dagen. Alle app-exemplaren die in de afgelopen 90 dagen zijn ingecheckt bij de MAM-service, worden opgenomen in het rapport App-beveiligingsstatus. Een *app-exemplaar* is een combinatie van een unieke gebruiker, app en apparaat. 

## <a name="summary-view"></a>Samenvattingsweergave

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Client-apps**.
4. Kies in de workload **Client-apps**, onder **Controleren**, de optie **App-beveiligingsstatus** om de samenvattingsweergave te bekijken.

   ![Schermopname van de tegel Samenvatting van het deelvenster Mobile Application Management van Intune](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Toegewezen gebruikers**: Het totale aantal toegewezen gebruikers in uw bedrijf dat van een app gebruikmaakt die is gekoppeld aan een beleid in een werkcontext en wordt beveiligd en in licentie wordt gegeven, evenals de toegewezen gebruikers die onbeveiligd en niet-gelicentieerd zijn.
- **Gemarkeerde gebruikers**: Het aantal gebruikers dat problemen ondervindt met hun apparaat. Gekraakte (iOS) en geroote (Android) apparaten worden onder **Gemarkeerde gebruikers** gerapporteerd. Bovendien worden hier gebruikers gerapporteerd met apparaten die zijn gemarkeerd na de controle Google SafetyNet-apparaatattestation (indien ingeschakeld door de IT-beheerder). 
- **Gebruikers met mogelijk schadelijke apps**: Het aantal gebruikers waarvoor mogelijk een schadelijke app op hun Android-apparaat is gedetecteerd door Google Play Protect. 
- **Gebruikersstatus voor iOS** en **Gebruikersstatus voor Android**: Het aantal gebruikers dat een app heeft gebruikt en waaraan een beleid is toegewezen in een werkcontext voor het betreffende platform. Deze informatie toont het aantal gebruikers dat wordt beheerd door het beleid, evenals het aantal gebruikers dat gebruikmaakt van een app waarop geen beleid in een werkcontext is gericht. U kunt overwegen deze gebruikers toe te voegen aan het beleid.
- **Beste beschermde iOS-apps**: Op basis van de meestgebruikte iOS-apps geeft deze informatie het aantal beschermde en onbeschermde iOS-apps weer.
- **Beste beschermde Android-apps**: Op basis van de meestgebruikte Android-apps geeft deze informatie het aantal beschermde en onbeschermde Android-apps weer.
- **Beste geconfigureerde iOS-apps zonder inschrijving**: Op basis van de meestgebruikte iOS-apps voor niet-ingeschreven apparaten geeft deze informatie het aantal geconfigureerde iOS-apps weer.
- **Beste geconfigureerde Android-apps zonder inschrijving**: Op basis van de meestgebruikte Android-apps voor niet-ingeschreven apparaten geeft deze informatie het aantal geconfigureerde Android-apps weer.

    > [!NOTE]
    > Als u meerdere beleidsregels per platform hebt, wordt een gebruiker beschouwd als te worden beheerd door beleid als er ten minste één beleidsregel aan hem of haar is toegewezen.

## <a name="detailed-view"></a>Detailweergave
U kunt de gedetailleerde weergave van de samenvatting openen door de tegel **Gebruikersstatus** (op basis van het OS-platform van het apparaat), de tegel **Gebruikers met mogelijk schadelijke apps** en de tegel **Gemarkeerde gebruikers** te kiezen.

### <a name="user-status"></a>Gebruikersstatus
U kunt zoeken naar een afzonderlijke gebruiker en de nalevingsstatus voor deze gebruiker controleren. Het deelvenster **App-rapportage** bevat de volgende informatie voor de geselecteerde gebruiker:
- **Pictogram**: Geeft aan of de status van de app is bijgewerkt.
- **App-naam**: De naam van de app.
- **Apparaatnaam**: Apparaten die zijn gekoppeld aan het account van de gebruiker.
- **Apparaattype**: Het type apparaat of besturingssysteem dat het apparaat uitvoert.
- **Beleid**: Het beleid dat is gekoppeld aan de app.
- **Status**:
  - **Ingecheckt**: het beleid is geïmplementeerd voor de gebruiker en de app is minstens eenmaal in de werkcontext gebruikt.
  - **Niet ingecheckt**: Het beleid is geïmplementeerd voor de gebruiker, maar de app is sindsdien niet gebruikt in de werkcontext.
- **Laatste synchronisatie**: Wanneer de app voor het laatst is gesynchroniseerd met Intune. 

>[!NOTE]
> De kolom **Laatste synchronisatie** bevat in het rapport Gebruikersstatus op de console dezelfde waarde als in het [exporteerbare CSV-rapport](https://docs.microsoft.com/intune/app-protection-policies-monitor#export-app-protection-activities-to-csv) van het app-beveiligingsbeleid. Het verschil is een kleine vertraging in synchronisatie tussen de waarde in de twee rapporten. 
>
> De tijd waarnaar wordt verwezen in Laatste synchronisatie, is het moment waarop het app-exemplaar voor het laatst is gezien in Intune. Wanneer een gebruiker een app start, communiceert de app mogelijk op deze starttijd met de Intune-app-beveiligingsservice, afhankelijk van de datum waarop deze voor het laatst is ingecheckt. Zie [interval voor nieuwe pogingen voor inchecken van app-beveiligingsbeleid](https://docs.microsoft.com/en-us/intune/app-protection-policy-delivery). Als een eindgebruiker deze specifieke app niet heeft gebruikt gedurende het laatste interval voor inchecken (meestal 30 minuten, bij actief gebruik) en de app vervolgens start, gebeurt het volgende:
>
> - Het exporteerbare CSV rapport van het app-beveiligingsbeleid heeft de nieuwste tijd, binnen 1 minuut (minimum) en 30 minuten (maximum).
> - Het rapport Gebruikersstatus heeft direct de nieuwste tijd.
>
> Denk bijvoorbeeld aan een doelgebruiker met een licentie die een beveiligde app start om 12:00:
> - Als dit een eerste aanmelding betreft, betekent dit dat de gebruiker zich eerder heeft afgemeld, en dus geen registratie van een app-exemplaar bij Intune heeft. Nadat de gebruiker zich heeft aangemeld, ontvangt de gebruiker een nieuwe registratie van het app-exemplaar en kan onmiddellijk worden ingecheckt (met dezelfde vertragingen die eerder zijn vermeld voor toekomstige check-ins). De laatste synchronisatietijd is hier dus 12:00 in het rapport Gebruikersstatus en 12:01 (of op zijn laatst 12:30) in het rapport van het app-beveiligingsbeleid. 
> - Als de gebruiker de app voor het eerst start, is de gerapporteerde tijd van de Laatste synchronisatie afhankelijk van het tijdstip waarop de gebruiker voor het laatst heeft ingecheckt.


Ga als volgt te werk om de rapportage voor een gebruiker te bekijken:

1. Voor het selecteren van een gebruiker selecteert u de tegel **Gebruikersstatus**.

    ![Schermopname van de tegel Samenvatting van Mobile Application Management van Intune](./media/app-protection-policies-monitor/MAM-reporting-6.png)

2. Kies in het deelvenster **App-rapportage** de optie **Gebruiker selecteren** om een Azure Active Directory-gebruiker te zoeken.

    ![Schermopname van de optie Gebruiker selecteren in het deelvenster App-rapportage](./media/app-protection-policies-monitor/MAM-reporting-2.png)

3. Selecteer de gebruiker uit de lijst. U kunt de details van de nalevingsstatus voor die gebruiker bekijken.

>[!NOTE]
> Als het MAM-beleid niet is toegepast op de gebruikers waarnaar u hebt gezocht, wordt in een bericht gemeld dat er geen MAM-beleid wordt toegepast op de gebruikers.

### <a name="flagged-users"></a>Gemarkeerde gebruikers
De gedetailleerde weergave bevat het foutbericht, de app die werd geopend toen de fout is opgetreden, het besturingssysteem van het apparaat dat is beïnvloed en een tijdstempel. De fout is karakteristiek voor apparaten die zijn opengebroken (iOS) of geroot (Android). Bovendien worden hier gebruikers gerapporteerd met apparaten die zijn gemarkeerd na de controle SafetyNet-apparaatattestation voor voorwaardelijk starten, met de reden die is gerapporteerd in Google. Als een gebruiker uit het rapport moet worden verwijderd, moet de status van het apparaat zelf worden gewijzigd. Dit gebeurt na de volgende hoofddetectiecontrole (of jailbreakcontrole/SafetyNet-controle) die een positief resultaat moet hebben. Als het apparaat daadwerkelijk is hersteld, wordt de vernieuwing van het rapport Gemarkeerde gebruikers uitgevoerd wanneer de blade opnieuw wordt geladen.

### <a name="users-with-potentially-harmful-apps"></a>Gebruikers met mogelijk schadelijke apps
In de gedetailleerde weergave ziet u het volgende:

- De gebruiker.
- De id voor het app-pakket.
- Of de app beschikt over MAM.
- De bedreigingscategorie.
- Het e-mailadres.
- De apparaatnaam.
- Een tijdstempel.

Gebruikers met apparaten die zijn gemarkeerd na de controle **Bedreigingsscans voor apps vereisen** voor voorwaardelijk starten, worden hier gerapporteerd met de bedreigingscategorie die is gerapporteerd in Google. Als er in dit rapport apps worden vermeld die worden geïmplementeerd via Intune, neemt u contact op met de app-ontwikkelaar voor de app of verwijdert u de app zodat deze niet wordt toegewezen aan uw gebruikers. 

## <a name="reporting-view"></a>Rapportageweergave

U vindt dezelfde rapporten bovenaan de blade **App-beveiligingsstatus**.

> [!NOTE]
> Intune biedt aanvullende velden voor apparaatrapporten, waaronder de registratie-id van de app, de Android-fabrikant, het model, de versie van de beveiligingspatch en het iOS-model. In Intune gaat u naar deze velden door achtereenvolgens **Client-apps** > **App-beveiligingsstatus** > **App-beveiligingsrapport: iOS, Android** te selecteren. Bovendien helpen deze parameters u de lijst **Toestaan** te configureren voor de apparaatfabrikant (Android), evenals de lijst **Toestaan** voor het apparaatmodel (Android en iOS) en de versie-instellingen van de minimale Android-beveiligingspatch. 

Aanvullende rapporten zijn beschikbaar om u te helpen bij de compatibiliteitsstatus van de MAM-beleid. Als u deze rapporten wilt weergeven, selecteert u **Client-apps** > **App-beveiligingsstatus** > **Rapporten**. 

De blade **Rapporten** biedt verschillende rapporten op basis van de gebruiker en de app, waaronder de volgende:

- **Gebruikersrapport**: Dit rapport biedt dezelfde informatie als de informatie die u vindt in het rapport **Gebruikersstatus** onder de sectie [Gedetailleerde weergave](app-protection-policies-monitor.md#detailed-view) hierboven.

- **App-rapport**: In dit rapport worden niet alleen het platform en de app geselecteerd, maar vindt u twee verschillende statussen voor appbescherming die u kunt selecteren voordat u het rapport genereert. De statussen zijn **Beveiligd** of **Niet-beveiligd**.

  - Gebruikersstatus voor beheerde MAM-activiteit (**Beveiligd**): In dit rapport staat de activiteit van elke beheerde MAM-app, vermeld per gebruiker. Het geeft voor elke gebruiker alle apps weer waarop MAM-beleid is gericht, en de status van elke app als ingecheckt bij MAM-beleid. Het rapport bevat ook de status van elke app waarop MAM-beleid is gericht, maar die nooit is ingecheckt.
  - Gebruikersstatus voor niet-beheerde MAM-activiteit (**Niet-beveiligd**): In dit rapport staan de activiteiten van apps met MAM-beleid die momenteel niet worden beheerd, vermeld per gebruiker. Dit kan gebeuren omdat:
    - Deze apps worden gebruikt door een gebruiker of voor een app waarop momenteel geen MAM-beleid is gericht.
    - Alle apps zijn ingecheckt, maar er wordt geen MAM-beleid op toegepast.

    ![Schermopname van de blade App-rapportage van een gebruiker, met details voor drie apps](./media/app-protection-policies-monitor/MAM-reporting-4.png)

- **Rapport over gebruikersconfiguratie**: Op basis van een geselecteerde gebruiker biedt dit rapport details over appconfiguraties de gebruikers heeft ontvangen.
- **Appconfiguratierapport**: Op basis van het geselecteerde platform en de app, biedt dit rapport informatie over welke gebruikers configuraties hebben ontvangen voor de geselecteerde app.
- **App Learning-rapport voor Windows Information Protection**: In dit rapport staan welke apps beleidsgrenzen proberen te overschrijden.
- **Website Learning-rapport voor Windows Information Protection**: In dit rapport staan welke websites beleidsgrenzen proberen te overschrijden.

## <a name="table-grouping"></a>Tabelgroepering

Nadat de gegevens voor het **gebruikersrapport van de app-beveiliging** worden weergegeven, kunt u gegevens als volgt samenvoegen:

- **Validatieresultaat**: De gegevens worden gegroepeerd op app-beveiligingsstatus. Het resultaat kan Mislukt, Waarschuwing of Geslaagd zijn.
- **App-naam**: De gegevens worden gegroepeerd op basis van de werkelijke app-naam. Opnieuw kan de status Mislukt, Waarschuwing of Geslaagd zijn.

## <a name="export-app-protection-activities"></a>App-beveiligingsactiviteiten exporteren

U kunt alle beveiligingsactiviteiten voor apps exporteren naar één CSV-bestand. Dit kan nuttig zijn voor het analyseren van alle app-beveiligingsstatussen die door de gebruikers zijn gerapporteerd.

Volg deze stappen om het app-beveiligingsrapport te genereren:

1. Kies in het deelvenster Intune Mobile Application Management de optie **App-beveiligingsrapport**.

    ![Schermopname van de downloadkoppeling voor app-beveiliging](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Kies **Ja** om het rapport op te slaan, en kies vervolgens **Opslaan als**. Selecteer de map waarin u het rapport wilt opslaan.

    ![Schermopname van het bevestigingsvak Rapport opslaan](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)

## <a name="see-also"></a>Zie tevens
- [Gegevensoverdracht tussen iOS-apps beheren](data-transfer-between-apps-manage-ios.md)
- [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-android.md)
- [Wat u kunt verwachten wanneer uw iOS-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-ios.md)
