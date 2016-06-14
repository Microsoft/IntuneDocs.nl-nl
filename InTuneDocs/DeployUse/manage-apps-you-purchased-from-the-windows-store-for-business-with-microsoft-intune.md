---
# required metadata

title: Apps beheren die u hebt aangeschaft in de Windows Store voor Bedrijven | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Met Microsoft Intune apps beheren die u hebt aangeschaft in de Windows Store voor Bedrijven
De [Windows Store voor Bedrijven](https://www.microsoft.com/business-store) biedt een centrale locatie om apps te zoeken en aan te schaffen voor uw organisatie. U kunt zowel afzonderlijke exemplaren van een app als grotere volumes aanschaffen. Als u een koppeling tot stand brengt tussen de Store en Microsoft Intune, kunt u apps die in grotere volumes zijn aangeschaft, beheren vanuit de Intune-console. U hebt bijvoorbeeld de volgende mogelijkheden:
* U kunt de lijst met apps die u in de Store hebt aangeschaft, synchroniseren met Intune.
* Apps die zijn gesynchroniseerd, worden weergegeven in de Intune-beheerconsole en u kunt deze op dezelfde manier implementeren als andere apps
* U kunt in de Intune-beheerconsole bijhouden hoeveel licenties er beschikbaar zijn en hoeveel licenties er worden gebruikt
* Als er onvoldoende licenties beschikbaar zijn, blokkeert Intune de implementatie en installatie van apps.

## Voordat u begint
Bekijk de volgende informatie voordat u begint met het synchroniseren en implementeren van apps uit de Windows Store voor Bedrijven:
* U moet Intune configureren als de instantie voor het beheer van mobiele apparaten voor uw organisatie. Zie [Bereid u voor op het inschrijven van apparaten in Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md) voor meer informatie
* U moet zich hebben geregistreerd voor een account in de Windows Store voor Bedrijven
* Hebt u eenmaal een Windows Store voor Bedrijven-account aan Intune gekoppeld, dan kunt u later niet meer overschakelen op een ander account.
* Apps die zijn aangeschaft in de Store, kunnen niet handmatig worden toegevoegd aan of verwijderd uit Intune. Ze kunnen alleen worden gesynchroniseerd met de Windows Store voor Bedrijven.
* In Intune kunnen alleen online gelicentieerde apps worden gesynchroniseerd die u hebt aangeschaft in de Windows Store voor Bedrijven.

## Uw Windows Store voor Bedrijven-account koppelen aan Intune
Voordat u synchronisatie inschakelt in de Intune-console, moet u uw Store-account configureren om Intune te gebruiken als beheerprogramma:
1. Zorg ervoor dat u zich bij de Store voor Bedrijven aanmeldt met hetzelfde tenantaccount dat u gebruikt om u aan te melden bij Intune.
2. Ga in de Store naar **Instellingen** > **Beheerprogramma's**.
3. Kies op de pagina Beheerprogramma´s de optie **Beheerprogramma toevoegen** en selecteer Microsoft Intune.

U kunt nu doorgaan en synchronisatie instellen in de Intune-console.

## Synchronisatie configureren

1. Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beheer**.
2. Vouw in de werkruimte **Beheer** de optie **Mobile Device Management** uit en klik op **Store voor Bedrijven**.
3. Voer op de pagina **Windows Store voor Bedrijven** de volgende handelingen uit:
* Klik, als u dit nog niet hebt gedaan, op de koppeling om u te registreren bij de Windows Store voor Bedrijven
* Wanneer u zich hebt geregistreerd, klikt u op **Synchronisatie configureren**
4. Selecteer in het dialoogvenster **Synchronisatie met de app Windows Store voor Bedrijven configureren** de optie **Synchronisatie met Windows Store voor Bedrijven inschakelen**.
5. Kies in de vervolgkeuzelijst **Taal** de taal waarin apps uit de Windows Store voor Bedrijven moeten worden weergegeven in de Intune-console. Ongeacht de taal waarin deze apps worden weergegeven, worden ze geïnstalleerd in de taal van de eindgebruiker (indien beschikbaar).
6. Klik op **OK**..

## Apps synchroniseren

1. Klik op de pagina **Windows Store voor Bedrijven** op **Nu synchroniseren** om de apps te synchroniseren die u met Intune hebt aangeschaft in de Store.
2. Klik in de werkruimte **Apps** op **Beheerde Software** > **Gelicentieerde Software** om de beschikbare apps te bekijken en te controleren of uw aangeschafte apps juist zijn geïmporteerd.
Bij de apps in dit knooppunt wordt weergegeven hoeveel licenties u in totaal bezit en hoeveel licenties er voor u beschikbaar zijn.

## Apps implementeren

U kunt apps uit de Store op dezelfde manier implementeren als elke andere Intune-app. Zie [Apps implementeren in Microsoft Intune](deploy-apps-in-microsoft-intune.md) voor meer informatie.
Wanneer u een Windows Store voor Bedrijven-app implementeert, heeft elke gebruiker die de app installeert, hiervoor een licentie nodig. Als alle beschikbare licenties voor een geïmplementeerde app zijn gebruikt, kunt u geen kopieën van de app meer implementeren en moet u een van de volgende dingen doen:
* De app verwijderen van bepaalde apparaten
* Het bereik van de huidige implementatie beperken tot het aantal gebruikers voor wie u een licentie hebt
* Meer kopieën van de app kopen in de Windows Store voor Bedrijven


### Zie ook
[Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)




<!--HONumber=May16_HO1-->


