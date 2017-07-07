---
title: Intune-apparaatbeperkingsinstellingen voor Android
titleSuffix: Intune on Azure
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op Android-apparaten.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 44d80e1c72b58eccd4e69b1d561c7d651f39b3c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Android- en Samsung KNOX Standard-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gebruik deze instellingen met een restrictiebeleid voor Android-apparaten om apparaten in uw organisatie te configureren.

## <a name="general"></a>Algemeen

|||||
|-|-|-|-|
|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|**Camera**|Gebruik van de camera op het apparaat toestaan.|Ja|Yes|
|**Kopiëren en plakken**|Hiermee wordt kopiëren en plakken toegestaan op het apparaat.|Nee|Ja|
|**Klembord delen tussen apps**|Hiermee staat u het gebruik van het Klembord toe om te kopiëren en plakken tussen apps.|Nee|Yes|
|**Verzending van diagnostische gegevens**|Hiermee voorkomt u dat de gebruiker diagnostische gegevens vanaf het apparaat verzendt.|Nee|Yes|
|**Fabrieksinstellingen terugzetten**|Staat de gebruiker toe om de fabrieksinstellingen terug te zetten op het apparaat.|Nee|Ja|
|**Geolocatie**|Hiermee staat u toe dat het apparaat locatiegegevens gebruikt (alleen voor Samsung KNOX Standard).|Nee|Yes|
|**Uitschakelen**|Hiermee kan de gebruiker het apparaat uitschakelen.<br>Als deze optie is uitgeschakeld, kan **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist** niet worden ingesteld.|Nee|Ja|
|**Schermopname**|Hiermee kan de gebruiker de scherminhoud als afbeelding vastleggen.|Nee|Yes|
|**Spraakassistent**|Hiermee wordt het gebruik van de spraakassistent toegestaan op het apparaat.|Nee|Yes|
|**YouTube**|Hiermee staat u toe dat de YouTube-app wordt gebruikt op het apparaat.|Nee|Ja|
|**Gedeelde apparaten**|Een beheerd Samsung KNOX Standard-apparaat configureren als gedeeld apparaat. In deze modus kunnen eindgebruikers hun Azure AD-referenties gebruiken om zich aan en af te melden bij het apparaat. Het apparaat blijft beheerd, ongeacht of het in gebruik is of niet.<br>Wanneer eindgebruikers zich aanmelden, hebben ze toegang tot apps en wordt er een eventueel beleid toegepast. Wanneer ze zich afmelden, worden alle app-gegevens gewist.|Nee|Yes|

## <a name="password"></a>Wachtwoord

|||||
|-|-|-|-|
|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|**Wachtwoord**|Hiermee stelt u dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.|Yes|Yes|
|**Minimale wachtwoordlengte**|Voer de minimumlengte van het wachtwoord in dat een gebruiker moet opgeven (tussen 4 en 16 tekens).|Yes|Yes|
|**Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**|Geeft het aantal minuten van inactiviteit aan waarna het apparaat automatisch wordt vergrendeld.|Ja|Yes|
|**Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**|Geeft het aantal mislukte aanmeldingen aan dat is toegestaan voordat het apparaat wordt gewist.|Ja|Ja|
|**Dagen tot wachtwoord verloopt**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|Ja|Ja|
|**Vereist wachtwoordtype**|Hiermee geeft u het vereiste complexiteitsniveau voor het wachtwoord aan en of biometrische apparaten kunnen worden gebruikt. U kunt kiezen uit:<br><br>    -     **Standaardwaarde apparaat**<br>-     **Biometrie lage beveiliging**<br>    -     **Minstens numeriek**<br>    -     **Numeriek complex** (herhalende of opeenvolgende nummers zoals 1111 of 1234 zijn niet toegestaan)<sup>1</sup><br>    -     **Minstens alfabetisch**<br>    -     **Minstens alfanumeriek**<br>    -     **Minstens alfanumeriek met symbolen**|Yes|Ja|
|**Wachtwoorden niet opnieuw gebruiken**|Hiermee voorkomt u dat eindgebruikers een wachtwoord kunnen opgeven dat zij al eerder hebben gebruikt.|Yes|Ja|
|**Ontgrendelen met vingerafdruk**|Hiermee staat u toe dat de gebruiker ondersteunde apparaten ontgrendelt met een vingerafdruk.|Nee|Yes|
|**Smart Lock en andere trustagents**|Hiermee kunt u de Smart Lock-functie op compatibele Android-apparaten (Samsung KNOX Standard 5.0 en hoger) beheren. Met deze telefoonmogelijkheid, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt. Dit kan bijvoorbeeld worden gebruikt wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.|Ja (5.0 en hoger)|Yes|
|**Versleuteling**|Vereist dat bestanden op het apparaat zijn versleuteld.|Yes|Yes|

<sup>1</sup> Voordat u deze instelling aan apparaten toewijst, moet u controleren dat de bedrijfsportal-app op deze apparaten is bijgewerkt naar de nieuwste versie.

