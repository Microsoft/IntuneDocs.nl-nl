---
title: Microsoft Intune-apparaatbeperkingsinstellingen voor Android
titlesuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken voor het beheren van apparaatinstellingen en functionaliteit op Android-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 100742b378b30eab84b28c01728b2b382dd5155c
ms.sourcegitcommit: af0cc27b05bf0743f7d0970f5f3822f0aab346af
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2018
ms.locfileid: "34190653"
---
# <a name="microsoft-intune-android-and-samsung-knox-standard-device-restriction-settings"></a>Android- en Samsung Knox Standard-apparaatbeperkingsinstellingen in Microsoft Intune 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met Android.

>[!TIP]
>Als de gewenste instellingen niet beschikbaar zijn, kunt u uw apparaten mogelijk configureren met een [aangepast profiel](custom-settings-android.md).

## <a name="general"></a>Algemeen

- **Camera**: hiermee staat u het gebruik van de camera op het apparaat toe.
- **Kopiëren en plakken (alleen voor Samsung Knox)**: hiermee staat u het gebruik van de functies voor kopiëren en plakken op het apparaat toe.
- **Klembord delen tussen apps (alleen voor Samsung Knox)**: hiermee staat u het gebruik van het kopiëren en plakken met Klembord toe tussen apps.
- **Verzenden van diagnostische gegevens (alleen voor Samsung Knox)**: hiermee voorkomt u dat de gebruiker diagnostische gegevens vanaf het apparaat kan verzenden.
- **Fabrieksinstellingen terugzetten (alleen voor Samsung Knox)**: hiermee staat u de gebruiker toe de fabrieksinstellingen terug te zetten op het apparaat.
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
- **Maximum aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: hiermee geeft u het aantal minuten van inactiviteit op waarna het apparaat automatisch wordt vergrendeld.
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
