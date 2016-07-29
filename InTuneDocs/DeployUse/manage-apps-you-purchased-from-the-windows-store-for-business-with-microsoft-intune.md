---
title: Apps uit de Windows Store voor Bedrijven beheren | Microsoft Intune
description: Microsoft Intune verbinden met de Windows Store voor Bedrijven als u apps via het volume-aankoopprogramma hebt gekocht vanuit de Intune-console.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6716a3d1fb53dc3de0189f637d5664d0a2023d05
ms.openlocfilehash: 07079b6566bec45593bb9ae49272aa7154a7174d


---

# Apps die u hebt aangeschaft in de Windows Store voor Bedrijven, beheren met Microsoft Intune
[Windows Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en aan te schaffen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u een koppeling tussen Windows Store en Microsoft Intune instelt, kunt u apps die in grotere volumes zijn aangeschaft, beheren vanuit de Intune-console. U hebt bijvoorbeeld de volgende mogelijkheden:
* U kunt de lijst met aangeschafte apps synchroniseren met Intune.
* Apps die zijn gesynchroniseerd, worden weergegeven in de Intune-beheerconsole en u kunt deze op dezelfde manier implementeren als andere apps.
* U kunt in de Intune-beheerconsole bijhouden hoeveel licenties er beschikbaar zijn en hoeveel licenties er worden gebruikt.
* Als er onvoldoende licenties beschikbaar zijn, worden de implementatie en installatie van apps geblokkeerd met Intune.

## Voordat u begint
Lees de volgende informatie voordat u begint met het synchroniseren en implementeren van apps uit Windows Store voor Bedrijven:
* U moet Intune configureren als de Mobile Device Management-instantie voor uw organisatie. Zie [Bereid u voor op het registreren van apparaten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md) voor meer informatie.
* U moet zich hebben geregistreerd voor een account in Windows Store voor Bedrijven.
* Hebt u eenmaal een Windows Store voor Bedrijven-account aan Intune gekoppeld, dan kunt u later niet meer overschakelen op een ander account.
* Apps die zijn aangeschaft in Windows Store, kunnen niet handmatig worden toegevoegd aan of verwijderd uit Intune. Ze kunnen alleen worden gesynchroniseerd met Windows Store voor Bedrijven.
* In Intune kunnen alleen online gelicentieerde apps worden gesynchroniseerd die u hebt aangeschaft in Windows Store voor Bedrijven.
* Apparaten moeten lid zijn van een Active Directory-domein of aan de werkplek zijn toegevoegd voor het gebruik van deze mogelijkheid.
* Ingeschreven apparaten moeten gebruikmaken van de 1511-versie van Windows 10.

## Uw Windows Store voor Bedrijven-account koppelen aan Intune
Voordat u synchronisatie inschakelt in de Intune-console, moet u uw Store-account configureren om Intune te gebruiken als beheerprogramma:
1. Zorg ervoor dat u zich bij Windows Store voor Bedrijven aanmeldt met hetzelfde tenantaccount dat u gebruikt om u aan te melden bij Intune.
2. Kies in Windows Store voor Bedrijven **Instellingen** > **Beheerprogramma's**.
3. Kies op de pagina Beheerprogramma's de optie **Beheerprogramma toevoegen** en kies Microsoft Intune.

U kunt nu doorgaan en synchronisatie instellen in de Intune-console.

## Synchronisatie configureren

1. Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beheer**.
2. Vouw in de werkruimte **Beheer** de optie **Mobile Device Management** uit en klik op **Store voor Bedrijven**.
3. Voer op de pagina **Windows Store voor Bedrijven** de volgende handelingen uit:
* Klik, als u dit nog niet hebt gedaan, op de koppeling om u te registreren bij Windows Store voor Bedrijven
* Wanneer u zich hebt geregistreerd, klikt u op **Synchronisatie configureren**
4. Selecteer in het dialoogvenster **Synchronisatie met de app Windows Store voor Bedrijven configureren** de optie **Synchronisatie met Windows Store voor Bedrijven inschakelen**.
5. Kies in de vervolgkeuzelijst **Taal** de taal waarin apps uit Windows Store voor Bedrijven moeten worden weergegeven in de Intune-console. Ongeacht de taal waarin deze apps worden weergegeven, worden ze geïnstalleerd in de taal van de eindgebruiker (indien beschikbaar).
6. Klik op **OK**.

## Apps synchroniseren

1. Klik op de pagina **Windows Store voor Bedrijven** op **Nu synchroniseren** om de apps te synchroniseren die u met Intune hebt aangeschaft in de Store.
2. Klik in de werkruimte **Apps** op **Beheerde software** > **Gelicentieerde software** om de beschikbare apps te bekijken en te controleren of uw aangeschafte apps juist zijn geïmporteerd.
Bij de apps in dit knooppunt wordt weergegeven hoeveel licenties u in totaal bezit en hoeveel licenties er voor u beschikbaar zijn.

## Apps implementeren

U kunt apps uit de Store op dezelfde manier implementeren als elke andere Intune-app. Zie [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Apps implementeren in Microsoft Intune) voor meer informatie
Wanneer u een Windows Store voor Bedrijven-app implementeert, heeft elke gebruiker die de app installeert, hiervoor een licentie nodig. Als alle beschikbare licenties voor een geïmplementeerde app zijn gebruikt, kunt u geen exemplaren van de app meer implementeren en moet u een van de volgende dingen doen:
* De app verwijderen van bepaalde apparaten
* Het bereik van de huidige implementatie beperken tot het aantal gebruikers waarvoor u een licentie hebt
* Meer exemplaren van de app kopen in de Windows Store voor Bedrijven


### Zie ook
[Add apps for mobile devices in Microsoft Intune (Apps voor mobiele apparaten toevoegen in Microsoft Intune)](add-apps-for-mobile-devices-in-microsoft-intune.md)





<!--HONumber=Jul16_HO4-->


