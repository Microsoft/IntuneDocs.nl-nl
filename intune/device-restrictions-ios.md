---
title: iOS-apparaatinstellingen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: U kunt instellingen voor iOS-apparaten toevoegen, configureren of maken om functies te beperken, zoals wachtwoordvereisten instellen, het vergrendelingsscherm beheren, ingebouwde apps gebruiken, beperkte of goedgekeurde apps toevoegen, bluetooth-apparaten verwerken, verbinding maken met de cloud voor back-up en opslag, de kioskmodus inschakelen, domeinen toevoegen, en bepalen hoe gebruikers de Safari-webbrowser kunnen gebruiken in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0d0623e9d12132ac470813d65510bc2c76379109
ms.sourcegitcommit: 79baf89e4a7a7b1cecb8ccf5cb976736ae6a7286
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2019
ms.locfileid: "58871468"
---
# <a name="ios-device-settings-to-allow-or-restrict-features-using-intune"></a>Met iOS-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op iOS-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, bepaalde apps toe te staan of te beperken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw iOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een configuratieprofiel voor apparaatbeperkingen](device-restrictions-configure.md#create-the-profile).

## <a name="general"></a>Algemeen

- **Gebruiksgegevens delen**: kies **Blokkeren** om te voorkomen dat met het apparaat diagnostische gegevens en gebruiksgegevens worden verzonden naar Apple. **Niet geconfigureerd** (standaard): staat toe dat deze gegevens worden verzonden.
  - **Aanpassing van de instellingen voor het verzenden van diagnostische gegevens (alleen onder supervisie)**: Met **Blokkeren** voorkomt u dat de gebruiker de instellingen voor verzending van diagnostische gegevens en app-analyse kan wijzigen in **Diagnostische gegevens en gebruik** (instellingen op het apparaat). **Niet geconfigureerd** (standaard): staat de gebruiker toe om deze apparaatinstellingen te wijzigen.

    Deze functie is van toepassing op:  
    - iOS 9.3.2 en hoger

- **Schermafbeeldingen**: kies **Blokkeren** om te voorkomen dat schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. In iOS 9.0 en hoger omvat dit ook het blokkeren van video-opnamen van het scherm. **Niet geconfigureerd** (standaard): stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding of video.
  - **Observatie van extern scherm met de app Classroom (alleen onder supervisie)**: kies **Blokkeren** om te voorkomen dat het scherm van het apparaat extern kan worden weergegeven via de app Classroom. **Niet geconfigureerd** (standaard): staat de app Apple Classroom toe het scherm weer te geven.

    Deze functie is van toepassing op:  
    - iOS 9.3 en hoger

  - **Ongevraagde observatie van scherm met de app Classroom (alleen onder supervisie)**: indien ingesteld op **Toestaan**, kunnen docenten het scherm op de iOS-apparaten van leerlingen/studenten met de app Classroom observeren zonder dat de leerlingen/studenten dit weten. Op apparaten van leerlingen/studenten die zijn ingeschreven bij een cursus met de app Classroom, is toestemming voor de docent van deze cursus automatisch ingeschakeld. Met **Niet geconfigureerd** (standaard) voorkomt u deze functie.
- **Niet-vertrouwde TLS-certificaten**: kies **Blokkeren** om te voorkomen dat niet-vertrouwde TLS-certificaten (Transport Layer Security) zijn toegestaan op het apparaat. Met **Niet geconfigureerd** (standaard) staat u TLS-certificaten toe.
- **Bedrijfsapps vertrouwen**: kies **Blokkeren** om de knop **Ontwikkelaar vertrouwen** op het apparaat te verwijderen in Instellingen > Algemeen > Profielen en apparaatbeheer. **Niet geconfigureerd** (standaard): stelt de gebruiker in staat om apps te vertrouwen die niet zijn gedownload uit de App Store.
- **Accountaanpassingen (alleen onder supervisie)**: wanneer dit is ingesteld op **Blokkeren**, kan de gebruiker de apparaatspecifieke instellingen niet bijwerken vanuit de app voor iOS-instellingen. De gebruiker kan dan bijvoorbeeld geen nieuwe apparaataccounts maken, of de gebruikersnaam of het wachtwoord wijzigen. **Niet geconfigureerd** (standaard): staat gebruiker toe om deze instellingen te wijzigen.

  Deze functie geldt ook voor instellingen die toegankelijk zijn vanuit de app voor iOS-instellingen, zoals voor e-mail, contactpersonen, agenda, Twitter, en meer. Deze functie geldt niet voor apps met accountinstellingen die niet kunnen worden geconfigureerd in de app voor iOS-instellingen, zoals de Microsoft Outlook-app.
- **Schermtijd (alleen onder supervisie)**: kies **Blokkeren** om te voorkomen dat gebruikers hun eigen beperkingen in Schermtijd instellen (instellingen op het apparaat). Met **Niet geconfigureerd** kan de gebruiker apparaatbeperkingen (zoals ouderlijk toezicht, inhoudsbeperkingen en privacybeperkingen) configureren op het apparaat.

  Deze instelling heette eerst **Beperkingen inschakelen in de apparaatinstellingen**. Gevolgen van deze wijziging:  
  
  - iOS 11.4.1 en eerder: **Blokkeren** voorkomt dat eindgebruikers hun eigen beperkingen kunnen instellen bij de apparaatinstellingen. Dit is hetzelfde, en er zijn geen wijzigingen voor eindgebruikers.
  - iOS 12.0 en later: **Blokkeren** voorkomt dat eindgebruikers hun eigen **Schermtijd** kunnen instellen bij de apparaatinstellingen (Instellingen > Algemeen > Schermtijd), waaronder inhouds- en privacybeperkingen. Apparaten die zijn geüpgraded naar iOS 12.0 krijgen het tabblad Beperkingen niet meer te zien bij de apparaatinstellingen (Instellingen > Algemeen > Apparaatbeheer > Beheerprofiel > Beperkingen). Deze instellingen vindt u onder **Schermtijd**.
  
