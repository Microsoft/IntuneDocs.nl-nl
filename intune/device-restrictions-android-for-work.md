---
title: Apparaatinstellingen voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Op apparaten met Android Enterprise of Android for Work kunt u beperkingen op het apparaat instellen, zoals voor kopiëren en plakken, het weergeven van meldingen, app-machtigingen, het delen van gegevens, de wachtwoordlengte, mislukte aanmeldpogingen, het gebruik van vingerafdrukken om te ontgrendelen, het opnieuw gebruiken van wachtwoorden en het delen van zakelijke contactpersonen via Bluetooth. Apparaten configureren als een kiosk voor het uitvoeren van een of meer apps.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure, seodec18
ms.openlocfilehash: 91f338a768ef67106a9b65de759dd74da2902138
ms.sourcegitcommit: 06f62ae989da6c60bac4a52ccd41b429f7367d8c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/26/2019
ms.locfileid: "55072555"
---
# <a name="android-enterprise-device-settings-to-allow-or-restrict-features-using-intune"></a>Met Android Enterprise-apparaatinstellingen kunt u functies toestaan of beperken met behulp van Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u kunt beheren op Android Enterprise-apparaten. Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, apps uit te voeren in de kioskmodus, beveiliging te beheren en nog veel meer.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](device-restrictions-configure.md).

## <a name="device-owner-only"></a>Alleen eigenaar van het apparaat

### <a name="general-settings"></a>Algemene instellingen

- **Schermopname**: Kies **Blokkeren** als u wilt voorkomen dat schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. U voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben. **Niet geconfigureerd**: stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding.
- **Camera**: Kies **Blokkeren** als u de toegang tot de camera op het apparaat wilt blokkeren. **Niet vereist**: staat toegang tot de camera van het apparaat toe.
- **Standaardmachtigingsbeleid**: Met deze instelling bepaalt u het standaardmachtigingsbeleid voor aanvragen betreffende runtime-machtigingen. De mogelijke waarden zijn:
  - **Standaardwaarde apparaat**: De standaardinstelling van het apparaat wordt gebruikt.
  - **Vragen**: De gebruiker wordt gevraagd de machtiging goed te keuren.
  - **Automatisch verlenen**: Machtigingen worden automatisch verleend.
  - **Automatisch weigeren**: Machtigingen worden automatisch geweigerd.
- **Wijzigingen in datum en tijd**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers handmatig de datum en tijd instellen. **Niet geconfigureerd**: staat gebruikers toe om de datum en tijd in te stellen op het apparaat.
- **Volumewijzigingen**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers het volume van het apparaat wijzigen. **Niet geconfigureerd**: staat gebruik van de volume-instellingen toe op het apparaat.
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
- **E-mailadressen resetbeveiliging fabrieksinstellingen**: Kies **e-mailadressen van een Google-account**. Voer de e-mailadressen in van apparaatbeheerders die het apparaat kunnen ontgrendelen nadat dit is gewist. Plaats een puntkomma tussen de e-mailadressen, zoals `admin1@gmail.com;admin2@gmail.com`. Als u geen e-mailadres invoert, kan iedereen het apparaat ontgrendelen nadat de fabrieksinstellingen zijn hersteld.
- **Netwerknooduitgang**: Kies **Inschakelen** als gebruikers de functie Netwerknooduitgang mogen inschakelen. Als er geen netwerkverbinding tot stand wordt gebracht bij het opstarten van het apparaat, vraagt de functie of er tijdelijk verbinding moet worden gemaakt met een netwerk en of het apparaatbeleid moet worden vernieuwd. Wanneer het beleid is toegepast, wordt het tijdelijke netwerk vergeten en gaat het apparaat verder met opstarten. Deze functie maakt in de volgende gevallen verbinding tussen een apparaat en netwerk:
  - Er bevindt zich geen geschikt netwerk in het laatste beleid.
  - Het apparaat wordt opgestart naar een app in de modus vergrendelingstaak.
  - De gebruiker heeft geen toegang tot de apparaatinstellingen.

  **Niet geconfigureerd**: hiermee wordt voorkomen dat gebruikers de functie Netwerknooduitgang inschakelen op het apparaat.