Als u de instelling **Numeriek complex** configureert en toewijst aan een apparaat waarop een eerdere versie dan Android 5.0 wordt uitgevoerd, is het volgende van toepassing.
- Als er een eerdere versie dan versie 1704 van de bedrijfsportal-app wordt uitgevoerd, wordt er geen pincodebeleid toegepast op het apparaat en wordt er een foutmelding weergegeven in de Intune-portal.
- Als versie 1704 of later wordt uitgevoerd, kan er alleen een eenvoudig pincode worden toegepast. Android-versies die ouder zijn dan 5.0 bieden geen ondersteuning voor deze instelling. Er wordt geen fout weergegeven in de Intune-portal.


## <a name="google-play-store"></a>Google Play Store

|||||
|-|-|-|-|
|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|**Google Play Store**|Hiermee staat u toe dat de gebruiker toegang heeft tot de Google Play Store op het apparaat|Nee|Ja|

## <a name="restricted-apps"></a>Beperkte apps

In de lijst met beperkte apps kunt u een van de volgende lijsten configureren voor zowel Android- als Samsung KNOX Standard-apparaten:

Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren.
Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Om te blijven voldoen aan het beleid, mogen gebruikers geen andere apps installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.
Apparaatprofielen die instellingen voor beperkte apps bevatten, moeten worden toegewezen aan groepen met gebruikers.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps, voert u de volgende stappen uit:

In het [gedeelte Apps van Google Play](https://play.google.com/store/apps) zoekt u de app die u wilt gebruiken.

Open de installatiepagina voor de app en kopieer vervolgens de URL naar het klembord. U kunt deze URL nu gebruiken in de lijst met compatibele apps of de lijst met niet-compatibele apps.

Voorbeeld: zoek in Google Play naar Microsoft Office Mobile. Gebruik de volgende URL: **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst op hale uit een csv-bestand. Gebruik de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*> of klik in het CSV-bestand met de inhoud van de beperkte apps-lijst in dezelfde indeling op **Exporteren**.      

## <a name="browser"></a>Browser
|||||
|-|-|-|-|
|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|**Webbrowser**|Hiermee geeft u op of de standaardwebbrowser op het apparaat kan worden gebruikt.|Nee|Yes|
|**Automatisch doorvoeren**|Hiermee staat u toe dat de functie voor automatisch invullen van de webbrowser wordt gebruikt.|Nee|Yes|
|**Cookies**|Hiermee staat u toe dat de webbrowser van het apparaat gebruikmaakt van cookies.|Nee|Yes|
|**Javascript**|Hiermee staat u toe dat Java-scripts worden uitgevoerd door de webbrowser van het apparaat.|Nee|Yes|
|**Pop-ups**|Hiermee kunt het gebruik van pop-upblokkering in de webbrowser toestaan.|Nee|Yes|

## <a name="cloud-and-storage"></a>Cloud en opslag
|||||
|-|-|-|-|
|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|**Google-back-up**|Hiermee wordt het gebruik van Google-back-up toegestaan.|Nee|Yes|
|**Automatische synchronisatie van Google-accounts**|Toestaan dat instellingen voor Google-accounts automatisch worden gesynchroniseerd.|Nee|Yes|
|**Verwisselbare opslag**|Hiermee staat u het gebruik toe van verwisselbare opslag, zoals een SD-kaart, op het apparaat.|Nee|Ja|
|**Versleuteling op opslagkaarten**|Hiermee geeft u aan of de opslagkaart van het apparaat moet worden versleuteld.|Nee|Yes|

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit
|||||
|-|-|-|-|
|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|**Gegevensroaming**|Hiermee staat u dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Nee|Yes|
|**Sms-/mms-berichten**|Hiermee staat u het gebruik van sms- en mms-berichten toe op het apparaat.|Nee|Yes|
|**Nummer inspreken**|Hiermee wordt de functie voor het inspreken van nummers op het apparaat in- of uitgeschakeld.|Nee|Yes|
|**Spraakroaming**|Hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.|Nee|Yes|
|**Bluetooth**|Hiermee kan de gebruiker Bluetooth op het apparaat gebruiken.|Nee|Ja|
|**NFC**|Hiermee kunt u bewerkingen uitvoeren waarvoor near field communication wordt gebruikt op ondersteunde apparaten.|Nee|Yes|
|**Wi-Fi**|Hiermee kunt het gebruik van de Wi-Fi-mogelijkheden van het apparaat toestaan.|Nee|Yes|
|**Wi-Fi-tethering**|Hiermee kunt het gebruik van Wi-Fi-tethering op het apparaat toestaan.|Nee|Yes|

## <a name="kiosk"></a>Kiosk
|||||
|-|-|-|-|
|Naam van de instelling|Details|Android 4.0+|Samsung KNOX Standard|
|**Een beheerde app selecteren**|Kies een van de volgende opties voor het toevoegen van een of meer apps die kunnen worden uitgevoerd wanneer het apparaat zich in de kioskmodus bevindt. Er mogen geen andere apps op het apparaat worden uitgevoerd.<br><br>- **Apps toevoegen op pakketnaam**<br>- **Apps toevoegen op URL**<br>- **Beheerde apps toevoegen**|Nee|Yes|
|**Schermsluimerknop**|Hiermee wordt de knop voor slaapstand/ontwaken van het scherm in- of uitgeschakeld op het apparaat.|Nee|Yes|
|**Volumeknoppen**|Hiermee wordt het gebruik van de volumeknoppen op het apparaat in- of uitgeschakeld.|Nee|Ja|
