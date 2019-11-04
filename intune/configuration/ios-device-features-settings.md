---
title: Instellingen van apparaatfuncties voor iOS in Microsoft Intune - Azure | Microsoft Docs
description: Alle instellingen bekijken voor het configureren van iOS-apparaten, de indeling van het startscherm, app-meldingen, gedeelde apparaten, eenmalige aanmelding en het filteren van webinhoud in Microsoft Intune. Gebruik deze instellingen in een apparaatconfiguratieprofiel om iOS-apparaten te configureren voor het gebruik van deze Apple-functies in uw organisatie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/28/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e3e0ea523d71ff036f1f23c9436c65e105328d8b
ms.sourcegitcommit: 807ab3e35f4d9ffa18655410b7d61e5e772ab348
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/30/2019
ms.locfileid: "73057646"
---
# <a name="ios-and-ipados-device-settings-to-use-common-ios-features-in-intune"></a>iOS- en iPadOS-apparaatinstellingen voor het gebruik van algemene iOS-functies in Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune bevat enkele ingebouwde instellingen, zodat iOS-gebruikers verschillende functies van Apple op hun apparaten kunnen gebruiken. Beheerders kunnen bepalen hoe iOS-gebruikers AirPrint-printers gebruiken, apps en mappen toevoegen aan de dock en pagina's op het startscherm, app-meldingen weergeven, details van inventaristags weergeven op het vergrendelingsscherm, verificatie met eenmalige aanmelding gebruiken en gebruikers met certificaten verifiëren.

Gebruik deze functies om iOS-apparaten te beheren als onderdeel van uw Mobile Device Management-oplossing (MDM).

