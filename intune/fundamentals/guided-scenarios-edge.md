---
title: 'Begeleid scenario: Microsoft Edge voor mobiel implementeren'
titleSuffix: Microsoft Intune
description: Meer informatie over het begeleide scenario voor het implementeren van Microsoft Edge voor mobiel vanuit de portal voor Microsoft 365-apparaatbeheer.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e86f3a469169e7a805cb3f56e570ba4d3a90e925
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2019
ms.locfileid: "72585693"
---
# <a name="guided-scenario---deploy-microsoft-edge-for-mobile"></a>Begeleid scenario: Microsoft Edge voor mobiel implementeren 

Als u dit [begeleide scenario](~/fundamentals/guided-scenarios-overview.md) volgt, kunt u de Microsoft Edge-app toewijzen aan uw gebruikers op iOS- of Android-apparaten in uw organisatie. Als u deze app toewijst, kunnen uw gebruikers vanaf hun bedrijfsapparaten naadloos bladeren in inhoud. 

Microsoft Edge stelt gebruikers in staat zich een weg te banen door de wirwar van internet, door gebruik te maken van ingebouwde functies waarmee ze werkinhoud kunnen samenvoegen, ordenen en beheren. Gebruikers van iOS- en Android-apparaten die zich met hun zakelijke Azure AD-accounts aanmelden bij de Microsoft Edge-toepassing, zullen zien dat de **werkplekfavorieten** en de websitefilters die u voor hen hebt gedefinieerd, er vooraf in zijn geladen.

> [!NOTE]
> Als u hebt geblokkeerd dat gebruikers iOS- of Android-apparaten kunnen registreren, wordt in dit scenario registratie niet ingeschakeld en moeten gebruikers zelf Edge installeren.
Op basis van Intune-beleid zijn onder andere de volgende zakelijke functies van Microsoft Edge beschikbaar: 

- **Dual-Identity**. Gebruikers kunnen zowel een werkaccount als een persoonlijk account maken om mee te browsen. Er is sprake van een volledige scheiding tussen de twee identiteiten. Dit is vergelijkbaar met de architectuur en ervaring in Office 365 en Outlook. Intune-beheerders kunnen het gewenste beleid instellen voor beveiligde browsersessies binnen het werkaccount. 
- **Integratie van beveiligingsbeleid voor Intune-apps**. Beheerders kunnen nu app-beveiligingsbeleid instellen voor Microsoft Edge, inclusief beheer over knippen, kopiëren en plakken, waardoor er geen schermopnamen kunnen worden vastgelegd. Ook kunnen ze ervoor zorgen dat door de gebruiker geselecteerde koppelingen alleen kunnen worden geopend in andere beheerde apps.
- **Proxyintegratie met Azure-toepassingen**. Beheerders kunnen toegang tot SaaS-app en web-apps beheren, en ervoor zorgen dat browser-apps alleen worden uitgevoerd in de beveiligde Microsoft Edge-browser, of eindgebruikers nu verbinding maken vanuit het bedrijfsnetwerk of vanaf internet. 
- **Beheerde snelkoppelingen naar Favorieten en naar de startpagina**. Beheerders kunnen, voor een betere toegankelijkheid, URL’s instellen die worden weergegeven onder Favorieten wanneer eindgebruikers zich in hun zakelijke context bevinden. Beheerders kunnen een snelkoppeling naar de startpagina instellen, die wordt weergegeven als primaire snelkoppeling wanneer de zakelijke gebruiker een nieuwe pagina of een nieuw tabblad opent in Microsoft Edge.

## <a name="prerequisites"></a>Vereisten

