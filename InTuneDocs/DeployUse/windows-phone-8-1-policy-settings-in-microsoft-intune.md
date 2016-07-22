---
title: Beleidsinstellingen voor Windows Phone 8.1 | Microsoft Intune
description: 
keywords: 
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a280fcbecf82e6ff27e40d2d53331b3988953ff7
ms.openlocfilehash: fe685da41bb5379526bdc28c2f9cceb6b7800703


---

# Beleidsinstellingen voor Windows Phone 8.1 in Microsoft Intune

## Algemene configuratie-instellingen

Gebruik het **algemene configuratiebeleid voor Windows Phone (Windows Phone 8.1 en later)** om de volgende instellingen te configureren voor apparaten met Windows Phone 8.1:

-   **Beveiligingsinstellingen voor mobiele apparaten** : hier kiest u uit een lijst met vooraf gedefinieerde instellingen waarmee u een bereik aan functies en functionaliteiten op het apparaat kunt beheren.

-   **Compatibele en niet-compatibele apps**: hiermee geeft u een lijst op met apps die compatibel of niet compatibel zijn in uw bedrijf. Windows Phone-apparaten kunnen de installatie van deze apps blokkeren of toestaan.

### Toepasselijkheidsinstellingen

|Naam van de instelling|Details|
|----------------|----------------------------------|
|**Alle configuraties toepassen op Windows 10**|Hiermee kunt de instellingen in dit beleid naast Windows Phone 8.1-apparaten toepassen op Windows 10 Mobile-apparaten.|

### Wachtwoordinstellingen

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Wachtwoord vereist voor het ontgrendelen van mobiele apparaten**|Hiermee geeft u op of gebruikers een wachtwoord voor toegang tot hun apparaten moeten invoeren.|Ja|Ja|
|**Vereist wachtwoordtype**|Hiermee geeft u het type wachtwoord op dat is vereist, zoals alleen numeriek of alfanumeriek.|Ja|Ja|
|**Vereist wachtwoordtype – minimumaantal tekensets**|Er zijn vier tekensets: kleine letters, hoofdletters, cijfers en symbolen. Deze instelling geeft aan hoeveel verschillende tekensets moeten worden opgenomen in het wachtwoord). Voor iOS-apparaten geeft u hiermee echter het aantal symbooltekens aan dat moet zijn opgenomen in het wachtwoord)|Ja|Ja|
|**Minimale wachtwoordlengte**|Hiermee geeft u het minimumaantal tekens op dat in het wachtwoord is vereist.|Ja|Ja|
|**Eenvoudige wachtwoorden toestaan**|Eenvoudige wachtwoorden zijn onder andere '0000' en '1234'|Ja|Ja|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het apparaat wordt gewist**|Hiermee geeft u het aantal keren op dat een onjuist wachtwoord kan worden onthouden voordat het apparaat wordt gewist.|Ja|Ja|
|**Minuten van inactiviteit voordat het scherm wordt uitgeschakeld**|Hiermee geeft u de hoeveelheid tijd op die een apparaat niet-actief moet blijven voordat het scherm automatisch wordt vergrendeld.|Ja|Ja|
|**Wachtwoordverlooptijd (dagen)**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden**|Hiermee geeft u op of eerder gebruikte wachtwoorden worden onthouden om te voorkomen dat de gebruiker deze opnieuw gebruikt.|Ja|Ja|
|**Wachtwoordgeschiedenis onthouden** – **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u aan hoeveel eerder gebruikte wachtwoorden er worden onthouden.|Ja|Ja|

### Versleutelingsinstellingen

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Versleuteling vereisen voor mobiel apparaat**|Hiervoor is vereist dat de gegevens op ondersteunde mobiele apparaten moeten worden versleuteld.<br>Voor Windows Phone 8-apparaten moet u dit instellen op **Ja**.|Ja|Ja|

### Systeeminstellingen

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Schermafbeelding toestaan**|Hiermee kan de gebruiker de inhoud van het scherm als afbeelding vastleggen.|Nee|Ja|
|**Verzending van diagnostische gegevens toestaan**|Hiermee kunt u toestaan dat het apparaat diagnostische gegevens naar Microsoft verzendt.|Nee|Ja|

### Cloudinstellingen - accounts en synchronisatie

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Microsoft-account toestaan**|Hiermee kunt u een Microsoft-account aan het apparaat koppelen.|Nee|Ja|

### E-mailinstellingen

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Aangepaste e-mailaccounts toestaan**|Hiermee kunt u toestaan dat het apparaat verbinding maakt met niet-Microsoft-e-mailaccounts.|Nee|Ja|

### Toepassingsinstellingen - browser

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Webbrowser toestaan**|Hiermee kunt u de ingebouwde webbrowser op apparaten toestaan of blokkeren.|Nee|Ja|

### Toepassingsinstellingen - apps

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Toepassingsarchief toestaan**|Hiermee kunnen gebruikers verbinding maken met de app store van het apparaat.|Nee|Ja|

