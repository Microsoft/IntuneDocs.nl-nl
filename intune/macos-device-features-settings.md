---
title: Instellingen van apparaatfuncties voor macOS in Microsoft Intune - Azure | Microsoft Docs
description: Zie de instellingen om macOS-apparaten te configureren voor AirPrint en om energie-instellingen op het aanmeldingsvenster van Microsoft Intune weer te geven of te verbergen. Raadpleeg de stappen om het IP-adres, het pad en de poortinstellingen van een AirPrint-server in uw netwerk op te halen. Gebruik deze instellingen in een apparaatconfiguratieprofiel om functies voor macOS-apparaten te configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 63f2832dd321425efe8092f1bb12dd0d479ef71b
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 08/16/2019
ms.locfileid: "69549935"
---
# <a name="macos-device-feature-settings-in-intune"></a>Instellingen van apparaatfuncties voor macOS in Intune

Intune bevat een aantal ingebouwde instellingen om functies op uw macOS-apparaten aan te passen. Dit artikel beschrijft deze instellingen en wat elke instelling doet. Het beschrijft tevens de stappen voor het ophalen van het IP-adres, het pad en de poort van AirPrint-printers via de Terminal-app (emulator).

Deze functie is van toepassing op:

- macOS

Gebruik deze instellingen als onderdeel van de MDM-oplossing (Mobile Device Management) om een banner te maken, te kiezen hoe gebruikers zich aanmelden, een AirPrint-server toe te voegen en meer.

Deze instellingen worden toegevoegd aan een apparaatconfiguratieprofiel in Intune en vervolgens toegewezen aan of geïmplementeerd op uw macOS-apparaten.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een macOS-apparaatconfiguratieprofiel](device-features-configure.md).

## <a name="airprint"></a>AirPrint

- **IP-adres**: voer het IPv4- of IPv6-adres van de printer in. Als u hostnamen gebruikt om printers te identificeren, haalt u het IP-adres op door de printer in de Terminal-app te pingen. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
- **Pad**: voer het pad van de printer in. Het pad is doorgaans `ipp/print` voor printers in uw netwerk. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
- **Poort** (iOS 11.0 en hoger): Voer de luisterpoort van de AirPrint-bestemming in. Als u deze eigenschap leeg laat, maakt AirPrint gebruik van de standaardpoort.
- **TLS** (iOS 11.0 en hoger): selecteer **Inschakelen** om AirPrint-verbindingen te beveiligen met Transport Layer Security (TLS).

**Voeg** de AirPrint-server toe. U kunt veel AirPrint-servers toevoegen.

- **Importeren** (optioneel): U kunt ook een door komma's gescheiden bestand (.csv) met een lijst met AirPrint-printers **Importeren**. Nadat u AirPrint-printers aan Intune hebt toegevoegd, kunt u bovendien deze lijst **exporteren**.

Selecteer **OK** om uw wijzigingen op te slaan.

### <a name="get-the-ip-address-and-path"></a>IP-adres en pad ophalen

Om AirPrinter-servers toe te voegen, hebt u het IP-adres van de printer, het bronpad en de poort nodig. De volgende stappen laten zien hoe u aan deze informatie komt.

1. Open op een Mac die verbonden is met hetzelfde lokale netwerk (subnet) als de AirPrint-printers de **Terminal** (via **/Programma's/Hulpprogramma's**).
2. Typ in de Terminal-app `ippfind` en selecteer Enter.

    Noteer de printergegevens. Er wordt bijvoorbeeld iets in de trant van `ipp://myprinter.local.:631/ipp/port1` geretourneerd. Het eerste deel is de naam van de printer. Het laatste deel (`ipp/port1`) is het bronpad.

3. Typ in de terminal `ping myprinter.local` en selecteer Enter.

   Noteer het IP-adres. Er wordt bijvoorbeeld iets in de trant van `PING myprinter.local (10.50.25.21)` geretourneerd.

