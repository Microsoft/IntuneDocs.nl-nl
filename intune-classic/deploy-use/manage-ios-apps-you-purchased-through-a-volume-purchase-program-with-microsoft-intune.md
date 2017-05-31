---
title: IOS-apps beheren die zijn gekocht via het volume-aankoopprogramma | Microsoft Docs
description: Met Intune kunt u apps beheren die u via een volume-aankoopprogramma hebt aangeschaft door de licentiegegevens uit de app store te importeren en bij te houden hoeveel licenties u hebt gebruikt. Zo wordt voorkomen dat u meer exemplaren van de app installeert dan u hebt aangeschaft.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c05c9cb1a0de468f1a6663a7870631af159d9b04
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>iOS-apps beheren die u hebt aangeschaft via een volume-aankoopprogramma

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

De iOS App Store biedt u de mogelijkheid meerdere licenties te kopen voor een app die u wilt uitvoeren binnen uw bedrijf. Zodoende kunt u de administratieve overhead voor het bijhouden reduceren als u meerdere exemplaren van apps hebt aangeschaft.

Met Microsoft Intune kunt u nu apps beheren die u via een dergelijk programma hebt aangeschaft, door de licentiegegevens uit de App Store te importeren en bij te houden hoeveel licenties u hebt gebruikt. Zo wordt voorkomen dat u meer exemplaren van de app installeert dan u hebt aangeschaft.

> [!Important]
> Op dit moment wijst Intune iOS VPP-applicenties (Volume Purchase Program voor bedrijven) toe aan gebruikers en niet aan apparaten. Als gevolg hiervan moeten gebruikers het wachtwoord van hun Apple ID invoeren om de app te installeren.
> Het Apple Volume Purchase Program voor onderwijs wordt niet ondersteund in deze release.

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Volume-purchased apps voor iOS-apparaten beheren
U koopt meerdere licenties voor iOS-apps via het [Apple Volume Purchase Program voor bedrijven](http://www.apple.com/business/vpp/). Hiervoor moet u een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Bovendien moet u het volgende weten:

* Intune ondersteunt het toevoegen van maximaal 256 VPP-tokens.
* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt op elk gewenst moment een handmatige synchronisatie starten.
* Nadat u het VPP-token hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.
* Voordat u begint met het gebruik van iOS VPP met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers (Mobile Device Management). Uit veiligheidsoogpunt worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Intune synchroniseert alleen gegevens uit de Apple VPP-service, die zijn gemaakt door Intune.
* U kunt alleen iOS VPP-apps implementeren op apparaten van gebruikers die zijn ingeschreven met het Device Enrollment Protocol (DEP) als gebruikersaffiniteit voor het apparaat is geconfigureerd.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Een Apple VPP-token verkrijgen en uploaden

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Beheer** &gt; **iOS en Mac OS X** &gt; **Volume-aankoopprogramma**.

2.  Kies de koppeling **Apple VPP-account**. Als u dit nog niet hebt gedaan, meldt u zich aan voor het Volume Purchase Program voor bedrijven. Nadat u bent aangemeld, download u het Apple VPP-token voor uw account.

3.  Kies op de pagina **Volume-aankoopprogramma (VPP) van Apple beheren** van de Intune-console de optie **Het VPP-token uploaden**.

4.  Typ of plak in het dialoogvenster **Het VPP-token uploaden** de naam van het VPP-token en uw Apple ID. Kies vervolgens **Uploaden**.

5.  Schakel in het waarschuwingsvenster het selectievakje in om aan te geven dat u begrijpt dat u achteraf niet van VPP-account kunt veranderen. Kies vervolgens **Ja**.

Op de pagina **Volume Purchase Program** kunt u nu informatie bekijken over het Apple VPP-token, inclusief wanneer het voor het laatst is bijgewerkt, wanneer het token verloopt en wanneer dit voor het laatst is gesynchroniseerd met Intune.

U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door **Nu synchroniseren** te kiezen.

## <a name="to-deploy-a-volume-purchased-app"></a>Een app implementeren die is gekocht via het volume-aankoopprogramma

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Apps** &gt; **Apps** &gt; **Apps die zijn gekocht via het volume-aankoopprogramma**. Deze lijst bevat alle apps die zijn gesynchroniseerd met de Apple VPP-service.

2.  Kies de app die u wilt implementeren, kies **Implementatie beheren** en gebruik vervolgens de instructies in het onderwerp [Apps implementeren in Microsoft Intune](deploy-apps-in-microsoft-intune.md) om het uploaden, maken en implementeren van de app te voltooien.

> [!TIP]
> U moet de beschikbare installatie op **Vereist** zetten. Beschikbare installaties worden momenteel niet ondersteund. Bovendien kunt u de app alleen implementeren voor gebruikersgroepen.

Wanneer u de app als een **Vereiste** installatie implementeert, gebruikt iedere gebruiker die de app installeert een licentie.

Als u een licentie wilt vrijmaken, moet u de implementatieactie wijzigen in **Verwijderen**. De licentie wordt vrijgemaakt nadat de app is verwijderd.

Wanneer een gebruiker met een in aanmerking komend apparaat voor de eerste keer probeert een VPP-app te installeren, wordt deze gevraagd om deel te nemen aan het volume-aankoopprogramma van Apple. Dit moet plaatsvinden voordat de installatie van de app wordt voortgezet.

Als er geen licenties meer beschikbaar zijn, mislukt de implementatie.

## <a name="to-monitor-apple-vpp-apps"></a>Apple VPP-apps bewaken
U kunt bijhouden welke VPP-apps zijn geïmplementeerd en hoeveel licenties worden gebruikt vanuit de **Apps**-werkruimte, in het knooppunt **Apps die zijn gekocht via het volume-aankoopprogramma**.

> [!TIP]
> U kunt ook app-**filters** gebruiken om de status van elke app-installatie te onderzoeken.

### <a name="see-also"></a>Zie tevens
[Apps in Microsoft Intune implementeren](deploy-apps-in-microsoft-intune.md)