### Instellingen voor apparaatmogelijkheden - hardware

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Camera toestaan**|Hiermee kunt u het gebruik van de camera van het apparaat toestaan of blokkeren.|Nee|Ja|
|**Verwisselbare opslag toestaan**|Hiermee kan het apparaat verwisselbare opslag gebruiken, bijvoorbeeld een SD-kaart.|Ja|Ja|
|**Wi-Fi toestaan**|Hiermee schakelt u de Wi-Fi-functionaliteit van het apparaat in of uit.|Nee|Ja|
|**Wi-Fi-tethering toestaan**|Hiermee staat u het gebruik van Wi-Fi-tethering op het apparaat toe.|Nee|Ja
|**Automatische verbinding met gratis Wi-Fi-hotspots toestaan**|Hiermee kan het apparaat automatisch verbinding maken met gratis Wi-Fi-hotspots en automatisch alle gebruiksvoorwaarden accepteren.|Nee|Ja|
|**Melden van Wi-Fi-hotspots toestaan**|Hiermee kan er informatie over Wi-Fi-verbindingen worden verzonden om verbindingen in de buurt te detecteren.|Nee|Ja|
|**Geolocatie toestaan**|Hiermee kan het apparaat locatiegegevens gebruiken.|Nee|Ja|
|**NFC toestaan**|Hiermee staat u bewerkingen toe waarvoor Near Field Communication wordt gebruikt.|Nee|Ja|
|**Bluetooth toestaan**|Hiermee schakelt u de Bluetooth-functionaliteit van het apparaat in of uit.|Nee|Ja|

### Instellingen voor apparaatmogelijkheden - functies

|Naam van de instelling|Details|Windows Phone 8|Windows Phone 8,1|
|----------------|-----------------------------------------|
|**Kopiëren en plakken toestaan**|Hiermee staat u kopiëren en plakken op apparaten toe.|Nee|Ja|

### Instellingen voor compatibele en niet-compatibele apps
In de lijst **Compatibele en&amp; niet-compatibele apps** geeft u een lijst met compatibele of niet-compatibele apps op met behulp van de volgende gegevens:

> [!NOTE]
> Een enkele beleidsregel kan alleen een lijst met compatibele of een lijst met niet-compatibele apps bevatten. U kunt niet beide in dezelfde beleidsregel opgeven.

|Naam van de instelling|Details|
|----------------|--------------------|
|**Apparaten mogen apps in lijst niet openen**|Hiermee wordt een lijst gemaakt met de apps die niet worden beheerd door Intune en die niet mogen worden geïnstalleerd en uitgevoerd door gebruikers.|
|**Alleen de apps in de lijst mogen op apparaten worden geïnstalleerd**|Hiermee wordt een lijst gemaakt met de apps die gebruikers mogen installeren. Gebruikers mogen geen andere apps installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.|
|**Toevoegen**|Hiermee voegt u een app toe aan de geselecteerde lijst. Geef een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store. Zie 'URL's voor app stores opgeven' verderop in dit onderwerp voor meer informatie.
|**Apps importeren**|Hiermee importeert u een lijst met apps die u hebt opgegeven in een bestand met door komma's gescheiden waarden. Gebruik de notatie, toepassingsnaam, uitgever en app-URL in het bestand.|
|**Bewerken**|Hiermee kunt u de naam, de uitgever en de URL van de geselecteerde app bewerken.|
|**Verwijderen**|Hiermee verwijdert u de geselecteerde app uit de lijst.|
> [!IMPORTANT]
> Als u een lijst met toegestane apps voor Windows Phone 8.1-apparaten opgeeft, moet u de Bedrijfsportal-app aan deze lijst toevoegen, anders wordt deze app geblokkeerd.


### Referentie-informatie voor compatibele en niet-compatibele apps

#### URL's voor app stores opgeven
Als u een app-URL wilt opgeven in de lijst met compatibele apps, gebruikt u de volgende notatie:

Zoek in de pagina [Windows Phone Apps+Games](http://www.windowsphone.com/en-us/store/overview) naar de app die u wilt gebruiken.

Open de pagina van de app en kopieer de URL naar het klembord. U kunt deze nu als de URL gebruiken in de lijst met compatibele apps of de lijst met niet-compatibele apps.

**Voorbeeld:** Zoek in de store naar de Skype-app. De URL die u gebruikt, is **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Aangepaste beleidsinstellingen 
Gebruik het **aangepaste configuratiebeleid voor Windows Phone** van Microsoft Intune om OMA-URI-instellingen (Open Mobile Alliance Uniform Resource Identifier) te implementeren die kunnen worden gebruikt om de functies voor **Windows Phone 8.1-apparaten** te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Windows Phone-instellingen implementeren die niet met het algemene configuratiebeleid van Intune kunnen worden geconfigureerd. Zie [Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) voor informatie over de instellingen die u met dit beleid kunt configureren.

Zie [MDM-protocoldocumentatie voor Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx) voor meer informatie over het maken van OMA-URI-instellingen voor Windows Phone-apparaten.

### Algemene instellingen

|Naam van de instelling|Details|
|----------------|--------------------|
|**Naam**|Voer een unieke naam in voor het beleid, zodat u het beleid in de Intune-console kunt herkennen.|
|**Beschrijving**|Geef een beschrijving op die een overzicht geeft van het beleid en overige relevante informatie die u helpt om het beleid terug te vinden.|

### OMA-URI-instellingen

Klik in de sectie **OMA-URI-instellingen** op **Toevoegen** om een instelling toe te voegen. U kunt ook een bestaande instelling bewerken of verwijderen.

Geef in het dialoogvenster **OMA-URI-instelling toevoegen of bewerken** de volgende gegevens op:

|Naam van de instelling|Details|
    |--------|--------------------|
    |**Naam van de instelling**|Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
    |**Beschrijving van instelling**|Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    |**Gegevenstype**|Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. U kunt kiezen uit:<br /><br />-   **Tekenreeks**<br />-   **Tekenreeks (XML)**<br />-   **Datum en tijd**<br />-   **Geheel getal**<br />-   **Drijvende komma**<br />-   **Boolean-waarde**|
    |**OMA-URI (hoofdlettergevoelig)**|Geef aan voor welke OMA-URI u een instelling wilt opgeven.|
    |**Waarde**|Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|

### Zie ook
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)




<!--HONumber=Jun16_HO4-->


