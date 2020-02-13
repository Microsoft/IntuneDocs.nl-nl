---
title: Apparaatinstellingen voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Op apparaten met Android Enterprise of Android for Work kunt u beperkingen op het apparaat instellen, zoals voor kopiëren en plakken, het weergeven van meldingen, app-machtigingen, het delen van gegevens, de wachtwoordlengte, mislukte aanmeldpogingen, het gebruik van vingerafdrukken om te ontgrendelen, het opnieuw gebruiken van wachtwoorden en het delen van zakelijke contactpersonen via Bluetooth. Configureer apparaten als een toegewezen apparaatkiosk voor het uitvoeren van een of meer apps.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 122f0b0194a96b844e274ab39a73224eb23cc6b3
ms.sourcegitcommit: 9b29478f815e10c46c8030abe0146d601ce0e28c
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2020
ms.locfileid: "77051589"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Met Android Enterprise-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op Android Enterprise-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, apps uit te voeren op tiegewezen apps, beveiliging te beheren en nog veel meer.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Alleen eigenaar van het apparaat

Deze instellingen zijn van toepassing op Android Enterprise-inschrijvingstypen waarbij het hele apparaat wordt beheerd in Intune, zoals volledig beheerde Android Enterprise-apparaten of toegewezen apparaten.

### <a name="general-settings"></a>Algemene instellingen

- **Schermopname**: Kies **Blokkeren** als u wilt voorkomen dat schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. U voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben. **Niet geconfigureerd**: stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding.
- **Camera**: Kies **Blokkeren** als u de toegang tot de camera op het apparaat wilt blokkeren. **Niet vereist**: staat toegang tot de camera van het apparaat toe.
- **Standaardmachtigingsbeleid**: Met deze instelling bepaalt u het standaardmachtigingsbeleid voor aanvragen betreffende runtime-machtigingen. De mogelijke waarden zijn:
  - **Standaardwaarde apparaat**: De standaardinstelling van het apparaat wordt gebruikt.
  - **Vragen**: De gebruiker wordt gevraagd de machtiging goed te keuren.
  - **Automatisch verlenen**: Machtigingen worden automatisch verleend.
  - **Automatisch weigeren**: Machtigingen worden automatisch geweigerd.
- **Wijzigingen in datum en tijd**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers handmatig de datum en tijd instellen. **Niet geconfigureerd**: staat gebruikers toe om de datum en tijd in te stellen op het apparaat.
- **Volumewijzigingen**: **Blokkeren** voorkomt dat gebruikers het volume van het apparaat wijzigingen, en dempt ook het hoofdvolume. **Niet geconfigureerd**: staat gebruik van de volume-instellingen toe op het apparaat.
- **Fabrieksinstellingen terugzetten**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers de optie voor het terugzetten van de fabrieksinstellingen van het apparaat gebruiken. **Niet geconfigureerd**: staat gebruikers toe om deze instelling te gebruiken op het apparaat.
- **Opstarten in veilige modus**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers het apparaat opnieuw opstarten in de veilige modus. **Niet geconfigureerd**: staat gebruikers toe om het apparaat opnieuw op te starten in de veilige modus.
- **Statusbalk**: Kies **Blokkeren** als u de toegang wilt blokkeren tot de statusbalk, met inbegrip van meldingen en snelle instellingen. **Niet geconfigureerd**: gebruikers hebben toegang tot de statusbalk.
- **Roaming gegevensservices**: Kies **Blokkeren** om dataroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd**: staat dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Wi-Fi-instellingswijzigingen**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers Wi-Fi-instellingen wijzigen die zijn geconfigureerd door de eigenaar van het apparaat. Gebruikers kunnen hun eigen Wi-Fi-configuraties maken. **Niet geconfigureerd**: staat gebruikers toe om de Wi-Fi-instellingen op het apparaat te wijzigen.
- **Configuratie van Wi-Fi-toegangspunt**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers Wi-Fi-configuraties maken of wijzigen. **Niet geconfigureerd**: staat gebruikers toe om de Wi-Fi-instellingen op het apparaat te wijzigen.
- **Bluetooth-configuratie**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers Bluetooth configureren op het apparaat. **Niet geconfigureerd**: hiermee kan de gebruiker Bluetooth op het apparaat gebruiken.
- **Tethering en toegang tot hotspots**: Kies **Blokkeren** als u tethering en toegang tot draagbare hotspots wilt blokkeren. **Niet geconfigureerd**: tethering en toegang tot draagbare hotspots is toegestaan.
- **USB-opslag**: Kies **Toestaan** als u toegang tot USB-opslag op het apparaat toestaat. **Niet geconfigureerd**: voorkomt toegang tot USB-opslag.
- **USB-bestandsoverdracht**: Kies **Blokkeren** als u bestandsoverdracht via USB wilt voorkomen. **Niet geconfigureerd**: bestandsoverdracht is toegestaan.
- **Externe media**: Kies **Blokkeren** als u wilt voorkomen dat er externe media op het apparaat worden aangesloten of hiermee verbinding wordt gemaakt. **Niet geconfigureerd**: externe media toestaan op het apparaat.
- **Gegevens beamen met NFC**: Kies **Blokkeren** als u wilt voorkomen dat gegevens worden verzonden vanuit apps met behulp van de NFC-technologie. **Niet geconfigureerd**: NFC kan worden gebruikt voor het delen van gegevens tussen apparaten.
- **Foutopsporingsfuncties**: Kies **Toestaan** als u wilt toestaan dat gebruikers de functies voor foutopsporing gebruiken op het apparaat. **Niet geconfigureerd**: voorkomt dat gebruikers de functies voor foutopsporing kunnen gebruiken op het apparaat.
- **Microfoon aanpassen**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers de microfoon kunnen inschakelen of het volume van de microfoon kunnen aanpassen. **Niet geconfigureerd**: de gebruiker kan de microfoon van het apparaat gebruiken en het volume ervan aanpassen.
- **E-mailadressen resetbeveiliging fabrieksinstellingen**: Kies **e-mailadressen van een Google-account**. Voer de e-mailadressen in van apparaatbeheerders die het apparaat kunnen ontgrendelen nadat dit is gewist. Plaats een puntkomma tussen de e-mailadressen, zoals `admin1@gmail.com;admin2@gmail.com`. Als u geen e-mailadres invoert, kan iedereen het apparaat ontgrendelen nadat de fabrieksinstellingen zijn hersteld. Deze e-mailberichten zijn alleen van toepassing wanneer terugzetten van de fabrieksinstellingen wordt geactiveerd door een niet-gebruiker, zoals bijvoorbeeld een herstelmenu.
- **Netwerknooduitgang**: Kies **Inschakelen** als gebruikers de functie Netwerknooduitgang mogen inschakelen. Als er geen netwerkverbinding tot stand wordt gebracht bij het opstarten van het apparaat, vraagt de functie of er tijdelijk verbinding moet worden gemaakt met een netwerk en of het apparaatbeleid moet worden vernieuwd. Wanneer het beleid is toegepast, wordt het tijdelijke netwerk vergeten en gaat het apparaat verder met opstarten. Deze functie maakt in de volgende gevallen verbinding tussen een apparaat en netwerk:
  - Er bevindt zich geen geschikt netwerk in het laatste beleid.
  - Het apparaat wordt opgestart naar een app in de modus vergrendelingstaak.
  - De gebruiker heeft geen toegang tot de apparaatinstellingen.

  **Niet geconfigureerd**: hiermee wordt voorkomen dat gebruikers de functie Netwerknooduitgang inschakelen op het apparaat.

