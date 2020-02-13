---
title: iOS-apparaatinstellingen in Microsoft Intune - Azure | Microsoft Docs
titleSuffix: ''
description: U kunt instellingen voor iOS-apparaten toevoegen, configureren of maken om functies te beperken, zoals wachtwoordvereisten instellen, het vergrendelingsscherm beheren, ingebouwde apps gebruiken, beperkte of goedgekeurde apps toevoegen, Bluetooth-apparaten verwerken, verbinding maken met de cloud voor back-up en opslag, de kioskmodus inschakelen, domeinen toevoegen, en bepalen hoe gebruikers de Safari-webbrowser kunnen gebruiken in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: dc252068d963d75bf6ade79852d6ba01bda8800b
ms.sourcegitcommit: 9b29478f815e10c46c8030abe0146d601ce0e28c
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77051606"
---
# <a name="ios-and-ipados-device-settings-to-allow-or-restrict-features-using-intune"></a>Met instellingen voor iOS- en iPadOS-apparaten kunt u functies toestaan of beperken met behulp van Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op iOS- en iPadOS-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, wachtwoordregels in te stellen, bepaalde apps toe te staan of te beperken en nog veel meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw iOS-apparaten.

> [!TIP]
> Voor deze instellingen worden de MDM-instellingen van Apple gebruikt. Raadpleeg [Instellingen voor mobielapparaatbeheer van Apple](https://support.apple.com/guide/mdm/welcome/web) (hiermee opent u de website van Apple) voor meer informatie over deze instellingen.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een configuratieprofiel voor apparaatbeperkingen](../device-restrictions-configure.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvingstypen, waarbij sommige instellingen van toepassing zijn op alle inschrijvingsopties. Zie [iOS-inschrijving](../ios-enroll.md) voor meer informatie over de verschillende inschrijvingstypen.

## <a name="general"></a>Algemeen

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Gebruiksgegevens delen**: Kies **Blokkeren** om te voorkomen dat met het apparaat diagnostische gegevens en gebruiksgegevens worden verzonden naar Apple. **Niet geconfigureerd** (standaard): staat toe dat deze gegevens worden verzonden.

- **Schermopname**: Selecteer **Blokkeren** om te voorkomen dat schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. In iOS 9.0 en hoger worden ook schermopnamen geblokkeerd. **Niet geconfigureerd** (standaard): stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding of video.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Niet-vertrouwde TLS-certificaten**: Selecteer **Blokkeren** om te voorkomen dat niet-vertrouwde TLS-certificaten (Transport Layer Security) zijn toegestaan op het apparaat. Met **Niet geconfigureerd** (standaard) staat u TLS-certificaten toe.
- **Draadloze PKI-updates blokkeren**: **Blokkeren** voorkomt dat uw gebruikers software-updates ontvangen tenzij het apparaat is verbonden met een computer. **Niet geconfigureerd** (standaard): hiermee staat u toe dat een apparaat software-updates ontvangt zonder dat het verbonden is met een computer.
- **Bijhouden van advertenties beperken**: Selecteer **Beperken** om de advertentie-id van het apparaat uit te schakelen. Met **Niet geconfigureerd** (standaard) blijft deze instelling ingeschakeld.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Aanpassing van instellingen voor het verzenden van diagnostische gegevens**: Met **Blokkeren** voorkomt u dat de gebruiker de instelling voor verzending van diagnostische gegevens en app-analyse wijzigt in **Diagnostische gegevens en gebruik** (in Instellingen op het apparaat). **Niet geconfigureerd** (standaard): staat de gebruiker toe om deze apparaatinstellingen te wijzigen.

  Stel de instelling **Gebruiksgegevens delen** in op **Blokkeren** als u deze instelling wilt gebruiken.

  Deze functie is van toepassing op:  
  - iOS 9.3.2 en hoger

- **Observatie van extern scherm met de app Classroom**: Selecteer **Blokkeren** om te voorkomen dat de app Klaslokaal het scherm op het apparaat op afstand kan weergeven. **Niet geconfigureerd** (standaard): staat de app Apple Classroom toe het scherm weer te geven.

  Stel de instelling **Schermopname** in op **Blokkeren** als u deze instelling wilt gebruiken.

  Deze functie is van toepassing op:  
  - iOS 9.3 en hoger

- **Ongevraagde schermobservatie met de app Classroom**: Wanneer deze optie is ingesteld op **Toestaan**, kunnen docenten het scherm op de iOS-apparaten van leerlingen/studenten met de app Klaslokaal observeren zonder dat de leerlingen/studenten dit weten. Op apparaten van leerlingen/studenten die zijn ingeschreven bij een cursus met de app Classroom, is toestemming voor de docent van deze cursus automatisch ingeschakeld. Met **Niet geconfigureerd** (standaard) voorkomt u deze functie.

  Stel de instelling **Schermopname** in op **Blokkeren** als u deze instelling wilt gebruiken.

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
- **USB-accessoires toestaan terwijl het apparaat is vergrendeld**: Met **Toestaan** kunnen USB-accessoires gegevens uitwisselen met een apparaat dat al meer dan een uur is vergrendeld. **Niet geconfigureerd** (standaard) werkt de beperkte USB-modus niet bij op het apparaat en USB-accessoires kunnen geen gegevens overdragen vanaf het apparaat als het meer dan een uur is vergrendeld.
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

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Wachtwoord**: **Vereisen** dat de eindgebruiker een wachtwoord invoert voor toegang tot het apparaat. **Niet geconfigureerd** (standaard): geeft gebruikers toegang tot het apparaat zonder dat ze een wachtwoord hoeven in te voeren.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

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

- **Minimale wachtwoordlengte**: Voer de minimale lengte in die een gebruiker moet invoeren, tussen 4 en 14 tekens. Voer een lengte tussen 4 en 6 tekens in voor door de gebruiker ingeschreven apparaten.
  
  > [!NOTE]
  > Voor apparaten die door de gebruiker zijn ingeschreven, kunnen gebruikers een pincode van meer dan 6 cijfers instellen. Er worden echter niet meer dan 6 cijfers afgedwongen op het apparaat. Stel dat een beheerder de minimale lengte instelt op `8`. Gebruikers hoeven op apparaten die door gebruikers zijn ingeschreven alleen een 6-cijferig pincode in te stellen. Intune dwingt geen pincode van meer dan 6 cijfers af op door gebruikers geregistreerde apparaten.

- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Voer het aantal mislukte aanmeldingen in dat is toegestaan voordat het apparaat wordt gewist (tussen 4 en 11).
  
  iOS heeft ingebouwde beveiliging die van invloed kan zijn op deze instelling. iOS kan bijvoorbeeld het activeren van het beleid vertragen, afhankelijk van het aantal mislukte aanmeldingen. Ook kan het besturingssysteem het herhaaldelijk invoeren van dezelfde toegangscode als één poging beschouwen. De [iOS-beveiligingshandleiding](https://www.apple.com/business/site/docs/iOS_Security_Guide.pdf) van Apple (hiermee opent u de website van Apple) is een goede bron en biedt meer specifieke informatie over toegangscodes.
  
- **Maximum aantal minuten na schermvergrendeling voordat wachtwoord is vereist**<sup>1</sup>: Geef op hoelang het apparaat inactief blijft voordat gebruikers hun wachtwoord opnieuw moeten invoeren. Als de ingevoerde tijd langer is dan de tijd die is ingesteld op het apparaat, wordt de door u ingevoerde tijd genegeerd. Ondersteund op iOS 8.0-apparaten en nieuwere apparaten.

- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**<sup>1</sup>: Voer het maximale aantal minuten van inactiviteit in dat is toegestaan op het apparaat totdat het scherm wordt vergrendeld.

  **iOS-opties**:  

  - **Niet geconfigureerd** (standaard): Deze instelling wordt niet gewijzigd door Intune.
  - **Onmiddellijk**: Het scherm wordt vergrendeld na 30 seconden inactiviteit.
  - **1**: Het scherm wordt vergrendeld na 1 minuut inactiviteit.
  - **2**: Het scherm wordt vergrendeld na 2 minuten inactiviteit.
  - **3**: Het scherm wordt vergrendeld na 3 minuten inactiviteit.
  - **4**: Het scherm wordt vergrendeld na 4 minuten inactiviteit.
  - **5**: Het scherm wordt vergrendeld na 5 minuten inactiviteit.
    
  **Opties voor iPadOS**:  

  - **Niet geconfigureerd** (standaard): Deze instelling wordt niet gewijzigd door Intune.
  - **Onmiddellijk**: Het scherm wordt vergrendeld na 2 minuten inactiviteit.
  - **2**: Het scherm wordt vergrendeld na 2 minuten inactiviteit.
  - **5**: Het scherm wordt vergrendeld na 5 minuten inactiviteit.
  - **10**: Het scherm wordt vergrendeld na 10 minuten inactiviteit.
  - **15**: Het scherm wordt vergrendeld na 15 minuten inactiviteit.

  Als een waarde niet op iOS of iPadOS van toepassing is, gebruikt Apple de dichtstbijzijnde *laagste* waarde. Als u bijvoorbeeld `4` minuten invoert, zullen iPadOS-apparaten `2` minuten gebruiken. Als u `10` minuten invoert, gebruiken iOS-apparaten `5` minuten. Dit is een beperking van Apple.
  
  > [!NOTE]
  > De Intune-gebruikersinterface voor deze instelling scheidt de door iOS en iPadOS ondersteunde waarden niet. De gebruikersinterface wordt in een toekomstige versie mogelijk bijgewerkt.

- **Wachtwoordverlooptijd (dagen)** : Geef op na hoeveel dagen het wachtwoord voor het apparaat moet worden gewijzigd.
- **Wachtwoorden niet opnieuw gebruiken**: Voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt.
- **Ontgrendelen met Touch ID en Face ID**: Selecteer **Blokkeren** om te voorkomen dat een vingerafdruk of gezichtsherkenning kan worden gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd**: staat de gebruiker toe het apparaat te ontgrendelen met deze methoden.

  Door deze instelling te blokkeren, voorkomt u ook dat het apparaat wordt ontgrendeld met behulp van Face ID-verificatie.

  Face ID is van toepassing op:  
  - iOS 11.0 en hoger

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Aanpassing van wachtwoordcode**: Selecteer **Blokkeren** om ervoor te zorgen dat de wachtwoordcode niet meer kan worden gewijzigd, toegevoegd of verwijderd. Als deze functie is geblokkeerd worden wijzigingen in de wachtwoordcodebeperkingen genegeerd op apparaten in de supervisiemodus. **Niet geconfigureerd** (standaard): staat toe dat wachtwoordcodes worden toegevoegd, gewijzigd of verwijderd.

  - **Aanpassing van Touch ID en Face ID**: Met **Blokkeren** zorgt u ervoor dat de gebruiker geen Touch ID-vingerafdrukken en Face ID meer kan wijzigen, toevoegen of verwijderen. **Niet geconfigureerd** (standaard): staat de gebruiker toe de TouchID-vingerafdrukken en Face-ID op het apparaat bij te werken.

    Als u deze instelling blokkeert, kan de gebruiker ook geen Face ID-verificatie meer wijzigen, toevoegen of verwijderen.

    Face ID is van toepassing op:  
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

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Toegang tot Beheercentrum wanneer het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot de app Beheercentrum te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): verleent gebruikers toegang tot de app Beheercentrum terwijl het apparaat is vergrendeld.
- **Meldingen terwijl het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot meldingen te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): verleent gebruikers toegang tot meldingen zonder dat ze het apparaat hoeven te ontgrendelen.
- **De weergave Vandaag wanneer het apparaat vergrendeld**: Selecteer **Blokkeren** om de toegang tot de weergave Vandaag te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): geeft de gebruiker toegang tot de weergave Vandaag terwijl het apparaat is vergrendeld.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Wallet-meldingen terwijl het apparaat is vergrendeld**: Selecteer **Blokkeren** om de toegang tot de app Wallet te blokkeren terwijl het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): geeft de gebruiker toegang tot de app Wallet terwijl het apparaat is vergrendeld.