- **Installatie vanuit onbekende bronnen toestaan**: Kies **Toestaan**, zodat gebruikers de **onbekende bronnen** kunnen inschakelen. Met deze instelling kunnen apps worden geïnstalleerd vanuit onbekende bronnen. **Niet geconfigureerd**: voorkomt dat gebruikers **Onbekende bronnen** kunnen inschakelen.
- **Systeemupdate**: Kies een optie om te bepalen hoe het apparaat omgaat met draadloze updates:
  - **Standaardwaarde apparaat**: De standaardinstelling van het apparaat wordt gebruikt.
  - **Automatisch**: Updates worden automatisch geïnstalleerd zonder interactie van de gebruiker. Wanneer u dit beleid instelt, worden alle eventuele updates die nog niet zijn uitgevoerd, meteen geïnstalleerd.
  - **Uitgesteld**: Updates worden 30 dagen uitgesteld. Na 30 dagen wordt de gebruiker door Android gevraagd om de update te installeren. Het is mogelijk dat apparaatfabrikanten of leveranciers het uitstellen van belangrijke beveiligingsupdates voorkomen (uitzonderen). Voor een uitzonderingsupdate wordt een systeembericht weergegeven op het apparaat. 
  - **Onderhoudsvenster**: Hiermee worden updates automatisch geïnstalleerd tijdens een dagelijkse onderhoudsperiode die u in Intune instelt. Er wordt gedurende 30 dagen geprobeerd om de updates te installeren. Dit kan mislukken als er te weinig ruimte of onvoldoende accuvermogen is. Na 30 dagen vraagt Android de gebruiker om te installeren. Deze periode wordt is ook gebruikt om updates voor Play-apps te installeren. Gebruik deze optie voor specifieke apparaten, zoals kiosken, omdat kiosken met maar één app op de voorgrond kunnen worden bijgewerkt.
- **App wordt automatisch bijgewerkt**: Kies deze optie wanneer updates automatisch worden geïnstalleerd. Uw opties zijn:
  - **Niet geconfigureerd**
  - **Gebruiker kiezen**
  - **Nooit**
  - **Alleen Wi-Fi**
  - **Altijd**

- **Meldingsvensters**: Als de optie **Uitschakelen** is ingesteld, worden venstermeldingen, inclusief pop-ups, inkomende aanroepen, uitgaande aanroepen, systeemwaarschuwingen en systeemfouten niet weergegeven op het apparaat. Als de optie **Niet geconfigureerd** is ingesteld, wordt de standaardinstelling van het besturingssysteem gebruikt, die mogelijk bepaalt dat meldingen worden weergegeven.
- **Hints voor eerste gebruik overslaan**: Kies **Inschakelen** als u suggesties van apps wilt verbergen of overslaan voor het doorlopen van zelfstudies of voor het lezen van inleidende hints wanneer de app wordt gestart. Als de optie **Niet geconfigureerd** is ingesteld, wordt de standaardinstelling van het besturingssysteem gebruikt, die mogelijk bepaalt dat suggesties worden weergegeven wanneer de app wordt gestart.


### <a name="system-security-settings"></a>Systeembeveiligingsinstellingen

- **Bedreigingsscan voor apps**: Met **Vereisen** dwingt u af dat de instelling **Apps controleren** wordt ingeschakeld voor werk- en persoonlijke profielen.

### <a name="kiosk-settings"></a>Kioskinstellingen

U kunt een apparaat configureren voor het uitvoeren van één app of een aantal apps. Wanneer een apparaat in de kioskmodus staat, zijn alleen de apps beschikbaar die u expliciet hebt toegevoegd. Deze instellingen zijn van toepassing op toegewezen Android-apparaten, niet op volledig beheerde Android-apparaten.

**Kioskmodus**: Kies dit als op het apparaat een of meer apps moeten worden uitgevoerd.

