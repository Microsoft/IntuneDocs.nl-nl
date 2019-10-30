---
title: Apps beheren die zijn gekocht via het volume-aankoopprogramma van Apple
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u apps kunt synchroniseren die u via het volumeaankoopprogramma in de App Store voor iOS en macOS hebt gekocht, hoe u deze apps in Microsoft Intune kunt beheren en hoe u het gebruik ervan kunt bijhouden.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9625243698bffc93ed969a8c2e4b06b4f3093f4d
ms.sourcegitcommit: 06a1fe83fd95c9773c011690e8520733e1c031e3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/23/2019
ms.locfileid: "72785536"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>iOS- en macOS-apps beheren die zijn aangeschaft via het Apple Volume Purchase Program met Microsoft Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

U kunt bij Apple meerdere licenties aanschaffen voor een app die u in uw bedrijf wilt uitvoeren op iOS- en macOS-apparaten. Door meerdere exemplaren aan te schaffen, kunt u apps in uw bedrijf efficiënt beheren.

Microsoft Intune kan u op de volgende manieren helpen bij het beheren van meerdere exemplaren van apps die u via dit programma hebt gekocht:

- Licentiegegevens rapporteren vanuit de App Store.
- Bijhouden hoeveel van de licenties u hebt gebruikt.
- Niet meer exemplaren van de app installeren dan waar u recht op hebt.

U kunt twee methoden gebruiken voor het toewijzen van apps die zijn gekocht via het volume-aankoopprogramma:

## <a name="device-licensing"></a>Apparaatlicenties

Wanneer u een app aan apparaten toewijst, wordt er één app-licentie gebruikt en deze blijft gekoppeld aan het apparaat waaraan u de licentie hebt toegewezen.

Wanneer u apps aan een apparaat toewijst die zijn gekocht via het volume-aankoopprogramma, hoeft de eindgebruiker van het apparaat geen Apple-id te verstrekken voor toegang tot de Store.

## <a name="user-licensing"></a>Gebruikerslicenties

Wanneer u een app aan gebruikers toewijst, wordt er één app-licentie gebruikt en gekoppeld aan de gebruiker. De app kan worden uitgevoerd op maximaal 5 apparaten die eigendom zijn van de gebruiker (de limiet voor het aantal apparaten wordt bepaald door Apple).

Wanneer u een app aan gebruikers toewijst die is gekocht via het volume-aankoopprogramma, moet elke eindgebruiker een geldige en unieke Apple-id hebben voor toegang tot de App Store.

Verder kunt u met Intune boeken op iOS-apparaten die u hebt gekocht via het Apple Volume Purchase Program (VPP) synchroniseren, beheren en toewijzen. Zie [E-boeken in iOS beheren die u via een volume-aankoopprogramma hebt aangeschaft](vpp-ebooks-ios.md) voor meer informatie.

## <a name="manage-volume-purchased-apps-for-ios-and-macos-devices"></a>Apps voor iOS- en macOS-apparaten beheren die u hebt aangeschaft via een volume-aankoopprogramma

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps"></a>Ondersteunt apps die zijn gekocht via het Apple Volume Purchase Program

