---
title: iOS-apparaatinstellingen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: U kunt instellingen voor iOS-apparaten toevoegen, configureren of maken om functies te beperken, zoals wachtwoordvereisten instellen, het vergrendelingsscherm beheren, ingebouwde apps gebruiken, beperkte of goedgekeurde apps toevoegen, Bluetooth-apparaten verwerken, verbinding maken met de cloud voor back-up en opslag, de kioskmodus inschakelen, domeinen toevoegen, en bepalen hoe gebruikers de Safari-webbrowser kunnen gebruiken in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 476817b70f18fdd45a678ef3e12d1d3312c03dd3
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206530"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Met instellingen voor iOS- en iPadOS-apparaten kunt u functies toestaan of beperken met behulp van Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op iOS- en iPadOS-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, bepaalde apps toe te staan of te beperken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw iOS-apparaten.

> [!TIP]
> Deze instellingen gebruiken de MDM-instellingen van Apple. Voor meer informatie over deze instellingen raadpleegt u [de Mobile Device Management-instellingen van Apple](https://support.apple.com/guide/mdm/welcome/web) (opent de website van Apple).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een configuratieprofiel voor apparaatbeperkingen](../device-restrictions-configure.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvings typen, waarbij sommige instellingen van toepassing zijn op alle inschrijvings opties. Zie [IOS-inschrijving](../ios-enroll.md)voor meer informatie over de verschillende inschrijvings typen.

## <a name="general"></a>Algemeen

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Gebruiksgegevens delen**: Kies **Blokkeren** om te voorkomen dat met het apparaat diagnostische gegevens en gebruiksgegevens worden verzonden naar Apple. **Niet geconfigureerd** (standaard): staat toe dat deze gegevens worden verzonden.

- **Schermopname**: Selecteer **Blokkeren** om te voorkomen dat schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. In iOS 9,0 en hoger, worden ook scherm opnames geblokkeerd. **Niet geconfigureerd** (standaard): stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding of video.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Niet-vertrouwde TLS-certificaten**: Selecteer **Blokkeren** om te voorkomen dat niet-vertrouwde TLS-certificaten (Transport Layer Security) zijn toegestaan op het apparaat. Met **Niet geconfigureerd** (standaard) staat u TLS-certificaten toe.
- **Over-the-Air PKI-updates**: **blok** keren dat uw gebruikers geen software-updates ontvangen tenzij het apparaat is verbonden met een computer. **Niet geconfigureerd** (standaard): Hiermee staat u toe dat een apparaat software-updates ontvangt zonder dat er verbinding wordt gemaakt met een computer.
- **Bijhouden van advertenties beperken**: Selecteer **Beperken** om de advertentie-id van het apparaat uit te schakelen. Met **Niet geconfigureerd** (standaard) blijft deze instelling ingeschakeld.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Aanpassing van instellingen voor het verzenden van diagnostische gegevens**: Met **Blokkeren** voorkomt u dat de gebruiker de instelling voor verzending van diagnostische gegevens en app-analyse wijzigt in **Diagnostische gegevens en gebruik** (in Instellingen op het apparaat). **Niet geconfigureerd** (standaard): staat de gebruiker toe om deze apparaatinstellingen te wijzigen.

  Als u deze instelling wilt gebruiken, stelt u de instelling **gebruiks gegevens delen** in op **blok keren**.

  Deze functie is van toepassing op:  
  - iOS 9.3.2 en hoger

- **Observatie van extern scherm met de app Classroom**: Selecteer **Blokkeren** om te voorkomen dat de app Klaslokaal het scherm op het apparaat op afstand kan weergeven. **Niet geconfigureerd** (standaard): staat de app Apple Classroom toe het scherm weer te geven.

  Als u deze instelling wilt gebruiken, stelt u de instelling voor **scherm opname** in op **blok keren**.

  Deze functie is van toepassing op:  
  - iOS 9.3 en hoger

- **Ongevraagde schermobservatie met de app Classroom**: Wanneer deze optie is ingesteld op **Toestaan**, kunnen docenten het scherm op de iOS-apparaten van leerlingen/studenten met de app Klaslokaal observeren zonder dat de leerlingen/studenten dit weten. Op apparaten van leerlingen/studenten die zijn ingeschreven bij een cursus met de app Classroom, is toestemming voor de docent van deze cursus automatisch ingeschakeld. Met **Niet geconfigureerd** (standaard) voorkomt u deze functie.

  Als u deze instelling wilt gebruiken, stelt u de instelling voor **scherm opname** in op **blok keren**.

- **Bedrijfsapps vertrouwen**: Selecteer **Blokkeren** om de knop **Ontwikkelaar vertrouwen** op het apparaat te verwijderen in Instellingen > Algemeen > Profielen en apparaatbeheer. **Niet geconfigureerd** (standaard): stelt de gebruiker in staat om apps te vertrouwen die niet zijn gedownload uit de App Store.
- **Accountaanpassing**: Wanneer deze optie is ingesteld op **Blokkeren**, kan de gebruiker de apparaatspecifieke instellingen niet bijwerken vanuit de app voor iOS-instellingen. De gebruiker kan dan bijvoorbeeld geen nieuwe apparaataccounts maken, of de gebruikersnaam of het wachtwoord wijzigen. **Niet geconfigureerd** (standaard): staat gebruiker toe om deze instellingen te wijzigen.

  Deze functie geldt ook voor instellingen die toegankelijk zijn vanuit de app voor iOS-instellingen, zoals voor e-mail, contactpersonen, agenda, Twitter, en meer. Deze functie geldt niet voor apps met accountinstellingen die niet kunnen worden geconfigureerd in de app voor iOS-instellingen, zoals de Microsoft Outlook-app.

- **Schermtijd**: Kies **Blokkeren** om te voorkomen dat gebruikers hun eigen beperkingen in Schermtijd instellen (instellingen op het apparaat). Met **Niet geconfigureerd** kan de gebruiker apparaatbeperkingen (zoals ouderlijk toezicht, inhoudsbeperkingen en privacybeperkingen) configureren op het apparaat.

  Deze instelling heette eerst **Beperkingen inschakelen in de apparaatinstellingen**. Gevolgen van deze wijziging:  
  
  - iOS 11.4.1 en eerder: **Blokkeren** voorkomt dat eindgebruikers hun eigen beperkingen kunnen instellen bij de apparaatinstellingen. Het gedrag is hetzelfde, en er zijn geen wijzigingen voor eindgebruikers.
  - iOS 12.0 en nieuwer: Met **Blokkeren** voorkomt u dat eindgebruikers hun eigen **Schermtijd** kunnen instellen bij de apparaatinstellingen (Instellingen > Algemeen > Schermtijd), waaronder inhouds- en privacybeperkingen. Apparaten die zijn geüpgraded naar iOS 12.0 krijgen het tabblad Beperkingen niet meer te zien bij de apparaatinstellingen (Instellingen > Algemeen > Apparaatbeheer > Beheerprofiel > Beperkingen). Deze instellingen vindt u onder **Schermtijd**.
  
- **Gebruik van de optie voor het wissen van alle inhoud en instellingen op het apparaat**: Selecteer **Blokkeren** zodat gebruikers de optie voor het wissen van alle inhoud en instellingen op het apparaat niet kunnen gebruiken. **Niet geconfigureerd** (standaard): geeft de gebruiker toegang tot deze instellingen.
- **Apparaatnaam wijzigen**: Selecteer **Blokkeren**, zodat de apparaatnaam niet kan worden gewijzigd. **Niet geconfigureerd** (standaard): staat de gebruiker toe om de naam van het apparaat te wijzigen.
- **Aanpassing van meldingsinstellingen**: Selecteer **Blokkeren**, zodat de instellingen voor meldingen niet kunnen worden gewijzigd. **Niet geconfigureerd** (standaard): staat de gebruiker toe de meldingsinstellingen voor apparaten te wijzigen.
- **Aanpassing van achtergrond**: Selecteer **Blokkeren**, zodat de achtergrond niet kan worden gewijzigd. **Niet geconfigureerd** (standaard): staat de gebruiker toe om d achtergrond van het apparaat te wijzigen.
- **Aanpassing van vertrouwensinstellingen voor bedrijfsapps**: Selecteer **Blokkeren** om te voorkomen dat de gebruiker de instellingen voor vertrouwen in bedrijfsapps wijzigt op apparaten in de supervisiemodus. **Niet geconfigureerd** (standaard): staat de gebruiker toe om apps te vertrouwen die niet zijn gedownload uit de App Store.
- **Wijzigingen in configuratieprofielen**: Selecteer **Blokkeren** om te voorkomen dat configuratieprofielen op het apparaat kunnen worden gewijzigd. **Niet geconfigureerd** (standaard): staat de gebruiker toe om configuratieprofielen te installeren.
- **Activeringsvergrendeling**: Selecteer **Toestaan** om Activeringsslot op iOS-apparaten in de supervisiemodus in te schakelen. Met Activeringsslot kan een verloren of gestolen apparaat moeilijker opnieuw worden geactiveerd.
- **Verwijderen van app blokkeren**: Selecteer **Blokkeren** om te voorkomen dat gebruikers apps verwijderen. **Niet geconfigureerd** (standaard): staat gebruikers toe om apps te verwijderen van het apparaat.
- **USB-accessoires toestaan terwijl het apparaat is vergrendeld**: met **toestaan** kunnen USB-accessoires gegevens uitwisselen met een apparaat dat gedurende een uur is vergrendeld. **Niet geconfigureerd** (standaard) de modus USB-beperkt wordt niet bijgewerkt op het apparaat en USB-accessoires worden geblokkeerd voor het overdragen van gegevens van het apparaat als het gedurende een uur is vergrendeld.
- **Automatisch instellen van datum en tijd afdwingen**: Met **Vereisen** wordt het instellen van de datum en tijd automatisch afgedwongen op apparaten in de supervisiemodus. De tijdzone van het apparaat wordt bijgewerkt wanneer het apparaat mobiele verbindingen heeft of wanneer Wi-Fi met locatieservices is ingeschakeld voor het apparaat.
- **Studenten moeten toestemming vragen om de Classroom-cursus te verlaten**: Met **Vereisen** wordt afgedwongen dat leerlingen/studenten die zijn ingeschreven bij een niet-beheerde cursus met de app Klaslokaal, toestemming aan de docent vragen om de cursus te verlaten. **Niet geconfigureerd** (standaard): dwingt niet af dat de leerling/student toestemming vraagt.

  Deze functie is van toepassing op:  
  - iOS 11.3 en hoger

- **De app Classroom toestaan om een app te vergrendelen en het apparaat te vergrendelen zonder te vragen**: Met **Inschakelen** kan de docent zonder tussenkomst van de student apps of het apparaat vergrendelen met behulp van de app Classroom. Apps vergrendelen betekent dat alleen door de docent gespecificeerde apps op het apparaat toegankelijk zijn. **Niet geconfigureerd** (standaard) voorkomt dat de docenten zonder tussenkomst van de student apps of apparaten vergrendelt met behulp van de app Classroom.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Automatisch lid worden van Classroom-klassen zonder te vragen**: Met **Inschakelen** kunt studenten automatisch deelnemen aan een klas in de app Classroom, zonder tussenkomst van de docent. Met **Niet geconfigureerd** (standaard) wordt de docent gevraagd of studenten mogen deelnemen aan een klas in de app Classroom.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Het maken van VPN's blokkeren**: Selecteer **Blokkeren** om te voorkomen dat gebruikers instellingen maken voor VPN-configuratie. **Niet geconfigureerd** (standaard): stelt gebruikers in staat VPN's te maken op het apparaat.
- **eSIM-instellingen aanpassen**: Met **Blokkeren** voorkomt u dat gebruikers een mobiel abonnement kunnen verwijderen uit of toevoegen aan de eSIM op het apparaat. **Niet geconfigureerd** (standaard): staat gebruiker toe om deze instellingen te wijzigen.

  Deze functie is van toepassing op:  
  - iOS 12.1 en hoger

- **Software-updates uitstellen**: Als de waarde is ingesteld op **Niet geconfigureerd** (standaard), worden software-updates weergegeven op het apparaat wanneer Apple deze uitbrengt. Als Apple bijvoorbeeld op een bepaalde datum een iOS-update uitbrengt, wordt deze update rond de releasedatum automatisch op het apparaat weergegeven.

  Met **Inschakelen** kunt u het weergeven van software-updates op apparaten uitstellen, van 0-90 dagen. Deze instelling bepaalt niet wanneer updates wel of niet worden geïnstalleerd. 

  - **De zichtbaarheid van software-updates vertragen**: Voer een waarde in tussen 0 en 90 dagen. Wanneer de vertraging verloopt, krijgen gebruikers een melding om een update uit te voeren naar de vroegste versie van het besturingssysteem die beschikbaar was toen de vertraging werd geactiveerd.

    Als iOS 12.a bijvoorbeeld beschikbaar komt op **1 januari** en **Zichtbaarheid vertragen** is ingesteld op **5 dagen**, wordt iOS 12.a niet als beschikbare update weergeven op apparaten van de eindgebruiker. Op de **zesde dag** na de release komt deze update beschikbaar en kunnen eindgebruikers deze installeren.

    Deze instelling is van toepassing op:  
    - iOS 11.3 en hoger

## <a name="password"></a>Wachtwoord

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Wachtwoord**: **Vereisen** dat de eindgebruiker een wachtwoord invoert voor toegang tot het apparaat. **Niet geconfigureerd** (standaard): geeft gebruikers toegang tot het apparaat zonder dat ze een wachtwoord hoeven in te voeren.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

> [!IMPORTANT]
> Als u op door de gebruiker ingeschreven apparaten een wachtwoordinstelling configureert, worden de instellingen voor **Eenvoudige wachtwoorden** automatisch ingesteld op **Blokkeren** en wordt een 6-cijferige pincode afgedwongen.
>
> U kunt bijvoorbeeld de instelling **Wachtwoord verloopt** configureren en dit beleid pushen naar de door gebruikers ingeschreven apparaten. Op de apparaten gebeurt dan het volgende:
>
> - De instelling **Wachtwoord verloopt** wordt genegeerd.
> - Eenvoudige wachtwoorden, zoals `1111` of `1234`, worden niet toegestaan.
> - Er wordt een 6-cijferige pincode afgedwongen.

- **Eenvoudige wachtwoorden**: Selecteer **Blokkeren** om complexere wachtwoorden te vereisen. **Niet geconfigureerd**: staat eenvoudige wachtwoorden toe, zoals `0000` en `1234`.

- **Vereist wachtwoordtype**: Selecteer het type wachtwoord dat is vereist voor uw organisatie. Uw opties zijn:
  - **Standaardwaarde apparaat**
  - **Numeriek**
  - **Alfanumeriek**
- **Het aantal niet-alfanumerieke tekens in het wachtwoord**: Geef het aantal symbooltekens op, zoals `#` of `@`, dat het wachtwoord moet bevatten.

- **Minimale wachtwoordlengte**: Voer de minimale lengte in die een gebruiker moet invoeren, tussen 4 en 14 tekens. Voer een lengte tussen 4 en 6 tekens in voor door de gebruiker Inge schreven apparaten.
  
  > [!NOTE]
  > Voor apparaten die door de gebruiker zijn Inge schreven, kunnen gebruikers een pincode instellen die groter is dan 6 cijfers. Maar er worden niet meer dan 6 cijfers afgedwongen op het apparaat. Een beheerder stelt bijvoorbeeld de minimale lengte in op `8`. Gebruikers hoeven alleen een 6-cijferig pincode in te stellen op apparaten die door gebruikers zijn Inge schreven. InTune dwingt geen pincode af die groter is dan 6 cijfers op door gebruikers geregistreerde apparaten.

- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Voer het aantal mislukte aanmeldingen in dat is toegestaan voordat het apparaat wordt gewist (tussen 4 en 11).
  
  iOS heeft ingebouwde beveiliging die van invloed kan zijn op deze instelling. Bijvoorbeeld: iOS kan het activeren van het beleid vertragen, afhankelijk van het aantal mislukte aanmeldingen. Het kan ook worden aangeraden herhaaldelijk dezelfde wachtwoord code in te voeren als één poging. De [IOS-beveiligings handleiding](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) van Apple (opent de website van Apple) is een goede bron en biedt meer specifieke informatie over wachtwoord codes.
  
- **Maximum aantal minuten na schermvergrendeling voordat wachtwoord is vereist**<sup>1</sup>: Geef op hoelang het apparaat inactief blijft voordat gebruikers hun wachtwoord opnieuw moeten invoeren. Als de ingevoerde tijd langer is dan de tijd die is ingesteld op het apparaat, wordt de door u ingevoerde tijd genegeerd. Ondersteund op iOS 8.0-apparaten en nieuwere apparaten.

- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**<sup>1</sup>: Voer het maximale aantal minuten van inactiviteit in dat is toegestaan op het apparaat totdat het scherm wordt vergrendeld.

  **IOS-opties**:  

  - **Niet geconfigureerd** (standaard): intune raakt deze instelling niet aan.
  - **Onmiddellijk**: scherm vergrendelingen na 30 seconden inactiviteit.
  - **1**: het scherm wordt vergrendeld na 1 minuut inactiviteit.
  - **2**: het scherm wordt vergrendeld na 2 minuten van inactiviteit.
  - **3**: het scherm wordt vergrendeld na 3 minuten van inactiviteit.
  - **4**: het scherm wordt vergrendeld na 4 minuten van inactiviteit.
  - **5**: het scherm wordt vergrendeld na 5 minuten van inactiviteit.
    
  **Opties voor iPadOS**:  

  - **Niet geconfigureerd** (standaard): intune raakt deze instelling niet aan.
  - **Onmiddellijk**: scherm vergrendelingen na 2 minuten van inactiviteit.
  - **2**: het scherm wordt vergrendeld na 2 minuten van inactiviteit.
  - **5**: het scherm wordt vergrendeld na 5 minuten van inactiviteit.
  - **10**: scherm vergrendelingen na 10 minuten van inactiviteit.
  - **15**: vergrendelde scherm vergrendelingen na 15 minuten van inactiviteit.

  Als een waarde niet van toepassing is op iOS of iPadOS, gebruikt Apple de dichtstbijzijnde *laagste* waarde. Als u bijvoorbeeld `4` minuten invoert, gebruiken iPadOS-apparaten `2` minuten. Als u `10` minuten invoert, gebruiken iOS-apparaten `5` minuten. Dit is een beperking van Apple.
  
  > [!NOTE]
  > De intune-gebruikers interface voor deze instelling scheidt de door iOS en iPadOS ondersteunde waarden niet. De gebruikers interface kan in een toekomstige versie worden bijgewerkt.

- **Wachtwoordverlooptijd (dagen)** : Geef op na hoeveel dagen het wachtwoord voor het apparaat moet worden gewijzigd.
- **Wachtwoorden niet opnieuw gebruiken**: Voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt.
- **Aanraak-id en face id ontgrendelen**: Kies **blok** om te voor komen dat een vinger afdruk of een gezicht wordt gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd**: staat de gebruiker toe het apparaat te ontgrendelen met deze methoden.

  Door deze instelling te blok keren, voor komt u dat het apparaat wordt ontgrendeld met behulp van FaceID-verificatie

  Face-ID is van toepassing op:  
  - iOS 11.0 en hoger

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Aanpassing van wachtwoordcode**: Selecteer **Blokkeren** om ervoor te zorgen dat de wachtwoordcode niet meer kan worden gewijzigd, toegevoegd of verwijderd. Als deze functie is geblokkeerd worden wijzigingen in de wachtwoordcodebeperkingen genegeerd op apparaten in de supervisiemodus. **Niet geconfigureerd** (standaard): staat toe dat wachtwoordcodes worden toegevoegd, gewijzigd of verwijderd.

  - **Aanraak-id en gezichts-id wijzigen**: met **blok keren** wordt voor komen dat de gebruiker TouchID-vinger afdrukken of gezichts-id kan wijzigen, toevoegen of verwijderen. **Niet geconfigureerd** (standaard): staat de gebruiker toe de TouchID-vingerafdrukken en Face-ID op het apparaat bij te werken.

    Als u deze instelling blokkeert, wordt de gebruiker ook gestopt om te wijzigen, toe te voegen of te verwijderen.

    Face-ID is van toepassing op:  
    - iOS 11.0 en hoger

- **Automatisch wachtwoorden invullen blokkeren**: Selecteer **Blokkeren** om te voorkomen dat de functie Wachtwoorden automatisch invullen wordt gebruikt in iOS. Als u **Blokkeren** kiest, heeft dat ook de volgende gevolgen:

  - Gebruikers wordt niet meer gevraagd om een wachtwoord te gebruiken dat is opgeslagen in Safari of in een app.
  - Automatische sterke wachtwoorden zijn uitgeschakeld en gebruikers krijgen geen suggesties voor sterke wachtwoorden.

  **Niet geconfigureerd** (standaard) staat deze functies toe.

- **Aanvragen voor wachtwoordnabijheid blokkeren**: Selecteer **Blokkeren**, zodat het apparaat van een gebruiker geen wachtwoorden aanvraagt van apparaten in de omgeving. **Niet geconfigureerd** (standaard): staat deze wachtwoordaanvragen toe.
- **Wachtwoorden delen blokkeren**: Selecteer **Blokkeren** om te voorkomen dat wachtwoorden via AirDrop tussen apparaten worden gedeeld. **Niet geconfigureerd** (standaard): staat toe dat wachtwoorden worden gedeeld.
- **Touch ID- of Face ID-verificatie vereisen voor het automatisch invullen van wachtwoorden of creditcardgegevens**: Als **Vereisen** is ingesteld, moeten gebruikers zich verifiëren via Touch ID of Face ID voordat wachtwoorden of creditcardgegevens automatisch kunnen worden ingevuld in Safari en andere apps. Met **Niet geconfigureerd** (standaard) kunnen gebruikers deze functie beheren in de apparaatinstellingen.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger
  
<sup>1</sup>Wanneer u de instellingen **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld** en **Maximum aantal minuten waarna een wachtwoord voor het vergrendelde scherm is vereist** configureert, worden deze opeenvolgend toegepast. Als u de waarde voor beide instellingen bijvoorbeeld instelt op **vijf** minuten, wordt het scherm na vijf minuten automatisch uitgeschakeld en wordt het apparaat vergrendeld na nog eens vijf minuten. Als de gebruiker het scherm echter handmatig uitschakelt, wordt de tweede instelling onmiddellijk toegepast. Nadat de gebruiker in het hetzelfde voorbeeld het scherm heeft uitgeschakeld, wordt het apparaat vijf minuten later vergrendeld.

## <a name="locked-screen-experience"></a>Vergrendeld scherm

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Toegang tot Beheercentrum wanneer het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot de app Beheercentrum te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): verleent gebruikers toegang tot de app Beheercentrum terwijl het apparaat is vergrendeld.
- **Meldingen terwijl het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot meldingen te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): verleent gebruikers toegang tot meldingen zonder dat ze het apparaat hoeven te ontgrendelen.
- **De weergave Vandaag wanneer het apparaat vergrendeld**: Selecteer **Blokkeren** om de toegang tot de weergave Vandaag te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): geeft de gebruiker toegang tot de weergave Vandaag terwijl het apparaat is vergrendeld.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Wallet-meldingen terwijl het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot de app Wallet te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): geeft de gebruiker toegang tot de app Wallet terwijl het apparaat is vergrendeld.

