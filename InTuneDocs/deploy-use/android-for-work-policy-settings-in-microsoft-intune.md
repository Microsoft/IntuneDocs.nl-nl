---

title: Beleidsinstellingen voor Android for Work | Microsoft Docs
description: Beleidsregels maken voor het beheren van instellingen en functies op Android for Work-apparaten die u met Intune beheert.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 02c844a5b38023a6dfc6c4ef1de81e1416601fba
ms.openlocfilehash: b0c3520c7c1fd29a631587fe1a69d4c411099cb4
ms.lasthandoff: 03/07/2017


---

# <a name="android-for-work-policy-settings-in-microsoft-intune"></a>Beleidsinstellingen voor Android for Work in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune biedt diverse ingebouwde algemene instellingen die u op [Android for Work-apparaten](android-for-work.md) kunt configureren.

## <a name="general-configuration-policy"></a>Algemeen configuratiebeleid

Gebruik het Intune **algemene Android for Work-configuratiebeleid** om beveiligings- en werkprofielinstellingen te configureren voor uw Android for Work-apparaten.

Als de instelling die u zoekt niet wordt weergegeven in dit onderwerp, kunt u deze maken met behulp van een aangepast Android-beleid waarmee u OMA-URI-instellingen kunt gebruiken om het apparaat te beheren. Ga naar [Aangepaste beleidsinstellingen](#custom-policy-settings) verderop in dit onderwerp voor meer informatie.

> [!TIP]
> Apparaten worden automatisch versleuteld wanneer u een werkprofiel inricht. U kunt deze instelling niet wijzigen.

### <a name="password-settings"></a>Wachtwoordinstellingen

|Naam van de instelling|Details|
|----------------|-|
|**Wachtwoord vereisen voor het ontgrendelen van mobiele apparaten**|Hiermee wordt opgegeven of een wachtwoord voor beheerde apparaten vereist is. U kunt kiezen uit:<br><br>- **Complex**: vereist ten minste één letter, cijfer en symbool<br>- **Alfanumeriek**: vereist ten minste één cijfer en één letter<br>- **Alfabetisch**: vereist ten minste letters of symbolen<br>- **Numeriek complex**: vereist niet-herhaalde en niet-opeenvolgende numerieke tekens<br>- **Numeriek**<br><br>Als deze instelling niet is ingeschakeld, zijn er geen complexiteitsvereisten.|
|**Minimale wachtwoordlengte**|Hiermee wordt het minimum aantal tekens of cijfers voor het wachtwoord aangegeven.|
|**Aantal minuten inactief voordat het apparaat wordt vergrendeld**|Hiermee wordt het aantal minuten inactiviteit aangegeven waarna het apparaat automatisch wordt vergrendeld.|
|**Smart Lock en andere vertrouwensagents toestaan**<br>(Android 6 en hoger)|Hiermee kunt u de Smart Lock-functie op compatibele Android-apparaten beheren. Met deze telefoonmogelijkheid, soms ook wel vertrouwensagent genoemd, kunt u het vergrendelingsschermwachtwoord op het apparaat uitschakelen of overslaan als het zich op een vertrouwde locatie bevindt (bijvoorbeeld wanneer het is verbonden met een bepaald Bluetooth-apparaat, of wanneer het zich in de buurt van een NFC-tag bevindt.) U kunt deze instelling gebruiken om te voorkomen dat gebruikers Smart Lock configureren.|
|**Aantal mislukte aanmeldingen dat is toegestaan voordat het werkprofiel wordt verwijderd**|Hiermee wordt het aantal mislukte aanmeldingen aangegeven dat is toegestaan voordat het apparaat wordt verwijderd. Hierbij wordt het apparaat niet volledig gewist.|
|**Wachtwoordgeschiedenis onthouden**|Hiermee wordt voorkomen dat eerder gebruikte wachtwoorden opnieuw worden gebruikt.|
|**Wachtwoordgeschiedenis onthouden** - **Wachtwoorden niet opnieuw gebruiken**|Hiermee geeft u het aantal eerder gebruikte wachtwoorden aan dat moeten worden onthouden.|
|**Dagen tot wachtwoord verloopt**|Hiermee geeft u het aantal dagen op voordat het wachtwoord voor het apparaat moet worden gewijzigd.|
|**Vingerafdruk voor ontgrendelen toestaan**<br>(Android 6 en hoger)|Hiermee kunt u een vingerafdruk gebruiken voor het ontgrendelen van apparaten met deze mogelijkheid.|


### <a name="work-profile-settings"></a>Werkprofielinstellingen

|Naam van de instelling|Details|
|----------------|-|
|**Gegevens delen tussen werkprofielen en persoonlijke profielen toestaan**|Hiermee kunnen gegevens van apps in het werkprofiel en apps in het persoonlijke profiel van gebruikers worden gedeeld. U kunt kiezen uit:<br><br>- **Delen buiten grenzen voorkomen**<br>- **Met apps in het werkprofiel kunnen aanvragen voor delen van het persoonlijke profiel worden verwerkt**<br>- **Geen beperkingen voor delen**|
|**Meldingen van het werkprofiel verbergen wanneer het apparaat is vergrendeld**<br>(Android 6 en hoger)|Hiermee bepaalt u of u meldingen van het werkprofiel wilt weergeven wanneer het apparaat is vergrendeld.|
|**Standaardmachtigingsbeleid voor apps instellen**<br>(Android 6 en hoger)|Hiermee stelt u het standaardmachtigingsbeleid in voor alle apps in het werkprofiel. Vanaf Android 6 wordt voor sommige machtigingen voor apps tijdens runtime om goedkeuring gevraagd aan eindgebruikers.  Met deze beleidsinstelling kan de IT-afdeling in het werkprofiel bepalen hoe en of gebruikers om machtiging wordt gevraagd voor apps. <br/><br/>De IT-afdeling kan bijvoorbeeld een app naar het werkprofiel pushen waarvoor toegang tot de locatie is vereist.  Normaal gesproken wordt dan een pop-up in de app getoond met de vraag of de gebruiker de app toegang tot de locatie wilt geven. De gebruiker kan dit dan toestaan of weigeren.  Met dit beleid kan de IT-afdeling beslissen of alle machtigingen automatisch moeten worden toegekend zonder ernaar te vragen, automatisch moeten worden geweigerd zonder ernaar te vragen of dat de eindgebruiker dit mag beslissen.|


## <a name="custom-policy-settings"></a>Aangepaste beleidsinstellingen
Gebruik het **aangepaste Android for Work-configuratiebeleid** van Microsoft Intune om OMA-URI-instellingen te implementeren die kunnen worden gebruikt om de functies op Android for Work-apparaten te beheren. Dit zijn standaardinstellingen die door veel fabrikanten van mobiele apparaten worden gebruikt voor het beheren van apparaatfuncties.

Op deze manier kunt u Android-instellingen implementeren die niet met Intune-beleid kunnen worden geconfigureerd.
Intune biedt momenteel ondersteuning voor een beperkt aantal aangepaste Android-beleidsregels. Zie de voorbeelden in dit onderwerp om na te gaan welk beleid u kunt configureren.

### <a name="general-settings"></a>Algemene instellingen

|Naam van de instelling|Details|
    |----------------|--------------------|
    |**Naam**|Voer een unieke naam in voor het aangepaste Android-beleid, zodat dit gemakkelijk is te herkennen in de Intune-console.|
    |**Beschrijving**|Geef een beschrijving op die een overzicht biedt van het aangepaste Android-beleid, evenals andere relevante informatie die u helpt om het beleid weer te vinden.|

### <a name="oma-uri-settings"></a>OMA-URI-instellingen

   |Naam van de instelling|Details|
    |--------|--------------------|
    |**Naam van instelling**|Voer een unieke naam in voor de OMA-URI-instelling waaraan u deze kunt herkennen in de lijst met instellingen.|
    |**Beschrijving van instelling**|Geef een beschrijving op die een overzicht geeft van de instelling en overige relevante informatie die u helpt om de instelling terug te vinden.|
    |**Gegevenstype**|Selecteer het gegevenstype waarin u deze OMA-URI-instelling opgeeft. Kies uit: **tekenreeks, tekenreeks (XML), datum en tijd, geheel getal, drijvende komma** en **booleaanse waarde**.|
    |**OMA-URI (hoofdlettergevoelig)**|Geef aan voor welke OMA-URI u een instelling wilt opgeven.|
    |**Waarde**|Geef de waarde op die moet worden gekoppeld aan de OMA-URI die u eerder hebt opgegeven.|

### <a name="examples"></a>Voorbeelden

- [Een Wi-Fi-profiel maken met een vooraf gedeelde sleutel](pre-shared-key-wi-fi-profile.md)
- [Een aangepast beleid gebruiken voor een VPN-profiel per app voor Android-apparaten](per-app-vpn-for-android-pulse-secure.md)

### <a name="see-also"></a>Zie tevens
[Instellingen en functies op uw apparaten beheren met Microsoft Intune-beleid](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

