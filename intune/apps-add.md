---
title: Apps toevoegen aan Microsoft Intune
titlesuffix: ''
description: Ontdek hoe u apps toevoegt aan Microsoft Intune zodat u ook apps kunt toewijzen aan gebruikers en apparaten. Intune biedt ondersteuning voor een breed scala aan app-typen.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b4e87c36c3aa0aaeae1e1bf265902100612db15
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Een app toevoegen aan Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Voordat u apps kunt toewijzen, bewaken, configureren en beveiligen, moet u ze aan Microsoft Intune toevoegen.

De gebruikers van apps en apparaten in uw bedrijf (het personeel) hebben mogelijk verschillende vereisten voor apps. Voordat u apps toevoegt aan Intune en u ze beschikbaar maakt voor uw personeel, moet u enkele app-grondbeginselen controleren en begrijpen. U moet weten welke verschillende typen apps er beschikbaar zijn voor Intune. U moet de app-vereisten controleren, zoals welke platforms en mogelijkheden er nodig zijn voor uw personeel. U moet daarnaast bepalen of u Intune gaat gebruiken voor het beheren van de apparaten (en de apps), of dat u Intune de apps laat beheren zonder dat de apparaten worden beheerd. U moet bepalen welke personeelsleden verschillende apps en verschillende mogelijkheden nodig hebben. U kunt aan de hand van de informatie in dit artikel snel aan de slag.

## <a name="app-types-in-microsoft-intune"></a>App-typen in Microsoft Intune

Intune biedt ondersteuning voor een breed scala aan app-typen. De beschikbare opties verschillen per app-type. In Intune kunt u deze typen apps toevoegen en toewijzen:

| **App-typen**                                     | **Installatie**                                                                  | **Updates**                       |
|------------------------------------------ |----------------------------------------------------------------------------   |---------------------------    |
| Apps uit de Store (Store-apps)          | De app wordt door Intune op het apparaat geïnstalleerd                                       | App-updates worden automatisch uitgevoerd     |
| Apps die intern zijn ontwikkeld (line-of-business)  | De app wordt door Intune op het apparaat geïnstalleerd (u levert het installatiebestand)    | U moet de app bijwerken       |
| Apps die zijn ingebouwd (ingebouwde apps)    | De app wordt door Intune op het apparaat geïnstalleerd                                       | App-updates worden automatisch uitgevoerd     |
| Apps op internet (webkoppeling)                | Er wordt door Intune een snelkoppeling gemaakt naar de web-app op het beginscherm van het apparaat          | App-updates worden automatisch uitgevoerd     |

### <a name="specific-app-type-details"></a>Details specifieke app-typen
 
De volgende tabel bevat de specifieke app-typen en informatie over hoe u deze kunt toevoegen via de blade **App toevoegen** in Microsoft Intune:

