---
title: Het iOS-/iPadOS-activeringsslot overslaan met Intune
titleSuffix: Microsoft Intune
description: Meer informatie over het gebruik van Intune om het iOS-/iPadOS-activeringslot over te slaan voor toegang tot vergrendelde apparaten.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3f67a08ef3cbfae4a801333e5f8ffb5469e723ed
ms.sourcegitcommit: ecaff388038fb800f2e646f8efcf8f3b1e2fd1b1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2020
ms.locfileid: "77438052"
---
# <a name="disable-activation-lock-on-supervised-iosipados-devices-with-intune"></a>Activeringsslot op iOS-/iPadOS-apparaten onder supervisie uitschakelen met Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Microsoft Intune kan u helpen bij het beheer van de activeringsvergrendeling voor iOS/iPadOS, een onderdeel van de app Zoek mijn iPhone voor apparaten met iOS/iPadOS 8.0 en hoger. Activeringsvergrendeling wordt automatisch ingeschakeld wanneer een gebruiker de app Zoek mijn iPhone op een apparaat gebruikt. Nadat de vergrendeling is ingeschakeld, moeten de Apple ID en het wachtwoord van de gebruiker worden ingevoerd voordat een van de volgende handelingen kan worden verricht:

- Zoek mijn iPhone uitschakelen
- Het apparaat wissen
- Het apparaat opnieuw activeren

## <a name="how-activation-lock-affects-you"></a>Wat activeringsvergrendeling voor u betekent

Activeringsvergrendeling helpt iOS-/iPadOS-apparaten te beveiligen en verbetert de kans dat het apparaat wordt teruggevonden na verlies of diefstal. Deze mogelijkheid kan voor u als IT-beheerder echter een aantal uitdagingen opleveren. Bijvoorbeeld:

- Een gebruiker stelt activeringsvergrendeling in op een apparaat. De gebruiker verlaat vervolgens het bedrijf en levert het apparaat in. Zonder de Apple ID en het wachtwoord van de gebruiker is het niet mogelijk om het apparaat opnieuw te activeren.
- U hebt een lijst nodig van alle apparaten waarop activeringsvergrendeling is ingeschakeld.
- Tijdens het vervangen van apparaten binnen uw organisatie, wilt u bepaalde apparaten aan een andere afdeling toewijzen. U kunt alleen apparaten toewijzen waarop de activeringsvergrendeling niet is ingeschakeld.

Voor het oplossen van deze problemen heeft Apple in iOS/iPadOS 7.1 de mogelijkheid geïntroduceerd om het activeringsslot uit te schakelen. Met het uitschakelen van het activeringsslot kunt u het activeringsslot van apparaten onder supervisie verwijderen zonder dat u de Apple-id en het wachtwoord van de gebruiker nodig hebt. Op apparaten onder supervisie kan een apparaatspecifieke bypass-code voor de activeringsvergrendeling worden gegenereerd, die wordt opgeslagen op de activeringsserver van Apple.

>[!TIP]
>Met de supervisiemodus voor iOS-/iPadOS-apparaten kunt u Apple Configurator gebruiken en de vergrendelingsfunctionaliteit te beperken tot bepaalde bedrijfsdoeleinden. De supervisiemodus wordt doorgaans alleen gebruikt voor apparaten in bedrijfseigendom.

Meer informatie over het activeringsslot vindt u op de [website van Apple](https://support.apple.com/HT201365).

## <a name="how-intune-helps-you-manage-activation-lock"></a>Activeringsvergrendeling beheren met Intune
Intune kan de status opvragen van de activeringsvergrendeling van apparaten met supervisie waarop iOS/iPadOS 8.0 of hoger wordt uitgevoerd. Alleen voor apparaten onder supervisie kan met Intune de code voor het uitschakelen van het activeringsslot worden opgehaald direct aan het apparaat worden uitgegeven. Als het apparaat is gewist, kunt u rechtstreeks toegang krijgen tot het apparaat met een lege gebruikersnaam en de code als wachtwoord.

**De zakelijke voordelen van het gebruik van Intune voor het beheren van Activeringsslot zijn:**

- De gebruiker beschikt over de beveiligingsvoordelen van de app Zoek mijn iPhone.
- De gebruiker kan werken en u weet zeker dat u het apparaat buiten gebruik kunt stellen of kunt ontgrendelen wanneer het opnieuw moet worden toegewezen.

## <a name="before-you-start"></a>Voordat u begint
Voordat u het activeringsslot op apparaten kunt uitschakelen, moet u deze optie eerst inschakelen aan de hand van de volgende instructies:

1. Configureer een Intune-apparaatbeperkingsprofiel voor iOS/iPadOS op basis van de informatie in [Apparaatbeperkingsinstellingen configureren in Microsoft Intune](/intune-azure/configure-devices/how-to-configure-device-restrictions).
2. Schakel in de [instellingen voor apparaatbeperking voor iOS](../configuration/device-restrictions-ios.md), onder de **Algemene** instellingen, de optie **Activeringsslot** in.
3. Sla het profiel op en [wijs het toe](../configuration/device-profile-assign.md) aan de apparaten waarop u het uitschakelen van het activeringsslot wilt beheren.


## <a name="how-to-use-disable-activation-lock"></a>Uitschakelen van het activeringsslot gebruiken

>[!IMPORTANT]
>Nadat u het activeringsslot op een apparaat hebt uitgeschakeld en als de app Zoek mijn iPhone is gestart, wordt automatisch een nieuw activeringsslot toegepast. U moet daarom **het apparaat fysiek in bezit hebben voordat u deze procedure uitvoert**.

Met de externe apparaatactie **Activeringsslot uitschakelen** van Intune verwijdert u het activeringsslot van een iOS-/iPadOS-apparaat zonder de Apple ID en het wachtwoord van de gebruiker nodig te hebben. Wanneer u het activeringsslot hebt uitgeschakeld, wordt het activeringsslot opnieuw ingeschakeld zodra de app Zoek mijn iPhone wordt gestart. Schakel het activeringsslot alleen uit als u fysiek toegang hebt tot het apparaat.

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer op de blade **Intune** de optie **Apparaten**.
4. Selecteer op de blade **Apparaten** de optie **Alle apparaten**.
5. Selecteer in de lijst met apparaten die u beheert de externe apparaatactie **Activeringsvergrendeling uitschakelen**.
6. Ga naar de sectie Hardware van het apparaat en kopieer vervolgens de waarde **Code voor het overslaan van het Activeringsslot** onder **Voorwaardelijke toegang**.

    >[!NOTE]
    >Kopieer de bypass-code voordat u het apparaat wist. Als u instellingen van het apparaat opnieuw instelt voordat u de code hebt gekopieerd, wordt de code uit Azure verwijderd.

7. Ga naar de blade **Overzicht** voor het apparaat en selecteer vervolgens **Wissen**.
8. Nadat het apparaat opnieuw is ingesteld, wordt u gevraagd om de *Apple ID* en het *wachtwoord*. Laat het veld *Id* leeg en voer vervolgens de **code voor overslaan** in bij het *wachtwoord*. Hiermee verwijdert u het account van het apparaat. 


## <a name="next-steps"></a>Volgende stappen

Bekijk de status van de ontgrendelingsaanvraag op de detailpagina voor het apparaat in de workload **Apparaten beheren**.