## <a name="app-store-doc-viewing-gaming"></a>App Store, documenten bekijken, gamen

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Zakelijke documenten weergeven in niet-beheerde apps**: Selecteer **Blokkeren** om te voorkomen dat zakelijke documenten in niet-beheerde apps worden weergegeven. **Niet geconfigureerd** (standaard): staat gebruikers toe om zakelijke documenten weer te geven in elke willekeurige app. Voorbeeld: u wilt voorkomen dat gebruikers bestanden uit de OneDrive-app opslaan in Dropbox. Configureer deze instelling als **Blokkeren**. Nadat het apparaat het beleid heeft ontvangen (bijvoorbeeld nadat het opnieuw is opgestart), kunnen er geen bestanden meer worden opgeslagen.


  > [!NOTE]
  > Als deze instelling wordt geblokkeerd, worden ook toetsenborden van derden geblokkeerd die vanuit de App Store zijn geïnstalleerd.

  - **Toestaan dat niet-beheerde apps contactpersonen lezen in beheerde accounts voor contactpersonen**: Als deze instelling is ingesteld op **Toestaan**, kunnen niet-beheerde apps, zoals de ingebouwde iOS-app Contacten, de contactgegevens van beheerde apps lezen en openen, met inbegrip van de mobiele Outlook-app. **Niet geconfigureerd** (standaard): het lezen en het verwijderen van dubbele contactpersonen uit de ingebouwde app Contacten op het apparaat wordt voorkomen.  
  
    Met deze instelling wordt het lezen van contactgegevens toegestaan of voorkomen. Met de service wordt de synchronisatie van contactpersonen tussen de apps niet beheerd.
  
    Als u deze instelling wilt gebruiken, stelt u **Zakelijke documenten weergeven in niet-beheerde apps** in op **Blokkeren**.

  Voor meer informatie over deze twee instellingen en de invloed ervan op het synchroniseren van geëxporteerde contactpersonen in Outlook voor iOS raadpleegt u [Ondersteuningstip: Aangepaste profielinstellingen in Intune gebruiken voor de systeemeigen contactpersonen-app in iOS](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Use-Intune-custom-profile-settings-with-the-iOS/ba-p/298453).

