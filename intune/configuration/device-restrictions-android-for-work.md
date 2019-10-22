---
title: Apparaatinstellingen voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Op apparaten met Android Enterprise of Android for Work kunt u beperkingen op het apparaat instellen, zoals voor kopiëren en plakken, het weergeven van meldingen, app-machtigingen, het delen van gegevens, de wachtwoordlengte, mislukte aanmeldpogingen, het gebruik van vingerafdrukken om te ontgrendelen, het opnieuw gebruiken van wachtwoorden en het delen van zakelijke contactpersonen via Bluetooth. Configureer apparaten als een toegewezen apparaatkiosk voor het uitvoeren van een of meer apps.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: d1d83a77d8823a05accaf1c88b57f6e380636469
ms.sourcegitcommit: 0be25b59c8e386f972a855712fc6ec3deccede86
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/18/2019
ms.locfileid: "72585388"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Met Android Enterprise-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op Android Enterprise-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, apps uit te voeren op tiegewezen apps, beveiliging te beheren en nog veel meer.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Alleen eigenaar van het apparaat

### <a name="general-settings"></a>Algemene instellingen

- **Schermafbeeldingen**: kies **Blokkeren** om te voorkomen dat schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. U voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben. **Niet geconfigureerd**: stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding.
- **Camera**: kies **Blokkeren** om toegang tot de camera op het apparaat te blokkeren. **Niet vereist**: staat toegang tot de camera van het apparaat toe.
- **Standaardmachtigingsbeleid**: met deze instelling bepaalt u het standaardmachtigingsbeleid voor aanvragen betreffende runtime-machtigingen. De mogelijke waarden zijn:
  - **Standaardwaarde apparaat**: gebruik de standaardinstelling van het apparaat.
  - **Prompt**: de gebruiker wordt gevraagd de machtiging goed te keuren.
  - **Automatisch verlenen**: machtigingen worden automatisch verleend.
  - **Automatisch weigeren**: machtigingen worden automatisch geweigerd.
- **Wijzigingen in datum en tijd**: kies **Blokkeren** om te voorkomen dat gebruikers handmatig de datum en tijd instellen. **Niet geconfigureerd**: staat gebruikers toe om de datum en tijd in te stellen op het apparaat.
- **Volumewijzigingen**: kies **Blokkeren** om te voorkomen dat gebruikers het volume van het apparaat wijzigen. **Niet geconfigureerd**: staat gebruik van de volume-instellingen toe op het apparaat.
- **Fabrieksinstellingen terugzetten**: kies **Blokkeren** om te voorkomen dat gebruikers de optie voor het terugzetten van de fabrieksinstellingen van het apparaat gebruiken. **Niet geconfigureerd**: staat gebruikers toe om deze instelling te gebruiken op het apparaat.
- **Opstarten in veilige modus**: kies **Blokkeren** om te voorkomen dat gebruikers het apparaat opnieuw opstarten in de veilige modus. **Niet geconfigureerd**: staat gebruikers toe om het apparaat opnieuw op te starten in de veilige modus.
- **Statusbalk**: kies **Blokkeren** om toegang tot de statusbalk te voorkomen, met inbegrip van meldingen en snelle instellingen. **Niet geconfigureerd**: gebruikers hebben toegang tot de statusbalk.
- **Roaming gegevensservices**: kies **Blokkeren** om dataroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd**: staat dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Wi-Fi-instellingswijzigingen**: kies **Blokkeren** om te voorkomen dat gebruikers Wi-Fi-instellingen wijzigen die zijn gemaakt door de eigenaar van het apparaat. Gebruikers kunnen hun eigen Wi-Fi-configuraties maken. **Niet geconfigureerd**: staat gebruikers toe om de Wi-Fi-instellingen op het apparaat te wijzigen.
- **Wi-Fi-toegangspuntconfiguratie**: kies **Blokkeren** om te voorkomen dat gebruikers Wi-Fi-configuraties maken of wijzigen. **Niet geconfigureerd**: staat gebruikers toe om de Wi-Fi-instellingen op het apparaat te wijzigen.
- **Bluetooth-configuratie**: kies **Blokkeren** om te voorkomen dat gebruikers Bluetooth configureren op het apparaat. **Niet geconfigureerd**: hiermee kan de gebruiker Bluetooth op het apparaat gebruiken.
- **Tethering en toegang tot hotspots**: kies **Blokkeren** om tethering en toegang tot draagbare hotspots te voorkomen. **Niet geconfigureerd**: tethering en toegang tot draagbare hotspots is toegestaan.
- **USB-opslag**: kies **Toestaan** voor toegang tot USB-opslag op het apparaat. **Niet geconfigureerd**: voorkomt toegang tot USB-opslag.
- **USB-bestandsoverdracht**: kies **Blokkeren** om bestandsoverdracht via USB te voorkomen. **Niet geconfigureerd**: bestandsoverdracht is toegestaan.
- **Externe media**: kies **Blokkeren** om te voorkomen dat er externe media op het apparaat worden aangesloten of hiermee verbinding wordt gemaakt. **Niet geconfigureerd**: externe media toestaan op het apparaat.
- **Gegevens beamen met NFC**: kies **Blokkeren** om te voorkomen dat met behulp van de NFC-technologie gegevens worden verzonden vanuit apps. **Niet geconfigureerd**: NFC kan worden gebruikt voor het delen van gegevens tussen apparaten.
- **Foutopsporingsfuncties**: kies **Toestaan** om gebruikers de functies voor foutopsporing te laten gebruiken op het apparaat. **Niet geconfigureerd**: voorkomt dat gebruikers de functies voor foutopsporing kunnen gebruiken op het apparaat.
- **Microfoon aanpassen**: kies **Blokkeren** om te voorkomen dat gebruikers de microfoon kunnen inschakelen of het volume van de microfoon kunnen aanpassen. **Niet geconfigureerd**: de gebruiker kan de microfoon van het apparaat gebruiken en het volume ervan aanpassen.
- **E-mailadressen resetbeveiliging fabrieksinstellingen**: kies **E-mailadressen van Google-account**. Voer de e-mailadressen in van apparaatbeheerders die het apparaat kunnen ontgrendelen nadat dit is gewist. Plaats een puntkomma tussen de e-mailadressen, zoals `admin1@gmail.com;admin2@gmail.com`. Als u geen e-mailadres invoert, kan iedereen het apparaat ontgrendelen nadat de fabrieksinstellingen zijn hersteld. Deze e-mail berichten zijn alleen van toepassing wanneer een niet-gebruikers fabrieks instelling is uitgevoerd, zoals het uitvoeren van een fabrieks instelling opnieuw instellen met het menu herstellen.
- **Netwerknooduitgang**: kies **Inschakelen** als gebruikers de functie Netwerknooduitgang mogen inschakelen. Als er geen netwerkverbinding tot stand wordt gebracht bij het opstarten van het apparaat, vraagt de functie of er tijdelijk verbinding moet worden gemaakt met een netwerk en of het apparaatbeleid moet worden vernieuwd. Wanneer het beleid is toegepast, wordt het tijdelijke netwerk vergeten en gaat het apparaat verder met opstarten. Deze functie maakt in de volgende gevallen verbinding tussen een apparaat en netwerk:
  - Er bevindt zich geen geschikt netwerk in het laatste beleid.
  - Het apparaat wordt opgestart naar een app in de modus vergrendelingstaak.
  - De gebruiker heeft geen toegang tot de apparaatinstellingen.

  **Niet geconfigureerd**: hiermee wordt voorkomen dat gebruikers de functie Netwerknooduitgang inschakelen op het apparaat.

