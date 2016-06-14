---
# required metadata

title: Waarschuwingen beheren | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74dc4ce4-21da-4f40-a07f-3eea34561eee

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Waarschuwingen beheren in Microsoft Intune
Gebruik de werkruimte **Waarschuwingen** in de Intune-beheerconsole om de algemene status van apparaten in uw organisatie te beoordelen en problemen te identificeren.

#### Actieve waarschuwingen weergeven

1.  Voer in de Intune-beheerconsole een van de volgende handelingen uit:

    -   Klik op **Systeemoverzicht** **om algemene informatie over waarschuwingen weer te geven**, inclusief de eerste drie waarschuwingen en het totale aantal actieve waarschuwingen. U kunt op de koppelingen in deze waarschuwingen klikken om in te zoomen op meer gedetailleerde informatie.

    -   Klik op **Waarschuwingen &gt; Overzicht** **om samenvattingsgegevens voor waarschuwingen weer te geven**. Op de pagina **Overzicht waarschuwingen** wordt in het gebied **Overzicht van waarschuwingstypen** een samenvatting van de waarschuwingen weergegeven. Kritieke waarschuwingen worden eerst weergegeven. U kunt op de koppelingen in deze waarschuwingen klikken om in te zoomen op meer gedetailleerde informatie.

        > [!NOTE]
        > In sommige gevallen wordt een waarschuwingstype meer dan één keer weergegeven in de lijst **Overzicht van waarschuwingstypen**.
        > 
        > Zo kunnen bijvoorbeeld de volgende instanties van het waarschuwingstype 'Beschikbare ruimte logische schijf' worden weergegeven in de lijst:
        > 
        > -   3 Beschikbare ruimte logische schijf
        > -   2 Beschikbare ruimte logische schijf
        > 
        > Dit kan zich voordoen wanneer hetzelfde waarschuwingstype wordt gegenereerd voor apparaten waarop verschillende besturingssystemen worden uitgevoerd. In het voorbeeld is de eerste instantie van het waarschuwingstype Beschikbare ruimte logische schijf, 3 Beschikbare ruimte logische schijf, mogelijk gegenereerd op computers waarop Windows® 7 wordt uitgevoerd. De tweede instantie van het waarschuwingstype Beschikbare ruimte logische schijf is mogelijk gegenereerd op computers waarop Windows Vista® wordt uitgevoerd.

    -   Klik op **Waarschuwingen &gt; Alle waarschuwingen** **om alle actieve waarschuwingen weer te geven**. Op de pagina **Waarschuwingen** wordt een lijst met alle actieve waarschuwingen weergegeven met de volgende kolommen:

        1.  **Naam**: de naam van het waarschuwingstype dat de waarschuwing heeft gegenereerd.

        2.  **Bron**: een koppeling naar de bron van de waarschuwing. Als de weergavedrempel van het waarschuwingstype is ingesteld op **Alles weergeven**, wordt met deze koppeling één apparaat weergegeven. Als de weergavedrempel van het waarschuwingstype is ingesteld op een waarde, wordt met deze koppeling een lijst weergegeven met elk apparaat waarop deze waarschuwing van toepassing is.

        3.  **Laatst bijgewerkt**: geeft de tijd aan waarop de waarschuwing voor het laatst is gewijzigd. Als een waarschuwing is gesloten, wordt de tijd weergegeven waarop de waarschuwing is gesloten.

        4.  **Ernst**: geeft de ernst van de waarschuwing aan.

## Waarschuwingen op het mededelingenbord weergeven
Waarschuwingen op het mededelingenbord bevatten belangrijke servicemededelingen zoals een toekomstige upgrade, een gepland onderhoud of onderbrekingen van de service. Met deze procedure kunt u waarschuwingen op het mededelingenbord weergeven en beheren.

#### Waarschuwingen op het mededelingenbord weergeven en beheren

1.  Klik in de Intune-beheerconsole op **Systeemoverzicht**.

