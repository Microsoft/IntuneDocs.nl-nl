---
title: Beleidsinstellingen voor Android en Samsung KNOX
description: Beleidsregels maken voor het beheren van instellingen en functies op Android-apparaten die u met Intune beheert.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e1b18486f84bb5d4d47caceb871bf6884b9b8f89
ms.sourcegitcommit: 53a1f5226d1e1172f013a1b192321dde610b2d6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/06/2017
---
# <a name="android-and-samsung-knox-standard-policy-settings-in-microsoft-intune"></a>Beleidsinstellingen voor Android en Samsung KNOX Standard in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune biedt diverse ingebouwde algemene instellingen die u op Android-apparaten kunt configureren. Daarnaast kunt u OMA-URI-waarden (Open Mobile Alliance Uniform Resource Identifier) opgeven om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.

## <a name="general-configuration-policy"></a>Algemeen configuratiebeleid

Gebruik het Intune **algemene Android-configuratiebeleid** om instellingen te configureren voor:

-   **Beveiligingsinstellingen voor mobiele apparaten**: hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u een reeks functies en functionaliteiten op het apparaat kunt beheren.

-   **Kioskmodus** (alleen voor Samsung KNOX Standard-apparaten): hiermee kunt u een apparaat zodanig vergrendelen dat alleen bepaalde functies beschikbaar zijn. U kunt bijvoorbeeld toestaan dat een apparaat slechts één beheerde app uitvoert die u opgeeft, of kunt u de volumeknoppen op een apparaat uitschakelen. Deze instellingen kunnen worden gebruikt voor een demonstratiemodel van een apparaat of voor een apparaat dat is toegewezen aan slechts één functie, zoals een verkooppuntapparaat.

-   **Compatibele en niet-compatibele apps**: hiermee geeft u een lijst op met apps die compatibel of niet compatibel zijn in uw bedrijf. Op Android- en iOS-apparaten kan het **Rapport niet-compatibele apps** worden gebruikt om de compatibiliteit van apps die u in de lijst hebt opgegeven, te vergelijken met de apps die gebruikers hebben geïnstalleerd. Met het rapport kan de installatie van de app niet daadwerkelijk worden geblokkeerd.

> [!TIP]
> U kunt voorwaarden voor gebruikers configureren om ervoor te zorgen dat ze ermee instemmen dat alle apps op hun apparaat, waaronder persoonlijke apps, worden geëvalueerd, en dat niet-compatibele apps worden geblokkeerd of gerapporteerd als niet-compatibel. Gebruikers moeten deze voorwaarden accepteren voordat ze hun apparaat kunnen registreren en de bedrijfsportal kunnen gebruiken om apps op te halen. Zie [Beleidsinstellingen voor voorwaarden in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md) voor meer informatie over het gebruik van voorwaarden.