- **Gebruik van de optie voor het wissen van alle inhoud en instellingen op het apparaat (alleen onder supervisie)**: kies **Blokkeren** zodat gebruikers de optie voor het wissen van alle inhoud en instellingen op het apparaat niet kunnen gebruiken (alleen onder supervisie). **Niet geconfigureerd** (standaard): geeft de gebruiker toegang tot deze instellingen.
- **Apparaatnaam wijzigen (alleen onder supervisie)**: kies **Blokkeren** zodat de naam van het apparaat niet kan worden gewijzigd. **Niet geconfigureerd** (standaard): staat de gebruiker toe om de naam van het apparaat te wijzigen.
- **Aanpassing van meldingsinstellingen (alleen onder supervisie)**: kies **Blokkeren** zodat de meldingsinstellingen niet kunnen worden gewijzigd. **Niet geconfigureerd** (standaard): staat de gebruiker toe de meldingsinstellingen voor apparaten te wijzigen.
- **Aanpassing van achtergrond (alleen onder supervisie)**: **Blokkeren** voorkomt dat de achtergrond kan worden gewijzigd. **Niet geconfigureerd** (standaard): staat de gebruiker toe om d achtergrond van het apparaat te wijzigen.
- **Wijzigen van de vertrouwensinstellingen voor bedrijfsapps (alleen onder supervisie)**: **Blokkeren** voorkomt dat de gebruiker de instellingen voor bedrijfsapps vertrouwen wijzigt op apparaten in de supervisiemodus. **Niet geconfigureerd** (standaard): staat de gebruiker toe om apps te vertrouwen die niet zijn gedownload uit de App Store.
- **Wijzigingen in configuratieprofielen (alleen onder supervisie)**: **Blokkeren** voorkomt wijzigingen in configuratieprofielen op het apparaat. **Niet geconfigureerd** (standaard): staat de gebruiker toe om configuratieprofielen te installeren.
- **Activeringsslot (alleen onder supervisie)**: kies **Toestaan** om Activeringsslot in te schakelen op iOS-apparaten in de supervisiemodus. Met Activeringsslot kan een verloren of gestolen apparaat moeilijker opnieuw worden geactiveerd.
- **Verwijdering van apps blokkeren (alleen onder supervisie)**: kies **Blokkeren** om de voorkomen dat gebruikers apps verwijderen. **Niet geconfigureerd** (standaard): staat gebruikers toe om apps te verwijderen van het apparaat.
- **Beperkte USB-modus blokkeren (alleen onder supervisie)**: kies **Blokkeren** om de beperkte USB-modus uit te schakelen op apparaten in de supervisiemodus. De beperkte USB-modus voorkomt dat USB-apparaten gegevens uitwisselen met een apparaat dat gedurende langer dan een uur is vergrendeld. **Niet geconfigureerd** (standaard) staat de beperkte USB-modus toe.
- **Automatisch datum en tijd afdwingen (alleen onder supervisie)**: met **Vereisen** wordt instellen van de datum en tijd automatisch afgedwongen op apparaten in de supervisiemodus. De tijdzone van het apparaat wordt bijgewerkt wanneer het apparaat mobiele verbindingen heeft of wanneer Wi-Fi met locatieservices is ingeschakeld voor het apparaat.
- **Vereisen dat leerlingen/studenten toestemming vragen om een Classroom-cursus te verlaten (alleen onder supervisie)**: met **Vereisen** wordt afgedwongen dat leerlingen/studenten die zijn ingeschreven bij een niet-beheerde cursus met de app Classroom, toestemming aan de docent vragen om de cursus te verlaten. **Niet geconfigureerd** (standaard): dwingt niet af dat de leerling/student toestemming vraagt.

  Deze functie is van toepassing op:  
  - iOS 11.3 en hoger

- **Leslokaal toestaan om een app te vergrendelen en het apparaat te vergrendelen zonder vragen (alleen onder supervisie)**: Met **Inschakelen** kan de docent zonder tussenkomst van de student apps of het apparaat vergrendelen met behulp van de app Classroom. Apps vergrendelen betekent dat alleen door de docent gespecificeerde apps op het apparaat toegankelijk zijn. **Niet geconfigureerd** (standaard) voorkomt dat de docenten zonder tussenkomst van de student apps of apparaten vergrendelt met behulp van de app Classroom. 

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Automatisch deelnemen aan Classroom-klassen zonder te vragen (alleen onder supervisie)**: Met **Inschakelen** kunt studenten automatisch deelnemen aan een klas in de app Classroom, zonder tussenkomst van de docent. Met **Niet geconfigureerd** (standaard) wordt de docent gevraagd of studenten mogen deelnemen aan een klas in de app Classroom.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Draadloze PKI-updates toestaan**: met **Toestaan** kunnen gebruikers software-updates ontvangen zonder dat hun apparaten zijn aangesloten op een computer.
- **Bijhouden van advertenties beperken**: kies **Beperken** om de advertentie-id van het apparaat uit te schakelen. Met **Niet geconfigureerd** (standaard) blijft deze instelling ingeschakeld.
- **Het maken van VPN's blokkeren (alleen onder supervisie)**: **Blokkeren** voorkomt dat gebruikers instellingen maken voor VPN-configuratie. **Niet geconfigureerd** (standaard): stelt gebruikers in staat VPN's te maken op het apparaat.
- **ESIM-instellingen wijzigen (alleen onder supervisie)**: **Blokkeren** voorkomt dat gebruikers een mobiel abonnement kunnen verwijderen uit of toevoegen aan de eSIM op het apparaat. **Niet geconfigureerd** (standaard): staat gebruiker toe om deze instellingen te wijzigen.

  Deze functie is van toepassing op:  
  - iOS 12.1 en hoger

