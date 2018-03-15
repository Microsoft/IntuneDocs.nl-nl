---
title: Wat is Microsoft Intune
description: Leer over Intune als het MDM-onderdeel (beheer van mobiele apparaten) en MAM-onderdeel (beheer van mobiele apps) van de oplossing Enterprise Mobility + Security en hoe u hiermee bedrijfsgegevens kunt beschermen.
keywords: wat is Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/01/2018
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
ms.custom: 
ms.openlocfilehash: aa28f11a32a35e53c8e135a9f5f738513f416c37
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2018
---
# <a name="what-is-intune"></a>Wat is Intune?

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Intune is een clouddienst voor het beheren van bedrijfsmobiliteit (Enterprise Mobility Management, EMM) die uw werknemers in staat stelt om productief te zijn terwijl uw zakelijke gegevens veilig blijven. Met Intune kunt u het volgende doen:
* De mobiele apparaten beheren die door uw werknemers worden gebruikt voor toegang tot bedrijfsgegevens.
* De mobiele apps beheren waarvan uw werknemers gebruikmaken.
* Gegevens van uw bedrijf beschermen door te bepalen hoe uw werknemers toegang hebben tot de gegevens en deze delen.
* Garanderen dat apparaten en apps compatibel zijn met de beveiligingsvereisten van het bedrijf.

## <a name="common-business-problems-that-intune-helps-solve"></a>Algemene bedrijfsproblemen die Intune u helpt op te lossen

* [Uw on-premises-e-mail en -gegevens beveiligen, zodat deze veilig kunnen worden geopend vanaf mobiele apparaten](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Uw Office 365-e-mail en -gegevens beveiligen, zodat deze veilig kunnen worden geopend vanaf mobiele apparaten](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Bedrijfstelefoons ter hand stellen aan uw medewerkers](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Een Bring Your Own Device-programma (BYOD) aan alle werknemers aanbieden](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Uw werknemers in staat stellen Office 365 veilig te gebruiken vanuit een niet-beheerde openbare kiosk](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Tablets voor beperkt gebruik verstrekken aan taakgerichte werknemers](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)


## <a name="how-does-intune-work"></a>Hoe werkt Intune?
Intune is het onderdeel van Microsoft Enterprise Mobility + Security (EMS) dat mobiele apparaten en apps beheert. De oplossing is nauw geïntegreerd met andere EMS-onderdelen, zoals Azure Active Directory (Azure AD), voor identiteits- en toegangsbeheer en met Azure Information Protection voor gegevensbeveiliging. Als u de oplossing in combinatie met Office 365 gebruikt, kunt u uw medewerkers in staat stellen om productief te zijn op al hun apparaten terwijl de gegevens van uw organisatie beschermd blijven.

![Afbeelding van Intune-architectuur](./media/intunearch_sm.png)

Geef een [grotere versie](./media/intunearchitecture.svg) van het diagram van de Intune-architectuur weer.

