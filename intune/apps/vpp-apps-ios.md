---
title: Apps beheren die zijn gekocht via het volume-aankoopprogramma van Apple
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u apps kunt synchroniseren die u via het volumeaankoopprogramma in de App Store voor iOS en macOS hebt gekocht, hoe u deze apps in Microsoft Intune kunt beheren en hoe u het gebruik ervan kunt bijhouden.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/17/2019
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
ms.openlocfilehash: 0bc511669ec8a88523581b3afbcca161d5208934
ms.sourcegitcommit: de663ef5f3e82e0d983899082a7f5b62c63f24ef
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2020
ms.locfileid: "75956210"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>iOS- en macOS-apps beheren die zijn aangeschaft via het Apple Volume Purchase Program met Microsoft Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Bij Apple kunt u meerdere licenties aanschaffen voor een app die u wilt gebruiken in uw organisatie op iOS- en macOS-apparaten met [Apple Business Manager](https://business.apple.com/) of [Apple School Manager](https://school.apple.com/). U kunt uw gegevens over volume-aankopen vervolgens synchroniseren met Intune en het gebruik bijhouden van uw via het volume-aankoopprogramma gekochte apps. Door app-licenties aan te schaffen kunt u apps binnen uw bedrijf op efficiënte wijze beheren en het eigendom en beheer van aangeschafte apps in handen houden. 

Microsoft Intune kan u op de volgende manieren helpen bij het beheren via dit programma aangeschafte apps:

- Het synchroniseren van locatietokens die u van Apple Business Manager downloadt.
- Bijhouden hoeveel licenties er beschikbaar zijn en zijn gebruikt voor aangeschafte apps.
- Helpt u bij het installeren van apps tot het aantal licenties dat u bezit.

Verder kunt u met Intune boeken die u hebt gekocht via Apple Business Manager synchroniseren, beheren en toewijzen op iOS-apparaten. Zie [E-boeken in iOS beheren die u via een volume-aankoopprogramma hebt aangeschaft](vpp-ebooks-ios.md) voor meer informatie.

## <a name="what-are-location-tokens"></a>Wat zijn locatietokens?
Locatietokens worden ook wel VPP-tokens (volume Purchase Program) genoemd. Deze tokens worden gebruikt voor het toewijzen en beheren van licenties die zijn gekocht via Apple Business Manager. Inhoudsbeheerders kunnen licenties kopen en koppelen aan locatietokens waarvoor ze machtigingen hebben in Apple Business Manager. Deze locatietokens worden vervolgens gedownload van Apple Business Manager en geüpload in Microsoft Intune. Microsoft Intune ondersteunt het uploaden van meerdere locatietokens per tenant. Elke token is één jaar geldig.

## <a name="how-are-purchased-apps-licensed"></a>Hoe worden gekochte apps gelicentieerd?
Aangeschafte apps kunnen aan groepen worden toegewezen met behulp van twee typen licenties die Apple biedt voor iOS-en macOS-apparaten.

|   | Apparaatlicenties | Gebruikerslicenties |
|-----|------------------|----------------|
| **Aanmelden bij de App Store** | Niet vereist. | Elke eindgebruiker moet een unieke Apple-ID gebruiken wanneer deze wordt gevraagd zich aan te melden bij App Store. |
| **Apparaatconfiguratie blokkeert de toegang tot App Store** | Apps kunnen worden geïnstalleerd en bijgewerkt met behulp van Bedrijfsportal. | Voor de uitnodiging om lid te worden van Apple VPP is toegang tot App Store vereist. Als u een beleid hebt ingesteld om App Store uit te schakelen, werkt de gebruikerslicentie voor VPP-apps niet. |
| **Automatische app-updates** | Zoals geconfigureerd door de Intune-beheerder in de instellingen voor Apple VPP-tokens, waarbij het **toewijzingstype** van de app **vereist** is. <br> <br> Als het **toewijzingstype** **beschikbaar voor ingeschreven apparaten** is, kunnen beschikbare app-updates worden geïnstalleerd vanuit Bedrijfsportal. | Zoals geconfigureerd door de eindgebruiker in de persoonlijke instellingen voor App Store. Dit kan niet worden beheerd door de Intune-beheerder. |
| **Gebruikersinschrijving** | Niet ondersteund. | Ondersteund met beheerde Apple-id's. |
| **Books** | Niet ondersteund. | Ondersteund. |
| **Gebruikte licenties** | 1 licentie per apparaat. De licentie is gekoppeld aan het apparaat. | 1 licentie voor maximaal vijf apparaten met dezelfde persoonlijke Apple-ID. De licentie is gekoppeld aan de gebruiker. <br> <br> Een eindgebruiker die is gekoppeld aan een persoonlijke Apple-ID en een beheerde Apple-ID in Intune gebruikt twee app-licenties.|
| **Licentiemigratie** | Apps kunnen op de achtergrond worden gemigreerd van gebruikers- naar apparaatlicenties. | Apps kunnen niet van apparaat- naar gebruikerslicenties worden gemigreerd. |

> [!NOTE]  
> In Bedrijfsportal worden geen apps met apparaatlicenties weergegeven op Gebruikersinschrijving-apparaten, omdat alleen apparaten met gebruikerslicenties kunnen worden geïnstalleerd op Gebruikersinschrijving-apparaten.

## <a name="what-app-types-are-supported"></a>Welke app-typen worden ondersteund?
U kunt zowel openbare als persoonlijke apps aanschaffen en distribueren met behulp van Apple Business Manager.
- **Store-apps:** Met Apple Business Manager kunnen inhoudsbeheerders zowel gratis als betaalde apps kopen die beschikbaar zijn in de App Store.
- **Aangepaste apps:** Met Apple Business Manager kunnen inhoudsbeheerders ook aangepaste apps kopen die privé beschikbaar worden gesteld aan uw organisatie. Deze apps worden door ontwikkelaars met wie u rechtstreeks samenwerkt op de specifieke behoeften van uw organisatie afgestemd. Meer informatie over het [distribueren van aangepaste apps](https://developer.apple.com/business/custom-apps/).

## <a name="prerequisites"></a>Vereisten
- Een [Apple Business Manager](https://business.apple.com/)- of [Apple School Manager](https://school.apple.com/)-account voor uw organisatie. 
- Aangeschafte app-licenties die zijn toegewezen aan een of meer locatietokens. 
- Gedownloade locatietokens. 

> [!IMPORTANT]
> - Een locatietoken kan slechts met één oplossing voor apparaatbeheer tegelijk worden gebruikt. Voordat u begint met het gebruik van aangeschafte apps met Intune, verwijdert u eventuele bestaande locatietokens die zijn gebruikt bij toepassingen voor het beheren van mobiele apparaten (MDM) van andere leveranciers. 
> - Een locatietoken wordt alleen ondersteund voor gebruik op één Intune-tenant tegelijk. Gebruik hetzelfde locatietoken niet voor meerdere Intune-tenants.
> - Intune synchroniseert de locatietokens standaard twee keer per dag met Apple. U kunt vanuit Intune op elk gewenst moment een handmatige synchronisatie starten.
> - Nadat u het locatietoken hebt geïmporteerd in Intune, kunt u hetzelfde token niet in een andere oplossing voor apparaatbeheer importeren. Dit kan leiden tot verlies van licentietoewijzngen en gebruikersrecords.

## <a name="migrate-from-volume-purchase-program-vpp-to-apps-and-books"></a>Migreren van het Volume Purchase Program (VPP) naar Apps en Books
Als uw organisatie nog niet is gemigreerd naar Apple Business Manager of Apple School Manager, raadpleegt u de [richtlijnen van Apple over het migreren naar Apps en Books](https://support.apple.com/HT208257) voordat u doorgaat met het beheren van aangeschafte apps in Intune.

> [!IMPORTANT]
> - Migreer voor de beste migratie-ervaring slechts één VPP-koper per locatie. Als elke koper naar een unieke locatie wordt gemigreerd, worden alle licenties (toegewezen en niet-toegewezen) verplaatst naar Apps en Books.
> - Verwijder het bestaande verouderde VPP-token in Intune niet, evenmin als apps en toewijzingen die aan het bestaande verouderde VPP-token in Intune zijn gekoppeld. Door deze acties moeten alle app-toewijzingen opnieuw worden gemaakt in Intune.

U kunt als volgt bestaande, gekochte VPP-inhoud en -tokens migreren naar Apps en Books in Apple Business Manager of Apple School Manager:

1. Nodig VPP-kopers uit om lid te worden van uw organisatie, en laat elke gebruiker een unieke locatie selecteren. 
2. Zorg ervoor dat alle VPP-kopers binnen uw organisatie stap 1 hebben voltooid voordat u doorgaat.
3. Controleer of alle gekochte apps en licenties zijn gemigreerd naar Apps en Books in Apple Business Manager of Apple School Manager.
4. Download een nieuw locatietoken via **Apple Business (of School) Manager** > **Instellingen** > **Apps en Books** > **Mijn servertokens**.
5. Ga voor het bijwerken van een locatietoken in het Beheercentrum voor Microsoft Eindpuntbeheer naar **Tenant-beheer** > **Connectors en tokens** > **Apple VPP-tokens** en synchroniseer het token.

## <a name="upload-an-apple-vpp-or-location-token"></a>Een Apple VPP- of locatietoken uploaden

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecteer **Tenantbeheer** > **Connectors en tokens** > **Apple VPP-tokens**.
4. Selecteer **Maken** in het deelvenster met de lijst VPP-tokens.
5. Geef in het deelvenster **VPP-token maken** de volgende gegevens op:
    - **VPP-tokenbestand**: registreer u bij Apple Business Manager of Apple School Manager als u dit nog niet hebt gedaan. Nadat u bent aangemeld, downloadt u het Apple VPP-token voor uw account en selecteert u dit hier.
    - **Apple ID**: voer de beheerde Apple-id in van het account dat aan het geüploade token is gekoppeld.
    - **Controle over token van andere MDM**: als u deze optie op **Ja** instelt, kan het token van een andere MDM-oplossing opnieuw worden toegewezen aan Intune.
    - **Tokennaam**: een beheerveld voor het instellen van de tokennaam.    
    - **Land/regio**: selecteer VPP-store voor uw land/regio.  Intune synchroniseert VPP-apps voor alle landinstellingen uit de opgegeven store uit het land of de regio waar de VPP geldt.
        > [!WARNING]  
        > Als u het land of de regio wijzigt, worden de metagegevens en App Store-URL van de apps bijgewerkt bij de volgende synchronisatie met de Apple-service voor de apps die met deze token zijn gemaakt. De app wordt niet bijgewerkt als deze niet bestaat in de store van het nieuwe land of de nieuwe regio.

    - **Type VPP-account**: u hebt de keuze uit **Bedrijven** of **Onderwijs**.
    - **Automatische updates voor apps**: kies **Aan** of **Uit** om automatische updates in of uit te schakelen. Wanneer deze zijn ingeschakeld, detecteert Intune updates voor de VPP-app in de app store en pusht ze automatisch naar het apparaat als dit incheckt. 
        
        > [!NOTE] 
        > Met automatische updates voor Apple VPP-apps worden alleen apps die zijn geïmplementeerd met de installatie-intentie **Vereiste**, automatisch bijgewerkt. Voor apps die zijn geïmplementeerd met de installatie-intentie **Beschikbaar**, wordt met de automatische update voor de IT-beheerder een statusbericht gegenereerd waarin staat dat een nieuwe versie van de app beschikbaar is. Dit statusbericht kan worden weergegeven door de app te selecteren, Apparaatinstallatiestatus te selecteren en de Statusdetails te controleren.  

    - **Ik geef Microsoft toestemming om gebruikers- en apparaatgegevens naar Apple te verzenden.** - U moet **Ik ga akkoord** selecteren om door te gaan. Zie [Gegevens die Intune naar Apple verzendt](~/protect/data-intune-sends-to-apple.md) om te kijken welke gegevens Microsoft naar Apple verzendt.

6. Selecteer **Maken** wanneer u klaar bent. Het token wordt weergegeven in het deelvenster met de lijst met tokens.

## <a name="synchronize-a-vpp-token"></a>Een VPP-token synchroniseren
U kunt de app-namen, metagegevens en licentiegegevens voor uw aangeschafte apps in Intune synchroniseren door **Synchroniseren** te kiezen voor een geselecteerd token.

## <a name="assign-a-volume-purchased-app"></a>Een app toewijzen die is gekocht via het volume-aankoopprogramma

1. Selecteer **Apps** > **Alle apps**.
2. Kies in het deelvenster met de lijst met apps de app die u wilt toewijzen en kies **Toewijzingen**.
3. Kies in het deelvenster **App-naam** - **Toewijzingen** de optie **Groep toevoegen** en kies in het deelvenster **Groep toevoegen** een **Toewijzingstype**. Kies ook de Azure AD-gebruikers- of apparaatgroepen waaraan u de app wilt toewijzen.
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
| 1 | BYOD – gebruiker met licentie (geen apparaat voor gebruikersregistratie)                             | J                                                                                               | J                                           | J                                 |
| 2 | Corp - gebruiker met licentie (apparaat niet onder supervisie)     | J                                                                                               | J                                           | J                                 |
| 3 | Corp - gebruiker met licentie (apparaat onder supervisie)         | J                                                                                               | N                                           | J                                 |
| 4 | BYOD – apparaat met licentie                           | N                                                                                               | J                                           | N                                 |
| 5 | CORP - apparaat met licentie (apparaat niet onder supervisie)                           | N                                                                                               | J                                           | N                                 |
| 6 | CORP - apparaat met licentie (apparaat onder supervisie)                           | N                                                                                               | N                                           | N                                 |
| 7 | Kioskmodus (apparaat onder supervisie) - apparaat met licentie | N                                                                                               | N                                           | N                                 |
| 8 | Kioskmodus (apparaat niet onder supervisie) - apparaat met licentie   | --- | ---                                          | ---                                |

> [!Note]  
> Het is niet aan te raden om VPP-apps aan apparaten in de kioskmodus toe te wijzen met gebruikerslicenties.

## <a name="revoking-app-licenses"></a>App-licenties intrekken

U kunt alle bijbehorende licenties voor iOS of macOS VPP-apps intrekken op basis van een bepaald apparaat of een bepaalde gebruiker of app.  Maar er zijn wel enkele verschillen tussen iOS-en macOS-platforms. 

|   | iOS | macOS |
|-----|------------------|----------------|
| **App-toewijzing verwijderen** | Wanneer u een app verwijdert die is toegewezen aan een gebruiker, maakt Intune de gebruiker of apparaatlicentie vrij en verwijdert de app van het apparaat. | Wanneer u een app verwijdert die is toegewezen aan een gebruiker, maakt Intune de gebruikers- of apparaatlicentie vrij. De app wordt niet van het apparaat verwijderd. |
| **App-licentie intrekken** | Als u een app-licentie intrekt, wordt de app-licentie van de gebruiker of het apparaat vrijgemaakt. U moet de toewijzing wijzigen in **Verwijderen** om de app van het apparaat te verwijderen. | Als u een app-licentie intrekt, wordt de app-licentie van de gebruiker of het apparaat vrijgemaakt. De macOS-app waarvan de licentie is ingetrokken, blijft bruikbaar op het apparaat, maar kan pas worden bijgewerkt als een licentie opnieuw wordt toegewezen aan de gebruiker of het apparaat. Volgens Apple worden dergelijke apps na een respijtperiode van 30 dagen verwijderd. Apple biedt echter geen manier om de app via Intune te verwijderen met de toewijzingsactie Verwijderen.

>[!NOTE]
> - Intune maakt app-licenties vrij wanneer een werknemer niet langer bij een bedrijf werkt en geen lid meer is van de AAD-groepen.
> - Wanneer u een aangeschafte app de intentie **Verwijderen** toewijst in Intune, wordt zowel de licentie vrijgemaakt als de app verwijderd.
> - App-licenties worden niet vrijgemaakt wanneer een apparaat Intune-beheer wordt verwijderd. 

## <a name="deleting-vpp-tokens"></a>VPP-tokens verwijderen
<!-- 820879 -->  
U kunt tokens van het Apple Volume Purchasing Program (VPP) verwijderen via de console. Dit kan nodig zijn als er dubbele exemplaren van een VPP-token zijn. Als u een token verwijdert, worden ook alle eraan gekoppelde apps en toewijzingen verwijderd. Als u een token verwijdert, worden de app-licenties echter niet ingetrokken en worden er geen apps verwijderd. 

>[!NOTE]
>Intune kan geen applicenties intrekken nadat een token is verwijderd. 

<!-- 820870 -->  
Als u de licenties van alle VPP-apps van een bepaald VPP-token wilt intrekken, moet u eerst alle app-licenties intrekken die aan het token zijn gekoppeld. Daarna verwijdert u het token.

## <a name="renewing-app-licenses"></a>App-licenties vernieuwen

U kunt een Apple VPP-token vernieuwen door een nieuw token te downloaden van Apple Business Manager of Apple School Manager en het bestaande token in Intune bij te werken.

## <a name="deleting-a-vpp-app"></a>Een VPP-app verwijderen

U kunt een iOS VPP-app op dit moment niet verwijderen uit Microsoft Intune.

## <a name="assigning-custom-role-permissions-for-vpp"></a>Machtigingen voor aangepaste rollen toewijzen voor VPP

Toegang tot Apple VPP-tokens en VPP-apps kan onafhankelijk worden beheerd met behulp van machtigingen die worden toegewezen aan aangepaste beheerdersrollen in Intune.

* Als u een aangepaste rol in Intune wilt toestaan om Apple VPP-tokens te beheren onder **Apps** > **Apple VPP-tokens**, wijst u machtigingen toe voor **Beheerde apps**.
* Als u een aangepaste rol in Intune wilt toestaan om apps die zijn gekocht met iOS VPP-tokens, te beheren onder **Apps** > **Alle apps**, wijst u machtigingen toe voor **Mobiele apps**. 

## <a name="additional-information"></a>Aanvullende informatie

Apple biedt rechtstreekse hulp voor het maken en vernieuwen van VPP-tokens. Zie [Inhoud verdelen over uw gebruikers met het Volume Purchase Program (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) als onderdeel van de Apple-documentatie voor meer informatie. 

Als **Toegewezen aan een externe MDM** wordt aangegeven in de Intune-portal, dan moet u (de beheerder) het VPP-token van de externe MDM verwijderen voordat u het VPP-token in Intune gebruikt.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

### <a name="how-many-tokens-can-i-upload"></a>Hoeveel tokens kan ik uploaden?
U kunt maximaal 3000 tokens uploaden in Intune.

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Hoe lang duurt het voordat de portal het aantal licenties heeft bijgewerkt nadat een app is geïnstalleerd of verwijderd van het apparaat?
De licentie wordt binnen een paar uur na het installeren of verwijderen van een app bijgewerkt. Als de eindgebruiker de app van het apparaat verwijdert, is de licentie nog toegewezen aan deze gebruiker of dit apparaat.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Is het mogelijk om een app aan meer apparaten toe te wijzen dan het aantal licenties, en zo ja, in welke omstandigheden?
Ja. De Intune-beheerder kan een app aan meer apparaten toewijzen dan het aantal licenties. Een voorbeeld: een beheerder koopt 100 licenties voor app XYZ en maakt de app vervolgens beschikbaar voor een groep van 500 leden. De licentie wordt aan de eerste 100 leden (gebruikers of apparaten) toegewezen; de rest van de leden kunnen de licentie niet toegewezen krijgen.


## <a name="next-steps"></a>Volgende stappen

Zie [How to monitor apps](apps-monitor.md) (Apps controleren) voor meer informatie over het controleren van app-toewijzingen.

Zie [Problemen met apps oplossen](~/apps/troubleshoot-app-install.md) voor informatie over het oplossen van app-gerelateerde problemen.
