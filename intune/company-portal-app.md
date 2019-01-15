---
title: De bedrijfsportal-app configureren
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u de specifieke huisstijl van uw bedrijf kunt toepassen op de Intune-bedrijfsportal-app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 6d9d6cb1eccd91e7832a9456504c36cb983b4810
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/02/2019
ms.locfileid: "53817378"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>De app Microsoft Intune-bedrijfsportal configureren

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

De Microsoft Intune-bedrijfsportal is de plaats waar gebruikers toegang hebben tot bedrijfsgegevens en algemene taken kunnen uitvoeren, zoals apparaten registreren, apps installeren en naar ondersteuningsinformatie van uw IT-afdeling zoeken.        

> [!Tip]        
> Wanneer u de bedrijfsportal aanpast, zijn de configuraties zowel van toepassing op de website als op de apps van de bedrijfsportal. Houd er rekening mee dat gebruikers een Intune-licentie nodig hebben die is toegewezen aan de bedrijfsportal-website.

Een aangepaste bedrijfsportal geeft uw eindgebruikers een vertrouwde en nuttige ervaring. Voor het aanpassen van de bedrijfsportal kiest u vanuit de workload **Client-apps** de optie **Instellen** > **Aangepaste stijl van de bedrijfsportal** en configureert u vervolgens de vereiste instellingen.  

> [!Note]       
> Als u gebruikmaakt van Azure Government, worden er app-logboeken aangeboden aan de eindgebruiker zodat deze kan beslissen hoe deze de logboeken graag wil delen wanneer er een probleem moet worden opgelost. Als u niet gebruikmaakt van Azure Government, worden vanuit de bedrijfsportal voor Windows 10 app-logboeken rechtstreeks naar Microsoft verzonden wanneer de gebruiker hulp nodig heeft bij het oplossen van een probleem. Als de app-logboeken naar Microsoft worden verzonden, is het eenvoudiger om problemen op te lossen. 

## <a name="company-information-and-privacy-statement"></a>Bedrijfsinformatie en privacyverklaring        
De bedrijfsnaam wordt weergegeven als de titel van de bedrijfsportal. Wanneer een gebruiker op de privacykoppeling klikt, wordt de privacyverklaring weergegeven.

Velden met een asterisk (*) zijn verplicht.       


| Veldnaam | Max. lengte | Meer informatie |
|---|---|---|
|**Bedrijfsnaam**| 40 | Deze naam wordt weergegeven als de titel van de bedrijfsportal en wordt in Intune als tekst getoond. |
| **URL voor de privacyverklaring** |     79     | U kunt de privacyverklaring van uw eigen bedrijf opgeven. Deze wordt dan weergegeven wanneer gebruikers in de bedrijfsportal op de privacykoppelingen klikken. U moet een geldige URL opgeven in de notatie `<https://www.contoso.com>`. |

## <a name="support-information"></a>Ondersteuningsinformatie      
Voer de ondersteuningsinformatie van uw bedrijf in zodat uw werknemer een contactpersoon heeft voor Intune-gerelateerde vragen.          

