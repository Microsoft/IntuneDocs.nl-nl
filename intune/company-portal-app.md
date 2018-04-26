---
title: De bedrijfsportal-app configureren
titleSuffix: Microsoft Intune
description: Meer informatie over hoe u de specifieke huisstijl van uw bedrijf kunt toepassen op de Intune-bedrijfsportal-app.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: dec6f258-ee1b-4824-bf66-29053051a1ae
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aed2bec6e6fea40fdbd78bc487896d167d036f06
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-the-microsoft-intune-company-portal-app"></a>De app Microsoft Intune-bedrijfsportal configureren

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

De Microsoft Intune-bedrijfsportal is de plaats waar gebruikers toegang hebben tot bedrijfsgegevens en algemene taken kunnen uitvoeren, zoals apparaten registreren, apps installeren en naar ondersteuningsinformatie van uw IT-afdeling zoeken.        

> [!Tip]        
> Wanneer u de bedrijfsportal aanpast, zijn de configuraties zowel van toepassing op de website als op de apps van de bedrijfsportal.       

Een aangepaste bedrijfsportal geeft uw eindgebruikers een vertrouwde en nuttige ervaring. Voor het aanpassen van de bedrijfsportal kiest u vanuit de workload **Mobiele apps** de optie **Instellen** > **Aangepaste stijl van de bedrijfsportal** en configureert u vervolgens de vereiste instellingen.      

## <a name="company-contact-information-and-privacy-statement"></a>Contactgegevens en privacyverklaring van bedrijf        
De bedrijfsnaam wordt weergegeven als de titel van de bedrijfsportal. Gebruikers zien de contactgegevens en details in het scherm **Contact opnemen met IT** van de bedrijfsportal. Wanneer een gebruiker op de privacykoppeling klikt, wordt de privacyverklaring weergegeven.        


|                   Veldnaam                   | Max. lengte |                                                                                                 Meer informatie                                                                                                 |
|------------------------------------------------|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         <strong>Bedrijfsnaam</strong>          |     40     |                                                                            Deze naam wordt weergegeven als de titel van de bedrijfsportal.                                                                            |
|  <strong>Naam van contactpersoon IT-afdeling</strong>   |     40     |                                                                         Deze naam wordt weergegeven op de pagina <strong>Contact opnemen met IT</strong>.                                                                          |
|  <strong>Telefoonnummer IT-afdeling</strong>   |     20     |                                                                    Dit contacttelefoonnummer wordt weergegeven op de pagina <strong>Contact opnemen met IT</strong>.                                                                     |
|  <strong>E-mailadres van de IT-afdeling</strong>  |     40     |                       Dit contactadres wordt weergegeven op de pagina <strong>Contact opnemen met IT</strong>. U moet een geldig e-mailadres invoeren in de notatie <strong>alias@domainname.com</strong>.                       |
|    <strong>Aanvullende informatie</strong>     |    120     |                                                                                Wordt weergegeven op de pagina <strong>Contact opnemen met IT</strong>.                                                                                |
| <strong>URL van privacyverklaring van bedrijf</strong> |     79     | U kunt de privacyverklaring van uw eigen bedrijf opgeven. Deze wordt dan weergegeven wanneer gebruikers in de bedrijfsportal op de privacykoppelingen klikken. U moet een geldige URL opgeven in de notatie <strong><https://www.contoso.com></strong>. |

## <a name="support-contacts"></a>Contactpersonen voor ondersteuning     
Aan gebruikers in de bedrijfsportal wordt de ondersteuningswebsite weergegeven voor toegang tot onlineondersteuning.        



|Veldnaam|Max. lengte|Meer informatie|        
|-|-|-|     
|**URL van ondersteuningswebsite**|150|Als u over een ondersteuningswebsite voor uw gebruikers beschikt, kunt u hier de URL opgeven. De URL moet in de notatie **https://www.contoso.com** worden opgegeven. Als u geen URL opgeeft, wordt op de pagina **Contact opnemen met IT** in de bedrijfsportal niets weergegeven voor de ondersteuningswebsite.|        
|**URL van ondersteuningswebsite**|40|Deze naam is de beschrijvende naam die wordt weergegeven voor de URL naar de ondersteuningswebsite. Als u een URL van een ondersteuningswebsite en geen beschrijvende naam opgeeft, wordt in de bedrijfsportal Ga naar de website van IT weergegeven op de pagina **Contact opnemen met IT**.       

## <a name="company-branding-customization"></a>Aanpassing bedrijfshuisstijl       
U kunt uw bedrijfsportal aanpassen met uw bedrijfslogo, bedrijfsnaam, themakleur en achtergrond.     



|Veldnaam|Meer informatie|       
|-|-|       
|**Themakleur**|Selecteer een themakleur die u wilt toepassen op de bedrijfsportal. U kunt een kleur kiezen uit de kleurkiezer of een specifieke hex-code invoeren.|      
|**Bedrijfslogo weergeven**|Als u deze optie inschakelt, kunt u het bedrijfslogo uploaden dat u in uw bedrijfsportal wilt weergeven. U kunt twee logo's uploaden: één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal wit is en één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal de door u geselecteerde themakleur heeft. Beide logo’s moeten png- of jpg-bestanden zijn met een resolutie van maximaal 400 x 100 pixels en een grootte van maximaal 750 kB.<br>U kunt ook de ingevoerde bedrijfsnaam naast het geüploade logo weergeven.|      

Nadat u uw wijzigingen hebt opgeslagen, kunt u **Een voorbeeld van uw instellingen bekijken in de Intune-webportal** kiezen om weer te geven hoe uw configuraties eruit gaan zien.
