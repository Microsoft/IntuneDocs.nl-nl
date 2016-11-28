---
title: Wat is Microsoft Intune?| Microsoft Docs
description: Meer informatie over Intune als het MDM-onderdeel (Mobile Device Management) van de oplossing Enterprise Mobility + Security en hoe u hiermee bedrijfsgegevens kunt beschermen.
keywords: wat is Intune
author: Lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b4e778d-ac13-4c23-974f-5122f74626bc
ms.reviewer: pmay
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6932a0d81654edc4c2e3108ca11df892e9ec5bf4
ms.openlocfilehash: 50a9b89140a0fff9994b267f10fa7912af89f116


---

# <a name="what-is-intune"></a>Wat is Intune?
Intune is een cloudgebaseerde service voor het beheer van bedrijfsmobiliteit (Enterprise Mobility Management, EMM) die uw werknemers in staat stelt om productief te zijn terwijl uw zakelijke gegevens veilig blijven. Met Intune kunt u het volgende doen:
* De mobiele apparaten beheren die door uw werknemers worden gebruikt voor toegang tot bedrijfsgegevens.
* De mobiele apps beheren waarvan uw werknemers gebruikmaken.
* Gegevens van uw bedrijf beschermen door te bepalen hoe uw werknemers toegang hebben tot de gegevens en deze delen.
* Garanderen dat apparaten en apps compatibel zijn met de beveiligingsvereisten van het bedrijf.

Intune is nauw geïntegreerd met Azure Active Directory (Azure AD) voor identiteits- en toegangsbeheer en met Azure Rights Management (Azure RMS) voor gegevensbeveiliging. Het is de *beheertak* van Microsoft Enterprise Mobility + Security (EMS), terwijl Office 365 de *productiviteitstak* is van de mobiliteitsoplossing van Microsoft.  

Samen stellen Office 365 en EMS uw medewerkers in staat om productief te zijn op al hun apparaten terwijl de gegevens van uw organisatie beschermd blijven. Office 365 met EMS is een volledig geïntegreerde oplossing voor bedrijfsmobiliteit, met inbegrip van productiviteit, identiteit, toegangsbeheer, beheer en gegevensbeveiliging. Dit biedt u een effectieve manier om een mobiliteitsoplossing te implementeren en te gebruiken in uw organisatie.

## <a name="how-does-intune-work"></a>Hoe werkt Intune?
Intune biedt mogelijkheden voor beheer van mobiele apparaten (MDM) en beheer van mobiele apps (MAM). De MDM- en MAM-functies van Intune dragen vervolgens bij aan de EMS-suite voor scenario’s van gegevensbescherming en naleving.  