- **Kiosk voor één app**: Gebruikers hebben slechts toegang tot één app op het apparaat. Wanneer het apparaat wordt gestart, wordt alleen de specifieke app gestart. Gebruikers kunnen geen nieuwe apps openen of de actieve app wijzigen.

  **Stappen**
  1. Kies **Beheerde app selecteren** en selecteer de beheerde Google Play-app in de lijst. 

      Als er geen apps worden vermeld, [voegt u enkele Android-apps toe](apps-add-android-for-work.md) aan het apparaat. Zorg ervoor dat u [de app toewijst aan de apparaatgroep die is gemaakt voor uw kioskapparaten](apps-deploy.md).

  2. Kies **OK** > **OK** om de app toe te voegen.

- **Kiosk voor meerdere apps**: Gebruikers hebben toegang tot een beperkte set apps op het apparaat. Wanneer het apparaat wordt gestart, worden alleen de toegevoegde apps gestart. U kunt ook enkele webkoppelingen toevoegen die gebruikers kunnen openen. Wanneer het beleid wordt toegepast, zien gebruikers pictogrammen voor de toegestane apps op het startscherm.

  > [BELANGRIJK] Voor apparaten in de modus Kios voor meerdere apps **moet** de [app Managed Home Screen](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) van Google Play zijn:
  >   - [Toegevoegd als een client-app](apps-add-android-for-work.md) in Intune
  >   - [Toegewezen aan de apparaatgroep](apps-deploy.md) die is gemaakt voor uw kioskapparaten.
  > 
  > De app **Managed Home Screen** hoeft niet te zijn opgenomen in het configuratieprofiel, maar moet wel worden toegevoegd als een client-app. Wanneer de app **Managed Home Screen** wordt toegevoegd als een client-app, worden andere apps die u aan het configuratieprofiel toevoegt, weergegeven als pictogrammen in de app **Managed Home Screen**. 

  - Kies **Toevoegen** en selecteer uw apps in de lijst.

    Als de app **Managed Home Screen** niet wordt vermeld, [voegt u deze toe vanuit Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise). Zorg ervoor dat u [de app toewijst](apps-deploy.md) aan de apparaatgroep die is gemaakt voor uw kioskapparaten.

    U kunt ook andere [Android-apps](apps-add-android-for-work.md) toevoegen aan het apparaat, evenals [web-apps](web-app.md) die zijn gemaakt door uw organisatie. Zorg ervoor dat u [de app toewijst aan de apparaatgroep die is gemaakt voor uw kioskapparaten](apps-deploy.md).

  - **Virtuele startknop**: Kies **Inschakelen** om een startknop weer te geven op het kioskapparaat. Als deze knop wordt geselecteerd, gaan gebruikers terug naar het startscherm van het apparaat, zodat ze eenvoudig kunnen schakelen tussen apps. Op sommige Android-apparaten moeten gebruikers misschien omhoog vegen op het scherm om de startknop weer te geven. **Uitschakelen**: er wordt geen startknop weergegeven, wat betekent dat gebruikers de knop Terug moeten gebruiken om te schakelen tussen apps.
  - **Kioskmodus verlaten**: Kies **Inschakelen** om beheerders toestemming te geven de kioskmodus tijdelijk te onderbreken om het apparaat bij te werken. Om deze functie te gebruiken, moet de beheerder het volgende doen: 
  
    1. Doorgaan met het selecteren van de knop Terug totdat de knop Kiosk verlaten wordt weergegeven. 
    2. De knop selecteren en de pincode voor het **verlaten van de kioskmodus** invoeren.
    3. Nadat de wijzigingen zijn aangebracht, de app **Managed Home Screen** selecteren. Met deze stap wordt het apparaat weer vergrendeld in de kioskmodus voor gebruik van meerdere apps. 
    
    **Uitschakelen**: hiermee voorkomt u dat de kioskmodus kan worden onderbroken. Als de beheerder de knop Terug blijft selecteren en vervolgens de knop Kiosk verlaten selecteert, verschijnt er een bericht dat er een wachtwoordcode moet worden ingevoerd.
    
    - **Code voor verlaten kioskmodus**: Voer een 4-6-cijferige numerieke pincode in. De beheerder gebruikt deze pincode om de kioskmodus tijdelijk te onderbreken.
 
  - **Achtergrond voor aangepaste URL instellen**: Voer een URL in voor het aanpassen van het achtergrondscherm op het kioskapparaat.