- **Systeemupdate**: Kies een optie om te bepalen hoe het apparaat omgaat met draadloze updates:
  - **Standaardwaarde apparaat**: De standaardinstelling van het apparaat wordt gebruikt.
  - **Automatisch**: Updates worden automatisch geïnstalleerd zonder interactie van de gebruiker. Wanneer u dit beleid instelt, worden alle eventuele updates die nog niet zijn uitgevoerd, meteen geïnstalleerd.
  - **Uitgesteld**: Updates worden 30 dagen uitgesteld. Na 30 dagen wordt de gebruiker door Android gevraagd om de update te installeren. Het is mogelijk dat apparaatfabrikanten of leveranciers het uitstellen van belangrijke beveiligingsupdates voorkomen (uitzonderen). Voor een uitzonderingsupdate wordt een systeembericht weergegeven op het apparaat.
  - **Onderhoudsvenster**: Hiermee worden updates automatisch geïnstalleerd tijdens een dagelijkse onderhoudsperiode die u in Intune instelt. Er wordt gedurende 30 dagen geprobeerd om de updates te installeren. Dit kan mislukken als er te weinig ruimte of onvoldoende accuvermogen is. Na 30 dagen vraagt Android de gebruiker om te installeren. Deze periode wordt is ook gebruikt om updates voor Play-apps te installeren. Gebruik deze optie voor specifieke apparaten, zoals kiosken, omdat toegewezen apparaten mt maar één app op de voorgrond kunnen worden bijgewerkt.

- **Meldingsvensters**: Als de optie **Uitschakelen** is ingesteld, worden venstermeldingen, inclusief pop-ups, inkomende oproepen, uitgaande oproepen, systeemwaarschuwingen en systeemfouten niet weergegeven op het apparaat. Als de optie **Niet geconfigureerd** is ingesteld, wordt de standaardinstelling van het besturingssysteem gebruikt, die mogelijk bepaalt dat meldingen worden weergegeven.
- **Hints voor eerste gebruik overslaan**: **Inschakelen** verbergt suggesties (of slaat deze over) van apps die stapsgewijs door zelfstudies gaan, of hints wanneer de app wordt gestart. Als de optie **Niet geconfigureerd** is ingesteld, wordt de standaardinstelling van het besturingssysteem gebruikt, die mogelijk bepaalt dat suggesties worden weergegeven wanneer de app wordt gestart.

### <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

- **Bedreigingsscan voor apps**: Met **Vereisen** (standaard) kunnen apps worden gescand door Google Play Protect voor- en nadat deze zijn geïnstalleerd. Als er een bedreiging wordt gedetecteerd, kan de gebruiker de waarschuwing krijgen dat de app moet worden verwijderd van het apparaat. **Niet geconfigureerd**: hiermee wordt Google Play Protect niet in staat gesteld of uitgevoerd om apps te scannen.

### <a name="dedicated-device-settings"></a>Toegewezen apparaatinstellingen

Gebruik deze instellingen om een kioskstijlervaring op uw toegewezen apparaten te configureren. U kunt een apparaat configureren voor het uitvoeren van één app of een aantal apps. Wanneer een apparaat op de kioskmodus is ingesteld, zijn alleen de apps beschikbaar die u expliciet hebt toegevoegd. Deze instellingen zijn van toepassing op toegewezen Android Enterprise-apparaten. Deze zijn niet van toepassing op volledig beheerde Android Enterprise-apparaten.

**Kioskmodus**: Kies dit als op het apparaat één app of meerdere apps worden uitgevoerd.

- **Eén app**: Gebruikers hebben slechts toegang tot één app op het apparaat. Wanneer het apparaat wordt gestart, wordt alleen de specifieke app gestart. Gebruikers kunnen geen nieuwe apps openen of de actieve app wijzigen.

  - **Een beheerde app selecteren**: Selecteer de beheerde Google Play-app in de lijst.

    Als er geen apps worden vermeld, [voegt u enkele Android-apps toe](../apps/apps-add-android-for-work.md) aan het apparaat. Zorg ervoor dat u [de app toewijst](../apps/apps-deploy.md) aan de apparaatgroep die is gemaakt voor uw toegewezen apparaten.

  > [!IMPORTANT]
  > Wanneer u de kioskmodus voor één app gebruikt, werken de apps voor kiezer/telefoon mogelijk niet goed. 
  