Hoe u de MDM-/MAM-functies van Intune en EMS-gegevensbescherming gebruikt, hangt af van het [bedrijfsprobleem dat u wilt oplossen](#common-business-problems-that-intune-helps-solve). Bijvoorbeeld:
* U maakt volop gebruik van MDM als u een groep van apparaten voor afzonderlijk gebruik maakt die worden gedeeld door winkelmedewerkers die elkaar in diensten afwisselen.
* U vertrouwt op MAM en gegevensbescherming als u toestaat dat uw werknemers hun eigen apparaten gebruiken voor toegang tot bedrijfsgegevens (BYOD).  
* Als u informatiemedewerkers bedrijfstelefoons ter hand stelt, zult u sterk afhankelijk zijn van al deze technologieën.

## <a name="intune-mobile-device-management-mdm-explained"></a>Uitleg over Intune Mobile Device Management (MDM)
MDM werkt met behulp van de protocollen of API's die beschikbaar zijn in de mobiele besturingssystemen. Het omvat taken zoals:
* Apparaten inschrijven voor beheer, zodat de IT-afdeling beschikt over een overzicht van de apparaten die toegang hebben tot bedrijfsservices.
* Apparaten configureren zodat ze voldoen aan de bedrijfsnormen voor beveiliging en gezondheid.
* Certificaten en Wi-Fi-/VPN-profielen bieden voor toegang tot bedrijfsservices.
* Rapportage over en beoordelen van apparaatcompatibiliteit ten opzichte van bedrijfsnormen.
* Bedrijfsgegevens verwijderen van beheerde apparaten.  

**Beheer van toegang tot bedrijfsgegevens** wordt door sommigen gezien als een MDM-functie. Wij zien dat anders, omdat dit niet iets is dat door het mobiele besturingssysteem wordt geboden. Het is eerder iets waarin de identiteitsprovider voorziet. Bij ons is de identiteitsprovider Azure Active Directory (Azure AD) het beheersysteem voor identiteit en toegang van Microsoft.  

Intune integreert met Azure AD om tal van scenario’s voor toegangsbeheer mogelijk te maken. U kunt bijvoorbeeld vereisen dat een mobiel apparaat voldoet aan bedrijfsnormen die zijn gedefinieerd in Intune voordat het apparaat toegang krijgt tot bedrijfsservices zoals Exchange. U kunt ook de bedrijfsservice vergrendelen voor een specifieke set mobiele apps. Zo kunt u Exchange Online bijvoorbeeld vergrendelen, zodat deze toepassing alleen toegankelijk is voor Outlook of Outlook Mobile.

## <a name="intune-mobile-app-management-mam-explained"></a>Uitleg over Intune Mobile Application Management (MAM):
Wanneer we het hebben over MAM, bedoelen we de reeks acties die IT-professionals met onze oplossingen kunnen uitvoeren met mobiele apps, zoals:
* Mobiele apps publiceren naar werknemers
* Apps configureren
* Beheren hoe bedrijfsgegevens worden gebruikt en gedeeld in mobiele apps
* Bedrijfsgegevens verwijderen van mobiele apps   
* Mobiele apps bijwerken
* Rapportage over de inventaris van mobiele apps
* Bijhouden van het gebruik van mobiele apps

Soms wordt de term MAM gebruikt om één van deze toepassingen afzonderlijk aan te duiden of om te verwijzen naar een specifieke combinatie ervan. Veelal wordt het concept van app-configuratie (dat wil zeggen, het gebruik van technologieën zoals de [configuratie van beheerde iOS-apps](https://developer.apple.com/library/content/samplecode/sc2279/Introduction/Intro.html)) vermengd met het concept van de beveiliging van bedrijfsgegevens binnen mobiele apps. Dat is omdat sommige mobiele apps instellingen doorgeven waarmee hun functies voor gegevensbescherming kunnen worden geconfigureerd.

In combinatie met besturingssysteemfuncties voor het beveiligen van gegevens (bijvoorbeeld MDM-functies zoals Windows Information Protection in Windows 10) biedt dit veel bescherming voor gegevens op mobiele apparaten.

Als u Intune gebruikt met andere services in EMS, kunt u uw organisatie veel meer beveiliging van mobiele apps bieden dan door het mobiele besturingssysteem en de configuratie van mobiele apps zelf wordt geleverd. Een app die wordt beheerd met EMS heeft toegang tot een uitgebreidere reeks functies voor de bescherming van mobiele apps en gegevens, met onder meer:

* [Eenmalige aanmelding](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-appssoaccess-whatis)  
*   [Multi-Factor Authentication](https://docs.microsoft.com/en-us/multi-factor-authentication/multi-factor-authentication)
* [Voorwaardelijke toegang tot apps (toegang toestaan als de mobiele app bedrijfsgegevens bevat)](https://docs.microsoft.com/en-us/intune/deploy-use/allow-policy-managed-apps-access-to-o365)
* [Het isoleren van bedrijfsgegevens ten opzichte van persoonlijke gegevens binnen dezelfde app](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [App-beveiligingsbeleid (pincode, codering, opslaan als, klembord, enzovoort)](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Bedrijfsgegevens wissen uit een mobiele app](https://docs.microsoft.com/en-us/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
* [Ondersteuning voor Rights Management-services](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-azure-rms)

![Installatiekopie waarin de niveaus van beheer van gegevensbeveiliging voor apps worden weergegeven](./media/managing-mobile-apps.png)

### <a name="intune-mobile-app-security"></a>Beveiliging van mobiele apps met Intune
App-beveiliging is een onderdeel van MAM en wanneer we het in verband met Intune hebben over de beveiliging van mobiele apps, bedoelen we:
* Persoonlijke gegevens geïsoleerd houden van bedrijfsgegevens en IT.
* Beperken van de acties die gebruikers kunnen ondernemen met bedrijfsgegevens, zoals kopiëren, knippen en plakken, opslaan en weergeven.
* Bedrijfsgegevens verwijderen uit mobiele apps, ook wel selectief wissen of zakelijk wissen genoemd.

Een van de manieren waarop Intune beveiliging van mobiele apps biedt, is via de functie voor **app-beveiligingsbeleid**. App-beveiligingsbeleid maakt gebruik van Azure AD-identiteit om bedrijfsgegevens te isoleren van persoonlijke gegevens. Gegevens die toegankelijk zijn met behulp van zakelijke referenties, krijgen extra bedrijfsbeveiliging.

Wanneer gebruikers zich bij hun apparaat aanmelden met behulp van hun zakelijke referenties, hebben ze via hun bedrijfsidentiteit toegang tot gegevens die aan hun persoonlijke identiteit worden geweigerd. Terwijl deze bedrijfsgegevens worden gebruikt, bepaalt Intune samen met andere EMS-technologieën hoe de gegevens worden opgeslagen en gedeeld. Dergelijke beveiligingen worden niet toegepast op gegevens waar gebruikers toegang toe krijgen als ze zich bij hun apparaat aanmelden met hun persoonlijke identiteit. De IT-afdeling heeft zo het beheer over de bedrijfsgegevens, terwijl de eindgebruikers het beheer houden over hun persoonlijke gegevens en de privacy daarvan.

## <a name="emm-with-and-without-device-enrollment"></a>EMM met en zonder apparaatinschrijving
De meeste oplossingen voor het beheer van bedrijfsmobiliteit ondersteunen basistechnologieën voor mobiele apparaten en mobiele apps. Deze zijn meestal gekoppeld aan het apparaat dat wordt ingeschreven in de MDM-oplossing in uw organisatie. Intune biedt ondersteuning voor deze scenario's en ondersteunt daarnaast tal van 'zonder inschrijving'-scenario's.  

In verschillende organisaties worden verschillende 'zonder inschrijving'-scenario's gebruikt. Voor sommige organisaties is apparaatgebruik zonder inschrijving de norm. Andere organisaties staan dit soort scenario’s toe voor begeleidingsapparaten, zoals een persoonlijke tablet. Weer andere organisaties ondersteunen deze scenario’s helemaal niet. Zelfs in het laatste geval, als een organisatie vereist dat alle apparaten van werknemers worden ingeschreven in MDM, ondersteunen deze organisaties meestal 'zonder inschrijving'-scenario's voor uitzendkrachten en leveranciers, en voor andere apparaten waarvoor een specifieke uitzondering geldt.

U kunt de 'zonder inschrijving'-technologie van Intune zelfs gebruiken op ingeschreven apparaten. Een apparaat dat is ingeschreven in MDM kan bijvoorbeeld 'Open-in'-beveiliging hebben die wordt geleverd door het mobiele besturingssysteem. Bovendien kan de IT-afdeling app-beveiligingsbeleid toepassen op met EMS beheerde mobiele apps om de opslaan als-bewerkingen te controleren of om meervoudige verificatie te bieden.

Intune als onderdeel van EMS heeft hulpprogramma's waarmee uw medewerkers hun productiviteit kunnen verhogen terwijl uw bedrijfsgegevens beschermd blijven, ongeacht hoe uw organisatie omgaat met ingeschreven en niet-ingeschreven mobiele apparaten en apps.

## <a name="common-business-problems-that-intune-helps-solve"></a>Algemene bedrijfsproblemen die Intune u helpt op te lossen
De volgende lijst van bedrijfsproblemen is gekoppeld aan meer gedetailleerde informatie over de oplossingen die we kunnen bieden. Alleen voor het laatste item is MDM-registratie vereist als onderdeel van de oplossing:

* [Uw on-premises-e-mail en -gegevens beveiligen, zodat deze veilig kunnen worden geopend vanaf mobiele apparaten](common-ways-to-use-intune.md#Protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Uw Office 365-e-mail en -gegevens beveiligen, zodat deze veilig kunnen worden geopend vanaf mobiele apparaten](common-ways-to-use-intune.md#Protecting-your-Office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Bedrijfstelefoons ter hand stellen aan uw medewerkers](common-ways-to-use-intune.md#Issue-corporate-owned-phones-to-your-information-workers)
* [Een Bring Your Own Device-programma (BYOD) aan alle werknemers aanbieden](common-ways-to-use-intune.md#Offer-a-bring-your-own-device-program-to-all-employees)
* [Uw werknemers in staat stellen Office 365 veilig te gebruiken vanuit een niet-beheerde openbare kiosk](common-ways-to-use-intune.md#Enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Tablets voor beperkt gebruik overhandigen aan taakgerichte werknemers](common-ways-to-use-intune.md#Issue-limited-use-shared-tablets-to-your-task-workers)

### <a name="next-steps"></a>Volgende stappen
* Meer informatie over een aantal [algemene manieren om Intune te gebruiken](common-ways-to-use-intune.md).
* Vertrouwd raken met het product [met een 30-daagse evaluatieversie van Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md).
* Duik in de [technische vereisten en mogelijkheden](/intune/get-started/what-to-know-before-you-start-microsoft-intune) van Intune.



<!--HONumber=Nov16_HO3-->


