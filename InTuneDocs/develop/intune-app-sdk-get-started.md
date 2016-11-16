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
ms.sourcegitcommit: ed1008c786285821c608a8404805c6615c60507f
ms.openlocfilehash: c80868fdee79df62aae0aa64e378be5dcc9664ae


---

# <a name="getting-started-with-the-microsoft-intune-app-sdk"></a>Aan de slag met de Microsoft Intune App SDK

Deze handleiding helpt u bij het snel geschikt maken van uw mobiele app voor Mobile Application Management met Microsoft Intune. Wellicht vindt u het handig om eerst inzicht te krijgen in de voordelen van de Intune App SDK, zoals opgesomd in [Overzicht van de Intune App SDK](intune-app-sdk.md).

Deze handleiding bespreekt de belangrijkste stappen die nodig zijn om uw mobiele app geschikt te maken voor Mobile Application Management met Microsoft Intune. De Intune App SDK ondersteunt vergelijkbare scenario's op verschillende platforms en is ervoor bedoeld om voor een consistente ervaring voor IT-beheerders op de verschillende platforms te zorgen. Er zijn echter kleine verschillen in de ondersteuning van bepaalde functies vanwege beperkingen van de platforms.

# <a name="getting-started"></a>Getting Started

## <a name="register-your-store-app-with-microsoft"></a>Uw Store-app registreren bij Microsoft

**Als uw app een interne bedrijfsapp is die niet beschikbaar wordt gesteld in een openbare appstore**:

U hoeft uw app **niet** te registreren. Voor interne line-of-business-apps implementeert de beheerder de app intern. Intune detecteert dat de app is gemaakt met de SDK en staat de IT-beheerder toe MAM-beleidsinstellingen toe te passen. U kunt de sectie [Enable your iOS or Android mobile app for MAM with the SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk) overslaan.

**Als uw app wordt uitgebracht in een openbare appstore, zoals de Apple App Store of Google Play**: 

U **moet** uw app eerst registreren bij Microsoft Intune en akkoord gaan met de voorwaarden van de registratie. Na de registratie kunnen IT-beheerders Intune MAM-beleidsinstellingen toepassen op de geïnformeerde app, die wordt weergegeven als Intune app-partner. Zolang de registratie nog niet is voltooid en bevestigd door het team van Microsoft Intune, krijgen Intune-beheerders nog niet de mogelijkheid om MAM-beleid toe te passen op de dieptekoppeling van uw app. Microsoft voegt de app ook toe aan de [pagina voor Microsoft Intune-partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps), waar het pictogram van de app wordt weergegeven om aan te geven dat deze Microsoft Intune MAM-beleid ondersteunt.

Als u het registratieproces wilt starten, vult u de **[Vragenlijst voor Microsoft Intune-partners](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u)** in. 

Microsoft gebruikt de e-mailadressen in uw antwoorden om contact met u op te nemen voor het vervolg van het registratieproces. Daarnaast gebruiken wij uw registratie-e-mailadres om contact met u op te nemen als we nog vragen hebben.

