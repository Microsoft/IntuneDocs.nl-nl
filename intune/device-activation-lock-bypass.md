---
title: Het iOS-activeringsslot overslaan met Intune
titlesuffix: Azure portal
description: Meer informatie over het gebruik van om het iOS-activeringslot over te slaan voor toegang tot vergrendelde apparaten.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15c288b31ab3fb31080aff72d2461dc1d24ec5ae
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/25/2018
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a>Activeringsslot op iOS-apparaten onder supervisie overslaan met Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Microsoft Intune kan u helpen bij het beheer van de activeringsvergrendeling voor iOS, een onderdeel van de app Zoek mijn iPhone voor apparaten met iOS 8.0 en hoger. Activeringsvergrendeling wordt automatisch ingeschakeld wanneer een gebruiker de app Zoek mijn iPhone op een apparaat gebruikt. Nadat de vergrendeling is ingeschakeld, moeten de Apple ID en het wachtwoord van de gebruiker worden ingevoerd voordat een van de volgende handelingen kan worden verricht:

- Zoek mijn iPhone uitschakelen
- Het apparaat wissen
- Het apparaat opnieuw activeren

## <a name="how-activation-lock-affects-you"></a>Wat activeringsvergrendeling voor u betekent

Activeringsvergrendeling helpt iOS-apparaten te beveiligen en verbetert de kans dat het apparaat wordt teruggevonden na verlies of diefstal. Deze mogelijkheid kan voor u als IT-beheerder echter een aantal uitdagingen opleveren. Bijvoorbeeld:

- Een gebruiker stelt activeringsvergrendeling in op een apparaat. De gebruiker verlaat vervolgens het bedrijf en levert het apparaat in. Zonder de Apple ID en het wachtwoord van de gebruiker is het niet mogelijk om het apparaat opnieuw te activeren.
- U hebt een lijst nodig van alle apparaten waarop activeringsvergrendeling is ingeschakeld.
- Tijdens het vervangen van apparaten binnen uw organisatie, wilt u bepaalde apparaten aan een andere afdeling toewijzen. U kunt alleen apparaten toewijzen waarop de activeringsvergrendeling niet is ingeschakeld.

Voor het oplossen van deze problemen heeft Apple in iOS 7.1 de mogelijkheid geïntroduceerd om een bypass van de activeringsvergrendeling uit te voeren. Met een bypass van het activeringsslot kunt u het activeringsslot van apparaten onder supervisie verwijderen zonder dat u de Apple-id en het wachtwoord van de gebruiker nodig hebt. Op apparaten onder supervisie kan een apparaatspecifieke bypass-code voor de activeringsvergrendeling worden gegenereerd, die wordt opgeslagen op de activeringsserver van Apple.

>[!TIP]
>Met de supervisiemodus voor iOS-apparaten kunt u Apple Configurator gebruiken en de vergrendelingsfunctionaliteit te beperken tot bepaalde bedrijfsdoeleinden. De supervisiemodus wordt doorgaans alleen gebruikt voor apparaten in bedrijfseigendom.

Meer informatie over het activeringsslot vindt u op de [website van Apple](https://support.apple.com/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Activeringsvergrendeling beheren met Intune
Intune kan de status opvragen van de activeringsvergrendeling van apparaten met supervisie waarop iOS 8.0 of hoger wordt uitgevoerd. Alleen voor apparaten onder supervisie kan met Intune de bypass-code van de activeringsvergrendeling worden opgehaald direct aan het apparaat worden uitgegeven. Als het apparaat is gewist, kunt u rechtstreeks toegang krijgen tot het apparaat met een lege gebruikersnaam en de code als wachtwoord.

**De zakelijke voordelen van het gebruik van Intune voor het beheren van Activeringsslot zijn:**

- De gebruiker beschikt over de beveiligingsvoordelen van de app Zoek mijn iPhone.
- De gebruiker kan werken en u weet zeker dat u het apparaat buiten gebruik kunt stellen of kunt ontgrendelen wanneer het opnieuw moet worden toegewezen.

## <a name="before-you-start"></a>Voordat u begint
Voordat u een bypass van het activeringsslot op apparaten kunt uitvoeren, moet u deze optie eerst inschakelen aan de hand van de volgende instructies:

1. Configureer een Intune-apparaatbeperkingsprofiel voor iOS op basis van de informatie in [How to configure device restriction settings](/intune-azure/configure-devices/how-to-configure-device-restrictions) (Apparaatbeperkingsinstellingen configureren).
2. Schakel in de [instellingen voor apparaatbeperking voor iOS](device-restrictions-ios.md), onder de **Algemene** instellingen, de optie **Activeringsslot** in.
3. Sla het profiel op en [wijs het toe](device-profile-assign.md) aan de apparaten waarop u een bypass van Activeringsslot wilt beheren.


## <a name="how-to-use-activation-lock-bypass"></a>Activeringsslot overslaan gebruiken

>[!IMPORTANT]
>Nadat u voor het activeringsslot op een apparaat een bypass hebt uitgevoerd en als de app Zoek mijn iPhone is geopend, wordt automatisch een nieuw activeringsslot toegepast. U moet daarom **het apparaat fysiek in bezit hebben voordat u deze procedure uitvoert**.

Met de externe apparaatactie **Activeringsvergrendeling overslaan** verwijdert u het activeringsslot van een iOS-apparaat zonder de Apple-id en het wachtwoord van de gebruiker. Als u de activeringsvergrendeling hebt overgeslagen, wordt de activeringsvergrendeling opnieuw ingeschakeld zodra de app Zoek mijn iPhone start. Sla de activeringsvergrendeling alleen over als u fysiek toegang hebt tot het apparaat.

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Apparaten** op de blade **Intune**.
4. Kies op de blade **Apparaten en groepen** de optie **Alle apparaten**.
5. Kies in de lijst met apparaten die u beheert, een iOS-apparaat onder supervisie en kies vervolgens de externe apparaatactie **Activeringsvergrendeling overslaan**.

## <a name="next-steps"></a>Volgende stappen

Bekijk de status van de ontgrendelingsaanvraag op de detailpagina voor het apparaat in de workload **Apparaten beheren**.