|Veldnaam|Max. lengte|Meer informatie|
|---|---|---|
|**Naam van de contactpersoon** | 40 | Deze naam wordt weergegeven op de pagina **Contact opnemen met IT**. |
|**Telefoonnummer** | 20 | Dit contactnummer wordt weergegeven op de pagina **Contact opnemen met IT**, zodat werknemers contact met u kunnen opnemen voor ondersteuning. |
|**E-mailadres**| 40 | Dit contactadres wordt weergegeven op de pagina **Contact opnemen met IT**. U moet een geldig e-mailadres invoeren in de notatie `alias@domainname.com`. |
|**Naam van de website**| 40 | Deze naam is de beschrijvende naam die wordt weergegeven voor de URL naar de ondersteuningswebsite. Als u een URL van een ondersteuningswebsite en geen beschrijvende naam opgeeft, wordt in de bedrijfsportal Ga naar de website van IT weergegeven op de pagina **Contact opnemen met IT**. |
|**URL van de site**| 150 | Als u over een ondersteuningswebsite voor uw gebruikers beschikt, kunt u hier de URL opgeven. De URL moet in de notatie `https://www.contoso.com` worden opgegeven. Als u geen URL opgeeft, wordt op de pagina **Contact opnemen met IT** in de bedrijfsportal niets weergegeven voor de ondersteuningswebsite. |
| **Aanvullende informatie**| 120 | Wordt weergegeven op de pagina **Contact opnemen met IT**. |


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
|**Uw merkafbeelding uploaden**| Deze optie is beschikbaar zodat een achtergrondafbeelding kan worden weergegeven op de profielpagina van de gebruiker in de bedrijfsportal-app.<p>*Opmerking*: de afbeelding wordt op verschillende platformen mogelijk anders weergegeven.<p><ul><li>Aanbevolen breedte van afbeelding: kleiner dan 1125 px, maar niet kleiner dan 640 px</li><li>Maximale afbeeldingsgrootte: 1,3 MB</li><li>Bestandstype: PNG, JPG of JPEG</li></ul>|

Met de juiste merkafbeelding kan het vertrouwen van de gebruiker in de bedrijfsportal-app worden versterkt, doordat de app uw huisstijl weerspiegelt. Hier volgen enkele tips die u kunt gebruiken voor het verkrijgen, kiezen en optimaliseren van een afbeelding voor de bedrijfsportal. 

- Neem contact op met uw marketing- of huisstijlafdeling. Mogelijk beschikken zij al over een goedgekeurde set afbeeldingen. Wellicht kunnen ze u ook helpen bij het naar behoefte optimaliseren van afbeeldingen. 

- Houd rekening met zowel liggende als staande weergave. De afbeelding moet voldoende achtergrond rond het centrale punt hebben. De afbeelding wordt mogelijk verschillend bijgesneden op basis van apparaatgrootte, -oriëntatie en platform. 

- Vermijd het gebruik van een standaardafbeelding. De afbeelding moet het merk en de identiteit van uw bedrijf uitstralen, zoals de gebruikers dit kennen. Als u geen geschikte afbeelding hebt, kunt u nog beter helemaal geen afbeelding gebruiken, dan te kiezen voor een afbeelding die voor de gebruiker geen betekenis heeft. 

- Verwijder onnodige metagegevens. Afbeeldingsbestanden bevatten soms metagegevens, zoals een cameraprofiel, geografische locatie, titel, bijschrift, enzovoort. Gebruik een hulpprogramma voor afbeeldingoptimalisatie voor het verwijderen van deze gegevens. Zo blijft de kwaliteit behouden en kunt u voldoet aan de maximale bestandsgrootte. 

Nadat in Intune een merkafbeelding is toegevoegd of gewijzigd, ziet de eindgebruiker de wijziging mogelijk niet op iOS-apparaten totdat de Bedrijfsportal de wijzigingen bij opstarten heeft herkend en vervolgens opnieuw is opgestart, waarna de merkafbeelding wordt weergegeven. 

### <a name="brand-image-examples"></a>Voorbeelden van merkafbeeldingen

In de volgende afbeelding ziet u een voorbeeld van een merkafbeelding op een iPad:

![Schermafbeelding van een voorbeeld van een merkafbeelding op een iPhone](media/company-portal-app/company-portal-app-03.png)

In de volgende afbeelding ziet u een voorbeeld van een merkafbeelding op een iPhone:

![Schermafbeelding van een voorbeeld van een merkafbeelding op een iPad](media/company-portal-app/company-portal-app-02.png)

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

Eindgebruikers zien ook de beschikbare snelkoppelingen in de Bedrijfsportal-app in Windows.

![Schermafbeelding van beschikbare sneltoetsen in de Windows-bedrijfsportal](media/company-portal-app/company-portal-app-01.png)

## <a name="next-steps"></a>Volgende stappen

- [De Windows 10-bedrijfsportal-app handmatig toevoegen met Microsoft Intune](store-apps-company-portal-app.md)
