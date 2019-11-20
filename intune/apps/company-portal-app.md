---
title: De bedrijfsportal-app configureren
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u de specifieke huisstijl van uw bedrijf kunt toepassen op de Intune-bedrijfsportal-app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b750c09207b1950aa27a5f2cae1267503537b6e7
ms.sourcegitcommit: 01fb3d844958a0e66c7b87623160982868e675b0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2019
ms.locfileid: "74199199"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>De app Microsoft Intune-bedrijfsportal configureren

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

De Microsoft Intune-bedrijfsportal is de plaats waar gebruikers toegang hebben tot bedrijfsgegevens en algemene taken kunnen uitvoeren, zoals apparaten registreren, apps installeren en naar ondersteuningsinformatie van uw IT-afdeling zoeken. Daarnaast kan de gebruiker via de bedrijfsportal-app veilig toegang krijgen tot bedrijfsresources. De bedrijfsportal-app bevat verschillende pagina's, zoals de startpagina, Apps, App-details, Apparaten en Apparaatdetails. Als u snel apps wilt vinden in de bedrijfsportal, kunt u de apps filteren op de pagina Apps.

> [!IMPORTANT]
> Als u Firebase Cloud Messaging (FCM) van Google wilt ondersteunen, moet u uw Android-bedrijfsportal-app bijwerken naar de nieuwste versie.  

> [!Tip]
> Wanneer u de bedrijfsportal aanpast, zijn de configuraties zowel van toepassing op de website als op de apps van de bedrijfsportal. Houd er rekening mee dat gebruikers een Intune-licentie nodig hebben die is toegewezen aan de bedrijfsportal-website.

Door de bedrijfsportal aan te passen geeft u uw eindgebruikers een vertrouwde en efficiënte ervaring. Selecteer hiervoor in de Intune-portal achtereenvolgens **Client-apps** > **Huisstijl en aanpassing**, en configureer vervolgens de vereiste instellingen.

Wanneer een gebruiker een iOS-toepassing installeert vanuit de bedrijfsportal wordt er een prompt weergegeven. Dit doet zich voor wanneer de iOS-app is gekoppeld aan de App Store, aan een volume-aankoopprogramma (VPP) of aan een Line-Of-Business-app (LOB). Met de prompt kunnen gebruikers de actie accepteren of het beheer van de app toestaan. In de prompt wordt uw bedrijfsnaam weergegeven. Wanneer uw bedrijfsnaam niet beschikbaar is, wordt **Bedrijfsportal** weergegeven. 

> [!Note]
> Als u gebruikmaakt van Azure Government, worden er app-logboeken aangeboden aan de eindgebruiker zodat deze kan beslissen hoe deze de logboeken graag wil delen wanneer er een probleem moet worden opgelost. Als u niet gebruikmaakt van Azure Government, worden vanuit de bedrijfsportal voor Windows 10 app-logboeken rechtstreeks naar Microsoft verzonden wanneer de gebruiker hulp nodig heeft bij het oplossen van een probleem. Als de app-logboeken naar Microsoft worden verzonden, is het eenvoudiger om problemen op te lossen. 

## <a name="company-information-and-privacy-statement"></a>Bedrijfsinformatie en privacyverklaring
De bedrijfsnaam wordt weergegeven als de titel van de bedrijfsportal. Wanneer een gebruiker op de privacykoppeling klikt, wordt de privacyverklaring weergegeven.

| Veldnaam | Max. lengte | Meer informatie |
|---|---|---|
|**Bedrijfsnaam**| 40 | Deze naam wordt weergegeven als de titel van de bedrijfsportal en wordt in Intune als tekst getoond. |
| **URL voor de privacyverklaring** |     79     | U kunt de privacyverklaring van uw eigen bedrijf opgeven. Deze wordt dan weergegeven wanneer gebruikers in de bedrijfsportal op de privacykoppelingen klikken. U moet een geldige URL opgeven in de notatie `<https://www.contoso.com>`. |

> [!NOTE]
> Conform beleid van Microsoft en Apple verkopen we gegevens die met onze service zijn verzameld om geen enkele reden aan externe partijen.

## <a name="support-information"></a>Ondersteuningsinformatie
Voer de ondersteuningsinformatie van uw bedrijf in zodat uw werknemer een contactpersoon heeft voor Intune-gerelateerde vragen.