## <a name="app-store-doc-viewing-gaming"></a>App Store, documenten bekijken, gamen

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Zakelijke documenten weergeven in niet-beheerde apps**: Selecteer **Blokkeren** om te voorkomen dat zakelijke documenten in niet-beheerde apps worden weergegeven. **Niet geconfigureerd** (standaard): staat gebruikers toe om zakelijke documenten weer te geven in elke willekeurige app. Voorbeeld: u wilt voorkomen dat gebruikers bestanden uit de OneDrive-app opslaan in Dropbox. Configureer deze instelling als **Blokkeren**. Nadat het apparaat het beleid heeft ontvangen (bijvoorbeeld nadat het opnieuw is opgestart), kunnen er geen bestanden meer worden opgeslagen.


  > [!NOTE]
  > Als deze instelling wordt geblokkeerd, worden toetsen borden van derden die zijn geïnstalleerd vanuit de App Store, ook geblokkeerd.

  - **Onbeheerde apps toestaan om te lezen uit beheerde accounts voor contact personen**: wanneer deze zijn ingesteld op **toestaan**, kunnen niet-beheerde apps, zoals de ingebouwde app voor IOS-contact personen, de contact gegevens van beheerde apps lezen en openen, met inbegrip van de mobiele app van Outlook. **Niet geconfigureerd** (standaard): het lezen en het verwijderen van dubbele contactpersonen uit de ingebouwde app Contacten op het apparaat wordt voorkomen.  
  
    Met deze instelling wordt het lezen van contact gegevens toegestaan of voor komt. De service beheert niet de synchronisatie van contact personen tussen de apps.
  
    Als u deze instelling wilt gebruiken, stelt u **Zakelijke documenten weergeven in niet-beheerde apps** in op **Blokkeren**.

  Zie [support Tip: aangepaste profiel instellingen van intune gebruiken met de IOS-app voor systeem eigen contact personen](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453)voor meer informatie over deze twee instellingen en de invloed op Outlook voor IOS-contact exporteren.

