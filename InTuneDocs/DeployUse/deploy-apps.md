---
# required metadata

title: Apps implementeren | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: mghadial
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Apps implementeren met Microsoft Intune

In dit onderwerp worden enkele concepten uitgelegd die u moet begrijpen voordat u apps met Microsoft Intune gaat implementeren.

## De Microsoft Intune-software-uitgever
De **Microsoft Intune-software-uitgever** wordt gestart wanneer u apps aan de Microsoft Intune-beheerconsole toevoegt of hierin wijzigt. Vanuit de uitgever selecteert en configureert u een type software-installatieprogramma dat apps (programma's voor computers of apps voor mobiele apparaten) uploadt voor opslag in Intune-cloudopslag, of dat doorverwijst naar een webwinkel of webtoepassing.

### Vereisten
Voordat u de Microsoft Intune-software-uitgever gaat gebruiken, moet u de volledige versie van [Microsoft .NET Framework 4.0](https://www.microsoft.com/download/details.aspx?id=17851) installeren. Na de installatie moet u uw computer mogelijk opnieuw opstarten voordat de software-uitgever correct wordt geopend.

## Cloudopslag
Alle apps die u implementeert met behulp van het installatietype van het software-installatieprogramma, moeten worden verpakt en naar Microsoft Intune-cloudopslag worden geüpload. Een proefabonnement op Intune omvat 2 GB (gigabyte) cloudopslag, die wordt gebruikt voor het opslaan van beheerde apps en updates. Een betaald abonnement omvat 20 GB, met de mogelijkheid extra opslagruimte te kopen.

In het knooppunt **Opslaggebruik** van de werkruimte **Beheer** kunt u zien hoeveel ruimte u gebruikt. U kunt er ook meer opslagruimte kopen.

De volgende regels zijn van toepassing op het aanschaffen van extra cloudopslag voor Intune:

-   U moet een actief betaald abonnement hebben om meer opslagruimte te kunnen aanschaffen.

-   Alleen financieel medewerkers of hoofdbeheerders voor uw Microsoft Online Service kunnen extra opslag aanschaffen via de Office 365-beheerportal. Als u deze medewerkers wilt toevoegen, verwijderen of beheren, moet u hoofdbeheerder zijn en u aanmelden bij de Office 365-beheerportal.

-   Als u een volumelicentieklant bent die Intune of de Microsoft Intune-invoegtoepassing heeft aangeschaft via de Enterprise Agreement, neem dan contact op met uw accountmanager bij Microsoft of Microsoft Partner voor prijsinformatie en om meer opslagruimte aan te schaffen.

#### Vereisten voor cloudopslag

-   Alle bestanden die bij een app horen, moeten zich op dezelfde locatie bevinden en voor Intune toegankelijk zijn.

-   De maximale bestandsgrootte voor elk bestand dat u uploadt, is 2 GB.

-   Als u bestanden wilt uploaden, moet u een minimale internetsnelheid van 768 kbps hebben.

## Acties voor de implementatie van apps
Wanneer u apps implementeert, kunt u kiezen uit een van de volgende implementatieacties:

-   **Vereiste installatie**: de app wordt op het apparaat geïnstalleerd zonder dat tussenkomst van de eindgebruiker is vereist.

    > [!TIP] Voor iOS-apparaten die zich niet in de modus Supervisie bevinden, en voor alle Android-apparaten, moet de gebruiker de aangeboden app accepteren voordat deze wordt geïnstalleerd.
    >
    > U kunt geen nieuwe apps meer implementeren op iOS-apparaten met een besturingssysteem dat ouder is dan iOS 7.1. Eventuele bestaande geïmplementeerde apps op apparaten met een ouder besturingssysteem dan iOS 7.1 blijven werken en worden door Intune beheerd.
    > 
    >  Als een eindgebruiker een app verwijdert die u hebt geïmplementeerd als een vereiste installatie, wordt de app automatisch opnieuw geïnstalleerd door Intune na de volgende inventarisatiecyclus die meestal elke 7 dagen plaatsvindt.

-   **Beschikbare installatie**: de app wordt weergegeven in de bedrijfsportal en eindgebruikers kunnen de app op aanvraag installeren.

-   **Verwijderen** : de app wordt van het apparaat verwijderd.

-   **Niet van toepassing**: de app wordt niet weergegeven in de bedrijfsportal en wordt op geen enkel apparaat geïnstalleerd.

#### Inzicht in welke implementatieacties beschikbaar zijn voor elk type installatieprogramma

|Type installatieprogramma|Vereiste installatie|Beschikbare installatie|Verwijderen|Niet van toepassing|
|------------------|--------------------|---------------------|-------------|------------------|
|App-pakket voor Windows (geïmplementeerd op een gebruikersgroep)|Ja|Ja|Ja|Ja|
|App-pakket voor Windows (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
|App-pakket voor mobiele apparaten (geïmplementeerd op een gebruikersgroep)|Ja|Ja|Ja|Ja|
|App-pakket voor mobiele apparaten (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
|Windows Installer (geïmplementeerd op een gebruikersgroep)|Nee|Ja|Nee|Ja|
|Windows Installer (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
|Externe koppeling (geïmplementeerd op een gebruikersgroep)|Nee|Ja|Nee|Ja|
|Externe koppeling (geïmplementeerd op een apparaatgroep)|Nee|Nee|Nee|Nee|
|Beheerde iOS-app uit de App Store (geïmplementeerd op een gebruikersgroep)|Ja|Ja|Ja|Ja|
|Beheerde iOS-app uit de App Store (geïmplementeerd op een apparaatgroep)|Ja|Nee|Ja|Ja|
> [!TIP] Wanneer u een app implementeert en zowel gebruikers- als apparaatgroepen selecteert, kunt u de app alleen als **Beschikbare installatie** implementeren.

## Implementatieconflicten
Wanneer twee implementaties met dezelfde implementatieactie worden ontvangen door een apparaat, gelden de volgende regels:

-   Implementaties op een apparaatgroep hebben prioriteit boven implementaties op een gebruikersgroep. Als een app echter op een gebruikersgroep wordt geïmplementeerd met de implementatieactie **Beschikbaar** en dezelfde app wordt ook op een apparaatgroep geïmplementeerd met de implementatieactie **Niet van toepassing**, wordt de app beschikbaar gesteld in de bedrijfsportal zodat gebruikers deze kunnen installeren.

-   De intentie van de IT-beheerder heeft prioriteit ten opzichte van de gebruiker.

-   Een installatieactie heeft prioriteit ten opzichte van een verwijderingsactie.

-   Als een apparaat zowel een vereiste installatie als een beschikbare installatie ontvangt, worden de acties gecombineerd (de app is zowel vereist als beschikbaar).


## Volgende stappen

Lees hoe u [apps in Microsoft Intune implementeert](deploy-apps-in-microsoft-intune.md).

<!--HONumber=Jun16_HO2-->