4. Gebruik de waarden van het IP-adres en het bronpad. In dit voorbeeld is het IP-adres `10.50.25.21` en het bronpad `/ipp/port1`.

## <a name="login-items"></a>Aanmeldings items

- **Bestanden, mappen en aangepaste apps**: Voeg het pad **toe** van een bestand, map, aangepaste app of systeem-app die u wilt openen wanneer een gebruiker zich aanmeldt bij het apparaat. Systeem-apps of apps die zijn gebouwd of aangepast voor uw organisatie, bevinden zich doorgaans in de `Applications` map, met een pad dat `/Applications/AppName.app`vergelijkbaar is met. 

  U kunt veel bestanden, mappen en apps toevoegen. Voer bijvoorbeeld het volgende in:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Zorg ervoor dat u het juiste pad opgeeft bij het toevoegen van een app, map of bestand. Niet alle items bevinden zich `Applications` in de map. Als een gebruiker een item verplaatst van de ene locatie naar een andere, verandert het pad. Dit verplaatste item wordt niet geopend wanneer de gebruiker zich aanmeldt.

## <a name="login-window"></a>Aanmeldingsvenster

### <a name="window-layout"></a>Vensterindeling

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

### <a name="login-screen-power-settings"></a>Energie-instellingen op het aanmeldingsscherm

- **Knop Afsluiten**: Met **Verbergen** wordt de knop Afsluiten niet weergegeven op het aanmeldingsscherm. **Niet geconfigureerd** (standaard): de knop Afsluiten wordt wel weergegeven.
- **Knop Opnieuw opstarten**: Met **Verbergen** wordt de knop Opnieuw opstarten niet weergegeven op het aanmeldingsscherm. **Niet geconfigureerd** (standaard): de knop Opnieuw opstarten wordt wel weergegeven.
- **Knop Slaapstand**: Met **Verbergen** wordt de knop Slaapstand niet weergegeven op het aanmeldingsscherm. **Niet geconfigureerd** (standaard): de knop Slaapstand wordt wel weergegeven.

### <a name="other"></a>Overige

- **Gebruikersaanmelding via console uitschakelen**: Met **Uitschakelen** wordt de macOS-opdrachtregel die wordt gebruikt voor aanmelding verborgen. Voor standaardgebruikers kunt u deze instelling het beste **Uitschakelen**. **Niet geconfigureerd** (standaard): geavanceerde gebruikers kunnen zich aanmelden via de macOS-opdrachtregel. Om de consolemodus in te schakelen moeten gebruikers `>console` invoeren in het veld Gebruikersnaam en zich verifiëren in het consolevenster.

### <a name="apple-menu"></a>Apple-menu

Nadat gebruikers zich bij de apparaten hebben aangemeld, bepalen de volgende instellingen wat ze kunnen doen.

- **Afsluiten deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Afsluiten** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Afsluiten** wel selecteren op het apparaat.
- **Opnieuw opstarten deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Opnieuw opstarten** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Opnieuw opstarten** wel selecteren op het apparaat.
- **Uitschakelen deactiveren**: Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Uitschakelen** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Uitschakelen** wel selecteren op het apparaat.
- **Afmelden deactiveren** (macOS 10.13 en hoger): Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Afmelden** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Afmelden** wel selecteren op het apparaat.
- **Vergrendelingsscherm deactiveren** (macOS 10.13 en hoger): Met **Uitschakelen** wordt voorkomen dat gebruikers na aanmelding de optie **Scherm vergrendelen** selecteren. **Niet geconfigureerd** (standaard): gebruikers kunnen de menuopdracht **Scherm vergrendelen** wel selecteren op het apparaat.

Selecteer **OK** om uw wijzigingen op te slaan.

## <a name="next-steps"></a>Volgende stappen

- Bekijk alle instellingen voor [iOS](ios-device-features-settings.md)-apparaten.
- [Wijs dit profiel toe](device-profile-assign.md) aan uw groepen en [controleer de status ervan](device-profile-monitor.md).