- **Software-updates uitstellen (alleen onder supervisie)**: Als de waarde is ingesteld op **Niet geconfigureerd** (standaard), worden software-updates weergegeven op het apparaat wanneer Apple deze uitbrengt. Als Apple bijvoorbeeld op een bepaalde datum een iOS-update uitbrengt, wordt deze update rond de releasedatum automatisch op het apparaat weergegeven.

  Met **Inschakelen** kunt u het weergeven van software-updates op apparaten uitstellen, van 0-90 dagen. Deze instelling bepaalt niet wanneer updates wel of niet worden geïnstalleerd. 

  - **De zichtbaarheid van software-updates vertragen**: Voer een waarde van 0-90 dagen in. Wanneer de vertraging verloopt, krijgen gebruikers een melding om een update uit te voeren naar de vroegste versie van het besturingssysteem die beschikbaar was toen de vertraging werd geactiveerd.

    Als iOS 12.a bijvoorbeeld beschikbaar komt op **1 januari** en **Zichtbaarheid vertragen** is ingesteld op **5 dagen**, wordt iOS 12.a niet als beschikbare update weergeven op apparaten van de eindgebruiker. Op de **zesde dag** na de release komt deze update beschikbaar en kunnen eindgebruikers deze installeren.

    Deze instelling is van toepassing op:  
    - iOS 11.3 en hoger

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: kies **Vereisen** om af te dwingen dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat. **Niet geconfigureerd**: geeft gebruikers toegang tot het apparaat zonder dat ze een wachtwoord hoeven in te voeren.
  - **Eenvoudige wachtwoorden**: kies **Blokkeren** om complexere wachtwoorden te vereisen. **Niet geconfigureerd**: staat eenvoudige wachtwoorden toe, zoals `0000` en `1234`.
  - **Wachtwoordtype vereisen**: kies het type wachtwoord dat is vereist voor uw organisatie. Uw opties zijn:
    - **Standaardwaarde apparaat**
    - **Numeriek**
    - **Alfanumeriek**
  - **Het minimumaantal niet-alfanumerieke tekens in een wachtwoord**: voer het aantal symbooltekens in, bijvoorbeeld `#` of `@`, dat het wachtwoord moet bevatten.
  - **Minimale wachtwoordlengte**: voer de minimale lengte in die een gebruiker moet invoeren (tussen 4 en 14 tekens).
  - **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer het aantal mislukte aanmeldingen in dat is toegestaan voordat het apparaat wordt gewist (tussen 1 en 11).
  - **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** <sup>1</sup>: voer in hoelang het apparaat inactief moet zijn voordat gebruikers hun wachtwoord opnieuw moeten invoeren. Als de ingevoerde tijd langer is dan de tijd die is ingesteld op het apparaat, wordt de door u ingevoerde tijd genegeerd. Ondersteund op iOS 8.0-apparaten en nieuwere apparaten.
  - **Maximale aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**<sup>1</sup>: voer het maximale aantal minuten van inactiviteit in dat is toegestaan op het apparaat totdat het scherm wordt vergrendeld. Als de ingevoerde tijd langer is dan de tijd die is ingesteld op het apparaat, wordt de door u ingevoerde tijd genegeerd.
  - **Wachtwoord verloopt (dagen)**: voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd.
  - **Wachtwoorden niet opnieuw gebruiken**: voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt.
  - **Ontgrendelen met vingerafdruk**: kies **Blokkeren** om te voorkomen dat vingerafdrukken kunnen worden gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd**: staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.
- **Wachtwoordcode wijzigen (alleen onder supervisie)**: kies **Blokkeren** om ervoor te zorgen dat de wachtwoordcode niet meer kan worden gewijzigd, toegevoegd of verwijderd. Als deze functie is geblokkeerd worden wijzigingen in de wachtwoordcodebeperkingen genegeerd op apparaten in de supervisiemodus. **Niet geconfigureerd** (standaard): staat toe dat wachtwoordcodes worden toegevoegd, gewijzigd of verwijderd.

  - **Wijziging van vingerafdruk (alleen onder supervisie)**: kies **Blokkeren** om ervoor te zorgen dat de gebruiker TouchID-vingerafdrukken niet meer kan wijzigen, toevoegen of verwijderen. **Niet geconfigureerd** (standaard): staat de gebruiker toe de TouchID-vingerafdrukken op het apparaat bij te werken.

- **Automatisch doorvoeren van wachtwoorden blokkeren (alleen onder supervisie)**: kies **Blokkeren** om te voorkomen dat de functie Wachtwoorden automatisch doorvoeren wordt gebruikt in iOS. Als u **Blokkeren** kiest, gebeurt ook het volgende:

  - Gebruikers wordt niet meer gevraagd om een wachtwoord te gebruiken dat is opgeslagen in Safari of in een app.
  - Automatische sterke wachtwoorden zijn uitgeschakeld en gebruikers krijgen geen suggesties voor sterke wachtwoorden.

  **Niet geconfigureerd** (standaard) staat deze functies toe.

- **Aanvragen voor wachtwoordnabijheid blokkeren (alleen onder supervisie)**: kies **Blokkeren** zodat het apparaat van een gebruiker geen wachtwoorden aanvraagt van apparaten in de omgeving. **Niet geconfigureerd** (standaard): staat deze wachtwoordaanvragen toe.
- **Delen van wachtwoorden blokkeren (alleen onder supervisie)**: **Blokkeren** voorkomt het delen van wachtwoorden tussen apparaten via AirDrop. **Niet geconfigureerd** (standaard): staat toe dat wachtwoorden worden gedeeld.
- **Vragen om Touch ID- of Face ID-verificatie voor het automatisch invullen van wachtwoorden of creditcardgegevens (alleen onder supervisie)** : Als de waarde **Vereisen** is ingesteld, moeten gebruikers zich verifiëren via Touch ID of Face ID voordat wachtwoorden of creditcardgegevens automatisch kunnen worden ingevuld in Safari en andere apps. Met **Niet geconfigureerd** (standaard) kunnen gebruikers deze functie beheren in de apparaatinstellingen.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

<sup>1</sup>Wanneer u de instellingen **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld** en **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen bijvoorbeeld instelt op **vijf** minuten, wordt het scherm na vijf minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens vijf minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat vijf minuten later vergrendeld.

## <a name="locked-screen-experience"></a>Vergrendeld scherm

- **Toegang tot Beheercentrum wanneer het apparaat is vergrendeld**: kies **Blokkeren** om de toegang tot de app Beheercentrum te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: verleent gebruikers toegang tot de app Beheercentrum terwijl het apparaat is vergrendeld.
- **Meldingen terwijl het apparaat is vergrendeld**: met **Blokkeren** wordt de toegang tot meldingen geblokkeerd terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: verleent gebruikers toegang tot meldingen terwijl het apparaat is vergrendeld.
- **Wallet-meldingen terwijl het apparaat is vergrendeld**: met **Blokkeren** wordt de toegang tot de app Wallet geblokkeerd terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: geeft de gebruiker toegang tot de app Wallet terwijl het apparaat is vergrendeld.
- **De weergave Vandaag wanneer het apparaat is vergrendeld**: met **Blokkeren** wordt de toegang tot de weergave Vandaag geblokkeerd terwijl het apparaat is vergrendeld. **Niet geconfigureerd**: geeft de gebruiker toegang tot de weergave Vandaag terwijl het apparaat is vergrendeld.