### <a name="device-password-settings"></a>Instellingen voor apparaatwachtwoord

- **Keyguard**: Kies **Uitschakelen** als u wilt voorkomen dat de functie voor het vergrendelen van het scherm Keyguard op het apparaat wordt gebruikt. **Niet geconfigureerd**: staat de gebruiker toe de Keyguard-functies te gebruiken.
- **Keyguard-functies uitgeschakeld**: Kies, wanneer keyguard is ingeschakeld op het apparaat, welke functies u wilt uitschakelen. Wanneer bijvoorbeeld de optie **Veilige camera** is geselecteerd, wordt de functie van de camera op het apparaat is uitgeschakeld. Alle functies die niet zijn geselecteerd, zijn op het apparaat ingeschakeld.
- **Vereist wachtwoordtype**: Bepaal welk type wachtwoord wordt vereist voor het apparaat. Uw opties zijn:
  - **Ten minste numeriek**
  - **Complex numeriek**: Herhaalde of opeenvolgende cijfers, zoals '1111' of '1234', zijn niet toegestaan.
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Minimale wachtwoordlengte**: Voer de minimumlengte van het wachtwoord in dat een gebruiker moet opgeven (tussen 4 en 16 tekens).
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Geef het aantal mislukte aanmeldingen op dat is toegestaan voordat het apparaat wordt gewist (tussen 1 en 11).

### <a name="power-settings"></a>Energie-instellingen

- **Tijd tot het scherm wordt vergrendeld**: Stel in na hoeveel niet-actieve tijd het apparaat wordt vergrendeld.
- **Scherm aan terwijl het apparaat is aangesloten**: Kies bij welke energiebronnen het scherm aan blijft wanneer het apparaat is aangesloten.

### <a name="users-and-accounts-settings"></a>Gebruikers- en accountinstellingen

- **Nieuwe gebruikers toevoegen**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers nieuwe gebruikers toevoegen. Elke gebruiker heeft een persoonlijke ruimte op het apparaat voor aangepaste beginschermen, accounts, apps en instellingen. **Niet geconfigureerd**: staat gebruikers toe om andere gebruikers toe te voegen aan het apparaat.
- **Gebruiker verwijderen**: Selecteer **Blokkeren** om te voorkomen dat gebruikers andere gebruikers verwijderen. **Niet geconfigureerd**: staat gebruikers toe om andere gebruikers te verwijderen van het apparaat.
- **Accountwijzigingen**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers accounts wijzigen. **Niet geconfigureerd**: staat gebruikers toe om gebruikersaccounts op het apparaat bij te werken.

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
  >  - De VPN-client die u kiest moet op het apparaat worden geïnstalleerd en moet VPN per app in werkprofielen ondersteunen. Anders treedt er een fout op. 
  >  - U dient de VPN-client-app goed te keuren in de **Beheerde Google Play Store**, de app te synchroniseren naar Intune en de app te implementeren op het apparaat. Nadat u dit hebt gedaan, is de app geïnstalleerd in het werkprofiel van de gebruiker.
  >  - Er zijn mogelijk bekende problemen bij het gebruik van VPN per app met F5 Access voor Android 3.0.4. Zie [Releaseopmerkingen voor F5 Access voor Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) voor meer informatie.

- **Vergrendelingsmodus**: Kies **Inschakelen** als u wilt afdwingen dat al het verkeer de VPN-tunnel gebruikt. Als er geen VPN-verbinding is ingesteld, heeft het apparaat geen toegang tot het netwerk.

  Kies **Niet geconfigureerd** om toe te staan dat verkeer via de VPN-tunnel of via het mobiele netwerk gaat.

