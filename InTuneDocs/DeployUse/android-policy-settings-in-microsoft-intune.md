---

title: Beleidsinstellingen voor Android en Samsung KNOXs | Microsoft Intune
description: Beleidsregels maken voor het beheren van instellingen en functies op Android-apparaten die u met Intune beheert.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71cc39cf-e726-40fd-8d08-78776e099a4b
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6e3e81f37e677a016ac49240cc70602a568afcd5
ms.openlocfilehash: 9385ca0e5aa9dd8fc2daf79c57b47951bcd5c0cb


---

# Instellingen voor het Android- en Samsung KNOX-beleid in Microsoft Intune

Intune biedt diverse ingebouwde algemene instellingen die u op Android-apparaten kunt configureren. Daarnaast kunt u OMA-URI-waarden (Open Mobile Alliance Uniform Resource Identifier) opgeven om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.

## Algemeen configuratiebeleid

Gebruik het Intune **algemene Android-configuratiebeleid** om instellingen te configureren voor:

-   **Beveiligingsinstellingen voor mobiele apparaten**: hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u een reeks functies en functionaliteiten op het apparaat kunt beheren.

-   **Kioskmodus** (alleen voor Samsung KNOX-apparaten): hiermee kunt u een apparaat zodanig vergrendelen dat alleen bepaalde functies beschikbaar zijn. U kunt bijvoorbeeld toestaan dat een apparaat slechts één beheerde app uitvoert die u opgeeft, of kunt u de volumeknoppen op een apparaat uitschakelen. Deze instellingen kunnen worden gebruikt voor een demonstratiemodel van een apparaat of voor een apparaat dat is toegewezen aan slechts één functie, zoals een verkooppuntapparaat.

-   **Compatibele en niet-compatibele apps**: hiermee geeft u een lijst op met apps die compatibel of niet compatibel zijn in uw bedrijf. Op Android- en iOS-apparaten kan het **Rapport niet-compatibele apps** worden gebruikt om de compatibiliteit van apps die u in de lijst hebt opgegeven, te vergelijken met de apps die gebruikers hebben geïnstalleerd. Met het rapport kan de installatie van de app niet daadwerkelijk worden geblokkeerd.

> [!TIP]
> U kunt voorwaarden voor gebruikers configureren om ervoor te zorgen dat ze ermee instemmen dat alle apps op hun apparaat, waaronder persoonlijke apps, worden geëvalueerd, en dat niet-compatibele apps worden geblokkeerd of gerapporteerd als niet-compatibel. Gebruikers moeten deze voorwaarden accepteren voordat ze hun apparaat kunnen registreren en de bedrijfsportal kunnen gebruiken om apps op te halen. Zie [Beleidsinstellingen voor voorwaarden in Microsoft Intune](terms-and-condition-policy-settings-in-microsoft-intune.md) voor meer informatie over het gebruik van voorwaarden.

