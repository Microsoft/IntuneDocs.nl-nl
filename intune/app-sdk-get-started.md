---
title: Aan de slag met de Microsoft Intune App SDK
description: Maak uw mobiele app snel geschikt voor Mobile Application Management (MAM) met Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune
ms.openlocfilehash: a8cbe80154e5eac6a48c86101c76faed4602288a
ms.sourcegitcommit: 1134ecd733356277b40eb1c7f2b318b36d387e00
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/02/2018
ms.locfileid: "50915713"
---
# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Aan de slag met de Microsoft Intune App SDK

Met deze handleiding kunt u uw mobiele app snel geschikt maken voor beleid voor app-beveiliging met Microsoft Intune. Wellicht vindt u het handig om eerst inzicht te krijgen in de voordelen van de Intune App SDK, zoals uitgelegd in [Overzicht van de Intune App SDK](app-sdk.md).

De Intune App SDK biedt ondersteuning voor vergelijkbare scenario's op iOS en Android, en is ervoor bedoeld om een consistente ervaring voor IT-beheerders te leveren op de verschillende platformen. Er zijn kleine verschillen in de ondersteuning van bepaalde functies vanwege beperkingen van de platformen.

## <a name="register-your-store-app-with-microsoft"></a>Uw Store-app registreren bij Microsoft

### <a name="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available"></a>Als uw app alleen intern in uw organisatie wordt gebruikt en niet openbaar beschikbaar wordt gesteld, geldt het volgende:

