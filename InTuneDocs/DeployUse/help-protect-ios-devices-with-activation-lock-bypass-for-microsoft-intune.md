---
title: IOS-activeringsvergrendeling op apparaten beheren | Microsoft Intune
description: Microsoft Intune kan u helpen bij het beheer van de activeringsvergrendeling voor iOS, een onderdeel van de app Zoek mijn iPhone voor apparaten met iOS 7.1 en hoger.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ms.reviewer: joglocke
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8d0e2b79a19dfce1541506bc1da89cb716a1d0af
ms.openlocfilehash: c03c309e1e27a47b65a87aae8833b88680b0d8e8


---

# iOS-apparaten beschermen met bypass van activeringsvergrendeling voor Microsoft Intune
Microsoft Intune kan u helpen bij het beheer van de activeringsvergrendeling voor iOS, een onderdeel van de app Zoek mijn iPhone voor apparaten met iOS 7.1 en hoger. Activeringsvergrendeling wordt automatisch ingeschakeld wanneer een gebruiker de app Zoek mijn iPhone op een apparaat gebruikt. Nadat de vergrendeling is ingeschakeld, moeten de Apple ID en het wachtwoord van de gebruiker worden ingevoerd voordat een van de volgende handelingen kan worden verricht: 

-   Zoek mijn iPhone uitschakelen

-   Het apparaat wissen

-   Het apparaat opnieuw activeren

## Wat activeringsvergrendeling voor u betekent
Activeringsvergrendeling helpt iOS-apparaten te beveiligen en verbetert de kans dat het apparaat wordt teruggevonden na verlies of diefstal. Deze mogelijkheid kan voor u als IT-beheerder echter een aantal uitdagingen opleveren. Bijvoorbeeld:

-   Een gebruiker stelt activeringsvergrendeling in op een apparaat. De gebruiker verlaat vervolgens het bedrijf en levert het apparaat in. Zonder de Apple-id en het wachtwoord van de gebruiker is het niet mogelijk om het apparaat opnieuw te activeren.

-   U hebt een lijst nodig van alle apparaten waarop activeringsvergrendeling is ingeschakeld.

-   Tijdens het vervangen van apparaten binnen uw organisatie, wilt u bepaalde apparaten aan een andere afdeling toewijzen. U kunt alleen apparaten toewijzen waarop de activeringsvergrendeling niet is ingeschakeld.

Voor het oplossen van deze problemen heeft Apple in iOS 7.1 de mogelijkheid geïntroduceerd om een bypass van de activeringsvergrendeling uit te voeren. Hiermee kunt u de activeringsvergrendeling van een apparaat onder supervisie verwijderen zonder dat u de Apple-id en het wachtwoord van de gebruiker nodig hebt. Op apparaten onder supervisie kan een apparaatspecifieke bypass-code voor de activeringsvergrendeling worden gegenereerd, die wordt opgeslagen op de activeringsserver van Apple.

> [!TIP]
> Met de supervisiemodus voor iOS-apparaten kunt u Apple Configurator gebruiken en de vergrendelingsfunctionaliteit te beperken tot bepaalde bedrijfsdoeleinden. De supervisiemodus wordt doorgaans alleen gebruikt voor apparaten in bedrijfseigendom.

## Activeringsvergrendeling beheren met Intune
Intune kan de status opvragen van de activeringsvergrendeling van apparaten met en zonder supervisie waarop iOS 7.1 of hoger wordt uitgevoerd. Alleen voor apparaten onder supervisie kan met Intune de bypass-code van de activeringsvergrendeling worden opgehaald direct aan het apparaat worden uitgegeven. Als het apparaat is gewist, kunt u rechtstreeks toegang krijgen tot het apparaat met de code als gebruikersnaam en een leeg wachtwoord.

**De zakelijke voordelen hiervan zijn**:

-   De gebruiker beschikt over de beveiligingsvoordelen van de app Zoek mijn iPhone.

-   De gebruiker kan werken en u weet zeker dat u het apparaat buiten gebruik kunt stellen of kunt ontgrendelen wanneer het opnieuw moet worden toegewezen.

## Bypass van activeringsvergrendeling gebruiken vanuit de Intune-beheerconsole
> [!IMPORTANT]
> Nadat u voor de activeringsvergrendeling op een apparaat een bypass hebt uitgevoerd, wordt automatisch een nieuwe activeringsvergrendeling toegepast zodra de app Zoek mijn iPhone wordt geopend. U moet daarom **het apparaat fysiek in bezit hebben voordat u deze procedure uitvoert**.

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Groepen** &gt; **Alle apparaten** &gt; **Alle apparaten in bedrijfseigendom**.

2.  Selecteer het apparaat waarvoor u een bypass van de activeringsvergrendeling wilt uitvoeren. Kies **Bypass van activeringsvergrendeling**.

3.  Lees de waarschuwing. Kies **Ja** om door te gaan.

Bekijk de status van de ontgrendelingsaanvraag op de detailpagina voor het apparaat.

## Hoe ziet u op welke apparaten activeringsvergrendeling is ingeschakeld
U kunt op twee manieren zien op welke apparaten activeringsvergrendeling is ingeschakeld:

-   Voer de **Inventarisrapporten van mobiele apparaten**uit: Dit rapport bevat de kolommen **Status activeringsvergrendeling** en **Onder supervisie**, waarin de status van apparaten wordt weergegeven. De waarden voor **Onder supervisie** zijn **Ja** of **Nee**, en de waarden voor **Status activeringsvergrendeling** zijn:

    -   Ingeschakeld met bypass-code

    -   Ingeschakeld zonder bypass-code (apparaat niet onder supervisie)

    -   Ingeschakeld zonder bypass-code (apparaat kan niet worden bereikt)

    -   Niet ingeschakeld

    Het vak **Status activeringsvergrendeling** is leeg voor apparaten waarop niet iOS 7.1 of hoger wordt uitgevoerd.

-   Selecteer een apparaat in een groepsoverzicht om de status van de activeringsvergrendeling in het detailvenster van het apparaat weer te geven.

    Als u een apparaat selecteert in het knooppunt **Alle apparaten in bedrijfseigendom** en de activeringsvergrendeling voor dat apparaat is ingeschakeld, ziet u ook de bypass-code. Deze code kan worden gebruikt om handmatig een bypass van de activeringsvergrendeling uit te voeren.

    > [!IMPORTANT]
    >Intune inventariseert apparaten elke zeven dagen voor Activeringsvergrendeling. Als gevolg hiervan worden apparaten mogelijk niet onmiddellijk weergegeven met hun activeringsvergrendelingstatus in de Intune-console.


### Zie tevens
[Apparaten buiten gebruik stellen](retire-devices-from-microsoft-intune-management.md)
[Uw apparaten beschermen met extern vergrendelen en het opnieuw instellen van de wachtwoordcode](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