## <a name="work-profile-only"></a>Alleen werkprofiel 

### <a name="work-profile-settings"></a>Werkprofielinstellingen

#### <a name="general"></a>Algemeen

- **Kopiëren en plakken tussen werkprofielen en persoonlijke profielen**: Kies **Blokkeren** om kopiëren en plakken te voorkomen tussen werkprofielen en persoonlijke apps. **Niet geconfigureerd**: staat gebruikers toe om gegevens met behulp van kopiëren en plakken te delen met apps in het persoonlijke profiel. 
- **Gegevens delen tussen werkprofielen en persoonlijke profielen**: Kies of delen mogelijk is tussen apps in het werkprofiel en apps in het persoonlijke profiel. Met deze instelling kunt u bijvoorbeeld deelacties binnen toepassingen bepalen, zoals de optie **Delen…** in de Chrome-browser-app. Deze instelling geldt niet voor kopiëren en plakken op het klembord. Uw opties voor delen:
  - **Delen buiten grenzen toestaan**: Dit is de standaardinstelling voor het delen van gegevens van het apparaat. Deze instelling is afhankelijk van de Android-versie. Delen van het persoonlijke profiel naar het werkprofiel is standaard toegestaan. Delen van het werkprofiel naar het persoonlijke profiel is standaard geblokkeerd. Met deze instelling wordt voorkomen dat er gegevens worden gedeeld van het werkprofiel met het persoonlijke profiel. Google blokkeert niet delen van het persoonlijke profiel naar het werkprofiel op apparaten met versie 6.0 of hoger.
  - **Met apps in het werkprofiel kunnen aanvragen voor delen van het persoonlijke profiel worden verwerkt**: Hiermee wordt de ingebouwde Android-functie ingeschakeld waarmee het delen van het persoonlijke profiel naar het werkprofiel is toegestaan. Wanneer dit is ingeschakeld, kan een deelverzoek van een app in het persoonlijke profiel worden gedeeld met apps in het werkprofiel. Dit is de standaardinstelling voor Android-apparaten met een oudere versie dan 6.0.
  - **Standaardbeperkingen voor delen**: Biedt de mogelijkheid om in beide richtingen buiten de grenzen van het werkprofiel te delen. Wanneer u deze instelling selecteert, kunnen apps met het werkprofiel gegevens delen met apps in het persoonlijke profiel die geen badge hebben. Met deze instelling kunnen beheerde apps in het werkprofiel gegevens delen met apps aan de onbeheerde zijde van het apparaat. Gebruik deze instelling daarom zorgvuldig.

- **Werkprofielmeldingen terwijl het apparaat is vergrendeld**: Hiermee kunt u bepalen of de apps in het werkprofiel gegevens in meldingen kunnen weergeven wanneer het apparaat is vergrendeld. **Blokkeren**: de gegevens worden niet weergegeven. **Niet geconfigureerd**: de gegevens worden weergegeven.
- **Standaardapp-machtigingen**: Hiermee stelt u het standaardmachtigingsbeleid in voor alle apps in het werkprofiel. Vanaf Android 6 wordt de gebruiker gevraagd bepaalde vereiste machtigingen aan apps toe te kennen wanneer de app wordt gestart. Met deze beleidsinstelling kunt u in het werkprofiel bepalen of gebruikers wordt gevraagd om machtigingen toe te kennen voor alle apps in het werkprofiel. U kunt bijvoorbeeld een app aan het werkprofiel toewijzen waarvoor toegang tot de locatie is vereist. Normaal gesproken wordt de gebruiker gevraagd of hij de app toegang tot de locatie wil geven. Gebruik dit beleid om automatisch machtigingen te verlenen zonder om bevestiging te vragen, automatisch machtigingen te weigeren zonder om bevestiging te vragen, of om de eindgebruiker te laten beslissen. U kunt kiezen uit:
  - **Standaardwaarde apparaat**
  - **Vragen**
  - **Automatisch verlenen**
  - **Automatisch weigeren**

  U kunt ook een app-configuratiebeleid gebruiken om machtigingen voor afzonderlijke apps te verlenen (**Client-apps** > **App-configuratiebeleid**).

