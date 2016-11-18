---
title: Aan de slag met de Microsoft Intune App SDK | Microsoft Intune
description: 
keywords: 
author: Msmbaldwin
manager: jeffgilb
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8bc2f6e8dcf9d0ac3e7fccec792c86ff1fd4131c
ms.openlocfilehash: 15be877edbdeb827a4318af226ea8cde8c8e46f4


---

# <a name="get-started-with-the-microsoft-intune-app-sdk"></a>Aan de slag met de Microsoft Intune App SDK

Met deze handleiding kunt u snel uw mobiele app geschikt maken voor Mobile Application Management (MAM) met Microsoft Intune. Wellicht vindt u het handig om eerst inzicht te krijgen in de voordelen van de Intune App SDK, zoals uitgelegd in [Overzicht van de Intune App SDK](intune-app-sdk.md).

In deze handleiding vindt u de belangrijkste stappen die nodig zijn om MAM met Microsoft Intune in te schakelen voor uw app. De Intune App SDK biedt ondersteuning voor vergelijkbare scenario's op verschillende platformen en is ervoor bedoeld om een consistente ervaring voor IT-beheerders te leveren op de verschillende platformen. Er zijn kleine verschillen in de ondersteuning van bepaalde functies vanwege beperkingen van de platformen.

## <a name="register-your-store-app-with-microsoft"></a>Uw Store-app registreren bij Microsoft

**Als uw app een interne bedrijfsapp is die niet beschikbaar wordt gesteld in een openbare appstore**:

U hoeft uw app *niet* te registreren. Voor interne Line-Of-Business-apps implementeert de beheerder de app intern. Er wordt met Intune gedetecteerd dat de app is gemaakt met de SDK waarna de IT-beheerder de MAM-beleidsinstellingen kan toepassen. U kunt de sectie [Enable your iOS or Android mobile app for MAM with the SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) overslaan.

**Als uw app wordt uitgebracht in een openbare App Store, zoals de Apple App Store of Google Play**:

U *moet* uw app eerst registreren bij Microsoft Intune en akkoord gaan met de voorwaarden van de registratie. Na de registratie kunnen IT-beheerders de MAM-beleidsinstellingen van Intune toepassen op de compatibele app, die wordt vermeld als app-partner van Intune. Zolang de registratie nog niet is voltooid en bevestigd door het team van Microsoft Intune, krijgen Intune-beheerders nog niet de mogelijkheid om MAM-beleid toe te passen op de dieptekoppeling van uw app. Uw app wordt ook toegevoegd aan de [pagina voor Microsoft Intune-partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps). Op deze pagina wordt het pictogram van uw app weergegeven om aan te geven dat de app het Microsoft Intune MAM-beleid ondersteunt.

Als u het registratieproces wilt starten, vult u de [vragenlijst voor app-partners van Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u) in.

De e-mailadressen die u vermeldt in uw antwoorden, worden gebruikt om contact met u op te nemen voor het vervolg van het registratieproces. Ook wordt het e-mailadres voor registratie gebruikt om contact met u op te nemen bij verdere vragen.

