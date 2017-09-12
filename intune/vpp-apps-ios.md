---
title: iOS-apps beheren die zijn gekocht via het volume-aankoopprogramma
titlesuffix: Azure portal
description: Meer informatie over hoe u apps kunt synchroniseren die u via het Volume Purchase Program in de iOS Store hebt gekocht, hoe u deze apps kunt beheren en hoe u het gebruik ervan kunt bijhouden.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: addcc2c9a939b8dc62d708b3f9f000cb7c09cef3
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>iOS-apps beheren die u hebt aangeschaft via een volume-aankoopprogramma met Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De iOS App Store biedt u de mogelijkheid meerdere licenties te kopen voor een app die u wilt uitvoeren binnen uw bedrijf. Op deze manier is er minder administratieve overhead dan wanneer u meerdere exemplaren van apps koopt.

Microsoft Intune kan u op de volgende manieren helpen bij het beheren van apps die u via dit programma hebt gekocht:

- Licentiegegevens rapporteren vanuit de App Store
- Bijhouden hoeveel van de licenties u hebt gebruikt
- Niet meer exemplaren van de app installeren dan waar u recht op hebt

U kunt twee methoden gebruiken voor het toewijzen van apps die zijn gekocht via het volume-aankoopprogramma:

### <a name="device-licensing"></a>Apparaatlicenties

Wanneer u een app aan apparaten toewijst, wordt er één app-licentie gebruikt en deze blijft gekoppeld aan het apparaat waaraan u de licentie hebt toegewezen.
Wanneer u apps aan een apparaat toewijst die zijn gekocht via het volume-aankoopprogramma, hoeft de eindgebruiker van het apparaat geen Apple-id te verstrekken voor toegang tot de Store. 



### <a name="user-licensing"></a>Gebruikerslicenties

Wanneer u een app aan gebruikers toewijst, wordt er één app-licentie gebruikt en deze wordt gekoppeld aan de gebruiker. De app kan worden uitgevoerd op meerdere apparaten die eigendom zijn van de gebruiker (met een limiet die door Apple wordt bepaald).
Wanneer u een app aan gebruikers toewijst die is gekocht via het volume-aankoopprogramma, moet elke eindgebruiker een geldige en unieke Apple-id hebben voor toegang tot de App Store.


Verder kunt u met Intune boeken die u hebt gekocht via het volume-aankoopprogramma van Apple synchroniseren, beheren en toewijzen. Zie [E-boeken in iOS beheren die u via een volume-aankoopprogramma hebt aangeschaft](vpp-ebooks-ios.md) voor meer informatie.


## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Volume-purchased apps voor iOS-apparaten beheren
U kunt meerdere licenties voor iOS-apps kopen via het [Apple-VPP voor bedrijven (Volume Purchase Program)](http://www.apple.com/business/vpp/) of het [Apple VPP voor onderwijs (Volume Purchase Program)](http://volume.itunes.apple.com/us/store). Hiervoor moet u een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Bovendien moet u op de hoogte zijn van het volgende:

* U kunt meerdere VPP-tokens aan uw Intune-account koppelen.
* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt op elk gewenst moment een handmatige synchronisatie starten.
* Voordat u begint met het gebruik van iOS VPP met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers (Mobile Device Management). Uit veiligheidsoverwegingen worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Er worden alleen gegevens uit de Apple VPP-service gesynchroniseerd die zijn gemaakt met Intune.
* Intune ondersteunt het toevoegen van maximaal 256 VPP-tokens.
* Als u een app die via een volume-aankoopprogramma is gekocht, toewijst aan een apparaat dat is ingeschreven via een inschrijvingsprofiel voor apparaten of Apple Configurator, werken alleen apps die speciaal zijn gericht op apparaten. Het is niet mogelijk om apps die via een volume-aankoopprogramma zijn gekocht, te richten op gebruikers van een DEP-apparaat, aangezien een dergelijk apparaat niet beschikt over gebruikersaffiniteit.
Dit komt omdat VPP-gebruikerslicenties in iOS kunnen toestaan dat duizenden apparaten via hetzelfde gebruikersaccount worden ingeschreven. Met VPP-gebruikerslicenties in iOS kan een eindgebruiker een app op 5 tot 10 apparaten installeren.
Dat betekent dat de eerste via DEM ingeschreven apparaten de VPP-app installeren via gebruikerslicentieverlening en dat de andere apparaten de app niet krijgen.
* Een VPP-token wordt alleen ondersteund voor gebruik met één Intune-account tegelijk. Gebruik hetzelfde VPP-token niet voor meerdere tenants van Intune.
* Wanneer u VPP-apps met behulp van het gebruikerslicentiemodel toewijst aan gebruikers of apparaten (met gebruikersaffiniteit), moet elke Intune-gebruiker zijn gekoppeld aan een unieke Apple ID of een e-mailadres wanneer ze de voorwaarden en bepalingen van Apple op hun apparaat accepteren.
Als u een apparaat gaat instellen voor een nieuwe Intune-gebruiker, moet u het apparaat configureren met de unieke Apple ID of het e-mailadres van die gebruiker. De Apple ID of het e-mailadres en de Intune-gebruiker vormen een uniek paar dat kan worden gebruikt op maximaal vijf apparaten.

>[!IMPORTANT]
>Nadat u het VPP-token hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.

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

1.  Kies **Beheren** > **App-licenties** in de workload **Mobiele apps**.
2.  Kies de app die u wilt toewijzen op de blade met de lijst met apps en kies vervolgens '**...**' > **Groepen toewijzen**.
3.  Kies **Beheren** > **Toewijzingen** op de blade *<app name>* - **Toewijzingen**.
4.  Kies **Groepen selecteren** en kies op de blade **Groepen selecteren** de Azure AD- gebruikers- of apparaatgroepen waaraan u de app wilt toewijzen.
5.  Voor elke groep die u hebt geselecteerd, kiest u de volgende instellingen:
    - **Type**: kies of de app **Beschikbaar** is (eindgebruikers kunnen de app installeren vanaf de bedrijfsportal), of **Vereist** (de app wordt automatisch geïnstalleerd).
    - **Licentietype**: kies uit **Gebruikerslicenties** of **Apparaatlicenties**.
6.  Als u klaar bent, kiest u **Opslaan**.


>[!NOTE]
>Er wordt een lijst met apps weergegeven die zijn gekoppeld aan een token. Als u een app hebt die aan meerdere VPP-tokens is gekoppeld, wordt dezelfde app meerdere keren weergegeven; eenmaal voor elk token.

## <a name="further-information"></a>Meer informatie

Als u een licentie wilt vrijmaken, moet u de toewijzingsactie wijzigen in Verwijderen. De licentie wordt vrijgemaakt nadat de app is verwijderd. Als u een app die aan een gebruiker werd toegewezen verwijdert, probeert Intune alle app-licenties vrij te maken die aan die gebruiker waren gekoppeld.

Wanneer een gebruiker met een in aanmerking komend apparaat voor de eerste keer probeert een VPP-app op een apparaat te installeren, wordt de gebruiker gevraagd om deel te nemen aan het volume-aankoopprogramma van Apple. Deelname aan het programma moet plaatsvinden voordat de installatie van de app wordt uitgevoerd. De uitnodiging om deel te nemen aan het Apple Volume Purchase Program vereist dat de gebruiker de iTunes-app op het iOS-apparaat kan gebruiken. Als u een beleid hebt ingesteld om de iTunes Store-app uit te schakelen, werkt de gebruikerslicentie niet voor VPP-apps. U kunt dit probleem oplossen door het beleid te verwijderen, zodat de iTunes-app is toegestaan, of door een licentie te verlenen op basis van het apparaat.



## <a name="next-steps"></a>Volgende stappen

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.