U kunt meerdere licenties voor iOS- en macOS-apps kopen via het [Apple VPP voor bedrijven (Volume Purchase Program)](https://www.apple.com/business/vpp/) of het [Apple VPP voor onderwijs (Volume Purchase Program)](https://volume.itunes.apple.com/us/store). Hiervoor moet u een Apple VPP-account via de website van Apple instellen en het Apple VPP-token uploaden naar Intune.  U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps.

### <a name="supports-business-to-business-volume-purchased-apps"></a>Ondersteunt apps die zijn gekocht via het business-to-business-volume-aankoopprogramma

Daarnaast kunnen externe ontwikkelaars privé apps distribueren naar geautoriseerde Volume Purchase Program for Business-leden die zijn opgegeven in App Store Connect. Deze VPP for Business-leden kunnen zich aanmelden bij de Volume Purchase Program App Store en hun apps kopen. VPP for Business-apps die door de gebruiker zijn gekocht, worden gesynchroniseerd naar hun Intune-tenant.

## <a name="before-you-start"></a>Voordat u begint
Voordat u begint, moet u een VPP-token van Apple verkrijgen en dit uploaden naar uw Intune-account. Bovendien moet u op de hoogte zijn van het volgende:

* U kunt meerdere VPP-tokens koppelen aan uw Intune-account.
* Als u eerder een VPP-token hebt gebruikt voor een ander product, moet u een nieuw token voor gebruik met Intune genereren.
* Elke token is één jaar geldig.
* Standaard wordt Intune twee keer per dag gesynchroniseerd met de Apple VPP-service. U kunt op elk gewenst moment een handmatige synchronisatie starten.
* Voordat u begint met het gebruik van Apple VPP met Intune, verwijdert u eventuele bestaande VPP-gebruikersaccounts die zijn gemaakt met andere MDM-leveranciers (Mobile Device Management). Uit veiligheidsoverwegingen worden deze gebruikersaccounts niet met Intune gesynchroniseerd. Er worden alleen gegevens uit de Apple VPP-service gesynchroniseerd die zijn gemaakt met Intune.
* Intune ondersteunt het toevoegen van maximaal 256 VPP-tokens.
* Met het DEP-programma (Device Enrollment Profile) van Apple wordt de MDM-registratie (Mobile Device Management) geautomatiseerd. Met DEP kunt u bedrijfsapparaten op afstand configureren. U kunt zich registreren voor het DEP-programma met hetzelfde programma-agentaccount dat u hebt gebruikt voor VPP van Apple. De Apple Deployment Programs-id is uniek voor programma's die worden vermeld op de website [Apple Deployment Programs](https://deploy.apple.com) en kan niet worden gebruikt voor het aanmelden bij Apple-services, zoals de iTunes Store.
* Wanneer u VPP-apps met behulp van het gebruikerslicentiemodel toewijst aan gebruikers of apparaten (met gebruikersaffiniteit), moet elke Intune-gebruiker zijn gekoppeld aan een unieke Apple ID of een e-mailadres wanneer ze de voorwaarden en bepalingen van Apple op hun apparaat accepteren.
* Als u een apparaat instelt voor een nieuwe Intune-gebruiker, configureert u dit met de unieke Apple-id of het e-mailadres van de desbetreffende gebruiker. De Apple-id of het e-mailadres en de Intune-gebruiker vormen een uniek paar dat kan worden gebruikt op maximaal vijf apparaten.
* Een VPP-token wordt alleen ondersteund voor gebruik met één Intune-account tegelijk. Gebruik hetzelfde VPP-token niet voor meerdere tenants van Intune.

>[!IMPORTANT]
>Nadat u het VPP-token hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Een Apple VPP-token verkrijgen en uploaden

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Client-apps** > **Apple VPP-tokens** onder **Installatie**.
4. Selecteer **Maken** in het deelvenster met de lijst VPP-tokens.
5. Geef in het deelvenster **VPP-token maken** de volgende gegevens op:
    - **VPP-tokenbestand**: meld u aan voor het VPP-programma voor bedrijven of voor het VPP-programma voor onderwijs als u dit nog niet hebt gedaan. Nadat u bent aangemeld, downloadt u het Apple VPP-token voor uw account en selecteert u dit hier.
    - **Apple ID**: voer de Apple ID in van het account dat aan het VPP is gekoppeld.
    - **Land/regio**: selecteer VPP-store voor uw land/regio.  Intune synchroniseert VPP-apps voor alle landinstellingen uit de opgegeven store uit het land of de regio waar de VPP geldt.
        > [!WARNING]  
        > Als u het land of de regio wijzigt, worden de metagegevens en store-URL van de apps bijgewerkt bij de volgende synchronisatie met de Apple-service voor de apps die met deze token zijn gemaakt. De app wordt niet bijgewerkt als deze niet bestaat in de store van het nieuwe land of de nieuwe regio.

    - **Type VPP-account**: u hebt de keuze uit **Bedrijven** of **Onderwijs**.
    - **Automatische updates voor apps**: kies **Aan** of **Uit** om automatische updates in of uit te schakelen. Wanneer deze zijn ingeschakeld, detecteert Intune updates voor de VPP-app in de app store en pusht ze automatisch naar het apparaat als dit incheckt. Met automatische updates voor Apple VPP-apps worden alleen apps die zijn geïmplementeerd met de installatie-intentie **Vereiste**, automatisch bijgewerkt. Voor apps die zijn geïmplementeerd met de installatie-intentie **Beschikbaar**, wordt met de automatische update voor de IT-beheerder een statusbericht gegenereerd waarin staat dat een nieuwe versie van de app beschikbaar is. Dit statusbericht kan worden weergegeven door de app te selecteren, Apparaatinstallatiestatus te selecteren en de Statusdetails te controleren. Daarnaast ziet de gebruiker dat de app niet is geïnstalleerd in de Bedrijfsportal, zelfs als er een eerdere versie van de app is geïnstalleerd. In dit geval kan de gebruiker de app opnieuw installeren door te klikken op **Installeren** in het app-detailscherm in de bedrijfsportal-app om de nieuwe versie van de app te installeren.

        > [!NOTE]
        > Automatische updates voor apps worden gebruikt voor apps voor zowel gelicentieerde apparaten als gebruikers voor iOS-versie 11.0 en hoger of macOS 10.12 en hoger.
6. Selecteer **Maken** wanneer u klaar bent.

Het token wordt weergegeven in het deelvenster met de lijst met tokens.

U kunt de gegevens waarover Apple beschikt, op elk gewenst moment synchroniseren met Intune door **Nu synchroniseren** te kiezen.

## <a name="to-assign-a-volume-purchased-app"></a>Een app toewijzen die is gekocht via het volume-aankoopprogramma

1. Kies in het deelvenster **Intune** de optie **Client-apps** > **Apps** onder **Beheren**.
2. Kies in het deelvenster met de lijst met apps de app die u wilt toewijzen en kies **Toewijzingen**.
3. Kies in het deelvenster ***App-naam*** - **Toewijzingen** de optie **Groep toevoegen** en kies in het deelvenster **Groep toevoegen** een **Toewijzingstype**. Kies ook de Azure AD-gebruikers- of apparaatgroepen waaraan u de app wilt toewijzen.
5. Voor elke groep die u hebt geselecteerd, kiest u de volgende instellingen:
    - **Type**: kies of de app **Beschikbaar** is (eindgebruikers kunnen de app installeren vanaf de bedrijfsportal) of **Vereist** (de app wordt automatisch geïnstalleerd).
    - **Licentietype**: kies uit **Gebruikerslicenties** of **Apparaatlicenties**.
6. Als u klaar bent, kiest u **Opslaan**.


>[!NOTE]
>De Beschikbare implementatie-opzet wordt niet ondersteund voor apparaatgroepen. Alleen gebruikersgroepen worden ondersteund. Er wordt een lijst met apps weergegeven die zijn gekoppeld aan een token. Als u een app hebt die aan meerdere VPP-tokens is gekoppeld, wordt dezelfde app meerdere keren weergegeven; eenmaal voor elk token.

## <a name="end-user-prompts-for-vpp"></a>Eindgebruikerprompts voor VPP

De eindgebruiker wordt in een aantal scenario’s gevraagd om de VPP-app te installeren. De volgende tabel beschrijft elke voorwaarde:

| # | Scenario                                | Uitnodigen voor Apple VPP-programma                              | Vraag om app-installatie | Vraag om Apple ID |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | BYOD - gebruiker met licentie                             | J                                                                                               | J                                           | J                                 |
| 2 | Corp - gebruiker met licentie (apparaat niet onder supervisie)     | J                                                                                               | J                                           | J                                 |
| 3 | Corp - gebruiker met licentie (apparaat onder supervisie)         | J                                                                                               | N                                           | J                                 |
| 4 | BYOD – apparaat met licentie                           | N                                                                                               | J                                           | N                                 |
| 5 | CORP - apparaat met licentie (apparaat niet onder supervisie)                           | N                                                                                               | J                                           | N                                 |
| 6 | CORP - apparaat met licentie (apparaat onder supervisie)                           | N                                                                                               | N                                           | N                                 |
| 7 | Kioskmodus (apparaat onder supervisie) - apparaat met licentie | N                                                                                               | N                                           | N                                 |
| 8 | Kioskmodus (apparaat niet onder supervisie) - apparaat met licentie   | --- | ---                                          | ---                                |

> [!Note]  
> Het is niet aan te raden om VPP-apps toe te wijzen aan apparaten in de kioskmodus met de VPP-gebruikerslicenties.

## <a name="revoking-app-licenses"></a>App-licenties intrekken

U kunt alle bijbehorende licenties voor iOS of macOS VPP-apps intrekken op basis van een bepaald apparaat of een bepaalde gebruiker of app.  Maar er zijn wel enkele verschillen tussen iOS-en macOS-platforms. 

### <a name="revoking-app-licenses-on-ios"></a>App-licenties intrekken op iOS
U kunt gebruikers waarschuwen wanneer een app niet meer aan hen is toegewezen. Maar als u een app-licentie intrekt, wordt de desbetreffende VPP-app niet van het apparaat verwijderd. Als u een VPP-app wilt verwijderen en een app-licentie wilt vrijmaken die is toegewezen aan een gebruiker of apparaat, moet u de toewijzingsactie wijzigen in **Verwijderen**. Wanneer u een app verwijdert die is toegewezen aan een gebruiker, maakt Intune de gebruiker of apparaatlicentie vrij en verwijdert de app van het apparaat. Het aantal geregenereerde licenties wordt weergegeven in het knooppunt **Gelicentieerde apps** in de workload **App** van Intune. Zodra een VPP-app is verwijderd en de app-licentie is vrijgemaakt, kunt u de app-licentie toewijzen aan een andere gebruiker of ander apparaat.


### <a name="revoking-app-licenses-on-macos"></a>App-licenties intrekken op macOS
Als u een app-licentie intrekt, wordt de VPP-app niet van het apparaat verwijderd. Wanneer u een app-licentie intrekt die is toegewezen aan een gebruiker, maakt Intune de gebruikers- of apparaatlicentie vrij. De macOS-app waarvan de licentie is ingetrokken, blijft bruikbaar op het apparaat, maar kan pas worden bijgewerkt als een licentie opnieuw wordt toegewezen aan de gebruiker of het apparaat. Volgens Apple worden dergelijke apps na een respijtperiode van 30 dagen verwijderd. Apple biedt echter geen manier om de app via Intune te verwijderen met de toewijzingsactie **Verwijderen**. U kunt de vrijgemaakte app-licentie wel toewijzen aan een andere gebruiker of een ander apparaat.

>[!NOTE]
>Intune haalt alle licenties op voor iOS en macOS VPP-apps die door gebruikers zijn gelicentieerd wanneer een medewerker niet langer bij een bedrijf werkt en geen lid meer is van de AAD-groepen.

## <a name="deleting-vpp-tokens"></a>VPP-tokens verwijderen
<!-- 820879 -->  
U kunt tokens van het Apple Volume Purchasing Program (VPP) verwijderen via de console. Dit kan nodig zijn als er dubbele exemplaren van een VPP-token zijn. Als u een token verwijdert, worden ook alle eraan gekoppelde apps en toewijzingen verwijderd. Als u een token verwijdert, worden de app-licenties echter niet ingetrokken en worden er geen apps verwijderd. 

>[!NOTE]
>Intune kan geen applicenties intrekken nadat een token is verwijderd. 

<!-- 820870 -->  
Als u de licenties van alle VPP-apps van een bepaald VPP-token wilt intrekken, moet u eerst alle app-licenties intrekken die aan het token zijn gekoppeld. Daarna verwijdert u het token.

## <a name="renewing-app-licenses"></a>App-licenties vernieuwen

U kunt een Apple VPP-token vernieuwen door een nieuw token te downloaden uit de Apple Volume Purchase Program-portal en het bestaande token in Intune bij te werken.

## <a name="deleting-a-vpp-app"></a>Een VPP-app verwijderen

U kunt een iOS VPP-app op dit moment niet verwijderen uit Microsoft Intune.

## <a name="assigning-custom-role-permissions-for-vpp"></a>Machtigingen voor aangepaste rollen toewijzen voor VPP

Toegang tot Apple VPP-tokens en VPP-apps kan onafhankelijk worden beheerd met behulp van machtigingen die worden toegewezen aan aangepaste beheerdersrollen in Intune.

* Als u een aangepaste rol in Intune wilt toestaan om Apple VPP-tokens te beheren onder **Client-apps** > **Apple VPP-tokens**, wijst u machtigingen toe voor **Beheerde apps**.
* Als u een aangepaste rol in Intune wilt toestaan om apps die zijn gekocht met iOS VPP-tokens te beheren onder **Client-apps** > **Apps**, wijst u machtigingen toe voor **Mobiele apps**. 

## <a name="additional-information"></a>Aanvullende informatie

Wanneer een gebruiker met een in aanmerking komend apparaat voor de eerste keer probeert een VPP-app op een apparaat te installeren, wordt de gebruiker gevraagd om deel te nemen aan het volume-aankoopprogramma van Apple. Deelname aan het programma moet plaatsvinden voordat de installatie van de app wordt uitgevoerd. De uitnodiging om deel te nemen aan het Apple Volume Purchase Program vereist dat de gebruiker de App Store-app op het iOS- of macOS-apparaat kan gebruiken. Als u een beleid hebt ingesteld om de App Store-app uit te schakelen, werkt de gebruikerslicentie niet voor VPP-apps. U kunt dit probleem oplossen door het beleid te verwijderen, zodat de App Store-app is toegestaan, of door een licentie te verlenen op basis van het apparaat.

Apple biedt rechtstreekse hulp voor het maken en vernieuwen van VPP-tokens. Zie [Inhoud verdelen over uw gebruikers met het Volume Purchase Program (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) als onderdeel van de Apple-documentatie voor meer informatie. 

Als **Toegewezen aan een externe MDM** wordt aangegeven in de Intune-portal, dan moet u (de beheerder) het VPP-token van de externe MDM verwijderen voordat u het VPP-token in Intune gebruikt.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Hoe lang duurt het voordat de portal het aantal licenties heeft bijgewerkt nadat een app is geïnstalleerd of verwijderd van het apparaat?
De licentie wordt binnen een paar uur na het installeren of verwijderen van een app bijgewerkt. Als de eindgebruiker de app van het apparaat verwijdert, is de licentie nog toegewezen aan deze gebruiker of dit apparaat.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Is het mogelijk om een app aan meer apparaten toe te wijzen dan het aantal licenties, en zo ja, in welke omstandigheden?
Ja. De Intune-beheerder kan een app aan meer apparaten toewijzen dan het aantal licenties. Een voorbeeld: een beheerder koopt 100 licenties voor app XYZ en maakt de app vervolgens beschikbaar voor een groep van 500 leden. De licentie wordt aan de eerste 100 leden (gebruikers of apparaten) toegewezen; de rest van de leden kunnen de licentie niet toegewezen krijgen.

### <a name="how-frequently-does-intune-sync-vpp-tokens-with-apple"></a>Hoe vaak worden VPP-tokens met Apple gesynchroniseerd door Intune?
VPP-tokens en -licenties worden tweemaal per dag met Apple gesynchroniseerd door Intune. De Intune-beheerder kan een handmatige synchronisatie starten onder **Client apps** > **Apple VPP-tokens**.

## <a name="next-steps"></a>Volgende stappen

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.