| **Specifiek app-type**                         | **Algemeen type**             | **App-specifieke procedures**                                                                                                                                                 |
|---------------------------------------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android Store-apps                        | Store-app                  | Selecteer **Android** als het **type app** en voer de Google Play Store-URL in voor de app.                                                                                       |
| iOS Store-apps                            | Store-app                  | Selecteer **iOS** als het **type app**, zoek de app en selecteer de app in Intune.                                                                                     |
| Windows Phone 8.1 Store-apps              | Store-app                  | Selecteer **Windows Phone 8.1** als het **type app** en voer de URL van de Microsoft Store in voor de app.                                                                               |
| Microsoft Store-apps                      | Store-app                  | Selecteer **Windows** als het **type app** en voer de URL van de Microsoft Store in voor de app.                                                                                         |
| Android for Work-apps                     | Store-app                  | Zoek de Android for Work-app in de Google Play for Work Store en keur deze goed.                                                                                        |
| Office 365-apps voor Windows 10            | Store-app (Office 365)     | Selecteer **Windows 10** bij **Office 365-suite** als het **type app** en selecteer dan de Office 365-app die u wilt installeren.                                                |
| Office 365-apps voor macOS                 | Store-app (Office 365)     | Selecteer **macOS** bij **Office 365-suite** als het **type app** en selecteer vervolgens de Office 365-app-suite.                                                                     |
| Android LOB-apps (Line-Of-Business)       | LOB-apps (Line-Of-Business) | Selecteer **Line-Of-Business**-app als het **type app**, selecteer het **app-pakketbestand** en voeg vervolgens een Android-installatiebestand toe met de extensie **.apk**.                    |
| iOS LOB-apps (Line-of-Business)           | LOB-apps (Line-Of-Business) | Selecteer **Line-Of-Business**-app als het **type app**, selecteer het **app-pakketbestand** en voeg vervolgens een iOS-installatiebestand toe met de extensie **.ipa**.                        |
| Windows Phone LOB-apps (Line-Of-Business) | LOB-apps (Line-Of-Business) | Selecteer **Line-Of-Business**-app als het **type app**, selecteer het **app-pakketbestand** en voeg vervolgens een iOS-installatiebestand toe met de extensie **.xap**.                        |
| Windows LOB-apps (Line-Of-Business)       | LOB-apps (Line-Of-Business) | Selecteer Line-Of-Business-app als het type app, selecteer het app-pakketbestand en voeg vervolgens een iOS-installatiebestand toe met de extensie **.msi**, **.appx** of **.appxbundle**. |
| Ingebouwde iOS-app                          | Ingebouwde app               | Selecteer **Ingebouwde app** als het **type app** en selecteer vervolgens de ingebouwde app in de lijst beschikbare apps.                                                                  |
| Ingebouwde Android-app                      | Ingebouwde app               | Selecteer **Ingebouwde app** als het **type app** en selecteer vervolgens de ingebouwde app in de lijst beschikbare apps.                                                                  |
| Web-apps                                  | Web-app                    | Selecteer **Webkoppeling** als het **type app** en voer een geldige URL in die verwijst naar de web-app.                                                                                        |

   
U kunt in Microsoft Intune apps toevoegen via **Mobiele apps** > **Apps** > **Toevoegen**. De blade **App toevoegen** wordt weergegeven. Hier kunt u het **type app** selecteren. 

>[!TIP]
> Een LOB-app is een app die u vanaf een app-installatiebestand toevoegt. Als u bijvoorbeeld een LOB-app voor iOS wilt installeren, voegt u de toepassing toe door op de blade **App toevoegen** de optie **LOB-app** als het **app-type** te kiezen. Selecteer vervolgens het app-pakketbestand (met de extensie .ipa). Deze app-typen worden doorgaans intern ontwikkeld.

## <a name="assess-app-requirements"></a>De app-vereisten beoordelen
Als IT-beheerder moet u niet alleen vaststellen welke apps door de groep moeten worden gebruikt, maar moet u ook bepalen over welke functies elke groep en subgroep moet beschikken. U moet voor elke app bepalen welke platformen moeten worden gebruikt, welke gebruikersgroepen de app nodig hebben, welk configuratiebeleid van toepassing is voor die groepen en welk beveiligingsbeleid moet worden toegepast.  

Daarnaast moet u bepalen of u zich moet richten op Mobile Device Management (MDM) of alleen op Mobile Application Management (MAM). Het apparaat beheren met Intune (Mobile Device Management) is handig wanneer:
- Gebruikers over een Wi-Fi- of VPN-bedrijfsconnectiviteitsprofiel moeten beschikken om te kunnen werken.
- Er voor de gebruikers een aantal apps naar hun apparaat moet worden gepusht.
- Uw organisatie moet voldoen aan de regelgeving of andere beleidsregels ten aanzien van specifieke MDM-beheerelementen (Mobile Device Management), zoals de beveiliging of versleuteling.

Apps beheren met Intune (Mobile Application Management) zonder het apparaat te beheren, is nuttig wanneer:
- U wilt toestaan dat gebruikers hun eigen apparaat gebruiken (BYOD).
- U de gebruikers eenmalig via een pop-uptekst wilt laten weten dat MAM-beveiliging van kracht is, in plaats van continu meldingen op apparaatniveau te verzenden.
- U wilt voldoen aan beleidsregels waarvoor minder beheerfuncties op persoonlijke apparaten nodig zijn. U wilt bijvoorbeeld de bedrijfsgegevens voor de apps beheren en niet de bedrijfsgegevens voor het hele apparaat.

