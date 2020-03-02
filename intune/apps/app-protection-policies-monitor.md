---
title: App-beveiligingsbeleid controleren
titleSuffix: Microsoft Intune
description: In dit onderwerp wordt beschreven hoe u app-beveiligingsbeleid in Intune bewaakt.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/13/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 317f39b28909196d03ef5e7c68c7980f5fdfea3f
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512208"
---
# <a name="how-to-monitor-app-protection-policies"></a>App-beveiligingsbeleid controleren
[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U kunt de status van het app-beveiligingsbeleid bewaken dat u hebt toegepast op gebruikers vanuit het venster Intune-app-beveiliging in de [Azure Portal](https://portal.azure.com). Bovendien vindt u informatie over de gebruikers die te maken hebben met app-beveiligingsbeleid, de nalevingsstatus van beleid en problemen waarmee uw gebruikers mogelijk hebben te maken.

Er zijn drie verschillende plaatsen waar u app-beveiligingsbeleid kunt bewaken:
- Samenvattingsweergave
- Detailweergave
- Rapportageweergave

De bewaarperiode voor app-beveiligingsgegevens is 90 dagen. Alle app-exemplaren die in de afgelopen 90 dagen zijn ingecheckt bij de Intune-service, worden opgenomen in het rapport App-beveiligingsstatus. Een *app-exemplaar* is een combinatie van een unieke gebruiker, app en apparaat. 

> [!NOTE]
> Zie [App-beveiligingsbeleid maken en toewijzen](app-protection-policies.md) voor meer informatie.

## <a name="summary-view"></a>Samenvattingsweergave

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer **Apps** > **Bewaken** > **Status app-beveiliging**.

   ![Schermopname van de tegel Samenvatting van het deelvenster Mobile Application Management van Intune](./media/app-protection-policies-monitor/app-protection-user-status-summary.png)

- **Toegewezen gebruikers**: Het totale aantal toegewezen gebruikers in uw bedrijf dat van een app gebruikmaakt die is gekoppeld aan een beleid in een werkcontext en wordt beveiligd en in licentie wordt gegeven, evenals de toegewezen gebruikers die onbeveiligd en niet-gelicentieerd zijn.
- **Gemarkeerde gebruikers**: Het aantal gebruikers dat problemen ondervindt met hun apparaat. Gekraakte (iOS/iPadOS) en geroote (Android) apparaten worden onder **Gemarkeerde gebruikers** gerapporteerd. Bovendien worden hier gebruikers gerapporteerd met apparaten die zijn gemarkeerd na de controle Google SafetyNet-apparaatattestation (indien ingeschakeld door de IT-beheerder). 
- **Gebruikers met mogelijk schadelijke apps**: Het aantal gebruikers waarvoor mogelijk een schadelijke app op hun Android-apparaat is gedetecteerd door Google Play Protect. 
- **Gebruikersstatus voor iOS** en **Gebruikersstatus voor Android**: Het aantal gebruikers dat een app heeft gebruikt en waaraan een beleid is toegewezen in een werkcontext voor het betreffende platform. Deze informatie toont het aantal gebruikers dat wordt beheerd door het beleid, evenals het aantal gebruikers dat gebruikmaakt van een app waarop geen beleid in een werkcontext is gericht. U kunt overwegen deze gebruikers toe te voegen aan het beleid.
- **Meestgebruikte beveiligde iOS-/iPadOS-apps** en **Meestgebruikte beveiligde Android-apps**: Op basis van de meestgebruikte iOS-/iPadOS- en Android-apps geeft deze informatie het aantal beschermde en onbeschermde apps per platform weer.
- **Meestgebruikte geconfigureerde iOS-/iPadOS-apps zonder registratie** en **Meestgebruikte geconfigureerde Android-apps zonder registratie**: Op basis van de meestgebruikte iOS- en Android-apps voor niet-geregistreerde apparaten geeft deze informatie het aantal geconfigureerde per platform weer (met gebruik van een app-configuratiebeleid).

    > [!NOTE]
    > Als u meerdere beleidsregels per platform hebt, wordt een gebruiker beschouwd als te worden beheerd door beleid als er ten minste één beleidsregel aan hem of haar is toegewezen.

## <a name="detailed-view"></a>Detailweergave
U kunt de gedetailleerde weergave van de samenvatting openen door de tegel **Gemarkeerde gebruikers** en de tegel **Gebruikers met mogelijk schadelijke apps** te kiezen.

### <a name="flagged-users"></a>Gemarkeerde gebruikers
De gedetailleerde weergave bevat het foutbericht, de app die werd geopend toen de fout is opgetreden, het besturingssysteem van het apparaat dat is beïnvloed en een tijdstempel. De fout is karakteristiek voor apparaten die zijn opengebroken (iOS/iPadOS) of geroot (Android). Bovendien worden hier gebruikers gerapporteerd met apparaten die zijn gemarkeerd na de controle SafetyNet-apparaatattestation voor voorwaardelijk starten, met de reden die is gerapporteerd in Google. Als een gebruiker uit het rapport moet worden verwijderd, moet de status van het apparaat zelf worden gewijzigd. Dit gebeurt na de volgende hoofddetectiecontrole (of jailbreakcontrole/SafetyNet-controle) die een positief resultaat moet hebben. Als het apparaat daadwerkelijk is hersteld, wordt de vernieuwing van het rapport Gemarkeerde gebruikers uitgevoerd wanneer het deelvenster opnieuw wordt geladen.

### <a name="users-with-potentially-harmful-apps"></a>Gebruikers met mogelijk schadelijke apps
Gebruikers met apparaten die zijn gemarkeerd na de controle **Bedreigingsscans voor apps vereisen** voor voorwaardelijk starten, worden hier gerapporteerd met de bedreigingscategorie die is gerapporteerd in Google. Als er in dit rapport apps worden vermeld die worden geïmplementeerd via Intune, neemt u contact op met de app-ontwikkelaar voor de app of verwijdert u de app zodat deze niet wordt toegewezen aan uw gebruikers. In de gedetailleerde weergave ziet u het volgende:

- **Gebruiker**: De naam van de gebruiker.
- **Id van app-pakket**: Dit is de manier waarop het Android-besturingssysteem een app identificeert.
- **Of de app beschikt over MAM**: Hiermee wordt aangegeven of de app wordt geïmplementeerd via Microsoft Intune. 
- De **bedreigingscategorie**: In welke door Google bepaalde bedreigingscategorie deze app valt. 
- **E-mail**: Het e-mailadres van de gebruiker.
- **Apparaatnaam**: Namen van apparaten die zijn gekoppeld aan het account van de gebruiker.
- **Een tijdstempel**: Dit is de datum van de laatste synchronisatie die Google heeft voltooid met Microsoft Intune voor mogelijk schadelijke apps.

## <a name="reporting-view"></a>Rapportageweergave

U vindt dezelfde rapporten bovenaan het deelvenster **App-beveiligingsstatus**. Als u deze rapporten wilt weergeven, selecteert u **Apps** > **App-beveiligingsstatus** > **Rapporten**. Het deelvenster **Rapporten** biedt verschillende rapporten op basis van de gebruiker en de app, waaronder de volgende:

### <a name="user-report"></a>Gebruikersrapport
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
> De kolom **Laatste synchronisatie** bevat in het rapport Gebruikersstatus op de console dezelfde waarde als in het [exporteerbare CSV-rapport](https://docs.microsoft.com/intune/app-protection-policies-monitor#export-app-protection-activities) van het app-beveiligingsbeleid. Het verschil is een kleine vertraging in synchronisatie tussen de waarde in de twee rapporten. 
>
> De tijd waarnaar wordt verwezen in Laatste synchronisatie, is het moment waarop het app-exemplaar voor het laatst is gezien in Intune. Wanneer een gebruiker een app start, communiceert de app mogelijk op deze starttijd met de Intune-app-beveiligingsservice, afhankelijk van de datum waarop deze voor het laatst is ingecheckt. Zie [interval voor nieuwe pogingen voor inchecken van app-beveiligingsbeleid](~/apps/app-protection-policy-delivery.md). Als een eindgebruiker deze specifieke app niet heeft gebruikt gedurende het laatste interval voor inchecken (meestal 30 minuten, bij actief gebruik) en de app vervolgens start, gebeurt het volgende:
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

### <a name="app-report"></a>App-rapport
U kunt zoeken op platform en app. Vervolgens geeft het rapport twee verschillende statussen voor app-bescherming die u kunt selecteren voordat u het rapport genereert. De statussen zijn **Beveiligd** of **Niet-beveiligd**.

  - Gebruikersstatus voor beheerde MAM-activiteit (**Beveiligd**): In dit rapport staat de activiteit van elke beheerde MAM-app, vermeld per gebruiker. Het geeft voor elke gebruiker alle apps weer waarop MAM-beleid is gericht, en de status van elke app als ingecheckt bij MAM-beleid. Het rapport bevat ook de status van elke app waarop MAM-beleid is gericht, maar die nooit is ingecheckt.
  - Gebruikersstatus voor niet-beheerde MAM-activiteit (**Niet-beveiligd**): In dit rapport staan de activiteiten van apps met MAM-beleid die momenteel niet worden beheerd, vermeld per gebruiker. Dit kan gebeuren omdat:
    - Deze apps worden gebruikt door een gebruiker of voor een app waarop momenteel geen MAM-beleid is gericht.
    - Alle apps zijn ingecheckt, maar er wordt geen MAM-beleid op toegepast.

    ![Schermopname van het deelvenster App-rapportage van een gebruiker, met details voor drie apps](./media/app-protection-policies-monitor/MAM-reporting-4.png)

### <a name="user-configuration-report"></a>**Rapport over gebruikersconfiguratie**
Op basis van een geselecteerde gebruiker biedt dit rapport details over appconfiguraties de gebruikers heeft ontvangen.

### <a name="app-configuration-report"></a>**Appconfiguratierapport**
Op basis van het geselecteerde platform en de app, biedt dit rapport informatie over welke gebruikers configuraties hebben ontvangen voor de geselecteerde app.

### <a name="app-learning-report-for-windows-information-protection"></a>App Learning-rapport voor Windows Information Protection
In dit rapport staan welke apps beleidsgrenzen proberen te overschrijden.

### <a name="website-learning-for-windows-information-protection"></a>Website Learning-rapport voor Windows Information Protection
In dit rapport staan welke websites beleidsgrenzen proberen te overschrijden.

## <a name="export-app-protection-activities"></a>App-beveiligingsactiviteiten exporteren
U kunt alle beveiligingsactiviteiten voor apps exporteren naar één CSV-bestand. Dit kan nuttig zijn voor het analyseren van alle app-beveiligingsstatussen die door de gebruikers zijn gerapporteerd. In het **CSV-bestand van app-beveiliging ziet u**:
- **Gebruiker**: De naam van de gebruiker.
- **E-mail**: Het e-mailadres van de gebruiker.
- **App**: De naam van de app.
- **App-versie**: De versie van de toepassing app.
- **Apparaatnaam**: Namen van apparaten die zijn gekoppeld aan het account van de gebruiker.
- **Apparaatfabrikant**: Hier wordt de fabrikant van het apparaat weergegeven (alleen Android). 
- **Apparaatmodel**: Hier wordt de fabrikant van het apparaat weergegeven (alleen Android). 
- **Patchversie voor Android**: De datum van de laatste Android-beveiligingspatch.
- **AAD-apparaat-id**: Deze kolom wordt gevuld als het apparaat is gekoppeld aan een AAD.
- **MDM-apparaat-id**: Deze kolom wordt gevuld als het apparaat wordt is geregistreerd bij Microsoft Intune MDM.
- **Platform**: Het besturingssysteem.
- **Platformversie**: De versie van het besturingssysteem.
- **Beheertype**: Type beheer op het apparaat. Bijvoorbeeld Android Enterprise, niet beheerd of MDM.  
- **Status van de app-beveiliging**: Niet beveiligd of beveiligd.
- **Beleid**: Het app-beveiligingsbeleid dat is gekoppeld aan de app.
- **Laatste synchronisatie**: Wanneer de app voor het laatst is gesynchroniseerd met Microsoft Intune. 
- **Nalevingsstatus**: Hiermee wordt aangegeven of de app op het apparaat van de gebruiker op apps gebaseerd beleid voor voorwaardelijke toegang naleeft.  

Volg deze stappen om het CSV-bestand App-beveiliging of App-configuratie te genereren:

1. Kies in het deelvenster Intune Mobile Application Management de optie **App-beveiligingsrapport**.

    ![Schermopname van de downloadkoppeling voor app-beveiliging](./media/app-protection-policies-monitor/app-protection-report-csv-2.png)

2. Kies **Ja** om het rapport op te slaan, en kies vervolgens **Opslaan als**. Selecteer de map waarin u het rapport wilt opslaan.

    ![Schermopname van het bevestigingsvak Rapport opslaan](./media/app-protection-policies-monitor/app-protection-report-csv-1.png)
   
> [!NOTE]
> Intune biedt aanvullende velden voor apparaatrapporten, waaronder de registratie-id van de app, de Android-fabrikant, het model, de versie van de beveiligingspatch en het iOS-/iPadOS-model. In Intune gaat u naar deze velden door achtereenvolgens **Apps** > **App-beveiligingsstatus** > **App-beveiligingsrapport: iOS/iPadOS, Android** te selecteren. Bovendien helpen deze parameters u de lijst **Toestaan** te configureren voor de apparaatfabrikant (Android), evenals de lijst **Toestaan** voor het apparaatmodel (Android en iOS/iPadOS) en de **versie-instellingen van de minimale Android-beveiligingspatch**.   
 
## <a name="see-also"></a>Zie tevens
- [Gegevensoverdracht tussen iOS-/iPadOS-apps beheren](data-transfer-between-apps-manage-ios.md)
- [Wat u kunt verwachten wanneer uw Android-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-android.md)
- [Wat u kunt verwachten wanneer uw iOS-/iPadOS-app wordt beheerd door een app-beveiligingsbeleid](../fundamentals/end-user-mam-apps-ios.md)
