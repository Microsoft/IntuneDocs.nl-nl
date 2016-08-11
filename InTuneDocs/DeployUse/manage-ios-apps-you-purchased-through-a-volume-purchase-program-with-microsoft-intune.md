---
title: IOS-apps beheren die zijn gekocht via het volume-aankoopprogramma | Microsoft Intune
description: Met Intune kunt u apps beheren die u via een volume-aankoopprogramma hebt aangeschaft door de licentiegegevens uit de app store te importeren en bij te houden hoeveel licenties u hebt gebruikt. Zo wordt voorkomen dat u meer exemplaren van de app installeert dan u hebt aangeschaft.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c64fb33893027d0000cae4cc3d9c3ed28cc38901
ms.openlocfilehash: 5db23913601973630a4d013aae86cf26af337c4b


---

# iOS-apps beheren die u hebt aangeschaft via een volume-aankoopprogramma
De iOS App Store biedt u de mogelijkheid meerdere licenties te kopen voor een app die u wilt uitvoeren binnen uw bedrijf. Zodoende kunt u de administratieve overhead voor het bijhouden reduceren als u meerdere exemplaren van apps hebt aangeschaft.

Met Microsoft Intune kunt u nu apps beheren die u via een dergelijk programma hebt aangeschaft, door de licentiegegevens uit de App Store te importeren en bij te houden hoeveel licenties u hebt gebruikt. Zo wordt voorkomen dat u meer exemplaren van de app installeert dan u hebt aangeschaft.

> [!Important]
> Op dit moment wijst Intune iOS VPP-applicenties toe aan gebruikers en niet aan apparaten. Als gevolg hiervan moeten eindgebruikers het wachtwoord van hun Apple-id invoeren om de app te installeren.

## Volume-purchased apps voor iOS-apparaten beheren
U koopt meerdere licenties voor iOS-apps via het [Apple-VPP(Volume Purchase Program voor bedrijven)](http://www.apple.com/business/vpp/). Hiervoor moet u via de website van Apple een Apple VPP-account instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

## Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Bovendien moet u het volgende weten:

* Elke organisatie kan slechts één VPP-account en -token hebben.
* Zodra u een Apple VPP-account aan Intune koppelt, kunt u geen ander account meer koppelen. Daarom is het belangrijk dat er meerdere personen zijn die over de details van het account beschikken dat u gebruikt.
* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt echter op elk gewenst moment een handmatig synchroniseren.
* Nadat u het VPP-token hebt geïmporteerd in Intune, mag u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.
* Voordat u begint met het gebruik van iOS VPP met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers. Uit veiligheidsoogpunt worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Intune synchroniseert alleen gegevens uit de Apple VPP-service die zijn gemaakt door Intune. 
* U kunt geen iOS VPP-apps implementeren op apparaten die zijn geregistreerd met het Device Enrollment Protocol (DEP).

## Een Apple VPP-token verkrijgen en uploaden

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer** &gt; **iOS en Mac OS X** &gt; **Volume-aankoopprogramma**.

2.  Selecteer de koppeling **Apple VPP-account** en meld u zo nodig aan voor het Volume-aankoopprogramma voor bedrijven. Zodra u zich hebt aangemeld, download u de Apple VPP-token voor uw account.

3.  Kies op de pagina **Volume-aankoopprogramma (VPP) van Apple beheren** van de Intune-console de optie **Het VPP-token uploaden**.

4.  Typ of plak in het dialoogvenster **Het VPP-token uploaden** de naam van het VPP-token en uw Apple-id. Kies vervolgens **Uploaden**.

5.  Schakel in het waarschuwingsvenster het selectievakje in om aan te geven dat u begrijpt dat u achteraf niet van VPP-account kunt veranderen. Kies vervolgens **Ja**.

Op de pagina **Volume-aankoopprogramma** kunt u nu informatie bekijken over het Apple VPP-token, zoals wanneer het voor het laatst is bijgewerkt, wanneer het verloopt en wanneer het voor het laatst met Intune is gesynchroniseerd.

U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door **Nu synchroniseren** te kiezen.

## Een app implementeren die is gekocht via het volume-aankoopprogramma

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Apps** &gt; **Beheerde software** &gt; **Apps die zijn gekocht via het volume-aankoopprogramma**. Deze lijst bevat alle apps die zijn gesynchroniseerd met de Apple VPP-service.

2.  Kies de app die u wilt implementeren, kies **Implementatie beheren** en gebruik vervolgens de instructies in het onderwerp [Apps implementeren in Microsoft Intune ](deploy-apps-in-microsoft-intune.md) om het uploaden, maken en implementeren van de app te voltooien.

> [!TIP]
> U moet de beschikbare installatie op **Vereist** zetten. Beschikbare installaties worden momenteel niet ondersteund.

Wanneer u de app als een **Vereiste** installatie implementeert, moet iedere gebruiker die de app installeert, een licentie gebruiken.

Als u een licentie wilt vrijmaken, moet u de implementatieactie wijzigen in **Verwijderen**. De licentie wordt vrijgemaakt zodra de app is verwijderd.

Wanneer een gebruiker met een in aanmerking komend apparaat voor de eerste keer probeert een VPP-app te installeren, wordt deze gevraagd om deel te nemen aan het volume-aankoopprogramma van Apple. Dit moet plaatsvinden voordat de installatie van de app wordt voortgezet.

> [!TIP]
> Bekijk de kolom **Status VPP-gebruiksrechtovereenkomst** voor de acceptatiestatus voor elke gebruiker voor wie de app is geïmplementeerd.

Als er geen licenties meer beschikbaar zijn, mislukt de implementatie.

## Apple VPP-apps bewaken
U kunt bewaken welke VPP-apps zijn geïmplementeerd en hoeveel licenties worden gebruikt vanuit de **Apps**-werkruimte, in het knooppunt **Beheerde software** &gt; **Apps die zijn gekocht via het volume-aankoopprogramma**.

> [!TIP]
> U kunt ook de app **Filters** gebruiken om de status van elke app-installatie te onderzoeken.

### Zie tevens
[Apps in Microsoft Intune implementeren](deploy-apps-in-microsoft-intune.md)




<!--HONumber=Jul16_HO5-->