> [!NOTE]
> Op alle gegevens die via de vragenlijst en via e-mailcorrespondentie met het Microsoft Intune-team worden verzameld, is de [privacyverklaring van Microsoft](https://www.microsoft.com/en-us/privacystatement/default.aspx) van toepassing.

**Wat u tijdens het registratieproces kunt verwachten**:

1. Nadat u de vragenlijst hebt verzonden, wordt er via het e-mailadres voor registratie contact met u opgenomen om de ontvangst te bevestigen of om aanvullende informatie te vragen waarmee de registratie kan worden voltooid.
2. Nadat alle benodigde informatie is ontvangen, ontvangt u de Overeenkomst voor app-partners van Microsoft Intune ter ondertekening. In deze overeenkomst worden de voorwaarden beschreven die uw bedrijf moet accepteren voordat u een app-partner van Microsoft Intune kunt worden.
3. U ontvangt een bericht wanneer de registratie van uw app bij de Microsoft Intune-service is geslaagd en wanneer uw app wordt weergegeven op de site voor [Microsoft Intune-partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps).
4. Tot slot wordt de dieptekoppeling voor uw app toegevoegd aan de volgende maandelijkse service-update voor Intune. Als u de registratiegegevens bijvoorbeeld in juli hebt ingevuld, wordt de dieptekoppeling vanaf half augustus ondersteund.

Als de dieptekoppeling voor uw app in de Store in de toekomst wordt gewijzigd, moet u de app opnieuw registreren. Laat het ons ook weten als u uw app bijwerkt naar een nieuwe versie van de Intune App SDK.



## <a name="download-the-sdk-files"></a>De SDK-bestanden downloaden

De SDK's voor Intune-apps voor systeemeigen iOS en Android worden gehost op een Microsoft GitHub-account. De volgende openbare opslagplaatsen bevatten de SDK-bestanden voor respectievelijk iOS en Android:

* [SDK voor Intune-apps voor iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [SDK voor Intune-apps voor Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

Als uw app een Xamarin- of Cordova-app is, gebruikt u de volgende ontwikkelhulpprogramma's:

* [Intune App SDK Xamarin-onderdeel](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune App SDK Cordova-invoegtoepassing](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Het is verstandig om u te registreren voor een GitHub-account waarmee u splitsingen en pulls vanuit de opslagplaatsen kunt uitvoeren. Met GitHub kunnen ontwikkelaars communiceren met het productteam, problemen melden en snel antwoord ontvangen, opmerkingen bij de release bekijken en feedback naar Microsoft verzenden. Neem contact op via msintuneappsdk@microsoft.com voor vragen over het GitHub-account en de -opslagplaatsen.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>Uw mobiele iOS- of Android-app geschikt maken voor MAM met de SDK

U hebt het volgende nodig als u de SDK voor de Intune-app wilt integreren in uw systeemeigen iOS-app:

* **[Ontwikkelaarshandleiding voor Intune App SDK voor iOS](intune-app-sdk-ios.md)**: in dit document wordt u stapsgewijs begeleid bij het geschikt maken van uw mobiele iOS-app voor de Intune App SDK.


U hebt het volgende nodig als u de SDK voor de Intune-app wilt integreren in uw systeemeigen Android-app:

* **[Ontwikkelaarshandleiding voor Intune App SDK voor Android](intune-app-sdk-android.md)**: in dit document wordt u stapsgewijs begeleid bij het geschikt maken van uw mobiele Android-app voor de Intune App SDK.

De documentatie voor het Intune App SDK Xamarin-onderdeel en de Intune App SDK Cordova-invoegtoepassing is beschikbaar in de respectieve GitHub-opslagplaatsen.


## <a name="set-up-telemetry-for-your-app"></a>Telemetrie instellen voor uw app

Met Microsoft Intune worden gebruiksstatistieken verzameld voor uw app.

* **Intune App SDK voor iOS**: de SDK registreert standaard SDK-telemetriegegevens van gebruiksgebeurtenissen. Deze gegevens worden naar Microsoft Intune verzonden.

    * Als u ervoor kiest geen SDK-telemetriegegevens vanuit uw app naar Microsoft Intune te verzenden, moet u het vastleggen van telemetriegegevens uitschakelen door 'JA' in te schakelen voor de eigenschap `MAMTelemetryDisabled` in het IntuneMAMSettings-woordenboek .

* **SDK voor Intune-app voor Android**: telemetriegegevens worden niet geregistreerd via de SDK.

## <a name="test-your-mamenabled-app-with-microsoft-intune"></a>Uw app met MAM-functionaliteit testen met Microsoft Intune

Nadat u de benodigde stappen hebt uitgevoerd om uw iOS- of Android-app te integreren met de Intune App SDK, moet u ervoor zorgen dat alle beleidsregels voor app-beheer zijn ingeschakeld en correct werken voor de gebruiker en de IT-beheerder. Als u uw geïntegreerde app wilt testen, gaat u als volgt te werk:

<!--TODO-->

* **Testing your MAM enabled app with Microsoft Intune** (Uw app met MAM-functionaliteit testen met Microsoft Intune): In dit document wordt stapsgewijs uitgelegd hoe u uw compatibele iOS- of Android-apps kunt testen met Microsoft Intune. Dit document vindt u in de GitHub-opslagplaatsen voor de SDK's.

* **Microsoft Intune-account**: als u uw apps met MAM-functionaliteit wilt testen met Microsoft Intune, hebt u een Microsoft Intune-account nodig.
    * Als u een ISV bent die apps voor de iOS of Android Store wilt inschakelen voor Intune MAM, ontvangt u een promotiecode nadat u de registratie bij Microsoft Intune hebt voltooid. Dit wordt beschreven in de registratiestap. Met de promotiecode kunt u zich aanmelden voor een Microsoft Intune-proefversie met uitgebreid gebruik van één jaar.
    * Als u een Line-Of-Business-app ontwikkelt die niet naar de Store word verzonden, wordt ervan uitgegaan dat u via uw organisatie toegang hebt tot Microsoft Intune. U kunt zich ook registreren voor een gratis proefversie van één maand via [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).



<!--HONumber=Nov16_HO3-->