## <a name="app-store-doc-viewing-gaming"></a>App Store, documenten bekijken, gamen

- **App Store**: met **Blokkeren** wordt de toegang tot de App Store geblokkeerd op apparaten in de supervisiemodus. **Niet geconfigureerd**: geeft gebruikers toegang.
  - **Apps installeren via de App Store (alleen onder supervisie)**: kies **Blokkeren** om de App Store te blokkeren op het startscherm van het apparaat. Eindgebruikers kunnen iTunes nog steeds gebruiken of met Apple Configurator apps installeren. **Niet geconfigureerd**: geeft gebruikers toegang tot de App Store vanaf het startscherm.
  - **Automatisch downloaden van apps (alleen onder supervisie)**: kies **Blokkeren** om te voorkomen dat apps die zijn gekocht op andere apparaten, automatisch worden gedownload. Dit is niet van invloed op updates voor bestaande apps. **Niet geconfigureerd**: staat gebruikers toe om apps die zijn gekocht op andere iOS-apparaten, te downloaden op het apparaat.
- **Wachtwoord voor toegang tot de App Store**: **Vereisen** dat gebruikers een wachtwoord invoeren voordat ze de App Store kunnen bezoeken. **Niet geconfigureerd**: geeft gebruikers toegang tot de App Store zonder dat ze een wachtwoord hoeven in te voeren.
- **In-app aankopen**: kies **Blokkeren** om in-app aankopen van de Store te voorkomen. **Niet geconfigureerd**: staat gebruikers toe aankopen in de Store te doen vanuit een actieve app.
- **Expliciete muziek-, podcast- of nieuwsinhoud op iTunes (alleen onder supervisie)**: kies **Blokkeren** om expliciete muziek-, podcast- of nieuwsinhoud op iTunes te blokkeren. **Niet geconfigureerd**: geeft het apparaat toegang tot inhoud voor volwassenen in de Store.
- **Inhoud uit iBooks Store met de markering Erotisch downloaden**: kies **Blokkeren** om te voorkomen dat gebruikers media downloaden uit de iBook Store die is gelabeld als Erotisch. **Niet geconfigureerd**: staat de gebruiker toe om boeken te downloaden uit de categorie Erotisch.
- **Zakelijke documenten weergeven in niet-beheerde apps**: **Blokkeren** voorkomt het weergeven van zakelijke documenten in niet-beheerde apps. **Niet geconfigureerd**: staat gebruikers toe om zakelijke documenten weer te geven in elke willekeurige app. Voorbeeld: u wilt voorkomen dat gebruikers bestanden uit de OneDrive-app opslaan in Dropbox. Configureer deze instelling als **Blokkeren**. Nadat het apparaat het beleid heeft ontvangen (bijvoorbeeld nadat het opnieuw is opgestart), kunnen er geen bestanden meer worden opgeslagen.
  - **Toestaan dat beheerde apps contactpersonen doorgeven aan niet-beheerde accounts voor contactpersonen**: Wanneer deze optie is ingesteld op **Toestaan**, kunnen gebruikers de contactgegevens in Outlook van personen, zoals zakelijke contactpersonen, toevoegen aan of synchroniseren met de ingebouwde app Contacten op het apparaat. Wanneer deze optie is ingesteld op **Niet geconfigureerd**, kunnen gebruikers geen contactpersonen in Outlook toevoegen aan de ingebouwde Contacten-app op het apparaat.
  
    Als u deze instelling wilt gebruiken, stelt u **Zakelijke documenten weergeven in niet-beheerde apps** in op **Blokkeren**.
  
- **Niet-zakelijke documenten weergeven in zakelijke apps**: **Blokkeren** voorkomt het weergeven van niet-zakelijke documenten in zakelijke apps. **Niet geconfigureerd**: staat gebruikers toe elk willekeurig document weer te geven in zakelijke beheerde apps.
  - **Toestaan dat niet-beheerde apps contactpersonen lezen in beheerde accounts voor contactpersonen**: Wanneer deze optie is ingesteld op **Toestaan**, kunnen gebruikers de contactgegevens van personen in de app iContacts toevoegen aan Outlook. Wanneer deze optie is ingesteld op **Niet geconfigureerd**, wordt het lezen en het verwijderen van dubbele contactpersonen uit de ingebouwde app Contacten op het apparaat voorkomen.
  
    Als u deze instelling wilt gebruiken, stelt u **Niet-zakelijke documenten weergeven in zakelijke apps** in op **Blokkeren**.
  
- **AirDrop beschouwen als een niet-beheerd doel**: **Vereisen** dwingt af dat AirDrop wordt beschouwd als een niet-beheerd doel. Het zorgt ervoor dat via beheerde apps geen gegevens meer kunnen worden verzonden met behulp van AirDrop. 
- **Game Center-vrienden toevoegen (alleen onder supervisie)**: **Blokkeren** voorkomt dat gebruikers vrienden kunnen toevoegen in Game Center. **Niet geconfigureerd**: staat de gebruiker toe om vrienden toe te voegen in Game Center.
- **Game Center (alleen onder supervisie)**: met **Blokkeren** wordt het gebruik van de app Game Center geblokkeerd. **Niet geconfigureerd**: staat gebruik van de app Game Center toe op het apparaat.
- **Games voor meerdere spelers (alleen onder supervisie)**: kies **Blokkeren** om games voor meerdere spelers te blokkeren. **Niet geconfigureerd**: staat de gebruiker toe om games voor meerdere spelers te spelen op het apparaat.
- **Regio voor restricties**: kies de regio voor restricties die u wilt gebruiken voor toegestane downloads. En kies vervolgens de toegestane beoordelingen voor **Films** en **Tv-shows**.
- **Apps**: kies de toegestane leeftijdscategorie van apps die gebruikers kunnen downloaden, of kies **Alle apps toestaan**.

## <a name="built-in-apps"></a>Ingebouwde apps

- **Camera**: kies **Blokkeren** om toegang tot de camera op het apparaat te blokkeren. **Niet geconfigureerd**: staat toegang tot de camera van het apparaat toe.
  - **FaceTime**: **Blokkeren** voorkomt toegang tot de app FaceTime. **Niet geconfigureerd**: staat toegang tot de app FaceTime toe.