U hoeft uw app *niet* te registreren. Voor interne line-of-business-apps implementeert de beheerder de app intern. Intune detecteert dat de app is gemaakt met de SDK waarna de IT-beheerder het beleid voor app-beveiliging erop kan toepassen. U kunt verdergaan naar de sectie [Uw mobiele iOS- of Android-app geschikt maken voor beleid voor app-beveiliging](#enable-your-iOS-or-Android-app-for-app-protection-policy).

### <a name="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play"></a>Als uw app wordt uitgebracht in een openbare app-store, zoals de Apple App Store of Google Play, geldt het volgende:

U _**moet**_ uw app eerst registreren bij Microsoft Intune en akkoord gaan met de voorwaarden van de registratie. Na de registratie kunnen IT-beheerders beleid voor app-beveiliging toepassen op de beheerde app, die wordt vermeld als app-partner van Intune.

Zolang de registratie nog niet is voltooid en bevestigd door het team van Microsoft Intune, krijgen Intune-beheerders nog niet de mogelijkheid om beleid voor app-beveiliging toe te passen op de dieptekoppeling van uw app. Uw app wordt ook toegevoegd aan de [pagina voor Microsoft Intune-partners](https://www.microsoft.com/cloud-platform/microsoft-intune-apps). Op deze pagina wordt het pictogram van uw app weergegeven om aan te geven dat de app het Intune-beleid voor app-beveiliging ondersteunt.

Als u aan het registratieproces wilt beginnen en u nog niet werkt met een Microsoft-contactpersoon, vult u de [enquête voor Microsoft Intune-app-partners](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u) in.

De e-mailadressen die u vermeldt in uw antwoorden, worden gebruikt om contact met u op te nemen voor het vervolg van het registratieproces. Ook wordt het e-mailadres voor registratie gebruikt om contact met u op te nemen bij verdere vragen.

> [!NOTE]
> Op alle gegevens die via de vragenlijst en via e-mailcorrespondentie met het Microsoft Intune-team worden verzameld, is de [privacyverklaring van Microsoft](https://www.microsoft.com/privacystatement/default.aspx) van toepassing.

**Wat u tijdens het registratieproces kunt verwachten**:

1. Nadat u de vragenlijst hebt verzonden, wordt er via het e-mailadres voor registratie contact met u opgenomen om de ontvangst te bevestigen of om aanvullende informatie te vragen waarmee de registratie kan worden voltooid.

2. Nadat alle benodigde informatie is ontvangen, ontvangt u de Overeenkomst voor app-partners van Microsoft Intune ter ondertekening. In deze overeenkomst worden de voorwaarden beschreven die uw bedrijf moet accepteren voordat u een app-partner van Microsoft Intune kunt worden.

3. U ontvangt een bericht wanneer de registratie van uw app bij de Microsoft Intune-service is geslaagd en wanneer uw app wordt weergegeven op de site voor [Microsoft Intune-partners](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

4. Tot slot wordt de dieptekoppeling voor uw app toegevoegd aan de volgende maandelijkse service-update voor Intune. Als u de registratiegegevens bijvoorbeeld in juli hebt ingevuld, wordt de dieptekoppeling vanaf half augustus ondersteund.

Als de dieptekoppeling voor uw app in de Store in de toekomst wordt gewijzigd, moet u de app opnieuw registreren.

> [!NOTE]
> Laat het ons weten als u uw app bijwerkt naar een nieuwe versie van de Intune App SDK.

## <a name="download-the-sdk-files"></a>De SDK-bestanden downloaden

De SDK's voor Intune-apps voor systeemeigen iOS en Android worden gehost op een Microsoft GitHub-account. De volgende openbare opslagplaatsen bevatten de SDK-bestanden voor respectievelijk systeemeigen iOS en Android:

* [SDK voor Intune-apps voor iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [SDK voor Intune-apps voor Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Als uw app een Xamarin-app is, gebruikt u de volgende SDK-variant:

* [Microsoft Intune App SDK Xamarin Bindings](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)

Het is verstandig om u te registreren voor een GitHub-account waarmee u splitsingen en pulls vanuit de opslagplaatsen kunt uitvoeren. Met GitHub kunnen ontwikkelaars communiceren met het productteam, problemen melden en snel antwoord ontvangen, opmerkingen bij de release bekijken en feedback naar Microsoft verzenden. Voor vragen over de GitHub van de Intune App SDK kunt u contact opnemen met msintuneappsdk@microsoft.com.

## <a name="enable-your-ios-or-android-app-for-app-protection-policy"></a>Uw mobiele iOS- of Android-app geschikt maken voor beleid voor app-beveiliging

U hebt een van de volgende handleidingen voor ontwikkelaars nodig om de App Intune SDK te integreren in uw app:

* **[Ontwikkelaarshandleiding voor Intune App SDK voor iOS](app-sdk-ios.md)**: in dit document wordt u stapsgewijs begeleid bij het geschikt maken van uw systeemeigen iOS-app voor de Intune App SDK.

* **[Ontwikkelaarshandleiding voor Intune App SDK voor Android](app-sdk-android.md)**: in dit document wordt u stapsgewijs begeleid bij het geschikt maken van uw systeemeigen Android-app voor de Intune App SDK.

* **[Handleiding Intune App SDK Xamarin Bindings](app-sdk-xamarin.md)**: dit document bevat informatie over het bouwen van iOS- en Android-apps met Xamarin voor het Intune-beleid voor app-beveiliging.



## <a name="enable-your-ios-or-android-app-for-app-based-conditional-access"></a>Uw mobiele iOS- of Android-app geschikt maken voor voorwaardelijke toegang op app-basis
 
 Als u uw app geschikt hebt gemaakt voor het app-beveiligingsbeleid, is daarnaast het volgende vereist voor uw app om deze correct te laten functioneren met voorwaardelijke toegang op app-basis voor Azure ActiveDirectory (AAD):
 
 * De app is gebouwd met de [Azure Active Directory-verificatiebibliotheek](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) en geschikt gemaakt voor AAD Broker-verificatie.
 
 * De [AAD-client-id](https://docs.microsoft.com/azure/app-service/app-service-mobile-how-to-configure-active-directory-authentication#optional-configure-a-native-client-application) voor uw app moet uniek zijn voor de iOS- en Android-platformen.
 
## <a name="configure-telemetry-for-your-app"></a>Telemetrie configureren voor uw app

Met Microsoft Intune worden gebruiksstatistieken verzameld voor uw app.

* **Intune App SDK voor iOS**: de SDK registreert standaard SDK-telemetriegegevens van gebruiksgebeurtenissen. Deze gegevens worden naar Microsoft Intune verzonden.

    * Als u ervoor kiest geen SDK-telemetriegegevens vanuit uw app naar Microsoft Intune te verzenden, moet u het vastleggen van telemetriegegevens uitschakelen door 'JA' in te schakelen voor de eigenschap `MAMTelemetryDisabled` in het IntuneMAMSettings-woordenboek .

* **Intune App SDK voor Android**: de Intune App SDK voor Android beheert niet de gegevensverzameling vanuit uw app. De bedrijfsportal-app registreert standaard telemetriegegevens. Deze gegevens worden naar Microsoft Intune verzonden. Geheel volgens het Microsoft-beleid worden er geen persoonsgegevens verzameld. 

    * Als eindgebruikers ervoor kiezen deze gegevens niet te verzenden, moeten ze telemetrie uitschakelen onder Instellingen op de bedrijfsportal-app. Zie [Gegevensverzameling door Microsoft uitschakelen](https://docs.microsoft.com/intune-user-help/turn-off-microsoft-usage-data-collection-android) voor meer informatie. 


 Het versienummer van de line-of-business-app voor iOS en Android is zichtbaar <!-- 1380712 -->

## <a name="line-of-business-app-version-numbers"></a>Versienummers van line-of-business-apps

In line-of-business-apps in Intune wordt nu het versienummer getoond voor iOS- en Android-apps. Het nummer wordt in de Azure Portal in de app-lijst en in de blade App-overzicht getoond. Eindgebruikers kunnen het app-nummer in de bedrijfsportal-app en in de webportal zien.

### <a name="full-version-number"></a>Volledig versienummer

Het volledige versienummer duidt een specifieke release van de app aan. Het nummer wordt weergegeven als _Versie_(_Build_). Bijvoorbeeld 2.2(2.2.17560800). 

Het volledige versienummer bevat twee onderdelen:

 - **Versie**  
   Het versienummer is het door mensen leesbare releasenummer van de app. Dit wordt door eindgebruikers gebruikt om de verschillende releases van de app aan te duiden.

 - **Buildnummer**  
    Het buildnummer is een intern nummer dat voor de detectie van apps en het beheer van apps via een programma kan worden gebruikt. Het buildnummer verwijst naar een iteratie van de app die refereert aan wijzigingen in de code.

### <a name="version-and-build-number-in-android-and-ios"></a>Versie- en buildnummer in Android en iOS

Zowel Android als iOS gebruiken versie- en buildnummers ter verwijzing naar apps. Beide besturingssystemen bevatten echter betekenissen die specifiek zijn voor het besturingssysteem. De volgende tabel biedt een verklaring van de samenhang van deze termen.

Let op dat u zowel het versie- als het buildnummer gebruikt wanneer u een line-of-business-app ontwikkelt voor gebruik in Intune. Beheereigenschappen van een Intune-app zijn afhankelijk van een zinvolle **CFBundleVersion** (voor iOS) en **PackageVersionCode** (voor Android). Deze nummers zijn opgenomen in het app-manifest. 

Intune|iOS|Android|Beschrijving|
|---|---|---|---|
Versienummer|CFBundleShortVersionString|PackageVersionName |Dit nummer geeft een specifieke release van de app aan voor eindgebruikers.|
Buildnummer|CFBundleVersion|PackageVersionCode |Met dit nummer wordt een iteratie in de app-code aangegeven.|

#### <a name="ios"></a>iOS

- **CFBundleShortVersionString**  
    Hiermee wordt het releaseversienummer van de bundel opgegeven. Dit nummer duidt een releaseversie van de app aan. Met dit nummer kunnen eindgebruikers aan de app refereren.
- **CFBundleVersion**  
    De buildversie van de bundel, die een iteratie van de bundel aanduidt. Het nummer duidt eventueel een release of een releasebundel aan. Met dit nummer vindt detectie van apps plaats.

#### <a name="android"></a>Android

 - **PackageVersionName**  
    Het versienummer dat zichtbaar is voor gebruikers. Dit kenmerk kan als onbewerkte tekenreeks of als referentie aan een tekenreeksbron worden ingesteld. De tekenreeks is enkel bedoeld om aan gebruikers te worden getoond.
 - **PackageVersionCode**  
    Een intern versienummer. Dit nummer wordt alleen gebruikt om te bepalen of een versie meer recent is dan een andere, waarbij hogere nummers meer recente versies aangeven. Dit is niet de versie 

## <a name="next-steps-after-integration"></a>Vervolgstappen na de integratie

### <a name="test-your-app"></a>Uw app testen
Nadat u de benodigde stappen hebt uitgevoerd om uw iOS- of Android-app te integreren met de Intune App SDK, moet u ervoor zorgen dat alle beleid voor app-beveiliging is ingeschakeld en correct werkt voor de gebruiker en de IT-beheerder. Als u uw geïntegreerde app wilt testen, gaat u als volgt te werk:

* **Microsoft Intune-testaccount**: als u uw door Intune beheerde app wilt testen aan de hand van beveiligingsfuncties voor Intune-apps, hebt u een Microsoft Intune-account nodig.

    * Als u een ISV bent die apps voor de iOS of Android Store wilt inschakelen voor Intune-beleid voor app-beveiliging, ontvangt u een promotiecode nadat u de registratie bij Microsoft Intune hebt voltooid. Dit wordt beschreven in de registratiestap. Met de promotiecode kunt u zich aanmelden voor een Microsoft Intune-proefversie met uitgebreid gebruik van één jaar.

    * Als u een Line-Of-Business-app ontwikkelt die niet naar de Store word verzonden, wordt ervan uitgegaan dat u via uw organisatie toegang hebt tot Microsoft Intune. U kunt zich ook registreren voor een gratis proefversie van één maand via [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).

* **Intune-beleid voor app-beveiliging**: als u uw app wilt testen aan de hand van alle Intune-beleid voor app-beveiliging, moet u voor elke beleidsinstelling het te verwachten gedrag kennen. Zie de beschrijvingen van [iOS-beleid voor app-beveiliging](app-protection-policy-settings-ios.md) en [Android-beleid voor app-beveiliging](app-protection-policy-settings-android.md).

* **Probleemoplossing**: als u problemen ondervindt tijdens het handmatig testen van de gebruikerservaring van uw app-installatie, gaat u naar [Problemen met app-installatie oplossen](troubleshoot-app-install.md). 

### <a name="badge-your-app-optional"></a>Uw app van een logo voorzien (optioneel)

Nadat u de werking van Intune-beleid voor app-beveiliging hebt gevalideerd in uw app, kunt u het pictogram van uw app voorzien van het logo van Intune-beleid voor app-beveiliging.

Aan de hand van dit logo kunnen IT-beheerders, eindgebruikers en potentiële Intune-klanten zien dat uw app werkt met Intune-beleid voor app-beveiliging. Hiermee wordt de aanvaarding en het gebruik van uw app door Intune-klanten aangemoedigd.

Het logo ziet eruit als het pictogram van een aktetas zoals in de voorbeelden hieronder wordt weergegeven:

![Logovoorbeeld 1](./media/badge-example-1.png) ![Logovoorbeeld 2](./media/badge-example-2.png)

**Wat u nodig hebt om uw app van een logo te voorzien**:

* Een toepassing voor het bewerken van afbeeldingen die **EPS**-bestanden kan lezen of een Adobe-toepassing die **AI**-bestanden kan lezen.

* U kunt de [hulpmiddelen en richtlijnen voor het app-logo van Intune](https://github.com/msintuneappsdk/intune-app-partner-badge) vinden op de Microsoft Intune GitHub.
