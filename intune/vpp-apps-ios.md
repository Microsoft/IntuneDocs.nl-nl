---
title: iOS-apps beheren die zijn gekocht via het volume-aankoopprogramma
titleSuffix: Intune on Azure
description: Meer informatie over hoe u apps kunt synchroniseren die u via het Volume Purchase Program in de iOS Store hebt gekocht, hoe u deze apps kunt beheren en hoe u het gebruik ervan kunt bijhouden.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16b7ce81eb63a81534af2911b34904d870ac41ad
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>iOS-apps beheren die u hebt aangeschaft via een volume-aankoopprogramma met Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De iOS App Store biedt u de mogelijkheid meerdere licenties te kopen voor een app die u wilt uitvoeren binnen uw bedrijf. Op deze manier is er minder administratieve overhead dan wanneer u meerdere exemplaren van apps koopt.

Microsoft Intune kan u op de volgende manieren helpen bij het beheren van apps die u via dit programma hebt gekocht:

- Licentiegegevens importeren uit de uit de App Store
- Bijhouden hoeveel van de licenties u hebt gebruikt
- Voorkomen dat u meer exemplaren van de app installeert dan u hebt gekocht

Verder kunt u met Intune boeken die u hebt gekocht via het volume-aankoopprogramma van Apple synchroniseren, beheren en toewijzen. Gebruik de werkbelasting **Boeken** in de Intune-portal voor het beheren van boeken. De procedures voor het beheren van boeken zijn hetzelfde als die u gebruikt voor het beheren van apps.
U moet voordat u begint een token van Apple Volume Purchase Program uploaden. Op dit moment kunt u alleen boeken als toewijzen een **Vereiste** installatie.
Wanneer u een boek aan een apparaat toewijst, moet op dat apparaat de ingebouwde app iBooks geïnstalleerd zijn. Als dat niet het geval is, moet de gebruiker de app opnieuw installeren om het boek te kunnen lezen. U kunt Intune momenteel niet gebruiken voor het herstellen van verwijderde ingebouwde apps.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Volume-purchased apps voor iOS-apparaten beheren
U kunt meerdere licenties voor iOS-apps kopen via het [Apple-VPP voor bedrijven (Volume Purchase Program)](http://www.apple.com/business/vpp/) of het [Apple VPP voor onderwijs (Volume Purchase Program)](http://volume.itunes.apple.com/us/store). Hiervoor moet u een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Bovendien moet u op de hoogte zijn van het volgende:

* U kunt meerdere VPP-tokens aan uw Intune-account koppelen.
* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt op elk gewenst moment een handmatige synchronisatie starten.
* Nadat u het VPP-token hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.
* Voordat u begint met het gebruik van iOS VPP met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers (Mobile Device Management). Uit veiligheidsoverwegingen worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Er worden alleen gegevens uit de Apple VPP-service gesynchroniseerd die zijn gemaakt met Intune.
* Intune ondersteunt het toevoegen van maximaal 256 VPP-tokens.
* Als u een app die via een volume-aankoopprogramma is gekocht, toewijst aan een apparaat dat is ingeschreven via een inschrijvingsprofiel voor apparaten of Apple Configurator, werken alleen apps die speciaal zijn gericht op apparaten. Het is niet mogelijk om apps die via een volume-aankoopprogramma zijn gekocht, te richten op gebruikers van een DEP-apparaat, aangezien een dergelijk apparaat niet beschikt over gebruikersaffiniteit.
* Een VPP-token wordt alleen ondersteund voor gebruik met één Intune-account tegelijk. Gebruik hetzelfde VPP-token niet voor meerdere tenants van Intune.
* Wanneer u VPP-apps met behulp van het gebruikerslicentiemodel toewijst aan gebruikers of apparaten (met gebruikersaffiniteit), moet elke Intune-gebruiker zijn gekoppeld aan een unieke Apple ID of een e-mailadres wanneer ze de voorwaarden en bepalingen van Apple op hun apparaat accepteren.
Als u een apparaat gaat instellen voor een nieuwe Intune-gebruiker, moet u het apparaat configureren met de unieke Apple ID of het e-mailadres van die gebruiker. De Apple ID of het e-mailadres en de Intune-gebruiker vormen een uniek paar dat kan worden gebruikt op maximaal vijf apparaten.


## <a name="to-get-and-upload-an-apple-vpp-token"></a>Een Apple VPP-token verkrijgen en uploaden

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Mobiele apps** op de blade **Intune**.
1.  Kies **Instellen** > **VPP-tokens voor iOS** in de workload **Mobiele apps**.
2.  Klik op de blade met de lijst met VPP-tokens en klik op **Toevoegen**.
3.  Geef op de blade **Nieuw VPP-token** de volgende gegevens op:
    - **VPP-tokenbestand**: meld u aan voor het VPP-programma voor bedrijven of voor het VPP-programma voor onderwijs als u dit nog niet hebt gedaan. Nadat u bent aangemeld, downloadt u het Apple VPP-token voor uw account en selecteert u dit hier.
    - **Apple ID**: voer de Apple ID in van het account dat aan het VPP is gekoppeld.
    - **Type VPP-account**: u hebt de keuze uit **Bedrijven** of **Onderwijs**.
4. Klik wanneer u klaar bent op **Uploaden**.

Het token wordt weergegeven op de blade met de lijst met tokens.


U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door **Nu synchroniseren** te kiezen.

> [!NOTE]
> Microsoft Intune synchroniseert alleen gegevens van apps die openbaar beschikbaar zijn via de iTunes Store. **Aangepaste B2B-apps voor iOS** worden nog niet ondersteund. Als uw scenario gericht is op dergelijke apps, wordt de app-informatie niet gesynchroniseerd.

## <a name="to-assign-a-volume-purchased-app"></a>Een app toewijzen die is gekocht via het volume-aankoopprogramma

1. Kies **Beheren** > **Apps met licenties** in de workload **Mobiele apps**.
2. Kies de app die u wilt toewijzen op de blade met de lijst met apps en kies vervolgens **...** > **Groepen toewijzen**.
3. Kies **Beheren** > **Toegewezen groepen** op de blade <*app-naam*> - **Toegewezen groepen**.
4. Kies **Groepen toewijzen** en kies op de blade **Groepen selecteren** de Azure AD- gebruikers- of apparaatgroepen waaraan u de app wilt toewijzen.
U moet de toewijzingsactie instellen op **Vereist**. Daarnaast zijn toewijzingen aan apparaatgroepen beschikbaar voor tenants die zijn gemaakt na januari 2017. Als uw tenant voor die datum is gemaakt en u niet de optie hebt om VPP-apps toe te wijzen aan apparaatgroepen, neemt u contact op met Intune-support.
5. Als u klaar bent, kiest u **Opslaan**.

>[!NOTE]
>Er wordt een lijst met apps weergegeven die zijn gekoppeld aan een token. Als u een app hebt die aan meerdere VPP-tokens is gekoppeld, wordt dezelfde app meerdere keren weergegeven; eenmaal voor elk token.

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.

## <a name="further-information"></a>Meer informatie

Wanneer u de app als een **vereiste** installatie toewijst, gebruikt elke gebruiker die de app installeert een licentie.

Als u een licentie wilt vrijmaken, moet u de toewijzingsactie wijzigen in **Verwijderen**. De licentie wordt vrijgemaakt nadat de app is verwijderd.

Wanneer een gebruiker met een in aanmerking komend apparaat voor de eerste keer probeert een VPP-app te installeren, wordt de gebruiker gevraagd om deel te nemen aan het volume-aankoopprogramma van Apple. Deelname aan het programma moet plaatsvinden voordat de installatie van de app wordt uitgevoerd. De uitnodiging om deel te nemen aan het Apple Volume Purchase Program vereist dat de gebruiker de iTunes-app op het iOS-apparaat kan gebruiken. Als u een beleid hebt ingesteld om de iTunes Store-app uit te schakelen, werkt de gebruikerslicentie niet voor VPP-apps. U kunt dit probleem oplossen door het beleid te verwijderen, zodat de iTunes-app is toegestaan, of door een licentie te verlenen op basis van het apparaat.

Wanneer u een VPP-app als beschikbaar toewijst, worden de app-inhoud en de licentie rechtstreeks vanuit de App Store toegewezen.