Als de instelling die u zoekt niet wordt weergegeven in dit onderwerp, kunt u deze maken met behulp van een aangepast Android-beleid waarmee u OMA-URI-instellingen kunt gebruiken om het apparaat te beheren. Ga naar [Aangepaste beleidsinstellingen](#custom-policy-settings) verderop in dit onderwerp voor meer informatie.

### <a name="password-settings"></a>Wachtwoordinstellingen

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|-|----------------|----------------|
|**Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**|Geeft aan of er een wachtwoord op ondersteunde apparaten is vereist of niet.|Ja|Yes|
|**Minimale wachtwoordlengte**|Geeft de minimale lengte van het wachtwoord aan.|Ja|Yes|
|**Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Geeft het aantal mislukte aanmeldingen aan dat is toegestaan voordat het apparaat wordt gewist.|Ja|Yes|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Geeft het aantal minuten van inactiviteit aan waarna het apparaat automatisch wordt vergrendeld.|Ja|Ja|
|**Dagen tot wachtwoord verloopt**|Geeft het aantal dagen aan waarna een wachtwoord moet worden gewijzigd.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden aan dat moeten worden onthouden.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** - **Wachtwoorden niet opnieuw gebruiken**|Voorkomt dat wachtwoorden opnieuw worden gebruikt.|Ja|Ja|
|**Wachtwoordkwaliteit**|Hiermee geeft u het complexiteitsniveau voor het wachtwoord aan en of biometrische apparaten kunnen worden gebruikt.|Ja|Yes|
|**Vingerafdruk voor ontgrendelen toestaan**|Hiermee wordt toegestaan dat het apparaat kan worden ontgrendeld met een vingerafdruk.|Nee|Yes|
|**Smart Lock en andere vertrouwensagents toestaan**<br>(Android 5 en hoger)|Hiermee kunt u de Smart Lock-functie op compatibele Android-apparaten beheren. Met deze telefoonmogelijkheid, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt (bijvoorbeeld wanneer het is verbonden met een bepaald Bluetooth-apparaat, of wanneer het zich in de buurt van een NFC-tag bevindt.) U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.|Ja|Nee|

### <a name="encryption-settings"></a>Versleutelingsinstellingen

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Versleuteling vereisen voor mobiel apparaat**|Vereist dat bestanden op het mobiele apparaat zijn versleuteld.|Ja|Yes|
|**Versleuteling vereisen op opslagkaarten**|Hiermee geeft u aan of de opslagkaart van het apparaat moet worden versleuteld.|Nee|Ja|

### <a name="system-settings"></a>Systeeminstellingen

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Schermopname toestaan**|Hiermee kan de gebruiker de scherminhoud als afbeelding vastleggen.|Nee|Ja|
|**Verzending van diagnostische gegevens toestaan**|Hiermee kan het apparaat diagnostische gegevens indienen bij Google.|Nee|Yes|
|**Fabrieksinstellingen terugzetten toestaan**|Staat de gebruiker toe om de fabrieksinstellingen terug te zetten op het apparaat.|Nee|Ja|

### <a name="cloud-settings---documents-and-data"></a>Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------------------|----------------|
|**Google-back-up toestaan**|Hiermee wordt het gebruik van Google-back-up toegestaan.|Nee|Ja|

### <a name="cloud-settings---accounts-and-synchronization"></a>Cloudinstellingen - accounts en synchronisatie

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Automatisch synchroniseren van Google-account toestaan**|Toestaan dat instellingen voor Google-accounts automatisch worden gesynchroniseerd.|Nee|Ja|

### <a name="application-settings---browser"></a>Toepassingsinstellingen - browser

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Webbrowser toestaan**|Hiermee geeft u op of de standaardwebbrowser op het apparaat kan worden gebruikt.|Nee|Ja|
|**Automatisch invullen toestaan**|Hiermee staat u toe dat de functie voor automatisch invullen van de webbrowser wordt gebruikt.|Nee|Yes|
|**Pop-upblokkering toestaan**|Hiermee kunt het gebruik van pop-upblokkering in de webbrowser toestaan.|Nee|Ja|
|**Cookies toestaan**|Hiermee staat u toe dat de webbrowser van het apparaat gebruikmaakt van cookies.|Nee|Ja|
|**Active Scripting toestaan**|Hiermee staat u toe dat de webbrowser van het apparaat gebruikmaakt van Active Scripting.|Nee|Ja|

### <a name="application-settings---apps"></a>Toepassingsinstellingen - apps

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Google Play Store toestaan**|Hiermee kan de gebruiker de Google Play Store openen op het apparaat.|Nee|Ja|

### <a name="device-capabilities-settings---hardware"></a>Instellingen voor apparaatmogelijkheden - hardware

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|-----|-----------|----------------|
|**Camera toestaan**|Gebruik van de camera op het apparaat toestaan.|Ja|Ja|
|**Verwisselbare opslag toestaan**|Hiermee staat u het gebruik toe van verwisselbare opslag, zoals een SD-kaart, op het apparaat.|Nee|Yes|
|**Wi-Fi toestaan**|Hiermee kunt het gebruik van de Wi-Fi-mogelijkheden van het apparaat toestaan.|Nee|Yes|
|**Wi-Fi-tethering toestaan**|Hiermee kunt het gebruik van Wi-Fi-tethering op het apparaat toestaan.|Nee|Yes|
|**Geolocatie toestaan**|Hiermee kan het apparaat locatiegegevens gebruiken.|Nee|Ja|
|**NFC toestaan**|Hiermee kunt u bewerkingen uitvoeren waarvoor near field communication wordt gebruikt, mits het apparaat er ondersteuning voor biedt.|Nee|Yes|
|**Bluetooth toestaan**|Hiermee kan de gebruiker Bluetooth op het apparaat gebruiken.|Nee|Yes|
|**Uitschakelen toestaan**|Hiermee kan de gebruiker het apparaat uitschakelen.<br /><br />Als deze instelling is uitgeschakeld, werkt de instelling **Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist** voor Samsung KNOX Standard-apparaten niet.|Nee|Ja|

### <a name="device-capabilities-settings---cellular"></a>Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|---|-------------|----------------|
|**Spraakroaming toestaan**|Hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Nee|Yes|
|**Dataroaming toestaan**|Hiermee staat u dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Nee|Yes|
|**Sms-/mms-berichten toestaan**|Hiermee staat u het gebruik van sms- en mms-berichten toe op het apparaat.|Nee|Ja|

### <a name="device-capabilities-settings---features"></a>Instellingen voor apparaatmogelijkheden - functies

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|----------------|----|------------|----------------|
|**Spraakassistent toestaan**|Hiermee wordt het gebruik van de spraakassistent toegestaan op het apparaat.|Nee|Ja|
|**Nummer inspreken toestaan**|Hiermee wordt de functie voor het inspreken van nummers op het apparaat in- of uitgeschakeld.|Nee|Ja|
|**Kopiëren en plakken toestaan**|Hiermee wordt kopiëren en plakken toegestaan op het apparaat.|Nee|Ja|
|**Klembord delen tussen toepassingen toestaan**|Hiermee staat u het gebruik van het Klembord toe om te kopiëren en plakken tussen apps.|Nee|Yes|
|**YouTube toestaan**|Hiermee wordt het gebruik van YouTube toegestaan op het apparaat.|Nee|Ja|

### <a name="settings-for-compliant-and-noncompliant-apps"></a>Instellingen voor compatibele en niet-compatibele apps
In de lijst **Compatibele en&amp; niet-compatibele apps** geeft u een lijst op met compatibele of niet-compatibele apps die van de volgende gegevens gebruikmaken:

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met compatibele apps of een lijst met niet-compatibele apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Hiermee worden de apps vermeld die niet worden beheerd door Intune en waarvan u niet wilt dat deze door gebruikers worden geïnstalleerd en uitgevoerd. Als gebruikers een van deze apps installeren, wordt deze vermeld in het rapport voor niet-compatibele apps.|
|**Niet rapporteren wanneer gebruikers niet-compatibele apps installeren die in de lijst staan**|Vermeldt de apps die u wilt toestaan. Om te blijven voldoen aan het beleid, mogen gebruikers geen apps installeren die niet worden vermeld. Apps die worden beheerd door Intune, zijn automatisch toegestaan.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef de naam van de app op, de uitgever van de app (optioneel) en de URL van de app in de app store.<br /><br />Zie[URL's voor app stores opgeven](#specify-urls-to-app-stores) verderop in dit onderwerp voor meer informatie.|
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik de notatie, toepassingsnaam, uitgever en app-URL in het bestand.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de URL van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|

Beleid met compatibele en niet-compatibele app-instellingen moet worden geïmplementeerd voor groepen van gebruikers.

### <a name="kiosk-mode-settings"></a>Instellingen voor kioskmodus
Geef de volgende instellingen op voor **Samsung KNOX Standard-apparaten**:

|Naam van de instelling|Details|
|----------------|--------------------|
|**Een beheerde app selecteren die kan worden uitgevoerd wanneer het apparaat in kioskmodus is**|Kies **Bladeren** en selecteer vervolgens de beheerde app die mag worden uitgevoerd wanneer het apparaat zich in de kioskmodus bevindt (apps die zijn opgegeven als een koppeling naar de Store worden momenteel niet ondersteund). Er mogen geen andere apps op het apparaat worden uitgevoerd.|
|**Volumeknoppen toestaan**|Hiermee wordt het gebruik van de volumeknoppen op het apparaat in- of uitgeschakeld.|
|**Knop voor slaapstand/ontwaken van scherm toestaan**|Hiermee wordt de knop voor slaapstand/ontwaken van het scherm in- of uitgeschakeld op het apparaat.|

### <a name="reference-information-for-compliant-and-noncompliant-apps"></a>Referentie-informatie voor compatibele en niet-compatibele apps

#### <a name="monitor-compliant-and-noncompliant-apps"></a>Compatibele apps en niet-compatibele apps controleren
Gebruik het **Rapport met niet-compatibele apps** om de compatibiliteit van toegestane en geblokkeerde apps weer te geven.

###### <a name="to-run-the-noncompliant-apps-report"></a>Het rapport met niet-compatibele apps uitvoeren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Rapporten** &gt; **Rapport met niet-compatibele apps**.

2.  Selecteer de apparaatgroepen die u wilt controleren. Kies of u wilt controleren op compatibele apps, niet-compatibele apps of beide. En kies ten slotte **Rapport weergeven**.

#### <a name="specify-urls-to-app-stores"></a>URL's voor app stores opgeven
Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps, voert u de volgende stappen uit:

In het [gedeelte Apps van Google Play](https://play.google.com/store/apps) zoekt u de app die u wilt gebruiken.

Open de installatiepagina voor de app en kopieer vervolgens de URL naar het klembord. U kunt deze nu als de URL gebruiken in de lijst met compatibele apps of de lijst met niet-compatibele apps.

Voorbeeld: zoek in Google Play naar Microsoft Office Mobile. De URL die u gebruikt, is **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## <a name="custom-policy-settings"></a>Aangepaste beleidsinstellingen
Gebruik het **aangepaste Android-configuratiebeleid** van Microsoft Intune om OMA-URI-instellingen te implementeren die kunnen worden gebruikt om de functies op Android-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen implementeren die niet met Intune-beleid kunnen worden geconfigureerd.
Intune biedt momenteel ondersteuning voor een beperkt aantal aangepaste Android-beleidsregels. Zie de voorbeelden in dit onderwerp om na te gaan welk beleid u kunt configureren.

### <a name="general-settings"></a>Algemene instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    | **Naam** |Voer een unieke naam in voor het aangepaste Android-beleid, zodat dit gemakkelijk is te herkennen in de Intune-console.|
    | **Beschrijving** |Geef een beschrijving op die een overzicht biedt van het aangepaste Android-beleid, evenals andere relevante informatie die u helpt om het beleid weer te vinden.|

### <a name="oma-uri-settings"></a>OMA-URI-instellingen

   |Naam van de instelling|Details|
    |--------|--------------------|
    | **Naam van instelling** |Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
    | **Beschrijving van instelling** |Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    | **Gegevenstype** |Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **tekenreeks, tekenreeks (XML), datum en tijd, geheel getal, drijvende komma** en **booleaanse waarde**.|
    | **OMA-URI (hoofdlettergevoelig)** |Geef aan voor welke OMA-URI u een instelling wilt opgeven.|
    | **Waarde** |Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|

### <a name="examples"></a>Voorbeelden

- [Een Wi-Fi-profiel maken met een vooraf gedeelde sleutel](pre-shared-key-wi-fi-profile.md)
- [Een aangepast beleid gebruiken voor een VPN-profiel per app voor Android-apparaten](per-app-vpn-for-android-pulse-secure.md)
- [Aangepaste beleidsregels gebruiken om apps toe te staan of te blokkeren voor Samsung KNOX-apparaten](custom-policy-to-allow-and-block-samsung-knox-apps.md)

## <a name="supported-samsung-knox-standard-devices"></a>Ondersteunde Samsung KNOX Standard-apparaten

Via de bedrijfsportal-app wordt de Samsung KNOX-activering alleen uitgevoerd tijdens MDM-registratie als het apparaat wordt weergegeven in de [lijst met ondersteunde KNOX-apparaten](https://www.samsungknox.com/knox-supported-devices/knox-workspace). Hierdoor wordt voorkomen dat er KNOX-activeringsfouten optreden waardoor MDM-registratie mislukt. Apparaten die geen ondersteuning bieden voor Samsung KNOX-activering, worden geregistreerd als standaard-Android-apparaten. Bepaalde modelnummers van Samsung-apparaten bieden ondersteuning voor KNOX, andere niet. Controleer de KNOX-compatibiliteit bij de verkoper van uw apparaat voordat u Samsung-apparaten koopt en implementeert.

De volgende Samsung-apparaatmodellen bieden geen ondersteuning voor KNOX en worden geregistreerd als systeemeigen Android-apparaten door de bedrijfsportal-app voor Android:

| **Apparaatnaam** | **Apparaatmodelnummers** |
| --- | --- |
| Galaxy A3 | SM-A300G<br>SM-A310Y<br>SM-A320FL |
| Galaxy A5 | SM-A500G |
| Galaxy Alpha | SM-G850M |
| Galaxy Avant | SM-G386T |
| Galaxy C9/C9 Pro | SM-C900F |
| Galaxy Core 2/Core 2 Duos | SM-G355H<br>SM-G355M |
| Galaxy Core Lite | SM-G3588V |
| Galaxy Core Prime | SM-G360H |
| Galaxy Core LTE | SM-G386F<br>SM-G386W |
| Galaxy Grand | GT-I9082L<br>GT-I9082<br>GT-I9080L |
| Galaxy Grand 3 | SM-G7200 |
| Galaxy Grand Neo | GT-I9060I |
| Galaxy Grand Prime | SM-G530M |
| Galaxy Grand Prime Value Edition | SM-G531H |
| Galaxy J Max | SM-T285YD |
| Galaxy J1 | SM-J100H<br>SM-J100M<br>SM-J100ML |
| Galaxy J1 Ace | SM-J110F<br>SM-J110H |
| Galaxy J1 Mini | SM-J105M |
| Galaxy J2/J2 Pro | SM-J200H<br>SM-J210F |
| Galaxy J3 | SM-J320F<br>SM-J320FN<br>SM-J320H<br>SM-J320M<br>SM-J320W8 |
| Galaxy J5 | SM-J500G |
| Galaxy J7 | SM-J710F |
| Galaxy J7 Prime | SM-J727T1 |
| Galaxy K Zoom | SM-C115 |
| Galaxy Light | SGH-T399N |
| Galaxy Note 3 | SM-N9002<br>SM-N9009 |
| Galaxy Note 5 | SM-N920G<br>SM-N920I<br>SM-N920W8 |
| Galaxy Note 7/Note 7 Duos | SM-N930S<br>SM-N9300<br>SM-N930F<br>SM-N930T<br>SM-N9300<br>SM-N930F<br>SM-N930S<br>SM-N930T |
| Galaxy Note 10.1 3G | SM-P602 |
| Galaxy NotePRO 12.2&quot; | SM-P902 |
| Galaxy On5 | SM-G570MSM-G570Y |
| Galaxy On7 | SM-G600FY<br>SM-G610M<br>SM-G610Y |
| Galaxy S2 Plus | GT-I9105P |
| Galaxy S3 Mini | SM-G730A<br>SM-G730V |
| Galaxy S3 Neo | GT-I9300<br>GT-I9300I |
| Galaxy S4 | SM-S975L |
| Galaxy S4 Active | GT-I9295 |
| Galaxy S4 Neo | SM-G318ML |
| Galaxy S5 | SM-G9006W<br>SM-G900M |
| Galaxy S5 Neo | SM-G903M |
| Galaxy S6 Edge | 404SCSM-G925I<br>SM-G928G |
| Galaxy Tab A 7.0&quot; | SM-T280SM-T285 |
| Galaxy Tab A 9.7&quot; | SM-P555M |
| Galaxy Tab 3 7&quot;/Tab 3 Lite 7&quot; | SM-T116SM-T210SM-T211 |
| Galaxy Tab 3 8.0&quot; | SM-T311 |
| Galaxy Tab 3 10.1&quot; | GT-P5200<br>GT-P5210<br>GT-P5220 |
| Galaxy Trend 2 Lite | SM-G318H |
| Galaxy V Plus | SM-G318HZ |
| Galaxy Young 2 Duos | SM-G130BU |



### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