- **AirDrop behandelen als een onbeheerd doel**: Wanneer deze optie is ingesteld op **Vereisen**, wordt AirDrop beschouwd als een onbeheerde bestemming. Het zorgt ervoor dat via beheerde apps geen gegevens meer kunnen worden verzonden met behulp van AirDrop. 
- **Niet-zakelijke documenten weergeven in zakelijke apps**: Met **Blokkeren** voorkomt u dat niet-zakelijke documenten in zakelijke apps worden weergegeven. **Niet geconfigureerd** (standaard): staat gebruikers toe elk willekeurig document weer te geven in zakelijke beheerde apps.

  Als u deze instelling op **Blokkeren** instelt, voorkomt u ook de synchronisatie van geëxporteerde contactpersonen in Outlook voor iOS. Voor meer informatie raadpleegt u [Ondersteuningstip: Synchronisatie van contactpersonen in Outlook voor iOS inschakelen met MDM-besturingselementen in iOS 12](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Enabling-Outlook-iOS-Contact-Sync-with-iOS12-MDM/ba-p/298453).

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **iTunes Store-wachtwoord voor alle aankopen vereisen**: Met **Vereisen** moet de gebruiker het Apple ID-wachtwoord invoeren voor elke in-app- of iTunes-aankoop. **Niet geconfigureerd** (standaard): hiermee zijn aankopen mogelijk zonder dat elke keer om het wachtwoord wordt gevraagd.
- **In-app aankopen**: Selecteer **Blokkeren** om in-app aankopen in de Store te voorkomen. **Niet geconfigureerd** (standaard): staat gebruikers toe aankopen in de Store te doen vanuit een actieve app.
- **Inhoud uit Book Store met de markering Erotisch downloaden**: Selecteer **Blokkeren** om te voorkomen dat gebruikers media downloaden uit de Book Store die is gelabeld als Erotisch. **Niet geconfigureerd** (standaard): staat de gebruiker toe om boeken te downloaden uit de categorie Erotisch.
- **Toestaan dat beheerde apps contactpersonen doorgeven aan niet-beheerde accounts voor contactpersonen**: Als deze optie is ingesteld op **Toestaan** kunnen beheerde apps, zoals de mobiele Outlook-app, contactinformatie, inclusief zakelijke contactpersonen, opslaan in of synchroniseren met de ingebouwde iOS-app Contacten op het apparaat. Als de instelling is ingesteld op **Niet geconfigureerd** (standaard), kunnen beheerde apps geen contactgegevens opslaan op of synchroniseren met de ingebouwde app Contacten op het iOS-apparaat.
  
  Als u deze instelling wilt gebruiken, stelt u **Zakelijke documenten weergeven in niet-beheerde apps** in op **Blokkeren**.

- **Regio voor restricties**: Selecteer de regio voor restricties die u wilt gebruiken voor toegestane downloads. En kies vervolgens de toegestane beoordelingen voor **Films**, **Tv-programma's** en **Apps**.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **App Store**: Selecteer **Blokkeren** om de toegang tot de App Store te blokkeren op apparaten in de supervisiemodus. Met **Niet geconfigureerd** (standaard) is deze toegang toegestaan.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

  - **Apps installeren via de App Store**: Selecteer **Blokkeren** om de App Store te blokkeren op het startscherm van het apparaat. Eindgebruikers kunnen iTunes nog steeds gebruiken of met Apple Configurator apps installeren. **Niet geconfigureerd** (standaard): de App Store is toegestaan op het startscherm.
  - **Automatisch downloaden van apps**: Selecteer **Blokkeren** om te voorkomen dat apps die zijn gekocht op andere apparaten, automatisch worden gedownload. Dit is niet van invloed op updates voor bestaande apps. **Niet geconfigureerd** (standaard): staat gebruikers toe om apps die zijn gekocht op andere iOS-apparaten, te downloaden op het apparaat.

- **Expliciete muziek-, podcast- of nieuwsinhoud op iTunes**: Selecteer **Blokkeren** om expliciete muziek-, podcast- of nieuwsinhoud op iTunes te blokkeren. **Niet geconfigureerd** (standaard): geeft het apparaat toegang tot inhoud voor volwassenen in de Store. Voor iOS 13 en hoger zijn mogelijk alleen apparaten onder supervisie vereist. 

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

- **Game Center-vrienden toevoegen**: Met **Blokkeren** voorkomt u dat gebruikers vrienden kunnen toevoegen in Game Center. **Niet geconfigureerd** (standaard): staat de gebruiker toe om vrienden toe te voegen in Game Center.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

- **Game Center**: Met **Blokkeren** blokkeert u het gebruik van de Game Center-app. **Niet geconfigureerd** (standaard): staat gebruik van de app Game Center toe op het apparaat.
- **Games voor meerdere spelers**: Selecteer **Blokkeren** om te voorkomen dat gebruikers kunnen gamen met meerdere spelers. **Niet geconfigureerd** (standaard): staat de gebruiker toe om games voor meerdere spelers te spelen op het apparaat.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

- **Toegang tot netwerkstation in de app Bestanden**: Met behulp van het Server Message Block-protocol (SMB) kunnen apparaten toegang krijgen tot bestanden of andere resources op een netwerkserver. Met **Uitschakelen** voorkomt u toegang tot bestanden op een netwerkstation via SMB. Met **Niet geconfigureerd** (standaard) is deze toegang toegestaan.

  Deze functie is van toepassing op:  
  - iOS en iPadOS 13.0 en hoger

## <a name="built-in-apps"></a>Ingebouwde apps

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Siri**: Met **Blokkeren** voorkomt u toegang tot Siri. **Niet geconfigureerd** (standaard): staat toegang tot de spraakassistent Siri toe op het apparaat.
  - **Siri als het apparaat is vergrendeld**: Selecteer **Blokkeren** om te toegang tot Siri te blokkeren wanneer het apparaat is vergrendeld. **Niet geconfigureerd** (standaard): staat toegang tot de spraakassistent Siri toe op het apparaat wanneer het is vergrendeld.

- **Waarschuwingen voor fraude in Safari**: Als u **Vereisen** selecteert, worden fraudewaarschuwingen weergegeven in de webbrowser op het apparaat. Met **Niet geconfigureerd** (standaard) schakelt u deze functie uit.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Spotlight-zoekacties voor de weergave van resultaten op internet**: Met **Blokkeren** zorgt u ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd** (standaard): staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.

