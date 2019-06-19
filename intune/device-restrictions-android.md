---
title: Apparaatbeperkingsinstellingen voor Android in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk een lijst met alle Android-apparaatinstellingen die u kunt beheren en beperken in Microsoft Intune. Gebruik deze instellingen om het wachtwoord te beheren, Google Play te openen, apps toe te staan of te blokkeren, browserinstellingen te beheren, apps te blokkeren, back-ups te maken in de Google-cloud en de verbindingsopties te beheren voor berichten, spraak, dataroaming, wifi en bluetooth.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ayesham, chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f13b78e05b9f0b94d98677004c7059f1acaa80f9
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045724"
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-lists-in-intune"></a>Lijsten met apparaatbeperkingen voor Android en Samsung Knox Standard in Intune

In dit artikel komt u meer te weten over de Microsoft Intune-apparaatbeperkingsinstellingen die u kunt configureren voor apparaten met Android.

>[!TIP]
>Als de gewenste instellingen niet beschikbaar zijn, kunt u uw apparaten mogelijk configureren met een [aangepast profiel](custom-settings-android.md).

## <a name="general"></a>Algemeen

- **Camera**: kies **Blokkeren** om toegang tot de camera te voorkomen. **Niet geconfigureerd**: staat toegang tot de camera van het apparaat toe.
- **Kopiëren en plakken (alleen voor Samsung Knox)** : kies **Blokkeren** om kopiëren en plakken te voorkomen. **Niet geconfigureerd**: hiermee worden functies voor kopiëren en plakken toegestaan op het apparaat.
- **Klembord delen tussen apps (alleen voor Samsung Knox)** : kies  **Blokkeren** om het kopiëren en plakken via het Klembord niet toe te staan tussen apps. **Niet geconfigureerd**: hiermee staat u het gebruik van het Klembord toe voor kopiëren en plakken tussen apps.
- **Verzenden van diagnostische gegevens (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat de gebruiker diagnostische gegevens vanaf het apparaat kan verzenden. **Niet geconfigureerd**: staat de gebruiker toe de gegevens te verzenden.
- **Wissen (alleen voor Samsung Knox)** : hiermee staat u de gebruiker toe het apparaat te [wissen](devices-wipe.md).
- **Geolocatie (alleen voor Samsung Knox)** : kies **Blokkeren** als er op het apparaat geen locatiegegevens mogen worden gebruikt. **Niet geconfigureerd**: hiermee kunnen op het apparaat locatiegegevens worden gebruikt.
- **Uitschakelen (alleen Samsung Knox)** : kies **Blokkeren** om te voorkomen dat de gebruiker het apparaat uitschakelt. Als deze instelling is uitgeschakeld, kan **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist** niet worden ingesteld en werkt deze optie niet. **Niet geconfigureerd**: hiermee staat u toe dat de gebruiker het apparaat mag uitschakelen.
- **Schermafbeelding (alleen voor Samsung Knox)** : kies **Blokkeren** om het maken van schermafbeeldingen te voorkomen. **Niet geconfigureerd**: stelt de gebruiker in staat om de inhoud van het scherm vast te leggen als afbeelding.
- **Spraakassistent (alleen voor Samsung Knox)** : kies **Blokkeren** om de service S Voice uit te schakelen. **Niet geconfigureerd**: hiermee staat u het gebruik van de S Voice-service en -app toe op het apparaat. Deze instelling geldt niet voor Bixby of de spraakassistent voor toegankelijkheid waarmee inhoud op het scherm hardop wordt voorgelezen.
- **YouTube (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat gebruikers de YouTube-app gebruiken. **Niet geconfigureerd**: staat gebruik van de YouTube-app toe op het apparaat.
- **Gedeelde apparaten (alleen voor Samsung Knox)** : hiermee kunt u een beheerd Samsung Knox Standard-apparaat configureren als een gedeeld apparaat. Als deze optie is ingesteld op  **Toestaan**, kunnen eindgebruikers hun Azure AD-referenties gebruiken om zich aan en af te melden bij het apparaat. Het apparaat blijft beheerd, ongeacht of het in gebruik is of niet.</br>Wanneer deze functie wordt gebruikt met een SCEP-certificaatprofiel, zorgt u er hiermee voor dat eindgebruikers een apparaat met dezelfde apps kunnen delen voor alle gebruikers. Elke gebruiker heeft wel een eigen SCEP-gebruikerscertificaat. Wanneer ze zich afmelden, worden alle app-gegevens gewist. Deze functie is beperkt tot LOB-apps. </br>**Niet geconfigureerd**: hiermee wordt voorkomen dat meerdere eindgebruikers zich met hun eigen Azure AD-referenties aanmelden bij de bedrijfsportal-app op het apparaat.
- **Wijzigingen in datum en tijd blokkeren (Samsung Knox)** : kies **Blokkeren** om te voorkomen dat de gebruiker de datum- en tijdinstellingen op het apparaat kan wijzigen. **Niet geconfigureerd**: staat gebruikers toe om de datum- en tijdinstellingen te wijzigen.

## <a name="password"></a>Wachtwoord

- **Wachtwoord**: kies **Vereisen** om af te dwingen dat de eindgebruiker een wachtwoord moet invoeren voor toegang tot het apparaat. **Niet geconfigureerd**: geeft gebruikers toegang tot het apparaat zonder dat ze een wachtwoord hoeven in te voeren.

    > [!NOTE]
    > Voor Samsung Knox-apparaten is tijdens MDM-inschrijving automatisch een pincode van vier cijfers vereist. Voor systeemeigen Android-apparaten is mogelijk automatisch een pincode vereist om te voldoen aan voorwaardelijke toegang.

- **Minimale wachtwoordlengte**: voer de minimale lengte van het wachtwoord in dat een gebruiker moet invoeren (tussen 4 en 16 tekens).
- **Maximale aantal minuten van inactiviteit voordat het scherm wordt vergrendeld**: voer het maximale aantal minuten van inactiviteit in dat is toegestaan op het apparaat totdat het scherm wordt vergrendeld. Een eindgebruiker kan op een apparaat geen tijdwaarde instellen die groter is dan de geconfigureerde tijd in het profiel. Een eindgebruiker kan een lagere tijdwaarde instellen. Bijvoorbeeld: als het profiel is ingesteld op 15 minuten, kan een eindgebruiker de waarde instellen op 5 minuten. Een eindgebruiker kan de waarde niet instellen op 30 minuten. 
- **Aantal mislukte aanmeldingen voordat een apparaat wordt gewist**: voer het aantal mislukte aanmeldingen in dat is toegestaan voordat het apparaat wordt gewist.
- **Wachtwoord verloopt (dagen)** : voer het aantal dagen in voordat het wachtwoord voor het apparaat moet worden gewijzigd.
- **Vereist wachtwoordtype**: geef het vereiste complexiteitsniveau voor het wachtwoord op en of biometrische apparaten kunnen worden gebruikt. Uw opties zijn:
  - **Standaardwaarde apparaat**
  - **Lage beveiligingsbiometrie**
  - **Ten minste numeriek**
  - **Numeriek complex**: herhaalde of opeenvolgende cijfers, zoals '1111' of '1234', zijn niet toegestaan.<sup>1</sup>
  - **Ten minste alfabetisch**
  - **Ten minste alfanumeriek**
  - **Minstens alfanumeriek met symbolen**
- **Wachtwoorden niet opnieuw gebruiken**: hiermee voorkomt u dat eindgebruikers een wachtwoord kunnen maken dat zij al eerder hebben gebruikt.
- **Ontgrendelen met vingerafdruk (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat vingerafdrukken kunnen worden gebruikt om het apparaat te ontgrendelen. **Niet geconfigureerd**: staat de gebruiker toe het apparaat te ontgrendelen met een vingerafdruk.
- **Smart Lock en andere trustagenten**: kies **Blokkeren** om te voorkomen dat Smart Lock of andere trustagenten instellingen voor het vergrendelingsscherm aanpassen (Samsung KNOX Standard 5.0 +). Met deze telefoonfunctie, ook wel een vertrouwensagent genoemd, kunt u het wachtwoord voor het vergrendelingsscherm op het apparaat uitschakelen of overslaan als het apparaat zich op een vertrouwde locatie bevindt. Deze functie kan bijvoorbeeld worden gebruikt wanneer het apparaat is verbonden met een bepaald Bluetooth-apparaat of wanneer het zich in de buurt van een NFC-tag bevindt. U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.
- **Versleuteling**: kies **Vereisen** om bestanden op het apparaat te versleutelen. Niet alle apparaten ondersteunen versleuteling. Om deze functie te gebruiken, moet u ook het volgende doen: 
  1. Stel **Wachtwoord** in op **Vereisen**.
  2. Stel **Vereist wachtwoordtype** in op **Ten minste numeriek**.
  3. Stel **Minimale wachtwoordlengte** in op ten minste 4 om naleving voor deze instelling juist te rapporteren.

  > [!NOTE]
  > Als er een versleutelingsbeleid van kracht is, moeten gebruikers van Samsung Knox-apparaten een complex wachtwoord van zes tekens instellen als wachtwoordcode voor het apparaat.

<sup>1</sup> Voordat u deze instelling aan apparaten toewijst, moet u controleren of de bedrijfsportal-app op deze apparaten is bijgewerkt naar de nieuwste versie.

Als u  **Vereist wachtwoordtype** instelt op **Numeriek complex** en het beleid vervolgens toewijst aan een apparaat waarop een versie van Android eerder dan 5.0 wordt uitgevoerd, is het volgende van toepassing:

- Als er een eerdere versie dan versie 1704 van de bedrijfsportal-app wordt uitgevoerd, wordt er geen pincodebeleid toegepast op het apparaat en wordt er een foutmelding weergegeven in de Azure-portal.
- Als versie 1704 of later wordt uitgevoerd, kan er alleen een eenvoudig pincode worden toegepast. Versies van Android die ouder zijn dan 5.0 bieden geen ondersteuning voor deze instelling. Er wordt geen fout weergegeven in de Azure-portal.

## <a name="google-play-store"></a>Google Play Store

- **Google Play Store (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat gebruikers de Google Play Store gebruiken. **Niet geconfigureerd**: hiermee staat u toe dat de gebruiker toegang heeft tot de Google Play Store op het apparaat.

## <a name="restricted-apps"></a>Beperkte apps

Gebruik deze instellingen om bepaalde apps op het apparaat toe te staan of te blokkeren. Deze functie wordt ondersteund op Android- en Samsung Knox Standard-apparaten:

- **Verboden apps**: een lijst met apps die niet worden beheerd in Intune die u beter niet kunt installeren op het apparaat. Als een gebruiker een app uit deze lijst installeert, ontvangt u een melding van Intune.
- **Goedgekeurde apps**: een lijst met goedgekeurde apps die gebruikers mogen installeren. Om te voldoen aan het beleid, mogen gebruikers geen andere apps installeren. Apps die worden beheerd door Intune, zijn automatisch toegestaan.

Als u apps wilt toevoegen aan deze lijsten, kunt u:

- De Google Play Store-URL van de gewenste app **toevoegen**. Als u bijvoorbeeld de app voor het Extern bureaublad van Microsoft voor Android wilt toevoegen, voert u `https://play.google.com/store/apps/details?id=com.microsoft.rdc.android` in. Als u de URL van een app wilt vinden, opent u de [Google Play Store](https://play.google.com/store/apps) en zoekt u de app. Zoek bijvoorbeeld naar `Microsoft Remote Desktop Play Store` of `Microsoft Planner`. Selecteer de app en kopieer de URL.
- Importeer een CSV-bestand met details over de app, inclusief de URL. Gebruik de indeling <*app-url*>, <*appnaam*>, <*app-uitgever*>. Of een bestaande lijst **exporteren** die de beperkte apps bevat in dezelfde indeling.

> [!IMPORTANT]
> Apparaatprofielen die instellingen voor beperkte apps gebruiken, moeten worden toegewezen aan groepen gebruikers.

## <a name="browser"></a>Browser

- **Webbrowser (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat de standaardwebbrowser op het apparaat wordt gebruikt. **Niet geconfigureerd**: hiermee kan de standaardwebbrowser van het apparaat worden gebruikt.
- **Automatisch invullen (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat tekst automatisch wordt ingevuld in de browser. **Niet geconfigureerd**: hiermee staat u het gebruik van de functie voor automatisch invullen van de webbrowser toe.
- **Cookies (alleen voor Samsung Knox)** : geef aan hoe u cookies van websites wilt afhandelen op het apparaat. Uw opties zijn:
  - Toestaan
  - Alle cookies blokkeren
  - Cookies van bezochte websites toestaan
  - Cookies van huidige website toestaan
- **JavaScript (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat de webbrowser Java-scripts uitvoert. **Niet geconfigureerd**: hiermee staat u toe dat de webbrowser Java-scripts uitvoert op het apparaat.
- **Pop-ups (alleen voor Samsung Knox)** : kies **Blokkeren** om de weergave van pop-ups in de webbrowser te voorkomen. Met **Niet geconfigureerd** zijn pop-ups toegestaan in de webbrowser.

## <a name="allow-or-block-apps"></a>Apps toestaan of blokkeren

Gebruik deze instellingen om specifieke apps toe te staan, te blokkeren of te verbergen voor Samsung Knox Standard-apparaten. Apps die verborgen zijn, kunnen niet worden geopend of worden uitgevoerd door de gebruiker.

Uw opties zijn:

- **Apps die mogen worden geïnstalleerd (alleen Samsung Knox Standard)**
- **Apps die nu kunnen worden geopend (alleen Samsung Knox Standard)**
- **Apps die verborgen zijn voor de gebruiker (alleen Samsung Knox Standard)**

Voeg voor elke instelling een lijst met apps toe. Uw opties zijn:

- **Apps toevoegen op pakketnaam**: voornamelijk gebruikt voor Line-Of-Business-apps. Vul de naam van de app en de naam van het app-pakket in.
- **Apps toevoegen op URL**: voer de naam van de app en de URL in de Google Play Store in.
- **Store-app toevoegen**: selecteer een app uit de bestaande lijst met apps die u in Intune beheert.

## <a name="cloud-and-storage"></a>Cloud en opslag

- **Google-back-up (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat het apparaat synchroniseren met Google-back-up. **Niet geconfigureerd**: hiermee staat u het gebruik van Google-back-up toe.
- **Google-account automatisch synchroniseren (alleen voor Samsung Knox)** : kies **Blokkeren** om de functie voor het automatisch synchroniseren van het Google-account op het apparaat te blokkeren. **Niet geconfigureerd**: toestaan dat instellingen voor Google-accounts automatisch worden gesynchroniseerd.
- **Verwisselbare opslag (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat op het apparaat verwisselbare opslag wordt gebruikt. **Niet geconfigureerd**: hiermee staat u het gebruik toe van verwisselbare opslag, zoals een SD-kaart, op het apparaat.
- **Versleuteling voor opslagkaarten (alleen voor Samsung Knox)** : kies **Vereisen** om in te stellen dat opslagkaarten moeten worden versleuteld. **Niet geconfigureerd**: hiermee kunnen niet-versleutelde opslagkaarten worden gebruikt. Niet alle apparaten ondersteunen versleuteling van opslagkaarten. Neem voor meer informatie contact op met de fabrikant van het apparaat.

## <a name="cellular-and-connectivity"></a>Mobiel en connectiviteit

- **Dataroaming (alleen voor Samsung Knox)** : kies **Blokkeren** om dataroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd**: staat dataroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Sms-/mms-berichten (alleen voor Samsung Knox)** : kies **Blokkeren** om het gebruik van sms- en mms-berichten op het apparaat te voorkomen. **Niet geconfigureerd**: hiermee staat u het gebruik van sms- en mms-berichten toe op het apparaat.
- **Nummer inspreken (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat gebruikers de functie Nummer inspreken op het apparaat gebruiken. **Niet geconfigureerd**: hiermee wordt Nummer inspreken toegestaan op het apparaat.
- **Spraakroaming (alleen voor Samsung Knox)** : kies **Blokkeren** om spraakroaming via het mobiele netwerk te voorkomen. **Niet geconfigureerd**: staat spraakroaming toe wanneer het apparaat verbinding heeft met een mobiel netwerk.
- **Bluetooth (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat Bluetooth wordt gebruikt op het apparaat. **Niet geconfigureerd**: hiermee kan de gebruiker Bluetooth op het apparaat gebruiken.
- **NFC (alleen voor Samsung Knox)** : kies **Blokkeren** om de NFC-technologie (Near Field Communication) te stoppen. **Niet geconfigureerd**: hiermee staat u bewerkingen toe waarvoor NFC wordt gebruikt op ondersteunde apparaten.
- **Wi-Fi (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat Wi-Fi wordt gebruikt op het apparaat. **Niet geconfigureerd**: staat het gebruik van Wi-Fi-functies toe op het apparaat.
- **Wi-Fi-tethering (alleen voor Samsung Knox)** : kies **Blokkeren** om te voorkomen dat Wi-Fi-tethering wordt gebruikt op het apparaat. **Niet geconfigureerd**: hiermee wordt het gebruik van Wi-Fi-tethering op het apparaat toegestaan.

## <a name="kiosk"></a>Kiosk

Kioskinstellingen zijn alleen van toepassing op apparaten met Samsung Knox Standard en alleen op apps die u beheert via Intune.

- Voeg apps toe die moeten worden uitgevoerd wanneer het apparaat in de kiosk-modus staat. In de kiosk-modus worden alleen de apps uitgevoerd die u toevoegt. Apps die niet zijn toegevoegd, worden niet uitgevoerd. Vooraf geïnstalleerde browsers worden niet uitgevoerd als een app wanneer het apparaat in de kiosk-modus staat. Als een browser is vereist, kunt u overwegen de [Managed Browser](app-configuration-managed-browser.md) te gebruiken.

  Opties voor uw app:

  - **Apps toevoegen op pakketnaam**: voornamelijk gebruikt voor Line-Of-Business-apps. Vul de naam van de app en de naam van het app-pakket in.
  - **Apps toevoegen op URL**: voer de naam van de app en de URL in de Google Play Store in.
  - **Store-app toevoegen**: selecteer een app uit de bestaande lijst met apps die u in Intune beheert.

- **Schermsluimerknop**: kies **Blokkeren** om te voorkomen dat de schermsluimerknop wordt gebruikt of om de knop te verbergen. **Niet geconfigureerd**: hiermee kan de knop voor de slaapstand/activeren van het scherm worden gebruikt op het apparaat.
- **Volumeknoppen**: kies **Blokkeren** om te voorkomen dat de gebruiker het volume aanpast door de volumeknoppen uit te schakelen. **Niet geconfigureerd**: staat gebruik van de volumeknoppen toe op het apparaat.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook kiosk-profielen maken voor apparaten met [Android Enterprise](device-restrictions-android-for-work.md#dedicated-device-settings) en [Windows 10](kiosk-settings.md).
