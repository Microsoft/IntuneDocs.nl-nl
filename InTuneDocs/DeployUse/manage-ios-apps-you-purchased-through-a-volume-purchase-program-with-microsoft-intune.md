---
# required metadata

title: iOS-apps beheren die u hebt aangeschaft via een volume-aankoopprogramma| Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# iOS-apps beheren die u hebt aangeschaft via een volume-aankoopprogramma
Bepaalde App Stores bieden u de mogelijkheid meerdere licenties te kopen voor een app die u wilt uitvoeren binnen uw bedrijf. Zodoende kunt u de administratieve overhead voor het bijhouden reduceren als u meerdere exemplaren van apps hebt aangeschaft.

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

## Een Apple VPP-token verkrijgen en uploaden

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Beheer** &gt; **iOS en Mac OS X** &gt;  **Volume-aankoopprogramma**..

2.  Klik op de koppeling **Apple VPP-account**. Als u dit nog niet hebt gedaan, meldt u zich aan voor het volume-aankoopprogramma voor bedrijven. Zodra u zich hebt aangemeld, download u de Apple VPP-token voor uw account.

3.  Klik op de pagina **Het volume-aankoopprogramma van Apple beheren** van de Intune-console op **Een VPP-token uploaden**..

4.  Typ of plak in het dialoogvenster **Een VPP-token uploaden** de naam van het VPP-token en uw Apple-ID. Klik vervolgens op **Uploaden**..

5.  Schakel in het waarschuwingsvenster het selectievakje in om aan te geven dat u begrijpt dat u het VPP-account achteraf niet kunt wijzigen. Klik vervolgens op **Ja**..

Op de pagina **Volume-aankoopprogramma** kunt u nu informatie bekijken over het Apple VPP-token, zoals wanneer het voor het laatst is bijgewerkt, wanneer het verloopt en wanneer het voor het laatst met Intune is gesynchroniseerd.

U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door op **Nu synchroniseren** te klikken..

## Een via een volume-aankoopprogramma gekochte app implementeren

1.  Klik in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) op **Apps** &gt; **Beheerde software** &gt; **Apps die zijn gekocht via het volume-aankoopprogramma**..

2.  Volg de instructies in het onderwerp [Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) om het uploaden, maken en implementeren van de app te voltooien.

Wanneer u de app als een **Vereiste** installatie implementeert, moet iedere gebruiker die de app installeert, een licentie gebruiken.

Als u een licentie wilt vrijmaken, moet u de implementatieactie wijzigen in **Verwijderen**. De licentie wordt vrijgemaakt zodra de app is verwijderd.

Wanneer een gebruiker met een in aanmerking komend apparaat voor de eerste keer probeert een VPP-app te installeren, wordt deze gevraagd om deel te nemen aan het volume-aankoopprogramma van Apple. Dit moet plaatsvinden voordat de installatie van de app wordt voortgezet.

> [!TIP]
> Bekijk de kolom **Status VPP-gebruiksrechtovereenkomst** voor de acceptatiestatus voor elke gebruiker voor wie de app is geïmplementeerd.

Als er geen licenties meer beschikbaar zijn, mislukt de implementatie.

## Apple VPP-apps bewaken
U kunt bewaken welke VPP-apps er zijn geïmplementeerd en hoeveel licenties er worden gebruikt, vanuit de **Apps**-werkruimte, in het knooppunt **Beheerde software** &gt; **Apps die zijn gekocht via het volume-aankoopprogramma**.

> [!TIP]
> U kunt ook de app **Filters** gebruiken om de status van elke app-installatie te onderzoeken.

### Zie ook
[Apps voor mobiele apparaten toevoegen in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md)



<!--HONumber=May16_HO1-->