|Veldnaam|Max. lengte|Meer informatie|
|---|---|---|
|**Naam van de contactpersoon** | 40 | Deze naam wordt weergegeven op de pagina **Help en ondersteuning**. |
|**Telefoonnummer** | 20 | Dit contactnummer wordt weergegeven op de pagina **Help en ondersteuning**, zodat werknemers contact met u kunnen opnemen voor ondersteuning. |
|**E-mailadres**| 40 | Dit contactadres wordt weergegeven op de pagina **Help en ondersteuning**. U moet een geldig e-mailadres invoeren in de notatie `alias@domainname.com`. |
|**Naam van de website**| 40 | Deze naam is de beschrijvende naam die wordt weergegeven voor de URL naar de ondersteuningswebsite. Als u een URL van een ondersteuningswebsite en geen beschrijvende naam opgeeft, wordt in de bedrijfsportal Ga naar de website van IT weergegeven op de pagina **Help en ondersteuning**. |
|**URL van de site**| 150 | Als u over een ondersteuningswebsite voor uw gebruikers beschikt, kunt u hier de URL opgeven. De URL moet in de notatie `https://www.contoso.com` worden opgegeven. Als u geen URL opgeeft, wordt op de pagina **Help en ondersteuning** in de bedrijfsportal niets weergegeven voor de ondersteuningswebsite. |
| **Aanvullende informatie**| 120 | Wordt weergegeven op de pagina **Help en ondersteuning**. |


## <a name="company-identity-branding-customization"></a>Aanpassing bedrijfshuisstijl
U kunt uw bedrijfsportal aanpassen met uw bedrijfslogo, bedrijfsnaam, themakleur en achtergrond.

### <a name="theme-color-and-logo-in-the-company-portal"></a>Themakleur en logo in de bedrijfsportal
Pas een themakleur toe op de bedrijfsportal. Selecteer een standaardkleur of voer een 6-cijferige hexadecimale code in voor een aangepaste kleur.

|Veldnaam|Meer informatie|
|---|---|
|**Een standaardkleur selecteren of een 6-cijferige hexadecimale code invoeren**| Kies **Standard** om een kleur op zicht te selecteren. Kies **Aangepast** om een specifieke kleur te selecteren op basis van een hexadecimale code.|
|**Themakleur kiezen**| Selecteer een themakleur die u wilt toepassen op de bedrijfsportal. U kunt een standaardkleur kiezen of een specifieke hexadecimale code invoeren. |
|**Weergave**| Geef op of **het logo en de naam van het bedrijf**, **alleen het bedrijfslogo** of **alleen de bedrijfsnaam** moet worden weergegeven. |
|**Het bedrijfslogo uploaden**|U kunt het bedrijfslogo uploaden dat u in uw bedrijfsportal wilt weergeven. De tekstkleur wordt automatisch gekozen om een zo hoog mogelijk contrast te bieden. Upload voor de beste weergave een logo met een transparante achtergrond.<p><ul><li>Maximale afbeeldingsgrootte: 400 px x 400 px</li><li>Maximale bestandsgrootte: 750 KB</li><li>Bestandstype: PNG, JPG of JPEG</li></ul>|

Nadat u het logo hebt geüpload, wordt dit met de themakleur weergegeven in het voorbeeldgebied. Als u ervoor kiest om uw bedrijfsnaam weer te geven, wordt deze in het zwart of het wit weergegeven in de bedrijfsportal. De kleur wordt automatisch gekozen op basis van uw themakleur, zodat het hoogst mogelijke contrast wordt bereikt. In het voorbeeldgebied op het scherm wordt uw bedrijfsnaam niet weergegeven. 

### <a name="logo-to-use-on-white-or-light-backgrounds"></a>Logo dat moet worden gebruikt op een witte of lichte achtergrond
Kies een logo dat er het beste uitziet op een witte of lichte achtergrond.

|Veldnaam|Meer informatie|
|---|---|
|**Uw logo uploaden**| Deze optie is beschikbaar als u ervoor kiest om het bedrijfslogo weer te geven. Upload voor de beste weergave een logo met een transparante achtergrond.<p><ul><li>Maximale afbeeldingsgrootte: 400 px x 400 px</li><li>Maximale bestandsgrootte: 750 KB</li><li>Bestandstype: PNG, JPG of JPEG</li></ul>|