- **AirDrop behandelen als een onbeheerd doel**: Wanneer deze optie is ingesteld op **Vereisen**, wordt AirDrop beschouwd als een onbeheerde bestemming. Het zorgt ervoor dat via beheerde apps geen gegevens meer kunnen worden verzonden met behulp van AirDrop. 
- **Niet-zakelijke documenten weergeven in zakelijke apps**: Met **Blokkeren** voorkomt u dat niet-zakelijke documenten in zakelijke apps worden weergegeven. **Niet geconfigureerd** (standaard): staat gebruikers toe elk willekeurig document weer te geven in zakelijke beheerde apps.

  Als u wilt **blok keren** , voor komt u dat de synchronisatie van contact exporteren in Outlook voor IOS wordt voor komen. Zie [ondersteunings Tip: Outlook IOS-contact personen synchroniseren met IOS12 MDM-besturings elementen inschakelen](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453)voor meer informatie.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Wacht woord voor iTunes Store vereisen voor alle aankopen** **: de gebruiker moet het** wacht woord van Apple ID invoeren voor elke in-app of iTunes-aankoop. **Niet geconfigureerd** (standaard) Hiermee kunnen aankopen zonder wacht woord elke keer worden gevraagd.
- **In-app aankopen**: Selecteer **Blokkeren** om in-app aankopen in de Store te voorkomen. **Niet geconfigureerd** (standaard): staat gebruikers toe aankopen in de Store te doen vanuit een actieve app.
- **Inhoud uit Book Store met de markering Erotisch downloaden**: Selecteer **Blokkeren** om te voorkomen dat gebruikers media downloaden uit de Book Store die is gelabeld als Erotisch. **Niet geconfigureerd** (standaard): staat de gebruiker toe om boeken te downloaden uit de categorie Erotisch.
- **Toestaan dat beheerde apps contact personen naar niet-beheerde accounts voor contact personen schrijven**: wanneer deze optie is ingesteld op **toestaan**, kunnen beheerde apps, zoals de mobiele app van Outlook, contact gegevens opslaan of synchroniseren, inclusief zakelijke contact personen, naar de ingebouwde app voor IOS-contact personen. Als de instelling is ingesteld op **niet geconfigureerd** (standaard), kunnen beheerde apps geen contact gegevens opslaan of synchroniseren met de ingebouwde IOS-contact personen-app op het apparaat.
  
  Als u deze instelling wilt gebruiken, stelt u **Zakelijke documenten weergeven in niet-beheerde apps** in op **Blokkeren**.

