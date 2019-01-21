---
title: iOS-apparaatinstellingen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: U kunt instellingen voor iOS-apparaten toevoegen, configureren of maken om functies te beperken, zoals wachtwoordvereisten instellen, het vergrendelingsscherm beheren, ingebouwde apps gebruiken, beperkte of goedgekeurde apps toevoegen, bluetooth-apparaten verwerken, verbinding maken met de cloud voor back-up en opslag, de kioskmodus inschakelen, domeinen toevoegen, en bepalen hoe gebruikers de Safari-webbrowser kunnen gebruiken in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune; seodec18
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: d6fb1c65199b68f7492b1f397c4f6075e345d3e8
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203668"
---
# <a name="ios-device-settings-to-allow-or-restrict-features-using-intune"></a>Met iOS-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op iOS-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, bepaalde apps toe te staan of te beperken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw iOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint
[Maak een apparaatconfiguratieprofiel](device-restrictions-configure.md).

## <a name="general"></a>Algemeen

- **Gebruiksgegevens delen**: Kies **Blokkeren** om te voorkomen dat met het apparaat diagnostische gegevens en gebruiksgegevens worden verzonden naar Apple. **Niet geconfigureerd**: staat toe dat deze gegevens worden verzonden.
  - **Verzending van diagnostische gegevens**: Met **Blokkeren** voorkomt u dat de gebruiker de instelling voor verzending van diagnostische gegevens en app-analyse wijzigt in **Diagnostische gegevens en gebruik** (in Instellingen op het apparaat). Als u deze instelling wilt gebruiken, moet het apparaat in de supervisiemodus staan (iOS 9.3.2+). **Niet geconfigureerd**: staat de gebruiker toe om deze apparaatinstellingen te wijzigen.
