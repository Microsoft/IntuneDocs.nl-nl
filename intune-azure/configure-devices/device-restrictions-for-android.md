---
title: Intune-apparaatbeperkingsinstellingen voor Android
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp vindt u meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op Android-apparaten.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: fafc2b14d3060f79b92bb9d18aabda6b08737881
ms.lasthandoff: 02/18/2017


---

# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Android- en Samsung KNOX Standard-apparaatbeperkingsinstellingen in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="general"></a>Algemeen
-     **Camera**: hiermee staat u het gebruik van de camera op het apparaat toe.
-     **Kopiëren en plakken**: hiermee staat u het gebruik van de functies voor kopiëren en plakken op het apparaat toe.
-     **Klembord delen tussen apps**: hiermee staat u het gebruik van het kopiëren en plakken van Klembord toe tussen apps (alleen voor Samsung KNOX Standard).
-     **Verzenden van diagnostische gegevens**: hiermee voorkomt u dat de gebruiker diagnostische gegevens vanaf het apparaat kan verzenden.    
-     **Fabrieksinstellingen terugzetten**: hiermee staat u de gebruiker toe de fabrieksinstellingen terug te zetten op het apparaat.
-     **Geolocatie**: hiermee staat u toe dat het apparaat locatiegegevens (alleen voor Samsung KNOX Standard) mag gebruiken.
-     **Uitschakelen**: hiermee staat u toe dat de gebruiker het apparaat mag uitschakelen.<br>Als deze instelling is uitgeschakeld, werkt de instelling **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist** voor Samsung KNOX Standard-apparaten niet.
-     **Schermafbeelding**: hiermee staat u de gebruiker toe om de inhoud van het scherm vast te leggen als afbeelding.
-     **Spraakassistent**: hiermee staat u het gebruik van de Spraakassistent-software op het apparaat toe (alleen voor Samsung KNOX Standard).
-     **Bluetooth**: hiermee staat u het gebruik van Bluetooth op het apparaat toe (alleen voor Samsung KNOX Standard).

## <a name="password"></a>Wachtwoord
-     **Wachtwoord vereist**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.
-     **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in dat een gebruiker moet configureren (tussen 4 en 16 tekens).
-     **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u het aantal minuten van inactiviteit op waarna het apparaat automatisch wordt vergrendeld.
-     **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee geeft u het aantal mislukte aanmeldingen op dat is toegestaan voordat het apparaat wordt gewist.
-     **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.
-     **Vereist wachtwoordtype**: hiermee geeft u het complexiteitsniveau voor het wachtwoord aan en of biometrische apparaten kunnen worden gebruikt.
-     **Wachtwoorden niet opnieuw gebruiken**: hiermee voorkomt u dat eindgebruikers een wachtwoord kunnen maken dat zij al eerder hebben gebruikt.
-     **Ontgrendelen met vingerafdruk**: hiermee staat u de gebruiker toe ondersteunde apparaten te ontgrendelen met een vingerafdruk.
-     **Smart Lock en andere trustagenten**: hiermee kunt u de Smart Lock- functie op compatibele Android-apparaten beheren (Samsung KNOX Standard 5.0 en hoger). Met deze telefoonmogelijkheid, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt (bijvoorbeeld wanneer het is verbonden met een bepaald Bluetooth-apparaat, of wanneer het zich in de buurt van een NFC-tag bevindt.) U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.
-     **Versleuteling**: hiermee geeft u aan dat bestanden op het apparaat moeten worden versleuteld.

## <a name="google-play-store"></a>Google Play Store

-     **Google Play store**: hiermee staat u toe dat de gebruiker toegang tot de Google Play Store op het apparaat kan krijgen (alleen voor Samsung KNOX Standard).

## <a name="restricted-apps"></a>Beperkte apps

Configureer een van de volgende lijsten in de lijst met beperkte apps:

Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en die gebruikers niet mogen installeren en uitvoeren.
Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Om te blijven voldoen aan het beleid, mogen gebruikers apps die niet worden vermeld, niet installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.
Apparaatprofielen die instellingen voor beperkte apps bevatten, moeten worden geïmplementeerd in groepen met gebruikers.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps, voert u de volgende stappen uit:

In het [gedeelte Apps van Google Play](https://play.google.com/store/apps) zoekt u de app die u wilt gebruiken.

Open de installatiepagina voor de app en kopieer vervolgens de URL naar het klembord. U kunt deze nu als de URL gebruiken in de lijst met compatibele apps of de lijst met niet-compatibele apps.

Voorbeeld: zoek in Google Play naar Microsoft Office Mobile. De URL die u gebruikt, is **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst te vullen met waarden uit een CSV-bestand in de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*>. Of klik op **Exporteren** om een CSV-bestand (met dezelfde indeling) te maken met de inhoud van de lijst met beperkte apps.        

## <a name="browser"></a>Browser
-     **Webbrowser**: hiermee geeft u op of de standaardwebbrowser op het apparaat kan worden gebruikt.
-     **Automatisch doorvoeren**: hiermee staat u het gebruik van de functie voor automatisch doorvoeren van de webbrowser toe.
-     **Cookies**: hiermee staat u het gebruik van cookies toe in de webbrowser van het apparaat.
-     **JavaScript**: hiermee staat u de uitvoering van Java-scripts in de webbrowser van het apparaat toe.
-     **Pop-ups**: hiermee staat u het gebruik van pop-upblokkering in de webbrowser toe.

## <a name="cloud-and-storage"></a>Cloud en opslag
-     **Google-back-up**: hiermee staat u het gebruik van Google-back-up toe.
-     **Google-account automatisch synchroniseren**: hiermee staat u toe dat instellingen voor Google-accounts automatisch worden gesynchroniseerd.
-     **Verwisselbare opslag**: hiermee staat u toe dat op het apparaat gebruik mag worden gemaakt van verwisselbare opslag, zoals een SD-kaart (alleen voor Samsung KNOX Standard).
-     **Versleuteling voor opslagkaarten**: hiermee geeft u aan of de opslagkaart van het apparaat moet worden versleuteld.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit
-     **Dataroaming**: hiermee staat u dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk (alleen voor Samsung KNOX Standard).
-     **Sms-/mms-berichten**: hiermee staat u het gebruik van sms- en mms-berichten op het apparaat toe (alleen voor Samsung KNOX Standard).
-     **Nummer inspreken**: hiermee schakelt u de functie Nummer inspreken op het apparaat in of uit (alleen voor Samsung KNOX Standard).
-     **Spraakroaming**: hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk (alleen voor Samsung KNOX Standard).
-     **Bluetooth**: hiermee staat u het gebruik van Bluetooth op het apparaat toe (alleen voor Samsung KNOX Standard).
-     **NFC**: hiermee staat u het uitvoeren van bewerkingen toe waarvoor Near Field Communication wordt gebruikt, mits het apparaat er ondersteuning voor biedt (alleen voor Samsung KNOX Standard).
-     **Wi-Fi**: hiermee staat u het gebruik van de Wi-Fi-mogelijkheden van het apparaat toe (alleen voor Samsung KNOX Standard).
-     **Wi-Fi-tethering**: hiermee staat u het gebruik van Wi-Fi-tethering van het apparaat toe (alleen voor Samsung KNOX Standard).

## <a name="kiosk"></a>Kiosk
-     **Selecteer een beheerde app**: zoek en selecteer de beheerde app die mag worden uitgevoerd wanneer het apparaat zich in de kioskmodus bevindt (apps die zijn opgegeven als een koppeling naar de Store worden momenteel niet ondersteund). Er mogen geen andere apps op het apparaat worden uitgevoerd.
-     **Schermsluimerknop**: hiermee schakelt u de knop voor slaapstand/ontwaken van het scherm in of uit op het apparaat.
-     **Volumeknoppen**: hiermee wordt het gebruik van de volumeknoppen op het apparaat in- of uitgeschakeld.