- **Regio voor restricties**: Selecteer de regio voor restricties die u wilt gebruiken voor toegestane downloads. En kies vervolgens de toegestane beoordelingen voor **Films**, **Tv-programma's** en **Apps**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **App Store**: Selecteer **Blokkeren** om de toegang tot de App Store te blokkeren op apparaten in de supervisiemodus. Met **Niet geconfigureerd** (standaard) is deze toegang toegestaan.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

  - **Apps installeren via de App Store**: Selecteer **Blokkeren** om de App Store te blokkeren op het startscherm van het apparaat. Eindgebruikers kunnen iTunes nog steeds gebruiken of met Apple Configurator apps installeren. **Niet geconfigureerd** (standaard): de App Store is toegestaan op het startscherm.
  - **Automatisch downloaden van apps**: Selecteer **Blokkeren** om te voorkomen dat apps die zijn gekocht op andere apparaten, automatisch worden gedownload. Dit is niet van invloed op updates voor bestaande apps. **Niet geconfigureerd** (standaard): staat gebruikers toe om apps die zijn gekocht op andere iOS-apparaten, te downloaden op het apparaat.

- **Expliciete muziek-, podcast- of nieuwsinhoud op iTunes**: Selecteer **Blokkeren** om expliciete muziek-, podcast- of nieuwsinhoud op iTunes te blokkeren. **Niet geconfigureerd** (standaard): geeft het apparaat toegang tot inhoud voor volwassenen in de Store. voor iOS 13 en hoger zijn mogelijk alleen apparaten met een super visie vereist. 

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

- **Game Center-vrienden toevoegen**: Met **Blokkeren** voorkomt u dat gebruikers vrienden kunnen toevoegen in Game Center. **Niet geconfigureerd** (standaard): staat de gebruiker toe om vrienden toe te voegen in Game Center.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

- **Game Center**: Met **Blokkeren** blokkeert u het gebruik van de Game Center-app. **Niet geconfigureerd** (standaard): staat gebruik van de app Game Center toe op het apparaat.
- **Games voor meerdere spelers**: Kies **blok** om games voor meerdere spelers te voor komen. **Niet geconfigureerd** (standaard): staat de gebruiker toe om games voor meerdere spelers te spelen op het apparaat.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

- **Toegang tot netwerk station in bestanden app**: met het SMB-protocol (Server Message Block) kunnen apparaten toegang krijgen tot bestanden of andere bronnen op een netwerk server. **Uitschakelen** voor komt dat toegang tot bestanden op een netwerk-SMB-station. Met **Niet geconfigureerd** (standaard) is deze toegang toegestaan.

  Deze functie is van toepassing op:  
  - iOS en iPadOS 13,0 en hoger

## <a name="built-in-apps"></a>Ingebouwde apps

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Siri**: Met **Blokkeren** voorkomt u toegang tot Siri. **Niet geconfigureerd** (standaard): staat toegang tot de spraakassistent Siri toe op het apparaat.
  - **Siri als het apparaat is vergrendeld**: Selecteer **Blokkeren** om te toegang tot Siri te blokkeren wanneer het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): staat toegang tot de spraakassistent Siri toe op het apparaat wanneer het is vergrendeld.