Dit artikel beschrijft deze instellingen en wat elke instelling doet. Ga voor meer informatie over deze functies naar [instellingen voor Ios-of macOS-apparaten toevoegen](../device-features-configure.md).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een iOS-apparaatconfiguratieprofiel](../device-features-configure.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvings typen, waarbij sommige instellingen van toepassing zijn op alle inschrijvings opties. Zie [IOS-inschrijving](../ios-enroll.md)voor meer informatie over de verschillende inschrijvings typen.

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

> [!NOTE]
> Vergeet niet om alle printers aan hetzelfde profiel toe te voegen. Apple voor komt dat meerdere afdruk profielen worden gericht op hetzelfde apparaat.

- **IP-adres**: voer het IPv4- of IPv6-adres van de printer in. Als u hostnamen gebruikt om printers te identificeren, krijgt u het IP-adres door de printer in de terminal te pingen. In Haal het IP-adres en het pad op (in dit artikel) vindt u meer informatie.
- **Pad**: het pad is doorgaans `ipp/print` voor printers in uw netwerk. In Haal het IP-adres en het pad op (in dit artikel) vindt u meer informatie.
- **Poort**: voer de luisterpoort van de AirPrint-bestemming in. Als u deze eigenschap leeg laat, maakt AirPrint gebruik van de standaardpoort. Beschikbaar in iOS 11.0 en hoger.
- **TLS**: kies **Inschakelen** voor het beveiligen van AirPrint-verbindingen met Transport Layer Security (TLS). Beschikbaar in iOS 11.0 en hoger.

Als u printer servers wilt toevoegen, kunt u het volgende doen:

- Met **Toevoegen** wordt de AirPrint-server aan de lijst toegevoegd. Er kunnen veel afdruk servers worden toegevoegd.
- Een door komma's gescheiden bestand (.csv) met deze informatie **importeren**. U kunt ook **exporteren** om een lijst te maken met de afdruk servers die u hebt toegevoegd.

### <a name="get-server-ip-address-resource-path-and-port"></a>IP-adres van de server, bronpad en poort ophalen

Om AirPrinter-servers toe te voegen, hebt u het IP-adres van de printer, het bronpad en de poort nodig. De volgende stappen laten zien hoe u aan deze informatie komt.

1. Open op een Mac die verbonden is met hetzelfde lokale netwerk (subnet) als de AirPrint-printers de **Terminal** (via **/Programma's/Hulpprogramma's**).
2. Typ in de terminal `ippfind` en selecteer Enter.

    Noteer de printergegevens. Er wordt bijvoorbeeld iets in de trant van `ipp://myprinter.local.:631/ipp/port1` geretourneerd. Het eerste deel is de naam van de printer. Het laatste deel (`ipp/port1`) is het bronpad.

3. Typ in de terminal `ping myprinter.local` en selecteer Enter.

   Noteer het IP-adres. Er wordt bijvoorbeeld iets in de trant van `PING myprinter.local (10.50.25.21)` geretourneerd.

4. Gebruik de waarden van het IP-adres en het bronpad. In dit voorbeeld is het IP-adres `10.50.25.21` en het bronpad `/ipp/port1`.

## <a name="home-screen-layout"></a>Indeling van het startscherm

Deze functie is van toepassing op:

- iOS 9,3 of hoger

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

### <a name="dock"></a>Dock

Gebruik de **Dock**-instellingen om maximaal zes items of mappen aan de dock onder aan in het iOS-scherm toe te voegen. Veel apparaten ondersteunen minder items. IPhone-apparaten ondersteunen bijvoorbeeld maximaal vier items. In dit geval worden alleen de eerste vier items die u hebt toegevoegd op het apparaat weergegeven.

U kunt maximaal **zes** items (combinatie van apps en mappen) voor de apparaatdock toevoegen.

- **Toevoegen**: apps of mappen toevoegen aan de dock op het apparaat.
- **Type**: een **app** of een **map** toevoegen:

  - **App**: kies deze optie om apps aan de dock op het scherm toe te voegen. Voer het volgende in:

    - **App-naam**: Voer een naam voor de app in. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het iOS-apparaat.
    - **App-bundel-id**: geef de bundel-id van de app op. Zie [Bundel-id's voor ingebouwde iOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

  - **Map**: kies deze optie om een map aan de dock op het scherm toe te voegen.

    Apps die u aan een pagina in een map toevoegt, worden gerangschikt van links naar rechts, en in dezelfde volgorde als de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een andere pagina verplaatst.

    - **Mapnaam**: voer de naam van de map in. Deze naam zien gebruikers op hun apparaat.
    - **Lijst met pagina's**: u kunt een pagina **toevoegen** en de volgende eigenschappen invoeren:

      - **Paginanaam**: Voer een naam voor de pagina in. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het iOS-apparaat.
      - **App-naam**: Voer een naam voor de app in. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het iOS-apparaat.
      - **App-bundel-id**: geef de bundel-id van de app op. Zie [Bundel-id's voor ingebouwde iOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

      U kunt maximaal **20** pagina's toevoegen voor de apparaatdock.

> [!NOTE]
> Wanneer u pictogrammen toevoegt met behulp van de Dock-instellingen, zijn de pictogrammen op het startscherm en de pagina's vergrendeld en kunnen deze niet worden verplaatst. Dit is mogelijk inherent aan iOS en de MDM-beleidsregels van Apple.

#### <a name="example"></a>Voorbeeld

In het volgende voorbeeld worden op het dock-scherm alleen de apps Safari, Mail en Aandelen weergegeven. De app Mail is geselecteerd om de eigenschappen ervan weer te geven:

![Voorbeeld van iOS-dockinstellingen](./media/ios-device-features-settings/FfFiUcP.png)

Wanneer u het beleid aan een iPhone toewijst, ziet de dock er ongeveer hetzelfde uit als de volgende afbeelding:

![Voorbeeld van iOS-dockindeling op iPhone](./media/ios-device-features-settings/bAgCe8F.png)

### <a name="pages"></a>Pages

Voeg de pagina's toe die u wilt weergeven op het startscherm en de apps die moeten worden weergegeven op elke pagina. Apps die u aan een pagina toevoegt, worden gerangschikt van links naar rechts, in dezelfde volgorde als de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een andere pagina verplaatst.

> [!TIP]
> U kunt items slepen en neerzetten in elk startscherm en alle paginalijsten om deze te opnieuw te rangschikken.

U kunt maximaal **40** pagina's toevoegen.

- **Lijst met pagina's**: u kunt een pagina **toevoegen** en de volgende eigenschappen invoeren:

  - **Paginanaam**: Voer een naam voor de pagina in. Deze naam wordt ter referentie gebruikt in de Microsoft Azure-portal en wordt *niet* weergegeven op het iOS-apparaat.

  U kunt maximaal **60** items (combinatie van apps en mappen) toevoegen op een apparaat.

  - **Toevoegen**: apps of mappen toevoegen aan een pagina op het apparaat.

    - **Type**: een **app** of een **map** toevoegen:

      - **App**: kies deze optie om apps aan een pagina op het scherm toe te voegen. Voer ook in:

        - **App-naam**: Voer een naam voor de app in. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het iOS-apparaat.
        - **App-bundel-id**: geef de bundel-id van de app op. Zie [Bundel-id's voor ingebouwde iOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

      - **Map**: kies deze optie om een map aan de dock op het scherm toe te voegen.

        Apps die u aan een pagina in een map toevoegt, worden gerangschikt van links naar rechts, en in dezelfde volgorde als de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een andere pagina verplaatst.

        - **Mapnaam**: voer een naam voor de map in. Deze naam zien gebruikers op het apparaat.
        - **Toevoegen**: hiermee worden pagina's aan de map toegevoegd. Voer ook de volgende eigenschappen in:

          - **Paginanaam**: Voer een naam voor de pagina in. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het iOS-apparaat.
          - **App-naam**: Voer een naam voor de app in. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het iOS-apparaat.
          - **App-bundel-id**: geef de bundel-id van de app op. Zie [Bundel-id's voor ingebouwde iOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

#### <a name="example"></a>Voorbeeld

In het volgende voorbeeld wordt een nieuwe pagina met de naam **Contoso** toegevoegd. Op de pagina worden de apps Zoek vrienden en Instellingen weergegeven. De app Instellingen is geselecteerd om de eigenschappen ervan weer te geven:

![Voorbeeld van instellingen voor iOS-startscherm](./media/ios-device-features-settings/Jc2OxyX.png)

Wanneer u het beleid aan een iPhone toewijst, ziet de pagina er ongeveer hetzelfde uit als de volgende afbeelding:

![iOS-apparaat met gewijzigd startscherm](./media/ios-device-features-settings/Bd37PHa.png)

## <a name="app-notifications"></a>App-meldingen

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Toevoegen**: meldingen voor apps toevoegen:

    ![App-melding toevoegen in iOS-profiel in Intune](./media/ios-device-features-settings/ios-macos-app-notifications.png)

  - **App-bundel-id**: geef de **App-bundel-id** op van de app die u wilt toevoegen. Zie [Bundel-id's voor ingebouwde iOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.
  - **App-naam**: voer de naam in van de app die u wilt toevoegen. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het apparaat.
  - **Uitgever**: voer de uitgever in van de app die u toevoegt. Deze naam wordt ter referentie in de Microsoft Azure-portal gebruikt. Deze wordt *niet* weergegeven op het apparaat.
  - **Meldingen**: hiermee kunt u **inschakelen** of **uitschakelen** dat de app meldingen naar het apparaat verzendt.
    - **Weergeven in het meldingencentrum**: als u **Inschakelen** kiest, geeft de app meldingen weer in meldingencentrum van het apparaat. als u **Uitschakelen** kiest, geeft de app geen meldingen weer in meldingencentrum.
    - **Weergeven in het vergrendelingsscherm**: selecteer **Inschakelen** om meldingen van de app weer te geven op het vergrendelingsscherm van de app. als u **Uitschakelen** kiest, worden meldingen van de app niet weergegeven op het vergrendelingsscherm.
    - **Waarschuwingstype**: kies hoe de melding moet worden weergegeven wanneer het apparaat wordt ontgrendeld. Uw opties zijn:
      - **Geen**: er wordt geen melding weergegeven.
      - **Banner**: er wordt kort een banner weergegeven met de melding.
      - **Modaal**: de melding wordt weergegeven en de gebruiker moet deze handmatig sluiten voordat de gebruiker kan doorgaan en het apparaat kan gebruiken.
    - **Badge op app-pictogram**: Selecteer **Inschakelen** om een badge toe te voegen aan het app-pictogram. De badge betekent dat de app een melding heeft verzonden.
    - **Geluiden**: selecteer **Inschakelen** om een geluid af te spelen wanneer een melding wordt afgeleverd.

## <a name="lock-screen-message"></a>Bericht voor vergrendelingsscherm

Deze functie is van toepassing op:

- iOS 9.3 en hoger

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Informatie over de assettag**: voer informatie over de assettag van het apparaat in. Voer bijvoorbeeld `Owned by Contoso Corp` of `Serial Number: {{serialnumber}}` in.

  De tekst die u opgeeft, wordt weergegeven in het aanmeldingsvenster en het vergrendelingsscherm van het apparaat.

- **Voetnoot voor het vergrendelingsscherm**: voer een opmerking in waarmee u het apparaat misschien kunt terugkrijgen als het verloren of gestolen is. U kunt elke gewenste tekst invoeren. Voer bijvoorbeeld iets in zoals `If found, call Contoso at ...`.

  Apparaattokens kunnen ook worden gebruikt om apparaatspecifieke informatie aan deze velden toe te voegen. Als u bijvoorbeeld het serienummer wilt weergeven, voert u `Serial Number: {{serialnumber}}` in. De tekst die in het vergrendelingsscherm wordt weergegeven, is vergelijkbaar met `Serial Number 123456789ABC`. Wanneer u variabelen opgeeft, moet u ervoor zorgen dat u accolades `{{ }}` gebruikt. [App-configuratietokens](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat een lijst met variabelen die kunnen worden gebruikt. U kunt ook `deviceName` of een andere apparaatspecifieke waarde gebruiken.

  > [!NOTE]
  > Variabelen worden niet gevalideerd in de gebruikers interface en zijn hoofdletter gevoelig. Hierdoor ziet u mogelijk profielen die met onjuiste invoer zijn opgeslagen. Als u bijvoorbeeld `{{DeviceID}}` invoert in plaats van `{{deviceid}}`, wordt de letterlijke tekenreeks weergegeven in plaats van de unieke id van het apparaat. Zorg ervoor dat u de juiste informatie invoert.

## <a name="single-sign-on"></a>Eenmalige aanmelding

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: apparaatregistratie, automatische registratie van apparaten (onder Super visie)

- **Het kenmerk Gebruikersnaam in AAD**: Intune zoekt naar dit kenmerk voor elke gebruiker in Azure AD. Het betreffende veld (zoals UPN) wordt vervolgens door Intune ingevuld vóór het genereren van de XML die op het apparaat wordt geïnstalleerd. Uw opties zijn:

  - **User Principal Name**: de UPN wordt op de volgende manier geparseerd:

    ![Kenmerk Gebruikersnaam](./media/ios-device-features-settings/User-name-attribute.png)

    U kunt de realm ook overschrijven met de tekst die u in het tekstvak **Realm** invoert.

    Contoso heeft bijvoorbeeld meerdere regio's, waaronder Europa, Azië en Noord-Amerika. Contoso wil dat gebruikers uit Azië eenmalige aanmelding gebruiken en de app moet de UPN in de indeling `username@asia.contoso.com` hebben. Wanneer u **User Principal Name** selecteert, wordt de realm voor elke gebruiker overgenomen uit Microsoft Azure Active Directory, namelijk `contoso.com`. Voor gebruikers in Azië selecteert u dus **User Principal Name** en voert u `asia.contoso.com` in. De UPN van de eindgebruiker wordt `username@asia.contoso.com` in plaats van `username@contoso.com`.

  - **Apparaat-id voor Intune**: de apparaat-id voor Intune wordt automatisch door Intune geselecteerd.

    Apps hoeven standaard alleen de apparaat-id te gebruiken. Als uw app echter gebruikmaakt van de realm en de apparaat-id, kunt u de realm in het tekstvak Realm invoeren.

    > [!NOTE]
    > Houd de realm standaard leeg als u de apparaat-id gebruikt.

  - **Apparaat-id voor Microsoft Azure Active Directory**

- **Realm**: voer het domeingedeelte van de URL in. Voer bijvoorbeeld `contoso.com` in.
- **URL-voorvoegsels die gebruikmaken van eenmalige aanmelding**: **voeg** URL's in uw organisatie toe waarvoor gebruikersverificatie met eenmalige aanmelding vereist is.

  Bijvoorbeeld: wanneer een gebruiker verbinding maakt met een van deze sites, gebruikt het iOS-apparaat de referenties voor eenmalige aanmelding. De gebruiker hoeft geen aanvullende referenties in te voeren. Als meervoudige verificatie is ingeschakeld, moeten gebruikers de tweede verificatie invoeren.

  > [!NOTE]
  > Deze URL's moeten de juiste FQDN-indeling hebben. Apple vereist dat deze de indeling `http://<yourURL.domain>` hebben.

  De URL-vergelijkingspatronen moeten beginnen met `http://` of `https://`. Er wordt een eenvoudige vergelijking van de tekenreeksen uitgevoerd. Het URL-voorvoegsel `http://www.contoso.com/` komt dus niet overeen met `http://www.contoso.com:80/`. Bij iOS 10.0 of hoger kan het jokerteken \* worden gebruikt om alle overeenkomende waarden in te voeren. Bijvoorbeeld: `http://*.contoso.com/` komt overeen met zowel `http://store.contoso.com/` als `http://www.contoso.com`.

  De patronen `http://.com` en `https://.com` komen overeen met respectievelijk alle HTTP- en HTTPS-URL's.

- **Apps die gebruikmaken van eenmalige aanmelding**: **voeg** apps toe op apparaten van eindgebruikers die gebruik kunnen maken van eenmalige aanmelding.

  De matrix `AppIdentifierMatches` moet tekenreeksen bevatten die overeenkomen met de app-bundel-id's. Deze tekenreeksen kunnen exacte overeenkomsten zijn, zoals `com.contoso.myapp`, of u kunt identieke begintekens voor de bundel-id invoeren met het jokerteken \*. Het jokerteken moet worden weergegeven na een punt (.) en kan slechts één keer worden weergegeven aan het einde van de tekenreeks, zoals `com.contoso.*`. Wanneer een jokerteken wordt opgenomen, krijgt elke app waarvan de bundel-id begint met het voorvoegsel toegang tot het account.

  Gebruik **App-naam** om een gebruiksvriendelijke naam in te voeren waarmee u de bundel-id kunt aangeven.

- **Referentievernieuwingscertificaat**: als u certificaten voor verificatie gebruikt (geen wachtwoorden), selecteert u het SCEP- of PFX-certificaat als het verificatiecertificaat. Dit certificaat is meestal hetzelfde certificaat dat voor de gebruiker is geïmplementeerd voor andere profielen, bijvoorbeeld voor VPN, Wi-Fi of e-mail.

## <a name="web-content-filter"></a>Webinhoudsfilter

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Filtertype**: hiermee kunt u specifieke websites toestaan. Uw opties zijn:

  - **URL's configureren**: gebruik het ingebouwde webfilter van Apple dat zoekt naar ongepaste termen, zoals grof en seksueel getint taalgebruik. Deze functie evalueert elke webpagina terwijl deze wordt geladen, en identificeert en blokkeert ongeschikte inhoud. U kunt ook URL's toevoegen waarvan u niet wilt dat deze worden gecontroleerd door het filter. U kunt ook specifieke URL's blokkeren, ongeacht de filterinstellingen van Apple.

    - **Toegestane URL's**: **Voeg** de URL's toe die u wilt toestaan. Deze URL's omzeilen het webfilter van Apple.

        > [!NOTE]
        > De URL's die u invoert, zijn de URL's die u niet wilt laten evalueren door het webfilter van Apple. Deze URL's zijn geen lijst met toegestane websites. Als u een lijst met toegestane websites wilt maken, stelt u het **Filtertype** in op **Alleen specifieke websites**.

    - **Geblokkeerde URL's**: **voeg** de URL's toe waarvan u niet wilt dat deze worden geopend, ongeacht het webfilter van Apple.

  - **Alleen specifieke websites** (alleen voor Safari): deze URL's worden toegevoegd aan de bladwijzers van de Safari-browser. De gebruiker mag **alleen** deze sites bezoeken. Andere sites kunnen niet worden geopend. Gebruik deze optie alleen als u de exacte lijst van URL's weet die gebruikers mogen bezoeken.

    - **URL**: voer de URL in van de website die u wilt toestaan. Voer bijvoorbeeld `https://www.contoso.com` in.
    - **Bladwijzer pad**: Apple heeft deze instelling gewijzigd. Alle blad wijzers gaan naar de map **goedgekeurde sites** . Blad wijzers worden niet doorgezet naar het bladwijzer pad dat u invoert.
    - **Titel**: geef een beschrijvende titel voor de bladwijzer op.

    Als u geen URL's opgeeft, hebben eindgebruikers geen toegang tot websites, met uitzondering van `microsoft.com`, `microsoft.net` en `apple.com`. Deze URL's zijn automatisch toegestaan door Intune.

## <a name="single-sign-on-app-extension"></a>App-extensie voor eenmalige aanmelding

Deze functie is van toepassing op:

- iOS 13.0 en hoger
- iPadOS 13,0 en hoger

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Extensie type voor SSO-app**: Kies het type referentie-SSO-app-extensie. Uw opties zijn:

  - **Niet geconfigureerd**: app-extensies worden niet gebruikt. Als u een app-extensie wilt uitschakelen, kunt u het extensie type voor SSO-apps overschakelen van **Kerberos** of **referentie** naar **niet geconfigureerd**.
  - **Referentie**: gebruik een algemene, aanpas bare referentie-app-extensie om SSO uit te voeren. Zorg ervoor dat u de extensie-ID voor de SSO-app-extensie van uw organisatie kent.
  - **Kerberos**: gebruik de ingebouwde Kerberos-uitbrei ding van Apple, die is opgenomen in Ios 13,0 (en nieuwer) en iPadOS 13,0 (en nieuwer). Deze optie is een Kerberos-specifieke versie van de extensie voor **referentie** -apps.

  > [!TIP]
  > Met het **referentie** type voegt u uw eigen configuratie waarden toe om de extensie door te geven. In plaats daarvan kunt u gebruikmaken van ingebouwde configuratie-instellingen van Apple in het **Kerberos** -type.

- **Extensie-id** (alleen referentie): Geef de bundel-id op waarmee uw SSO-app-extensie wordt geïdentificeerd, zoals `com.apple.extensiblesso`.
- **Team-ID** (alleen referentie): Voer de team-ID van de extensie van uw SSO-app in. Een team-ID is een alfanumerieke teken reeks van 10 tekens (cijfers en letters) die wordt gegenereerd door Apple, zoals `ABCDE12345`. De team-ID is niet vereist.

  [Zoek uw team-ID](https://help.apple.com/developer-account/#/dev55c3c710c) (Open de website van Apple) voor meer informatie.

- **Realm**: Voer de naam van uw Kerberos-realm in. De realm-naam moet worden gekapitaliseerd, zoals `CONTOSO.COM`. Normaal gesp roken is uw realm-naam hetzelfde als de DNS-domein naam, maar in alle hoofd letters.

- **Domeinen**: Voer de domein-of hostnamen in van de sites die kunnen worden geverifieerd via SSO. Als uw website bijvoorbeeld `mysite.contoso.com` is, is `mysite` de hostnaam en is `contoso.com` de domein naam. Wanneer gebruikers verbinding maken met een van deze sites, wordt de verificatie vraag door de app-extensie afgehandeld. Met deze verificatie kunnen gebruikers gezichts-ID, aanraak-ID of Apple pincode/wachtwoord code gebruiken om zich aan te melden.

  - Alle domeinen in uw app-extensie voor eenmalige aanmelding moeten uniek zijn. U kunt een domein niet herhalen in een extensie profiel voor het aanmelden bij de app, zelfs niet als u verschillende typen SSO-app-extensies gebruikt.
  - Deze domeinen zijn niet hoofdletter gevoelig.

- **Aanvullende configuratie** (alleen referentie): voer aanvullende extensie-specifieke gegevens in die moeten worden door gegeven aan de SSO-appuitbreiding:
  - **Configuratie sleutel**: Voer de naam in van het item dat u wilt toevoegen, bijvoorbeeld `user name`.
  - **Waardetype**: Voer het type gegevens in. Uw opties zijn:

    - Tekenreeks
    - Boolean: Voer in **configuratie waarde**`True` of `False` in.
    - Geheel getal: Voer een getal in bij **configuratie waarde**.
    
  - **Configuratie waarde**: Voer de gegevens in.

  - **Toevoegen**: Selecteer deze optie om uw configuratie sleutels toe te voegen.

- **Gebruik van sleutel hanger** (alleen Kerberos): Kies **blok** om te voor komen dat wacht woorden worden opgeslagen en opgeslagen in de sleutel hanger. **Niet geconfigureerd** (standaard) Hiermee staat u toe dat wacht woorden worden opgeslagen en opgeslagen in de sleutel hanger.
- **Gezichts-id, aanraak-id of wachtwoord code** (alleen Kerberos): **vereisen dat** gebruikers hun gezichts-ID, aanraak-id of Apple-wachtwoord code invoeren om zich aan te melden bij de domeinen die u hebt toegevoegd. **Niet geconfigureerd** (standaard) gebruikers hoeven geen biometrie of wachtwoord code te gebruiken om zich aan te melden.
- **Standaard-realm** (alleen Kerberos): Kies **inschakelen** om de **realm** -waarde in te stellen die u hebt ingevoerd als de standaard-realm. **Niet geconfigureerd** (standaard) heeft geen standaard-realm ingesteld.

  > [!TIP]
  > - **Schakel** deze instelling in als u meerdere Kerberos SSO-app-extensies in uw organisatie wilt configureren.
  > - **Schakel** deze instelling in als u meerdere realms gebruikt. Hiermee stelt u de **realm** -waarde in die u hebt ingevoerd als de standaard-realm.
  > - Als u slechts één realm hebt, laat u deze **niet geconfigureerd** (standaard).

- **Principal-naam** (alleen Kerberos): Voer de gebruikers naam van de Kerberos-principal in. U hoeft de realm-naam niet op te vermelden. In `user@contoso.com` is `user` bijvoorbeeld de principal-naam en is `contoso.com` de realm-naam.
- **Active Directory site code** (alleen Kerberos): Voer de naam in van de Active Directory site die de Kerberos-uitbrei ding moet gebruiken. U hoeft deze waarde mogelijk niet te wijzigen, omdat de Kerberos-extensie de Active Directory site code mogelijk automatisch vindt.
- **Cache naam** (alleen Kerberos): Voer de naam in van de algemene beveiligings Services (gss) van de Kerberos-cache. U hoeft deze waarde waarschijnlijk niet in te stellen.
- **App-bundel-id's** (alleen Kerberos): Voeg de app-bundel-id's **toe** die gebruikmaken van eenmalige aanmelding op uw apparaten. Aan deze apps wordt toegang verleend tot de Kerberos ticket granting ticket, het verificatie ticket en de verificatie van gebruikers voor de services waartoe ze toegang hebben.
- **Domein realm-toewijzing** (alleen Kerberos): Voeg de DNS-achtervoegsels van het domein **toe** die moeten worden toegewezen aan uw realm. Gebruik deze instelling als de DNS-namen van de hosts niet overeenkomen met de realm-naam. U hoeft deze aangepaste domein-naar-realm-toewijzing waarschijnlijk niet te maken.

## <a name="wallpaper"></a>Achtergrond

Mogelijk ervaart u onverwacht gedrag wanneer een profiel zonder afbeelding wordt toegewezen aan apparaten met een bestaande afbeelding. U maakt bijvoorbeeld een profiel zonder afbeelding. Dit profiel wordt toegewezen aan apparaten die al een afbeelding hebben. In dit scenario kan de afbeelding worden gewijzigd in de standaardinstelling van het apparaat of de oorspronkelijke afbeelding blijft op het apparaat staan. Dit gedrag wordt geregeld en beperkt door het MDM-platform van Apple.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Instellingen zijn van toepassing op: automatische registratie van apparaten (onder Super visie)

- **Weergavelocatie voor achtergrond**: Kies een locatie op het apparaat om de afbeelding weer te geven. Uw opties zijn:
  - **Niet geconfigureerd**: Er is geen aangepaste afbeelding toegevoegd aan het apparaat. Het apparaat gebruikt de standaardinstelling van het besturingssysteem.
  - **Vergrendelingsscherm**: hiermee wordt de afbeelding toegevoegd aan het vergrendelingsscherm.
  - **Startscherm**: hiermee wordt de afbeelding toegevoegd aan het startscherm.
  - **Vergrendelingsscherm en startscherm**: dezelfde afbeelding wordt op het vergrendelingsscherm en het startscherm gebruikt.
- **Achtergrondafbeelding**: upload een bestaande PNG-, JPG- of JPEG-afbeelding die u wilt gebruiken. Zorg ervoor dat de bestandsgrootte minder is dan 750 KB. U kunt een afbeelding die u hebt toegevoegd ook **verwijderen**.

> [!TIP]
> Als u verschillende afbeeldingen op het vergrendelingsscherm en het startscherm wilt weergeven, maakt u een profiel met de afbeelding voor het vergrendelingsscherm. Maak een ander profiel met de afbeelding van het startscherm. Wijs beide profielen toe aan uw iOS-gebruikers- of -apparaatgroepen.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

U kunt ook apparaatfunctieprofielen maken voor [macOS](macos-device-features-settings.md)-apparaten.
