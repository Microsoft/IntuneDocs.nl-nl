---
title: Beleidsinstellingen voor Windows Phone 8.1
description: Intune biedt diverse ingebouwde algemene instellingen die u op Windows Phone 8.1-apparaten kunt configureren. Daarnaast kunt u OMA-URI-waarden opgeven om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b496acfa2a596f016142b73b8fc99d1f763c35e0
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/10/2017
---
# <a name="windows-phone-81-policy-settings-in-microsoft-intune"></a>Beleidsinstellingen voor Windows Phone 8.1 in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune biedt diverse ingebouwde algemene instellingen die u op Windows Phone 8.1-apparaten kunt configureren. Daarnaast kunt u OMA-URI-waarden (Open Mobile Alliance Uniform Resource Identifier) opgeven om aangepaste instellingen te maken die niet beschikbaar zijn vanuit Intune.

## <a name="general-configuration-settings"></a>Algemene configuratie-instellingen

Gebruik het **algemene configuratiebeleid voor Windows Phone (Windows Phone 8.1 en later)** om de volgende instellingen te configureren voor apparaten met Windows Phone 8.1:

-   **Beveiligingsinstellingen voor mobiele apparaten** : hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u een bereik aan functies en functionaliteiten op het apparaat kunt beheren.

-   **Compatibele en niet-compatibele apps**: hier kunt u een lijst opgeven met apps die compatibel of niet compatibel zijn in uw bedrijf. Windows Phone-apparaten kunnen de installatie van deze apps blokkeren of toestaan.

### <a name="applicability-settings"></a>Toepasselijkheidsinstellingen

|Naam van de instelling|Details|
|----------------|----------------------------------|
|**Alle configuraties toepassen op Windows 10**|Deze instelling maakt het mogelijk om de instellingen in dit beleid behalve op Windows Phone 8.1-apparaten, ook toe te passen op Windows 10 Mobile-apparaten.|

### <a name="password-settings"></a>Wachtwoordinstellingen

|Naam van de instelling|Details|
|----------------|------|
|**Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**|Hiermee geeft u op of gebruikers een wachtwoord voor toegang tot hun apparaten moeten invoeren.|
|**Vereist wachtwoordtype**|Hiermee geeft u het wachtwoordtype op dat is vereist, zoals alfanumeriek of alleen numeriek.|
|**Vereist wachtwoordtype – minimumaantal tekensets**|Hiermee geeft u op hoeveel verschillende tekensets er moeten worden opgenomen in het wachtwoord. Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Voor iOS-apparaten geeft u hiermee echter het aantal symbolen op dat moet worden opgenomen in het wachtwoord.|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimum aantal tekens op waaruit het wachtwoord moet bestaan.|
|**Eenvoudige wachtwoorden toestaan**|Hiermee geeft u op dat er eenvoudige wachtwoorden, zoals '0000' en '1234' kunnen worden gebruikt.|
|**Aantal herhaalde, mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Hiermee geeft u op hoe vaak een onjuist wachtwoord kan worden ingevoerd voordat het apparaat wordt gewist.|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u de hoeveelheid tijd op die een apparaat niet-actief moet blijven voordat het scherm automatisch wordt vergrendeld.|
|**Dagen tot wachtwoord verloopt**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u op of eerder gebruikte wachtwoorden worden onthouden om te voorkomen dat de gebruiker deze opnieuw gebruikt.|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u aan hoeveel eerder gebruikte wachtwoorden er worden onthouden.|

### <a name="encryption-settings"></a>Versleutelingsinstellingen

|Naam van de instelling|Details|
|----------------|------|
|**Versleuteling vereisen voor mobiel apparaat**|Hiermee vereist u dat de gegevens op ondersteunde mobiele apparaten worden versleuteld.|

### <a name="system-settings"></a>Systeeminstellingen

|Naam van de instelling|Details|
|----------------|-----|
|**Schermopname toestaan**|Hiermee kan de gebruiker de inhoud van het scherm als afbeelding vastleggen.|
|**Verzending van diagnostische gegevens toestaan**|Hiermee stelt u het apparaat in staat diagnostische gegevens naar Microsoft te verzenden.|

### <a name="cloud-settings--accounts-and-synchronization"></a>Cloudinstellingen - accounts en synchronisatie

|Naam van de instelling|Details|
|----------------|------|
|**Microsoft-account toestaan**|Hiermee maakt u het mogelijk om een Microsoft-account aan het apparaat te koppelen.|

### <a name="email-settings"></a>E-mailinstellingen

|Naam van de instelling|Details|
|----------------|-----|
|**Aangepaste e-mailaccounts toestaan**|Hiermee stelt u het apparaat in staat verbinding te maken met niet-Microsoft e-mailaccounts.|

### <a name="application-settings---browser"></a>Toepassingsinstellingen - browser

|Naam van de instelling|Details|
|----------------|-----|
|**Webbrowser toestaan**|Hiermee kunt u het gebruik van de ingebouwde webbrowser op apparaten toestaan of blokkeren.|

### <a name="application-settings---apps"></a>Toepassingsinstellingen - apps

|Naam van de instelling|Details|
|----------------|-----|
|**Toepassingsarchief toestaan**|Hiermee kunnen gebruikers verbinding maken met de app store van het apparaat.|

### <a name="device-capabilities-settings---hardware"></a>Instellingen voor apparaatmogelijkheden - hardware

