---
# required metadata

title: Aan de slag met de Microsoft Intune App SDK | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Aan de slag met de Microsoft Intune App SDK

Deze handleiding helpt u bij het snel geschikt maken van uw mobiele app voor Mobile Application Management met Microsoft Intune. Wellicht vindt u het handig om eerst inzicht te krijgen in de voordelen van de Intune App SDK, zoals opgesomd in [Overzicht van de Intune App SDK](intune-app-sdk.md).

Deze handleiding bespreekt de belangrijkste stappen die nodig zijn om uw mobiele app geschikt te maken voor Mobile Application Management met Microsoft Intune. De Intune App SDK ondersteunt vergelijkbare scenario's op verschillende platforms en is ervoor bedoeld om voor een consistente ervaring voor IT-beheerders op de verschillende platforms te zorgen. Er zijn echter kleine verschillen in de ondersteuning van bepaalde functies vanwege beperkingen van de platforms.

# Getting Started

## Registreren voor Microsoft Connect

De Intune App SDK is momenteel toegankelijk via Microsoft Connect en vereist aanmelding. Hiertoe registreert u zich met uw zakelijke e-mailadres voor een [Microsoft-account](https://connect.microsoft.com/ConfigurationManagervnext/InvitationUse.aspx?ProgramID=8967&InvitationID=8967-YJYJ-8G6X).

Uw registratie krijgt de status In behandeling totdat het Intune-team uw aanvraag beoordeelt. Gemiddeld duurt dit twee tot drie dagen. Na goedkeuring ontvangt u een e-mailbericht met de koppeling(en) voor het downloaden van de Intune App SDK voor uw platform(s) en alle gerelateerde handleidingen. Deze handleidingen zijn ook toegankelijk via de MSDN-website.

## Uw Store-app registreren bij Microsoft Intune

**Als uw ingeschakelde app bedoeld is voor intern gebruik binnen uw bedrijf en niet beschikbaar wordt gesteld in de App Store van Apple of Google**, hoeft u uw app niet te registreren. Dergelijke interne apps worden rechtstreeks door de IT-beheerder in de Microsoft Intune-beheerconsole geladen voor implementatie. Intune detecteert dat de app met de SDK is gemaakt en biedt de IT-beheerder de optie om MAM-beleid op de app toe te passen. U kunt doorgaan naar de sectie [Uw mobiele iOS- of Android-app geschikt maken voor MAM met de SDK](#enable-your-ios-or-android-mobile-app-for-mam-with-the-sdk).

**Als u een ISV bent die een app ontwikkelt die aan klanten beschikbaar zal worden gesteld via de App Store van Apple of Google**: u moet uw app eerst registreren bij Microsoft Intune en akkoord gaan met de registratievoorwaarden. Op dit moment kunt u de dieptekoppeling naar de app opgeven. Vervolgens kan een IT-beheerder het MAM-beleid van Intune toepassen op de app. Zolang de registratie nog niet is voltooid en bevestigd door het team van Microsoft Intune, krijgt de dieptekoppeling naar uw app niet de mogelijkheid om MAM-beleid toe te passen in de beheerconsole. Microsoft onderhoudt ook een website voor Microsoft Intune-partners waar de app wordt geregistreerd zodat klanten weten dat deze ondersteuning biedt voor MAM-beleid van Microsoft Intune.

Als u het registratieproces wilt starten, **leest en ondertekent** u de [Overeenkomst voor Microsoft Intune-partners](https://connect.microsoft.com/ConfigurationManagervnext/Survey/Survey.aspx?SurveyID=17806). Deze overeenkomst beschrijft de voorwaarden die uw bedrijf met accepteren voordat u een app-partner van Microsoft Intune kunt worden. U moet zich aanmelden voordat u dit document kunt weergeven. U vindt de overeenkomst in de Microsoft Connect-site Intune-App SDK op het tabblad Enquêtes of u kijkt hier. Ook vragen we u om de naam van de app, de naam van uw bedrijf, evenals de dieptekoppeling naar uw app in de Google- of iTunes Store op te geven.

![Microsoft Connect](../media/microsoft-connect.png)

We gebruiken uw e-mailadres voor registratie voor het bevestigen en voltooien van de ontvangst van het registratieproces. Daarnaast gebruiken wij uw registratie-e-mailadres om contact met u op te nemen als we nog vragen hebben.

**Wat u tijdens het registratieproces kunt verwachten**: nadat u het formulier hebt verzonden, neemt Microsoft via uw registratie-e-mailadres contact met u op om de ontvangst te bevestigen of om aanvullende informatie te vragen voor het voltooien van de registratie. We nemen ook contact met u op wanneer de registratie van uw app bij Microsoft Intune is geslaagd en wanneer uw app wordt weergegeven op de site voor Microsoft Intune-partners. Nadat de ontvangst van de informatie is bevestigd, wordt de dieptekoppeling naar uw app opgenomen in de volgende maandelijkse service-update van Intune. Als de registratiegegevens bijvoorbeeld in juli werden ingevuld, wordt de dieptekoppeling naar uw voor app medio augustus ondersteund. Als uw dieptekoppeling naar de Store-app in de toekomst wordt gewijzigd, moet u de app opnieuw registreren. Laat het ons ook weten als u uw app bijwerkt naar een nieuwe versie van de Intune App SDK.

**Opmerking**: alle gegevens die via het bovengenoemde formulier en via e-mailcorrespondentie met het Intune-team worden verzameld, respecteert de [Microsoft Privacyverklaring](https://www.microsoft.com/en-us/privacystatement/default.aspx).

## Uw mobiele iOS- of Android-app geschikt maken voor MAM met de SDK

Als u uw mobiele iOS-app geschikt wilt maken, hebt u het volgende nodig:

1. **[Handleiding voor Intune App SDK voor iOS-ontwikkelaars](intune-app-sdk-ios.md)**: in dit document wordt u stapsgewijs begeleid bij het geschikt maken van uw mobiele iOS-app voor de Intune App SDK. Dit document is te vinden in de documentatiemap die u hebt gedownload als onderdeel van het Intune App SDK-pakket.
2. **Intune App SDK voor iOS**: als onderdeel van het Intune App SDK-pakket dat u van Microsoft Intune hebt gedownload, vindt u een ondertekende map ‘Intune App SDK voor iOS’. Deze map bevat alle inhoud van de Intune App SDK voor iOS.

Als u uw mobiele Android-app geschikt wilt maken voor de Intune App SDK, hebt u het volgende nodig:

1. **[Ontwikkelaarshandleiding voor Intune App SDK voor Android](intune-app-sdk-android.md)**: dit document begeleidt u stapsgewijs door het geschikt maken van uw mobiele Android-app voor de Intune App SDK. Dit document is te vinden in de documentatiemap die u hebt gedownload als onderdeel van het Intune App SDK-pakket.
2. **Intune App SDK voor Android**: als onderdeel van het Intune App SDK-pakket dat u van Microsoft Intune hebt gedownload, vindt u een ondertekende map ‘App SDK Intune voor Android’. Deze map bevat alle inhoud van de Intune App SDK voor Android.

## Telemetrie uitschakelen voor uw app

**Intune App SDK voor iOS**: de SDK registreert standaard SDK-telemetriegegevens van gebruiksgebeurtenissen. Deze gegevens worden naar Microsoft Intune verzonden.

Als u ervoor kiest geen SDK-telemetriegegevens vanuit uw app naar Microsoft Intune te verzenden, moet u het vastleggen van telemetriegegevens in de SDK **uitschakelen** door de eigenschap `MAMTelemetryDisabled` in de `IntuneMAMSettings`.

**Intune App SDK voor Android**: SDK-telemetriegegevens worden niet geregistreerd via de SDK.

## Uw voor MAM ingeschakelde app testen met Microsoft Intune

Nadat u de nodige stappen hebt gevolgd om uw Intune App SDK voor iOS of Android te informeren (de Intune App SDK integreren), moet u ervoor te zorgen dat alle beleidsregels voor app-beheer worden ingeschakeld en correct werken voor de eindgebruiker en de IT-beheerder. Als u uw geïnformeerde app wilt testen, gaat u als volgt te werk:

1. **Testing your MAM enabled app with Microsoft Intune** (Uw voor MAM ingeschakelde app testen met Microsoft Intune): in dit document wordt stapsgewijs uitgelegd hoe u uw geïnformeerde iOS- of Android-apps kunt testen met Microsoft Intune. Dit document is te vinden in de documentatiemap die u hebt gedownload als onderdeel van het Intune App SDK-pakket.
2. **Microsoft Intune-account**: als u uw voor MAM ingeschakelde apps wilt testen met Microsoft Intune, hebt u een Microsoft Intune-account nodig. Als u een ISV bent die uw apps voor de iOS of Android Store voor MAM wilt inschakelen, ontvangt u een promotiecode nadat u de registratie bij Microsoft Intune hebt voltooid, zoals wordt beschreven in de registratiestap. Met de promotiecode kunt u zich aanmelden voor een proefabonnement van 1 jaar uitgebreid gebruik op Microsoft Intune. Als u een Line-Of-Business-app ontwikkelt die niet naar de Store word verzonden, wordt ervan uitgegaan dat u via uw organisatie toegang hebt tot Microsoft Intune. U kunt zich ook aanmelden voor een gratis proefabonnement van 1 maand op [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).



<!--HONumber=May16_HO2-->