### <a name="brand-image-for-company-portal"></a>Merkafbeelding toevoegen voor de bedrijfsportal

Geef een merkafbeelding weer die de huisstijl van uw bedrijf uitstraalt. Nadat u uw wijzigingen hebt opgeslagen, kiest u in de Intune-webportal, boven in de blade **Een voorbeeld van uw instellingen bekijken** om te zien hoe uw configuraties eruit gaan zien. Houd er rekening mee dat u de merkafbeelding alleen kunt bekijken op een iOS-apparaat, en niet in de Intune-webportal. 

|Veldnaam|Meer informatie|
|---|---|
|**Uw merkafbeelding uploaden**| Met deze optie kunt u een merkafbeelding weergeven. Deze wordt op de profielpagina van de gebruiker in de iOS-bedrijfsportal weergegeven als een achtergrondafbeelding.<p><ul><li>Aanbevolen breedte van afbeelding: Groter dan 1125 pixels (minimaal 650 pixels vereist)</li><li>Maximale afbeeldingsgrootte: 1,3 MB</li><li>Bestandstype: PNG, JPG of JPEG</li></ul>|

Met de juiste merkafbeelding kan het vertrouwen van de gebruiker in de bedrijfsportal-app worden versterkt, doordat de app uw huisstijl weerspiegelt. Hier volgen enkele tips die u kunt gebruiken voor het verkrijgen, kiezen en optimaliseren van een afbeelding voor de bedrijfsportal. 

- Neem contact op met uw marketing- of huisstijlafdeling. Mogelijk beschikken zij al over een goedgekeurde set afbeeldingen. Wellicht kunnen ze u ook helpen bij het naar behoefte optimaliseren van afbeeldingen. 

- Houd rekening met zowel liggende als staande weergave. De afbeelding moet voldoende achtergrond rond het centrale punt hebben. De afbeelding wordt mogelijk verschillend bijgesneden op basis van apparaatgrootte, -oriëntatie en platform. 

- Vermijd het gebruik van een standaardafbeelding. De afbeelding moet het merk en de identiteit van uw bedrijf uitstralen, zoals de gebruikers dit kennen. Als u geen geschikte afbeelding hebt, kunt u nog beter helemaal geen afbeelding gebruiken, dan te kiezen voor een afbeelding die voor de gebruiker geen betekenis heeft. 

- Verwijder onnodige metagegevens. Afbeeldingsbestanden bevatten soms metagegevens, zoals een cameraprofiel, geografische locatie, titel, bijschrift, enzovoort. Gebruik een hulpprogramma voor afbeeldingoptimalisatie voor het verwijderen van deze gegevens. Zo blijft de kwaliteit behouden en kunt u voldoet aan de maximale bestandsgrootte. 

Nadat in Intune een merkafbeelding is toegevoegd of gewijzigd, ziet de eindgebruiker de wijziging mogelijk niet op iOS-apparaten totdat de Bedrijfsportal de wijzigingen bij opstarten heeft herkend en vervolgens opnieuw is opgestart, waarna de merkafbeelding wordt weergegeven. 

### <a name="brand-image-examples"></a>Voorbeelden van merkafbeeldingen

In de volgende afbeelding ziet u een voorbeeld van een merkafbeelding op een iPad:

![Schermafbeelding van een voorbeeld van een merkafbeelding op een iPhone](./media/company-portal-app/company-portal-app-03.png)

In de volgende afbeelding ziet u een voorbeeld van een merkafbeelding op een iPhone:

![Schermafbeelding van een voorbeeld van een merkafbeelding op een iPad](./media/company-portal-app/company-portal-app-02.png)

## <a name="privacy-statement-customization"></a>Aanpassing van de privacyverklaring

U kunt de privacyverklaring aanpassen die voor uw organisatie wordt weergegeven op beheerde iOS-apparaten. In dit bericht worden de items vermeld die uw organisatie niet kan zien of uitvoeren op beheerde iOS-apparaten.

Onder **Aanpassing van de bedrijfsportal** > **Apparaatbeheer en privacybericht** kunt u het volgende doen:

