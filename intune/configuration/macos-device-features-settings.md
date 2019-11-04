---
title: Instellingen van apparaatfuncties voor macOS in Microsoft Intune - Azure | Microsoft Docs
description: Zie de instellingen om macOS-apparaten te configureren voor AirPrint en om energie-instellingen op het aanmeldingsvenster van Microsoft Intune weer te geven of te verbergen. Raadpleeg de stappen om het IP-adres, het pad en de poortinstellingen van een AirPrint-server in uw netwerk op te halen. Gebruik deze instellingen in een apparaatconfiguratieprofiel om functies voor macOS-apparaten te configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/22/2019
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
ms.openlocfilehash: 3d0cff4ad624d35843f3388535b60549d1893eeb
ms.sourcegitcommit: c38a856725993a4473ada75e669a57f75ab376f8
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 10/30/2019
ms.locfileid: "73143153"
---
# <a name="macos-device-feature-settings-in-intune"></a>Instellingen van apparaatfuncties voor macOS in Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune bevat een aantal ingebouwde instellingen om functies op uw macOS-apparaten aan te passen. Zo kunnen beheerders printer printers toevoegen, kiezen hoe gebruikers zich aanmelden, de energiebeheer functies configureren, eenmalige aanmelding en meer gebruiken.

Gebruik deze functies om macOS-apparaten te beheren als onderdeel van uw Mobile Device Management-oplossing (MDM).

Dit artikel beschrijft deze instellingen en wat elke instelling doet. Het beschrijft tevens de stappen voor het ophalen van het IP-adres, het pad en de poort van AirPrint-printers via de Terminal-app (emulator). Ga voor meer informatie over de functies van het apparaat naar [instellingen voor Ios-of macOS-apparaten toevoegen](device-features-configure.md).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een macOS-apparaatconfiguratieprofiel](device-features-configure.md).