- **Siri**: **Blokkeren** voorkomt toegang tot Siri. **Niet geconfigureerd**: staat toegang tot de spraakassistent Siri toe op het apparaat.
  - **Siri als het apparaat is vergrendeld**: kies **Blokkeren** om te toegang tot Siri te blokkeren wanneer het apparaat is vergrendeld. **Niet geconfigureerd**: staat toegang tot de spraakassistent Siri toe op het apparaat wanneer het is vergrendeld.
  - **Siri-filter voor scheldwoorden (alleen onder supervisie)**: **Vereisen** voorkomt het dicteren van grove taal met Siri of dat Siri grove taal spreekt.
  - **Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet (alleen onder supervisie)**: **Blokkeren** voorkomt dat Siri websites raadpleegt om vragen te beantwoorden. **Niet geconfigureerd**: staat Siri toe om door gebruikers gegenereerde inhoud te raadplegen op internet.
- **Apple News (alleen onder supervisie)**: kies **Blokkeren** om toegang tot de app Apple News op het apparaat te blokkeren. **Niet geconfigureerd**: staat het gebruik van de app Apple News toe.
- **iBooks Store (alleen onder supervisie)**: met **Blokkeren** wordt de toegang tot de iBooks Store geblokkeerd. **Niet geconfigureerd**: staat gebruikers toe te zoeken naar boeken en deze te kopen in de iBooks Store.
- **Berichten-app op het apparaat (alleen onder supervisie)**: kies **Blokkeren** zodat gebruikers de app Berichten niet kunnen gebruiken op het apparaat. **Niet geconfigureerd**: staat het gebruik van de app Berichten toe voor het verzenden en lezen van sms-berichten.
- **Podcasts (alleen onder supervisie)**: **Blokkeren** voorkomt dat gebruikers de app Podcasts kunnen gebruiken. **Niet geconfigureerd**: staat het gebruik van de app Podcasts toe.
- **Music-service (alleen onder supervisie)**: met **Blokkeren** keert u terug naar de klassieke modus van de app Music en wordt de Music-service uitgeschakeld. **Niet geconfigureerd**: staat het gebruik van de app Apple Music toe.
- **iTunes Radio-service (alleen onder supervisie)**: **Blokkeren** voorkomt dat gebruikers de app iTunes Radio gebruiken. **Niet geconfigureerd**: staat het gebruik van de app iTunes Radio toe.
- **Wijzigingen in de instellingen van de app Zoek vrienden (alleen onder supervisie)**: **Blokkeren** voorkomt wijzigingen in de instellingen van de app Zoek vrienden. **Niet geconfigureerd**: staat de gebruiker toe de instellingen van de app Zoek vrienden te wijzigen.
- **Zoeken met Spotlight resultaten laten retourneren van internet (alleen onder supervisie)**: **Blokkeren** zorgt ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd**: staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.
- **Verwijderen van systeemapps van het apparaat blokkeren (alleen onder supervisie)**: kies **Blokkeren** om de mogelijkheid uit te schakelen om systeemapps te verwijderen van het apparaat. **Niet geconfigureerd**: staat gebruikers toe om systeemapps te verwijderen.

#### <a name="safari"></a>Safari

- **Safari (alleen onder supervisie)**: gebruik van de Safari-browser op het apparaat **Blokkeren**. **Niet geconfigureerd**: staat gebruikers toe de Safari-browser te gebruiken.
- **Automatisch doorvoeren**: met **Blokkeren** wordt de functie Automatisch doorvoeren in Safari uitgeschakeld op het apparaat. **Niet geconfigureerd**: staat gebruikers toe de instellingen voor automatisch doorvoeren te wijzigen in de webbrowser.
- **Cookies**: kies hoe cookies moeten worden verwerkt op het apparaat. Uw opties zijn:
  - Toestaan
  - Alle cookies blokkeren
  - Cookies van bezochte websites toestaan
  - Cookies van huidige website toestaan
- **JavaScript**: **Blokkeren** voorkomt dat Java-scripts worden uitgevoerd in de browser op het apparaat. **Niet geconfigureerd**: staat Java-scripts toe.
- **Waarschuwingen voor fraude**: **Vereisen** dat fraudewaarschuwingen worden weergegeven in de webbrowser op het apparaat. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Pop-ups**: met **Blokkeren** wordt het gebruik van pop-upblokkering in de webbrowser uitgeschakeld. **Niet geconfigureerd**: staat de pop-upblokkering toe.

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

- **Verboden apps**: een lijst met apps die niet worden beheerd in Intune die u beter niet kunt installeren op het apparaat. Als een gebruiker een app uit deze lijst installeert, ontvangt u een melding van Intune.
- **Goedgekeurde apps**: een lijst met goedgekeurde apps die gebruikers mogen installeren. Om te voldoen aan het beleid, mogen gebruikers geen andere apps installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Als een gebruiker een app uit deze lijst installeert, ontvangt u een melding van Intune.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- De App Store-URL van de gewenste iTunes-app **toevoegen**. Voer bijvoorbeeld `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

- Importeer een CSV-bestand met details over de app, inclusief de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. Of exporteer een bestaande lijst die de beperkte apps bevat in dezelfde indeling.

> [!IMPORTANT]
> Apparaatprofielen die instellingen voor beperkte apps gebruiken, moeten worden toegewezen aan groepen gebruikers.

## <a name="show-or-hide-apps-supervised-only"></a>Apps weergeven of verbergen (alleen onder supervisie)

In de lijst Apps weergeven of verbergen kunt u een van de volgende lijsten configureren op apparaten in de supervisiemodus met iOS 9.3 of hoger.

- **Verborgen apps**: voer een lijst met apps in die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of openen.
- **Zichtbare apps**: voer een lijst met apps in die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- De App Store-URL van de gewenste iTunes-app **toevoegen**. Voer bijvoorbeeld `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

- Importeer een CSV-bestand met details over de app, inclusief de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. Of exporteer een bestaande lijst die de beperkte apps bevat in dezelfde indeling.

## <a name="wireless"></a>Draadloos