- De **standaardinstelling** accepteren om de lijst te gebruiken zoals deze wordt weergegeven, of
- **Aangepast** kiezen om de lijst met items die uw organisatie niet kan zien of uitvoeren op beheerde iOS-apparaten aan te passen. U kunt [Markdown](https://daringfireball.net/projects/markdown/) gebruiken om opsommingstekens, vet, cursief en koppelingen toe te voegen.

## <a name="company-portal-derived-credentials-for-ios-devices"></a>Van de bedrijfsportal afgeleide referenties voor iOS-apparaten
Intune ondersteunt referenties die zijn afgeleid van Personal Identity Verification (PIV) en Common Access Card (CAC), in samenwerking met de referentieproviders DISA Purebred, Entrust Datacard en Intercede. Eindgebruikers voeren na inschrijving aanvullende stappen uit op hun iOS-apparaat om hun identiteit te verifiëren in de toepassing Bedrijfsportal. Afgeleide referenties worden ingeschakeld voor gebruikers door eerst een referentieprovider voor uw tenant in te stellen en vervolgens een profiel dat gebruikmaakt van afgeleide referenties te richten op gebruikers of apparaten.

> [!NOTE]
> De gebruiker ziet instructies over afgeleide referenties op basis van de koppeling die u via Intune hebt opgegeven.

Zie [Afgeleide referenties gebruiken in Microsoft Intune](~/protect/derived-credentials.md) voor meer informatie over afgeleide referenties voor iOS-apparaten.

## <a name="dark-mode-for-ios-company-portal"></a>Donkere modus voor iOS-bedrijfsportal

Donkere modus is beschikbaar voor de iOS-bedrijfsportal. Gebruikers kunnen bedrijfsapps downloaden, hun apparaten beheren en IT-ondersteuning krijgen in het gewenste kleurenschema op basis van hun apparaatinstellingen. De iOS-bedrijfsportal wordt automatisch afgestemd op de apparaatinstellingen van de eindgebruiker voor donkere of lichte modus. 

## <a name="windows-company-portal-keyboard-shortcuts"></a>Sneltoetsen voor Windows-bedrijfsportal

Eindgebruikers kunnen navigatie-, app- en apparaatacties in de Windows-bedrijfsportal activeren met behulp van sneltoetsen (accelerators).

De volgende sneltoetsen zijn beschikbaar in de Windows-bedrijfsportal-app.

| Gebied | Beschrijving | Sneltoets |
|:------------------:|:--------------:|:-----------------:|
| Navigatiemenu | Navigatie | Alt+M |
|  | Home | Alt+H |
|  | Alle apps | Alt+A |
|  | Geïnstalleerde apps | Alt+I |
|  | Feedback verzenden | Alt+F |
|  | Mijn profiel | Alt+U |
|  | Instellingen | Alt+T |
| Startpagina - Apparaattegel | Naam wijzigen | F2 |
|  | Verwijderen | Ctrl+D of Delete |
|  | Toegang controleren | Ctrl+M of F9 |
| Apparaatgegevens | Naam wijzigen | F2 |
|  | Verwijderen | Ctrl+D of Delete |
|  | Toegang controleren | Ctrl+M of F9 |
| App-details | Installeren | Ctrl+I |
| Apparaten | Beschikbaar | Ctrl+D |

Eindgebruikers zien ook de beschikbare snelkoppelingen in de Bedrijfsportal-app in Windows.

![Schermafbeelding van beschikbare sneltoetsen in de Windows-bedrijfsportal](./media/company-portal-app/company-portal-app-01.png)

## <a name="user-self-service-device-actions-from-the-company-portal"></a>Apparaatacties voor selfservicegebruikers van de bedrijfsportal

Gebruikers kunnen acties uitvoeren op hun lokale of externe apparaten via de app of website van de bedrijfsportal. De acties die gebruikers kunnen uitvoeren, kunnen per platform en configuratie van het apparaat verschillen. In alle gevallen kunnen de acties van het externe apparaat alleen worden uitgevoerd door de primaire gebruiker van het apparaat.
- **Buiten gebruik stellen**: hiermee wordt het apparaat uit Intune verwijderd. In de app en op de website van de bedrijfsportal wordt dit weergegeven als **Verwijderen**.
- **Wissen**: met deze actie wordt het apparaat opnieuw ingesteld. Op de website van de bedrijfsportal wordt dit weergegeven als **Opnieuw instellen** en als **Fabrieksinstellingen** in de iOS-bedrijfsportal-app.
- **Naam wijzigen**: met deze actie wijzigt u de apparaatnaam die de gebruiker kan zien in de bedrijfsportal. Alleen de vermelding in de bedrijfsportal wordt gewijzigd. De naam van het lokale apparaat wordt niet gewijzigd.
- **Synchroniseren**: met deze actie wordt een apparaat ingecheckt bij de Intune-service. Dit wordt weergegeven als **Status controleren** in de bedrijfsportal.
- **Extern vergrendelen**: hiermee wordt het apparaat vergrendeld en is een pincode vereist om het apparaat weer te ontgrendelen.
- **Wachtwoordcode opnieuw instellen**: deze actie wordt gebruikt om de wachtwoordcode van het apparaat opnieuw in te stellen. Op iOS-apparaten wordt de wachtwoordcode verwijderd en moet de eindgebruiker een nieuwe code invoeren in Instellingen. Op ondersteunde Android-apparaten wordt een nieuwe wachtwoordcode gegenereerd door Intune, die tijdelijk wordt weergegeven in de bedrijfsportal.
- **Sleutelherstel**: deze actie wordt gebruikt om een persoonlijke herstelsleutel te herstellen voor versleutelde macOS-apparaten vanaf de Bedrijfsportal-website. 

### <a name="self-service-actions"></a>Selfserviceacties

Voor sommige platforms en configuraties zijn geen selfserviceacties voor apparaten toegestaan. De onderstaande tabel bevat meer informatie over selfserviceacties:

|  | Windows 10<sup>(3)</sup> | iOS/iPadOS<sup>(3)</sup> | MacOS<sup>(3)</sup> | Android<sup>(3)</sup> |
|----------------------|--------------------------|-------------------|-----------------------------------|-------------------------|
| Buiten gebruik stellen | Beschikbaar<sup>(1)</sup> | Beschikbaar | Beschikbaar | Beschikbaar<sup>(7)</sup> |
| Wissen | Beschikbaar | Beschikbaar<sup>(5)</sup> | NA | Beschikbaar<sup>(7)</sup> |
| Naam wijzigen<sup>(4)</sup> | Beschikbaar | Beschikbaar | Beschikbaar | Beschikbaar |
| Synchroniseren | Beschikbaar | Beschikbaar | Beschikbaar | Beschikbaar |
| Vergrendelen op afstand | Alleen Windows Phone | Beschikbaar | Beschikbaar | Beschikbaar |
| Wachtwoordcode opnieuw instellen | Alleen Windows Phone | Beschikbaar<sup>(8)</sup> | NA | Beschikbaar<sup>(6)</sup> |
| Sleutelherstel | NA | NA | Beschikbaar<sup>(2)</sup> | NA |

<sup>(1)</sup> **Buiten gebruik stellen** wordt altijd geblokkeerd op Windows-apparaten die zijn toegevoegd aan Azure AD.<br>
<sup>(2)</sup> **Sleutelherstel** voor MacOS is alleen beschikbaar via de webportal.<br>
<sup>(3) </sup> Alle externe acties worden uitgeschakeld als u een Apparaatinschrijvingsmanager-inschrijving gebruikt.<br>
<sup>(4)</sup> Met **Naam wijzigen** wordt alleen de apparaatnaam in de app of webportal van de bedrijfsportal gewijzigd, niet op het apparaat zelf.<br>
<sup>(5)</sup> **Wissen** is niet beschikbaar op door de gebruiker ingeschreven iOS-apparaten.<br>
<sup>(6)</sup> **Wachtwoordcode opnieuw instellen** wordt niet ondersteund in bepaalde Android- en Android Enterprise-configuraties. Zie [De wachtwoordcode van een apparaat opnieuw instellen of verwijderen via Intune](../remote-actions/device-passcode-reset.md) voor meer informatie.<br>
<sup>(7)</sup> **Buiten gebruik stellen** en **Wissen** is niet beschikbaar in Android Enterprise-apparaateigenaarscenario's (COPE, COBO, COSU).<br> 
<sup>(8)</sup> **Wachtwoordcode opnieuw instellen** wordt niet ondersteund voor door de gebruiker ingeschreven iOS-apparaten.

## <a name="next-steps"></a>Volgende stappen

- [De Windows 10-bedrijfsportal-app handmatig toevoegen met Microsoft Intune](company-portal-app.md)
