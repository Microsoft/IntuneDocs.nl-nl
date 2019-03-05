---
title: App-beveiligingsbeleid en werkprofielen in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk de verschillen en de voors en tegens bij het beslissen of u beveiligingsbeleid voor apps of werkprofielen wilt gebruiken voor persoonlijke of BYOD Android Enterprise-apparaten in Microsoft Intune. Vergelijk de verschillen en functies waarover u beschikt met beveiligingsbeleid voor apps zonder inschrijving (APP-WE) en met Android Enterprise-werkprofielen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/13/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6fd12432d07d1486e0943f88c0cf8b4536e651bc
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57236497"
---
# <a name="application-protection-policies-and-work-profiles-on-android-enterprise-devices-in-intune"></a>Toepassingsbeveiligingsbeleid en werkprofielen op Android Enterprise-apparaten in Intune

In veel organisaties is het voor beheerders een uitdaging om resources en gegevens op verschillende apparaten te beschermen. Eén uitdaging is het beschermen van resources voor gebruikers met persoonlijke Android Enterprise-apparaten, ook bekend als bring-your-own-device (BYOD). Microsoft Intune ondersteunt twee Android-implementatiescenario's voor bring-your-own-device (BYOD):

- Beveiligingsbeleid voor apps zonder inschrijving (APP-WE)
- Android Enterprise-werkprofielen

De APP-WE- en Android-werkprofiel-implementatiescenario’s hebben de volgende hoofdfuncties die belangrijk zijn voor BYOD-omgevingen:

1. **Beveiliging en scheiding van door de organisatie beheerde gegevens**: Beide oplossingen beschermen organisatiegegevens door controles voor preventie van gegevensverlies (DLP) af te dwingen op door de organisatie beheerde gegevens. Deze beveiligingen voorkomen onbedoeld lekken van beveiligde gegevens, zoals wanneer een eindgebruiker per ongeluk gegevens deelt met een privé-app of -account. Ze dienen ook om ervoor te zorgen dat een apparaat dat toegang krijgt tot de gegevens in orde is en niet gecompromitteerd.

2. **Privacy van eindgebruikers**: APP-WE en Android Enterprise-werkprofielen scheiden inhoud van eindgebruikers op het apparaat en gegevens die worden beheerd door de MDM-beheerder (Mobile Device Management). In beide scenario's dwingen IT-beheerders beleid af, zoals pincodeverificatie voor door de organisatie beheerde apps of identiteiten. IT-beheerders kunnen gegevens die eigendom zijn van of worden beheerd door eindgebruikers, niet lezen, openen of wissen.

Of u APP-WE of Android Enterprise-werkprofielen kiest voor uw BYOD-implementatie, is afhankelijk van uw vereisten en de behoeften van uw bedrijf. Het doel van dit artikel is u te helpen bij het maken van een keuze.

## <a name="about-intune-app-protection-policies"></a>Beveiligingsbeleid voor apps in Intune

Intune app-beveiligingsbeleid (APP) zijn beleidsregels voor gegevensbescherming gericht op gebruikers. Deze beleidsregels passen preventie van gegevensverlies toe op toepassingsniveau. Intune-APP vereist dat app-ontwikkelaars APP-functies inschakelen in de apps die ze maken.

Afzonderlijke Android-apps kunnen op verschillende manier van APP worden voorzien:

1. **Geïntegreerd in de eigen apps van Microsoft**: Microsoft Office-apps voor Android en een aantal andere Microsoft-apps worden geleverd met ingebouwde Intune-APP. Deze Office-apps, zoals Word, OneDrive, Outlook, enzovoort, hoeven niet te worden aangepast om beleid te kunnen toepassen. Deze apps kunnen rechtstreeks door eindgebruikers worden geïnstalleerd vanuit Google Play Store.

2. **Geïntegreerd in app-builds door ontwikkelaars die gebruikmaken van de Intune-SDK**: App-ontwikkelaars kunnen de Intune SDK integreren in hun broncode en hun apps opnieuw compileren om Intune APP-beleidsfuncties te ondersteunen.