Als de instelling die u zoekt niet wordt weergegeven in dit onderwerp, kunt u deze maken met behulp van een aangepast Android-beleid waarmee u OMA-URI-instellingen kunt gebruiken om het apparaat te beheren. Ga naar [Aangepaste beleidsinstellingen](#custom-policy-settings) verderop in dit onderwerp voor meer informatie.

### Wachtwoordinstellingen

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|-|----------------|----------------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Geeft aan of er een wachtwoord op ondersteunde apparaten is vereist of niet.|Ja|Ja|
|**Minimale wachtwoordlengte**|Geeft de minimale lengte van het wachtwoord aan.|Ja|Ja|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Geeft het aantal mislukte aanmeldingen aan dat is toegestaan voordat het apparaat wordt gewist.|Ja|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Geeft het aantal minuten van inactiviteit aan waarna het apparaat automatisch wordt vergrendeld.|Ja|Ja|
|**Wachtwoordverlooptijd (dagen)**|Geeft het aantal dagen aan waarna een wachtwoord moet worden gewijzigd.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden aan dat moeten worden onthouden.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** - **Wachtwoorden niet opnieuw gebruiken**|Voorkomt dat wachtwoorden opnieuw worden gebruikt.|Ja|Ja|
|**Wachtwoordkwaliteit**|Hiermee geeft u het complexiteitsniveau voor het wachtwoord aan en of biometrische apparaten kunnen worden gebruikt.|Ja|Ja|
|**Vingerafdruk voor ontgrendelen toestaan**|Hiermee wordt toegestaan dat het apparaat kan worden ontgrendeld met een vingerafdruk.|Nee|Ja|
|**Smart Lock en andere vertrouwensagents toestaan**<br>(Android 5 en hoger)|Hiermee kunt u de Smart Lock-functie op compatibele Android-apparaten beheren. Met deze telefoonmogelijkheid, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt (bijvoorbeeld wanneer het is verbonden met een bepaald Bluetooth-apparaat, of wanneer het zich in de buurt van een NFC-tag bevindt.) U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.|Ja|Nee|

### Versleutelingsinstellingen

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Versleuteling vereisen voor mobiel apparaat**|Vereist dat bestanden op het mobiele apparaat zijn versleuteld.|Ja|Ja|
|**Versleuteling vereisen voor opslagkaarten**|Hiermee geeft u aan of de opslagkaart van het apparaat moet worden versleuteld.|Nee|Ja|

### Systeeminstellingen

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Schermafbeelding toestaan**|Hiermee kan de gebruiker de scherminhoud als afbeelding vastleggen.|Nee|Ja|
|**Verzending van diagnostische gegevens toestaan**|Hiermee kan het apparaat diagnostische gegevens indienen bij Google.|Nee|Ja|
|**Terugzetten op fabrieksinstellingen toestaan**|Staat de gebruiker toe om de fabrieksinstellingen terug te zetten op het apparaat.|Nee|Ja|

### Cloudinstellingen – documenten en gegevens

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------------------|----------------|
|**Back-up van Google toestaan**|Hiermee wordt het gebruik van Google-back-up toegestaan.|Nee|Ja|

### Cloudinstellingen - accounts en synchronisatie

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Automatische synchronisatie van Google-account toestaan**|Toestaan dat instellingen voor Google-accounts automatisch worden gesynchroniseerd.|Nee|Ja|

### Toepassingsinstellingen - browser

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Webbrowser toestaan**|Hiermee geeft u op of de standaardwebbrowser op het apparaat kan worden gebruikt.|Nee|Ja|
|**Automatisch invullen toestaan**|Hiermee staat u toe dat de functie voor automatisch invullen van de webbrowser wordt gebruikt.|Nee|Ja|
|**Pop-upblokkering toestaan**|Hiermee kunt het gebruik van pop-upblokkering in de webbrowser toestaan.|Nee|Ja|
|**Cookies toestaan**|Hiermee staat u toe dat de webbrowser van het apparaat gebruikmaakt van cookies.|Nee|Ja|
|**Active Scripting toestaan**|Hiermee staat u toe dat de webbrowser van het apparaat gebruikmaakt van Active Scripting.|Nee|Ja|

### Toepassingsinstellingen - apps

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Google Play store toestaan**|Hiermee kan de gebruiker de Google Play Store openen op het apparaat.|Nee|Ja|

### Instellingen voor apparaatmogelijkheden - hardware

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Camera toestaan**|Gebruik van de camera op het apparaat toestaan.|Ja|Ja|
|**Verwisselbare opslag toestaan**|Hiermee staat u het gebruik toe van verwisselbare opslag, zoals een SD-kaart, op het apparaat.|Nee|Ja|
|**Wi-Fi toestaan**|Hiermee kunt het gebruik van de Wi-Fi-mogelijkheden van het apparaat toestaan.|Nee|Ja|
|**Wi-Fi-tethering toestaan**|Hiermee kunt het gebruik van Wi-Fi-tethering op het apparaat toestaan.|Nee|Ja|
|**Geolocatie toestaan**|Hiermee kan het apparaat locatiegegevens gebruiken.|Nee|Ja|
|**NFC toestaan**|Hiermee kunt u bewerkingen uitvoeren waarvoor near field communication wordt gebruikt, mits het apparaat er ondersteuning voor biedt.|Nee|Ja|
|**Bluetooth toestaan**|Hiermee kan de gebruiker Bluetooth op het apparaat gebruiken.|Nee|Ja|
|**Uitschakelen toestaan**|Hiermee kan de gebruiker het apparaat uitschakelen.<br /><br />Als deze instelling is uitgeschakeld, werkt de instelling **Aantal mislukte aanmeldpogingen voordat het apparaat wordt gewist** voor Samsung KNOX-apparaten niet.|Nee|Ja|

### Instellingen voor apparaatmogelijkheden - mobiel

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Spraakroaming toestaan**|Hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Nee|Ja|
|**Gegevensroaming toestaan**|Hiermee staat u dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Nee|Ja|
|**SMS- en MMS-berichten toestaan**|Hiermee staat u het gebruik van sms- en mms-berichten toe op het apparaat.|Nee|Ja|

### Instellingen voor apparaatmogelijkheden - functies

|Naam van de instelling|Details|Android 4.0+|Samsung KNOX|
|----------------|----------------|----------------|
|**Spraakassistent toestaan**|Hiermee wordt het gebruik van de spraakassistent toegestaan op het apparaat.|Nee|Ja|
|**Nummer inspreken toestaan**|Hiermee wordt de functie voor het inspreken van nummers op het apparaat in- of uitgeschakeld.|Nee|Ja|
|**Kopiëren en plakken toestaan**|Hiermee wordt kopiëren en plakken toegestaan op het apparaat.|Nee|Ja|
|**Klembord delen tussen toepassingen toestaan**|Hiermee staat u het gebruik van het Klembord toe om te kopiëren en plakken tussen apps.|Nee|Ja|
|**YouTube toestaan**|Hiermee wordt het gebruik van YouTube toegestaan op het apparaat.|Nee|Ja|

### Instellingen voor compatibele en niet-compatibele apps
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

### Instellingen voor kioskmodus
Geef de volgende instellingen op voor **Samsung KNOX-apparaten**:

|Naam van de instelling|Details|
|----------------|--------------------|
|**Een beheerde app selecteren die mag worden uitgevoerd wanneer het apparaat in kioskmodus is**|Kies **Bladeren** en selecteer vervolgens de beheerde app die mag worden uitgevoerd wanneer het apparaat zich in de kioskmodus bevindt (apps die zijn opgegeven als een koppeling naar de Store worden momenteel niet ondersteund). Er mogen geen andere apps op het apparaat worden uitgevoerd.|
|**Volumeknoppen toestaan**|Hiermee wordt het gebruik van de volumeknoppen op het apparaat in- of uitgeschakeld.|
|**Knop voor slaapstand/ontwaken van scherm toestaan**|Hiermee wordt de knop voor slaapstand/ontwaken van het scherm in- of uitgeschakeld op het apparaat.|

### Referentie-informatie voor compatibele en niet-compatibele apps

#### Compatibele apps en niet-compatibele apps controleren
Gebruik het **Rapport met niet-compatibele apps** om de compatibiliteit van toegestane en geblokkeerde apps weer te geven.

###### Het rapport met niet-compatibele apps uitvoeren

1.  Kies in de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) de optie **Rapporten** &gt; **Rapport met niet-compatibele apps**.