- **Systeemupdate**: kies een optie om te bepalen hoe het apparaat omgaat met draadloze updates:
  - **Standaardwaarde apparaat**: gebruik de standaardinstelling van het apparaat.
  - **Automatisch**: updates worden automatisch geïnstalleerd zonder interactie van de gebruiker. Wanneer u dit beleid instelt, worden alle eventuele updates die nog niet zijn uitgevoerd, meteen geïnstalleerd.
  - **Uitgesteld**: updates worden gedurende 30 dagen uitgesteld. Na 30 dagen wordt de gebruiker door Android gevraagd om de update te installeren. Het is mogelijk dat apparaatfabrikanten of leveranciers het uitstellen van belangrijke beveiligingsupdates voorkomen (uitzonderen). Voor een uitzonderingsupdate wordt een systeembericht weergegeven op het apparaat.
  - **Onderhoudsperiode**: hiermee worden updates automatisch geïnstalleerd tijdens een dagelijkse onderhoudsperiode die u in Intune instelt. Er wordt gedurende 30 dagen geprobeerd om de updates te installeren. Dit kan mislukken als er te weinig ruimte of onvoldoende accuvermogen is. Na 30 dagen vraagt Android de gebruiker om te installeren. Deze periode wordt is ook gebruikt om updates voor Play-apps te installeren. Gebruik deze optie voor specifieke apparaten, zoals kiosken, omdat toegewezen apparaten mt maar één app op de voorgrond kunnen worden bijgewerkt.

- **Meldingsvensters**: als de optie **Uitschakelen** is ingesteld, worden venstermeldingen, inclusief pop-ups, inkomende aanroepen, uitgaande aanroepen, systeemwaarschuwingen en systeemfouten niet weergegeven op het apparaat. Als de optie **Niet geconfigureerd** is ingesteld, wordt de standaardinstelling van het besturingssysteem gebruikt, die mogelijk bepaalt dat meldingen worden weergegeven.
- **Hints voor eerste gebruik overslaan**: kies **Inschakelen** als u suggesties van apps wilt verbergen of overslaan voor het doorlopen van zelfstudies of voor het lezen van inleidende hints wanneer de app wordt gestart. Als de optie **Niet geconfigureerd** is ingesteld, wordt de standaardinstelling van het besturingssysteem gebruikt, die mogelijk bepaalt dat suggesties worden weergegeven wanneer de app wordt gestart.

### <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

- **Bedreigingsscan voor apps**: Met **Vereisen** (standaard) kunnen apps worden gescand door Google Play Protect voor- en nadat deze zijn geïnstalleerd. Als er een bedreiging wordt gedetecteerd, kan de gebruiker de waarschuwing krijgen dat de app moet worden verwijderd van het apparaat. **Niet geconfigureerd**: hiermee wordt Google Play Protect niet in staat gesteld of uitgevoerd om apps te scannen.

### <a name="dedicated-device-settings"></a>Toegewezen apparaatinstellingen

Gebruik deze instellingen om een kioskstijlervaring op uw toegewezen apparaten te configureren. U kunt een apparaat configureren voor het uitvoeren van één app of een aantal apps. Wanneer een apparaat op de kioskmodus is ingesteld, zijn alleen de apps beschikbaar die u expliciet hebt toegevoegd. Deze instellingen zijn van toepassing op toegewezen Android Enterprise-apparaten. Deze zijn niet van toepassing op volledig beheerde Android Enterprise-apparaten.