> [!NOTE]
> Op alle gegevens die via het bovengenoemde formulier en via e-mailcorrespondentie met het Microsoft Intune-team worden verzameld, is de [Microsoft Privacyverklaring](https://www.microsoft.com/en-us/privacystatement/default.aspx) van toepassing.

**Wat u tijdens het registratieproces kunt verwachten**: 

1. Nadat u de vragenlijst hebt verzonden, neemt Microsoft via uw registratiemailadres contact met u op om de ontvangst te bevestigen of om aanvullende informatie te vragen voor het voltooien van de registratie. 
2. Nadat alle benodigde informatie is ontvangen, ontvangt u de Overeenkomst voor app-partners van Microsoft Intune ter ondertekening. Deze overeenkomst beschrijft de voorwaarden die uw bedrijf met accepteren voordat u een app-partner van Microsoft Intune kunt worden. 
3. U ontvangt een bericht wanneer de registratie van uw app bij de Microsoft Intune-service is geslaagd en wanneer uw app wordt weergegeven op de site voor [Microsoft Intune-partners](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-apps). 
4. Ten slotte wordt de dieptekoppeling voor uw app toegevoegd aan de volgende maandelijkse update van de Intune-service. Als de registratiegegevens bijvoorbeeld in juli werden ingevuld, wordt de dieptekoppeling naar uw voor app medio augustus ondersteund. 

Als uw dieptekoppeling voor de app in de Store in de toekomst wordt gewijzigd, moet u de app opnieuw registreren. Laat het ons ook weten als u uw app bijwerkt naar een nieuwe versie van de Intune App SDK.



## <a name="download-the-sdk-files"></a>De SDK-bestanden downloaden

De SDK's voor Intune-apps voor systeemeigen iOS en Android worden gehost op een Microsoft GitHub-account. De onderstaande openbare opslagplaatsen bevatten de SDK-bestanden voor respectievelijk iOS en Android:

* [SDK voor Intune-apps voor iOS](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [SDK voor Intune-apps voor Android](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

**Als uw app een Xamarin- of Cordova-app is, gebruikt u de onderstaande hulpprogramma’s voor ontwikkelaars**:

* [Intune App SDK Xamarin-onderdeel](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [Intune App SDK Cordova-invoegtoepassing](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

Het is raadzaam dat u zich aanmeldt voor een GitHub-account waarmee u kunt vertakken en pulls uit onze opslagplaatsen kunt uitvoeren. Met GitHub kunnen ontwikkelaars communiceren met ons productteam, problemen melden en snel antwoord ontvangen, release-opmerkingen bekijken en feedback naar Microsoft sturen. Neem contact op via msintuneappsdk@microsoft.com voor vragen over het GitHub-account en de -opslagplaatsen.





## <a name="enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk"></a>Uw mobiele iOS- of Android-app geschikt maken voor MAM met de SDK

U hebt het volgende nodig als u de SDK voor de Intune-app wilt integreren in uw systeemeigen iOS-app: 

* **[Handleiding voor Intune App SDK voor iOS-ontwikkelaars](intune-app-sdk-ios.md)**: in dit document wordt u stapsgewijs begeleid bij het geschikt maken van uw mobiele iOS-app voor de Intune App SDK. 


U hebt het volgende nodig als u de SDK voor de Intune-app wilt integreren in uw systeemeigen Android-app:

* **[Ontwikkelaarshandleiding voor Intune App SDK voor Android](intune-app-sdk-android.md)**: dit document begeleidt u stapsgewijs door het geschikt maken van uw mobiele Android-app voor de Intune App SDK. 

Documentatie voor het Intune App SDK Xamarin-onderdeel en de Intune App SDK Cordova-invoegtoepassing vindt u in hun respectieve GitHub-opslagplaatsen. 


## <a name="configuring-telemetry-for-your-app"></a>Telemetrie configureren voor uw app

Met Microsoft Intune worden gebruiksstatistieken verzameld voor uw app.

* **Intune App SDK voor iOS**: de SDK registreert standaard SDK-telemetriegegevens van gebruiksgebeurtenissen. Deze gegevens worden naar Microsoft Intune verzonden.

    * Als u ervoor kiest geen SDK-telemetriegegevens vanuit uw app naar Microsoft Intune te verzenden, moet u het vastleggen van telemetriegegevens uitschakelen door 'JA' in te schakelen voor de eigenschap `MAMTelemetryDisabled` in het IntuneMAMSettings-woordenboek .

* **SDK voor Intune-app voor Android**: telemetriegegevens worden niet geregistreerd via de SDK.

## <a name="test-your-mam-enabled-app-with-microsoft-intune"></a>Uw voor MAM ingeschakelde app testen met Microsoft Intune

Nadat u de nodige stappen hebt gevolgd om uw iOS- of Android-app te integreren met de SDK voor de Intune-app, moet u ervoor zorgen dat alle beleidsregels voor app-beheer worden ingeschakeld en correct werken voor de eindgebruiker en de IT-beheerder. Als u uw geïntegreerde app wilt testen, gaat u als volgt te werk:

<!--TODO-->

* **Testing your MAM enabled app with Microsoft Intune** (Uw voor MAM ingeschakelde app testen met Microsoft Intune): in dit document wordt stapsgewijs uitgelegd hoe u uw geïnformeerde iOS- of Android-apps kunt testen met Microsoft Intune. Dit document vindt u in de GitHub-opslagplaatsen voor de SDK's.

* **Microsoft Intune-account**: als u uw voor MAM ingeschakelde apps wilt testen met Microsoft Intune, hebt u een Microsoft Intune-account nodig. 
    * Als u een ISV bent die uw apps voor de iOS of Android Store voor Intune MAM wilt inschakelen, ontvangt u een promotiecode nadat u de registratie bij Microsoft Intune hebt voltooid, zoals wordt beschreven in de registratiestap. Met de promotiecode kunt u zich aanmelden voor een proefabonnement van 1 jaar uitgebreid gebruik op Microsoft Intune. 
    * Als u een Line-Of-Business-app ontwikkelt die niet naar de Store word verzonden, wordt ervan uitgegaan dat u via uw organisatie toegang hebt tot Microsoft Intune. U kunt zich ook aanmelden voor een gratis proefabonnement van 1 maand op [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).




<!--HONumber=Nov16_HO1-->


