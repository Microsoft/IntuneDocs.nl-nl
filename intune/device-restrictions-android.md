---
title: Apparaatbeperkingsinstellingen voor Android in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst met alle Android-apparaatinstellingen die u kunt beheren en beperken in Microsoft Intune. Gebruik deze instellingen om het wachtwoord te beheren, Google Play te openen, apps toe te staan of te blokkeren, browserinstellingen te beheren, apps te blokkeren, back-ups te maken in de Google-cloud en de verbindingsopties te beheren voor berichten, spraak, dataroaming, wifi en bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 731f6f5baaa150210765313ffc60133623e52923
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313696"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings---intune"></a>Android- en Samsung Knox Standard-apparaatbeperkingsinstellingen - Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met Android.

>[!TIP]
>Als de gewenste instellingen niet beschikbaar zijn, kunt u uw apparaten mogelijk configureren met een [aangepast profiel](custom-settings-android.md).

## <a name="general"></a>Algemeen

- **Camera**: hiermee staat u het gebruik van de camera op het apparaat toe.
- **Kopiëren en plakken (alleen voor Samsung Knox)**: hiermee staat u het gebruik van de functies voor kopiëren en plakken op het apparaat toe.
- **Klembord delen tussen apps (alleen voor Samsung Knox)**: hiermee staat u het gebruik van het kopiëren en plakken met Klembord toe tussen apps.
- **Verzenden van diagnostische gegevens (alleen voor Samsung Knox)**: hiermee voorkomt u dat de gebruiker diagnostische gegevens vanaf het apparaat kan verzenden.
- **Wissen (alleen voor Samsung Knox)**: hiermee staat u de gebruiker toe het apparaat te [Wissen](devices-wipe.md).
- **Geolocatie (alleen voor Samsung Knox)**: hiermee staat u toe dat het apparaat locatiegegevens gebruikt.
- **Uitschakelen (alleen voor Samsung Knox)**: hiermee staat u toe dat de gebruiker het apparaat mag uitschakelen.<br>Als deze optie is uitgeschakeld, kan **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist** niet worden ingesteld.
- **Schermafbeelding (alleen voor Samsung Knox)**: hiermee staat u de gebruiker toe om de inhoud van het scherm vast te leggen als afbeelding.
- **Spraakassistent (alleen voor Samsung Knox)**: hiermee staat u het gebruik van spraakassistent-software op het apparaat toe.
- **YouTube (alleen voor Samsung Knox)**: hiermee staat u het gebruik van YouTube op het apparaat toe.
- **Gedeelde apparaten (alleen voor Samsung Knox)**: hiermee kunt u een beheerd Samsung Knox Standard-apparaat configureren als een gedeeld apparaat. In deze modus kunnen eindgebruikers hun Azure AD-referenties gebruiken om zich aan en af te melden bij het apparaat. Het apparaat blijft beheerd, ongeacht of het in gebruik is of niet.<br>Wanneer deze functie wordt gebruikt in combinatie met een SCEP-certificaatprofiel, zorgt u er hiermee voor dat eindgebruikers met hun eigen SCEP-gebruikerscertificaat een apparaat met dezelfde set van apps kunnen delen voor alle gebruikers.  Wanneer ze zich afmelden, worden alle app-gegevens gewist.  Deze functie is beperkt tot LOB-apps.
- **Wijzigingen in datum en tijd blokkeren (Samsung Knox)**: hiermee voorkomt u dat de gebruiker de datum- en tijdinstellingen op het apparaat kan wijzigen. 

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: hiermee geeft u aan dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat.|Ja|Ja|

    > [!NOTE]
    > Voor Samsung Knox-apparaten is tijdens MDM-inschrijving automatisch een pincode van vier cijfers vereist. Voor systeemeigen Android-apparaten is mogelijk automatisch een pincode vereist om te voldoen aan voorwaardelijke toegang.

- **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in dat een gebruiker moet configureren (tussen 4 en 16 tekens).
- **Maximale aantal minuten van inactiviteit voordat het scherm wordt vergrendeld** - voer het maximale aantal minuten van inactiviteit in dat is toegestaan op het apparaat totdat het scherm wordt vergrendeld. Een eindgebruiker kan op een apparaat geen tijdwaarde instellen die groter is dan de geconfigureerde tijd in het profiel. Een eindgebruiker kan een lagere tijdwaarde instellen. Bijvoorbeeld: als het profiel is ingesteld op 15 minuten, kan een eindgebruiker de waarde instellen op 5 minuten. Een eindgebruiker kan de waarde niet instellen op 30 minuten. 
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: hiermee geeft u het aantal mislukte aanmeldingen op dat is toegestaan voordat het apparaat wordt gewist.
- **Wachtwoord verloopt (dagen)**: hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.
-  **Vereist wachtwoordtype**: hiermee geeft u het complexiteitsniveau voor het vereiste wachtwoord aan en of biometrische apparaten kunnen worden gebruikt. U kunt kiezen uit:
    - **Standaardwaarde apparaat**
    - **Lage beveiligingsbiometrie**
    - **Ten minste numeriek**
    - **Numeriek complex**: herhaalde of opeenvolgende cijfers (zoals 1111 of 1234) zijn niet toegestaan.<sup>1</sup>
    - **Ten minste alfabetisch**
    - **Ten minste alfanumeriek**
    - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: hiermee voorkomt u dat eindgebruikers een wachtwoord kunnen maken dat zij al eerder hebben gebruikt.