|Naam van de instelling|Details|
|----------------|-----|
|**Camera toestaan**|Hiermee kunt u het gebruik van de camera van het apparaat toestaan of blokkeren.|
|**Verwisselbare opslag toestaan**|Hiermee stelt u het apparaat in staat verwisselbare opslag te gebruiken, zoals SD-kaarten.|
|**Wi-Fi toestaan**|Hiermee schakelt u de Wi-Fi-functionaliteit van het apparaat in of uit.|
|**Wi-Fi-tethering toestaan**|Hiermee maakt u het gebruik van Wi-Fi-tethering op het apparaat mogelijk.|
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Hiermee staat u het apparaat toe automatisch verbinding te maken met gratis Wi-Fi-hotspots en automatisch alle gebruiksvoorwaarden te accepteren.|
|**Rapportage van Wi-Fi-hotspots toestaan**|Hiermee wordt informatie over Wi-Fi-verbindingen verzonden om de gebruiker te helpen verbindingen in de buurt te detecteren.|
|**Geolocatie toestaan**|Hiermee stelt u het apparaat in staat locatiegegevens te gebruiken.|
|**NFC toestaan**|Hiermee maakt u bewerkingen mogelijk waarvoor Near Field Communication wordt gebruikt.|
|**Bluetooth toestaan**|Hiermee schakelt u de Bluetooth-functionaliteit van het apparaat in of uit.|

### <a name="device-capabilities-settings---features"></a>Instellingen voor apparaatmogelijkheden - functies

|Naam van de instelling|Details|
|----------------|----|
|**Kopiëren en plakken toestaan**|Hiermee maakt u kopiëren en plakken op apparaten mogelijk.|

### <a name="settings-for-allowed-and-blocked-apps"></a>Instellingen voor toegestane en geblokkeerde apps
In de lijst **Toegestane en geblokkeerde apps** geeft u de apps op die u wilt toestaan of blokkeren op basis van de volgende gegevens:

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met toegestane of geblokkeerde apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Apparaten mogen apps in lijst niet openen**|Hiermee wordt een lijst gemaakt met de apps die niet worden beheerd met Intune en die niet mogen worden geïnstalleerd en uitgevoerd door gebruikers.|
|**Alleen de apps in de lijst mogen op apparaten worden geïnstalleerd**|Hiermee wordt een lijst gemaakt met de apps die gebruikers mogen installeren. Gebruikers mogen geen andere apps installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef een naam van uw keuze op, geef de URL op van de app in de App Store en vermeld desgewenst de uitgever van de app. Zie 'URL's voor app stores opgeven' verderop in dit onderwerp voor meer informatie.
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik de notatie, toepassingsnaam, uitgever en app-URL in het bestand.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de URL van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|
> [!IMPORTANT]
> Als u een lijst met toegestane apps voor Windows Phone 8.1-apparaten opgeeft, moet u de Bedrijfsportal-app aan deze lijst toevoegen, anders wordt deze app geblokkeerd.


### <a name="reference-information-for-allowed-and-blocked-apps"></a>Referentie-informatie voor toegestane en geblokkeerde apps

#### <a name="how-to-specify-urls-to-app-stores"></a>URL's voor app stores opgeven
Als u een app-URL wilt opgeven in de lijst met toegestane en geblokkeerde apps, gebruikt u de volgende notatie:

Zoek op de pagina [Windows Phone Apps+Games](http://www.windowsphone.com/store/overview) naar de app die u wilt gebruiken.

Open de pagina van de app en kopieer de URL naar het klembord. U kunt deze URL nu gebruiken in de lijst met toegestane apps of de lijst met geblokkeerde apps.

**Voorbeeld:** Zoek in de store naar de Skype-app. De URL die u gebruikt, is **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## <a name="custom-policy-settings"></a>Aangepaste beleidsinstellingen
Gebruik het **aangepaste configuratiebeleid voor Windows Phone** van Microsoft Intune om OMA-URI-instellingen te implementeren die kunnen worden gebruikt om functies op **Windows Phone 8.1-apparaten** te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Windows Phone-instellingen implementeren die niet met het algemene configuratiebeleid van Intune kunnen worden geconfigureerd. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor informatie over de instellingen die u met dit beleid kunt configureren.

Zie [MDM-protocoldocumentatie voor Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx) voor meer informatie over het maken van OMA-URI-instellingen voor Windows Phone-apparaten.

### <a name="general-settings"></a>Algemene instellingen

|Naam van de instelling|Details|
|----------------|--------------------|
|**Naam**|Voer een unieke naam in voor het beleid, zodat u het beleid in de Intune-console kunt herkennen.|
|**Beschrijving**|Geef een beschrijving op die een overzicht geeft van het beleid en overige relevante informatie die u helpt om het beleid terug te vinden.|

### <a name="oma-uri-settings"></a>OMA-URI-instellingen

Klik in de sectie **OMA-URI-instellingen** op **Toevoegen** om een instelling toe te voegen. U kunt ook een bestaande instelling bewerken of verwijderen.

Geef in het dialoogvenster **OMA-URI-instelling toevoegen of bewerken** de volgende gegevens op:

|Naam van de instelling|Details|
    |--------|--------------------|
    |**Naam van instelling**|Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
    |**Beschrijving van instelling**|Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    |**Gegevenstype**|Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. U kunt kiezen uit:<br /><br />-   **Tekenreeks**<br />-   **Tekenreeks (XML)**<br />-   **Datum en tijd**<br />-   **Geheel getal**<br />-   **Drijvende komma**<br />-   **Boolean-waarde**|
    |**OMA-URI (hoofdlettergevoelig)**|Geef de OMA-URI op waarvoor u een instelling wilt opgeven.|
    |**Waarde**|Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|

### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