Raadpleeg [MDM en MAM vergelijken](byod-technology-decisions.md) voor meer informatie.

### <a name="determine-who-will-use-the-app"></a>Bepalen wie de app gaat gebruiken

Wanneer u bepaalt welke apps uw personeel nodig heeft, moet u nadenken over welke verschillende gebruikersgroepen verschillende apps gebruiken. Als u weet welke verschillende groepen er zijn, komt dat ook van pas na het toevoegen van een app. Nadat u een app hebt toegevoegd, wijst u een groep gebruikers toe die de app mag gebruiken. U moet eerst op basis van de vertrouwelijkheid van de gegevens in de app bepalen welke groep toegang mag krijgen tot de app. U moet mogelijk bepaalde soorten rollen binnen uw organisatie opnemen of uitsluiten. Het verkoopteam heeft misschien alleen bepaalde LOB-apps nodig, terwijl medewerkers die zich bezighouden met engineering, financiën, HR of juridische aangelegenheden mogelijk geen LOB-apps gebruiken. Daarnaast is er voor het verkoopteam mogelijk aanvullende gegevensbeveiliging nodig en moet het team op hun mobiele apparaten toegang hebben tot interne bedrijfsservices. U moet bepalen hoe deze groep met de app verbinding maakt met de resources. Zijn de gegevens die worden opgehaald met de app in de cloud of op een on-premises server opgeslagen? En hoe maken de gebruikers met de app verbinding met de resources. Intune biedt ook ondersteuning voor het inschakelen van beveiligde toegang tot mobiele apps die worden gebruikt om on-premises gegevens te openen, zoals een line-of-business-app. Dit soort toegang vindt meestal plaats met behulp van [door Intune beheerde certificaten](certificates-configure.md) voor toegangsbeheer in combinatie met een standaard VPN-gateway of proxy in het perimeternetwerk, zoals de Microsoft Azure Active Directory-toepassingsproxy. U kunt met de [App Wrapping Tool en App SDK](apps-prepare-mobile-application-management.md) van Intune de opgehaalde gegevens binnen de LOB-app houden, zodat de bedrijfsgegevens niet worden doorgegeven aan consumenten-apps of -services.

In de [Intune-handleiding voor implementatieplanning, ontwerp en implementatie](planning-guide.md) kunt u lezen hoe u bepaalt welke organisatiegroepen gekoppeld zijn aan elk gebruiksscenario en ondergeschikt gebruiksscenario voor apps. Raadpleeg [Apps aan groepen toewijzen met Microsoft Intune](apps-deploy.md) voor meer informatie over het toewijzen van apps aan groepen.

### <a name="determine-the-type-of-app-for-your-solution"></a>Het type app voor uw oplossing bepalen

U kunt kiezen uit de volgende app-typen:
- **Apps uit de Store**: een Store-app is een app die naar de Microsoft Store, iOS Store of Android Store is geüpload. De aanbieder van de Store-app onderhoudt de app en levert hiervoor updates. U selecteert de app in de lijst van de Store en voegt deze met behulp van Intune toe als een beschikbare app voor uw gebruikers.
- **Apps die intern zijn ontwikkeld (line-of-business)**: apps die intern zijn gemaakt, worden LOB-apps (line-of-business) genoemd. De functionaliteit van dit type app is gemaakt voor een van de platformen die door Intune worden ondersteund, zoals Windows, iOS of Android. Uw organisatie maakt en levert u updates als een afzonderlijk bestand. U levert updates van de app aan gebruikers door de updates via Intune toe te voegen en te implementeren.
- **Apps op internet**: een web-app is een client-/servertoepassing. De server levert de web-app, waaronder de gebruikersinterface, inhoud en functionaliteit. Bovendien bieden moderne webhostingplatformen meestal beveiliging, taakverdeling en andere voordelen. Dit type app wordt afzonderlijk onderhouden op internet. U gebruikt Intune om naar dit type app te verwijzen. U wijst ook de groepen gebruikers toe die toegang krijgen tot deze app. Houd er rekening mee dat Android geen ondersteuning biedt voor web-apps.