- **Safari-cookies**: Kies hoe cookies moeten worden verwerkt op het apparaat. Uw opties zijn:
  - Toestaan
  - Alle cookies blokkeren
  - Cookies van bezochte websites toestaan
  - Cookies van huidige website toestaan

- **Safari JavaScript**: Met **Blokkeren** voorkomt u dat Java-scripts worden uitgevoerd in de browser op het apparaat. Met **Niet geconfigureerd** (standaard) staat u Java-scripts toe.

- **Safari-pop-ups**: Als u **Blokkeren** selecteert, wordt het gebruik van de pop-upblokkering in de webbrowser uitgeschakeld. Met **Niet geconfigureerd** (standaard) staat u de pop-upblokkering toe.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Camera**: Met **Blokkeren** voorkomt u toegang tot de camera op het apparaat. **Niet geconfigureerd** (standaard): staat toegang tot de camera van het apparaat toe.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

  - **FaceTime**: Met **Blokkeren** voorkomt u toegang tot de app FaceTime. **Niet geconfigureerd** (standaard): staat toegang tot de app FaceTime toe op het apparaat.

    Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

- **Siri-filter voor scheldwoorden**: Met **Vereisen** voorkomt u dat grove taal wordt gedicteerd of uitgesproken door Siri.

  Stel de instelling **Siri** in op **Blokkeren** om deze instelling te gebruiken.

- **Query's uitvoeren met Siri op door gebruikers gegenereerde inhoud op internet**: Selecteer **Blokkeren** om te voorkomen dat Siri toegang tot websites krijgt om vragen te beantwoorden. **Niet geconfigureerd** (standaard): staat Siri toe om door gebruikers gegenereerde inhoud te raadplegen op internet.

  Stel de instelling **Siri** in op **Blokkeren** om deze instelling te gebruiken.

- **Apple News**: Selecteer **Blokkeren** om toegang tot de app Apple News op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat het gebruik van de app Apple News toe.
- **iBooks Store**: Selecteer **Blokkeren** om toegang tot de Book Store op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat gebruikers toe te zoeken naar boeken en deze te kopen in de iBooks Store.
- **De app Berichten op het apparaat**: Met **Blokkeren** voorkomt u dat gebruikers de app Berichten gebruiken voor iMessage. Als het apparaat tekstberichten ondersteunt, kan de gebruiker nog steeds tekstberichten verzenden en ontvangen met behulp van sms. Met **Niet geconfigureerd** (standaard) staat u toe dat met de Berichten-app berichten via internet worden verzonden en gelezen.
- **Podcasts**: Selecteer **Blokkeren** om toegang tot de app Podcasts op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat het gebruik van de app Podcasts toe.
- **De service Music**: Met **Blokkeren** keert u terug naar de klassieke modus van de app Muziek en wordt de Muziek-service uitgeschakeld. **Niet geconfigureerd** (standaard): staat het gebruik van de app Apple Music toe.
- **iTunes Radio-service**: Selecteer **Blokkeren** om toegang tot de app iTunes Radio op het apparaat te blokkeren. **Niet geconfigureerd** (standaard): staat het gebruik van de app iTunes Radio toe.
- **iTunes Store**: Met **Niet geconfigureerd** (standaard) staat u iTunes toe op de apparaten. Met **Blokkeren** voorkomt u dat gebruikers iTunes kunnen gebruiken op het apparaat. 

  Deze functie is van toepassing op:  
  - iOS 4.0 en hoger

- **Zoek mijn iPhone**: Met **Niet geconfigureerd** (standaard) maakt u het mogelijk om deze 'Zoek mijn'-appfunctie te gebruiken om de globale locatie van het apparaat op te halen. Met **Blokkeren** voorkomt u het gebruik van deze functie in de Zoek mijn-app. 

  Deze functie is van toepassing op:  
  - iOS 13.0 en iPadOS 13.0 en hoger

- **Zoek mijn vrienden**: Met **Niet geconfigureerd** (standaard) staat u toe dat deze 'Zoek mijn'-appfunctie wordt gebruikt om familie en vrienden te zoeken via een Apple-apparaat of via iCloud.com. Met **Blokkeren** voorkomt u het gebruik van deze functie in de Zoek mijn-app.

  Deze functie is van toepassing op:  
  - iOS 13.0 en iPadOS 13.0 en hoger

- **Wijzigingen in de instellingen van de app Zoek mijn vrienden**: Met **Blokkeren** voorkomt u wijzigingen in de instellingen van de app Zoek vrienden. **Niet geconfigureerd** (standaard): staat de gebruiker toe de instellingen van de app Zoek vrienden te wijzigen.

- **Spotlight-zoekacties voor de weergave van resultaten op internet**: Met **Blokkeren** zorgt u ervoor dat Spotlight geen resultaten meer retourneert na een zoekopdracht op internet. **Niet geconfigureerd** (standaard): staat Zoeken met Spotlight toe om verbinding te maken met internet voor zoekresultaten.

- **Het verwijderen van systeem-apps van apparaat blokkeren**: Selecteer **Blokkeren** om te voorkomen dat systeem-apps van het apparaat worden verwijderd. **Niet geconfigureerd** (standaard): staat gebruikers toe om systeemapps te verwijderen.

- **Safari**: Selecteer **Blokkeren** om te voorkomen dat gebruikers de Safari-browser op het apparaat kunnen gebruiken. **Niet geconfigureerd** (standaard): staat gebruikers toe de Safari-browser te gebruiken.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

- **Automatisch invullen in Safari**: Selecteer **Blokkeren** om de functie Automatisch invullen in Safari op het apparaat uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe de instellingen voor automatisch doorvoeren te wijzigen in de webbrowser.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