- **Accounts toevoegen en verwijderen**: Kies **Blokkeren** om te voorkomen dat eindgebruikers handmatig accounts in het werkprofiel kunnen toevoegen of uit het werkprofiel kunnen verwijderen. Als u de Gmail-app bijvoorbeeld implementeert in een Android-werkprofiel, kunt u verhinderen dat eindgebruikers accounts toevoegen aan of verwijderen uit dit werkprofiel. **Niet geconfigureerd**: hiermee wordt toegestaan dat accounts worden toegevoegd aan het werkprofiel.  

- **Contactpersoon delen via Bluetooth**: Hiermee krijgt u toegang tot werkcontactpersonen op een ander apparaat, zoals een auto, dat via Bluetooth is gekoppeld. Standaard is deze instelling niet geconfigureerd en worden contactpersonen met een werkprofiel niet weergegeven. Selecteer **Inschakelen** om het delen hiervan toe te staan en contactpersonen met een werkprofiel weer te geven. Deze instelling is van toepassing op Android-apparaten met een werkprofiel met Android OS v6.0 en hoger. Door deze instelling in te schakelen, kunnen bepaalde Bluetooth-apparaten werkcontactpersonen cachen bij de eerste verbinding. Als u dit beleid uitschakelt na een eerste synchronisatie, zijn de werkcontactpersonen van een Bluetooth-apparaat niet meteen verwijderd.

- **Schermopname**: Kies **Blokkeren** als u wilt voorkomen dat in het werkprofiel schermopnamen of schermafbeeldingen worden gemaakt met het apparaat. U voorkomt ook dat de inhoud wordt weergegeven op weergaveapparaten die geen beveiligde video-uitvoer hebben. **Niet geconfigureerd**: schermafbeeldingen zijn toegestaan.

- **Beller-id van zakelijk contactpersoon weergeven in persoonlijk profiel**: Indien ingeschakeld (**niet-geconfigureerd**), worden de details van de beller die een zakelijke contactpersoon is, weergegeven in het persoonlijke profiel. Indien ingesteld op **Blokkeren** wordt het nummer van deze zakelijke contactpersoon niet weergegeven in het persoonlijke profiel. Van toepassing op Android OS v6.0 en nieuwere versies.

- **Werkcontacten zoeken in persoonlijk profiel**: Kies **Blokkeren** als u wilt voorkomen dat gebruikers in apps in het persoonlijke profiel zoeken naar werkcontacten. **Niet geconfigureerd**: zoeken naar werkcontacten in het persoonlijke profiel is toegestaan.

- **Camera**: Kies **Blokkeren** als u de toegang tot de camera op het apparaat in het werkprofiel wilt blokkeren. De camera aan de persoonlijke zijde wordt niet beïnvloed door de instelling. **Niet geconfigureerd** staat de toegang tot de camera in het werkprofiel toe.

#### <a name="work-profile-password"></a>Werkprofielwachtwoord