Wanneer u bepaalt welke apps door uw organisatie moeten worden gebruikt, houd er dan rekening mee hoe deze apps worden geïntegreerd met cloudservices, welke gegevens worden opgehaald met de apps, of de apps beschikbaar zijn voor BYOD-gebruikers en of internettoegang nodig is voor de apps.

Raadpleeg **Apps** in het gedeelte **Functievereisten** van [Een ontwerp maken](planning-guide-design.md#feature-requirements) om te lezen hoe u bepaalt welk type apps uw organisatie nodig heeft.

### <a name="understanding-app-management-and-protection-policies"></a>Informatie over app-beheer en beveiligingsbeleid
U kunt in Intune de functionaliteit wijzigen van apps die u implementeert, zodat deze in overeenstemming zijn met het nalevings- en beveiligingsbeleid van uw bedrijf. Met dit beheer kunt u bepalen hoe de bedrijfsgegevens worden beveiligd. Door Intune beheerde apps worden ingeschakeld met een uitgebreide reeks van beveiligingsbeleidsregels voor mobiele toepassingen, zoals:

- De beperking van functies voor kopiëren en plakken en opslaan als
- De configuratie van webkoppelingen zodat deze in de Intune-app Managed Browser worden geopend
- De inschakeling van het gebruik van meerdere identiteiten en voorwaardelijke toegang op app-niveau

Voor apps die door Intune worden beheerd, kan ook app-beveiliging worden ingeschakeld zonder dat een apparaat hoeft te worden ingeschreven. U kunt op die manier beleid voor de preventie van gegevensverlies toepassen zonder dat u het apparaat van de gebruiker hoeft te beheren. Daarnaast kunt u het beheer van mobiele apps in uw mobiele apps en LOB-apps opnemen via de Intune App SDK en de App Wrapping Tool. Raadpleeg [Overzicht van de Intune App SDK](app-sdk.md) voor meer informatie over deze hulpprogramma's.

### <a name="understanding-licensed-apps"></a>Informatie over apps met licentie
Naast het feit dat er verschillende typen apps zijn, zoals web-apps, Store-apps en LOB-apps, moet u ook rekening houden met het verschil tussen apps die zijn aangeschaft via een volumeaankoopprogramma en apps met licentie, bijvoorbeeld:     
- **Apple-volumeaankoopprogramma voor bedrijven (iOS en MacOS)**: u kunt in iOS App Store meerdere licenties aanschaffen voor een app die u in uw bedrijf wilt uitvoeren. Door meerdere exemplaren aan te schaffen, kunt u apps in uw bedrijf efficiënt beheren. Raadpleeg [iOS-apps beheren die zijn aangeschaft via een volumeaankoopprogramma met Microsoft Intune](vpp-apps-ios.md) voor meer informatie.
- **Android for Work (Android)**: u wijst apps aan Android for Work-apparaten op een andere manier toe dan aan standaard-Android-apparaten. Alle apps die u installeert voor Android for Work, zijn afkomstig uit de Google Play for Work-store. U meldt zich aan bij de store, bladert naar de gewenste apps en keurt deze goed. De app wordt vervolgens weergegeven in het knooppunt Apps met licentie van Azure Portal. Hier kunt u de toewijzing van de app op dezelfde manier beheren als toewijzingen van andere apps.
- **Microsoft Store voor Bedrijven (Windows 10)**: in Microsoft Store voor Bedrijven kunt u apps vinden en afzonderlijk of in bulk aanschaffen voor uw organisatie. Als u Windows Store voor Bedrijven aan Microsoft Intune koppelt, kunt u apps die zijn aangeschaft via een volume-aankoopprogramma, beheren in de Azure-portal. Raadpleeg [Apps die u hebt aangeschaft in Microsoft Store voor Bedrijven, beheren met Microsoft Intune](windows-store-for-business.md) voor meer informatie.

## <a name="before-you-add-apps"></a>Voordat u apps toevoegt
Overweeg de volgende punten voordat u begint met het toevoegen en toewijzen van apps.

- Wanneer u een app vanuit een App Store toevoegt en toevoegt, moeten eindgebruikers beschikken over een account bij die Store om de app te kunnen installeren.
- Sommige apps of items die u toewijst, zijn mogelijk afhankelijk van ingebouwde iOS-apps. Als u bijvoorbeeld een boek uit de iOS Store toewijst, moet de app iBooks op het apparaat staan. Als u de ingebouwde app iBooks hebt verwijderd, kunt u Intune niet gebruiken om dit te herstellen.

## <a name="cloud-storage-space"></a>Cloudopslag
Alle apps die u maakt met het installatietype van het software-installatieprogramma (bijvoorbeeld een Line-Of-Business-app), worden verpakt en geüpload naar Intune-cloudopslag. Een proefabonnement op Intune omvat 2 GB (gigabyte) cloudopslag, die wordt gebruikt voor het opslaan van beheerde apps en updates. Een volledig abonnement omvat 20 GB aan opslagruimte.

U kunt extra opslagruimte kopen voor Intune met uw oorspronkelijke aankoop-methode. Als u hebt betaald via een factuur of met een creditcard, gaat u naar de [Beheerportal abonnementen](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions). Neem anders contact op met uw partner of verkoopassistent.

De vereisten voor cloudopslag zijn als volgt:

-   Alle app-installatiebestanden moeten zich in dezelfde map bevinden.
-   De maximale bestandsgrootte voor elk bestand dat u uploadt, is 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Categorieën voor apps maken en bewerken

App-categorieën kunnen worden gebruikt om apps te sorteren, zodat gebruikers deze sneller kunnen vinden in de bedrijfsportal. U kunt een of meer categorieën toewijzen aan een app, bijvoorbeeld **Ontwikkelaars-apps** of **Communicatie-apps**.
Als u een app aan Intune toevoegt, kunt u de gewenste categorie selecteren. Aan de hand van de platformenpecifieke onderwerpen kunt u een app toevoegen en categorieën toewijzen. Als u uw eigen categorieën wilt maken en bewerken, gebruikt u de volgende procedure:

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies **Mobiele apps** op de blade **Intune**.
4. In de workload **Mobiele apps** kiest u **App-categorieën** in het gedeelte **Installatie**. 
5. Op de blade **App-categorieën** wordt een lijst met de huidige categorieën weergegeven. Kies een van de volgende acties:
    - **Een categorie maken**: selecteer **Toevoegen** om de blade **Categorie maken** weer te geven en voer vervolgens een naam in voor de nieuwe categorie. Namen kunnen slechts in één taal worden ingevoerd en worden niet door Intune vertaald. Wanneer u klaar bent, klikt u op **Maken**.
    - **Een categorie bewerken**: kies voor elke categorie in de lijst '**...** '. Bij deze optie wordt een snelmenu weergegeven, zodat u de categorie kunt **vastmaken aan het dashboard** of **verwijderen**.

## <a name="apps-added-automatically-by-intune"></a>Apps die door Intune automatisch zijn toegevoegd

Voorheen bevatte Intune een aantal ingebouwde apps die u snel kon toewijzen. Op basis van uw feedback is deze lijst verwijderd en worden ingebouwde apps niet meer weergegeven.
Als u echter al ingebouwde apps hebt toegewezen, worden deze apps nog steeds weergegeven in de lijst met apps. U kunt deze apps desgewenst blijven toewijzen.

## <a name="next-steps"></a>Volgende stappen

Kies een van de volgende onderwerpen om erachter te komen hoe u apps voor elk platform kunt toevoegen aan Intune:

- [Android Store-apps](store-apps-android.md)
- [Android LOB-apps](lob-apps-android.md)
- [iOS Store-apps](store-apps-ios.md)
- [iOS LOB-apps](lob-apps-ios.md)
- [Web-apps (voor alle platformen)](web-app.md)
- [Windows Phone 8.1 Store-apps](store-apps-windows-phone-8-1.md)
- [Windows Phone LOB-apps](lob-apps-windows-phone.md)
- [Microsoft Store-apps](store-apps-windows.md)
- [Windows LOB-app](lob-apps-windows.md)
- [Office 365-apps voor Windows 10](apps-add-office365.md)
- [Office 365-apps voor macOS](apps-add-office365-macos.md)
- [Ingebouwde apps](apps-add-built-in.md)
