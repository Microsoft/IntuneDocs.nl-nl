---
title: Instellingen van apparaatfuncties voor iOS/iPadOS in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk alle instellingen voor het configureren van iOS-/iPadOS-apparaten, de indeling van het startscherm, app-meldingen, gedeelde apparaten, eenmalige aanmelding en het filteren van webinhoud in Microsoft Intune. Gebruik deze instellingen in een apparaatconfiguratieprofiel om iOS-/iPadOS-apparaten te configureren voor het gebruik van deze Apple-functies in uw organisatie.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
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
ms.openlocfilehash: 7f19ccfb6949dbfa0de62a8b711436ab9cde8c9c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512939"
---
# <a name="ios-and-ipados-device-settings-to-use-common-iosipados-features-in-intune"></a>iOS- en iPadOS-apparaatinstellingen voor het gebruik van algemene iOS-/iPadOS-functies in Intune

Intune bevat enkele ingebouwde instellingen, zodat iOS-/iPadOS-gebruikers verschillende functies van Apple op hun apparaten kunnen gebruiken. Beheerders kunnen bijvoorbeeld bepalen hoe iOS-/iPadOS-gebruikers AirPrint-printers gebruiken, apps en mappen toevoegen aan de dock en pagina's op het startscherm, app-meldingen weergeven, details van inventaristags weergeven op het vergrendelingsscherm, verificatie met eenmalige aanmelding gebruiken, en gebruikers met certificaten verifiëren.

Gebruik deze functies om iOS-/iPadOS-apparaten te beheren als onderdeel van uw MDM-oplossing (Mobile Device Management).