- **Waarschuwingen voor fraude in Safari**: Als u **Vereisen** selecteert, worden fraudewaarschuwingen weergegeven in de webbrowser op het apparaat. Met **Niet geconfigureerd** (standaard) schakelt u deze functie uit.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Spotlight-zoekacties voor de weergave van resultaten op internet**: Met **Blokkeren** zorgt u ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd** (standaard): staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.

- **Safari-cookies**: Kies hoe cookies moeten worden verwerkt op het apparaat. Uw opties zijn:
  - Toestaan
  - Alle cookies blokkeren
  - Cookies van bezochte websites toestaan
  - Cookies van huidige website toestaan

- **Safari JavaScript**: Met **Blokkeren** voorkomt u dat Java-scripts worden uitgevoerd in de browser op het apparaat. **Niet geconfigureerd** (standaard) staat Java-scripts toe.

- **Safari-pop-ups**: Als u **Blokkeren** selecteert, wordt het gebruik van de pop-upblokkering in de webbrowser uitgeschakeld. **Niet geconfigureerd** (standaard) Hiermee staat u de pop-upblokkering toe.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Camera**: Met **Blokkeren** voorkomt u toegang tot de camera op het apparaat. **Niet geconfigureerd** (standaard): staat toegang tot de camera van het apparaat toe.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

  - **FaceTime**: Met **Blokkeren** voorkomt u toegang tot de app FaceTime. **Niet geconfigureerd** (standaard): staat toegang tot de app FaceTime toe op het apparaat.

    Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

- **Siri-filter voor scheldwoorden**: Met **Vereisen** voorkomt u dat grove taal wordt gedicteerd of uitgesproken door Siri.

  Als u deze instelling wilt gebruiken, stelt u de instelling **SIRI** in op **blok keren**.

- **Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet**: Selecteer **Blokkeren** om te voorkomen dat Siri toegang tot websites krijgt om vragen te beantwoorden. **Niet geconfigureerd** (standaard): staat Siri toe om door gebruikers gegenereerde inhoud te raadplegen op internet.

  Als u deze instelling wilt gebruiken, stelt u de instelling **SIRI** in op **blok keren**.

- **Apple News**: Selecteer **Blokkeren** om toegang tot de app Apple News op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat het gebruik van de app Apple News toe.
- **iBooks Store**: Selecteer **Blokkeren** om toegang tot de Book Store op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat gebruikers toe te zoeken naar boeken en deze te kopen in de iBooks Store.
- **Berichten-app op het apparaat**: de **blok kering** voor komt dat gebruikers de berichten-app gebruiken voor iMessage. Als het apparaat tekst berichten ondersteunt, kan de gebruiker nog steeds tekst berichten verzenden en ontvangen met behulp van SMS. **Niet geconfigureerd** (standaard) Hiermee kunt u de app berichten gebruiken om berichten via internet te verzenden en te lezen.
- **Podcasts**: Selecteer **Blokkeren** om toegang tot de app Podcasts op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat het gebruik van de app Podcasts toe.
- **De service Music**: Met **Blokkeren** keert u terug naar de klassieke modus van de app Muziek en wordt de Muziek-service uitgeschakeld. **Niet geconfigureerd** (standaard): staat het gebruik van de app Apple Music toe.
- **iTunes Radio-service**: Selecteer **Blokkeren** om toegang tot de app iTunes Radio op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat het gebruik van de app iTunes Radio toe.
- **iTunes Store**: **niet geconfigureerd** (standaard) Hiermee staat u iTunes toe op de apparaten. **Blok keren** dat gebruikers geen iTunes kunnen gebruiken op het apparaat. 

  Deze functie is van toepassing op:  
  - iOS 4.0 en hoger

- **Mijn iPhone zoeken**: **niet geconfigureerd** (standaard) Hiermee kunt u de functie mijn app zoeken gebruiken om de geschatte locatie van het apparaat op te halen. **Blok keren** dat deze functie in de app zoeken wordt voor komen. 

  Deze functie is van toepassing op:  
  - iOS 13,0 en iPadOS 13,0 en hoger

- **Mijn vrienden zoeken**: **niet geconfigureerd** (standaard) Hiermee kunt u de functie mijn app zoeken gebruiken om familie en vrienden van een Apple-apparaat of iCloud.com te vinden. **Blok keren** dat deze functie in de app zoeken wordt voor komen.

  Deze functie is van toepassing op:  
  - iOS 13,0 en iPadOS 13,0 en hoger

- **Wijzigingen in de instellingen van de app Zoek mijn vrienden**: Met **Blokkeren** voorkomt u wijzigingen in de instellingen van de app Zoek vrienden. **Niet geconfigureerd** (standaard): staat de gebruiker toe de instellingen van de app Zoek vrienden te wijzigen.

- **Spotlight-zoekacties voor de weergave van resultaten op internet**: Met **Blokkeren** zorgt u ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd** (standaard): staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.

- **Het verwijderen van systeem-apps van apparaat blokkeren**: Selecteer **Blokkeren** om te voorkomen dat systeem-apps van het apparaat worden verwijderd. **Niet geconfigureerd** (standaard): staat gebruikers toe om systeemapps te verwijderen.

- **Safari**: Selecteer **Blokkeren** om te voorkomen dat gebruikers de Safari-browser op het apparaat kunnen gebruiken. **Niet geconfigureerd** (standaard): staat gebruikers toe de Safari-browser te gebruiken.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

- **Automatisch invullen in Safari**: Selecteer **Blokkeren** om de functie Automatisch invullen in Safari op het apparaat uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe de instellingen voor automatisch doorvoeren te wijzigen in de webbrowser.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

## <a name="restricted-apps"></a>Beperkte apps

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Lijst met beperkte apps**: een lijst met apps maken die gebruikers niet mogen installeren of gebruiken. Uw opties zijn:

  - **Niet geconfigureerd** (standaard): er zijn geen beperkingen ten opzichte van intune. Gebruikers hebben toegang tot apps die u toewijst en ingebouwde apps.
  - **Niet-toegestane apps**: Apps die niet worden beheerd in Intune waarvan u niet wilt dat deze op het apparaat worden geïnstalleerd. Gebruikers kunnen geen verboden apps installeren. Maar als een gebruiker een app uit deze lijst installeert, wordt deze in intune gerapporteerd.
  - **Goedgekeurde apps**: Apps die gebruikers mogen installeren. Gebruikers mogen geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Er wordt niet voorkomen dat gebruikers een app installeren die niet in de goedgekeurde lijst wordt vermeld. Maar als dat wel het geval is, wordt deze in intune gerapporteerd.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- De App Store-URL van de gewenste iTunes-app **toevoegen**. Voer bijvoorbeeld `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` of `https://apps.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

- **Importeer** een CSV-bestand met details van de app, waaronder de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. Of een bestaande lijst **exporteren** die de beperkte apps bevat in dezelfde indeling.

> [!IMPORTANT]
> Apparaatprofielen die instellingen voor beperkte apps gebruiken, moeten worden toegewezen aan groepen gebruikers.

## <a name="show-or-hide-apps"></a>Apps weergeven of verbergen

Is van toepassing op apparaten met iOS 9,3 of hoger.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Type lijst met apps**: een lijst met apps maken om weer te geven of te verbergen. U kunt ingebouwde apps en line-of-Business-Apps weer geven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094). Uw opties zijn:

  - **Verborgen apps**: Voer een lijst met apps in die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of openen.
  
    Apple voor komt dat sommige systeem eigen apps worden verborgen. U kunt de **instellingen** of de **Wallet** -apps bijvoorbeeld niet verbergen op het apparaat. [Ingebouwde Apple-apps verwijderen](https://support.apple.com/HT208094) bevat de apps die kunnen worden verborgen.
  
  - **Zichtbare apps**: Voer een lijst met apps in die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

- **App-URL**: Voer de URL van de Store-app in van de app die u wilt weer geven of verbergen. Bijvoorbeeld:

  - Voer `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` of `https://apps.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen. 

  - Als u de micro soft Word-app wilt toevoegen, voert u `https://itunes.apple.com/de/app/microsoft-word/id586447913` of `https://apps.apple.com/de/app/microsoft-word/id586447913`.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.
  
  Zie [de bundel-id voor een IOS-app zoeken](https://support.microsoft.com/help/4294074/how-to-find-the-bundle-id-for-an-ios-app)voor meer informatie over het zoeken naar een bundel-id.

- **App-bundel-id**: Voer de [App-bundel-id](bundle-ids-built-in-ios-apps.md) van de gewenste app in. U kunt ingebouwde apps en line-of-Business-Apps weer geven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094).
- **App-naam**: Voer de naam van de gewenste app in. U kunt ingebouwde apps en line-of-Business-Apps weer geven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094).
- **Uitgever**: Voer de uitgever van de gewenste app in.