## <a name="restricted-apps"></a>Beperkte apps

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Lijst met typen beperkte apps**: Hiermee maakt u een lijst met apps die gebruikers niet mogen installeren of gebruiken. Uw opties zijn:

  - **Niet geconfigureerd** (standaard): Er zijn geen beperkingen vanuit Intune. Gebruikers hebben toegang tot apps die u toewijst en tot ingebouwde apps.
  - **Niet-toegestane apps**: Apps die niet worden beheerd in Intune waarvan u niet wilt dat deze op het apparaat worden geïnstalleerd. Gebruikers kunnen geen verboden apps installeren. Maar als een gebruiker een app uit deze lijst installeert, wordt deze in Intune gerapporteerd.
  - **Goedgekeurde apps**: Apps die gebruikers mogen installeren. Gebruikers mogen geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan. Er wordt niet voorkomen dat gebruikers een app installeren die niet in de goedgekeurde lijst wordt vermeld. Maar als dat wel het geval is, wordt dit in Intune gerapporteerd.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- De App Store-URL van de gewenste iTunes-app **toevoegen**. Voer bijvoorbeeld `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` of `https://apps.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

- **Importeer** een CSV-bestand met details van de app, waaronder de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. Of een bestaande lijst **exporteren** die de beperkte apps bevat in dezelfde indeling.

> [!IMPORTANT]
> Apparaatprofielen die instellingen voor beperkte apps gebruiken, moeten worden toegewezen aan groepen gebruikers.

## <a name="show-or-hide-apps"></a>Apps weergeven of verbergen

Is van toepassing op apparaten met iOS 9.3 of hoger.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Lijst met typen apps**: Hiermee maakt u een lijst met apps die moeten worden weergegeven of verborgen. U kunt ingebouwde apps en Line-Of-Business-apps weergeven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094). Uw opties zijn:

  - **Verborgen apps**: Voer een lijst met apps in die verborgen zijn voor gebruikers. Gebruikers kunnen deze apps niet weergeven of openen.
  
    Apple voorkomt dat sommige systeemeigen apps worden verborgen. U kunt bijvoorbeeld niet de apps **Instellingen** en **Wallet** verbergen op het apparaat. [Ingebouwde Apple-apps verwijderen](https://support.apple.com/HT208094) toont de apps die kunnen worden verborgen.
  
  - **Zichtbare apps**: Voer een lijst met apps in die gebruikers kunnen weergeven en starten. Andere apps kunnen niet worden weergegeven of gestart.

- **App-URL**: Voer de Store-URL in voor de app die u wilt weergeven of verbergen. Bijvoorbeeld:

  - Voer `https://itunes.apple.com/us/app/work-folders/id950878067?mt=8` of `https://apps.apple.com/us/app/work-folders/id950878067?mt=8` in om de app Microsoft Werkmappen toe te voegen. 

  - Voer `https://itunes.apple.com/de/app/microsoft-word/id586447913` of `https://apps.apple.com/de/app/microsoft-word/id586447913` in om de Microsoft Word-app toe te voegen.

  Als u de URL van een app wilt vinden, opent u de iTunes App Store en gaat u naar de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop` of `Microsoft Word`. Selecteer de app en kopieer de URL.

  U kunt ook iTunes gebruiken om de app te zoeken en vervolgens de taak **Koppeling kopiëren** gebruiken om de URL van de app te krijgen.

- **App-bundel-id**: Voer de [App-bundel-id](bundle-ids-built-in-ios-apps.md) van de gewenste app in. U kunt ingebouwde apps en Line-Of-Business-apps weergeven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094).
- **App-naam**: Voer de naam van de gewenste app in. U kunt ingebouwde apps en Line-Of-Business-apps weergeven of verbergen. De website van Apple bevat een lijst met [ingebouwde Apple-apps](https://support.apple.com/HT208094).
- **Uitgever**: Voer de uitgever van de gewenste app in.

Ga op een van de volgende manieren te werk om apps toe te voegen:

- **Toevoegen**: Selecteer deze optie om een lijst met uw apps te maken.
- **Importeer** een CSV-bestand met details van de app, waaronder de URL. Gebruik de notatie `<app url>, <app name>, <app publisher>`. U kunt ook **Exporteren** om een lijst in dezelfde indeling te maken met de beperkte apps die u hebt toegevoegd.

## <a name="wireless"></a>Draadloos

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

Opmerking vereist voor dataroaming (tip of belangrijke opmerking om verwarring bij klanten te voorkomen): Deze instelling wordt niet weergegeven in het beheerprofiel van het doelapparaat. Dat komt doordat deze instelling wordt behandeld als een actie voor een extern apparaat. Elke keer dat de status van gegevensroaming op het apparaat wordt gewijzigd, wordt deze weer geblokkeerd door de Intune-service. Hoewel de optie zich niet in het beheerprofiel bevindt, werkt het als er een succesvolle uitvoering wordt weergegeven in de rapportage in de beheerconsole. 
- **Gegevensroaming**: Selecteer **Blokkeren** om dataroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd** (standaard): staat dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.

  > [!IMPORTANT]
  > Deze instelling wordt behandeld als een actie op een extern apparaat. Deze instelling wordt dus niet weergegeven in het beheerprofiel op het apparaat. Steeds wanneer de status van de gegevensroaming op het apparaat wordt gewijzigd, wordt **Gegevensroaming** geblokkeerd door de Intune-service. Als in een Intune-rapport de geslaagde uitvoering wordt weergegeven, weet u zeker dat het werkt, ook al wordt de instelling niet weergegeven in het beheerprofiel op het apparaat.

- **Op de achtergrond ophalen tijdens roaming**: Met **Blokkeren** voorkomt u dat gegevens tijdens roaming op de achtergrond kunnen worden opgehaald via het mobiele netwerk. **Niet geconfigureerd** (standaard): staat het apparaat toe om gegevens zoals e-mail op te halen tijdens roaming op een mobiel netwerk.
- **Voicedialing**: Selecteer **Blokkeren** om te voorkomen dat gebruikers de functie Voicedialing op het apparaat kunnen gebruiken. **Niet geconfigureerd** (standaard): hiermee wordt Nummer inspreken toegestaan op het apparaat.
- **Gespreksroaming**: Selecteer **Blokkeren** om gespreksroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd** (standaard): staat spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Persoonlijke hotspot**: Met **Blokkeren** schakelt u de persoonlijke hotspot op apparaten van de gebruikers uit bij elke apparaatsynchronisatie. Mogelijk is deze instelling niet compatibel met bepaalde providers. Met **Niet geconfigureerd** (standaard) blijft de configuratie van de persoonlijke hotspot behouden als de standaardwaarde die is ingesteld door de gebruiker.

  > [!IMPORTANT]
  > Deze instelling wordt behandeld als een actie op een extern apparaat. Deze instelling wordt dus niet weergegeven in het beheerprofiel op het apparaat. Steeds wanneer de status van de persoonlijke hotspot op het apparaat wordt gewijzigd, wordt **Persoonlijke hotspot** geblokkeerd door de Intune-service. Als in een Intune-rapport de geslaagde uitvoering wordt weergegeven, weet u zeker dat het werkt, ook al wordt de instelling niet weergegeven in het beheerprofiel op het apparaat.

- **Regels voor mobiel gebruik (alleen beheerde apps)** : Definieer de gegevenstypen die beheerde apps kunnen gebruiken die zijn verbonden met een mobiel netwerk. Uw opties zijn:
  - **Gebruik van mobiel dataverkeer blokkeren**: U kunt het gebruik van mobiel dataverkeer blokkeren voor **Alle beheerde apps** of u kunt **specifieke apps kiezen**.
  - **Gebruik van mobiel dataverkeer tijdens roaming blokkeren**: U kunt het gebruik van mobiel dataverkeer tijdens roaming blokkeren voor **Alle beheerde apps** of u kunt **specifieke apps** kiezen.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Wijzigingen in de instellingen voor het gebruik van mobiel gegevensverkeer voor apps**: Selecteer **Blokkeren** om te voorkomen dat er wijzigingen kunnen worden aangebracht in de instellingen voor het gebruik van mobiel dataverkeer voor apps. **Niet geconfigureerd** (standaard): staat de gebruiker toe om te bepalen welke apps mobiel dataverkeer mogen gebruiken.
- **Wijzigingen in de instellingen voor mobiel gegevensverkeer**: Met **Blokkeren** voorkomt u dat gebruikers instellingen voor mobiel gegevensverkeer wijzigen. Met **Niet geconfigureerd** (standaard) kunnen gebruikers wijzigingen aanbrengen.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Aanpassing van Persoonlijke hotspot door gebruiker**: Als u deze optie instelt op **Blokkeren**, kan de gebruiker de instelling voor persoonlijke hotspot niet wijzigen. Met **Niet geconfigureerd** (standaard) stelt u eindgebruikers in staat om hun persoonlijke hotspot in of uit te schakelen.

  Als u deze instelling blokkeert en de instelling voor **Persoonlijke hotspot** blokkeert, wordt de persoonlijke hotspot uitgeschakeld.

  Deze functie is van toepassing op:  
  - iOS 12.2 en hoger

- **Toevoegen aan Wi-Fi-netwerken die alleen configuratieprofielen gebruiken**: Met **Vereisen** dwingt u af dat het apparaat alleen Wi-Fi-netwerken gebruikt die zijn ingesteld via Intune-configuratieprofielen. **Niet geconfigureerd** (standaard): staat het apparaat toe andere Wi-Fi-netwerken te gebruiken.

  Als u deze optie instelt op **Vereist**, moet u ervoor zorgen dat het apparaat een Wi-Fi-profiel heeft. Als u geen Wi-Fi-profiel toewijst, kan deze instelling ertoe leiden dat het apparaat geen verbinding kan maken met internet. Met andere woorden: als dit profiel voor apparaatbeperkingen vóór een Wi-Fi-profiel is toegewezen, kan het apparaat mogelijk geen verbinding maken met internet.
  
  Als er geen verbinding kan worden gemaakt, moet u de registratie van het apparaat ongedaan maken en het apparaat opnieuw inschrijven met een Wi-Fi-profiel. Stel deze instelling vervolgens in op **Vereist** in een profiel voor apparaatbeperkingen en wijs het profiel toe aan het apparaat.

- **Wi-Fi altijd ingeschakeld**: Als de instelling is ingesteld op **Vereist**, blijft Wi-Fi ingeschakeld in de app Instellingen. De optie kan niet worden uitgeschakeld in Instellingen of in het beheercentrum, ook niet als het apparaat zich in de vliegtuigmodus bevindt. Met **Niet geconfigureerd** (standaard) staat u de gebruiker toe om Wi-Fi in of uit te schakelen.

  Als u deze instelling configureert, wordt niet voorkomen dat gebruikers een Wi-Fi-netwerk selecteren.

  Deze functie is van toepassing op:  
  - iOS en iPadOS 13.0 en hoger

## <a name="connected-devices"></a>Verbonden apparaten

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Draagdetectie voor een gekoppelde Apple Watch**: Als u **Vereisen** selecteert, moet de gekoppelde Apple Watch de functie Draagdetectie gebruiken. Wanneer dit is vereist, worden op de Apple Watch geen meldingen weergegeven wanneer deze niet wordt gedragen. 

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Wachtwoord voor koppelen voor uitgaande AirPlay-aanvragen vereisen**: Met **Vereisen** stelt u in dat een wachtwoord voor koppelen is vereist wanneer AirPlay wordt gebruikt om inhoud te streamen naar andere Apple-apparaten. **Niet geconfigureerd** (standaard): staat de gebruiker toe inhoud te streamen met AirPlay zonder een wachtwoord in te voeren.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **AirDrop**: Selecteer **Blokkeren** om het gebruik van AirDrop op het apparaat te voorkomen. **Niet geconfigureerd** (standaard): staat het gebruik van de functie AirDrop toe voor het uitwisselen van inhoud met apparaten in de omgeving.
- **Koppelen met Apple Watch**: Selecteer **Blokkeren** om koppeling met een Apple Watch te voorkomen. **Niet geconfigureerd** (standaard): staat toe dat het apparaat wordt gekoppeld aan een Apple Watch.
- **Aanpassing van Bluetooth**: Selecteer **Blokkeren** om ervoor te zorgen dat de eindgebruiker geen Bluetooth-instellingen meer kan wijzigen op het apparaat. **Niet geconfigureerd** (standaard): staat de gebruiker toe om deze instellingen te wijzigen.
- **Koppelen met een host om te bepalen met welke apparaten een iOS-apparaat kan worden gekoppeld**: Met **Niet geconfigureerd** (standaard) staat u het koppelen met een host toe, waarmee de beheerder kan bepalen aan welke apparaten een iOS-apparaat kan worden gekoppeld. **Blokkeren**: voorkomt het koppelen met een host.
- **AirPrint blokkeren**: Selecteer **Blokkeren** om te voorkomen dat de functie AirPrint wordt gebruikt op het apparaat. **Niet geconfigureerd** (standaard): staat de gebruiker toe AirPrint te gebruiken.
  - **Opslag van AirPrint-referenties in de Sleutelhanger blokkeren**: Met **Blokkeren** voorkomt u het gebruik van de Sleutelhanger om de gebruikersnaam en het wachtwoord op te slaan op het apparaat. **Niet geconfigureerd** (standaard): staat toe dat de gebruikersnaam en het wachtwoord van AirPrint worden opgeslagen in de app Sleutelhanger.
  - **Een vertrouwd TLS-certificaat voor AirPrint vereisen**: Met **Vereisen** dwingt u af dat op het apparaat vertrouwde certificaten worden gebruikt voor TLS-afdrukcommunicatie.
  - **iBeacon-detectie van AirPrint-printers blokkeren**: Met **Blokkeren** voorkomt u phishing met schadelijke AirPrint Bluetooth-bakens voor netwerkverkeer. **Niet geconfigureerd** (standaard): staat het adverteren van AirPrint-printers op het apparaat toe.
- **Het instellen van nieuwe apparaten in de buurt blokkeren**: Met **Blokkeren** wordt de vraag om nieuwe apparaten in de buurt in te stellen uitgeschakeld. Met **Niet geconfigureerd** (standaard) wordt gebruikers gevraagd verbinding te maken met andere Apple-apparaten in de buurt.

  Deze functie is van toepassing op:  
  - iOS 11.0 en hoger

- **Toegang tot bestanden op een USB-station**: Apparaten kunnen verbinding maken met een USB-schijf en bestanden die hierop staan openen. Met **Uitschakelen** voorkomt u dat het apparaat toegang heeft tot het USB-schijf in de Bestanden-app als er een USB-verbinding met het apparaat is gemaakt. Als u deze functie uitschakelt, kunnen eindgebruikers ook geen bestanden overdragen naar een USB-schijf die is verbonden met een iPad. Met **Niet geconfigureerd** (standaard) staat u toegang tot een USB-schijf in de app Bestanden toe.

  Deze functie is van toepassing op:  
  - iOS en iPadOS 13.0 en hoger

## <a name="keyboard-and-dictionary"></a>Toetsenbord en woordenlijst

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Definities van woorden opzoeken**: Met **Blokkeren** voorkomt u dat de gebruiker een woord markeert en vervolgens de definitie ervan opzoekt op het apparaat. **Niet geconfigureerd** (standaard): geeft toegang tot de functie Opzoeken van definities van woorden.
- **Tekstvoorspelling**: Met **Niet geconfigureerd** (standaard) staat u het gebruik van tekstvoorspelling toe voor suggesties voor woorden die de gebruiker mogelijk wil invoeren. Met **Blokkeren** wordt deze functie geblokkeerd.
- **Automatische correctie**: Met **Niet geconfigureerd** (standaard) staat u automatische correctie van verkeerd gespelde woorden toe op het apparaat. **Blokkeren**: blokkeert het gebruik van Autocorrectie.
- **Spellingcontrole**: Met **Niet geconfigureerd** (standaard) kan de gebruiker spellingcontrole op het apparaat gebruiken. **Blokkeren**: staat de spellingcontrole toe.
- **Sneltoetsen**: Met **Niet geconfigureerd** (standaard) staat u het gebruik van sneltoetsen toe op het apparaat. **Blokkeren**: zorgt ervoor dat de gebruiker geen sneltoetsen meer kan gebruiken.
- **Dicteren**: Met **Blokkeren** zorgt u ervoor dat de gebruiker geen spraak meer kan gebruiken om tekst in te voeren. **Niet geconfigureerd** (standaard): staat de gebruiker toe invoer van Dicteren te gebruiken.
- **QuickPath**: Met **Niet geconfigureerd** (standaard) staat u gebruikers toe om QuickPath te gebruiken, waarmee doorlopende invoer kan worden gebruikt op het toetsenbord van het apparaat. Gebruikers kunnen typen door over de toetsen te vegen om woorden te maken. Met **Blokkeren** voorkomt u dat gebruikers QuickPath kunnen gebruiken. 

  Deze functie is van toepassing op:  
  - iOS 13.0 en iPadOS 13.0 en hoger

## <a name="cloud-and-storage"></a>Cloud en opslag

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Versleutelde back-up**: Selecteer **Vereisen** om ervoor te zorgen dat back-ups van het apparaat moeten worden versleuteld.
- **Beheerde apps synchroniseren met de cloud**: Met **Niet geconfigureerd** (standaard) staat u toe dat in door Intune beheerde apps gegevens kunnen worden gesynchroniseerd naar het iCloud-account van de gebruiker. **Blokkeren**: voorkomt deze gegevenssynchronisatie naar iCloud.
- **Back-ups van Enterprise Book blokkeren**: Selecteer **Blokkeren** om te voorkomen dat gebruikers back-ups maken van Enterprise Book-boeken. **Niet geconfigureerd** (standaard): staat gebruikers toe om back-ups te maken van deze boeken.
- **Synchronisatie van metagegevens van Enterprise Book blokkeren (notities en markeringen)** : Met **Blokkeren** voorkomt u dat notities en markeringen in Enterprise Book-boeken worden gesynchroniseerd. Met **Niet geconfigureerd** (standaard) staat u synchronisatie toe.

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Photo Stream synchroniseren met iCloud**: Met **Niet geconfigureerd** (standaard) stelt u gebruikers in staat **Mijn fotostream** in te schakelen op hun apparaat om te synchroniseren met iCloud, en foto's weer te geven op alle apparaten van de gebruikers. **Blokkeren**: voorkomt dat met Photo Stream foto’s worden gesynchroniseerd met iCloud. Als u deze functie blokkeert, kan dit leiden tot gegevensverlies. 
- **iCloud-fotobibliotheek**: Selecteer **Blokkeren** om het gebruik van de iCloud-fotobibliotheek voor het opslaan van foto's en video's in de cloud uit te schakelen. Foto's die niet volledig naar het apparaat zijn gedownload vanaf de iCloud-fotobibliotheek, worden van het apparaat verwijderd. **Niet geconfigureerd** (standaard): staat het gebruik van de iCloud-fotobibliotheek toe.
- **Gedeelde fotostream**: Selecteer **Blokkeren** om **iCloud-fotodeling** uit te schakelen op het apparaat. **Niet geconfigureerd** (standaard): staat streaming van gedeelde foto’s toe.
- **Handoff**: Met **Niet geconfigureerd** (standaard) staat u gebruikers toe om op een iOS-apparaat te werken en vervolgens hun werk voort te zetten op een ander iOS- of macOS-apparaat. **Blokkeren**: voorkomt deze handoff.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Back-up naar iCloud**: Met **Niet geconfigureerd** (standaard) staat u de gebruiker toe een back-up van het apparaat op te slaan in iCloud. **Blokkeren**: zorgt ervoor dat de gebruiker geen back-ups van het apparaat meer kan opslaan in iCloud.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

- **iCloud-documentsynchronisatie blokkeren**: Met **Niet geconfigureerd** (standaard) staat u het synchroniseren van documenten en sleutelwaarden met uw iCloud-opslagruimte toe. **Blokkeren**: voorkomt dat documenten en gegevens worden gesynchroniseerd met iCloud.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

- **Synchronisatie van iCloud-sleutelhanger blokkeren**: Selecteer **Blokkeren** om het synchroniseren van referenties die zijn opgeslagen in de Sleutelhanger, naar iCloud uit te schakelen. **Niet geconfigureerd** (standaard): staat gebruikers toe deze referenties te synchroniseren.

  Vanaf iOS 13.0 is het voor deze instelling vereist dat apparaten onder supervisie staan.

## <a name="autonomous-single-app-mode"></a>Autonome modus voor één app

Gebruik deze instellingen om iOS-/iPadOS-apparaten te configureren om specifieke apps in de autonome modus voor één app uit te voeren. Wanneer deze modus is geconfigureerd en de gebruiker een van de geconfigureerde apps start, wordt het apparaat vergrendeld voor deze app. Schakelen tussen apps/taken is uitgeschakeld totdat de gebruiker de toegestane app verlaat.

Voeg bijvoorbeeld in een school- of universiteitsomgeving een app toe waarmee gebruikers een test kunnen uitvoeren op het apparaat. Of vergrendel het apparaat in de Bedrijfsportal-app totdat de eindgebruiker zich verifieert. Wanneer de acties van de app zijn voltooid door de gebruiker, of wanneer u het beleid verwijdert, keert het apparaat terug naar de normale staat.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **App-naam**: Voer de naam in van de gewenste app.
- **App-bundel-id**: Voer de [bundel-id](bundle-ids-built-in-ios-apps.md) in van de gewenste app.
- **Toevoegen**: Selecteer deze optie om een lijst met uw apps te maken.

U kunt ook een CSV-bestand met de lijst met app-namen en de bijbehorende bundel-id’s **importeren**. Of **Exporteer** een bestaande lijst die de apps bevat.

## <a name="kiosk"></a>Kiosk

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **App uitvoeren in kioskmodus**: Selecteer het type apps dat u wilt uitvoeren in de kioskmodus. Uw opties zijn:
  - **Niet geconfigureerd** (standaard): De kioskinstellingen worden niet toegepast. Het apparaat wordt niet uitgevoerd in de kioskmodus.
  - **Store-app**: Voer de URL in voor een app in de iTunes App Store.
  - **Beheerde app**: Selecteer een app die u hebt toegevoegd aan Intune.
  - **Ingebouwde app**: Voer de [bundel-id](bundle-ids-built-in-ios-apps.md) in van de ingebouwde app.

- **Ondersteunende aanraking**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Ondersteunende aanraking op het apparaat te vereisen. Deze functie helpt gebruikers bij schermbewegingen die mogelijk moeilijk zijn voor hen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Keer kleuren om**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Keer kleuren om in te stellen, zodat gebruikers met een beperkt gezichtsvermogen de display kunnen wijzigen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Mono-audio**: Selecteer **Vereisen** om de toegankelijkheidsinstelling Mono-audio op het apparaat te vereisen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Spraakbeheer**: Met **Vereisen** maakt u spraakbesturing op het apparaat mogelijk en stelt u gebruikers in staat om het besturingssysteem volledig te bedienen met behulp van Siri-opdrachten. Met **Niet geconfigureerd** schakelt u de spraakbesturing uit op het apparaat.

  Deze instelling is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger
  
  > [!TIP]
  > Als u Line-Of-Business-apps beschikbaar hebt voor uw organisatie en **Spraakbesturing** niet gereed is op dag 0 als iOS 13.0 wordt uitgebracht, wordt u aangeraden deze instelling te laten staan op **Niet geconfigureerd**.

- **VoiceOver**: Selecteer **Vereisen** om de toegankelijkheidsinstelling VoiceOver te vereisen op het apparaat om tekst op het scherm hardop voor te lezen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Zoomen**: Selecteer **Vereisen**, zodat gebruikers met behulp van aanraken het scherm kunnen inzoomen. **Niet geconfigureerd**: deze functie wordt niet uitgevoerd of ingeschakeld in de kioskmodus.
- **Automatisch vergrendelen**: Met **Blokkeren** voorkomt u dat het apparaat automatisch wordt vergrendeld. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Schakelaar voor belsignaal**: Met **Blokkeren** wordt de schakelaar voor belsignaal (dempen) op het apparaat uitgeschakeld. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Scherm draaien**: Met **Blokkeren** blijft de schermstand ongewijzigd wanneer de gebruiker het apparaat draait. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Schermsluimerknop**: Kies **Blokkeren** om de knop voor slaapstand/ontwaken van het scherm op het apparaat uit te schakelen. Met **Niet geconfigureerd** wordt deze functie toegestaan.
- **Aanraken**: Met **Blokkeren** wordt het aanraakscherm uitgeschakeld op het apparaat. **Niet geconfigureerd**: staat de gebruiker toe het aanraakscherm te gebruiken.
- **Volumeknoppen**: Met **Blokkeren** voorkomt u dat de volumeknoppen op het apparaat worden gebruikt. Met **Niet geconfigureerd** staat u gebruik van de volumeknoppen toe.
- **Besturingselement voor ondersteunende aanraking**: Selecteer **Toestaan**, zodat gebruikers de functie Ondersteunende aanraking kunnen gebruiken. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Besturingselement voor kleuren omkeren**: Met **Toestaan** staat u aanpassingen in de functie Keer kleuren om toe, zodat gebruikers deze functie kunnen aanpassen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Geselecteerde tekst uitspreken**: Selecteer **Toestaan** om de toegankelijkheidsinstellingen Selectie uitspreken op het apparaat toe te staan. Met deze functie wordt tekst die de gebruiker selecteert, hardop gelezen. **Niet geconfigureerd**: zorgt ervoor dat deze functie is uitgeschakeld.
- **Wijziging van spraakbesturing**: Met **Toestaan** stelt u gebruikers in staat om spraakbesturing te regelen op hun apparaten. Met **Niet geconfigureerd** voorkomt u dat gebruikers de status van spraakbesturing op hun apparaten kunnen wijzigen.

  Deze instelling is van toepassing op:  
  - iOS 13.0 en hoger
  - iPadOS 13.0 en hoger

- **Besturingselement voor VoiceOver**: Selecteer **Toestaan**, zodat gebruikers de functie VoiceOver kunnen bijwerken, bijvoorbeeld hoe snel schermtekst hardop wordt gelezen. **Niet geconfigureerd**: voorkomt wijzigingen in Voice-over.
- **Besturingselement voor zoomen**: Selecteer **Toestaan**, zodat gebruikers de zoominstelling kunnen aanpassen. **Niet geconfigureerd**: voorkomt wijzigingen in Inzoomen.

> [!NOTE]
> Voordat u een iOS-apparaat voor de kioskmodus kunt configureren, moet u het hulpprogramma Apple Configurator of het Device Enrollment Program van Apple gebruiken om het apparaat in de supervisiemodus te plaatsen. Raadpleeg de handleiding van Apple voor het gebruik van het hulpprogramma Apple Configurator.
> Als de iOS-app die u invoert, wordt geïnstalleerd nadat u het profiel hebt toegewezen, wordt de kioskmodus van het apparaat pas geactiveerd nadat het opnieuw is opgestart.

## <a name="domains"></a>Domains

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Niet-gemarkeerde e-maildomeinen** > **URL van e-maildomein**: Voeg een of meer URL's toe aan de lijst. Wanneer eindgebruikers een e-mail ontvangen die afkomstig is van een ander domein dan de domeinen die u invoert, wordt de e-mail in de iOS Mail-app gemarkeerd als niet-vertrouwd.

- **Beheerde webdomeinen** > **Webdomein-URL**: Voeg een of meer URL's toe aan de lijst. Wanneer documenten worden gedownload uit de domeinen die u invoert, worden ze beschouwd als beheerd. Deze instelling geldt alleen voor documenten die zijn gedownload met Safari.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Domeinen voor automatisch invullen van Safari-wachtwoorden** > **Domein-URL**: Voeg een of meer URL's toe aan de lijst. Gebruikers kunnen in deze lijst alleen webwachtwoorden van URL's opslaan. Deze instelling geldt alleen voor Safari en voor apparaten die onder supervisie staan. Als u geen URL's invoert, kunnen wachtwoorden van alle websites worden opgeslagen.

  Deze instelling is van toepassing op:  
  - iOS 9.3 en hoger

## <a name="settings-that-require-supervised-mode"></a>Instellingen waarvoor de supervisiemodus is vereist

De supervisiemodus voor iOS kan alleen worden ingeschakeld tijdens de initiële installatie van het apparaat via het Device Enrollment Program van Apple of met behulp van Apple Configurator. Zodra de supervisiemodus is ingeschakeld, kunt u in Intune een apparaat configureren met de volgende functionaliteit:

- App-vergrendeling (modus voor één app) 
- Algemene HTTP-proxy 
- Activeringsslot uitschakelen 
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
