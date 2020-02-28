---
title: Instellingen van apparaatfuncties voor macOS in Microsoft Intune - Azure | Microsoft Docs
description: Zie de instellingen om macOS-apparaten te configureren voor AirPrint en om energie-instellingen op het aanmeldingsvenster van Microsoft Intune weer te geven of te verbergen. Raadpleeg de stappen om het IP-adres, het pad en de poortinstellingen van een AirPrint-server in uw netwerk op te halen. Gebruik deze instellingen in een apparaatconfiguratieprofiel om functies voor macOS-apparaten te configureren.
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
ms.openlocfilehash: df5b53be159fd082090e61fd736e4c9329644c85
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512735"
---
# <a name="macos-device-feature-settings-in-intune"></a>Instellingen van apparaatfuncties voor macOS in Intune

Intune bevat een aantal ingebouwde instellingen om functies op uw macOS-apparaten aan te passen. Zo kunnen beheerders onder meer AirPrint-printers toevoegen, kiezen hoe gebruikers zich aanmelden, de energiebeheerfuncties configureren, verificatie voor eenmalige aanmelding gebruiken.

Gebruik deze functies om macOS-apparaten te beheren als onderdeel van uw Mobile Device Management-oplossing (MDM).

Dit artikel beschrijft deze instellingen en wat elke instelling doet. Het beschrijft tevens de stappen voor het ophalen van het IP-adres, het pad en de poort van AirPrint-printers via de Terminal-app (emulator). Ga voor meer informatie over de functies van het apparaat naar [Instellingen voor iOS-/iPadOS- of macOS-apparaatfuncties toevoegen](device-features-configure.md).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een macOS-apparaatconfiguratieprofiel](device-features-configure.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvingstypen, waarbij sommige instellingen van toepassing zijn op alle inschrijvingsopties. Zie [macOS-inschrijving](../enrollment/macos-enroll.md) voor meer informatie over de verschillende inschrijvingstypen.

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving en geautomatiseerde apparaatinschrijving 

- **IP-adres**: voer het IPv4- of IPv6-adres van de printer in. Als u hostnamen gebruikt om printers te identificeren, haalt u het IP-adres op door de printer in de Terminal-app te pingen. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
- **Pad**: Voer het pad van de printer in. Het pad is doorgaans `ipp/print` voor printers in uw netwerk. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
- **Poort** (iOS 11.0+, iPadOS 13.0+): Voer de luisterpoort van de AirPrint-bestemming in. Als u deze eigenschap leeg laat, maakt AirPrint gebruik van de standaardpoort.
- **TLS** (iOS 11.0+, iPadOS 13.0+): Selecteer **Inschakelen** voor het beveiligen van AirPrint-verbindingen met Transport Layer Security (TLS).

- **Voeg** de AirPrint-server toe. U kunt veel AirPrint-servers toevoegen.

U kunt ook een door komma's gescheiden bestand (.csv) **importeren** met een lijst van AirPrint-printers. Nadat u AirPrint-printers aan Intune hebt toegevoegd, kunt u bovendien deze lijst **exporteren**.

### <a name="get-the-ip-address-and-path"></a>IP-adres en pad ophalen

Om AirPrinter-servers toe te voegen, hebt u het IP-adres van de printer, het bronpad en de poort nodig. De volgende stappen laten zien hoe u aan deze informatie komt.

1. Open op een Mac die verbonden is met hetzelfde lokale netwerk (subnet) als de AirPrint-printers de **Terminal** (via **/Programma's/Hulpprogramma's**).
2. Typ in de Terminal-app `ippfind` en selecteer Enter.

    Noteer de printergegevens. Er wordt bijvoorbeeld iets in de trant van `ipp://myprinter.local.:631/ipp/port1` geretourneerd. Het eerste deel is de naam van de printer. Het laatste deel (`ipp/port1`) is het bronpad.

3. Typ in de terminal `ping myprinter.local` en selecteer Enter.

   Noteer het IP-adres. Er wordt bijvoorbeeld iets in de trant van `PING myprinter.local (10.50.25.21)` geretourneerd.

4. Gebruik de waarden van het IP-adres en het bronpad. In dit voorbeeld is het IP-adres `10.50.25.21` en het bronpad `/ipp/port1`.

## <a name="login-items"></a>Aanmeldingsitems

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **Bestanden, mappen en aangepaste apps**: **voeg het pad toe** van een bestand, map, aangepaste app of systeem-app die u wilt openen wanneer een gebruiker zich aanmeldt bij het apparaat. Systeem-apps of apps die zijn gebouwd of aangepast voor uw organisatie, bevinden zich doorgaans in de map `Applications` en hebben een pad dat er als volgt uitziet: `/Applications/AppName.app`. 

  U kunt een groot aantal bestanden, mappen en apps toevoegen. Voer bijvoorbeeld het volgende in:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Let erop dat u het juiste pad opgeeft bij het toevoegen van een app, map of bestand. Niet alle items bevinden zich in de map `Applications`. Als een gebruiker een item naar een andere locatie verplaatst, verandert het pad. Dit verplaatste item wordt niet geopend wanneer de gebruiker zich aanmeldt.

## <a name="login-window"></a>Aanmeldingsvenster

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Deze instellingen zijn van toepassing op: Apparaatinschrijving en geautomatiseerde apparaatinschrijving

#### <a name="window-layout"></a>Vensterindeling

- **Aanvullende informatie op de menubalk weergeven**: Wanneer het tijdgebied op de menubalk wordt geselecteerd, wordt met **Toestaan** de hostnaam en macOS-versie getoond. **Niet geconfigureerd** (standaard): deze informatie wordt niet weergegeven op de menubalk.
- **Banner**: Voer een bericht in dat op het aanmeldingsscherm van het apparaat wordt weergegeven. Voer bijvoorbeeld gegevens over uw organisatie, een welkomstbericht, informatie over gevonden voorwerpen, enzovoort in.
- **Aanmeldingsindeling kiezen**: kies hoe gebruikers zich aanmelden op het apparaat. Uw opties zijn:
  - **Vragen om gebruikersnaam en wachtwoord** (standaard): Hiermee vereist u dat gebruikers een gebruikersnaam en wachtwoord invoeren.
  - **Een lijst met alle gebruikers weergeven, vragen om wachtwoord**: Hiermee vereist u dat gebruikers hun gebruikersnaam selecteren in een lijst met gebruikers en vervolgens hun wachtwoord invoeren. Configureer ook het volgende:

    - **Lokale gebruikers**: Met **Verbergen** worden de lokale gebruikersaccounts niet weergegeven in de lijst met gebruikers, waaronder mogelijk de standaard- en beheerdersaccounts. Alleen de netwerk- en systeemgebruikersaccounts worden weergegeven. **Niet geconfigureerd** (standaard): de lokale gebruikersaccounts worden wel weergegeven in de lijst met gebruikers.
    - **Mobiele accounts**: Met **Verbergen** worden mobiele accounts niet weergegeven in de lijst met gebruikers. **Niet geconfigureerd** (standaard): de mobiele accounts worden wel weergegeven in de lijst met gebruikers. Sommige mobiele accounts worden mogelijk weergegeven als netwerkgebruikers.
    - **Netwerkgebruikers**: Selecteer **Weergeven** om de netwerkgebruikers in de lijst met gebruikers weer te geven. **Niet geconfigureerd** (standaard): de netwerkgebruikers worden niet weergegeven in de lijst met gebruikers.
    - **Gebruikers met beheerdersrechten**: Met **Verbergen** worden de gebruikersaccounts met beheerdersrechten niet weergegeven in de lijst met gebruikers. **Niet geconfigureerd** (standaard): de gebruikers met beheerdersrechten worden wel weergegeven in de lijst met gebruikers.
    - **Andere gebruikers**: Selecteer **Weergeven** om de **Andere...** gebruikers weer te geven in de lijst met gebruikers. **Niet geconfigureerd** (standaard): de andere gebruikersaccounts worden niet weergegeven in de lijst met gebruikers.

#### <a name="login-screen-power-settings"></a>Energie-instellingen op het aanmeldingsscherm

- **Knop Afsluiten**: Met **Verbergen** wordt de knop Afsluiten niet weergegeven op het aanmeldingsscherm. **Niet geconfigureerd** (standaard): de knop Afsluiten wordt wel weergegeven.
- **Knop Opnieuw opstarten**: Met **Verbergen** wordt de knop Opnieuw opstarten niet weergegeven op het aanmeldingsscherm. **Niet geconfigureerd** (standaard): de knop Opnieuw opstarten wordt wel weergegeven.
- **Knop Slaapstand**: Met **Verbergen** wordt de knop Slaapstand niet weergegeven op het aanmeldingsscherm. **Niet geconfigureerd** (standaard): de knop Slaapstand wordt wel weergegeven.

#### <a name="other"></a>Overige

- **Gebruikersaanmelding via console uitschakelen**: Met **Uitschakelen** wordt de macOS-opdrachtregel verborgen die wordt gebruikt voor aanmelding. Voor standaardgebruikers kunt u deze instelling het beste **Uitschakelen**. **Niet geconfigureerd** (standaard): geavanceerde gebruikers kunnen zich aanmelden via de macOS-opdrachtregel. Om de consolemodus in te schakelen moeten gebruikers `>console` invoeren in het veld Gebruikersnaam en zich verifiëren in het consolevenster.

#### <a name="apple-menu"></a>Apple-menu

Nadat gebruikers zich bij de apparaten hebben aangemeld, bepalen de volgende instellingen wat ze kunnen doen.

- **Afsluiten deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Afsluiten** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Afsluiten** wel selecteren op het apparaat.
- **Opnieuw opstarten deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Opnieuw opstarten** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Opnieuw opstarten** wel selecteren op het apparaat.
- **Uitschakelen deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Uitschakelen** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Uitschakelen** wel selecteren op het apparaat.
- **Afmelden deactiveren** (macOS 10.13 en hoger): Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Afmelden** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Afmelden** wel selecteren op het apparaat.
- **Vergrendelingsscherm deactiveren** (macOS 10.13 en hoger): Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Vergrendelingsscherm** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Scherm vergrendelen** wel selecteren op het apparaat.

## <a name="single-sign-on-app-extension"></a>App-extensie voor eenmalige aanmelding

Deze functie is van toepassing op:

- macOS 10.15 of hoger

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen 

- **Type app-extensie voor SSO**: kies Referentie als het type app-extensie voor SSO. Uw opties zijn:

  - **Niet geconfigureerd**: app-extensies worden niet gebruikt. Als u een app-extensie wilt uitschakelen, stelt u het type app-extensie voor SSO in op **Niet geconfigureerd**.
  - **Omleiding**: gebruik een algemene, aanpasbare app-extensie Omleiding om eenmalige aanmelding uit te voeren met moderne verificatiestromen. Zorg ervoor dat u de extensie- en team-id van de app-extensie van uw organisatie kent.
  - **Referentie**: gebruik een algemene, aanpasbare app-extensie Referentie voor het uitvoeren van eenmalige aanmelding met uitdaging-en-reactie-verificatiestromen. Zorg ervoor dat u de extensie-id en de team-id van de app-extensie van uw organisatie kent.  
  - **Kerberos**: gebruik de ingebouwde Kerberos-extensie van Apple, die is opgenomen in macOS Catalina 10.15 en hoger. Deze optie is een Kerberos-versie van de app-extensie **Referentie**.

  > [!TIP]
  > Met de typen **Omleiding** en **Referentie** voegt u uw eigen configuratiewaarden toe om door te geven aan de extensie. Als u het type **Referentie** gebruikt, kunt u overwegen om de ingebouwde configuratie-instellingen te gebruiken die Apple heeft opgenomen in het type **Kerberos**.

- **Extensie-id** (Omleiding en Referentie): voer de bundel-id in waarmee de app-extensie voor SSO wordt geïdentificeerd, zoals `com.apple.ssoexample`.
- **Team-id** (Omleiding en Referentie): voer de team-id in van uw app-extensie voor SSO. Een team-id is een alfanumerieke tekenreeks van 10 tekens (cijfers en letters) die wordt gegenereerd met Apple, zoals `ABCDE12345`. 

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

- **Automatisch opsporen** (alleen Kerberos): als u hier **Blokkeren** instelt, maakt de Kerberos-extensie niet automatisch gebruik van LDAP en DNS om de Active Directory-sitenaam te bepalen. **Niet geconfigureerd** (standaard): staat toe dat de extensie de Active Directory-sitenaam automatisch kan vinden.
- **Wachtwoordwijzigingen** (alleen Kerberos): kies **Blokkeren** als u wilt voorkomen dat gebruikers de wachtwoorden kunnen wijzigen waarmee ze zich aanmelden bij de door u ingevoerde domeinen. **Niet geconfigureerd** (standaard): staat toe dat wachtwoorden worden gewijzigd.  
- **Wachtwoordsynchronisatie** (alleen Kerberos): kies **Inschakelen** om de lokale wachtwoorden van uw gebruikers te synchroniseren met Azure AD. **Niet geconfigureerd** (standaard): schakelt wachtwoordsynchronisatie met Azure AD uit. Gebruik deze instelling als alternatief of als back-up voor SSO. Deze instelling werkt niet als gebruikers zijn aangemeld met een mobiel Apple-account.
- **Active Directory-wachtwoordcomplexiteit van Windows Server** (alleen Kerberos): kies **Vereisen** om gebruikerswachtwoorden af te dwingen die voldoen aan de vereisten voor wachtwoordcomplexiteit van Active Directory. Zie [Wachtwoorden moeten voldoen aan complexiteitsvereisten](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) voor meer informatie. **Niet geconfigureerd** (standaard): gebruikers hoeven niet te voldoen aan de wachtwoordvereisten van Active Directory.
- **Minimale wachtwoordlengte** (alleen Kerberos): voer het minimale aantal tekens op waaruit het wachtwoord van een gebruiker moet bestaan. **Niet geconfigureerd** (standaard): er wordt geen minimale wachtwoordlengte afgedwongen voor de gebruikers.
- **Limiet voor opnieuw gebruiken van wachtwoord** (alleen Kerberos): voer het aantal nieuwe wachtwoorden in, van 1 tot 24, dat moet worden gebruikt voordat een eerder gebruikt wachtwoord opnieuw kan worden gebruikt in het domein. **Niet geconfigureerd** (standaard): dwingt geen limiet voor het opnieuw gebruiken van wachtwoorden af.
- **Minimale wachtwoordduur** (alleen Kerberos): geef het aantal dagen op dat een wachtwoord moet worden gebruikt in het domein voordat een gebruiker het kan wijzigen. **Niet geconfigureerd** (standaard): dwingt geen minimale duur voor wachtwoorden af voordat deze kunnen worden gewijzigd.
- **Melding voor verlopen van wachtwoorden** (alleen Kerberos): voer het aantal dagen vóór het verlopen van een wachtwoord in dat gebruikers op de hoogte worden gesteld dat hun wachtwoord verloopt. **Niet geconfigureerd** (standaard): `15` dagen.
- **Wachtwoordverlooptijd** (alleen Kerberos): Geef op na hoeveel dagen het wachtwoord voor het apparaat moet worden gewijzigd. **Niet geconfigureerd** (standaard): dit betekent dat gebruikerswachtwoorden nooit verlopen.
- **URL voor het wijzigen van het wachtwoord** (alleen Kerberos): voer de URL in die wordt gestart wanneer de gebruiker een Kerberos-wachtwoordwijziging initieert.
- **Principal-naam** (alleen Kerberos): voer de gebruikersnaam in van de Kerberos-principal. U hoeft de realmnaam niet op te nemen. In `user@contoso.com` is `user` bijvoorbeeld de principal-naam en `contoso.com` de realmnaam.

  > [!TIP]
  > - U kunt ook variabelen gebruiken in de principal-naam door accolades `{{ }}` in te voeren. Voer bijvoorbeeld `Username: {{username}}` in om de gebruikersnaam weer te geven. 
  > - Wees echter voorzichtig met het vervangen van variabelen, want variabelen worden niet gevalideerd in de UI en zijn hoofdlettergevoelig. Zorg dat u de juiste informatie invoert.
  
- **Active Directory-sitecode** (alleen Kerberos): voer de naam in van de Active Directory-site die door de Kerberos-extensie moet worden gebruikt. Waarschijnlijk hoeft u deze waarde niet te wijzigen, omdat de Kerberos-extensie de Active Directory-sitecode mogelijk automatisch kan vinden.
- **Cachenaam** (alleen Kerberos): voer de naam in van de GSS (generieke beveiligingsservices) van de Kerberos-cache. Waarschijnlijk hoeft u deze waarde niet in te stellen.  
- **Bericht voor wachtwoordvereisten** (alleen Kerberos): voer een tekstversie in van de wachtwoordvereisten van uw organisatie die voor gebruikers worden weergegeven. Het bericht wordt weergegeven als u geen vereisten voor wachtwoordcomplexiteit van Active Directory nodig hebt of geen minimale wachtwoordlengte opgeeft.  
- **App-bundel-id's** (alleen Kerberos): u kunt de app-bundel-id's **toevoegen** die moeten gebruikmaken van eenmalige aanmelding op uw apparaten. Aan deze apps wordt toegang verleend tot de Kerberos TGT (Ticket Granting Ticket), het verificatieticket, en met deze apps worden gebruikers geverifieerd bij de services waarvoor ze een toegangsmachtiging hebben.
- **Toewijzen van domeinrealm** (alleen Kerberos): u kunt de domein-DNS-achtervoegsels **toevoegen** die moeten worden toegewezen aan uw realm. Gebruik deze instelling als de DNS-namen van de hosts niet overeenkomen met de realmnaam. Waarschijnlijk hoeft u deze aangepaste domein-naar-realm-toewijzing niet te maken.
- **PKINIT-certificaat** (alleen Kerberos): **selecteer** het PIKNIT-certificaat (Public Key Cryptography for Initial Authentication) dat kan worden gebruikt voor Kerberos-verificatie. U kunt kiezen uit een [PKCS](../protect/certficates-pfx-configure.md)- of [SCEP](../protect/certificates-scep-configure.md)-certificaat dat u hebt toegevoegd in Intune. Raadpleeg [Certificaten gebruiken voor verificatie in Microsoft Intune](../protect/certificates-configure.md) voor meer informatie over certificaten.

## <a name="associated-domains"></a>Gekoppelde domeinen

In Intune kunt u het volgende doen:

- Een groot aantal app-naar-domein-koppelingen toevoegen.
- Een groot aantal domeinen koppelen aan dezelfde app.

Deze functie is van toepassing op:

- macOS 10.15 of hoger

### <a name="settings-apply-to-all-enrollment-types"></a>Deze instellingen zijn van toepassing op: Alle inschrijvingstypen

- **App-id**: voer de app-id in van de app die u wilt koppelen aan een website. De app-id bevat de team-id en een bundel-id: `TeamID.BundleID`.

  De team-id is een alfanumerieke tekenreeks van 10 tekens (letters en cijfers) die door Apple wordt gegenereerd voor uw app-ontwikkelaars, zoals `ABCDE12345`. [Zoek uw team-id](https://help.apple.com/developer-account/#/dev55c3c710c) : (opent de website van Apple) biedt meer informatie.

  De bundel-id is een unieke identificatie van de app en heeft doorgaans de omgekeerde notatie van de domeinnaam. De bundel-id van Finder is bijvoorbeeld `com.apple.finder`. Gebruik het AppleScript in Terminal om de bundel-id te vinden:

  `osascript -e 'id of app "ExampleApp"'`

- **Domein**: voer het websitedomein in dat u aan een app wilt koppelen. Het domein bevat een servicetype en een volledig gekwalificeerde hostnaam, zoals `webcredentials:www.contoso.com`.

  U kunt alle subdomeinen van een gekoppeld domein vergelijken door `*.` (een asterisk-jokerteken en een punt) vóór het domein in te voeren. De punt is vereist. Exacte domeinen hebben een hogere prioriteit dan domeinen met een jokerteken. Patronen van bovenliggende domeinen worden vergeleken *als* er geen overeenkomst wordt gevonden in het volledig gekwalificeerde subdomein.

  Mogelijke servicetypen zijn:

  - **authsrv**: App-extensie voor eenmalige aanmelding
  - **applink**: universele koppeling
  - **webcredentials**: automatisch doorvoeren van wachtwoorden

- **Toevoegen**: selecteer deze optie om uw apps en gekoppelde domeinen toe te voegen.

> [!TIP]
> Als u problemen wilt oplossen, opent u **Systeemvoorkeuren** > **Profielen** op uw macOS-apparaat. Controleer of het profiel dat u hebt gemaakt, voorkomt in de lijst met apparaatprofielen. Zo ja, dan controleert u of de **configuratie voor gekoppelde domeinen** in het profiel voorkomt en de juiste app-id en domeinen bevat.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook apparaatfuncties configureren in [iOS/iPadOS](ios-device-features-settings.md).