- **Meerdere apps**: Gebruikers hebben toegang tot een beperkte set apps op het apparaat. Wanneer het apparaat wordt gestart, worden alleen de toegevoegde apps gestart. U kunt ook enkele webkoppelingen toevoegen die gebruikers kunnen openen. Wanneer het beleid wordt toegepast, zien gebruikers pictogrammen voor de toegestane apps op het startscherm.

  > [!IMPORTANT]
  > Voor toegewezen apparaten voor meerdere apps **moet** de [app Managed Home Screen](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) van Google Play zijn:
  >   - [Toegevoegd als een client-app](../apps/apps-add-android-for-work.md) in Intune
  >   - [Toegewezen aan de apparaatgroep](../apps/apps-deploy.md) die is gemaakt voor uw toegewezen apparaten
  >
  > De app **Managed Home Screen** hoeft niet te zijn opgenomen in het configuratieprofiel, maar moet wel worden toegevoegd als een client-app. Wanneer de app **Managed Home Screen** wordt toegevoegd als een client-app, worden andere apps die u aan het configuratieprofiel toevoegt, weergegeven als pictogrammen in de app **Managed Home Screen**.
  >
  > Wanneer u de kiosk modus voor meerdere apps gebruikt, werken de apps voor kiezer/telefoon mogelijk niet goed. 

  - **Toevoegen**: selecteer uw apps in de lijst.

    Als de app **Managed Home Screen** niet wordt vermeld, [voegt u deze toe vanuit Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Zorg ervoor dat u [de app toewijst](../apps/apps-deploy.md) aan de apparaatgroep die is gemaakt voor uw toegewezen apparaten.

    U kunt ook andere [Android-apps](../apps/apps-add-android-for-work.md) toevoegen aan het apparaat, evenals [web-apps](../apps/web-app.md) die zijn gemaakt door uw organisatie. Zorg ervoor dat u [de app toewijst](../apps/apps-deploy.md) aan de apparaatgroep die is gemaakt voor uw toegewezen apparaten.

  - **Virtuele knop Start**: een schermtoets waarmee gebruikers terugkeren naar Managed Home Screen zodat ze kunnen schakelen tussen apps. Uw opties zijn:

    - **Niet geconfigureerd** (standaard): er wordt geen knop Start weergegeven. Gebruikers moeten de knop Terug gebruiken om tussen apps te schakelen.
    - **Omhoog vegen**: er wordt een knop Start weergegeven wanneer een gebruiker naar boven veegt op het apparaat.
    - **Zwevend**: toont een permanente, zwevende knop Start op het apparaat.

  - **Kioskmodus verlaten**: Kies **Inschakelen** om beheerders toestemming te geven de kioskmodus tijdelijk te onderbreken om het apparaat bij te werken. Voor gebruik van deze functie moet de beheerder het volgende doen:
  
    1. Doorgaan met het selecteren van de knop Terug totdat de knop **Kiosk verlaten** wordt weergegeven. 
    2. Hiermee wordt de knop **Kiosk verlaten** geselecteerd en de pincode voor het **verlaten van de kioskmodus ingevoerd**.
    3. Wanneer u klaar bent, selecteert u de app **Managed Home Screen**. Met deze stap wordt het apparaat weer vergrendeld in de kioskmodus voor gebruik van meerdere apps.

      Als de instelling is ingesteld op **Niet geconfigureerd**, kunnen beheerders de kioskmodus niet onderbreken. Als de beheerder de knop Terug blijft selecteren en vervolgens de knop **Kiosk verlaten** selecteert, verschijnt er een bericht dat er een wachtwoordcode moet worden ingevoerd.

    - **Code voor verlaten kioskmodus**: Voer een 4-6-cijferige numerieke pincode in. De beheerder gebruikt deze pincode om de kioskmodus tijdelijk te onderbreken.

  - **Achtergrond voor aangepaste URL instellen**: Voer een URL in voor het aanpassen van het achtergrondscherm op het toegewezen apparaat.

    > [!NOTE]
    > In de meeste gevallen is het aan te raden om te beginnen met installatiekopieën van ten minste de volgende grootten:
    >
    > - Telefoon: 1080 x 1920 pixels
    > - Tablet: 1920 x 1080 pixels
    >
    > Voor de beste ervaring en heldere details is het aan te raden om per apparaatinstallatiekopie assets te maken voor de schermspecificaties.
    >
    > Moderne schermen hebben een hogere pixeldichtheid met de mogelijkheid om definitie-installatiekopieën gelijkwaardig aan 2K/4K weer te geven.

  - **Wi-Fi-configuratie**: met **Inschakelen** wordt het Wi-Fi-besturingselement weergegeven in Managed Home Screen, en krijgen eindgebruikers de mogelijkheid om het apparaat te verbinden met verschillende WiFi-netwerken. Als u deze functie inschakelt, wordt ook de apparaatlocatie ingeschakeld. **Niet geconfigureerd** (standaard): het Wi-Fi-besturingselement wordt niet weergegeven op Managed Home Screen. Hiermee voorkomt u dat gebruikers verbinding kunnen maken met Wi-Fi-netwerken terwijl ze Managed Home Screen gebruiken.

  - **Bluetooth-configuratie**: met **Inschakelen** wordt het Bluetooth-besturingselement weergegeven in Managed Home Screen, en krijgen eindgebruikers de mogelijkheid om apparaten te koppelen via Bluetooth. Als u deze functie inschakelt, wordt ook de apparaatlocatie ingeschakeld. **Niet geconfigureerd** (standaard): het Bluetooth-besturingselement wordt niet weergegeven in Managed Home Screen. Hiermee voorkomt u dat gebruikers Bluetooth configureren en apparaten koppelen terwijl ze Managed Home Screen gebruiken.

  - **Zaklamp-toegang**: met **Inschakelen** wordt het Zaklamp-besturingselement weergegeven in Managed Home Screen, en krijgen eindgebruikers de mogelijkheid om de zaklamp in of uit te schakelen. **Niet geconfigureerd** (standaard): het Zaklamp-besturingselement wordt niet weergegeven in Managed Home Screen. Hiermee voorkomt u dat gebruikers de zaklamp gebruiken terwijl ze Managed Home Screen gebruiken.

  - **Volumeregeling voor media**: met **Inschakelen** wordt het Volumeregeling voor media-besturingselement weergegeven in Managed Home Screen, en krijgen eindgebruikers de mogelijkheid om het mediavolume van het apparaat aan te passen met een schuifregelaar. **Niet geconfigureerd** (standaard): het Volumeregeling voor media-besturingselement wordt niet weergegeven in Managed Home Screen. Hiermee voorkomt u dat gebruikers het mediavolume van het apparaat aanpassen terwijl ze Managed Home Screen gebruiken, tenzij de hardwareknoppen hier ondersteuning voor bieden. 

  - **Schermbeveiligingsmodus**: met **Inschakelen** wordt een schermbeveiliging weergegeven in Managed Home Screen wanneer het apparaat is vergrendeld of wanneer er een time-out optreedt. **Niet geconfigureerd** (standaard): er wordt geen schermbeveiliging weergegeven in Managed Home Screen.

    Wanneer deze functie is ingeschakeld, moet u ook het volgende configureren:

    - **Aangepaste afbeelding voor schermbeveiliging instellen**: voer de URL in naar een aangepaste PNG-, JPG-, JPEG-, GIF-, BMP-, WebP- of ICO-afbeelding. Voer bijvoorbeeld het volgende in:

      - `http://www.contoso.com/image.jpg`
      - `www.contoso.com/image.bmp`
      - `https://www.contoso.com/image.webp`

      Als u geen URL opgeeft, wordt de standaardafbeelding van het apparaat gebruikt, indien aanwezig.
      
      > [!TIP]
      > Elke bestandsresource-URL die in een bitmap kan worden omgezet, wordt ondersteund.

    - **Het aantal seconden dat een schermbeveiliging wordt weergegeven op het apparaat voordat het scherm wordt uitgeschakeld**: kies hoe lang de schermbeveiliging wordt weergegeven op het apparaat. Voer een waarde in tussen 0-9.999.999 seconden. De standaardwaarde is `0` seconden. Als deze waarde leeg is of is ingesteld op 0 (`0`), blijft de schermbeveiliging actief totdat een gebruiker met het apparaat communiceert.
    - **Aantal seconden dat het apparaat inactief is voordat de schermbeveiliging wordt weergegeven**: kies hoe lang het apparaat inactief moet zijn voordat de schermbeveiliging wordt weergegeven. Voer een waarde in tussen 0-9.999.999 seconden. De standaardwaarde is `30` seconden. U moet een getal opgeven dat groter is dan nul (`0`).
    - **Media detecteren voordat de schermbeveiliging wordt gestart**: met **Inschakelen** (standaard) wordt de schermbeveiliging niet weergegeven wanneer er audio of video wordt afgespeeld op het apparaat. **Niet geconfigureerd**: de schermbeveiliging wordt weergegeven, zelfs als er audio of video wordt afgespeeld.

### <a name="device-password-settings"></a>Instellingen voor apparaatwachtwoord

- **Vergrendelingsscherm uitschakelen**: Kies **Uitschakelen** als u wilt voorkomen dat gebruikers de functie voor het vergrendelen van het scherm Keyguard op het apparaat gebruiken. **Niet geconfigureerd**: staat de gebruiker toe de Keyguard-functies te gebruiken.
- **Uitgeschakelde functies van het vergrendelingsscherm**: Kies, wanneer keyguard is ingeschakeld op het apparaat, welke functies u wilt uitschakelen. Wanneer bijvoorbeeld de optie **Veilige camera** is geselecteerd, wordt de functie van de camera op het apparaat is uitgeschakeld. Alle functies die niet zijn geselecteerd, zijn op het apparaat ingeschakeld.

  Deze functies zijn beschikbaar voor gebruikers wanneer het apparaat is vergrendeld. De geselecteerde functies zijn niet zichtbaar en niet toegankelijk voor gebruikers.

- **Vereist wachtwoordtype**: Bepaal welk type wachtwoord wordt vereist voor het apparaat. Uw opties zijn:
  - **Standaardwaarde apparaat**
  - **Wachtwoord vereist, geen beperkingen**
  - **Zwakke biometrie**: [Sterke versus zwakke biometrie](https://android-developers.googleblog.com/2018/06/better-biometrics-in-android-p.html) (hiermee wordt een Android-website geopend)
  - **Numeriek**: Het wachtwoord mag alleen uit getallen bestaan, bijvoorbeeld `123456789`. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Complex numeriek**: Herhaalde of opeenvolgende cijfers, zoals '1111' of '1234', zijn niet toegestaan. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Alfabetisch**: Letters uit het alfabet zijn vereist. Er zijn geen cijfers en symbolen vereist. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Alfanumeriek**: Dit zijn hoofdletters, kleine letters en numerieke tekens. Voer de **Minimale wachtwoordlengte** die een gebruiker moet invoeren in, tussen 4 en 16 tekens.
  - **Alfanumeriek met symbolen**: Dit zijn hoofdletters, kleine letters, numerieke tekens, leestekens en symbolen. Voer ook in:

    - **Minimale wachtwoordlengte**: Voer de minimale lengte van het wachtwoord in, tussen 4 en 16 tekens.
    - **Het vereiste aantal tekens**: Voer het aantal tekens in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal kleine letters**: Voer het aantal kleine letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal hoofdletters**: Voer het aantal hoofdletters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal andere tekens dan letters**: Voer het aantal andere tekens dan alfabetische letters in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal numerieke tekens**: Voer het aantal numerieke tekens (`1`, `2`, `3` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.
    - **Het vereiste aantal symbolen**: Voer het aantal symbolen (`&`, `#`, `%` enzovoort) in dat het wachtwoord moet bevatten, tussen 0 en 16 tekens.

- **Het aantal dagen totdat het wachtwoord verloopt**: Voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd, tussen 1 en 365. Als u bijvoorbeeld wilt dat het wachtwoord na zestig dagen moet worden gewijzigd, voert u `60` in. Wanneer het wachtwoord is verlopen, wordt gebruikers gevraagd een nieuw wachtwoord te maken.
- **Het vereiste aantal wachtwoorden voordat de gebruiker een wachtwoord opnieuw kan gebruiken**: Voer het aantal recente wachtwoorden in dat niet opnieuw mag worden gebruikt, tussen 1 en 24. Gebruik deze instelling om te voorkomen dat de gebruiker eerder gebruikte wachtwoorden hergebruikt.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Geef het aantal mislukte aanmeldingen op, tussen 4 en 11, dat is toegestaan voordat het apparaat wordt gewist.

### <a name="power-settings"></a>Energie-instellingen

- **Tijd voor schermvergrendeling**: voer de maximale tijd in die een gebruiker kan instellen, totdat het apparaat wordt vergrendeld. Als u deze instelling bijvoorbeeld instelt op **10 minuten**, kunnen gebruikers een tijd instellen tussen 15 seconden en 10 minuten. Wanneer dit is ingesteld op **Niet geconfigureerd** (standaard), wordt deze instelling niet gewijzigd of beheerd in Intune.

- **Scherm aan terwijl het apparaat is aangesloten**: Kies bij welke energiebronnen het scherm aan blijft wanneer het apparaat is aangesloten.

### <a name="users-and-accounts-settings"></a>Gebruikers- en accountinstellingen

- **Nieuwe gebruikers toevoegen**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers nieuwe gebruikers toevoegen. Elke gebruiker heeft een persoonlijke ruimte op het apparaat voor aangepaste beginschermen, accounts, apps en instellingen. **Niet geconfigureerd** (standaardinstelling) staat gebruikers toe om andere gebruikers toe te voegen aan het apparaat.
- **Gebruiker verwijderen**: Selecteer **Blokkeren** om te voorkomen dat gebruikers andere gebruikers verwijderen. **Niet geconfigureerd** (standaardinstelling) staat gebruikers toe om andere gebruikers toe te voegen aan het apparaat.
- **Accountwijzigingen** (alleen toegewezen apparaten): kies **Blokkeren** als u wilt voorkomen dat gebruikers accounts wijzigen. **Niet geconfigureerd** (standaardinstelling) staat gebruikers toe om gebruikersaccounts op het apparaat bij te werken.

  > [!NOTE]
  > Deze instelling geldt niet op apparaten van apparaateigenaar (volledig beheerd). Als u deze instelling configureert, wordt de instelling genegeerd en heeft deze geen invloed.

- **Gebruiker kan referenties configureren**: **Blokkeren** voorkomt dat gebruikers certificaten configureren die zijn toegewezen aan apparaten, zelfs bij apparaten die niet zijn gekoppeld aan een gebruikersaccount. **Niet geconfigureerd**: kan gebruikers de mogelijkheid bieden om hun referenties te configureren of te wijzigen wanneer ze deze openen in de KeyStore-opslag. 
- **Persoonlijke Google-accounts**: **Blokkeren** voorkomt dat gebruikers hun persoonlijke Google-account toevoegen aan het apparaat. **Niet geconfigureerd** (standaard): gebruikers kunnen hun persoonlijke Google-account toevoegen.

### <a name="applications"></a>Toepassingen

- **Installatie vanuit onbekende bronnen toestaan**: Kies **Toestaan**, zodat gebruikers **Onbekende bronnen** kunnen inschakelen. Met deze instelling kunnen apps van onbekende bronnen worden geïnstalleerd, met inbegrip van andere bronnen dan Google Play Store. **Niet geconfigureerd**: voorkomt dat gebruikers **Onbekende bronnen** kunnen inschakelen.
- **Toegang tot alle apps in Google Play Store toestaan**: Als deze optie is ingesteld op **Toestaan**, krijgen gebruikers toegang tot alle apps in Google Play store. Ze krijgen geen toegang tot apps die de beheerder blokkeert in[Client-apps](../apps/apps-add-android-for-work.md). **Niet geconfigureerd**: gebruikers hebben alleen toegang tot apps die de beheerder beschikbaar maakt in Google Play Store of apps die zijn vereist in [Client-apps](../apps/apps-add-android-for-work.md).
- **App wordt automatisch bijgewerkt**: Kies deze optie wanneer updates automatisch worden geïnstalleerd. Uw opties zijn:
  - **Niet geconfigureerd**
  - **Gebruiker kiezen**
  - **Nooit**
  - **Alleen Wi-Fi**
  - **Altijd**

### <a name="connectivity"></a>Connectiviteit

- **Permanente VPN**: Kies **Inschakelen** als u wilt instellen dat een VPN-client automatisch verbinding maakt en opnieuw verbinding maakt met het VPN. AlwaysOn VPN-verbindingen blijven verbonden of maken direct verbinding wanneer gebruikers hun apparaat vergrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. 

  Kies **Niet geconfigureerd** om AlwaysOn VPN voor alle VPN-clients uit te schakelen.

  > [!IMPORTANT]
  > Implementeer slechts één AlwaysOn VPN-beleid per apparaat. Het implementeren van meerdere AlwaysOn VPN-beleidsregels op één apparaat wordt niet ondersteund.

- **VPN-client**: Kies een VPN-client die ondersteuning biedt voor AlwaysOn. Uw opties zijn:
  - Cisco AnyConnect
  - F5-toegang
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Aangepast
    - **Pakket-id**: Voer de pakket-id in van de app in Google Play. Als de URL voor de app in Google Play bijvoorbeeld `https://play.google.com/store/details?id=com.contosovpn.android.prod` is, is de pakket-id `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - De VPN-client die u kiest moet op het apparaat worden geïnstalleerd en moet VPN per app in werkprofielen ondersteunen. Anders treedt er een fout op. 
  > - U dient de VPN-client-app goed te keuren in de **Beheerde Google Play Store**, de app te synchroniseren naar Intune en de app te implementeren op het apparaat. Nadat u dit hebt gedaan, is de app geïnstalleerd in het werkprofiel van de gebruiker.
  > - U moet de VPN-client nog steeds configureren met een [VPN-profiel](vpn-settings-android-enterprise.md) of via een [app-configuratieprofiel](../apps/app-configuration-policies-use-android.md).
  > - Er zijn mogelijk bekende problemen bij het gebruik van VPN per app met F5 Access voor Android 3.0.4. Zie [Releaseopmerkingen voor F5 Access voor Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) voor meer informatie.

- **Vergrendelingsmodus**: Kies **Inschakelen** als u wilt afdwingen dat al het verkeer de VPN-tunnel gebruikt. Als er geen VPN-verbinding is ingesteld, heeft het apparaat geen toegang tot het netwerk.

  Kies **Niet geconfigureerd** om toe te staan dat verkeer via de VPN-tunnel of via het mobiele netwerk gaat.

- **Aanbevolen algemene proxy**: kies **Inschakelen** om een algemene proxy toe te voegen aan de apparaten. Wanneer deze functie is ingeschakeld, wordt het HTTP- en HTTPS-verkeer, inclusief enkele apps op het apparaat, gebruikt voor de proxy die u invoert. Deze proxy is slechts een aanbeveling. Het kan zijn dat sommige apps de proxy niet gebruiken. **Niet geconfigureerd** (standaard): er wordt geen aanbevolen algemene proxy toegevoegd.

  Zie [setRecommendedGlobalProxy](https://developer.android.com/reference/android/app/admin/DevicePolicyManager.html#setRecommendedGlobalProxy(android.content.ComponentName,%20android.net.ProxyInfo)) (er wordt een Android-site geopend) voor meer informatie over deze functie.

  Wanneer deze functie is ingeschakeld, voert u ook het **Type** proxy in. Uw opties zijn:

  - **Direct**: kies deze optie om de proxyserverinstellingen handmatig in te voeren, waaronder:
    - **Host**: voer de hostnaam of het IP-adres van de proxyserver in. Voer bijvoorbeeld `proxy.contoso.com` of `127.0.0.1` in.
    - **Poortnummer**: Voer het TCP-poortnummer in dat wordt gebruikt voor de proxyserver. Voer bijvoorbeeld `8080` in.
    - **Uitgesloten hosts**: voer een lijst met hostnamen of IP-adressen in die niet gebruikmaken van de proxy. Deze lijst kan een asterisk (`*`) bevatten en meerdere hosts gescheiden door puntkomma’s (`;`) zonder spaties. Voer bijvoorbeeld `127.0.0.1;web.contoso.com;*.microsoft.com` in.

  - **Automatische proxyconfiguratie**: voer de **PAC-URL** in voor een automatisch script voor de proxyconfiguratie. Voer bijvoorbeeld `https://proxy.contoso.com/proxy.pac` in.

    Zie [PAC-bestand (Proxy Auto-Configuration)](https://developer.mozilla.org/docs/Web/HTTP/Proxy_servers_and_tunneling/Proxy_Auto-Configuration_(PAC)_file) (hiermee opent u een niet-Microsoft-site) voor meer informatie over PAC-bestanden.

## <a name="work-profile-only"></a>Alleen werkprofiel

Deze instellingen zijn van toepassing op Android Enterprise-inschrijvingstypen waarbij alleen het werkprofiel wordt beheerd in Intune, zoals een inschrijving voor een Android Enterprise-werkprofiel op een persoonlijk apparaat of een BYOD-apparaat (Bring-Your-Own-Device).

### <a name="work-profile-settings"></a>Werkprofielinstellingen

#### <a name="general"></a>Algemeen

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen**: Kies **Blokkeren** om kopiëren en plakken te voorkomen tussen werkprofielen en persoonlijke apps. **Niet geconfigureerd**: staat gebruikers toe om gegevens met behulp van kopiëren en plakken te delen met apps in het persoonlijke profiel. 
- **Gegevens delen tussen werkprofielen en persoonlijke profielen**: Kies of delen mogelijk is tussen apps in het werkprofiel en apps in het persoonlijke profiel. Met deze instelling kunt u bijvoorbeeld deelacties binnen toepassingen bepalen, zoals de optie **Delen…** in de Chrome-browser-app. Deze instelling geldt niet voor kopiëren en plakken op het klembord. Uw opties voor delen:
  - **Standaardwaarde apparaat**: Dit is de standaardinstelling voor het delen van gegevens van het apparaat. Deze instelling is afhankelijk van de Android-versie. Delen van het persoonlijke profiel naar het werkprofiel is standaard toegestaan. Delen van het werkprofiel naar het persoonlijke profiel is standaard geblokkeerd. Met deze instelling wordt voorkomen dat er gegevens worden gedeeld van het werkprofiel met het persoonlijke profiel. Google blokkeert niet delen van het persoonlijke profiel naar het werkprofiel op apparaten met versie 6.0 of hoger.
  - **Met apps in het werkprofiel kunnen aanvragen voor delen van het persoonlijke profiel worden verwerkt**: Hiermee wordt de ingebouwde Android-functie ingeschakeld waarmee het delen van het persoonlijke profiel naar het werkprofiel is toegestaan. Wanneer dit is ingeschakeld, kan een deelverzoek van een app in het persoonlijke profiel worden gedeeld met apps in het werkprofiel. Dit is de standaardinstelling voor Android-apparaten met een oudere versie dan 6.0.
  - **Delen buiten grenzen voorkomen**: voorkomt delen tussen een werkprofiel en een persoonlijk profiel.
  - **Geen beperkingen voor delen**: schakelt delen buiten de grenzen van een werkprofiel in, in beide richtingen. Wanneer u deze instelling selecteert, kunnen apps met het werkprofiel gegevens delen met apps in het persoonlijke profiel die geen badge hebben. Met deze instelling kunnen beheerde apps in het werkprofiel gegevens delen met apps aan de onbeheerde zijde van het apparaat. Gebruik deze instelling daarom zorgvuldig.

- **Werkprofielmeldingen terwijl het apparaat is vergrendeld**: Hiermee kunt u bepalen of de apps in het werkprofiel gegevens in meldingen kunnen weergeven wanneer het apparaat is vergrendeld. **Blokkeren**: de gegevens worden niet weergegeven. **Niet geconfigureerd**: de gegevens worden weergegeven.
- **Standaardapp-machtigingen**: Hiermee stelt u het standaardmachtigingsbeleid in voor alle apps in het werkprofiel. Vanaf Android 6 wordt de gebruiker gevraagd bepaalde vereiste machtigingen aan apps toe te kennen wanneer de app wordt gestart. Met deze beleidsinstelling kunt u in het werkprofiel bepalen of gebruikers wordt gevraagd om machtigingen toe te kennen voor alle apps in het werkprofiel. U kunt bijvoorbeeld een app aan het werkprofiel toewijzen waarvoor toegang tot de locatie is vereist. Normaal gesproken wordt de gebruiker gevraagd of hij de app toegang tot de locatie wil geven. Gebruik dit beleid om automatisch machtigingen te verlenen zonder om bevestiging te vragen, automatisch machtigingen te weigeren zonder om bevestiging te vragen, of om de eindgebruiker te laten beslissen. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Vragen**
  - **Automatisch verlenen**
  - **Automatisch weigeren**

  U kunt ook een app-configuratiebeleid gebruiken om machtigingen voor afzonderlijke apps te verlenen (**Client-apps** > **App-configuratiebeleid**).

- **Accounts toevoegen en verwijderen**: Kies **Blokkeren** om te voorkomen dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen. Als u de Gmail-app bijvoorbeeld implementeert in een Android-werkprofiel, kunt u verhinderen dat eindgebruikers accounts toevoegen aan of verwijderen uit dit werkprofiel. **Niet geconfigureerd**: hiermee wordt toegestaan dat accounts worden toegevoegd aan het werkprofiel.  

  > [!NOTE]
  > Google-accounts kunnen niet worden toegevoegd aan een werkprofiel.

- **Contactpersoon delen via Bluetooth**: Hiermee krijgt u toegang tot werkcontactpersonen op een ander apparaat, zoals een auto, dat via Bluetooth is gekoppeld. Standaard is deze instelling niet geconfigureerd en worden contactpersonen met een werkprofiel niet weergegeven. Selecteer **Inschakelen** om het delen hiervan toe te staan en contactpersonen met een werkprofiel weer te geven. Deze instelling is van toepassing op Android-apparaten met een werkprofiel met Android OS v6.0 en hoger. Door deze instelling in te schakelen, kunnen bepaalde Bluetooth-apparaten werkcontactpersonen cachen bij de eerste verbinding. Als u dit beleid uitschakelt na een eerste synchronisatie, zijn de werkcontactpersonen van een Bluetooth-apparaat niet meteen verwijderd.

- **Schermopname**: Kies **Blokkeren** als u wilt voorkomen dat in het werkprofiel schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. U voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben. **Niet geconfigureerd**: schermafbeeldingen zijn toegestaan.

- **Beller-id van zakelijk contactpersoon weergeven in persoonlijk profiel**: Indien ingeschakeld (**niet-geconfigureerd**), worden de details van de beller die een zakelijke contactpersoon is, weergegeven in het persoonlijke profiel. Indien ingesteld op **Blokkeren** wordt het nummer van deze zakelijke contactpersoon niet weergegeven in het persoonlijke profiel. Van toepassing op Android OS v6.0 en nieuwere versies.

- **Werkcontacten zoeken in persoonlijk profiel**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers in apps in het persoonlijke profiel zoeken naar werkcontacten. **Niet geconfigureerd**: zoeken naar werkcontacten in het persoonlijke profiel is toegestaan.

- **Camera**: Kies **Blokkeren** als u de toegang tot de camera op het apparaat in het werkprofiel wilt blokkeren. De camera aan de persoonlijke zijde wordt niet beïnvloed door de instelling. **Niet geconfigureerd** staat de toegang tot de camera in het werkprofiel toe.

- **Widgets van apps in het werkprofiel toestaan**: met **Inschakelen** krijgen eindgebruikers de mogelijkheid om widgets van apps op het startscherm te plaatsen. Met **Niet geconfigureerd** (standaard) schakelt u deze functie uit.

  Stel bijvoorbeeld dat Outlook is geïnstalleerd in de werkprofielen van uw gebruikers. Als deze instelling is ingesteld op **Inschakelen**, kunnen gebruikers de agendawidget op het startscherm van het apparaat plaatsen.

#### <a name="work-profile-password"></a>Werkprofielwachtwoord

- **Werkprofielwachtwoord vereisen**: Is van toepassing op Android 7.0 en hoger waarvoor het werkprofiel is ingeschakeld. Kies **Vereisen** om een beleid voor wachtwoordcodes in te voeren dat alleen van toepassing is op de apps in het werkprofiel. De eindgebruiker kan standaard de twee afzonderlijk gedefinieerde pincodes gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee. **Niet geconfigureerd**: staat de gebruiker toe om werk-apps te gebruiken, zonder een wachtwoord in te voeren.
- **Minimale wachtwoordlengte**: Geef het minimale aantal cijfers of tekens op waaruit het wachtwoord van de gebruiker moet bestaan, van **4**-**16**.
- **Maximum aantal minuten van inactiviteit voordat het werkprofiel wordt vergrendeld**: Selecteer de hoeveelheid tijd voordat het werkprofiel wordt vergrendeld. De gebruiker moet vervolgens zijn referenties invoeren om weer toegang te krijgen.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Geef op hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het werkprofiel wordt gewist van het apparaat.
- **Wachtwoordverlooptijd (dagen)** : Voer het aantal dagen in totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
- **Vereist wachtwoordtype**: Selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Complex numeriek**: Herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: Voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: Kies **Blokkeren** als u wilt voorkomen dat eindgebruikers de vingerafdrukscanner van het apparaat gebruiken om het apparaat te ontgrendelen. **Niet geconfigureerd**: gebruikers kunnen apparaten ontgrendelen met een vingerafdruk in het werkprofiel.
- **Smart Lock en andere trustagenten**: Kies **Blokkeren** als u wilt voorkomen dat Smart Lock of andere trustagenten instellingen voor het vergrendelingsscherm van compatibele apparaten aanpassen. Met deze functie, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

### <a name="device-password"></a>Wachtwoord van apparaat

Deze wachtwoordinstellingen zijn van toepassing op persoonlijke profielen op apparaten die gebruikmaken van een werkprofiel.

- **Minimale wachtwoordlengte**: Geef het minimale aantal cijfers of tekens op waaruit het wachtwoord van de gebruiker moet bestaan, van **4**-**14**.
- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: Selecteer de hoeveelheid tijd voordat een inactief apparaat automatisch wordt vergrendeld
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Geef op hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het werkprofiel wordt gewist van het apparaat.
- **Wachtwoordverlooptijd (dagen)** : Voer het aantal dagen in totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**)
- **Vereist wachtwoordtype**: Selecteer het type wachtwoord dat moet worden ingesteld op het apparaat. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Vereist**
  - **Ten minste numeriek**
  - **Complex numeriek**: Herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: Voer het aantal nieuwe wachtwoorden in dat moet worden gebruikt voordat een oud wachtwoord opnieuw kan worden gebruikt (van **1**-**24**).
- **Ontgrendelen met vingerafdruk**: Kies **Blokkeren** als u wilt voorkomen dat een eindgebruiker de vingerafdrukscanner van het apparaat gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd**: staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.
- **Smart Lock en andere trustagenten**: Kies **Blokkeren** als u wilt voorkomen dat Smart Lock of andere trustagenten instellingen voor het vergrendelingsscherm van compatibele apparaten aanpassen. Met deze functie, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

### <a name="system-security"></a>Systeembeveiliging

- **Bedreigingsscan voor apps**: Met **Vereisen** dwingt u af dat de instelling **Apps controleren** wordt ingeschakeld voor werk- en persoonlijke profielen.

   > [!Note]
   > Deze instelling werkt alleen voor apparaten met Android 8 (Oreo) en later.

- **Voorkomen dat apps uit onbekende bronnen worden geïnstalleerd in het persoonlijk profiel**: op apparaten met een Android Enterprise-werkprofiel kunnen geen apps worden geïnstalleerd uit andere bronnen dan de Play Store. Werkprofielapparaten zijn bedoeld voor twee profielen:

  - Een werkprofiel dat wordt beheerd met MDM.
  - Een persoonlijk profiel dat is geïsoleerd van MDM-beheer.

  Met deze instelling krijgen beheerders meer controle over de installatie van apps vanuit onbekende bronnen. **Niet geconfigureerd** (standaard): staat app-installaties toe die afkomstig zijn van onbekende bronnen in het persoonlijke profiel. **Blokkeren** voorkomt app-installaties in het persoonlijke profiel vanuit andere bronnen dan de Play Store.

### <a name="connectivity"></a>Connectiviteit

- **Permanente VPN**: Kies **Inschakelen** als u wilt instellen dat een VPN-client automatisch verbinding maakt en opnieuw verbinding maakt met het VPN. AlwaysOn VPN-verbindingen blijven verbonden of maken direct verbinding wanneer gebruikers hun apparaat vergrendelen, het apparaat opnieuw wordt opgestart of het draadloze netwerk wordt gewijzigd. 

  Kies **Niet geconfigureerd** om AlwaysOn VPN voor alle VPN-clients uit te schakelen.

  > [!IMPORTANT]
  > Implementeer slechts één AlwaysOn VPN-beleid per apparaat. Het implementeren van meerdere AlwaysOn VPN-beleidsregels op één apparaat wordt niet ondersteund.

- **VPN-client**: Kies een VPN-client die ondersteuning biedt voor AlwaysOn. Uw opties zijn:
  - Cisco AnyConnect
  - F5-toegang
  - Palo Alto Networks GlobalProtect
  - Pulse Secure
  - Aangepast
    - **Pakket-id**: Voer de pakket-id in van de app in Google Play. Als de URL voor de app in Google Play bijvoorbeeld `https://play.google.com/store/details?id=com.contosovpn.android.prod` is, is de pakket-id `com.contosovpn.android.prod`.

  > [!IMPORTANT]
  > - De VPN-client die u kiest moet op het apparaat worden geïnstalleerd en moet VPN per app in werkprofielen ondersteunen. Anders treedt er een fout op. 
  > - U dient de VPN-client-app goed te keuren in de **Beheerde Google Play Store**, de app te synchroniseren naar Intune en de app te implementeren op het apparaat. Nadat u dit hebt gedaan, is de app geïnstalleerd in het werkprofiel van de gebruiker.
  > - Er zijn mogelijk bekende problemen bij het gebruik van VPN per app met F5 Access voor Android 3.0.4. Zie [Releaseopmerkingen voor F5 Access voor Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) voor meer informatie.

- **Vergrendelingsmodus**: Kies **Inschakelen** als u wilt afdwingen dat al het verkeer de VPN-tunnel gebruikt. Als er geen VPN-verbinding is ingesteld, heeft het apparaat geen toegang tot het netwerk.

  Kies **Niet geconfigureerd** om toe te staan dat verkeer via de VPN-tunnel of via het mobiele netwerk gaat.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kioskprofielen maken voor toegewezen apparaten met [Android](device-restrictions-android.md#kiosk) en [Windows 10](kiosk-settings.md).

## <a name="see-also"></a>Zie tevens

[Apparaten met Android Enterprise configureren en problemen met deze apparaten oplossen in Microsoft Intune](https://support.microsoft.com/help/4476974)