- **Schermopname**: Selecteer **Blokkeren** om te voorkomen dat schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. **Niet geconfigureerd**: stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding.
  - **Observatie van extern scherm met de app Klaslokaal (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat de app Klaslokaal het scherm op het apparaat op afstand kan weergeven. Als u deze instelling wilt gebruiken, moet het apparaat in de supervisiemodus staan (iOS 9.3+). **Niet geconfigureerd**: staat de app Apple Classroom toe het scherm weer te geven.
  - **Ongevraagde observatie van scherm met de app Klaslokaal (alleen onder supervisie)**: Wanneer deze optie is ingesteld op **Toestaan**, kunnen docenten het scherm op de iOS-apparaten van leerlingen/studenten met de app Klaslokaal observeren zonder dat de leerlingen/studenten dit weten. Op apparaten van leerlingen/studenten die zijn ingeschreven bij een cursus met de app Classroom, is toestemming voor de docent van deze cursus automatisch ingeschakeld. **Niet geconfigureerd**: blokkeert deze functie.
- **Niet-vertrouwde TLS-certificaten**: Selecteer **Blokkeren** om te voorkomen dat niet-vertrouwde TLS-certificaten (Transport Layer Security) zijn toegestaan op het apparaat. **Niet geconfigureerd**: staat TLS-certificaten toe.
- **Bedrijfsapps vertrouwen**: Selecteer **Blokkeren** om de knop **Ontwikkelaar vertrouwen** op het apparaat te verwijderen in Instellingen > Algemeen > Profielen en apparaatbeheer. **Niet geconfigureerd**: stelt de gebruiker in staat om apps te vertrouwen die niet zijn gedownload uit de App Store.
- **Accountaanpassingen (alleen onder supervisie)**: Wanneer deze optie is ingesteld op **Blokkeren**, kan de gebruiker de apparaatspecifieke instellingen niet bijwerken vanuit de app voor iOS-instellingen. De gebruiker kan dan bijvoorbeeld geen nieuwe apparaataccounts maken, of de gebruikersnaam of het wachtwoord wijzigen. **Niet geconfigureerd**: staat gebruiker toe om deze instellingen te wijzigen.
  Deze functie geldt ook voor instellingen die toegankelijk zijn vanuit de app voor iOS-instellingen, zoals voor e-mail, contactpersonen, agenda, Twitter, en meer. Deze functie geldt niet voor apps met accountinstellingen die niet kunnen worden geconfigureerd in de app voor iOS-instellingen, zoals de Microsoft Outlook-app.
- **Beperkingen inschakelen in de apparaatinstellingen (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat gebruikers beperkingen kunnen inschakelen in de apparaatinstellingen. **Niet geconfigureerd**: staat de gebruiker toe apparaatbeperkingen (zoals ouderlijk toezicht) te configureren op het apparaat.
- **Gebruik van de optie voor het wissen van alle inhoud en instellingen op het apparaat (alleen onder supervisie)**: Selecteer **Blokkeren**, zodat gebruikers de optie voor het wissen van alle inhoud en instellingen op het apparaat niet kunnen gebruiken (alleen onder supervisie). **Niet geconfigureerd**: geeft de gebruiker toegang tot deze instellingen.
- **Wijzigen van apparaatnaam (alleen onder supervisie)**: Selecteer **Blokkeren**, zodat de apparaatnaam niet kan worden gewijzigd. **Niet geconfigureerd**: staat de gebruiker toe om de naam van het apparaat te wijzigen.
- **Wijzigen van de meldingsinstellingen (alleen onder supervisie)**: Selecteer **Blokkeren**, zodat de instellingen voor meldingen niet kunnen worden gewijzigd. **Niet geconfigureerd**: staat de gebruiker toe de meldingsinstellingen voor apparaten te wijzigen.
- **Achtergrond wijzigen (alleen onder supervisie)**: Selecteer **Blokkeren**, zodat de achtergrond niet kan worden gewijzigd. **Niet geconfigureerd**: staat de gebruiker toe om de achtergrond van het apparaat te wijzigen.
- **Wijzigen van de vertrouwensinstellingen voor bedrijfsapps (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat de gebruiker de instellingen voor vertrouwen in bedrijfsapps wijzigt op apparaten in de supervisiemodus. **Niet geconfigureerd**: staat de gebruiker toe om apps te vertrouwen die niet zijn gedownload uit de App Store.
- **Wijzigingen in configuratieprofielen (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat configuratieprofielen op het apparaat kunnen worden gewijzigd. **Niet geconfigureerd**: staat de gebruiker toe om configuratieprofielen te installeren.
- **Activeringsslot (alleen onder supervisie)**: Selecteer **Toestaan** om Activeringsslot op iOS-apparaten in de supervisiemodus in te schakelen. Met Activeringsslot kan een verloren of gestolen apparaat moeilijker opnieuw worden geactiveerd.
- **Verwijdering van apps blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat gebruikers apps verwijderen. **Niet geconfigureerd**: staat gebruikers toe om apps te verwijderen van het apparaat.
- **Beperkte USB-modus blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren** om de beperkte USB-modus uit te schakelen op apparaten in de supervisiemodus. De beperkte USB-modus voorkomt dat USB-apparaten gegevens uitwisselen met een apparaat dat gedurende langer dan een uur is vergrendeld. **Niet geconfigureerd**: staat de beperkte USB-modus toe.
- **Automatisch datum en tijd afdwingen (alleen onder supervisie)**: Met **Vereisen** wordt het instellen van de datum en tijd automatisch afgedwongen op apparaten in de supervisiemodus. De tijdzone van het apparaat wordt bijgewerkt wanneer het apparaat mobiele verbindingen heeft of wanneer Wi-Fi met locatieservices is ingeschakeld voor het apparaat.
- **Vereisen dat leerlingen/studenten toestemming vragen om een cursus in Klaslokaal te verlaten (alleen onder supervisie)**: Met **Vereisen** wordt afgedwongen dat leerlingen/studenten die zijn ingeschreven bij een niet-beheerde cursus met de app Klaslokaal, toestemming aan de docent vragen om de cursus te verlaten. Alleen beschikbaar in iOS 11.3 +. **Niet geconfigureerd**: dwingt niet af dat de leerling/student toestemming vraagt.
- **Draadloze PKI-updates toestaan**: Met **Toestaan** kunnen gebruikers software-updates ontvangen zonder dat hun apparaten zijn aangesloten op een computer.
- **Bijhouden van advertenties beperken**: Selecteer **Beperken** om de advertentie-id van het apparaat uit te schakelen. **Niet geconfigureerd**: houdt deze instelling ingeschakeld.
- **Het maken van VPN's blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat gebruikers instellingen maken voor VPN-configuratie. **Niet geconfigureerd**: stelt gebruikers in staat VPN’s te maken op het apparaat.

## <a name="configurations-requiring-supervision"></a>Configuraties die supervisie vereisen

De supervisiemodus voor iOS kan alleen worden ingeschakeld tijdens de initiële installatie van het apparaat via het Device Enrollment Program van Apple of met behulp van Apple Configurator. Zodra de supervisiemodus is ingeschakeld, kunt u in Intune een apparaat configureren met de volgende functionaliteit:

- App-vergrendeling (modus voor één app) 
- Algemene HTTP-proxy 
- Activeringsslot overslaan 
- Autonome modus voor één app 
- Webinhoudsfilter 
- Achtergrond en vergrendelingsscherm instellen 
- Stille app-push 
- Permanente VPN 
- Installatie van beheerde app exclusief toestaan 
- iBookstore 
- iMessages 
- Game Center 
- AirDrop 
- AirPlay 
- Koppelen aan host 
- Cloudsynchronisatie 
- Zoeken met Spotlight 
- Handoff 
- Apparaat wissen 
- Beperkingen voor gebruikersinterface 
- Installatie van configuratieprofielen per gebruikersinterface 
- Nieuws 
- Sneltoetsen 
- Wijzigingen van de wachtwoordcode 
- Wijzigingen van de apparaatnaam 
- Automatisch downloaden van apps 
- Wijzigingen in Bedrijfsapps vertrouwen 
- Apple Music 
- Binnenkomende e-mail 
- Koppelen aan Apple Watch 

> [!NOTE]
> Apple heeft bevestigd dat bepaalde instellingen worden verplaatst naar alleen onder supervisie in 2019. We raden u aan hiermee rekening te houden wanneer u deze instellingen gebruikt in plaats van dat u wacht totdat Apple deze migreert naar alleen onder supervisie:
> - App-installatie door eindgebruikers
> - App verwijderen
> - FaceTime
> - Safari
> - iTunes
> - Expliciete inhoud
> - iCloud-documenten en -gegevens
> - Games voor meerdere spelers
> - Game Center-vrienden toevoegen
> - Siri

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: Hiermee stelt u dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat. Niet geconfigureerd: geeft gebruikers toegang tot het apparaat zonder dat ze een wachtwoord hoeven in te voeren.
  - **Eenvoudige wachtwoorden**: Selecteer **Blokkeren** om complexere wachtwoorden te vereisen. **Niet geconfigureerd**: staat eenvoudige wachtwoorden toe, zoals `0000` en `1234`.
  - **Vereist wachtwoordtype**: Selecteer het type wachtwoord dat is vereist voor uw organisatie. Uw opties zijn:
    - **Standaardwaarde apparaat**
    - **Numeriek**
    - **Alfanumeriek**
  - **Het aantal niet-alfanumerieke tekens in het wachtwoord**: Geef het aantal symbooltekens op, zoals `#` of `@`, dat het wachtwoord moet bevatten.
  - **Minimale wachtwoordlengte**: Voer de minimale lengte in die een gebruiker moet invoeren (tussen 4 en 14 tekens).
  - **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Geef het aantal mislukte aanmeldingen op dat is toegestaan voordat het apparaat wordt gewist (tussen 1 en 11).
  - **Maximum aantal minuten na schermvergrendeling voordat wachtwoord is vereist**<sup>1</sup>: Geef op hoelang het apparaat inactief blijft voordat gebruikers hun wachtwoord opnieuw moeten invoeren. Als de ingevoerde tijd langer is dan de tijd die is ingesteld op het apparaat, wordt de door u ingevoerde tijd genegeerd. Ondersteund op iOS 8.0-apparaten en nieuwere apparaten.
  - **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**<sup>1</sup>: Voer het maximale aantal minuten van inactiviteit in dat is toegestaan op het apparaat totdat het scherm wordt vergrendeld. Als de ingevoerde tijd langer is dan de tijd die is ingesteld op het apparaat, wordt de door u ingevoerde tijd genegeerd.
  - **Wachtwoordverlooptijd (dagen)**: Geef op na hoeveel dagen het wachtwoord voor het apparaat moet worden gewijzigd.
  - **Wachtwoorden niet opnieuw gebruiken**: Voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt.
  - **Ontgrendelen met vingerafdruk**: Selecteer **Blokkeren** om te voorkomen dat vingerafdrukken kunnen worden gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd**: staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.
- **Wachtwoordcode wijzigen (alleen onder supervisie)**: Selecteer **Blokkeren** om ervoor te zorgen dat de wachtwoordcode niet meer kan worden gewijzigd, toegevoegd of verwijderd. Als deze functie is geblokkeerd worden wijzigingen in de wachtwoordcodebeperkingen genegeerd op apparaten in de supervisiemodus. **Niet geconfigureerd**: staat toe dat wachtwoordcodes worden toegevoegd, gewijzigd of verwijderd.
  - **Wijziging van vingerafdruk (alleen onder supervisie)**: Selecteer **Blokkeren** om ervoor te zorgen dat de gebruiker Touch ID-vingerafdrukken niet meer kan wijzigen, toevoegen of verwijderen. **Niet geconfigureerd**: staat de gebruiker toe de TouchID-vingerafdrukken op het apparaat bij te werken.
- **Automatisch doorvoeren van wachtwoorden blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat de functie Wachtwoorden automatisch invullen wordt gebruikt in iOS. Als u **Blokkeren** kiest, gebeurt ook het volgende:
  - Gebruikers wordt niet meer gevraagd om een wachtwoord te gebruiken dat is opgeslagen in Safari of in een app.
  - Automatische sterke wachtwoorden zijn uitgeschakeld en gebruikers krijgen geen suggesties voor sterke wachtwoorden.

  **Niet geconfigureerd**: staat deze functies toe.

- **Aanvragen voor wachtwoordnabijheid blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren**, zodat het apparaat van een gebruiker geen wachtwoorden aanvraagt van apparaten in de omgeving. **Niet geconfigureerd**: staat deze wachtwoordaanvragen toe.
- **Delen van wachtwoorden blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat wachtwoorden via AirDrop tussen apparaten worden gedeeld. **Niet geconfigureerd**: staat toe dat wachtwoorden worden gedeeld.

<sup>1</sup>Wanneer u de instellingen **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld** en **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen bijvoorbeeld instelt op **vijf** minuten, wordt het scherm na vijf minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens vijf minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat vijf minuten later vergrendeld.

## <a name="locked-screen-experience"></a>Vergrendeld scherm

- **Toegang tot Beheercentrum wanneer het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot de app Beheercentrum te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: verleent gebruikers toegang tot de app Beheercentrum terwijl het apparaat is vergrendeld.
- **Meldingen terwijl het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot meldingen te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: verleent gebruikers toegang tot meldingen terwijl het apparaat is vergrendeld.
- **Wallet-meldingen terwijl het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot de app Wallet te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: geeft de gebruiker toegang tot de app Wallet terwijl het apparaat is vergrendeld.
- **De weergave Vandaag wanneer het apparaat vergrendeld**: Selecteer **Blokkeren** om de toegang tot de weergave Vandaag te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: geeft de gebruiker toegang tot de weergave Vandaag terwijl het apparaat is vergrendeld.

## <a name="app-store-doc-viewing-gaming"></a>App Store, documenten bekijken, gamen

- **App Store**: Selecteer **Blokkeren** om de toegang tot de App Store te blokkeren op apparaten in de supervisiemodus. **Niet geconfigureerd**: geeft gebruikers toegang.
  - **Apps installeren via de App Store (alleen onder supervisie)**: Selecteer **Blokkeren** om de App Store te blokkeren op het startscherm van het apparaat. Eindgebruikers kunnen iTunes nog steeds gebruiken of met Apple Configurator apps installeren. **Niet geconfigureerd**: geeft gebruikers toegang tot de App Store vanaf het startscherm.
  - **Automatisch downloaden van apps (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat apps die zijn gekocht op andere apparaten, automatisch worden gedownload. Dit is niet van invloed op updates voor bestaande apps. **Niet geconfigureerd**: staat gebruikers toe om apps die zijn gekocht op andere iOS-apparaten, te downloaden op het apparaat.
- **Wachtwoord voor toegang tot de App Store**: Selecteer **Vereisen**, zodat gebruikers een wachtwoord moeten invoeren voordat ze naar de App Store kunnen gaan. **Niet geconfigureerd**: geeft gebruikers toegang tot de App Store zonder dat ze een wachtwoord hoeven in te voeren.
- **In-app aankopen**: Selecteer **Blokkeren** om in-app aankopen in de Store te voorkomen. **Niet geconfigureerd**: staat gebruikers toe aankopen in de Store te doen vanuit een actieve app.
- **Expliciete muziek-, podcast- of nieuwsinhoud op iTunes (alleen onder supervisie)**: Selecteer **Blokkeren** om expliciete muziek-, podcast- of nieuwsinhoud op iTunes te blokkeren. **Niet geconfigureerd**: geeft het apparaat toegang tot inhoud voor volwassenen in de Store.
- **Inhoud uit Book Store met de markering Erotisch downloaden**: Selecteer **Blokkeren** om te voorkomen dat gebruikers media downloaden uit de Book Store die is gelabeld als Erotisch. **Niet geconfigureerd**: staat de gebruiker toe om boeken te downloaden uit de categorie Erotisch.
- **Zakelijke documenten weergeven in niet-beheerde apps**: Selecteer **Blokkeren** om te voorkomen dat niet-zakelijke documenten in niet-beheerde apps worden weergegeven. **Niet geconfigureerd**: staat gebruikers toe om zakelijke documenten weer te geven in elke willekeurige app. Voorbeeld: u wilt voorkomen dat gebruikers bestanden uit de OneDrive-app opslaan in Dropbox. Configureer deze instelling als **Blokkeren**. Nadat het apparaat het beleid heeft ontvangen (bijvoorbeeld nadat het opnieuw is opgestart), kunnen er geen bestanden meer worden opgeslagen.
  - **Toestaan dat beheerde apps contactpersonen doorgeven aan niet-beheerde accounts voor contactpersonen (alleen onder supervisie)**: Wanneer deze optie is ingesteld op **Toestaan**, kunnen gebruikers de contactinformatie in Outlook van een persoon, zoals zakelijke contactpersonen, toevoegen aan of synchroniseren met de ingebouwde Contacten-app op het apparaat. Wanneer deze optie is ingesteld op **Niet geconfigureerd**, kunnen gebruikers geen contactpersonen in Outlook toevoegen aan de ingebouwde Contacten-app op het apparaat.
  
    Als u deze instelling wilt gebruiken, stelt u **Zakelijke documenten weergeven in niet-beheerde apps** in op **Blokkeren**.
  
- **Niet-zakelijke documenten weergeven in zakelijke apps**: Met **Blokkeren** voorkomt u dat niet-zakelijke documenten in zakelijke apps worden weergegeven. **Niet geconfigureerd**: staat gebruikers toe elk willekeurig document weer te geven in zakelijke beheerde apps.
  - **Toestaan dat niet-beheerde apps contactpersonen lezen in beheerde accounts voor contactpersonen (alleen onder supervisie)**: Wanneer deze optie is ingesteld op **Toestaan**, kunnen gebruikers de contactgegevens van een persoon in de app Contacten toevoegen aan Outlook. Wanneer deze optie is ingesteld op **Niet geconfigureerd**, wordt het lezen en het verwijderen van dubbele contactpersonen uit de ingebouwde app Contacten op het apparaat voorkomen.
  
    Als u deze instelling wilt gebruiken, stelt u **Niet-zakelijke documenten weergeven in zakelijke apps** in op **Blokkeren**.
  
- **AirDrop behandelen als een onbeheerd doel**: Wanneer deze optie is ingesteld op **Vereisen**, wordt AirDrop beschouwd als een onbeheerde bestemming. Het zorgt ervoor dat via beheerde apps geen gegevens meer kunnen worden verzonden met behulp van AirDrop. 
- **Game Center-vrienden toevoegen (alleen onder supervisie)**: Met **Blokkeren** voorkomt u dat gebruikers vrienden kunnen toevoegen in Game Center. **Niet geconfigureerd**: staat de gebruiker toe om vrienden toe te voegen in Game Center.
- **Game Center (alleen onder supervisie)**: Met **Blokkeren** blokkeert u het gebruik van de Game Center-app. **Niet geconfigureerd**: staat gebruik van de app Game Center toe op het apparaat.
- **Gamen met meerdere spelers (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat gebruikers kunnen gamen met meerdere spelers. **Niet geconfigureerd**: staat de gebruiker toe om games voor meerdere spelers te spelen op het apparaat.
- **Regio voor restricties**: Selecteer de regio voor restricties die u wilt gebruiken voor toegestane downloads. En kies vervolgens de toegestane beoordelingen voor **Films** en **Tv-shows**.
- **Apps**: Selecteer de toegestane leeftijdscategorie van apps die gebruikers kunnen downloaden of kies **Alle apps toestaan**.

## <a name="built-in-apps"></a>Ingebouwde apps

- **Camera**: Met **Blokkeren** voorkomt u toegang tot de camera op het apparaat. **Niet geconfigureerd**: staat toegang tot de camera van het apparaat toe.
  - **FaceTime**: Met **Blokkeren** voorkomt u toegang tot de app FaceTime. **Niet geconfigureerd**: staat toegang tot de app FaceTime toe.
- **Siri**: Met **Blokkeren** voorkomt u toegang tot Siri. **Niet geconfigureerd**: staat toegang tot de spraakassistent Siri toe op het apparaat.
  - **Siri als het apparaat is vergrendeld**: Selecteer **Blokkeren** om te toegang tot Siri te blokkeren wanneer het apparaat is vergrendeld. **Niet geconfigureerd**: staat toegang tot de spraakassistent Siri toe op het apparaat wanneer het is vergrendeld.
  - **Siri-filter voor scheldwoorden (alleen onder supervisie)**: Met **Vereisen** voorkomt u dat grove taal wordt gedicteerd of uitgesproken door Siri.
  - **Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat Siri toegang tot websites krijgt om vragen te beantwoorden. **Niet geconfigureerd**: staat Siri toe om door gebruikers gegenereerde inhoud te raadplegen op internet.
- **Apple News (alleen onder supervisie)**: Selecteer **Blokkeren** om toegang tot de app Apple News op het apparaat te blokkeren. **Niet geconfigureerd**: staat het gebruik van de app Apple News toe.
- **Book Store (alleen onder supervisie)**: Selecteer **Blokkeren** om toegang tot de Book Store op het apparaat te blokkeren. **Niet geconfigureerd**: staat gebruikers toe te zoeken naar boeken en deze te kopen in de iBooks Store.
- **De app Berichten op het apparaat (alleen onder supervisie)**: Selecteer **Blokkeren** om toegang tot de app Berichten op het apparaat te blokkeren. **Niet geconfigureerd**: staat het gebruik van de app Berichten toe voor het verzenden en lezen van sms-berichten.
- **Podcasts (alleen onder supervisie)**: Selecteer **Blokkeren** om toegang tot de app Podcasts op het apparaat te blokkeren. **Niet geconfigureerd**: staat het gebruik van de app Podcasts toe.
- **Muziek-service (alleen onder supervisie)**: Met **Blokkeren** keert u terug naar de klassieke modus van de app Muziek en wordt de Muziek-service uitgeschakeld. **Niet geconfigureerd**: staat het gebruik van de app Apple Music toe.
- **iTunes Radio-service (alleen onder supervisie)**: Selecteer **Blokkeren** om toegang tot de app iTunes Radio op het apparaat te blokkeren. **Niet geconfigureerd**: staat het gebruik van de app iTunes Radio toe.
- **Wijzigingen in de instellingen van de app Zoek vrienden (alleen onder supervisie)**: Met **Blokkeren** voorkomt u wijzigingen in de instellingen van de app Zoek vrienden. **Niet geconfigureerd**: staat de gebruiker toe de instellingen van de app Zoek vrienden te wijzigen.
- **Zoeken met Spotlight resultaten laten retourneren van internet (alleen onder supervisie):** Met **Blokkeren** zorgt u ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd**: staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.
- **Verwijderen van systeem-apps van het apparaat blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat systeem-apps van het apparaat worden verwijderd. **Niet geconfigureerd**: staat gebruikers toe om systeemapps te verwijderen.

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

- **Niet-toegestane apps**: Een lijst met apps die niet worden beheerd in Intune waarvan u niet wilt dat deze op het apparaat worden geïnstalleerd. Als een gebruiker een app uit deze lijst installeert, ontvangt u een melding van Intune.
- **Goedgekeurde apps**: Een lijst met apps die gebruikers mogen installeren. Om te voldoen aan het beleid, mogen gebruikers geen andere apps installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Als een gebruiker een app uit deze lijst installeert, ontvangt u een melding van Intune.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- De App Store-URL van de gewenste iTunes-app **toevoegen**. Voer bijvoorbeeld `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

- Importeer een CSV-bestand met details over de app, inclusief de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. Of exporteer een bestaande lijst die de beperkte apps bevat in dezelfde indeling.

> [!IMPORTANT]
> Apparaatprofielen die instellingen voor beperkte apps gebruiken, moeten worden toegewezen aan groepen gebruikers.

## <a name="show-or-hide-apps-supervised-only"></a>Apps weergeven of verbergen (alleen onder supervisie)

In de lijst Apps weergeven of verbergen kunt u een van de volgende lijsten configureren op apparaten in de supervisiemodus met iOS 9.3 of hoger.

- **Verborgen apps**: Voer een lijst met apps in die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of openen.
- **Zichtbare apps**: Voer een lijst met apps in die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- De App Store-URL van de gewenste iTunes-app **toevoegen**. Voer bijvoorbeeld `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

- Importeer een CSV-bestand met details over de app, inclusief de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. Of exporteer een bestaande lijst die de beperkte apps bevat in dezelfde indeling.

## <a name="wireless"></a>Draadloos

- **Dataroaming**: Selecteer **Blokkeren** om dataroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd**: staat dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Op de achtergrond ophalen tijdens roaming**: Met **Blokkeren** voorkomt u dat gegevens tijdens roaming op de achtergrond kunnen worden opgehaald via het mobiele netwerk. **Niet geconfigureerd**: staat het apparaat toe om gegevens zoals e-mail op te halen tijdens roaming op een mobiel netwerk.
- **Voicedialing**: Selecteer **Blokkeren** om te voorkomen dat gebruikers de functie Voicedialing op het apparaat kunnen gebruiken. **Niet geconfigureerd**: hiermee wordt Nummer inspreken toegestaan op het apparaat.
- **Gespreksroaming**: Selecteer **Blokkeren** om gespreksroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd**: staat spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Wijzigingen in de instellingen voor het gebruik van mobiel dataverkeer voor apps (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat er wijzigingen kunnen worden aangebracht in de instellingen voor het gebruik van mobiel dataverkeer voor apps. **Niet geconfigureerd**: staat de gebruiker toe om te bepalen welke apps mobiel dataverkeer mogen gebruiken.
- **Persoonlijke hotspot**: Selecteer **Blokkeren** om te voorkomen dat het apparaat wordt gebruikt als een persoonlijke hotspot. Mogelijk is deze instelling niet compatibel met bepaalde providers. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Toevoegen aan Wi-Fi-netwerken die alleen configuratieprofielen gebruiken (alleen onder supervisie)**: Met **Vereisen** dwingt u af dat het apparaat alleen Wi-Fi-netwerken gebruikt die zijn ingesteld via Intune-configuratieprofielen. **Niet geconfigureerd**: staat het apparaat toe andere Wi-Fi-netwerken te gebruiken.
- **Regels voor mobiel gebruik (alleen beheerde apps)**: Definieer de gegevenstypen die beheerde apps kunnen gebruiken die zijn verbonden met een mobiel netwerk. Uw opties zijn:
  - **Gebruik van mobiel dataverkeer blokkeren**: U kunt het gebruik van mobiel dataverkeer blokkeren voor **Alle beheerde apps** of u kunt **specifieke apps kiezen**.
  - **Gebruik van mobiel dataverkeer tijdens roaming blokkeren**: U kunt het gebruik van mobiel dataverkeer tijdens roaming blokkeren voor **Alle beheerde apps** of u kunt **specifieke apps** kiezen.

## <a name="connected-devices"></a>Verbonden apparaten

- **AirDrop (alleen onder supervisie)**: Selecteer **Blokkeren** om het gebruik van AirDrop op het apparaat te voorkomen. **Niet geconfigureerd**: staat het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
- **Koppelen met Apple Watch (alleen onder supervisie)**: Selecteer **Blokkeren** om koppeling met een Apple Watch te voorkomen. **Niet geconfigureerd**: staat toe dat het apparaat wordt gekoppeld aan een Apple Watch.
- **Draagdetectie voor een gekoppelde Apple Watch**: Als u **Vereisen** selecteert, moet de gekoppelde Apple Watch de functie Draagdetectie gebruiken. Wanneer dit is vereist, worden op de Apple Watch geen meldingen weergegeven wanneer deze niet wordt gedragen. 
- **Bluetooth-aanpassingen (alleen onder supervisie)**: Selecteer **Blokkeren** om ervoor te zorgen dat de eindgebruiker geen Bluetooth-instellingen meer kan wijzigen op het apparaat. **Niet geconfigureerd**: staat de gebruiker toe om deze instellingen te wijzigen.
- **Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld (alleen onder supervisie)**: Met **Niet geconfigureerd** staat u het koppelen met een host toe, waarmee de beheerder kan bepalen aan welke apparaten een iOS-apparaat kan worden gekoppeld. **Blokkeren**: voorkomt het koppelen met een host.
- **Wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**: Met **Vereisen** stelt u in dat een wachtwoord voor koppelen is vereist wanneer AirPlay wordt gebruikt om inhoud te streamen naar andere Apple-apparaten. **Niet geconfigureerd**: staat de gebruiker toe inhoud te streamen met AirPlay zonder een wachtwoord in te voeren.
- **AirPrint blokkeren (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat de functie AirPrint wordt gebruikt op het apparaat. **Niet geconfigureerd**: staat de gebruiker toe AirPrint te gebruiken.
  - **Opslag van AirPrint-referenties in de Sleutelhanger blokkeren (alleen onder supervisie)**: Met **Blokkeren** voorkomt u het gebruik van de Sleutelhanger om de gebruikersnaam en het wachtwoord op te slaan op het apparaat. **Niet geconfigureerd**: staat toe dat de gebruikersnaam en het wachtwoord van AirPrint worden opgeslagen in de app Sleutelhanger.
  - **Een vertrouwd TLS-certificaat vereisen voor AirPrint (alleen onder supervisie)**: Met **Vereisen** dwingt u af dat op het apparaat vertrouwde certificaten worden gebruikt voor TLS-afdrukcommunicatie.
  - **iBeacon-detectie van AirPrint-printers blokkeren (alleen onder supervisie)**: Met **Blokkeren** voorkomt u phishing met schadelijke AirPrint Bluetooth-bakens voor netwerkverkeer. **Niet geconfigureerd**: staat het adverteren van AirPrint-printers op het apparaat toe.

## <a name="keyboard-and-dictionary"></a>Toetsenbord en woordenlijst

- **Opzoeken van definities van woorden (alleen onder supervisie)**: Met **Blokkeren** voorkomt u dat de gebruiker een woord markeert en vervolgens de definitie ervan opzoekt op het apparaat. **Niet geconfigureerd**: geeft toegang tot de functie Opzoeken van definities van woorden.
- **Tekstvoorspelling (alleen onder supervisie)**: Met **Niet geconfigureerd** staat u het gebruik van tekstvoorspelling toe voor suggesties voor woorden die de gebruiker mogelijk wil invoeren. Met **Blokkeren** wordt deze functie geblokkeerd.
- **Autocorrectie (alleen onder supervisie)**: Met **Niet gecorrigeerd** staat u automatische correctie van verkeerd gespelde woorden toe op het apparaat. **Blokkeren**: blokkeert het gebruik van Autocorrectie.
- **Spellingcontrole (alleen onder supervisie)**: Met **Niet geconfigureerd** kan de gebruiker spellingcontrole op het apparaat gebruiken. **Blokkeren**: staat de spellingcontrole toe.
- **Sneltoetsen (alleen onder supervisie)**: Met **Niet geconfigureerd** staat u het gebruik van sneltoetsen toe op het apparaat. **Blokkeren**: zorgt ervoor dat de gebruiker geen sneltoetsen meer kan gebruiken.
- **Dicteren (alleen onder supervisie)**: Met **Blokkeren** zorgt u ervoor dat de gebruiker geen spraak meer kan gebruiken om tekst in te voeren. **Niet geconfigureerd**: staat de gebruiker toe invoer van Dicteren te gebruiken.

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Back-up naar iCloud**: Met **Niet geconfigureerd** staat u de gebruiker toe een back-up van het apparaat op te slaan in iCloud. **Blokkeren**: zorgt ervoor dat de gebruiker geen back-ups van het apparaat meer kan opslaan in iCloud.
- **Documenten synchroniseren met iCloud (alleen onder supervisie)**: Met **Niet geconfigureerd** staat u het synchroniseren van documenten en sleutelwaarden met uw iCloud-opslagruimte toe. **Blokkeren**: voorkomt dat documenten en gegevens worden gesynchroniseerd met iCloud.
- **Photo Stream synchroniseren met iCloud**: Met **Niet geconfigureerd** stelt u gebruikers in staat **Mijn fotostream** in te schakelen op hun apparaat om te synchroniseren met iCloud, en foto's weer te geven op alle apparaten van de gebruikers. **Blokkeren**: voorkomt dat met Photo Stream foto’s worden gesynchroniseerd met iCloud.
- **Versleutelde back-up**: Selecteer **Vereisen** om ervoor te zorgen dat back-ups van het apparaat moeten worden versleuteld.
- **iCloud-fotobibliotheek**: Selecteer **Blokkeren** om het gebruik van de iCloud-fotobibliotheek voor het opslaan van foto's en video's in de cloud uit te schakelen. Foto's die niet volledig naar het apparaat zijn gedownload vanaf de iCloud-fotobibliotheek, worden van het apparaat verwijderd. **Niet geconfigureerd**: staat het gebruik van de iCloud-fotobibliotheek toe.
- **Beheerde apps synchroniseren met de cloud**: Met **Niet geconfigureerd** staat u toe dat in door Intune beheerde apps gegevens kunnen worden gesynchroniseerd naar het iCloud-account van de gebruiker. **Blokkeren**: voorkomt deze gegevenssynchronisatie naar iCloud.
- **Gedeelde fotostream**: Selecteer **Blokkeren** om **iCloud-fotodeling** uit te schakelen op het apparaat. **Niet geconfigureerd**: staat streaming van gedeelde foto’s toe.
- **Voortzetting van activiteit**: Met **Niet geconfigureerd** staat u gebruikers toe op een ander iOS- of macOS-apparaat door te gaan met werk waaraan ze zijn begonnen op een iOS-apparaat (Handoff). **Blokkeren**: voorkomt deze handoff.
- **Synchronisatie van iCloud-sleutelhanger blokkeren**: Selecteer **Blokkeren** om het synchroniseren van referenties die zijn opgeslagen in de Sleutelhanger, naar iCloud uit te schakelen. **Niet geconfigureerd**: staat gebruikers toe deze referenties te synchroniseren.
- **Back-ups van Enterprise Book blokkeren**: Selecteer **Blokkeren** om te voorkomen dat gebruikers back-ups maken van Enterprise Book-boeken. **Niet geconfigureerd**: staat gebruikers toe om back-ups te maken van deze boeken.
- **Synchronisatie van metagegevens van Enterprise Book blokkeren (notities en markeringen)**: Met **Blokkeren** voorkomt u dat notities en markeringen in Enterprise Book-boeken worden gesynchroniseerd. **Niet geconfigureerd**: staat synchronisatie toe.

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonome modus voor enkele toepassing (alleen onder toezicht)

Gebruik deze instellingen om iOS-apparaten zodanig te configureren dat hierop specifieke apps in de autonome één-app-modus worden uitgevoerd. Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld. Alleen deze ene app kan worden uitgevoerd. Voeg bijvoorbeeld een app toe waarmee gebruikers een test kunnen uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

Ga op een van de volgende manieren te werk om apps toe te voegen:

- Voer de **App-naam** en **App-bundel-id** in, en selecteer **Toevoegen**. [Verwijzing met bundel-id’s voor ingebouwde iOS-apps](#bundle-id-reference-for-built-in-ios-apps) (in dit artikel) bevat enkele apps met de bijbehorende id’s.
- **Importeer** een CSV-bestand met de lijst met app-namen en de bijbehorende bundel-id’s. Of **Exporteer** een bestaande lijst die de apps bevat.

## <a name="kiosk-supervised-only"></a>Kiosk (alleen onder toezicht)

- **App uitvoeren in kioskmodus**: Selecteer het type apps dat u wilt uitvoeren in de kioskmodus. Uw opties zijn: 
  - **Store-app**: Voer de URL in voor een app in de iTunes App Store
  - **Beheerde app**: Selecteer een app die u hebt toegevoegd aan Intune
  - **Ingebouwde app**: Voer de [bundel-id](#bundle-id-reference-for-built-in-ios-apps) in van de ingebouwde app

- **Ondersteunende aanraking**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Ondersteunende aanraking op het apparaat te vereisen. Deze functie helpt gebruikers bij schermbewegingen die mogelijk moeilijk zijn voor hen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Keer kleuren om**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Keer kleuren om in te stellen, zodat gebruikers met een beperkt gezichtsvermogen de display kunnen wijzigen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Mono-audio**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Mono-audio op het apparaat te vereisen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **VoiceOver**: Selecteer **Vereisen** om de toegankelijkheidsinstelling VoiceOver te vereisen op het apparaat om tekst op het scherm hardop voor te lezen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Zoomen**: Selecteer **Vereisen**, zodat gebruikers met behulp van aanraken het scherm kunnen inzoomen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Automatisch vergrendelen**: Selecteer **Toestaan** voor automatische vergrendeling van het apparaat. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Schakelaar voor belsignaal**: Selecteer **Toestaan** om de schakelaar voor het belsignaal (dempen) op het apparaat in te stellen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Scherm draaien**: Selecteer **Toestaan** om het scherm te draaien wanneer de gebruiker het apparaat draait. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Schermsluimerknop**: Selecteer **Toestaan** om de knop voor slaapstand/ontwaken van het scherm op het apparaat uit te schakelen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is ingeschakeld.
- **Aanraken**: Met **Blokkeren** wordt het aanraakscherm uitgeschakeld op het apparaat. **Niet geconfigureerd**: staat de gebruiker toe het aanraakscherm te gebruiken.
- **Volumeknoppen**: Selecteer **Toestaan**, zodat gebruikers de volumeknoppen op het apparaat kunnen gebruiken. **Niet geconfigureerd**: zorgt ervoor dat de volumeknoppen zijn uitgeschakeld.
- **Besturingselement voor ondersteunende aanraking**: Selecteer **Toestaan**, zodat gebruikers de functie Ondersteunende aanraking kunnen gebruiken. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Besturingselement voor kleuren omkeren**: Met **Toestaan** staat u aanpassingen in de functie Keer kleuren om toe, zodat gebruikers deze functie kunnen aanpassen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Geselecteerde tekst uitspreken**: Selecteer **Toestaan** om de toegankelijkheidsinstellingen Selectie uitspreken op het apparaat toe te staan. Met deze functie wordt tekst die de gebruiker selecteert, hardop gelezen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Besturingselement voor VoiceOver**: Selecteer **Toestaan**, zodat gebruikers de functie VoiceOver kunnen bijwerken, bijvoorbeeld hoe snel schermtekst hardop wordt gelezen. **Niet geconfigureerd**: voorkomt wijzigingen in Voice-over.
- **Besturingselement voor zoomen**: Selecteer **Toestaan**, zodat gebruikers de zoominstelling kunnen aanpassen. **Niet geconfigureerd**: voorkomt wijzigingen in Inzoomen.

> [!NOTE]
> Voordat u een iOS-apparaat voor de kioskmodus kunt configureren, moet u het hulpprogramma Apple Configurator of het Device Enrollment Program van Apple gebruiken om het apparaat in de supervisiemodus te plaatsen. Raadpleeg de handleiding van Apple voor het gebruik van het hulpprogramma Apple Configurator.
> Als de iOS-app die u invoert, wordt geïnstalleerd nadat u het profiel hebt toegewezen, wordt de kioskmodus van het apparaat pas geactiveerd nadat het opnieuw is opgestart.

## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Lijst van bundel-id's voor ingebouwde iOS-apps

Deze lijst bevat de bundel-id's van een aantal algemene ingebouwde iOS-apps. Als u de bundel-ID van andere apps wilt weten, neemt u contact op met de softwareleverancier.

| Bundel-id                   | App-naam     | Uitgever |
|-----------------------------|--------------|-----------|
| com.apple.AppStore          | App Store    | Apple     |
| com.apple.calculator        | Rekenmachine   | Apple     |
| com.apple.mobilecal         | Kalender     | Apple     |
| com.apple.camera            | Camera       | Apple     |
| com.apple.mobiletimer       | Klok        | Apple     |
| com.apple.compass           | Kompas      | Apple     |
| com.apple.MobileAddressBook | Contactpersonen     | Apple     |
| com.apple.facetime          | FaceTime     | Apple     |
| com.apple.mobileme.fmf1     | Zoek vrienden | Apple     |
| com.apple.mobileme.fmip1    | Zoek mijn iPhone  | Apple     |
| com.apple.gamecenter        | Game Center  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Status       | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.MobileStore       | iTunes Store | Apple     |
| com.Apple.itunesu           | iTunes U     | Apple     |
| com.apple.Keynote           | Keynote      | Apple     |
| com.Apple.mobilemail        | Mail         | Apple     |
| com.apple.Maps              | Kaarten         | Apple     |
| com.apple.MobileSMS         | Berichten     | Apple     |
| com.apple.Music             | Music        | Apple     |
| com.apple.news              | Nieuws         | Apple     |
| com.apple.mobilenotes       | Opmerkingen        | Apple     |
| com.apple.Numbers           | Getallen      | Apple     |
| com.apple.Pages             | Pages        | Apple     |
| com.apple.Photo-Booth       | Photo Booth  | Apple     |
| com.apple.mobileslideshow   | Foto's       | Apple     |
| com.apple.podcasts          | Podcasts     | Apple     |
| com.apple.reminders         | Herinneringen    | Apple     |
| com.apple.MobileSafari      | Safari       | Apple     |
| com.apple.Preferences       | Instellingen     | Apple     |
| com.apple.stocks            | Aandelen       | Apple     |
| com.apple.tips              | Tips         | Apple     |
| com.apple.videos            | Video 's       | Apple     |
| com.apple.VoiceMemos        | Dictafoon   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Watch        | Apple     |
| com.apple.weather           | Weer      | Apple     |

## <a name="safari"></a>Safari

- **Safari (alleen onder supervisie)**: Selecteer **Blokkeren** om te voorkomen dat gebruikers de Safari-browser op het apparaat kunnen gebruiken. **Niet geconfigureerd**: staat gebruikers toe de Safari-browser te gebruiken.
- **Automatisch invullen**: Selecteer **Blokkeren** om de functie Automatisch invullen in Safari op het apparaat uit te schakelen. **Niet geconfigureerd**: staat gebruikers toe de instellingen voor automatisch doorvoeren te wijzigen in de webbrowser.
- **Cookies**: Kies hoe cookies moeten worden verwerkt op het apparaat. Uw opties zijn:
  - Toestaan
  - Alle cookies blokkeren
  - Cookies van bezochte websites toestaan
  - Cookies van huidige website toestaan
- **JavaScript**: Met **Blokkeren** voorkomt u dat Java-scripts worden uitgevoerd in de browser op het apparaat. **Niet geconfigureerd**: staat Java-scripts toe.
- **Fraudewaarschuwingen**: Als u **Vereisen** selecteert, worden fraudewaarschuwingen weergegeven in de webbrowser op het apparaat. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Pop-ups**: Als u **Blokkeren** selecteert, wordt het gebruik van de pop-upblokkering in de webbrowser uitgeschakeld. **Niet geconfigureerd**: staat de pop-upblokkering toe.

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Niet-gemarkeerde e-maildomeinen

Voeg in **E-maildomein-URL** een of meer URL's toe aan de lijst. Wanneer eindgebruikers een e-mail ontvangen die afkomstig is van een ander domein dan de domeinen die u invoert, wordt de e-mail in de iOS Mail-app gemarkeerd als niet-vertrouwd.

### <a name="managed-web-domains"></a>Beheerde webdomeinen

Voeg in **Webdomein-URL** een of meer URL's toe aan de lijst. Wanneer documenten worden gedownload uit de domeinen die u invoert, worden ze beschouwd als beheerd. Deze instelling geldt alleen voor documenten die zijn gedownload met Safari.

### <a name="safari-password-autofill-domains"></a>Domeinen voor automatisch invullen van Safari-wachtwoorden

Voeg in **Domein-URL** een of meer URL's toe aan de lijst. Gebruikers kunnen in deze lijst alleen webwachtwoorden van URL's opslaan. Deze instelling geldt alleen voor Safari en voor apparaten met iOS 9.3 en hoger in de modus supervisie. Als u geen URL's opgeeft, kunnen wachtwoorden van alle websites worden opgeslagen.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook apparaatbeperkingen en instellingen opgeven op [macOS](device-restrictions-macos.md)-apparaten.