3. **Verpakt met behulp van de Intune App Wrapping Tool**: Sommige klanten compileren Android-apps (.APK-bestanden) zonder toegang tot de broncode. Zonder de broncode kan de ontwikkelaar niet zorgen voor integratie met de Intune-SDK. Zonder de SDK kunnen ze de app niet geschikt maken voor APP-beleid. De ontwikkelaar moet de app wijzigen of opnieuw coderen om APP-beleid te ondersteunen.

    Om hierbij te helpen bevat Intune het hulpprogramma **App Wrapping Tool** voor bestaande Android-apps (APK's) waarmee een app kan worden gemaakt die APP-beleid herkent.

    Zie voor meer informatie over dit hulpprogramma [Prepare line-of-business apps for app protection policies](apps-prepare-mobile-application-management.md).

Zie [Intune-beheerde apps zijn uitgerust met een omvangrijke set beveiligings-policies](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) voor een lijst van apps met APP-mogelijkheden.

## <a name="deployment-scenarios"></a>Implementatiescenario 's

In deze sectie worden de belangrijkste kenmerken van implementatiescenario’s met APP-WE en Android Enterprise-werkprofielen beschreven.

#### <a name="app-we"></a>APP-WE

Bij een APP-WE-implementatie (app-beveiligingsbeleid zonder inschrijving) wordt beleid gedefinieerd op apps, en niet op apparaten. In dit scenario worden apparaten doorgaans niet ingeschreven of beheerd door een MDM-instantie zoals Intune. Beheerders maken gebruik van met APP beheerbare apps om apps en toegang tot organisatiegegevens te beschermen, en passen gegevensbeschermingsbeleid toe op deze apps.

Deze functie is van toepassing op:

- Android 4.4 en hoger

> [!TIP]
> Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie.

APP-WE-scenario's zijn bedoeld voor eindgebruikers die zo min mogelijk aanwezigheid van de organisatie willen op hun apparaat, en zich niet willen inschrijven in MDM. Als beheerder moet u uw gegevens toch beschermen. Deze apparaten worden niet beheerd. Veelvoorkomende MDM-taken en -functies, zoals Wi-Fi, VPN en certificaatbeheer, maken dus geen deel uit van dit implementatiescenario.

#### <a name="android-enterprise-work-profiles"></a>Android Enterprise-werkprofielen

Werkprofielen vormen de kern van het Android Enterprise-implementatiescenario, het enige scenario dat gericht is op BYOD. Het werkprofiel is een afzonderlijke partitie die wordt gemaakt op het niveau van Android OS, die kan worden beheerd door Intune.

Deze functie is van toepassing op:

- Apparaten met Android 5.0 en hoger met Google Mobile Services

Een werkprofiel bevat de volgende functies:

- **Traditionele MDM-functionaliteit**: Belangrijke MDM-mogelijkheden, zoals beheer van de app-levenscyclus met behulp van beheerde Google Play, zijn beschikbaar in ieder Android Enterprise-scenario. Beheerde Google Play biedt een robuuste ervaring voor het installeren en bijwerken van apps zonder tussenkomst van gebruikers. IT kan ook app-configuratie-instellingen pushen naar organisatie-apps. Het is evenmin nodig dat eindgebruikers installatie vanuit onbekende bronnen toestaan. Ook andere veelvoorkomende MDM-activiteiten, zoals het implementeren van certificaten, wifi-/VPN-verbindingen configureren en het instellen van wachtwoordcodes op apparaten, zijn beschikbaar met werkprofielen.

- **DLP op de grenzen van het werkprofiel**: Net als bij APP-WE, kan IT beleidsregels voor gegevensbescherming afdwingen. Met een werkprofiel wordt DLP-beleid afgedwongen op het niveau van het werkprofiel, en niet op app-niveau. Zo wordt bescherming bij kopiëren/plakken bijvoorbeeld afgedwongen door de APP-instellingen die zijn toegepast op een app, of afgedwongen door het werkprofiel. Wanneer de app wordt geïmplementeerd in een werkprofiel, kunnen beheerders beveiliging bij kopiëren/plakken naar het werkprofiel onderbreken door dit beleid uit te schakelen op APP-niveau.

## <a name="tips-to-optimize-the-work-profile-experience"></a>Tips voor het optimaliseren van de werkprofielervaring

### <a name="when-to-use-app-within-work-profiles"></a>Wanneer APP te gebruiken binnen werkprofielen

Intune-APP en werkprofielen zijn aanvullende technologieën, die gezamenlijk of apart kunnen worden gebruikt. De oplossingen dwingen beleid af op verschillende lagen van de architectuur: APP op de laag van afzonderlijke apps, en werkprofielen op de profiellaag. Het implementeren van apps die worden beheer met een APP-beleid in een werkprofiel is een geldig en ondersteund scenario. Of u APP, werkprofielen of een combinatie daarvan wilt gebruiken, hangt af van uw DLP-vereisten.

Werkprofielen en APP vullen elkaars instellingen aan door extra dekking te bieden als één profiel niet voldoet voor de gegevensbescherming die uw organisatie nodig heeft. Zo bieden werkprofielen standaard geen mechanismen om een app te verhinderen gegevens op te slaan op een niet-vertrouwde locatie in de cloud. APP bevat deze functie wel. U kunt besluiten dat de DLP van het werkprofiel alleen voldoende is, en er voor kiezen geen APP te gebruiken. Of u hebt mogelijk de beveiliging van een combinatie van beide nodig.

### <a name="suppress-app-policy-for-work-profiles"></a>APP-beleid onderdrukken voor werkprofielen

Het kan voorkomen dat u afzonderlijke gebruikers moet ondersteunen die meerdere apparaten hebben: onbeheerde apparaten in een APP-WE-scenario, en beheerde apparaten met werkprofielen. 

U vereist bijvoorbeeld dat eindgebruikers een pincode invoeren wanneer ze een werk-app openen. Afhankelijk van het apparaat, worden de pincodefuncties afgehandeld door APP of door het werkprofiel. Voor de APP-WE-apparaten wordt het invoeren van de pincode afgedwongen door APP. Voor apparaten met een werkprofiel kunt u een pincode voor het apparaat of werkprofiel gebruiken die wordt afgedwongen door het besturingssysteem. U implementeert dit scenario door APP-instellingen zo te configureren dat ze niet van toepassing zijn *wanneer* een app wordt geïmplementeerd in een werkprofiel. Als u het niet op deze manier configureert, wordt de eindgebruiker om een pincode gevraagd door het apparaat, en nogmaals op APP-niveau.

### <a name="control-multi-identity-behavior-in-work-profiles"></a>Gedrag van meerdere identiteiten in werkprofielen beheren

Office-toepassingen, zoals Outlook en OneDrive, kunnen werken met 'meerdere identiteiten'. Binnen één exemplaar van de toepassing kan de eindgebruiker verbindingen toevoegen met meerdere afzonderlijke accounts of opslaglocaties in de cloud. Binnen de toepassing kunnen de gegevens die van deze locaties worden opgehaald, worden gescheiden of samengevoegd. En de gebruiker kan context schakelen tussen persoonlijke id’s (user@outlook.com) en organisatie-id’s (user@contoso.com).

Wanneer u werkprofielen gebruikt, kunt u dit gedrag voor meerdere identiteiten uitschakelen. Wanneer u dit uitschakelt, kunnen badge-exemplaren van de app in het werkprofiel alleen worden geconfigureerd met een organisatie-id. Gebruik de app-configuratie-instelling Toegestane accounts voor het ondersteunen van Office Android-apps.

Zie voor meer informatie [Deploying Outlook for iOS and Android app configuration settings](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-configuration-with-microsoft-intune) (configuratie-instellingen implementeren voor Outlook voor iOS en Android).

## <a name="when-to-use-intune-app"></a>Wanneer Intune-APP te gebruiken

Er zijn verschillende scenario's voor bedrijfsmobiliteit waarbij het gebruiken van Intune-APP de beste aanbeveling is.

#### <a name="older-devices-running-android-44-51-are-being-used"></a>Er worden oudere apparaten met Android 4.4-5.1 gebruikt

Officieel bieden alle apparaten met Android 5.0 of hoger en Google Mobile Services ondersteuning voor werkprofielen, en kunnen op deze manier worden beheerd. Sommige Android 5.0- en 5.1-apparaten van sommige OEM’s ondersteunen echter geen werkprofielen.

Als u versies gebruikt die geen werkprofielen ondersteunen, moet u Intune-APP-functies gebruiken om te zorgen voor DLP voor organisatiegegevens op apparaten.

#### <a name="no-mdm-no-enrollment-google-services-are-unavailable"></a>Geen MDM, geen inschrijving, Google-services zijn niet beschikbaar

Sommige klanten willen geen enkele vorm van apparaatbeheer gebruiken, waaronder werkprofielbeheer, om diverse redenen:

- Wettelijke en aansprakelijkheidsredenen
- Voor consistentie van de gebruikerservaring
- De Android-apparaatomgeving is zeer heterogeen
- Er is geen connectiviteit met Google-services, wat vereist is voor werkprofielbeheer.

Zo kunnen klanten in China of die gebruikers hebben die zich daar bevinden, geen gebruik maken van Android-apparaatbeheer, omdat Google-services daar worden geblokkeerd. In dat geval kunt u gebruikmaken van Intune-APP voor DLP.

## <a name="summary"></a>Samenvatting

Met behulp van Intune zijn zowel APP-WE als Android Enterprise-werkprofielen beschikbaar voor uw Android BYOD-programma. De keuze tussen APP-WE of werkprofielen is afhankelijk van uw zakelijke en gebruiksvereisten. Kort samengevat: gebruik werkprofielen als u MDM-activiteiten op beheerde apparaten nodig hebt, zoals certificaatimplementatie, app-push, enzovoort. Gebruik APP-WE als u geen apparaten kunt of wilt beheren en alleen gebruikmaakt van apps die geschikt zijn voor Intune-APP.

## <a name="next-steps"></a>Volgende stappen
[App-beveiligingsbeleid gaan gebruiken](app-protection-policy.md) of [uw apparaten inschrijven](android-enroll.md).