Ga op een van de volgende manieren te werk om apps toe te voegen:

- **Toevoegen**: Selecteer deze optie om de lijst met apps te maken.
- **Importeer** een CSV-bestand met details van de app, waaronder de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. U kunt ook **exporteren** om een lijst te maken met de beperkte apps die u hebt toegevoegd, in dezelfde indeling.

## <a name="wireless"></a>Draadloos

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

Opmerking vereist voor gegevensroaming (tip of belang rijke opmerking voor meer informatie over de Verwar ring van klanten): deze instelling wordt niet weer gegeven op het beheer Profiel van het doel apparaat. Dat komt doordat deze instelling wordt behandeld als een actie voor een extern apparaat en elke keer dat de status van dataroaming op het apparaat wordt gewijzigd, de intune-service weer wordt geblokkeerd. Hoewel het zich niet in het beheer profiel bevindt, werkt het samen als het wordt weer gegeven als een succes van de rapportage in de beheer console. 
- **Gegevensroaming**: Selecteer **Blokkeren** om dataroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd** (standaard): staat dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.

  > [!IMPORTANT]
  > Deze instelling wordt behandeld als een actie op een extern apparaat. Deze instelling wordt dus niet weer gegeven in het beheer profiel op het apparaat. Telkens wanneer de status van de gegevens roaming op het apparaat wordt gewijzigd, wordt **gegevensroaming** geblokkeerd door de intune-service. Als in intune een succes wordt weer gegeven in de rapportage status, weet u zeker dat het werkt, zelfs als de instelling niet wordt weer gegeven in het beheer profiel op het apparaat.

- **Op de achtergrond ophalen tijdens roaming**: Met **Blokkeren** voorkomt u dat gegevens tijdens roaming op de achtergrond kunnen worden opgehaald via het mobiele netwerk. **Niet geconfigureerd** (standaard): staat het apparaat toe om gegevens zoals e-mail op te halen tijdens roaming op een mobiel netwerk.
- **Voicedialing**: Selecteer **Blokkeren** om te voorkomen dat gebruikers de functie Voicedialing op het apparaat kunnen gebruiken. **Niet geconfigureerd** (standaard): hiermee wordt Nummer inspreken toegestaan op het apparaat.
- **Gespreksroaming**: Selecteer **Blokkeren** om gespreksroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd** (standaard): staat spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Persoonlijke hotspot**: Met **Blokkeren** schakelt u de persoonlijke hotspot op apparaten van de gebruikers uit bij elke apparaatsynchronisatie. Mogelijk is deze instelling niet compatibel met bepaalde providers. Met **Niet geconfigureerd** (standaard) blijft de configuratie van de persoonlijke hotspot behouden als de standaardwaarde die is ingesteld door de gebruiker.

  > [!IMPORTANT]
  > Deze instelling wordt behandeld als een actie op een extern apparaat. Deze instelling wordt dus niet weer gegeven in het beheer profiel op het apparaat. Telkens wanneer de status van de persoonlijke hotspot op het apparaat wordt gewijzigd, wordt de **persoonlijke hotspot** geblokkeerd door de intune-service. Als in intune een succes wordt weer gegeven in de rapportage status, weet u zeker dat het werkt, zelfs als de instelling niet wordt weer gegeven in het beheer profiel op het apparaat.

- **Regels voor mobiel gebruik (alleen beheerde apps)** : Definieer de gegevenstypen die beheerde apps kunnen gebruiken die zijn verbonden met een mobiel netwerk. Uw opties zijn:
  - **Gebruik van mobiel dataverkeer blokkeren**: U kunt het gebruik van mobiel dataverkeer blokkeren voor **Alle beheerde apps** of u kunt **specifieke apps kiezen**.
  - **Gebruik van mobiel dataverkeer tijdens roaming blokkeren**: U kunt het gebruik van mobiel dataverkeer tijdens roaming blokkeren voor **Alle beheerde apps** of u kunt **specifieke apps** kiezen.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Wijzigingen in de instellingen voor het gebruik van mobiel gegevensverkeer voor apps**: Selecteer **Blokkeren** om te voorkomen dat er wijzigingen kunnen worden aangebracht in de instellingen voor het gebruik van mobiel dataverkeer voor apps. **Niet geconfigureerd** (standaard): staat de gebruiker toe om te bepalen welke apps mobiel dataverkeer mogen gebruiken.
- **Wijzigingen in de instellingen voor mobiel gegevensverkeer**: Met **Blokkeren** voorkomt u dat gebruikers instellingen voor mobiel gegevensverkeer wijzigen. Met **Niet geconfigureerd** (standaard) kunnen gebruikers wijzigingen aanbrengen.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Gebruikers wijziging van persoonlijke hotspot**: wanneer u deze optie instelt op **blok keren**, kan de gebruiker de persoonlijke hotspot-instelling niet wijzigen. **Niet geconfigureerd** (standaard) Hiermee kunnen eind gebruikers hun persoonlijke hotspot in-of uitschakelen.

  Als u deze instelling blokkeert en de instelling voor **persoonlijke HOTS pots** blokkeert, wordt de persoonlijke hotspot uitgeschakeld.

  Deze functie is van toepassing op:  
  - iOS 12.2 en hoger

- **Toevoegen aan Wi-Fi-netwerken die alleen configuratieprofielen gebruiken**: Met **Vereisen** dwingt u af dat het apparaat alleen Wi-Fi-netwerken gebruikt die zijn ingesteld via Intune-configuratieprofielen. **Niet geconfigureerd** (standaard): staat het apparaat toe andere Wi-Fi-netwerken te gebruiken.
- **Wi-Fi is altijd ingeschakeld**: wanneer de instelling **vereist**is, blijft Wi-Fi aanwezig in de instellingen-app. Het kan niet worden uitgeschakeld in instellingen of in het beheer centrum, zelfs wanneer het apparaat zich in de vliegtuig modus bevindt. **Niet geconfigureerd** (standaard) Hiermee staat u de gebruiker toe om in te scha kelen het in-of uitschakelen van Wi-Fi.

  Als u deze instelling configureert, wordt niet voor komen dat gebruikers een Wi-Fi-netwerk selecteren.

  Deze functie is van toepassing op:  
  - iOS en iPadOS 13,0 en hoger