2.  Selecteer de apparaatgroepen die u wilt controleren. Kies of u wilt controleren op compatibele apps, niet-compatibele apps of beide. En kies ten slotte **Rapport weergeven**.

#### URL's voor app stores opgeven
Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps, voert u de volgende stappen uit:

In het [gedeelte Apps van Google Play](https://play.google.com/store/apps) zoekt u de app die u wilt gebruiken.

Open de installatiepagina voor de app en kopieer vervolgens de URL naar het klembord. U kunt deze nu als de URL gebruiken in de lijst met compatibele apps of de lijst met niet-compatibele apps.

Voorbeeld: zoek in Google Play naar Microsoft Office Mobile. De URL die u gebruikt, is **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

## Aangepaste beleidsinstellingen
Gebruik het **aangepaste Android-configuratiebeleid** van Microsoft Intune om OMA-URI-instellingen te implementeren die kunnen worden gebruikt om de functies op Android-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen implementeren die niet met Intune-beleid kunnen worden geconfigureerd.

> [!NOTE]
> Momenteel wordt door het aangepaste Android-beleid alleen de configuratie ondersteund van Wi-Fi-instellingen voor Android-apparaten die een vooraf gedeelde sleutel bevatten.

### Algemene instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam**|Voer een unieke naam in voor het aangepaste Android-beleid, zodat dit gemakkelijk is te herkennen in de Intune-console.|
    |**Beschrijving**|Geef een beschrijving op die een overzicht biedt van het aangepaste Android-beleid, evenals andere relevante informatie die u helpt om het beleid weer te vinden.|

### OMA-URI-instellingen

   |Naam van de instelling|Details|
    |--------|--------------------|
    |**Naam van de instelling**|Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
    |**Beschrijving van instelling**|Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    |**Gegevenstype**|Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **tekenreeks, tekenreeks (XML), datum en tijd, geheel getal, drijvende komma** en **booleaanse waarde**.|
    |**OMA-URI (hoofdlettergevoelig)**|Geef aan voor welke OMA-URI u een instelling wilt opgeven.|
    |**Waarde**|Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|

### Voorbeeld: een aangepast Wi-Fi-profiel met een vooraf gedeelde sleutel configureren
Hoewel Wi-Fi-profielen voor Android-apparaten door Intune worden ondersteund, ondersteunt deze functie momenteel niet dat een vooraf gedeelde sleutel in de configuratie wordt opgenomen. In dit voorbeeld wordt uitgelegd hoe u een aangepast Android-beleid maakt, waarmee een Wi-Fi-profiel met een vooraf gedeelde sleutel op het Android-apparaat wordt gemaakt.

#### Een aangepast Wi-Fi-profiel met een vooraf gedeelde sleutel maken.

1.  Controleer of de gebruikers de nieuwste versie van de [Intune-bedrijfsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)-app voor Android gebruiken.

2.  Maak een aangepast Android-beleid en voeg de volgende instellingen toe:

|Naam van de instelling|Details|
|----------------|--------------------|
|**Naam van de instelling**|Geef een naam op voor de instelling.|
|**Beschrijving van de instelling**|Geef een beschrijving op voor de instelling.|
|**Gegevenstype**|Selecteer **Tekenreeks (XML)**.|
|**OMA-URI**|Typ het volgende: ./Vendor/MSFT/WiFi/Profile/*&lt;uw Wi-Fi-profiel&gt;*/Settings|

3.  Bij **Waarde** plakt u de volgende XML-code:

    ```
    <!--
    WEP Wifi Profile
                    <Name of wifi profile> = Name of profile
                    <SSID of wifi profile> = Plain text version of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
                    <WEP password> = Password to connect to the network
    -->
    <WLANProfile
    xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name><Name of wifi profile></name>
      <SSIDConfig>
        <SSID>
          <name><SSID of wifi profile></name>
        </SSID>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <MSM>
        <security>
          <authEncryption>
            <authentication>open</authentication>
            <encryption>WEP</encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial><WEP password></keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
    ```

4.  Wanneer u klaar bent, slaat u het beleid op en implementeert u het beleid op de betreffende Android-apparaten. Het nieuwe Wi-Fi-profiel wordt weergegeven in de lijst met verbindingen op het apparaat.

### Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Jul16_HO4-->