- **Dataroaming**: kies **Blokkeren** om dataroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd** (standaard): staat dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Wereldwijd ophalen op achtergrond tijdens roaming**: **Blokkeren** voorkomt het gebruik van de functie Wereldwijd ophalen op achtergrond tijdens roaming via het mobiele netwerk. **Niet geconfigureerd** (standaard): staat het apparaat toe om gegevens zoals e-mail op te halen tijdens roaming op een mobiel netwerk.
- **Nummer inspreken**: kies **Blokkeren** om te voorkomen dat gebruikers de functie Nummer inspreken op het apparaat gebruiken. **Niet geconfigureerd** (standaard): hiermee wordt Nummer inspreken toegestaan op het apparaat.
- **Spraakroaming**: kies **Blokkeren** om spraakroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd** (standaard): staat spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Wijzigingen in de app-instellingen voor het gebruik van mobiel dataverkeer (alleen onder supervisie)**: kies **Blokkeren** om wijzigingen te voorkomen in de app-instellingen voor het gebruik van mobiel dataverkeer. **Niet geconfigureerd** (standaard): staat de gebruiker toe om te bepalen welke apps mobiel dataverkeer mogen gebruiken.
- **Wijzigingen in de instellingen voor mobiel dataverkeer (alleen onder supervisie)**: Met **Blokkeren** voorkomt u dat gebruikers instellingen voor mobiel dataverkeer wijzigen. Met **Niet geconfigureerd** (standaard) kunnen gebruikers wijzigingen aanbrengen.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Persoonlijke Hotspot**: Met **Blokkeren** schakelt u de persoonlijke hotspot op apparaten van de gebruikers uit bij elke apparaatsynchronisatie. Mogelijk is deze instelling niet compatibel met bepaalde providers. Met **Niet geconfigureerd** (standaard) blijft de configuratie van de persoonlijke hotspot behouden als de standaardwaarde die is ingesteld door de gebruiker.
- **Toevoegen aan Wi-Fi-netwerken die alleen configuratieprofielen gebruiken (alleen onder supervisie)**: **Vereisen** dwingt af dat het apparaat alleen Wi-Fi-netwerken gebruikt die zijn ingesteld via Intune-configuratieprofielen. **Niet geconfigureerd** (standaard): staat het apparaat toe andere Wi-Fi-netwerken te gebruiken.
- **Regels voor mobiel gebruik (alleen beheerde apps)**: definieer de gegevenstypen die beheerde apps kunnen gebruiken die zijn verbonden met een mobiel netwerk. Uw opties zijn:
  - **Gebruik van mobiel dataverkeer blokkeren**: u kunt het gebruik van mobiel dataverkeer blokkeren voor **Alle beheerde apps** of u kunt **Specifieke apps kiezen**.
  - **Gebruik van mobiel dataverkeer tijdens roaming blokkeren**: u kunt het gebruik van mobiel dataverkeer tijdens roaming blokkeren voor **Alle beheerde apps** of u kunt **Specifieke apps kiezen**.

## <a name="connected-devices"></a>Verbonden apparaten

- **AirDrop (alleen onder supervisie)**: **Blokkeren** voorkomt het gebruik van AirDrop op het apparaat. **Niet geconfigureerd** (standaard): staat het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
- **Koppelen met Apple Watch (alleen onder supervisie)**: **Blokkeren** voorkomt dat het apparaat wordt gekoppeld aan een Apple Watch. **Niet geconfigureerd** (standaard): staat toe dat het apparaat wordt gekoppeld aan een Apple Watch.
- **De gekoppelde Apple Watch gebruikt Wrist Detection**: **Vereisen** dwingt af dat een gekoppelde Apple Watch Wrist Detection gebruikt. Wanneer dit is vereist, worden op de Apple Watch geen meldingen weergegeven wanneer deze niet wordt gedragen. 
- **Bluetooth-aanpassingen (alleen onder supervisie)**: **Blokkeren** zorgt ervoor dat de eindgebruiker geen Bluetooth-instellingen meer kan wijzigen op het apparaat. **Niet geconfigureerd** (standaard): staat de gebruiker toe om deze instellingen te wijzigen.
- **Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld (alleen onder supervisie)**: **Niet geconfigureerd** (standaard) staat het koppelen met een host toe, waarmee de beheerder kan bepalen aan welke apparaten een iOS-apparaat kan worden gekoppeld. **Blokkeren**: voorkomt het koppelen met een host.
- **Wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**: een wachtwoord voor koppelen **Vereisen** wanneer AirPlay wordt gebruikt om inhoud te streamen naar andere Apple-apparaten. **Niet geconfigureerd** (standaard): staat de gebruiker toe inhoud te streamen met AirPlay zonder een wachtwoord in te voeren.
- **AirPrint blokkeren (alleen onder supervisie)**: kies **Blokkeren** om te voorkomen dat de functie AirPrint wordt gebruikt op het apparaat. **Niet geconfigureerd** (standaard): staat de gebruiker toe AirPrint te gebruiken.
  - **Opslag van AirPrint-referenties in de Sleutelhanger blokkeren (alleen onder supervisie)**: **Blokkeren** voorkomt het gebruik van de Sleutelhanger om de gebruikersnaam en het wachtwoord op te slaan op het apparaat. **Niet geconfigureerd** (standaard): staat toe dat de gebruikersnaam en het wachtwoord van AirPrint worden opgeslagen in de app Sleutelhanger.
  - **Een vertrouwd TLS-certificaat vereisen voor AirPrint (alle onder supervisie)**: **Vereisen** dwingt af dat op het apparaat vertrouwde certificaten worden gebruikt voor TLS-afdrukcommunicatie.
  - **iBeacon-detectie van AirPrint-printers blokkeren (alleen onder supervisie)**: **Blokkeren** voorkomt phishing met schadelijke AirPrint Bluetooth-bakens voor netwerkverkeer. **Niet geconfigureerd** (standaard): staat het adverteren van AirPrint-printers op het apparaat toe.
- **Het instellen van nieuwe apparaten in de buurt blokkeren (alleen onder supervisie)**: met **Blokkeren** wordt de vraag om nieuwe apparaten in de buurt in te stellen uitgeschakeld. Met **Niet geconfigureerd** (standaard) wordt gebruikers gevraagd verbinding te maken met andere Apple-apparaten in de buurt.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

## <a name="keyboard-and-dictionary"></a>Toetsenbord en woordenlijst

