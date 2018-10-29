---
title: De bedrijfsportal-app configureren
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u de specifieke huisstijl van uw bedrijf kunt toepassen op de Intune-bedrijfsportal-app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/11/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01de402a48362f04680c569c40a812b6a4b83cc6
ms.sourcegitcommit: 38afcff149f9c86e92e5f1eccaa927859c395926
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/12/2018
ms.locfileid: "49307403"
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>De app Microsoft Intune-bedrijfsportal configureren

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

De Microsoft Intune-bedrijfsportal is de plaats waar gebruikers toegang hebben tot bedrijfsgegevens en algemene taken kunnen uitvoeren, zoals apparaten registreren, apps installeren en naar ondersteuningsinformatie van uw IT-afdeling zoeken.        

> [!Tip]        
> Wanneer u de bedrijfsportal aanpast, zijn de configuraties zowel van toepassing op de website als op de apps van de bedrijfsportal.       

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
Voer de ondersteuningsinformatie van uw bedrijf in zodat u werknemer een contactpersoon heeft voor Intune-gerelateerde vragen.       

|Veldnaam|Max. lengte|Meer informatie|
|---|---|---|
|**Naam van de contactpersoon** | 40 | Deze naam wordt weergegeven op de pagina **Contact opnemen met IT**. |
|**Telefoonnummer** | 20 | Dit contactnummer wordt weergegeven op de pagina **Contact opnemen met IT**, zodat werknemers contact met u kunnen opnemen voor ondersteuning. |
|**E-mailadres**| 40 | Dit contactadres wordt weergegeven op de pagina **Contact opnemen met IT**. U moet een geldig e-mailadres invoeren in de notatie `alias@domainname.com`. |
|**Naam van de website**| 40 | Deze naam is de beschrijvende naam die wordt weergegeven voor de URL naar de ondersteuningswebsite. Als u een URL van een ondersteuningswebsite en geen beschrijvende naam opgeeft, wordt in de bedrijfsportal Ga naar de website van IT weergegeven op de pagina **Contact opnemen met IT**. |
|**URL van de site**| 150 | Als u over een ondersteuningswebsite voor uw gebruikers beschikt, kunt u hier de URL opgeven. De URL moet in de notatie `https://www.contoso.com` worden opgegeven. Als u geen URL opgeeft, wordt op de pagina **Contact opnemen met IT** in de bedrijfsportal niets weergegeven voor de ondersteuningswebsite. |
| **Aanvullende informatie**| 120 | Wordt weergegeven op de pagina **Contact opnemen met IT**. |


## <a name="company-branding-customization"></a>Aanpassing bedrijfshuisstijl       
U kunt uw bedrijfsportal aanpassen met uw bedrijfslogo, bedrijfsnaam, themakleur en achtergrond. Als u snel een preview van een huismerkconfiguratie wilt weergeven zonder testapparaat, gaat u naar [portal.manage.microsoft.com](https://portal.manage.microsoft.com). Houd er rekening mee dat het logo dat u uploadt, wordt gebruikt voor e-mailsjablonen.      

### <a name="theme-color"></a>Themakleur
Pas een themakleur toe op de bedrijfsportal. Selecteer een standaardkleur of voer een 6-cijferige hexadecimale code in voor een aangepaste kleur.

|Veldnaam|Meer informatie|
|---|---|
|**Kleurtype**| Selecteer een themakleur die u wilt toepassen op de bedrijfsportal. U kunt een standaardkleur kiezen of een specifieke hexadecimale code invoeren. |
|**Kleur kiezen** of **Hexadecimale kleurcode**| Selecteer een themakleur die u wilt toepassen op de bedrijfsportal. U kunt een standaardkleur kiezen of een specifieke hexadecimale code invoeren. Deze opties zijn afhankelijk van het **Kleurtype** dat u selecteert.  |

### <a name="company-logo"></a>Bedrijfslogo
Upload uw bedrijfslogo zodat deze overal in Intune zichtbaar is.

|Veldnaam|Meer informatie|
|---|---|
|**Bedrijfslogo weergeven**|Als u deze optie inschakelt, kunt u het bedrijfslogo uploaden dat u in uw bedrijfsportal wilt weergeven. U kunt twee logo's uploaden: één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal wit is en één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal de door u geselecteerde themakleur heeft. |
|**Een logo uploaden dat u wilt gebruiken op achtergronden met een themakleur**| Deze optie is beschikbaar als u ervoor kiest om het bedrijfslogo weer te geven. Het logo moet een PNG- of JPG-bestand zijn met een resolutie van maximaal 400 x 400 pixels en een grootte van maximaal 750 kB. |
|**Logo uploaden om te gebruiken op een lichte achtergrond**| Deze optie is beschikbaar als u ervoor kiest om het bedrijfslogo weer te geven. Het logo moet een PNG- of JPG-bestand zijn met een resolutie van maximaal 400 x 400 pixels en een grootte van maximaal 750 kB. |
|**Bedrijfsnaam naast logo weergeven**| Selecteer deze optie om de ingevoerde bedrijfsnaam naast het geüploade logo weergeven. |

Nadat u uw wijzigingen hebt opgeslagen, kunt u boven in de blade **Een voorbeeld van uw instellingen bekijken in de Intune-webportal** kiezen om weer te geven hoe uw configuraties eruit gaan zien.

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

## <a name="next-steps"></a>Volgende stappen

- [De Windows 10-bedrijfsportal-app handmatig toevoegen met Microsoft Intune](store-apps-company-portal-app.md)