- [De MDM-instantie instellen op Intune](mdm-authority-set.md#set-mdm-authority-to-intune): Met de MDM-instantie (Mobile Device Management) wordt bepaald hoe u uw apparaten beheert. Als IT-beheerder moet u een MDM-instantie instellen voordat gebruikers apparaten voor beheer kunnen inschrijven.
- Vereiste Intune-beheerdersmachtigingen:
    - Machtigingen voor het lezen, maken, verwijderen en toewijzen van beheerde apps
    - Machtigingen voor het lezen, maken en toewijzen van mobiele apps
    - Machtigingen voor het lezen, maken en toewijzen van beleidssets
    - Machtigingen voor het lezen en bijwerken van organisaties

## <a name="step-1---introduction"></a>Stap 1: inleiding

Als u het begeleide scenario **Microsoft Edge voor mobiel implementeren** volgt, gaat u een eenvoudige implementatie van Microsoft Edge instellen voor een geselecteerde groep iOS- en Android-gebruikers. Door deze implementatie uit te voeren, worden **Dubbele identiteit** en **Beheerde snelkoppelingen naar Favorieten en naar de startpagina** geïmplementeerd. Daarnaast is op apparaten die door de geselecteerde gebruikers zijn geregistreerd, automatisch de Microsoft Edge-app geïnstalleerd door Intune. Deze automatische installatie vindt plaats op alle registratietypen op basis van gebruiker, zoals: 
- iOS-registratie via de bedrijfsportal-app 
- Inschrijving van iOS-gebruikersaffiniteit via Apple Business Manager 
- Verouderde Android-registratie via de bedrijfsportal-app 

In dit begeleide scenario wordt automatisch ingeschakeld dat **MyApps** wordt weergegeven bij de favorieten in Microsoft Edge, en wordt de browser geconfigureerd met dezelfde huisstijl die u hebt ingesteld voor de Intune-bedrijfsportal-app. 

### <a name="what-you-will-need-to-continue"></a>Wat u nodig hebt om verder te gaan
U krijgt vragen over de werkplekfavorieten die uw gebruikers nodig hebben en over de filters die u nodig hebt om op internet te surfen. Zorg ervoor dat u de volgende taken uitvoert voordat u doorgaat:

- Gebruikers toevoegen aan Azure AD-groepen. Zie [Een basisgroep maken en leden toevoegen met behulp van Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=2102458) voor meer informatie.
- iOS- of Android-apparaten inschrijven in Intune. Zie [Apparaatinschrijving](https://go.microsoft.com/fwlink/?linkid=2102547) voor meer informatie.
- Verzamel een lijst met werkplekfavorieten die u wilt toevoegen in Microsoft Edge.
- Verzamel een lijst met websitefilters die worden afgedwongen in Microsoft Edge.

## <a name="step-2---basics"></a>Stap 2: basisinformatie

In deze stap moet u een naam en beschrijving voor uw nieuwe beleidsregels voor Microsoft Edge invoeren. U kunt deze beleidsregels later raadplegen als u de toewijzingen en configuraties wilt wijzigen. In het begeleide scenario wordt zowel een Microsoft Edge iOS-app voor uw iOS-apparaten als een Microsoft Edge Android-app voor uw Android-apparaten toegevoegd en toegewezen. Met deze stap wordt ook een configuratiebeleid voor deze apps gemaakt.

## <a name="step-3---configuration"></a>Stap 3: configuratie

In deze stap van het begeleide scenario wordt Microsoft Edge geconfigureerd om alle andere apps weer te geven die via Intune aan gebruikers zijn toegewezen en die dezelfde huisstijl hebben als de Microsoft Intune-bedrijfsportal app. U kunt Microsoft Edge aanvullend configureren door er een **snelkoppelings-URL voor startpagina**, een lijst met **beheerde bladwijzers** en een lijst met **geblokkeerde URL's** aan toe te voegen. De **snelkoppelings-URL voor startpagina** wordt voor gebruikers als eerste pictogram onder de zoekbalk weergegeven, wanneer ze een nieuw tabblad in Microsoft Edge openen. De lijst met **beheerde bladwijzers** is een lijst met favoriete URL's die beschikbaar zijn voor uw gebruikers als ze Microsoft Edge in de context van hun werk gebruiken. Bij de **geblokkeerde URL's** kunt u de sites opgeven die voor uw gebruikers in de context van hun werk zijn geblokkeerd. Alle andere sites worden toegestaan. 

## <a name="step-4---assignments"></a>Stap 4: toewijzingen

In deze stap kunt u de gebruikersgroepen kiezen waarvoor u wilt dat Microsoft Edge is geconfigureerd voor mobiele apparaten voor hun werk. Microsoft Edge wordt ook geïnstalleerd op alle iOS- en Android-apparaten die door deze gebruikers worden ingeschreven.

## <a name="step-5---review--create"></a>Stap 5: beoordelen en maken

In de laatste stap kunt u een samenvatting beoordelen van de instellingen die u hebt geconfigureerd. Nadat u uw keuzes hebt beoordeeld, klikt u op **Maken** om het begeleide scenario te voltooien. 

> [!NOTE]
> Het kan tot 12 uur duren voordat Edge de configuratie heeft ontvangen. Zie [App-configuratiebeleidsregels voor Microsoft Intune](~/apps/app-configuration-policies-overview.md) voor meer informatie.

> [!IMPORTANT]
> Als het begeleide scenario is voltooid, wordt een samenvatting weergegeven. U kunt de resources in de samenvatting later wijzigen, maar de tabel waarin deze resources worden weergegeven, wordt niet opgeslagen.

## <a name="next-steps"></a>Volgende stappen

- De beveiliging van het gebruik van Microsoft Edge uitbreiden door integratie met het beveiligingsbeleid van de Intune-app. Zie [Beveiligingsbeleid voor apps voor Microsoft Edge](~/apps/manage-microsoft-edge.md#application-protection-policies-for-microsoft-edge) voor meer informatie.
- Als u ook intranetsites wilt opnemen in het beveiligingsbeleid, onderzoek dan de mogelijkheden voor toegangsbescherming met behulp van proxyintegratie met Azure-toepassingen. Zie [Toepassingproxy-instellingen configureren voor Microsoft Edge](~/apps/manage-microsoft-edge.md#configure-application-proxy-settings-for-microsoft-edge) voor meer informatie.