- **Opzoeken van definities van woorden (alleen onder supervisie)**: **Blokkeren** voorkomt dat de gebruiker een woord markeert en vervolgens de definitie ervan opzoekt op het apparaat. **Niet geconfigureerd**: geeft toegang tot de functie Opzoeken van definities van woorden.
- **Tekstvoorspelling (alleen onder supervisie)**: **Niet geconfigureerd** staat het gebruik van tekstvoorspelling toe voor suggesties voor woorden die de gebruiker mogelijk wil invoeren. Met **Blokkeren** wordt deze functie geblokkeerd.
- **Autocorrectie (alleen onder supervisie)**: **Niet gecorrigeerd** staat automatische correctie van verkeerd gespelde woorden toe op het apparaat. **Blokkeren**: blokkeert het gebruik van Autocorrectie.
- **Spellingcontrole (alleen onder supervisie)**: **Niet geconfigureerd** staat het gebruik van de spellingcontrole toe op het apparaat. **Blokkeren**: staat de spellingcontrole toe.
- **Sneltoetsen (alleen onder supervisie)**: **Niet geconfigureerd** staat het gebruik van sneltoetsen toe op het apparaat. **Blokkeren**: zorgt ervoor dat de gebruiker geen sneltoetsen meer kan gebruiken.
- **Dicteren (alleen onder supervisie)**: **Blokkeren** zorgt ervoor dat de gebruiker geen spraak meer kan gebruiken om tekst in te voeren. **Niet geconfigureerd**: staat de gebruiker toe invoer van Dicteren te gebruiken.

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Back-up naar iCloud**: **Niet geconfigureerd** staat de gebruiker toe een back-up van het apparaat op te slaan in iCloud. **Blokkeren**: zorgt ervoor dat de gebruiker geen back-ups van het apparaat meer kan opslaan in iCloud.
- **Documenten synchroniseren met iCloud blokkeren (alleen onder supervisie)**: **Niet geconfigureerd** staat het synchroniseren van documenten en sleutelwaarden met uw iCloud-opslagruimte toe. **Blokkeren**: voorkomt dat documenten en gegevens worden gesynchroniseerd met iCloud.
- **Photo Stream synchroniseren met iCloud**: **Niet geconfigureerd** stelt gebruikers in staat **Mijn Photo Stream**  in te schakelen op hun apparaat om te synchroniseren met iCloud, en foto’s weer te geven op alle apparaten van de gebruikers. **Blokkeren**: voorkomt dat met Photo Stream foto’s worden gesynchroniseerd met iCloud.
- **Versleutelde back-up**: kies **Vereisen** om ervoor te zorgen dat back-ups van het apparaat moeten worden versleuteld.
- **iCloud-fotobibliotheek**: stel in op **Blokkeren** om het gebruik van de
iCloud-fotobibliotheek voor het opslaan van foto’s en video’s in de cloud uit te schakelen. Foto's die niet volledig naar het apparaat zijn gedownload vanaf de iCloud-fotobibliotheek, worden van het apparaat verwijderd. **Niet geconfigureerd**: staat het gebruik van de iCloud-fotobibliotheek toe.
- **Beheerde apps synchroniseren met de cloud**: **Niet geconfigureerd** staat in Intune beheerde apps toe om gegevens te synchroniseren naar het iCloud-account van de gebruikers. **Blokkeren**: voorkomt deze gegevenssynchronisatie naar iCloud.
- **Streaming van gedeelde foto's**: kies **Blokkeren** om **Foto's delen via iCloud** uit te schakelen op het apparaat. **Niet geconfigureerd**: staat streaming van gedeelde foto’s toe.
- **Voortzetting van activiteit**: **Niet geconfigureerd** staat gebruikers toe op een ander iOS- of macOS-apparaat door te gaan met werk waaraan ze zijn begonnen op een iOS-apparaat (Handoff). **Blokkeren**: voorkomt deze handoff.
- **Synchronisatie van iCloud-sleutelhanger blokkeren**: kies **Blokkeren** om het synchroniseren van referenties die zijn opgeslagen in de Sleutelhanger, naar iCloud uit te schakelen. **Niet geconfigureerd**: staat gebruikers toe deze referenties te synchroniseren.
- **Back-ups van Enterprise Book blokkeren**: kies **Blokkeren** om te voorkomen dat gebruikers back-ups opslaan van Enterprise Book-boeken. **Niet geconfigureerd**: staat gebruikers toe om back-ups te maken van deze boeken.
- **Synchronisatie van metagegevens van Enterprise Book blokkeren (notities en markeringen)**: **Blokkeren** voorkomt het synchroniseren van notities en markeringen in Enterprise Book-boeken. **Niet geconfigureerd**: staat synchronisatie toe.

## <a name="autonomous-single-app-mode-supervised-only"></a>Autonome modus voor enkele toepassing (alleen onder toezicht)

Gebruik deze instellingen om iOS-apparaten zodanig te configureren dat hierop specifieke apps in de autonome één-app-modus worden uitgevoerd. Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld. Alleen deze ene app kan worden uitgevoerd. Voeg bijvoorbeeld een app toe waarmee gebruikers een test kunnen uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

Ga op een van de volgende manieren te werk om apps toe te voegen:

- Voer de **App-naam** en **App-bundel-id** in, en selecteer **Toevoegen**. [Bundel-id's voor ingebouwde iOS-apps](#bundle-ids-for-built-in-ios-apps) (in dit artikel) bevat enkele apps met de bijbehorende id's.
- **Importeer** een CSV-bestand met de lijst met app-namen en de bijbehorende bundel-id’s. Of **Exporteer** een bestaande lijst die de apps bevat.

## <a name="kiosk-supervised-only"></a>Kiosk (alleen onder toezicht)

- **App uitvoeren in kioskmodus**: kies het type apps dat u wilt uitvoeren in de kioskmodus. Uw opties zijn:
  - **Niet geconfigureerd**: De kioskinstellingen worden niet toegepast. Het apparaat wordt niet uitgevoerd in de kioskmodus.
  - **Store-app**: voer de URL voor een app in de iTunes App Store in.
  - **Beheerde app**: kies een app die u hebt toegevoegd in Intune.
  - **Ingebouwde app**: voer de [bundel-id](#bundle-ids-for-built-in-ios-apps) (in dit artikel) van de ingebouwde app in.

- **Ondersteunende aanraking**: de toegankelijkheidsinstelling Ondersteunende aanraking **Vereisen** op het apparaat. Deze functie helpt gebruikers bij schermbewegingen die mogelijk moeilijk zijn voor hen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Kleuren omkeren**: de toegankelijkheidsinstelling Kleuren omkeren **Vereisen**, zodat gebruikers met een beperkt gezichtsvermogen de display kunnen wijzigen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Mono-audio**: de toegankelijkheidsinstelling Mono-audio **Vereisen** op het apparaat. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Voice-over**: de toegankelijkheidsinstelling Voice-over **Vereisen** op het apparaat om tekst op het scherm hardop voor te lezen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Inzoomen**: **Vereisen** dat de instelling Inzoomen is ingesteld op het apparaat, zodat gebruikers met behulp van aanraken het scherm kunnen inzoomen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Automatisch vergrendelen**: automatische vergrendeling van het apparaat **Toestaan**. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Schakelaar voor belsignaal**: de schakelaar voor het belsignaal (dempen) op het apparaat **Toestaan**. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Scherm draaien**: wijzigen van de schermstand **Toestaan** wanneer de gebruiker het apparaat draait. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Schermsluimerknop**: kies **Toestaan** om de knop voor slaapstand/ontwaken van het scherm op het apparaat uit te schakelen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is ingeschakeld.
- **Aanraken**: met **Blokkeren** wordt het aanraakscherm uitgeschakeld op het apparaat. **Niet geconfigureerd**: staat de gebruiker toe het aanraakscherm te gebruiken.
- **Volumeknoppen**: het gebruik van de volumeknoppen **Toestaan** op het apparaat. **Niet geconfigureerd**: zorgt ervoor dat de volumeknoppen zijn uitgeschakeld.
- **Besturingselement voor ondersteunende aanraking**: gebruikers **Toestaan** de functie Ondersteunende aanraking te gebruiken. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Besturingselement voor Kleuren omkeren**: aanpassingen in de functie Kleuren omkeren **Toestaan** zodat gebruikers de functie Kleuren omkeren kunnen aanpassen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Geselecteerde tekst spreken**: de toegankelijkheidsinstellingen Selectie uitspreken **Toestaan** op het apparaat. Met deze functie wordt tekst die de gebruiker selecteert, hardop gelezen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Besturingselement voor Voice-over**: wijzigingen in Voice-over **Toestaan**, zodat gebruikers de functie Voice-over kunnen bijwerken, bijvoorbeeld hoe snel schermtekst hardop wordt gelezen. **Niet geconfigureerd**: voorkomt wijzigingen in Voice-over.
- **Besturingselement voor Inzoomen**: wijzigingen in Inzoomen door de gebruiker **Toestaan**. **Niet geconfigureerd**: voorkomt wijzigingen in Inzoomen.

> [!NOTE]
> Voordat u een iOS-apparaat voor de kioskmodus kunt configureren, moet u het hulpprogramma Apple Configurator of het Device Enrollment Program van Apple gebruiken om het apparaat in de supervisiemodus te plaatsen. Raadpleeg de handleiding van Apple voor het gebruik van het hulpprogramma Apple Configurator.
> Als de iOS-app die u invoert, wordt geïnstalleerd nadat u het profiel hebt toegewezen, wordt de kioskmodus van het apparaat pas geactiveerd nadat het opnieuw is opgestart.

## <a name="domains"></a>Domains

- **Niet-gemarkeerde e-maildomeinen** > **E-maildomein-URL**: Voeg een of meer URL's toe aan de lijst. Wanneer eindgebruikers een e-mail ontvangen die afkomstig is van een ander domein dan de domeinen die u invoert, wordt de e-mail in de iOS Mail-app gemarkeerd als niet-vertrouwd.

- **Beheerde webdomeinen** > **Webdomein-URL**: Voeg een of meer URL's toe aan de lijst. Wanneer documenten worden gedownload uit de domeinen die u invoert, worden ze beschouwd als beheerd. Deze instelling geldt alleen voor documenten die zijn gedownload met Safari.

- **Domeinen voor automatisch invullen van Safari-wachtwoorden** > **Domein-URL**: Voeg een of meer URL's toe aan de lijst. Gebruikers kunnen in deze lijst alleen webwachtwoorden van URL's opslaan. Deze instelling geldt alleen voor Safari en voor apparaten met iOS 9.3 en hoger in de modus supervisie. Als u geen URL's opgeeft, kunnen wachtwoorden van alle websites worden opgeslagen.

## <a name="bundle-ids-for-built-in-ios-apps"></a>Bundel-id's voor ingebouwde iOS-apps

De volgende lijst bevat de bundel-id's van een aantal algemene ingebouwde iOS-apps. Als u de bundel-ID van andere apps wilt weten, neemt u contact op met de softwareleverancier.

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
| com.apple.DocumentsApp      | Bestanden        | Apple     |
| com.apple.mobileme.fmf1     | Zoek vrienden | Apple     |
| com.apple.mobileme.fmip1    | Zoek mijn iPhone  | Apple     |
| com.apple.gamecenter        | Game Center  | Apple     |
| com.apple.mobilegarageband  | GarageBand   | Apple     |
| com.apple.Health            | Status       | Apple     |
| com.apple.Home              | Home         | Apple     |
| com.apple.iBooks            | iBooks       | Apple     |
| com.apple.iMovie            | iMovie       | Apple     |
| com.apple.itunesconnect.mobile | iTunes Connect | Apple |
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
| com.apple.mobilesafari      | Safari       | Apple     |
| com.apple.Preferences       | Instellingen     | Apple     |
| com.apple.SiriViewService   | Siri         | Apple     |
| com.apple.stocks            | Aandelen       | Apple     |
| com.apple.tips              | Tips         | Apple     |
| com.apple.TV                | TV           | Apple     |
| com.apple.videos            | Video 's       | Apple     |
| com.apple.VoiceMemos        | Dictafoon   | Apple     |
| com.apple.Passbook          | Wallet       | Apple     |
| com.apple.Bridge            | Watch        | Apple     |
| com.apple.weather           | Weer      | Apple     |

## <a name="settings-that-require-supervised-mode"></a>Instellingen waarvoor de supervisiemodus is vereist

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

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook apparaatfuncties en -instellingen beperken op [macOS](device-restrictions-macos.md)-apparaten.