2.  Als er belangrijke servicemededelingen zijn, worden deze weergegeven op het **Mededelingenbord**.

3.  Als u een waarschuwing op het mededelingenbord wilt exporteren naar een csv- of html-bestand, klikt u in de Intune-beheerconsole op **Waarschuwingen &gt; Alle waarschuwingen &gt; Mededelingen**. Selecteer een mededeling, klik op het pictogram Lijst exporteren en volg de instructies.

## Intune-statussen controleren
Bekijk in de werkruimte **Systeemoverzicht** de systeemstatussamenvattingen voor Endpoint Protection, Updates, Status agent, Beleid en Software om problemen te identificeren en te bepalen welke problemen uw onmiddellijke aandacht vereisen. In foutberichten wordt ook een koppeling geboden naar de samenvatting **Servicestatus** met informatie over wanneer het systeem is onderbroken. De samenvatting **Servicestatus** bevat gedetailleerde informatie over het probleem op elke locatie. Hier wordt altijd het tijdstip weergegeven waarop de status voor het laatst is bijgewerkt.

#### De status van uw abonnement weergeven

1.  Klik in de Intune-beheerconsole op **Systeemoverzicht**.

2.  Bij **Systeemstatus** kunt u de status van de verschillende Microsoft Intune-onderdelen onderzoeken. Veel van de items bevatten koppelingen waarmee u kunt inzoomen voor meer informatie. Selecteer bijvoorbeeld onder **Endpoint Protection** het aantal exemplaren om in de werkruimte **Endpoint Protection** een lijst met gedetecteerde schadelijke software weer te geven. Als u het aantal apparaten selecteert, wordt in de werkruimte **Groepen** een lijst met apparaten weergegeven waarop de schadelijke software is gevonden.

## Waarschuwingen sluiten en opnieuw activeren
Intune-waarschuwingen blijven actief totdat een van de volgende gebeurtenissen zich voordoet:

-   Het probleem dat de waarschuwing heeft gegenereerd, is opgelost.

-   De waarschuwing is handmatig gesloten.

-   Er zijn vijf dagen verstreken nadat de waarschuwing is gegenereerd. Na 45 dagen verloopt de waarschuwing en wordt deze automatisch gesloten.

Waarschuwingen die zijn gemarkeerd als gesloten, worden na 90 dagen permanent verwijderd.

#### Handmatig een waarschuwing sluiten

1.  Voer in de Intune-beheerconsole een van de volgende handelingen uit:

    1.  Klik op **Waarschuwingen &gt; Alle waarschuwingen** **om een waarschuwing te sluiten in de lijst met waarschuwingen**. Selecteer een waarschuwing en klik vervolgens op **Waarschuwing sluiten**..

    2.  Klik op **Groepen &gt; Alle apparaten** **om een waarschuwing voor een specifiek apparaat te sluiten**. Selecteer een apparaat en klik op **Eigenschappen weergeven**. Selecteer vervolgens een waarschuwing op het tabblad **Waarschuwingen** en klik op **Waarschuwing sluiten**..

    3.  Klik op **Systeemoverzicht** **om een waarschuwing op het mededelingenbord te sluiten**. Klik op de **X** naast de waarschuwing op het mededelingenbord.

#### Gesloten waarschuwingen weergeven en opnieuw activeren

1.  Klik in de Intune-beheerconsole op **Waarschuwingen &gt; Alle waarschuwingen**.

2.  Klik in de lijst **Filters** op **Gesloten**..

    De namen en aanvullende informatie over de waarschuwingen worden weergegeven in het deelvenster met de beheerlijst. Meer informatie over de geselecteerde waarschuwing wordt weergegeven in het voorbeeldvenster.

3.  Klik op **Waarschuwing opnieuw activeren** om de geselecteerde waarschuwing opnieuw te activeren.

### Zie ook
[Blijf op de hoogte met Microsoft Intune-waarschuwingen](get-notified-by-microsoft-intune-alerts.md)



<!--HONumber=May16_HO1-->


