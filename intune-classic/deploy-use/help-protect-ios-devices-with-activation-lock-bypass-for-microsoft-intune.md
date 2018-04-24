---
title: IOS-activeringsvergrendeling op apparaten beheren
description: Microsoft Intune kan u helpen bij het beheer van de activeringsvergrendeling voor iOS, een onderdeel van de app Zoek mijn iPhone voor apparaten met iOS 7.1 en hoger.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 04/24/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 37593e8c554cad73182873b01f6388bdb9cb0035
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a>iOS-apparaten beschermen met bypass van activeringsvergrendeling voor Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Microsoft Intune kan u helpen bij het beheer van de activeringsvergrendeling voor iOS, een onderdeel van de app Zoek mijn iPhone voor apparaten met iOS 8.0 en hoger. Activeringsvergrendeling wordt automatisch ingeschakeld wanneer een gebruiker de app Zoek mijn iPhone op een apparaat gebruikt. Nadat de vergrendeling is ingeschakeld, moeten de Apple ID en het wachtwoord van de gebruiker worden ingevoerd voordat een van de volgende handelingen kan worden verricht: 

-   Zoek mijn iPhone uitschakelen

-   Het apparaat wissen

-   Het apparaat opnieuw activeren

## <a name="how-activation-lock-affects-you"></a>Wat activeringsvergrendeling voor u betekent
Activeringsvergrendeling helpt iOS-apparaten te beveiligen en verbetert de kans dat het apparaat wordt teruggevonden na verlies of diefstal. Deze mogelijkheid kan voor u als IT-beheerder echter een aantal uitdagingen opleveren. Bijvoorbeeld:

-   Een gebruiker stelt activeringsvergrendeling in op een apparaat. De gebruiker verlaat vervolgens het bedrijf en levert het apparaat in. Zonder de Apple ID en het wachtwoord van de gebruiker is het niet mogelijk om het apparaat opnieuw te activeren.

-   U hebt een lijst nodig van alle apparaten waarop activeringsvergrendeling is ingeschakeld.

-   Tijdens het vervangen van apparaten binnen uw organisatie, wilt u bepaalde apparaten aan een andere afdeling toewijzen. U kunt alleen apparaten toewijzen waarop de activeringsvergrendeling niet is ingeschakeld.

Voor het oplossen van deze problemen heeft Apple in iOS 7.1 de mogelijkheid geïntroduceerd om een bypass van de activeringsvergrendeling uit te voeren. Hiermee kunt u de activeringsvergrendeling van een apparaat onder supervisie verwijderen zonder dat u de Apple ID en het wachtwoord van de gebruiker nodig hebt. Op apparaten onder supervisie kan een apparaatspecifieke bypass-code voor de activeringsvergrendeling worden gegenereerd, die wordt opgeslagen op de activeringsserver van Apple.

> [!TIP]
> Met de supervisiemodus voor iOS-apparaten kunt u Apple Configurator gebruiken en de vergrendelingsfunctionaliteit te beperken tot bepaalde bedrijfsdoeleinden. De supervisiemodus wordt doorgaans alleen gebruikt voor apparaten in bedrijfseigendom.

Meer informatie over de activeringsvergrendeling vindt u [hier](https://support.apple.com/en-us/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Activeringsvergrendeling beheren met Intune
Intune kan de status opvragen van de activeringsvergrendeling van apparaten met supervisie waarop iOS 8.0 of hoger wordt uitgevoerd. Alleen voor apparaten onder supervisie kan met Intune de bypass-code van de activeringsvergrendeling worden opgehaald direct aan het apparaat worden uitgegeven. Als het apparaat is gewist, kunt u rechtstreeks toegang krijgen tot het apparaat met een lege gebruikersnaam en de code als wachtwoord.

**De zakelijke voordelen hiervan zijn**:

-   De gebruiker beschikt over de beveiligingsvoordelen van de app Zoek mijn iPhone.

-   De gebruiker kan werken en u weet ondertussen zeker dat u het apparaat buiten gebruik kunt stellen of kunt ontgrendelen wanneer het opnieuw moet worden toegewezen.

## <a name="before-you-start"></a>Voordat u begint

Voordat u bypass van de activeringsvergrendeling op apparaten kunt uitvoeren, moet u deze optie eerst inschakelen. U doet dit als volgt:

1. Gebruik de informatie in het onderwerp [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).
2. In het gedeelte **Inschrijving** van de instellingenpagina stelt u de instelling **Activeringsvergrendeling voor apparaat in toezichtmodus toestaan** in op **Ja**.
3. Sla het beleid op en implementeer het op de apparaten waarop u bypass van activiteitsvergrendeling wilt beheren.

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a>Bypass van activeringsvergrendeling gebruiken vanuit de Intune-beheerconsole
> [!IMPORTANT]
> Nadat u voor de activeringsvergrendeling op een apparaat een bypass hebt uitgevoerd, wordt automatisch een nieuwe activeringsvergrendeling toegepast zodra de app Zoek mijn iPhone wordt geopend. U moet daarom **het apparaat fysiek in bezit hebben voordat u deze procedure uitvoert**.

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) achtereenvolgens **Groepen** &gt; **Alle apparaten** &gt; **Alle apparaten in bedrijfseigendom**.

2.  Selecteer het apparaat waarvoor u een bypass van de activeringsvergrendeling wilt uitvoeren. Kies **Bypass van activeringsvergrendeling**.

3.  Lees de waarschuwing. Kies **Ja** om door te gaan.

Bekijk de status van de ontgrendelingsaanvraag op de detailpagina voor het apparaat.

## <a name="how-to-see-which-devices-are-using-activation-lock"></a>Hoe ziet u op welke apparaten activeringsvergrendeling is ingeschakeld
U kunt op twee manieren zien op welke apparaten activeringsvergrendeling is ingeschakeld:

-   Voer de **Inventarisrapporten van mobiele apparaten**uit: Dit rapport bevat de kolommen **Status activeringsvergrendeling** en **Onder supervisie**, waarin de status van apparaten wordt weergegeven. De waarden voor **Onder supervisie** zijn **Ja** of **Nee**, en de waarden voor **Status activeringsvergrendeling** zijn:

    -   Ingeschakeld met bypass-code

    -   Ingeschakeld zonder bypass-code (apparaat niet onder supervisie)

    -   Ingeschakeld zonder bypass-code (apparaat kan niet worden bereikt)

    -   Niet ingeschakeld

    Het vak **Status activeringsvergrendeling** is leeg voor apparaten waarop niet iOS 8.0 of hoger wordt uitgevoerd.

-   Selecteer een apparaat in een groepsoverzicht om de status van de activeringsvergrendeling in het detailvenster van het apparaat weer te geven.

    Als u een apparaat selecteert in het knooppunt **Alle apparaten in bedrijfseigendom** en de activeringsvergrendeling voor dat apparaat is ingeschakeld, ziet u ook de bypass-code. Deze code kan worden gebruikt om handmatig een bypass van de activeringsvergrendeling uit te voeren.

    > [!IMPORTANT]
    >Intune inventariseert apparaten elke zeven dagen voor Activeringsvergrendeling. Als gevolg hiervan worden apparaten mogelijk niet onmiddellijk weergegeven met hun activeringsvergrendelingstatus in de Intune-console.


### <a name="see-also"></a>Zie ook
[Apparaten buiten gebruik stellen](retire-devices-from-microsoft-intune-management.md)
[Uw apparaten beschermen met extern vergrendelen en het opnieuw instellen van de wachtwoordcode](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)