Dit artikel beschrijft deze instellingen en wat elke instelling doet. Ga naar [Instellingen voor iOS-/iPadOS- of macOS-apparaatfuncties toevoegen](../device-features-configure.md) voor meer informatie over deze functies.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een iOS-/iPadOS-apparaatconfiguratieprofiel](../device-features-configure.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvingstypen, waarbij sommige instellingen van toepassing zijn op alle inschrijvingsopties. Zie [iOS-/iPadOS-inschrijving](../ios-enroll.md) voor meer informatie over de verschillende inschrijvingstypen.

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

> [!NOTE]
> Vergeet niet om alle printers toe te voegen aan hetzelfde profiel. In Apple kunnen niet meerdere AirPrint-profielen worden gekoppeld aan hetzelfde apparaat.

- **IP-adres**: voer het IPv4- of IPv6-adres van de printer in. Als u hostnamen gebruikt om printers te identificeren, krijgt u het IP-adres door de printer in de terminal te pingen. In Haal het IP-adres en het pad op (in dit artikel) vindt u meer informatie.
- **Pad**: het pad is doorgaans `ipp/print` voor printers in uw netwerk. In Haal het IP-adres en het pad op (in dit artikel) vindt u meer informatie.
- **Poort**: Voer de luisterpoort van de AirPrint-bestemming in. Als u deze eigenschap leeg laat, maakt AirPrint gebruik van de standaardpoort. Beschikbaar in iOS 11.0+, en iPadOS 13.0+.
- **TLS**: Kies **Inschakelen** voor het beveiligen van AirPrint-verbindingen met Transport Layer Security (TLS). Beschikbaar in iOS 11.0+, en iPadOS 13.0+.

Als u AirPrint-servers wilt toevoegen, kunt u het volgende doen:

- Met **Toevoegen** wordt de AirPrint-server aan de lijst toegevoegd. Er kunnen veel AirPrint-servers worden toegevoegd.
- Een door komma's gescheiden bestand (.csv) met deze informatie **importeren**. Of **Exporteren** om een lijst met AirPrint-servers te maken die u hebt toegevoegd.

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

- iOS 9.3 of nieuwer
- iPadOS 13.0 en hoger

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

### <a name="dock"></a>Dock

Gebruik de **Dock**-instellingen om maximaal zes items of mappen toe te voegen aan de dock onderaan in het iOS-/iPadOS-scherm. Veel apparaten ondersteunen minder items. IPhone-apparaten ondersteunen bijvoorbeeld maximaal vier items. In dit geval worden alleen de eerste vier items die u hebt toegevoegd op het apparaat weergegeven.

U kunt maximaal **zes** items (combinatie van apps en mappen) voor de apparaatdock toevoegen.

- **Toevoegen**: Apps of mappen toevoegen aan de dock op het apparaat.
- **Type**: Een **app** of een **map** toevoegen:

  - **App**: kies deze optie om apps aan de dock op het scherm toe te voegen. Voer het volgende in:

    - **App-naam**: voer een naam voor de app in. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het iOS-/iPadOS-apparaat.
    - **App-bundel-id**: voer de bundel-id van de app in. Zie [Bundel-id's voor ingebouwde iOS-/iPadOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

  - **Map**: kies deze optie om een map aan de dock op het scherm toe te voegen.

    Apps die u aan een pagina in een map toevoegt, worden gerangschikt van links naar rechts, en in dezelfde volgorde als de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een andere pagina verplaatst.

    - **Mapnaam**: Voer de naam van de map in. Deze naam zien gebruikers op hun apparaat.
    - **Lijst met pagina's**: U kunt een pagina **Toevoegen** en de volgende eigenschappen invoeren:

      - **Paginanaam**: voer een naam voor de pagina in. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het iOS-/iPadOS-apparaat.
      - **App-naam**: voer een naam voor de app in. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het iOS-/iPadOS-apparaat.
      - **App-bundel-id**: voer de bundel-id van de app in. Zie [Bundel-id's voor ingebouwde iOS-/iPadOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

      U kunt maximaal **20** pagina's toevoegen voor de apparaatdock.

> [!NOTE]
> Wanneer u pictogrammen toevoegt met behulp van de Dock-instellingen, zijn de pictogrammen op het startscherm en de pagina's vergrendeld en kunnen deze niet worden verplaatst. Dit is mogelijk inherent aan iOS/iPadOS en de MDM-beleidsregels van Apple.

#### <a name="example"></a>Voorbeeld

In het volgende voorbeeld worden op het dock-scherm alleen de apps Safari, Mail en Aandelen weergegeven. De app Mail is geselecteerd om de eigenschappen ervan weer te geven:

![Voorbeeld van iOS-/iPadOS-dockinstellingen](./media/ios-device-features-settings/FfFiUcP.png)

Wanneer u het beleid aan een iPhone toewijst, ziet de dock er ongeveer hetzelfde uit als de volgende afbeelding:

![Voorbeeld van iOS-/iPadOS-dockindeling op iPhone](./media/ios-device-features-settings/bAgCe8F.png)

### <a name="pages"></a>Pages

Voeg de pagina's toe die u wilt weergeven op het startscherm en de apps die moeten worden weergegeven op elke pagina. Apps die u aan een pagina toevoegt, worden gerangschikt van links naar rechts, in dezelfde volgorde als de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een andere pagina verplaatst.

> [!TIP]
> U kunt items slepen en neerzetten in elk startscherm en alle paginalijsten om deze te opnieuw te rangschikken.

U kunt maximaal **40** pagina's toevoegen.

- **Lijst met pagina's**: U kunt een pagina **Toevoegen** en de volgende eigenschappen invoeren:

  - **Paginanaam**: voer een naam voor de pagina in. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum, en wordt *niet* weergegeven op het iOS-/iPadOS-apparaat.

  U kunt maximaal **60** items (combinatie van apps en mappen) toevoegen op een apparaat.

  - **Toevoegen**: Apps of mappen toevoegen aan een pagina op het apparaat.

    - **Type**: Een **app** of een **map** toevoegen:

      - **App**: kies deze optie om apps aan een pagina op het scherm toe te voegen. Voer ook in:

        - **App-naam**: voer een naam voor de app in. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het iOS-/iPadOS-apparaat.
        - **App-bundel-id**: voer de bundel-id van de app in. Zie [Bundel-id's voor ingebouwde iOS-/iPadOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

      - **Map**: kies deze optie om een map aan de dock op het scherm toe te voegen.

        Apps die u aan een pagina in een map toevoegt, worden gerangschikt van links naar rechts, en in dezelfde volgorde als de lijst. Als u meer apps toevoegt dan er op een pagina passen, worden de apps naar een andere pagina verplaatst.

        - **Mapnaam**: Voer een naam voor de map in. Deze naam zien gebruikers op het apparaat.
        - **Toevoegen**: Hiermee worden pagina's aan de map toegevoegd. Voer ook de volgende eigenschappen in:

          - **Paginanaam**: voer een naam voor de pagina in. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het iOS-/iPadOS-apparaat.
          - **App-naam**: voer een naam voor de app in. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het iOS-/iPadOS-apparaat.
          - **App-bundel-id**: voer de bundel-id van de app in. Zie [Bundel-id's voor ingebouwde iOS-/iPadOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.

#### <a name="example"></a>Voorbeeld

In het volgende voorbeeld wordt een nieuwe pagina met de naam **Contoso** toegevoegd. Op de pagina worden de apps Zoek vrienden en Instellingen weergegeven. De app Instellingen is geselecteerd om de eigenschappen ervan weer te geven:

![Voorbeeld van instellingen voor het iOS-/iPadOS-startscherm in Intune](./media/ios-device-features-settings/Jc2OxyX.png)

Wanneer u het beleid aan een iPhone toewijst, ziet de pagina er ongeveer hetzelfde uit als de volgende afbeelding:

![iOS-/iPadOS-apparaat met gewijzigd startscherm in Intune](./media/ios-device-features-settings/Bd37PHa.png)

## <a name="app-notifications"></a>App-meldingen

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Toevoegen**: Meldingen voor apps toevoegen:

    ![App-melding toevoegen in iOS-/iPadOS-profiel in Intune](./media/ios-device-features-settings/ios-macos-app-notifications.png)

  - **App-bundel-id**: voer de **App-bundel-id** in van de app die u wilt toevoegen. Zie [Bundel-id's voor ingebouwde iOS-/iPadOS-apps](bundle-ids-built-in-ios-apps.md) voor enkele voorbeelden.
  - **App-naam**: voer de naam in van de app die u wilt toevoegen. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het apparaat.
  - **Uitgever**: voer de uitgever in van de app die u toevoegt. Deze naam wordt gebruikt voor uw referentie in het Microsoft Endpoint Manager-beheercentrum. Deze wordt *niet* weergegeven op het apparaat.
  - **Meldingen**: **in**- of **uitschakelen** dat de app meldingen naar het apparaat verzendt.
    - **Weergeven in het meldingencentrum**: als u **Inschakelen** kiest, geeft de app meldingen weer in meldingencentrum van het apparaat. als u **Uitschakelen** kiest, geeft de app geen meldingen weer in meldingencentrum.
    - **Weergeven in het vergrendelingsscherm**: als u **Inschakelen** kiest, worden meldingen van de app weergegeven op het vergrendelingsscherm van het apparaat. als u **Uitschakelen** kiest, worden meldingen van de app niet weergegeven op het vergrendelingsscherm.
    - **Waarschuwingstype**: kies hoe de melding moet worden weergegeven wanneer het apparaat wordt ontgrendeld. Uw opties zijn:
      - **Geen**: er wordt geen melding weergegeven.
      - **Banner**: er wordt kort een banner weergegeven met de melding.
      - **Modaal**: de melding wordt weergegeven en de gebruiker moet deze handmatig sluiten voordat de gebruiker kan doorgaan en het apparaat kan gebruiken.
    - **Badge op app-pictogram**: selecteer **Inschakelen** om een badge toe te voegen aan het app-pictogram. De badge betekent dat de app een melding heeft verzonden.
    - **Geluiden**: selecteer **Inschakelen** om een geluid af te spelen wanneer een melding wordt afgeleverd.

## <a name="lock-screen-message"></a>Bericht voor vergrendelingsscherm

Deze functie is van toepassing op:

- iOS 9.3 en hoger
- iPadOS 13.0 en hoger

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Informatie over de assettag**: Voer informatie over de assettag van het apparaat in. Voer bijvoorbeeld `Owned by Contoso Corp` of `Serial Number: {{serialnumber}}` in.

  De tekst die u opgeeft, wordt weergegeven in het aanmeldingsvenster en het vergrendelingsscherm van het apparaat.

- **Voetnoot voor vergrendelingsscherm**: Voer een opmerking in waarmee u het apparaat wellicht kunt terugkrijgen als het verloren of gestolen is. U kunt elke gewenste tekst invoeren. Voer bijvoorbeeld iets in zoals `If found, call Contoso at ...`.

  Apparaattokens kunnen ook worden gebruikt om apparaatspecifieke informatie aan deze velden toe te voegen. Als u bijvoorbeeld het serienummer wilt weergeven, voert u `Serial Number: {{serialnumber}}` in. De tekst die in het vergrendelingsscherm wordt weergegeven, is vergelijkbaar met `Serial Number 123456789ABC`. Wanneer u variabelen opgeeft, moet u ervoor zorgen dat u accolades `{{ }}` gebruikt. [App-configuratietokens](../apps/app-configuration-policies-use-ios.md#tokens-used-in-the-property-list) bevat een lijst met variabelen die kunnen worden gebruikt. U kunt ook `deviceName` of een andere apparaatspecifieke waarde gebruiken.

  > [!NOTE]
  > Variabelen worden niet gevalideerd in de gebruikersinterface en zijn hoofdlettergevoelig. Hierdoor ziet u mogelijk profielen die met onjuiste invoer zijn opgeslagen. Als u bijvoorbeeld `{{DeviceID}}` invoert in plaats van `{{deviceid}}`, wordt de letterlijke tekenreeks weergegeven in plaats van de unieke id van het apparaat. Zorg dat u de juiste informatie invoert.

## <a name="single-sign-on"></a>Eenmalige aanmelding

### <a name="settings-apply-to-device-enrollment-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving, automatische apparaatinschrijving (onder supervisie)

- **Het kenmerk Gebruikersnaam van AAD**: Intune zoekt naar dit kenmerk voor elke gebruiker in Microsoft Azure Active Directory. Het betreffende veld (zoals UPN) wordt vervolgens door Intune ingevuld vóór het genereren van de XML die op het apparaat wordt geïnstalleerd. Uw opties zijn:

  - **User Principal Name**: de UPN wordt op de volgende manier geparseerd:

    ![SSO-kenmerk van iOS-/iPadOS-gebruikersnaam in Intune](./media/ios-device-features-settings/User-name-attribute.png)

    U kunt de realm ook overschrijven met de tekst die u in het tekstvak **Realm** invoert.

    Contoso heeft bijvoorbeeld meerdere regio's, waaronder Europa, Azië en Noord-Amerika. Contoso wil dat gebruikers uit Azië eenmalige aanmelding gebruiken en de app moet de UPN in de indeling `username@asia.contoso.com` hebben. Wanneer u **User Principal Name** selecteert, wordt de realm voor elke gebruiker overgenomen uit Microsoft Azure Active Directory, namelijk `contoso.com`. Voor gebruikers in Azië selecteert u dus **User Principal Name** en voert u `asia.contoso.com` in. De UPN van de eindgebruiker wordt `username@asia.contoso.com` in plaats van `username@contoso.com`.

  - **Apparaat-id voor Intune**: de apparaat-id voor Intune wordt automatisch door Intune geselecteerd.

    Apps hoeven standaard alleen de apparaat-id te gebruiken. Als uw app echter gebruikmaakt van de realm en de apparaat-id, kunt u de realm in het tekstvak Realm invoeren.

    > [!NOTE]
    > Houd de realm standaard leeg als u de apparaat-id gebruikt.

  - **Apparaat-id voor Microsoft Azure Active Directory**

- **Realm**: voer het domeingedeelte van de URL in. Voer bijvoorbeeld `contoso.com` in.
- **URL-voorvoegsels die gebruikmaken van eenmalige aanmelding**: **voeg** alle URL's in uw organisatie toe die gebruikersverificatie met eenmalige aanmelding vereisen.

  Bijvoorbeeld: wanneer een gebruiker verbinding maakt met een van deze sites, gebruikt het iOS-/iPadOS-apparaat de referenties voor eenmalige aanmelding. De gebruiker hoeft geen aanvullende referenties in te voeren. Als meervoudige verificatie is ingeschakeld, moeten gebruikers de tweede verificatie invoeren.

  > [!NOTE]
  > Deze URL's moeten de juiste FQDN-indeling hebben. Apple vereist dat deze de indeling `http://<yourURL.domain>` hebben.

  De URL-vergelijkingspatronen moeten beginnen met `http://` of `https://`. Er wordt een eenvoudige vergelijking van de tekenreeksen uitgevoerd. Het URL-voorvoegsel `http://www.contoso.com/` komt dus niet overeen met `http://www.contoso.com:80/`. Bij iOS 10.0 en iPadOS 13.0+ kan het jokerteken \* worden gebruikt om alle overeenkomende waarden in te voeren. Bijvoorbeeld: `http://*.contoso.com/` komt overeen met zowel `http://store.contoso.com/` als `http://www.contoso.com`.

  De patronen `http://.com` en `https://.com` komen overeen met respectievelijk alle HTTP- en HTTPS-URL's.

- **Apps die gebruikmaken van eenmalige aanmelding**: **voeg** apps toe op apparaten van eindgebruikers die gebruik kunnen maken van eenmalige aanmelding.

  De matrix `AppIdentifierMatches` moet tekenreeksen bevatten die overeenkomen met de app-bundel-id's. Deze tekenreeksen kunnen exacte overeenkomsten zijn, zoals `com.contoso.myapp`, of u kunt identieke begintekens voor de bundel-id invoeren met het jokerteken \*. Het jokerteken moet worden weergegeven na een punt (.) en kan slechts één keer worden weergegeven aan het einde van de tekenreeks, zoals `com.contoso.*`. Wanneer een jokerteken wordt opgenomen, krijgt elke app waarvan de bundel-id begint met het voorvoegsel toegang tot het account.

  Gebruik **App-naam** om een gebruiksvriendelijke naam in te voeren waarmee u de bundel-id kunt aangeven.

- **Referentievernieuwingscertificaat**: als u certificaten voor verificatie gebruikt (geen wachtwoorden), selecteert u het SCEP- of PFX-certificaat als het verificatiecertificaat. Dit certificaat is meestal hetzelfde certificaat dat voor de gebruiker is geïmplementeerd voor andere profielen, bijvoorbeeld voor VPN, Wi-Fi of e-mail.

## <a name="web-content-filter"></a>Webinhoudsfilter

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Filtertype**: Hiermee kunt u specifieke websites toestaan. Uw opties zijn:

  - **URL's configureren**: gebruik het ingebouwde webfilter van Apple dat zoekt naar ongepaste termen, zoals grof en seksueel getint taalgebruik. Deze functie evalueert elke webpagina terwijl deze wordt geladen, en identificeert en blokkeert ongeschikte inhoud. U kunt ook URL's toevoegen waarvan u niet wilt dat deze worden gecontroleerd door het filter. U kunt ook specifieke URL's blokkeren, ongeacht de filterinstellingen van Apple.

    - **Toegestane URL's**: **voeg** de URL's toe die u wilt toestaan. Deze URL's omzeilen het webfilter van Apple.

        > [!NOTE]
        > De URL's die u invoert, zijn de URL's die u niet wilt laten evalueren door het webfilter van Apple. Deze URL's zijn geen lijst met toegestane websites. Als u een lijst met toegestane websites wilt maken, stelt u het **Filtertype** in op **Alleen specifieke websites**.

    - **Geblokkeerde URL's**: **voeg** de URL's toe waarvan u niet wilt dat deze worden geopend, ongeacht het webfilter van Apple.

  - **Alleen specifieke websites** (alleen voor de Safari-webbrowser): deze URL's worden toegevoegd aan de bladwijzers van de Safari-browser. De gebruiker mag **alleen** deze sites bezoeken. Andere sites kunnen niet worden geopend. Gebruik deze optie alleen als u de exacte lijst van URL's weet die gebruikers mogen bezoeken.

    - **URL**: voer de URL in van de website die u wilt toestaan. Voer bijvoorbeeld `https://www.contoso.com` in.
    - **Pad naar bladwijzer**: deze instelling is gewijzigd in Apple. Alle bladwijzers gaan naar de map **Goedgekeurde sites**. Bladwijzers komen niet in het pad naar de bladwijzer die u invoert.
    - **Titel**: geef een beschrijvende titel voor de bladwijzer op.

    Als u geen URL's opgeeft, hebben eindgebruikers geen toegang tot websites, met uitzondering van `microsoft.com`, `microsoft.net` en `apple.com`. Deze URL's zijn automatisch toegestaan door Intune.

## <a name="single-sign-on-app-extension"></a>App-extensie voor eenmalige aanmelding

Deze functie is van toepassing op:

- iOS 13.0 en hoger
- iPadOS 13.0 en hoger

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Type app-extensie voor SSO**: kies het type app-extensie voor SSO. Uw opties zijn:

  - **Niet geconfigureerd**: app-extensies worden niet gebruikt. Als u een app-extensie wilt uitschakelen, stelt u Type app-extensie voor SSO in op **Niet geconfigureerd**.
  - **Omleiding**: gebruik een algemene, aanpasbare app-extensie Omleiding om eenmalige aanmelding uit te voeren met moderne verificatiestromen. Zorg ervoor dat u weet wat de extensie-id is van de app-extensie van uw organisatie.
  - **Referentie**: gebruik een algemene, aanpasbare app-extensie Referentie voor het uitvoeren van eenmalige aanmelding met uitdaging-en-reactie-verificatiestromen. Zorg ervoor dat u weet wat de extensie-id is van de app-extensie van uw organisatie.
  - **Kerberos**: gebruik de ingebouwde Kerberos-extensie van Kerberos, die is opgenomen in iOS 13.0+ en iPadOS 13.0+. Deze optie is een Kerberos-versie van de app-extensie **Referentie**.

  > [!TIP]
  > Met de typen **Omleiding** en **Referentie** voegt u uw eigen configuratiewaarden toe om door te geven aan de extensie. Als u het type **Referentie** gebruikt, kunt u overwegen om de ingebouwde configuratie-instellingen te gebruiken die Apple heeft opgenomen in het type **Kerberos**.

- **Extensie-id** (Omleiding en Referentie): voer de bundel-id in waarmee de app-extensie voor SSO wordt geïdentificeerd, zoals `com.apple.extensiblesso`.

- **Team-id** (Omleiding en Referentie): voer de team-id in van uw app-extensie voor SSO. Een team-id is een alfanumerieke tekenreeks van 10 tekens (cijfers en letters) die wordt gegenereerd met Apple, zoals `ABCDE12345`. De team-id is niet vereist.

  [Zoek uw team-id](https://help.apple.com/developer-account/#/dev55c3c710c): (opent de website van Apple) biedt meer informatie.

- **Realm** (Referentie en Kerberos): voer de naam van uw verificatierealm in. De realmnaam moet in hoofdletters zijn, zoals `CONTOSO.COM`. Uw realmnaam is meestal gelijk aan uw DNS-domeinnaam, maar dan met alleen hoofdletters.

- **Domeinen** (Referentie en Kerberos): voer de domein- of hostnamen in van de sites die kunnen worden geverifieerd via SSO. Als bijvoorbeeld `mysite.contoso.com` uw website is, is `mysite` de hostnaam en is `contoso.com` de domeinnaam. Wanneer gebruikers verbinding maken met een van deze sites, wordt de verificatie-uitdaging afgehandeld via de app-extensie. Met deze verificatie kunnen gebruikers Face ID, Touch ID of de pincode/wachtwoordcode van Apple gebruiken om zich aan te melden.

  - Alle domeinen in uw app-extensie voor eenmalige aanmelding bij Intune-profielen moeten uniek zijn. U kunt een domein niet herhalen in een app-extensieprofiel voor eenmalige aanmelding, zelfs niet als u verschillende typen app-extensie voor SSO gebruikt.
  - Deze domeinen zijn niet hoofdlettergevoelig.

- **URL's** (alleen Omleiding): voer de URL-voorvoegsels van uw id-providers in namens wie SSO wordt uitgevoerd met de app-extensie Omleiding. Wanneer een gebruiker wordt omgeleid naar deze URL's, grijpt de app-extensie voor SSO in en wordt er om SSO gevraagd.

  - Alle URL's in uw app-extensie voor SSO bij Intune-profielen moeten uniek zijn. U kunt een domein niet herhalen in een app-extensieprofiel voor SSO, zelfs niet als u verschillende typen app-extensie voor SSO gebruikt.
  - De URL's moeten beginnen met http:// of https://.

- **Aanvullende configuratie** (Omleiding en Referentie): voer aanvullende extensiegegevens in die moeten worden doorgegeven aan de app-extensie voor SSO:
  - **Sleutel**: voer de naam in van het item dat u wilt toevoegen, zoals `user name`.
  - **Type**: voer het gegevenstype in. Uw opties zijn:

    - Tekenreeks
    - Booleaans: voer `True` of `False` in bij **Configuratiewaarde**.
    - Geheel getal: voer een getal in bij **Configuratiewaarde**.
    
  - **Waarde**: voer de gegevens in.

  - **Toevoegen**: selecteer deze optie om uw configuratiesleutels toe te voegen.

- **Gebruik van sleutelhanger** (alleen Kerberos): kies **Blokkeren** om te voorkomen dat wachtwoorden worden opgeslagen in de sleutelhanger. **Niet geconfigureerd** (standaard): staat toe dat wachtwoorden worden opgeslagen in de sleutelhanger.
- **Face ID, Touch ID of wachtwoordcode** (alleen Kerberos): **Vereisen** dwingt gebruikers om hun Face ID, Touch ID, of Apple-wachtwoordcode in te voeren om zich aan te melden bij de door u toegevoegde domeinen. **Niet geconfigureerd** (standaard): gebruikers hoeven geen biometrie of wachtwoordcode te gebruiken om zich aan te melden.
- **Standaardrealm** (alleen Kerberos): Kies **Inschakelen** om de waarde voor **Realm** in te stellen die u hebt ingevoerd als de standaardrealm. **Niet geconfigureerd** (standaard): er wordt geen standaardrealm ingesteld.

  > [!TIP]
  > - U moet deze instelling **inschakelen** als u meerdere app-extensies voor SSO bij Kerberos configureert in uw organisatie.
  > - U kunt deze instelling **inschakelen** als u meerdere realms gebruikt. Hiermee stelt u de waarde voor **Realm** in die u hebt ingevoerd als de standaardrealm.
  > - Als u slechts één realm hebt, laat u deze ingesteld op **Niet geconfigureerd** (standaard).

- **Principal-naam** (alleen Kerberos): voer de gebruikersnaam in van de Kerberos-principal. U hoeft de realmnaam niet op te nemen. In `user@contoso.com` is `user` bijvoorbeeld de principal-naam en `contoso.com` de realmnaam.

  > [!TIP]
  > - U kunt ook variabelen gebruiken in de principal-naam door accolades `{{ }}` in te voeren. Voer bijvoorbeeld `Username: {{username}}` in om de gebruikersnaam weer te geven. 
  > - Wees echter voorzichtig met het vervangen van variabelen, want variabelen worden niet gevalideerd in de UI en zijn hoofdlettergevoelig. Zorg dat u de juiste informatie invoert.

- **Active Directory-sitecode** (alleen Kerberos): voer de naam in van de Active Directory-site die door de Kerberos-extensie moet worden gebruikt. Waarschijnlijk hoeft u deze waarde niet te wijzigen, omdat de Kerberos-extensie de Active Directory-sitecode mogelijk automatisch kan vinden.
- **Cachenaam** (alleen Kerberos): voer de naam in van de GSS (generieke beveiligingsservices) van de Kerberos-cache. Waarschijnlijk hoeft u deze waarde niet in te stellen.
- **App-bundel-id's** (alleen Kerberos): u kunt de app-bundel-id's **toevoegen** die moeten gebruikmaken van eenmalige aanmelding op uw apparaten. Aan deze apps wordt toegang verleend tot de Kerberos TGT (Ticket Granting Ticket), het verificatieticket, en met deze apps worden gebruikers geverifieerd bij de services waarvoor ze een toegangsmachtiging hebben.
- **Toewijzen van domeinrealm** (alleen Kerberos): u kunt de domein-DNS-achtervoegsels **toevoegen** die moeten worden toegewezen aan uw realm. Gebruik deze instelling als de DNS-namen van de hosts niet overeenkomen met de realmnaam. Waarschijnlijk hoeft u deze aangepaste domein-naar-realm-toewijzing niet te maken.
- **PKINIT-certificaat** (alleen Kerberos): **selecteer** het PIKNIT-certificaat (Public Key Cryptography for Initial Authentication) dat kan worden gebruikt voor Kerberos-verificatie. U kunt kiezen uit een [PKCS](../protect/certficates-pfx-configure.md)- of [SCEP](../protect/certificates-scep-configure.md)-certificaat dat u hebt toegevoegd in Intune. Raadpleeg [Certificaten gebruiken voor verificatie in Microsoft Intune](../protect/certificates-configure.md) voor meer informatie over certificaten.

## <a name="wallpaper"></a>Achtergrond

Mogelijk ervaart u onverwacht gedrag wanneer een profiel zonder afbeelding wordt toegewezen aan apparaten met een bestaande afbeelding. U maakt bijvoorbeeld een profiel zonder afbeelding. Dit profiel wordt toegewezen aan apparaten die al een afbeelding hebben. In dit scenario kan de afbeelding worden gewijzigd in de standaardinstelling van het apparaat of de oorspronkelijke afbeelding blijft op het apparaat staan. Dit gedrag wordt geregeld en beperkt door het MDM-platform van Apple.

### <a name="settings-apply-to-automated-device-enrollment-supervised"></a>Deze instellingen zijn van toepassing op: Automatische apparaatinschrijving (onder toezicht)

- **Weergavelocatie voor achtergrond**: kies een locatie op het apparaat om de afbeelding weer te geven. Uw opties zijn:
  - **Niet geconfigureerd**: er is geen aangepaste afbeelding toegevoegd aan het apparaat. Het apparaat gebruikt de standaardinstelling van het besturingssysteem.
  - **Vergrendelingsscherm**: hiermee wordt de afbeelding toegevoegd aan het vergrendelingsscherm.
  - **Startscherm**: hiermee wordt de afbeelding toegevoegd aan het startscherm.
  - **Vergrendelingsscherm en startscherm**: dezelfde afbeelding wordt op het vergrendelingsscherm en het startscherm gebruikt.
- **Achtergrondafbeelding**: upload een bestaande PNG-, JPG- of JPEG-afbeelding die u wilt gebruiken. Zorg ervoor dat de bestandsgrootte minder is dan 750 KB. U kunt een afbeelding die u hebt toegevoegd ook **verwijderen**.

> [!TIP]
> Als u verschillende afbeeldingen op het vergrendelingsscherm en het startscherm wilt weergeven, maakt u een profiel met de afbeelding voor het vergrendelingsscherm. Maak een ander profiel met de afbeelding van het startscherm. Wijs beide profielen toe aan uw iOS-/iPadOS-gebruikers- of -apparaatgroepen.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](../device-profile-assign.md) en [de status ervan controleren](../device-profile-monitor.md).

U kunt ook apparaatfunctieprofielen maken voor [macOS](macos-device-features-settings.md)-apparaten.