## <a name="connected-devices"></a>Verbonden apparaten

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Draagdetectie voor een gekoppelde Apple Watch**: Als u **Vereisen** selecteert, moet de gekoppelde Apple Watch de functie Draagdetectie gebruiken. Wanneer dit is vereist, worden op de Apple Watch geen meldingen weergegeven wanneer deze niet wordt gedragen. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**: Met **Vereisen** stelt u in dat een wachtwoord voor koppelen is vereist wanneer AirPlay wordt gebruikt om inhoud te streamen naar andere Apple-apparaten. **Niet geconfigureerd** (standaard): staat de gebruiker toe inhoud te streamen met AirPlay zonder een wachtwoord in te voeren.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **AirDrop**: Selecteer **Blokkeren** om het gebruik van AirDrop op het apparaat te voorkomen. **Niet geconfigureerd** (standaard): staat het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
- **Koppeling voor Apple Watch**: **blok keren** dat koppelen met een Apple Watch wordt voor komen. **Niet geconfigureerd** (standaard): staat toe dat het apparaat wordt gekoppeld aan een Apple Watch.
- **Aanpassing van Bluetooth**: Selecteer **Blokkeren** om ervoor te zorgen dat de eindgebruiker geen Bluetooth-instellingen meer kan wijzigen op het apparaat. **Niet geconfigureerd** (standaard): staat de gebruiker toe om deze instellingen te wijzigen.
- **Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld**: Met **Niet geconfigureerd** (standaard) staat u het koppelen met een host toe, waarmee de beheerder kan bepalen aan welke apparaten een iOS-apparaat kan worden gekoppeld. **Blokkeren**: voorkomt het koppelen met een host.
- **AirPrint blokkeren**: Selecteer **Blokkeren** om te voorkomen dat de functie AirPrint wordt gebruikt op het apparaat. **Niet geconfigureerd** (standaard): staat de gebruiker toe AirPrint te gebruiken.
  - **Opslag van AirPrint-referenties in de Sleutelhanger blokkeren**: Met **Blokkeren** voorkomt u het gebruik van de Sleutelhanger om de gebruikersnaam en het wachtwoord op te slaan op het apparaat. **Niet geconfigureerd** (standaard): staat toe dat de gebruikersnaam en het wachtwoord van AirPrint worden opgeslagen in de app Sleutelhanger.
  - **Een vertrouwd TLS-certificaat voor AirPrint vereisen**: Met **Vereisen** dwingt u af dat op het apparaat vertrouwde certificaten worden gebruikt voor TLS-afdrukcommunicatie.
  - **iBeacon-detectie van AirPrint-printers blokkeren**: Met **Blokkeren** voorkomt u phishing met schadelijke AirPrint Bluetooth-bakens voor netwerkverkeer. **Niet geconfigureerd** (standaard): staat het adverteren van AirPrint-printers op het apparaat toe.
- **Het instellen van nieuwe apparaten in de buurt blokkeren**: Met **Blokkeren** wordt de vraag om nieuwe apparaten in de buurt in te stellen uitgeschakeld. Met **Niet geconfigureerd** (standaard) wordt gebruikers gevraagd verbinding te maken met andere Apple-apparaten in de buurt.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Toegang tot bestanden op USB-station**: apparaten kunnen verbinding maken en bestanden openen op een USB-station. **Uitschakelen** Hiermee wordt voor komen dat het apparaat toegang heeft tot het USB-station in de app bestanden wanneer een USB-verbinding met het apparaat is gemaakt. Als u deze functie uitschakelt, kunnen eind gebruikers ook geen bestanden overbrengen naar een USB-station dat is verbonden met een iPad. **Niet geconfigureerd** (standaard) Hiermee wordt toegang tot een USB-station in de app bestanden toegestaan.

  Deze functie is van toepassing op:  
  - iOS en iPadOS 13,0 en hoger

## <a name="keyboard-and-dictionary"></a>Toetsenbord en woordenlijst

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Definities van woorden opzoeken**: Met **Blokkeren** voorkomt u dat de gebruiker een woord markeert en vervolgens de definitie ervan opzoekt op het apparaat. **Niet geconfigureerd** (standaard): geeft toegang tot de functie Opzoeken van definities van woorden.
- **Tekstvoorspelling**: Met **Niet geconfigureerd** (standaard) staat u het gebruik van tekstvoorspelling toe voor suggesties voor woorden die de gebruiker mogelijk wil invoeren. Met **Blokkeren** wordt deze functie geblokkeerd.
- **Automatische correctie**: Met **Niet geconfigureerd** (standaard) staat u automatische correctie van verkeerd gespelde woorden toe op het apparaat. **Blokkeren**: blokkeert het gebruik van Autocorrectie.
- **Spelling controle voor het toetsen bord**: **niet geconfigureerd** (standaard) Hiermee kunt u de spellingcontrole functie op het apparaat gebruiken. **Blokkeren**: staat de spellingcontrole toe.
- **Sneltoetsen**: **niet geconfigureerd** (standaard) Hiermee kunt u sneltoetsen op het apparaat gebruiken. **Blokkeren**: zorgt ervoor dat de gebruiker geen sneltoetsen meer kan gebruiken.
- **Dicteren**: Met **Blokkeren** zorgt u ervoor dat de gebruiker geen spraak meer kan gebruiken om tekst in te voeren. **Niet geconfigureerd** (standaard): staat de gebruiker toe invoer van Dicteren te gebruiken.
- **QuickPath**: **niet geconfigureerd** (standaard) Hiermee kunnen gebruikers QuickPath gebruiken, waarmee doorlopende invoer kan worden gebruikt op het toetsen bord van het apparaat. Gebruikers kunnen typen door te vegen over de sleutels om woorden te maken. **Blok keren** dat gebruikers geen gebruik kunnen maken van QuickPath. 

  Deze functie is van toepassing op:  
  - iOS 13,0 en iPadOS 13,0 en hoger

## <a name="cloud-and-storage"></a>Cloud en opslag

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Versleutelde back-up**: Selecteer **Vereisen** om ervoor te zorgen dat back-ups van het apparaat moeten worden versleuteld.
- **Beheerde apps synchroniseren met de cloud**: Met **Niet geconfigureerd** (standaard) staat u toe dat in door Intune beheerde apps gegevens kunnen worden gesynchroniseerd naar het iCloud-account van de gebruiker. **Blokkeren**: voorkomt deze gegevenssynchronisatie naar iCloud.
- **Back-ups van Enterprise Book blokkeren**: Selecteer **Blokkeren** om te voorkomen dat gebruikers back-ups maken van Enterprise Book-boeken. **Niet geconfigureerd** (standaard): staat gebruikers toe om back-ups te maken van deze boeken.
- **Synchronisatie van metagegevens van Enterprise Book blokkeren (notities en markeringen)** : Met **Blokkeren** voorkomt u dat notities en markeringen in Enterprise Book-boeken worden gesynchroniseerd. Met **Niet geconfigureerd** (standaard) staat u synchronisatie toe.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Photo Stream synchroniseren met iCloud**: Met **Niet geconfigureerd** (standaard) stelt u gebruikers in staat **Mijn fotostream** in te schakelen op hun apparaat om te synchroniseren met iCloud, en foto's weer te geven op alle apparaten van de gebruikers. **Blokkeren**: voorkomt dat met Photo Stream foto’s worden gesynchroniseerd met iCloud. Als u deze functie blokkeert, kan dit leiden tot gegevens verlies. 
- **iCloud-fotobibliotheek**: Selecteer **Blokkeren** om het gebruik van de iCloud-fotobibliotheek voor het opslaan van foto's en video's in de cloud uit te schakelen. Foto's die niet volledig naar het apparaat zijn gedownload vanaf de iCloud-fotobibliotheek, worden van het apparaat verwijderd. **Niet geconfigureerd** (standaard): staat het gebruik van de iCloud-fotobibliotheek toe.
- **Gedeelde fotostream**: Selecteer **Blokkeren** om **iCloud-fotodeling** uit te schakelen op het apparaat. **Niet geconfigureerd** (standaard): staat streaming van gedeelde foto’s toe.
- Te **leveren:** **niet geconfigureerd** (standaard) Hiermee kunnen gebruikers beginnen met het werken met een IOS-apparaat en vervolgens het werk voortzetten dat ze op een ander IOS-of macOS-apparaat hebben gestart. **Blokkeren**: voorkomt deze handoff.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Back-up naar iCloud**: Met **Niet geconfigureerd** (standaard) staat u de gebruiker toe een back-up van het apparaat op te slaan in iCloud. **Blokkeren**: zorgt ervoor dat de gebruiker geen back-ups van het apparaat meer kan opslaan in iCloud.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