Hoe u de functies voor apparaat- en app-beheer in Intune en EMS-gegevensbescherming gebruikt, hangt af van het [bedrijfsprobleem dat u wilt oplossen](#common-business-problems-that-intune-helps-solve). Bijvoorbeeld:
* U maakt volop gebruik van apparaatbeheer als u een groep van apparaten voor afzonderlijk gebruik maakt die worden gedeeld door winkelmedewerkers die elkaar in diensten afwisselen.
* U vertrouwt op app-beheer en gegevensbescherming als u toestaat dat uw werknemers hun eigen apparaten gebruiken voor toegang tot bedrijfsgegevens (BYOD).  
* Als u informatiemedewerkers bedrijfstelefoons ter hand stelt, zult u afhankelijk zijn van al deze technologieën.

## <a name="intune-device-management-explained"></a>Apparaatbeheer in Intune uitgelegd
Apparaatbeheer in Intune werkt met behulp van de protocollen of API's die beschikbaar zijn in de mobiele besturingssystemen. Het omvat taken zoals:
* Apparaten inschrijven voor beheer, zodat uw IT-afdeling beschikt over een overzicht van de apparaten die toegang hebben tot bedrijfsservices
* Apparaten configureren zodat ze voldoen aan de bedrijfsnormen voor beveiliging en gezondheid.
* Certificaten en Wi-Fi-/VPN-profielen bieden voor toegang tot bedrijfsservices.
* Rapportage over en beoordelen van apparaatcompatibiliteit ten opzichte van bedrijfsnormen.
* Bedrijfsgegevens verwijderen van beheerde apparaten.  

Soms wordt gedacht dat **beheer van toegang tot bedrijfsgegevens** een functie binnen het apparaatbeheer is. Wij zien dat anders, omdat dit niet iets is dat door het mobiele besturingssysteem wordt geboden. Het is eerder iets waarin de identiteitsprovider voorziet. Bij ons is de identiteitsprovider Azure Active Directory (Azure AD) het beheersysteem voor identiteit en toegang van Microsoft.  

Intune integreert met Azure AD om tal van scenario’s voor toegangsbeheer mogelijk te maken. U kunt bijvoorbeeld vereisen dat een mobiel apparaat voldoet aan bedrijfsnormen die u in Intune definieert voordat het apparaat toegang krijgt tot bedrijfsservices zoals Exchange. U kunt ook de bedrijfsservice vergrendelen voor een specifieke set mobiele apps. Zo kunt u Exchange Online bijvoorbeeld vergrendelen, zodat deze toepassing alleen toegankelijk is voor Outlook of Outlook Mobile.

## <a name="intune-app-management-explained"></a>App-beheer in Intune uitgelegd
Als we het over app-beheer hebben, bedoelen we:
* Het toewijzen van mobiele apps aan medewerkers
* Het configureren van apps met standaardinstellingen die worden gebruikt als de app wordt uitgevoerd
* Beheren hoe bedrijfsgegevens worden gebruikt en gedeeld in mobiele apps
* Bedrijfsgegevens verwijderen van mobiele apps   
* Apps bijwerken
* Rapportage over de inventaris van mobiele apps
* Bijhouden van het gebruik van mobiele apps

Soms wordt de term beheer van mobiele apps (MAM) gebruikt om één van deze toepassingen afzonderlijk aan te duiden of om te verwijzen naar een specifieke combinatie ervan. Veelal wordt het concept van app-configuratie verward met het concept van de beveiliging van bedrijfsgegevens binnen mobiele apps. Dat is omdat sommige mobiele apps instellingen doorgeven waarmee hun functies voor gegevensbescherming kunnen worden geconfigureerd.

Wanneer we over app-configuratie en Intune spreken, verwijzen we specifiek naar technologieën zoals [beheerde app-configuratie in iOS](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html).

Als u Intune gebruikt met andere services in EMS, kunt u uw organisatie veel meer beveiliging van mobiele apps bieden dan door het mobiele besturingssysteem en de configuratie van mobiele apps zelf wordt geleverd. Een app die wordt beheerd met EMS heeft toegang tot een uitgebreidere reeks functies voor de bescherming van mobiele apps en gegevens, met onder meer:

* [Eenmalige aanmelding](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Multi-Factor Authentication](https://docs.microsoft.com/multi-factor-authentication/multi-factor-authentication)
* [Voorwaardelijke toegang tot apps: toegang toestaan als de mobiele app bedrijfsgegevens bevat](app-based-conditional-access-intune.md)
* [Het isoleren van bedrijfsgegevens ten opzichte van persoonlijke gegevens binnen dezelfde app](app-protection-policy.md)
* [App-beveiligingsbeleid (pincode, codering, opslaan als, klembord, enzovoort)](app-protection-policies.md)
* [Bedrijfsgegevens wissen uit een mobiele app](apps-selective-wipe.md)
* [Ondersteuning voor Rights Management-services](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

![Installatiekopie waarin de niveaus van beheer van gegevensbeveiliging voor apps worden weergegeven](./media/managing-mobile-apps.png)

### <a name="intune-app-security"></a>App-beveiliging in Intune
App-beveiliging is een onderdeel van app-beheer en wanneer we het in verband met Intune hebben over de beveiliging van mobiele apps, bedoelen we:
* Persoonlijke gegevens geïsoleerd houden van bedrijfsgegevens en IT.
* Beperken van de acties die gebruikers kunnen ondernemen met bedrijfsgegevens, zoals kopiëren, knippen en plakken, opslaan en weergeven.
* Bedrijfsgegevens verwijderen uit mobiele apps, ook wel selectief wissen of zakelijk wissen genoemd.

Een van de manieren waarop Intune beveiliging van mobiele apps biedt, is via de functie voor **app-beveiligingsbeleid**. App-beveiligingsbeleid maakt gebruik van Azure AD-identiteit om bedrijfsgegevens te isoleren van persoonlijke gegevens. Gegevens die toegankelijk zijn met behulp van zakelijke referenties, krijgen extra bedrijfsbeveiliging.

Als een gebruiker zich bijvoorbeeld op zijn apparaat aanmeldt met behulp van zijn zakelijke referenties, heeft hij via de bedrijfsidentiteit toegang tot gegevens die aan zijn persoonlijke identiteit worden geweigerd. Als die bedrijfsgegevens worden gebruikt, bepaalt het app-beveiligingsbeleid hoe ze worden opgeslagen en gedeeld. Dergelijke beveiligingen worden niet toegepast op gegevens waar gebruikers toegang toe krijgen als ze zich bij hun apparaat aanmelden met hun persoonlijke identiteit. De IT-afdeling heeft zo het beheer over de bedrijfsgegevens, terwijl de eindgebruikers het beheer houden over hun persoonlijke gegevens en de privacy daarvan.

## <a name="emm-with-and-without-device-enrollment"></a>EMM met en zonder apparaatinschrijving
De meeste oplossingen voor het beheer van bedrijfsmobiliteit ondersteunen basistechnologieën voor mobiele apparaten en mobiele apps. Deze zijn meestal gekoppeld aan het apparaat dat wordt ingeschreven in de MDM-oplossing (beheer van mobiele apparaten) in uw organisatie. Intune biedt ondersteuning voor deze scenario's en ondersteunt daarnaast tal van 'zonder inschrijving'-scenario's.  

In verschillende organisaties worden verschillende 'zonder inschrijving'-scenario's gebruikt. Voor sommige organisaties is apparaatgebruik zonder inschrijving de norm. Andere organisaties staan dit soort scenario’s toe voor begeleidingsapparaten, zoals een persoonlijke tablet. Weer andere organisaties ondersteunen deze scenario’s helemaal niet. Zelfs in het laatste geval, als een organisatie vereist dat alle apparaten van werknemers worden ingeschreven in MDM, ondersteunen ze meestal 'zonder inschrijving'-scenario's voor uitzendkrachten en leveranciers, en voor andere apparaten waarvoor een specifieke uitzondering geldt.

U kunt de 'zonder inschrijving'-technologie van Intune zelfs gebruiken op ingeschreven apparaten. Een apparaat dat is ingeschreven in MDM kan bijvoorbeeld 'Open-in'-beveiliging hebben die wordt geleverd door het mobiele besturingssysteem. 'Open-in'-beveiliging is een iOS-functie waarmee u documenten uit bepaalde apps, zoals Outlook, niet kunt openen in andere apps, zoals Word, tenzij beide apps worden beheerd door de MDM-provider. Bovendien kan de IT-afdeling app-beveiligingsbeleid toepassen op met EMS beheerde mobiele apps om de opslaan als-bewerkingen te controleren of om meervoudige verificatie te bieden.

Intune als onderdeel van EMS heeft hulpprogramma's waarmee uw medewerkers hun productiviteit kunnen verhogen terwijl uw bedrijfsgegevens beschermd blijven, ongeacht hoe uw organisatie omgaat met ingeschreven en niet-ingeschreven mobiele apparaten en apps.



### <a name="next-steps"></a>Volgende stappen
* Meer informatie over een aantal [algemene manieren om Intune te gebruiken](common-scenarios.md).
* Vertrouwd raken met het product [met een 30-daagse evaluatieversie van Intune](free-trial-sign-up.md).
* Duik in de [technische vereisten en mogelijkheden](supported-devices-browsers.md) van Intune.