- **Werkprofielwachtwoord vereisen**: Is van toepassing op Android 7.0 en hoger waarvoor het werkprofiel is ingeschakeld. Kies **Vereisen** om een beleid voor wachtwoordcodes in te voeren dat alleen van toepassing is op de apps in het werkprofiel. De eindgebruiker kan standaard de twee afzonderlijk gedefinieerde pincodes gebruiken, maar kan er ook voor kiezen om de twee gedefinieerde pincodes te combineren in de sterkste van de twee. **Niet geconfigureerd**: staat de gebruiker toe om werk-apps te gebruiken, zonder een wachtwoord in te voeren.
- **Minimale wachtwoordlengte**: Geef het minimale aantal cijfers of tekens op waaruit het wachtwoord van de gebruiker moet bestaan, van **4**-**16**.
- **Maximum aantal minuten van inactiviteit voordat het werkprofiel wordt vergrendeld**: Selecteer de hoeveelheid tijd voordat het werkprofiel wordt vergrendeld. De gebruiker moet vervolgens zijn referenties invoeren om weer toegang te krijgen.
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Geef op hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het werkprofiel wordt gewist van het apparaat.
- **Wachtwoordverlooptijd (dagen)**: Voer het aantal dagen in totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**).
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
- **Smart Lock en andere trustagenten**: Kies **Blokkeren** als u wilt voorkomen dat Smart Lock of andere trustagenten instellingen voor het vergrendelingsscherm van compatibele apparaten aanpassen. Met deze functie, ook wel een vertrouwensagent genoemd, kunt u het wachtwoord voor het vergrendelingsscherm op het apparaat uitschakelen of overslaan als het apparaat zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

### <a name="device-password"></a>Wachtwoord van apparaat

Deze wachtwoordinstellingen zijn van toepassing op persoonlijke profielen op apparaten die gebruikmaken van een werkprofiel.

- **Minimale wachtwoordlengte**: Geef het minimale aantal cijfers of tekens op waaruit het wachtwoord van de gebruiker moet bestaan, van **4**-**14**.
- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: Selecteer de hoeveelheid tijd voordat een inactief apparaat automatisch wordt vergrendeld
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: Geef op hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat alle gegevens worden gewist van het apparaat
- **Wachtwoordverlooptijd (dagen)**: Voer het aantal dagen in totdat het wachtwoord van de eindgebruiker moet worden gewijzigd (van **1**-**255**)
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
- **Smart Lock en andere trustagenten**: Kies **Blokkeren** als u wilt voorkomen dat Smart Lock of andere trustagenten instellingen voor het vergrendelingsscherm van compatibele apparaten aanpassen. Met deze functie, ook wel een vertrouwensagent genoemd, kunt u het wachtwoord voor het vergrendelingsscherm op het apparaat uitschakelen of overslaan als het apparaat zich op een vertrouwde locatie bevindt. Hiermee kan bijvoorbeeld het wachtwoord van het werkprofiel worden overgeslagen wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. Gebruik deze instelling om te voorkomen dat gebruikers Smart Lock configureren.

### <a name="system-security"></a>Systeembeveiliging

- **Bedreigingsscan voor apps**: Met **Vereisen** dwingt u af dat de instelling **Apps controleren** wordt ingeschakeld voor werk- en persoonlijke profielen.

   > [!Note]
   > Deze instelling werkt alleen voor apparaten met Android O en later.

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
  >  - De VPN-client die u kiest moet op het apparaat worden geïnstalleerd en moet VPN per app in werkprofielen ondersteunen. Anders treedt er een fout op. 
  >  - U dient de VPN-client-app goed te keuren in de **Beheerde Google Play Store**, de app te synchroniseren naar Intune en de app te implementeren op het apparaat. Nadat u dit hebt gedaan, is de app geïnstalleerd in het werkprofiel van de gebruiker.
  >  - Er zijn mogelijk bekende problemen bij het gebruik van VPN per app met F5 Access voor Android 3.0.4. Zie [Releaseopmerkingen voor F5 Access voor Android 3.0.4](https://support.f5.com/kb/en-us/products/big-ip_apm/releasenotes/related/relnote-f5access-android-3-0-4.html#relnotes_known_issues_f5_access_android) voor meer informatie.

- **Vergrendelingsmodus**: Kies **Inschakelen** als u wilt afdwingen dat al het verkeer de VPN-tunnel gebruikt. Als er geen VPN-verbinding is ingesteld, heeft het apparaat geen toegang tot het netwerk.

  Kies **Niet geconfigureerd** om toe te staan dat verkeer via de VPN-tunnel of via het mobiele netwerk gaat.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kioskprofielen maken voor apparaten met [Android](device-restrictions-android.md#kiosk) en [Windows 10](kiosk-settings.md).