> [!NOTE]
> Deze instellingen zijn van toepassing op verschillende inschrijvings typen, waarbij sommige instellingen van toepassing zijn op alle inschrijvings opties. Zie voor meer informatie over de verschillende inschrijvings typen [macOS-inschrijving](../enrollment/macos-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie 

- **IP-adres**: voer het IPv4- of IPv6-adres van de printer in. Als u hostnamen gebruikt om printers te identificeren, haalt u het IP-adres op door de printer in de Terminal-app te pingen. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
- **Pad**: voer het pad van de printer in. Het pad is doorgaans `ipp/print` voor printers in uw netwerk. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
- **Poort** (iOS 11.0 en hoger): Voer de luisterpoort van de AirPrint-bestemming in. Als u deze eigenschap leeg laat, maakt AirPrint gebruik van de standaardpoort.
- **TLS** (iOS 11.0 en hoger): selecteer **Inschakelen** om AirPrint-verbindingen te beveiligen met Transport Layer Security (TLS).

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

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **Bestanden, mappen en aangepaste apps**: Voeg het pad **toe** van een bestand, map, aangepaste app of systeem-app die u wilt openen wanneer een gebruiker zich aanmeldt bij het apparaat. Systeem-apps of apps die zijn gebouwd of aangepast voor uw organisatie, bevinden zich doorgaans in de map `Applications`, met een pad dat vergelijkbaar is met `/Applications/AppName.app`. 

  U kunt veel bestanden, mappen en apps toevoegen. Voer bijvoorbeeld het volgende in:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Zorg ervoor dat u het juiste pad opgeeft bij het toevoegen van een app, map of bestand. Niet alle items bevinden zich in de map `Applications`. Als een gebruiker een item verplaatst van de ene locatie naar een andere, verandert het pad. Dit verplaatste item wordt niet geopend wanneer de gebruiker zich aanmeldt.

## <a name="login-window"></a>Aanmeldingsvenster

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Instellingen zijn van toepassing op: registratie van apparaten en automatische apparaatregistratie 

#### <a name="window-layout"></a>Vensterindeling

- **Aanvullende informatie op de menubalk weergeven**: Wanneer het tijdgebied op de menubalk wordt geselecteerd, wordt met **Toestaan** de hostnaam en macOS-versie getoond. **Niet geconfigureerd** (standaard): deze informatie wordt niet weergegeven op de menubalk.
- **Banner**: Voer een bericht in dat op het aanmeldingsscherm van het apparaat wordt weergegeven. Voer bijvoorbeeld gegevens over uw organisatie, een welkomstbericht, informatie over gevonden voorwerpen, enzovoort in.
- **Aanmeldingsindeling kiezen**: Kies hoe gebruikers zich aanmelden op het apparaat. Uw opties zijn:
  - **Vragen om gebruikersnaam en wachtwoord** (standaard): hiermee vereist u dat gebruikers een gebruikersnaam en wachtwoord invoeren.
  - **Alle gebruikers weergeven, vragen om wachtwoord**: hiermee vereist u dat gebruikers hun gebruikersnaam selecteren in een lijst met gebruikers en vervolgens hun wachtwoord invoeren. Configureer ook het volgende:

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

- **Gebruikersaanmelding via console uitschakelen**: Met **Uitschakelen** wordt de macOS-opdrachtregel die wordt gebruikt voor aanmelding verborgen. Voor standaardgebruikers kunt u deze instelling het beste **Uitschakelen**. **Niet geconfigureerd** (standaard): geavanceerde gebruikers kunnen zich aanmelden via de macOS-opdrachtregel. Om de consolemodus in te schakelen moeten gebruikers `>console` invoeren in het veld Gebruikersnaam en zich verifiëren in het consolevenster.

#### <a name="apple-menu"></a>Apple-menu

Nadat gebruikers zich bij de apparaten hebben aangemeld, bepalen de volgende instellingen wat ze kunnen doen.

- **Afsluiten deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Afsluiten** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Afsluiten** wel selecteren op het apparaat.
- **Opnieuw opstarten deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Opnieuw opstarten** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Opnieuw opstarten** wel selecteren op het apparaat.
- **Uitschakelen deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Uitschakelen** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Uitschakelen** wel selecteren op het apparaat.
- **Afmelden deactiveren** (macOS 10.13 en hoger): Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Afmelden** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Afmelden** wel selecteren op het apparaat.
- **Vergrendelingsscherm deactiveren** (macOS 10.13 en hoger): Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Scherm vergrendelen** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Scherm vergrendelen** wel selecteren op het apparaat.

## <a name="single-sign-on-app-extension"></a>App-extensie voor eenmalige aanmelding

Deze functie is van toepassing op:

- macOS 10.15 of hoger

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen 

- **Extensie type voor SSO-app**: Kies het type referentie-SSO-app-extensie. Uw opties zijn:

  - **Niet geconfigureerd**: app-extensies worden niet gebruikt. Als u een SSO-extensie wilt uitschakelen, schakelt u het extensie type voor SSO-apps van **Kerberos** of **referentie** in op **niet geconfigureerd**.
  - **Referentie**: gebruik een algemene, aanpas bare referentie-app-extensie om SSO te gebruiken. Zorg ervoor dat u de extensie-ID en de team-ID voor de SSO-app-extensie van uw organisatie kent.  
  - **Kerberos**: gebruik de ingebouwde Kerberos-uitbrei ding van Apple, die is opgenomen in macOS Catalina 10,15 en hoger. Deze optie is een Kerberos-specifieke versie van de extensie voor **referentie** -apps.

  > [!TIP]
  > Met het **referentie** type voegt u uw eigen configuratie waarden toe om de extensie door te geven. In plaats daarvan kunt u gebruikmaken van ingebouwde configuratie-instellingen van Apple in het **Kerberos** -type.

- **Extensie-id** (alleen referentie): Geef de bundel-id op waarmee uw SSO-app-extensie wordt geïdentificeerd, zoals `com.apple.ssoexample`.
- **Team-ID** (alleen referentie): Voer de team-ID van de extensie van uw SSO-app in. Een team-ID is een alfanumerieke teken reeks van 10 tekens (cijfers en letters) die wordt gegenereerd door Apple, zoals `ABCDE12345`. 

  [Zoek uw team-ID](https://help.apple.com/developer-account/#/dev55c3c710c) (Open de website van Apple) voor meer informatie.

- **Realm**: Voer de naam in van uw verificatie-realm. De realm-naam moet worden gekapitaliseerd, zoals `CONTOSO.COM`. Normaal gesp roken is uw realm-naam hetzelfde als de DNS-domein naam, maar in alle hoofd letters.
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

- **Autodis cover** (alleen Kerberos): als u deze instelt op **blok keren**, gebruikt de Kerberos-extensie niet automatisch LDAP en DNS om de Active Directory site naam te bepalen. **Niet geconfigureerd** (standaard) Hiermee staat u toe dat de extensie de Active Directory site naam automatisch kan vinden.
- **Wachtwoord wijzigingen** (alleen Kerberos): de **blok kering** voor komt dat gebruikers de wacht woorden wijzigen die ze gebruiken om zich aan te melden bij de domeinen die u hebt ingevoerd. **Niet geconfigureerd** (standaard) Hiermee kunnen wacht woorden worden gewijzigd.  
- **Wachtwoord synchronisatie** (alleen Kerberos): Kies **inschakelen** om de lokale wacht woorden van uw gebruikers te synchroniseren met Azure AD. **Niet geconfigureerd** (standaard) Hiermee schakelt u wachtwoord synchronisatie met Azure AD uit. Gebruik deze instelling als alternatief of als back-up naar SSO. Deze instelling werkt niet als gebruikers zijn aangemeld met een Apple Mobile-account.
- **Wachtwoord complexiteit van Windows Server Active Directory** (alleen Kerberos): Kies **vereisen** dat wacht woorden van gebruikers geforceerd voldoen aan de vereisten voor wachtwoord complexiteit van Active Directory. Zie [wacht woord moet voldoen aan complexiteits vereisten](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) voor meer informatie. **Niet geconfigureerd** (standaard) vereist dat gebruikers niet voldoen aan de vereisten van Active Directory-wacht woord.
- **Minimale wachtwoord lengte** (alleen Kerberos): Geef het minimum aantal tekens op waaruit het wacht woord van een gebruiker kan bestaan. **Niet geconfigureerd** (standaard) dwingt geen minimale wachtwoord lengte af voor de gebruikers.
- **Limiet voor het opnieuw gebruiken van wacht woorden** (alleen Kerberos): Voer het aantal nieuwe wacht woorden in, van 1-24, dat moet worden gebruikt totdat een vorig wacht woord opnieuw kan worden gebruikt in het domein. **Niet geconfigureerd** (standaard) dwingt de limiet voor het opnieuw instellen van wacht woorden niet af.
- **Minimale wachtwoord duur** (alleen Kerberos): Geef het aantal dagen op dat een wacht woord moet worden gebruikt voor het domein voordat een gebruiker het kan wijzigen. **Niet geconfigureerd** (standaard) dwingt geen minimale leeftijd van wacht woorden af voordat deze kunnen worden gewijzigd.
- **Melding over verlopen van wacht woord** (alleen Kerberos): Voer het aantal dagen in waarna een wacht woord verloopt dat gebruikers op de hoogte worden gesteld dat hun wacht woord verloopt. **Niet geconfigureerd** (standaard) gebruikt `15` dagen.
- **Wachtwoord verloopt** (alleen Kerberos): voer het aantal dagen in waarna het wachtwoord voor het apparaat moet worden gewijzigd. **Niet geconfigureerd** (standaard) betekent dat gebruikers wachtwoorden nooit verlopen.
- **Principal-naam** (alleen Kerberos): Voer de gebruikers naam van de Kerberos-principal in. U hoeft de realm-naam niet op te vermelden. In `user@contoso.com` is `user` bijvoorbeeld de principal-naam en is `contoso.com` de realm-naam.
- **Active Directory site code** (alleen Kerberos): Voer de naam in van de Active Directory site die de Kerberos-uitbrei ding moet gebruiken. U hoeft deze waarde mogelijk niet te wijzigen, omdat de Kerberos-extensie de Active Directory site code mogelijk automatisch vindt.
- **Cache naam** (alleen Kerberos): Voer de naam in van de algemene beveiligings Services (gss) van de Kerberos-cache. U hoeft deze waarde waarschijnlijk niet in te stellen.  
- **Bericht voor wachtwoord vereisten** (alleen Kerberos): Voer een tekst versie in van de wachtwoord vereisten van uw organisatie die voor gebruikers worden weer gegeven. Het bericht wordt weer gegeven als u geen vereisten voor wachtwoord complexiteit van Active Directory nodig hebt of geen minimale wachtwoord lengte opgeeft.  
- **App-bundel-id's** (alleen Kerberos): Voeg de app-bundel-id's **toe** die gebruikmaken van eenmalige aanmelding op uw apparaten. Aan deze apps wordt toegang verleend tot de Kerberos ticket granting ticket, het verificatie ticket en de verificatie van gebruikers voor de services waartoe ze toegang hebben.
- **Domein realm-toewijzing** (alleen Kerberos): Voeg de DNS-achtervoegsels van het domein **toe** die moeten worden toegewezen aan uw realm. Gebruik deze instelling als de DNS-namen van de hosts niet overeenkomen met de realm-naam. U hoeft deze aangepaste domein-naar-realm-toewijzing waarschijnlijk niet te maken.

## <a name="associated-domains"></a>Gekoppelde domeinen

In Intune kunt u het volgende doen:

- Veel app-to-Domain-koppelingen toevoegen.
- Een groot aantal domeinen koppelen aan dezelfde app.

Deze functie is van toepassing op:

- macOS 10.15 of hoger

### <a name="settings-apply-to-all-enrollment-types"></a>Instellingen zijn van toepassing op: alle inschrijvings typen

- **App-ID**: Voer de app-id in van de app die u wilt koppelen aan een website. De app-id bevat de team-ID en een bundel-ID: `TeamID.BundleID`.

  De team-ID is een alfanumerieke teken reeks van 10 tekens (letters en cijfers) die door Apple wordt gegenereerd voor uw app-ontwikkel aars, zoals `ABCDE12345`. [Zoek uw team-ID](https://help.apple.com/developer-account/#/dev55c3c710c)   (Open de website van Apple) voor meer informatie.

  De bundel-ID is een unieke identificatie van de app en wordt doorgaans ingedeeld in omgekeerde domeinnaam notatie. De bundel-ID van Finder is bijvoorbeeld `com.apple.finder`. Gebruik de Apple script in Terminal om de bundel-ID te vinden:

  `osascript -e 'id of app "ExampleApp"'`

- **Domein**: Voer het website domein in dat u aan een app wilt koppelen. Het domein bevat een service type en een volledig gekwalificeerde hostnaam, zoals `webcredentials:www.contoso.com`.

  U kunt alle subdomeinen van een gekoppeld domein vergelijken door `*.` (een asterisk-Joker teken en een punt) voor het begin van het domein in te voeren. De periode is vereist. Exacte domeinen hebben een hogere prioriteit dan joker tekens. Patronen van bovenliggende domeinen worden dus vergeleken *als* er geen overeenkomst wordt gevonden in het volledig gekwalificeerde subdomein.

  Het Service type kan zijn:

  - **authsrv** : app-extensie voor eenmalige aanmelding
  - **applink**: Universele koppeling
  - **Webreferenties**: wacht woord automatisch door voeren

- **Toevoegen**: Selecteer deze optie om uw apps en gekoppelde domeinen toe te voegen.

> [!TIP]
> Als u problemen wilt oplossen, opent u **systeem voorkeuren**  > **profielen**op uw macOS-apparaat. Bevestig dat het profiel dat u hebt gemaakt, zich in de lijst met apparaatprofielen bevindt. Als dit wordt vermeld, moet u ervoor zorgen dat de configuratie van de **gekoppelde domeinen** zich in het profiel bevindt en dat de juiste app-id en domeinen zijn opgenomen.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook apparaatfuncties configureren op [IOS](ios-device-features-settings.md).