- **iCloud-documentsynchronisatie blokkeren**: Met **Niet geconfigureerd** (standaard) staat u het synchroniseren van documenten en sleutelwaarden met uw iCloud-opslagruimte toe. **Blokkeren**: voorkomt dat documenten en gegevens worden gesynchroniseerd met iCloud.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

- **Synchronisatie van iCloud-sleutelhanger blokkeren**: Selecteer **Blokkeren** om het synchroniseren van referenties die zijn opgeslagen in de Sleutelhanger, naar iCloud uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe deze referenties te synchroniseren.

  Vanaf iOS 13,0 vereist deze instelling apparaten met een super visie.

## <a name="autonomous-single-app-mode"></a>Autonome modus voor één app

Gebruik deze instellingen om iOS-apparaten zodanig te configureren dat hierop specifieke apps in de autonome één-app-modus worden uitgevoerd. Wanneer deze modus is geconfigureerd en de app wordt uitgevoerd, wordt het apparaat vergrendeld. Alleen deze ene app kan worden uitgevoerd. Voeg bijvoorbeeld een app toe waarmee gebruikers een test kunnen uitvoeren op het apparaat. Wanneer de acties van de app zijn voltooid of u het beleid verwijdert, keert het apparaat terug naar de normale staat.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **App-naam**: Voer de naam in van de gewenste app.
- **App-bundel-id**: Voer de [bundel-id](bundle-ids-built-in-ios-apps.md) in van de gewenste app.
- **Toevoegen**: Selecteer deze optie om de lijst met apps te maken.

U kunt ook een CSV-bestand met de lijst met app-namen en de bijbehorende bundel-id’s **importeren**. Of **Exporteer** een bestaande lijst die de apps bevat.

## <a name="kiosk"></a>Kiosk

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **App uitvoeren in kioskmodus**: Selecteer het type apps dat u wilt uitvoeren in de kioskmodus. Uw opties zijn:
  - **Niet geconfigureerd** (standaard): De kioskinstellingen worden niet toegepast. Het apparaat wordt niet uitgevoerd in de kioskmodus.
  - **Store-app**: Voer de URL in voor een app in de iTunes App Store.
  - **Beheerde app**: Selecteer een app die u hebt toegevoegd aan Intune.
  - **Ingebouwde app**: Voer de [bundel-id](bundle-ids-built-in-ios-apps.md) in van de ingebouwde app.

- **Ondersteunende aanraking**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Ondersteunende aanraking op het apparaat te vereisen. Deze functie helpt gebruikers bij schermbewegingen die mogelijk moeilijk zijn voor hen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Keer kleuren om**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Keer kleuren om in te stellen, zodat gebruikers met een beperkt gezichtsvermogen de display kunnen wijzigen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Mono-audio**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Mono-audio op het apparaat te vereisen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Spraak controle**: **vereisen** spraak controle op het apparaat, en stelt gebruikers in staat om het besturings systeem volledig te beheren met behulp van SIRI-opdrachten. Als u deze **niet configureert** , wordt de spraak besturing uitgeschakeld op het apparaat.

  Deze instelling is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger
  
  > [!TIP]
  > Als u beschikt over LOB-apps die beschikbaar zijn voor uw organisatie en u geen **spraak controle** hebt gemaakt op dag 0 wanneer IOS 13,0 wordt vrijgegeven, wordt u aangeraden deze instelling **niet geconfigureerd**te laten.

- **VoiceOver**: Selecteer **Vereisen** om de toegankelijkheidsinstelling VoiceOver te vereisen op het apparaat om tekst op het scherm hardop voor te lezen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Zoomen**: Selecteer **Vereisen**, zodat gebruikers met behulp van aanraken het scherm kunnen inzoomen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Automatisch vergren delen**: de **blok kering** voor komt dat het apparaat automatisch wordt vergrendeld. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Schakelaar voor belsignaal**: Met **Blokkeren** wordt de schakelaar voor belsignaal (dempen) op het apparaat uitgeschakeld. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Scherm draaien**: Met **Blokkeren** blijft de schermstand ongewijzigd wanneer de gebruiker het apparaat draait. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Schermsluimerknop**: Kies **Blokkeren** om de knop voor slaapstand/ontwaken van het scherm op het apparaat uit te schakelen. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Aanraken**: Met **Blokkeren** wordt het aanraakscherm uitgeschakeld op het apparaat. **Niet geconfigureerd**: staat de gebruiker toe het aanraakscherm te gebruiken.
- **Volume knoppen**: **blok keren** voor komt dat de volume knoppen op het apparaat worden gebruikt. Met **niet geconfigureerd** kunt u de volume knoppen.
- **Besturingselement voor ondersteunende aanraking**: Selecteer **Toestaan**, zodat gebruikers de functie Ondersteunende aanraking kunnen gebruiken. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Besturingselement voor kleuren omkeren**: Met **Toestaan** staat u aanpassingen in de functie Keer kleuren om toe, zodat gebruikers deze functie kunnen aanpassen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Geselecteerde tekst uitspreken**: Selecteer **Toestaan** om de toegankelijkheidsinstellingen Selectie uitspreken op het apparaat toe te staan. Met deze functie wordt tekst die de gebruiker selecteert, hardop gelezen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Wijziging van spraak besturings elementen**: **Hiermee staat u gebruikers toe** de status van spraak besturing op hun apparaten te wijzigen. **Niet geconfigureerd** blokkeert gebruikers om de status van spraak besturing op hun apparaten te wijzigen.

  Deze instelling is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger

- **Besturingselement voor VoiceOver**: Selecteer **Toestaan**, zodat gebruikers de functie VoiceOver kunnen bijwerken, bijvoorbeeld hoe snel schermtekst hardop wordt gelezen. **Niet geconfigureerd**: voorkomt wijzigingen in Voice-over.
- **Besturingselement voor zoomen**: Selecteer **Toestaan**, zodat gebruikers de zoominstelling kunnen aanpassen. **Niet geconfigureerd**: voorkomt wijzigingen in Inzoomen.

> [!NOTE]
> Voordat u een iOS-apparaat voor de kioskmodus kunt configureren, moet u het hulpprogramma Apple Configurator of het Device Enrollment Program van Apple gebruiken om het apparaat in de supervisiemodus te plaatsen. Raadpleeg de handleiding van Apple voor het gebruik van het hulpprogramma Apple Configurator.
> Als de iOS-app die u invoert, wordt geïnstalleerd nadat u het profiel hebt toegewezen, wordt de kioskmodus van het apparaat pas geactiveerd nadat het opnieuw is opgestart.

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Niet-gemarkeerde e-maildomeinen** > **URL van e-maildomein**: Voeg een of meer URL's toe aan de lijst. Wanneer eindgebruikers een e-mail ontvangen die afkomstig is van een ander domein dan de domeinen die u invoert, wordt de e-mail in de iOS Mail-app gemarkeerd als niet-vertrouwd.

- **Beheerde webdomeinen** > **Webdomein-URL**: Voeg een of meer URL's toe aan de lijst. Wanneer documenten worden gedownload uit de domeinen die u invoert, worden ze beschouwd als beheerd. Deze instelling geldt alleen voor documenten die zijn gedownload met Safari.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Domeinen voor automatisch invullen van Safari-wachtwoorden** > **Domein-URL**: Voeg een of meer URL's toe aan de lijst. Gebruikers kunnen in deze lijst alleen webwachtwoorden van URL's opslaan. Deze instelling geldt alleen voor Safari en voor apparaten die onder supervisie staan. Als u geen URL's invoert, kunnen wachtwoorden van alle websites worden opgeslagen.

  Deze instelling is van toepassing op:  
  - iOS 9.3 en hoger

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
>
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

[Het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

U kunt ook apparaatfuncties en -instellingen beperken op [macOS](device-restrictions-macos.md)-apparaten.