- **Ontgrendelen met vingerafdruk (alleen voor Samsung Knox)**: hiermee staat u de gebruiker toe ondersteunde apparaten te ontgrendelen met een vingerafdruk.
- **Smart Lock en andere trustagenten**: hiermee kunt u de Smart Lock- functie op compatibele Android-apparaten beheren (Samsung Knox Standard 5.0 en hoger). Met deze telefoonmogelijkheid, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt. Dit kan bijvoorbeeld worden gebruikt wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.
- **Versleuteling**: hiermee geeft u aan dat bestanden op het apparaat moeten worden versleuteld.

    > [!NOTE]
    > Als er een versleutelingsbeleid van kracht is, moeten gebruikers van Samsung Knox-apparaten een complex wachtwoord van zes tekens instellen als wachtwoordcode voor het apparaat.

<sup>1</sup> Voordat u deze instelling aan apparaten toewijst, moet u controleren dat de bedrijfsportal-app op deze apparaten is bijgewerkt naar de nieuwste versie.

Als u de instelling **Numeriek complex** configureert en toewijst aan een apparaat waarop een eerdere versie dan Android 5.0 wordt uitgevoerd, is het volgende van toepassing.
- Als er een eerdere versie dan versie 1704 van de bedrijfsportal-app wordt uitgevoerd, wordt er geen pincodebeleid toegepast op het apparaat en wordt er een foutmelding weergegeven in de Azure-portal.
- Als versie 1704 of later wordt uitgevoerd, kan er alleen een eenvoudig pincode worden toegepast. Android-versies die ouder zijn dan 5.0 bieden geen ondersteuning voor deze instelling. Er wordt geen fout weergegeven in de Azure-portal.


## <a name="google-play-store"></a>Google Play Store

- **Google Play Store (alleen voor Samsung Knox)**: hiermee staat u toe dat de gebruiker toegang tot de Google Play Store op het apparaat kan krijgen.

## <a name="restricted-apps"></a>Beperkte apps

In de lijst met beperkte apps kunt u een van de volgende lijsten configureren voor zowel Android- als Samsung Knox Standard-apparaten:

Lijst met **niet-toegestane apps**: hiermee maakt u een lijst met apps die niet worden beheerd door Intune en waarvan u een melding ontvangt als gebruikers deze installeren en uitvoeren.
Lijst met **goedgekeurde apps**: hiermee maakt u een lijst met apps die gebruikers mogen installeren. Om te blijven voldoen aan het beleid, mogen gebruikers geen andere apps installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.
Apparaatprofielen die instellingen voor beperkte apps bevatten, moeten worden toegewezen aan groepen met gebruikers.

Als u de lijst wilt configureren, klikt u op **Toevoegen** en geeft u een naam van uw keuze op, eventueel de uitgever van de app, en de URL van de app in de App Store.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>De URL naar een app in de Store opgeven

Als u een app-URL wilt opgeven in de lijst met compatibele en niet-compatibele apps, voert u de volgende stappen uit:

In het [gedeelte Apps van Google Play](https://play.google.com/store/apps) zoekt u de app die u wilt gebruiken.

Open de installatiepagina voor de app en kopieer vervolgens de URL naar het klembord. U kunt deze URL nu gebruiken in de lijst met compatibele apps of de lijst met niet-compatibele apps.

Voorbeeld: zoek in het [gedeelte Apps van Google Play](https://play.google.com/store/apps) op **Microsoft Planner**. Gebruik de URL: **https://play.google.com/store/apps/details?id=com.microsoft.planner**.

### <a name="additional-options"></a>Extra opties

U kunt ook op **Importeren** klikken om de lijst op hale uit een csv-bestand. Gebruik de indeling <*app-URL*>, <*app-naam*>, <*app-uitgever*> of klik in het CSV-bestand met de inhoud van de beperkte apps-lijst in dezelfde indeling op **Exporteren**.      

## <a name="browser"></a>Browser

- **Webbrowser (alleen voor Samsung Knox)**: hiermee geeft u aan of de standaardwebbrowser op het apparaat kan worden gebruikt.
- **Automatisch doorvoeren (alleen voor Samsung Knox)**: hiermee staat u het gebruik van de functie voor automatisch doorvoeren van de webbrowser toe.
- **Cookies (alleen voor Samsung Knox)**: hiermee staat u het gebruik van cookies toe in de webbrowser van het apparaat.
- **JavaScript (alleen voor Samsung Knox)**: hiermee staat u de uitvoering van Java-scripts in de webbrowser van het apparaat toe.
- **Pop-ups (alleen voor Samsung Knox)**: hiermee staat u het gebruik van pop-upblokkering in de webbrowser toe.

## <a name="allow-or-block-apps"></a>Apps toestaan of blokkeren

Deze instellingen kunnen worden gebruikt om apps te specificeren die kunnen worden geïnstalleerd of geopend op apparaten die alleen Samsung Knox Standard hebben.
Daarnaast kunt u geïnstalleerde apps opgegeven die voor de gebruiker van het apparaat worden verborgen. Gebruikers kunnen deze apps niet uitvoeren.

- **Apps die mogen worden geïnstalleerd (alleen Samsung Knox Standard)**
- **Apps die nu kunnen worden geopend (alleen Samsung Knox Standard)**
- **Apps die verborgen zijn voor de gebruiker (alleen Samsung Knox Standard)**

Configureer voor elke instelling een lijst met apps aan de hand van een van de volgende methoden:

- **Apps toevoegen op pakketnaam** - Hoofdzakelijk gebruikt voor Line-Of-Business-apps. Vul de naam van de app en de naam van het app-pakket in.
- **Apps toevoegen op URL** - Vul de naam van de app en de URL in de Google Play Store in.
- **Beheerde apps toevoegen** - Selecteer de app die u nodig hebt in de lijst met apps die u beheert met Intune.

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Google-back-up (alleen voor Samsung Knox)**: hiermee wordt het gebruik van Google-back-up toegestaan.
- **Google-account automatisch synchroniseren (alleen voor Samsung Knox)**: hiermee staat u toe dat instellingen voor Google-accounts automatisch worden gesynchroniseerd.
- **Verwisselbare opslag (alleen voor Samsung Knox)**: hiermee staat u toe dat op het apparaat gebruik mag worden gemaakt van verwisselbare opslag, zoals een SD-kaart.
- **Versleuteling voor opslagkaarten (alleen voor Samsung Knox)**: hiermee geeft u aan of de opslagkaart van het apparaat moet worden versleuteld.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit

- **Dataroaming (alleen voor Samsung Knox)**: hiermee staat u dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Sms-/mms-berichten (alleen voor Samsung Knox)**: hiermee staat u het gebruik van sms- en mms-berichten op het apparaat toe.
- **Nummer inspreken (alleen voor Samsung Knox)**: hiermee schakelt u de functie Nummer inspreken op het apparaat in of uit.
- **Spraakroaming (alleen voor Samsung Knox)**: hiermee staat u spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Bluetooth (alleen voor Samsung Knox)**: hiermee staat u het gebruik van Bluetooth op het apparaat toe.
- **NFC (alleen voor Samsung Knox)**: hiermee kunt u bewerkingen uitvoeren waarvoor near field communication wordt gebruikt op ondersteunde apparaten.
- **Wi-Fi (alleen voor Samsung Knox)**: hiermee staat u het gebruik van de Wi-Fi-mogelijkheden van het apparaat toe.
- **Wi-Fi-tethering (alleen voor Samsung Knox)**: hiermee staat u het gebruik van Wi-Fi-tethering van het apparaat toe.

## <a name="kiosk"></a>Kiosk

Kioskinstellingen zijn alleen van toepassing op apparaten met Samsung Knox Standard en alleen op apps die u beheert via Intune.

- **Selecteer een beheerde app** - kies een van de volgende opties voor het toevoegen van een of meer apps die kunnen worden uitgevoerd wanneer het apparaat zich in de kioskmodus bevindt. Er mogen geen andere apps op het apparaat worden uitgevoerd. Vooraf geïnstalleerde browsers kunnen niet worden gedefinieerd als app die mag worden uitgevoerd terwijl het apparaat zich in de kioskmodus bevindt. Als een browser is vereist, kunt u overwegen de [Managed Browser](app-configuration-managed-browser.md) te gebruiken.
    - **Apps toevoegen op pakketnaam**
    - **Apps toevoegen op URL**
    - **Beheerde apps toevoegen**.
- **Schermsluimerknop**: hiermee schakelt u de knop voor slaapstand/ontwaken van het scherm in of uit op het apparaat.
- **Volumeknoppen**: hiermee wordt het gebruik van de volumeknoppen op het apparaat in- of uitgeschakeld.


## <a name="next-steps"></a>Volgende stappen

Volg de instructies in [Apparaatbeperkingsinstellingen configureren](device-restrictions-configure.md) om het beperkingsprofiel voor het apparaat te maken en vervolgens toe te wijzen.