**Kioskmodus**: kies dit als op het apparaat één app of meerdere apps worden uitgevoerd.

- **Eén app**: gebruikers hebben slechts toegang tot één app op het apparaat. Wanneer het apparaat wordt gestart, wordt alleen de specifieke app gestart. Gebruikers kunnen geen nieuwe apps openen of de actieve app wijzigen.

  - **Beheerde app selecteren**: Selecteer de beheerde Google Play-app in de lijst.

    Als er geen apps worden vermeld, [voegt u enkele Android-apps toe](../apps/apps-add-android-for-work.md) aan het apparaat. Zorg ervoor dat u [de app toewijst](../apps/apps-deploy.md) aan de apparaatgroep die is gemaakt voor uw toegewezen apparaten.

  > [!IMPORTANT]
  > Wanneer u de kiosk modus van één app gebruikt, werken de apps voor kiezer/telefoon mogelijk niet goed. 
  
- **Meerdere apps**: gebruikers hebben toegang tot een beperkte set apps op het apparaat. Wanneer het apparaat wordt gestart, worden alleen de toegevoegde apps gestart. U kunt ook enkele webkoppelingen toevoegen die gebruikers kunnen openen. Wanneer het beleid wordt toegepast, zien gebruikers pictogrammen voor de toegestane apps op het startscherm.

  > [!IMPORTANT]
  > Voor toegewezen apparaten voor meerdere apps **moet** de [app Managed Home Screen](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) van Google Play zijn:
  >   - [Toegevoegd als een client-app](../apps/apps-add-android-for-work.md) in Intune
  >   - [Toegewezen aan de apparaatgroep](../apps/apps-deploy.md) die is gemaakt voor uw toegewezen apparaten
  >
  > De app **Managed Home Screen** hoeft niet te zijn opgenomen in het configuratieprofiel, maar moet wel worden toegevoegd als een client-app. Wanneer de app **Managed Home Screen** wordt toegevoegd als een client-app, worden andere apps die u aan het configuratieprofiel toevoegt, weergegeven als pictogrammen in de app **Managed Home Screen**.
  >
  > Wanneer u de kiosk modus van meerdere apps gebruikt, werken de apps voor kiezer/telefoon mogelijk niet goed. 

  - **Toevoegen**: Selecteer uw apps in de lijst.

    Als de app **Managed Home Screen** niet wordt vermeld, [voegt u deze toe vanuit Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Zorg ervoor dat u [de app toewijst](../apps/apps-deploy.md) aan de apparaatgroep die is gemaakt voor uw toegewezen apparaten.

    U kunt ook andere [Android-apps](../apps/apps-add-android-for-work.md) toevoegen aan het apparaat, evenals [web-apps](../apps/web-app.md) die zijn gemaakt door uw organisatie. Zorg ervoor dat u [de app toewijst](../apps/apps-deploy.md) aan de apparaatgroep die is gemaakt voor uw toegewezen apparaten.

  - **Knop voor virtuele introductie**: een knop met zachte sleutel waarmee gebruikers worden geretourneerd naar het beheerde Start scherm, zodat gebruikers tussen apps kunnen scha kelen. Uw opties zijn:

    - **Niet geconfigureerd** (standaard): er wordt geen start knop weer gegeven. Gebruikers moeten de knop terug gebruiken om tussen apps te scha kelen.
    - **Swipe omhoog**: er wordt een start knop weer gegeven wanneer een gebruiker naar het apparaat wordt geveegd.
    - **Zwevend**: toont een permanente, zwevende knop Start op het apparaat.

  - **Kioskmodus verlaten**: kies **Inschakelen** om beheerders toestemming te geven de kioskmodus tijdelijk te onderbreken om het apparaat bij te werken. Voor gebruik van deze functie moet de beheerder het volgende doen:
  
    1. Doorgaan met het selecteren van de knop Terug totdat de knop **Kiosk verlaten** wordt weergegeven. 
    2. Hiermee wordt de knop **Kiosk verlaten** geselecteerd en de pincode voor het **verlaten van de kioskmodus ingevoerd**.
    3. Wanneer u klaar bent, selecteert u de beheerde app voor het **Start scherm** . Met deze stap wordt het apparaat weer vergrendeld in de kioskmodus voor gebruik van meerdere apps.

      Als de instelling is ingesteld op **niet geconfigureerd**, kunnen beheerders de kiosk modus niet onderbreken. Als de beheerder de knop Terug blijft selecteren en vervolgens de knop **Kiosk verlaten** selecteert, verschijnt er een bericht dat er een wachtwoordcode moet worden ingevoerd.

    - **Code voor verlaten van kioskmodus**: voer een pincode van 4-6-cijfers in. De beheerder gebruikt deze pincode om de kioskmodus tijdelijk te onderbreken.

  - **URL voor aangepaste achtergrond**: voer een URL in voor het aanpassen van het achtergrondscherm op het toegewezen apparaat.

    > [!NOTE]
    > In de meeste gevallen is het aan te raden om te beginnen met installatiekopieën van ten minste de volgende grootten:
    >
    > - Telefoon: 1080 x 1920 pixels
    > - Tablet: 1920 x 1080 pixels
    >
    > Voor de beste ervaring en heldere details is het aan te raden om per apparaatinstallatiekopie assets te maken voor de schermspecificaties.
    >
    > Moderne schermen hebben een hogere pixeldichtheid met de mogelijkheid om definitie-installatiekopieën gelijkwaardig aan 2K/4K weer te geven.

  - **Wi-Fi-configuratie** **: Hiermee** wordt het besturings element Wi-Fi weer gegeven op het beheerde Start scherm en kunnen eind gebruikers het apparaat verbinden met verschillende WiFi-netwerken. Als u deze functie inschakelt, wordt ook de apparaatlocatie ingeschakeld. **Niet geconfigureerd** (standaard) geeft niet het besturings element Wi-Fi weer op het beheerde Start scherm. Hiermee voor komt u dat gebruikers verbinding kunnen maken met Wi-Fi-netwerken terwijl ze het beheerde Start scherm gebruiken.

  - **Bluetooth-configuratie**: **inschakelen** Hiermee wordt het Bluetooth-besturings element weer gegeven op het beheerde Start scherm en kunnen eind gebruikers apparaten koppelen via Bluetooth. Als u deze functie inschakelt, wordt ook de apparaatlocatie ingeschakeld. **Niet geconfigureerd** (standaard) het besturings element Bluetooth wordt niet weer gegeven op het beheerde Start scherm. Hiermee wordt voor komen dat gebruikers Bluetooth-en koppelings apparaten configureren tijdens het gebruik van het beheerde Start scherm.

  - **Zaklantaarn toegang**: **inschakelen** Hiermee wordt het besturings element zaklantaarn in het beheerde Start scherm weer gegeven en kunnen eind gebruikers de zaklantaarn in-of uitschakelen. **Niet geconfigureerd** (standaard) geeft niet het zaklantaarn-besturings element weer op het beheerde Start scherm. Hiermee wordt voor komen dat gebruikers de zaklantaarn gebruiken terwijl ze het beheerde Start scherm gebruiken.

  - **Volume regeling van media**: **inschakelen** geeft de volume regeling voor media weer op het beheerde Start scherm. Hiermee kunnen eind gebruikers het Media volume van het apparaat aanpassen met behulp van een schuif regelaar. **Niet geconfigureerd** (standaard) de volume regeling voor media op het beheerde Start scherm wordt niet weer gegeven. Hiermee wordt voor komen dat gebruikers het Media volume van het apparaat aanpassen tijdens het gebruik van het beheerde Start scherm, tenzij hun hardwareknoppen dit ondersteunen. 

  - **Scherm beveiligings modus**: **inschakelen** geeft een scherm afbeelding weer op het beheerde Start scherm wanneer het apparaat is vergrendeld of een time-out optreedt. **Niet geconfigureerd** (standaard) toont geen scherm beveiliging op het beheerde Start scherm.

    Wanneer deze functie is ingeschakeld, moet u ook het volgende configureren:

    - **Aangepaste scherm beveiliging instellen afbeelding**: Voer de URL naar een aangepaste installatie kopie in. Voer bijvoorbeeld het volgende in:

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.html`

      Als u geen URL opgeeft, wordt de standaard installatie kopie van het apparaat gebruikt, als er een standaard installatie kopie is.

    - **Het aantal seconden dat het apparaat scherm beveiliging bevat voordat het scherm wordt uitgeschakeld**: Kies hoe lang het apparaat de scherm beveiliging weergeeft. Voer een waarde tussen 0-9999999 seconden in. De standaard waarde is `0` seconden. Als u niets opgeeft of op nul (`0`) instelt, wordt de scherm beveiliging actief totdat een gebruiker met het apparaat communiceert.
    - **Aantal seconden dat het apparaat inactief is voordat scherm beveiliging wordt weer gegeven**: Kies hoe lang het apparaat inactief moet zijn voordat de scherm beveiliging wordt weer gegeven. Voer een waarde tussen 1-9999999 seconden in. De standaard waarde is `30` seconden. U moet een getal opgeven dat groter is dan nul (`0`).
    - **Media detecteren vóór start scherm beveiliging**: **inschakelen** (standaard) de scherm beveiliging wordt niet weer gegeven als audio of video wordt afgespeeld op het apparaat. **Niet geconfigureerd** toont de scherm beveiliging, zelfs als audio of video wordt afgespeeld.

### <a name="device-password-settings"></a>Instellingen voor apparaatwachtwoord

- **Vergrendelingsscherm uitschakelen**: Kies **Uitschakelen** als u wilt voorkomen dat gebruikers de Keyguard-functie voor schermvergrendeling op het apparaat gebruiken. **Niet geconfigureerd**: staat de gebruiker toe de Keyguard-functies te gebruiken.
- **Schermvergrendelingsfuncties uitschakelen**: Kies welke functies u wilt uitschakelen wanneer Keyguard is ingeschakeld op het apparaat. Wanneer bijvoorbeeld de optie **Veilige camera** is geselecteerd, wordt de functie van de camera op het apparaat is uitgeschakeld. Alle functies die niet zijn geselecteerd, zijn op het apparaat ingeschakeld.

  Deze functies zijn beschikbaar voor gebruikers wanneer het apparaat is vergrendeld. De geselecteerde functies zijn niet zichtbaar en niet toegankelijk voor gebruikers.

- **Vereist wachtwoordtype**: bepaal welk type wachtwoord wordt vereist voor het apparaat. Uw opties zijn:
  - **Standaardwaarde apparaat**
  - **Wachtwoord vereist, geen beperkingen**
  - **Zwakke biometrie**: [Sterke versus zwakke biometrie](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (hiermee wordt een Android-website geopend)
  - **Numeriek**: Het wachtwoord mag alleen uit getallen bestaan, bijvoorbeeld `123456789`. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Numeriek complex**: herhaalde of opeenvolgende cijfers, zoals '1111' of '1234', zijn niet toegestaan. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Alfabetisch**: Er zijn letters uit het alfabet vereist. Er zijn geen cijfers en symbolen vereist. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Alfanumeriek**: Dit zijn hoofdletters, kleine letters en numerieke tekens. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Alfanumeriek met symbolen**: dit zijn hoofdletters, kleine letters, numerieke tekens, leestekens en symbolen. Voer ook in:

    - **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in, tussen 4 en 16 tekens.
    - **Het vereiste aantal tekens**: voer het aantal tekens in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal kleine letters**: voer het aantal kleine letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal hoofdletters**: voer het aantal hoofdletters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal andere tekens dan letters**: voer het aantal andere tekens dan alfabetische letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal numerieke tekens**: voer het numerieke tekens (`1`, `2`, `3` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal symbolen**: voer het aantal symbolen (`&`, `#`, `%` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

- **Het aantal dagen totdat het wachtwoord verloopt**: Voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd, tussen 1 en 365. Als u bijvoorbeeld wilt dat het wachtwoord na zestig dagen moet worden gewijzigd, voert u `60` in. Wanneer het wachtwoord is verlopen, wordt gebruikers gevraagd een nieuw wachtwoord te maken.
- **Het vereiste aantal wachtwoorden voordat de gebruiker een wachtwoord opnieuw kan gebruiken**: Voer het aantal recente wachtwoorden in dat niet opnieuw mag worden gebruikt, tussen 1 en 24. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer het aantal mislukte aanmeldingen in dat is toegestaan voordat het apparaat wordt gewist, tussen 4 en 11.

### <a name="power-settings"></a>Energie-instellingen

- **Tijd tot het scherm wordt vergrendeld**: stel in hoeveel niet-actieve tijd er moet zijn voordat het apparaat wordt vergrendeld.
- **Scherm aan terwijl het apparaat is aangesloten**: kies bij welke energiebronnen het scherm aan blijft wanneer het apparaat is aangesloten.

### <a name="users-and-accounts-settings"></a>Gebruikers- en accountinstellingen

- **Nieuwe gebruikers toevoegen**: kies **Blokkeren** om te voorkomen dat gebruikers nieuwe gebruikers toevoegen. Elke gebruiker heeft een persoonlijke ruimte op het apparaat voor aangepaste beginschermen, accounts, apps en instellingen. **Niet geconfigureerd**: staat gebruikers toe om andere gebruikers toe te voegen aan het apparaat.
- **Gebruikers verwijderen**: kies **Blokkeren** om te voorkomen dat gebruikers gebruikers verwijderen. **Niet geconfigureerd**: staat gebruikers toe om andere gebruikers te verwijderen van het apparaat.
- **Accountwijzigingen**: kies **Blokkeren** om te voorkomen dat gebruikers accounts wijzigen. **Niet geconfigureerd**: staat gebruikers toe om gebruikersaccounts op het apparaat bij te werken.

  > [!NOTE]
  > Deze instelling wordt niet gehonoreerd op de apparaat-eigenaar (volledig beheerde) apparaten. Als u deze instelling configureert, wordt de instelling genegeerd en heeft dit geen invloed.

### <a name="applications"></a>Toepassingen

- **Installatie via onbekende bronnen toestaan**: Kies **Toestaan** zodat gebruikers **Onbekende bronnen** kunnen inschakelen. Met deze instelling kunnen apps van onbekende bronnen worden geïnstalleerd, met inbegrip van andere bronnen dan Google Play Store. **Niet geconfigureerd**: voorkomt dat gebruikers **Onbekende bronnen** kunnen inschakelen.
- **Toegang tot alle apps in Google Play Store toestaan**: Als deze optie is ingesteld op **Toestaan**, krijgen gebruikers toegang tot alle apps in Google Play store. Ze krijgen geen toegang tot apps die de beheerder blokkeert in[Client-apps](../apps/apps-add-android-for-work.md). **Niet geconfigureerd**: gebruikers hebben alleen toegang tot apps die de beheerder beschikbaar maakt in Google Play Store of apps die zijn vereist in [Client-apps](../apps/apps-add-android-for-work.md).
- **App wordt automatisch bijgewerkt**: kies dit wanneer updates automatisch worden geïnstalleerd. Uw opties zijn:
  - **Niet geconfigureerd**
  - **Gebruiker kiezen**
  - **Nooit**
  - **Alleen Wi-Fi**
  - **Altijd**

### <a name="connectivity"></a>Connectiviteit

- **AlwaysOn VPN**: kies **Inschakelen** om in te stellen dat een VPN-client automatisch verbinding maakt en opnieuw verbinding maakt met het VPN. AlwaysOn VPN-verbindingen blijven verbonden of maken direct verbinding wanneer gebruikers hun apparaat vergrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. 

  Kies **Niet geconfigureerd** om AlwaysOn VPN voor alle VPN-clients uit te schakelen.

  > [!IMPORTANT]
  > Implementeer slechts één AlwaysOn VPN-beleid per apparaat. Het implementeren van meerdere AlwaysOn VPN-beleidsregels op één apparaat wordt niet ondersteund.

- **VPN-client**: kies een VPN-client die ondersteuning biedt voor AlwaysOn. Uw opties zijn:
  - Cisco AnyConnect
  - F5-toegang
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Aangepast
    - **Pakket-id**: voer de pakket-id in van de app in Google Play. Als de URL voor de app in Google Play bijvoorbeeld `https://play.google.com/store/details?id=com.contosovpn.android.prod` is, is de pakket-id `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - De VPN-client die u kiest moet op het apparaat worden geïnstalleerd en moet VPN per app in werkprofielen ondersteunen. Anders treedt er een fout op. 
  > - U dient de VPN-client-app goed te keuren in de **Beheerde Google Play Store**, de app te synchroniseren naar Intune en de app te implementeren op het apparaat. Nadat u dit hebt gedaan, is de app geïnstalleerd in het werkprofiel van de gebruiker.
  > - Er zijn mogelijk bekende problemen bij het gebruik van VPN per app met F5 Access voor Android 3.0.4. Zie [Releaseopmerkingen voor F5 Access voor Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) voor meer informatie.

- **Vergrendelingsmodus**: kies **Inschakelen** als u wilt afdwingen dat al het verkeer de VPN-tunnel gebruikt. Als er geen VPN-verbinding is ingesteld, heeft het apparaat geen toegang tot het netwerk.

  Kies **Niet geconfigureerd** om toe te staan dat verkeer via de VPN-tunnel of via het mobiele netwerk gaat.

- **Aanbevolen globale proxy**: Kies **inschakelen** om een algemene proxy toe te voegen aan de apparaten. Wanneer deze functie is ingeschakeld, wordt het HTTP-en HTTPS-verkeer, inclusief enkele apps op het apparaat, gebruikt voor de proxy die u invoert. Deze proxy is alleen een aanbeveling. Het is mogelijk dat sommige apps de proxy niet gebruiken. **Niet geconfigureerd** (standaard) voegt geen aanbevolen algemene proxy toe.

  Zie [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (een Android-site openen) voor meer informatie over deze functie.

  Wanneer deze functie is ingeschakeld, voert u ook het **type** proxy in. Uw opties zijn:

  - **Direct**: Selecteer deze optie om de proxyserver gegevens hand matig in te voeren, waaronder:
    - **Host**: Geef de hostnaam of het IP-adres van de proxy server op. Voer bijvoorbeeld `proxy.contoso.com` of `127.0.0.1` in.
    - **Poortnummer**: voer het nummer van de TCP-poort in die wordt gebruikt door de proxyserver. Voer bijvoorbeeld `8080` in.
    - **Uitgesloten hosts**: Voer een lijst in met hostnamen of IP-adressen die de proxy niet gebruiken. Deze lijst kan een asterisk (`*`) Joker teken bevatten en meerdere hosts gescheiden door punt komma's (`;`) zonder spaties. Voer bijvoorbeeld `127.0.0.1;web.contoso.com;*.microsoft.com` in.

  - **Automatische proxy configuratie**: Voer de **Pac-URL** in voor een script voor automatische configuratie van de proxy. Voer bijvoorbeeld `https://proxy.contoso.com/proxy.pac` in.

    Zie voor meer informatie over PAC-bestanden het [bestand voor automatische proxy-configuratie (PAC)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (opent een niet-micro soft-site).

## <a name="work-profile-only"></a>Alleen werkprofiel

### <a name="work-profile-settings"></a>Werkprofielinstellingen

#### <a name="general"></a>Algemeen

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen**: kies **Blokkeren** om kopiëren en plakken tussen zakelijke en persoonlijke apps te voorkomen. **Niet geconfigureerd**: staat gebruikers toe om gegevens met behulp van kopiëren en plakken te delen met apps in het persoonlijke profiel. 
- **Gegevens delen tussen werkprofiel en persoonlijk profiel**: hiermee kunt u bepalen of apps in het werkprofiel gegevens mogen delen met apps in het persoonlijke profiel. Met deze instelling kunt u bijvoorbeeld deelacties binnen toepassingen bepalen, zoals de optie **Delen…** in de Chrome-browser-app. Deze instelling geldt niet voor kopiëren en plakken op het klembord. Uw opties voor delen:
  - **Apparaatstandaard**: de standaardinstelling voor het delen van gegevens van het apparaat. Deze instelling is afhankelijk van de Android-versie. Delen van het persoonlijke profiel naar het werkprofiel is standaard toegestaan. Delen van het werkprofiel naar het persoonlijke profiel is standaard geblokkeerd. Met deze instelling wordt voorkomen dat er gegevens worden gedeeld van het werkprofiel met het persoonlijke profiel. Google blokkeert niet delen van het persoonlijke profiel naar het werkprofiel op apparaten met versie 6.0 of hoger.
  - **Met de apps in het werkprofiel kunnen aanvragen voor het delen van het persoonlijke profiel worden verwerkt**: hiermee kunt u de ingebouwde Android-functie inschakelen waarmee het delen van gegevens vanuit het persoonlijke profiel naar het werkprofiel is toegestaan. Wanneer dit is ingeschakeld, kan een deelverzoek van een app in het persoonlijke profiel worden gedeeld met apps in het werkprofiel. Dit is de standaardinstelling voor Android-apparaten met een oudere versie dan 6.0.
  - **Delen over grenzen voor komen**: Hiermee wordt voor komen dat het werk en het persoonlijke profiel worden gedeeld.
  - **Geen beperkingen voor delen**: Hiermee wordt het delen van het werk profiel in beide richtingen verdeeld. Wanneer u deze instelling selecteert, kunnen apps met het werkprofiel gegevens delen met apps in het persoonlijke profiel die geen badge hebben. Met deze instelling kunnen beheerde apps in het werkprofiel gegevens delen met apps aan de onbeheerde zijde van het apparaat. Gebruik deze instelling daarom zorgvuldig.

- **Werkprofielmeldingen terwijl het apparaat is vergrendeld**: hiermee kunt u bepalen of de apps in het werkprofiel gegevens in meldingen kunnen weergeven wanneer het apparaat is vergrendeld. **Blokkeren**: de gegevens worden niet weergegeven. **Niet geconfigureerd**: de gegevens worden weergegeven.
- **Standaardapp-machtigingen**: hiermee stelt u het standaardmachtigingsbeleid in voor alle apps in het werkprofiel. Vanaf Android 6 wordt de gebruiker gevraagd bepaalde vereiste machtigingen aan apps toe te kennen wanneer de app wordt gestart. Met deze beleidsinstelling kunt u in het werkprofiel bepalen of gebruikers wordt gevraagd om machtigingen toe te kennen voor alle apps in het werkprofiel. U kunt bijvoorbeeld een app aan het werkprofiel toewijzen waarvoor toegang tot de locatie is vereist. Normaal gesproken wordt de gebruiker gevraagd of hij de app toegang tot de locatie wil geven. Gebruik dit beleid om automatisch machtigingen te verlenen zonder om bevestiging te vragen, automatisch machtigingen te weigeren zonder om bevestiging te vragen, of om de eindgebruiker te laten beslissen. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Vragen**
  - **Automatisch verlenen**
  - **Automatisch weigeren**

  U kunt ook een app-configuratiebeleid gebruiken om machtigingen voor afzonderlijke apps te verlenen (**Client-apps** > **App-configuratiebeleid**).

- **Accounts toevoegen en verwijderen**: kies **Blokkeren** om te voorkomen dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen. Als u de Gmail-app bijvoorbeeld implementeert in een Android-werkprofiel, kunt u verhinderen dat eindgebruikers accounts toevoegen aan of verwijderen uit dit werkprofiel. **Niet geconfigureerd**: hiermee wordt toegestaan dat accounts worden toegevoegd aan het werkprofiel.  

- **Contactpersonen delen via Bluetooth**: hiermee krijgt u toegang tot werkcontactpersonen op een ander apparaat, zoals een auto, dat via Bluetooth is gekoppeld. Standaard is deze instelling niet geconfigureerd en worden contactpersonen met een werkprofiel niet weergegeven. Selecteer **Inschakelen** om het delen hiervan toe te staan en contactpersonen met een werkprofiel weer te geven. Deze instelling is van toepassing op Android-apparaten met een werkprofiel met Android OS v6.0 en hoger. Door deze instelling in te schakelen, kunnen bepaalde Bluetooth-apparaten werkcontactpersonen cachen bij de eerste verbinding. Als u dit beleid uitschakelt na een eerste synchronisatie, zijn de werkcontactpersonen van een Bluetooth-apparaat niet meteen verwijderd.

- **Schermafbeeldingen**: kies **Blokkeren** om te voorkomen dat in het werkprofiel schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. U voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben. **Niet geconfigureerd**: schermafbeeldingen zijn toegestaan.

- **Beller-id zakelijk contactpersoon in persoonlijk profiel weergeven**: indien ingeschakeld (**Niet geconfigureerd**), worden de details van een beller die een zakelijke contactpersoon is, weergegeven in het persoonlijke profiel. Indien ingesteld op **Blokkeren** wordt het nummer van deze zakelijke contactpersoon niet weergegeven in het persoonlijke profiel. Van toepassing op Android OS v6.0 en nieuwere versies.

- **Werkcontacten zoeken in persoonlijk profiel**: kies **Blokkeren** om te voorkomen dat gebruikers in apps in het persoonlijke profiel zoeken naar werkcontacten. **Niet geconfigureerd**: zoeken naar werkcontacten in het persoonlijke profiel is toegestaan.

- **Camera**: kies **Blokkeren** om toegang tot de camera op het apparaat in het werkprofiel te blokkeren. De camera aan de persoonlijke zijde wordt niet beïnvloed door de instelling. **Niet geconfigureerd** staat de toegang tot de camera in het werkprofiel toe.

- **Widgets toestaan van apps voor werk profielen**: als u **inschakelt** , kunnen eind gebruikers widgets toevoegen aan de slag met apps op het Start scherm. Met **Niet geconfigureerd** (standaard) schakelt u deze functie uit.

  Outlook wordt bijvoorbeeld geïnstalleerd op de werk profielen van uw gebruikers. Als u deze **optie inschakelt**, kunnen gebruikers de object agenda op het Start scherm van het apparaat plaatsen.

#### <a name="work-profile-password"></a>Werkprofielwachtwoord

- **Werkprofielwachtwoord vereisen**: van toepassing op Android 7.0 en hoger waarvoor het werkprofiel is ingeschakeld. Kies **Vereisen** om een beleid voor wachtwoordcodes in te voeren dat alleen van toepassing is op de apps in het werkprofiel. De eindgebruiker kan standaard de twee afzonderlijk gedefinieerde pincodes gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee. **Niet geconfigureerd**: staat de gebruiker toe om werk-apps te gebruiken, zonder een wachtwoord in te voeren.
- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal tekens op waaruit het wachtwoord moet bestaan (**4**-**16**).
- **Maximum aantal minuten van inactiviteit voordat het werkprofiel wordt vergrendeld**: selecteer de hoeveelheid tijd voordat het werkprofiel wordt vergrendeld. De gebruiker moet vervolgens zijn referenties invoeren om weer toegang te krijgen.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer in hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het werkprofiel wordt gewist van het apparaat.
- **Wachtwoord verloopt (dagen)** : hiermee geeft u het aantal dagen op totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
- **Vereist wachtwoordtype**: selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Numeriek complex**: herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: kies **Blokkeren** om te voorkomen dat eindgebruikers de vingerafdrukscanner van het apparaat gebruiken om het apparaat te ontgrendelen. **Niet geconfigureerd**: gebruikers kunnen apparaten ontgrendelen met een vingerafdruk in het werkprofiel.
- **Smart Lock en andere trustagenten**: kies **Blokkeren** om te voorkomen dat Smart Lock of andere trustagenten instellingen voor het vergrendelingsscherm van compatibele apparaten aanpassen. Met deze functie, ook wel een vertrouwensagent genoemd, kunt u het wachtwoord voor het vergrendelingsscherm op het apparaat uitschakelen of overslaan als het apparaat zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

### <a name="device-password"></a>Wachtwoord van apparaat

Deze wachtwoordinstellingen zijn van toepassing op persoonlijke profielen op apparaten die gebruikmaken van een werkprofiel.

- **Minimale wachtwoordlengte**: hiermee geeft u het minimale aantal tekens op waaruit het wachtwoord moet bestaan (**4**-**14**).
- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: selecteer de hoeveelheid tijd voordat een inactief apparaat automatisch wordt vergrendeld.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer in hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat alle gegevens worden gewist van het apparaat.
- **Wachtwoord verloopt (dagen)** : hiermee geeft u het aantal dagen op totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
- **Vereist wachtwoordtype**: selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Numeriek complex**: herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: kies **Blokkeren** om te voorkomen dat eindgebruikers de vingerafdrukscanner van het apparaat gebruiken om het apparaat te ontgrendelen. **Niet geconfigureerd**: staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.
- **Smart Lock en andere trustagenten**: kies **Blokkeren** om te voorkomen dat Smart Lock of andere trustagenten instellingen voor het vergrendelingsscherm van compatibele apparaten aanpassen. Met deze functie, ook wel een vertrouwensagent genoemd, kunt u het wachtwoord voor het vergrendelingsscherm op het apparaat uitschakelen of overslaan als het apparaat zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

### <a name="system-security"></a>Systeembeveiliging

- **Bedreigingenscan voor apps**: **Vereisen**: hiermee dwingt u af dat de instelling **Apps controleren** wordt ingeschakeld voor werk- en persoonlijke profielen.

   > [!Note]
   > Deze instelling werkt alleen voor apparaten met Android O en later.

- **Voor komen dat app-installaties van onbekende bronnen in het persoonlijke profiel**worden uitgevoerd: op basis van het ontwerp van Android Enter prise-werk profielen kunnen geen apps worden geïnstalleerd vanuit andere bronnen dan de Play Store. Op basis van de aard van het werk profiel zijn de volgende twee profielen bedoeld:

  - Een werk profiel dat wordt beheerd met MDM.
  - Een persoonlijk profiel dat is geïsoleerd van MDM-beheer.

  Met deze instelling kunnen beheerders meer app-installaties beheren dan onbekende bronnen. **Niet geconfigureerd** (standaard) Hiermee staat u toe dat app-installaties afkomstig zijn van onbekende bronnen in het persoonlijke profiel. De **blok kering** voor komt dat app-installaties van andere bronnen dan de Play Store in het persoonlijke profiel.

### <a name="connectivity"></a>Connectiviteit

- **AlwaysOn VPN**: kies **Inschakelen** om in te stellen dat een VPN-client automatisch verbinding maakt en opnieuw verbinding maakt met het VPN. AlwaysOn VPN-verbindingen blijven verbonden of maken direct verbinding wanneer gebruikers hun apparaat vergrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. 

  Kies **Niet geconfigureerd** om AlwaysOn VPN voor alle VPN-clients uit te schakelen.

  > [!IMPORTANT]
  > Implementeer slechts één AlwaysOn VPN-beleid per apparaat. Het implementeren van meerdere AlwaysOn VPN-beleidsregels op één apparaat wordt niet ondersteund.

- **VPN-client**: kies een VPN-client die ondersteuning biedt voor AlwaysOn. Uw opties zijn:
  - Cisco AnyConnect
  - F5-toegang
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Aangepast
    - **Pakket-id**: voer de pakket-id in van de app in Google Play. Als de URL voor de app in Google Play bijvoorbeeld `https://play.google.com/store/details?id=com.contosovpn.android.prod` is, is de pakket-id `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - De VPN-client die u kiest moet op het apparaat worden geïnstalleerd en moet VPN per app in werkprofielen ondersteunen. Anders treedt er een fout op. 
  > - U dient de VPN-client-app goed te keuren in de **Beheerde Google Play Store**, de app te synchroniseren naar Intune en de app te implementeren op het apparaat. Nadat u dit hebt gedaan, is de app geïnstalleerd in het werkprofiel van de gebruiker.
  > - Er zijn mogelijk bekende problemen bij het gebruik van VPN per app met F5 Access voor Android 3.0.4. Zie [Releaseopmerkingen voor F5 Access voor Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) voor meer informatie.

- **Vergrendelingsmodus**: kies **Inschakelen** als u wilt afdwingen dat al het verkeer de VPN-tunnel gebruikt. Als er geen VPN-verbinding is ingesteld, heeft het apparaat geen toegang tot het netwerk.

  Kies **Niet geconfigureerd** om toe te staan dat verkeer via de VPN-tunnel of via het mobiele netwerk gaat.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kioskprofielen maken voor toegewezen apparaten met [Android](device-restrictions-android.md#kiosk) en [Windows 10](kiosk-settings.md).

## <a name="see-also"></a>Zie tevens

[Apparaten met Android Enterprise configureren en problemen met deze apparaten oplossen in Microsoft Intune](https://support.microsoft.com/help/4476974)
