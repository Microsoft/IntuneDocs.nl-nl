---
title: De bedrijfsportal aanpassen
description: Met de Intune-bedrijfsportal kunnen gebruikers algemene taken uitvoeren, zoals apparaten registreren, apps installeren en informatie over de IT-afdeling opzoeken.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: eb4a9f01-f857-4563-ab6f-5d0d7dfa659d
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: e54f1a2ab0e62ab3ffcbf6fa1ae6f974c5f18717
ms.contentlocale: nl-nl
ms.lasthandoff: 06/08/2017


---

# <a name="customize-the-company-portal"></a>De bedrijfsportal aanpassen

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

In dit onderwerp wordt aan beheerders uitgelegd hoe ze de Intune bedrijfsportal-app en bedrijfsportal-website kunnen aanpassen.

De Intune-bedrijfsportal is de plaats waar gebruikers toegang hebben tot bedrijfsgegevens en algemene taken kunnen uitvoeren, zoals apparaten registreren, apps installeren en naar ondersteuningsinformatie van uw IT-afdeling zoeken.

De Intune-bedrijfsportal biedt gebruikers toegang tot bedrijfsgegevens en -apps. De bedrijfsportal is beschikbaar in twee vormen:

-   **De bedrijfsportal-app**: een toepassing die beschikbaar is op apparaten die u beheert met Intune. Meer informatie over de bedrijfsportal-apps voor [Android](/intune-user-help/using-your-android-device-with-intune), [iOS](/intune-user-help/using-your-iOS-or-macOS-device-with-intune) en [Windows](/intune-user-help/using-your-windows-device-with-intune).


- **De bedrijfsportalwebsite**: een website waarmee eindgebruikers de meeste taken die ze kunnen verrichten, kunnen uitvoeren via de bedrijfsportal-app. De URL van de Intune-bedrijfsportal is [https://portal.manage.microsoft.com](https://portal.manage.microsoft.com). Meer informatie over deze website vindt u in [De Intune-bedrijfsportalwebsite gebruiken](/intune-user-help/using-the-intune-company-portal-website).

> [!TIP]
> Wanneer u de bedrijfsportal aanpast, zijn de configuraties zowel van toepassing op de website als op de apps van de bedrijfsportal.

Gebruikers kunnen in de bedrijfsportal onder andere de volgende taken uitvoeren:

-   Apparaten inschrijven
-   De status van hun apparaten weergeven
-   Hun apparaat opnieuw instellen
-   Hun wachtwoord opnieuw instellen
-   Hun apparaat op afstand vergrendelen
-   Software downloaden die door uw organisatie is geïmplementeerd
-   Contact opnemen met de IT-afdeling voor ondersteuning

## <a name="customize-company-portal-settings"></a>De instellingen van de bedrijfsportal aanpassen
Een aangepaste bedrijfsportal geeft uw eindgebruikers een vertrouwde en nuttige ervaring. Meld u aan bij de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) als tenant of servicebeheerder. Kies **Beheerder** &gt; **Bedrijfsportal** en configureer de instellingen van de bedrijfsportal.

## <a name="company-contact-information-and-privacy-statement"></a>Contactgegevens en privacyverklaring van bedrijf
De bedrijfsnaam wordt weergegeven als de titel van de bedrijfsportal. Gebruikers zien de contactgegevens en details in het scherm Contact opnemen met IT van de bedrijfsportal. Wanneer een gebruiker op de privacykoppeling klikt, wordt de privacyverklaring weergegeven.

|Veldnaam|Max. lengte|Meer informatie|
    |----------|------------------------|----------------|
    |Bedrijfsnaam|40|Deze naam wordt weergegeven als de titel van de bedrijfsportal.|
    |Naam van contactpersoon IT-afdeling|40|Deze naam wordt weergegeven op de pagina **Contact opnemen met IT**.|
    |Telefoonnummer IT-afdeling|20|Dit contacttelefoonnummer wordt weergegeven op de pagina **Contact opnemen met IT**.|
    |E-mailadres IT-afdeling|40|Dit contactadres wordt weergegeven op de pagina **Contact opnemen met IT**. U moet een geldig e-mailadres invoeren in de notatie **alias@domainname.com**.|
    |Aanvullende informatie|120|Wordt weergegeven op de pagina **Contact opnemen met IT**.|
    |URL van privacyverklaring van bedrijf|79|U kunt de privacyverklaring van uw eigen bedrijf opgeven. Deze wordt dan weergegeven wanneer gebruikers in de bedrijfsportal op de privacykoppelingen klikken. U moet een geldige URL opgeven in de notatie https://www.contoso.com.|

## <a name="support-contacts"></a>Contactpersonen voor ondersteuning
Aan gebruikers in de bedrijfsportal wordt de ondersteuningswebsite weergegeven voor toegang tot onlineondersteuning.

|Veldnaam|Max. lengte|Meer informatie|
    |----------|------------------------|----------------|
    |URL van ondersteuningswebsite|150|Als u over een ondersteuningswebsite voor uw gebruikers beschikt, kunt u hier de URL opgeven. De URL moet in de notatie https://www.contoso.com worden opgegeven. Als u geen URL opgeeft, wordt op de pagina **Contact opnemen met IT** in de bedrijfsportal niets weergegeven voor de ondersteuningswebsite.|
    |Naam website|40|Deze naam is de beschrijvende naam die wordt weergegeven voor de URL naar de ondersteuningswebsite. Als u een URL van een ondersteuningswebsite en geen beschrijvende naam opgeeft, wordt in de bedrijfsportal **Ga naar de website van IT** weergegeven op de pagina **Contact opnemen met IT**.|

## <a name="company-branding-customization"></a>Aanpassing bedrijfshuisstijl
U kunt uw bedrijfsportal aanpassen met uw bedrijfslogo, bedrijfsnaam, themakleur en achtergrond.

|Veldnaam|Meer informatie|
    |----------|----------------|
    |Themakleur|Selecteer een themakleur die u wilt toepassen op de bedrijfsportal.|
    |Bedrijfslogo opnemen|Als u deze optie inschakelt, kunt u het bedrijfslogo uploaden dat u in uw bedrijfsportal wilt weergeven. U kunt twee logo's uploaden: één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal wit is en één dat wordt weergegeven wanneer de achtergrond van de bedrijfsportal de door u geselecteerde themakleur heeft. Beide logo’s moeten png- of jpg-bestanden zijn met een resolutie van maximaal 400 x 100 pixels en een grootte van maximaal 750 kB.|
    |Kies een achtergrond voor de Windows 8-bedrijfsportal-app|Deze instelling is alleen van invloed op de achtergrond voor de bedrijfsportal-app voor Windows 8.|


Nadat u uw wijzigingen hebt opgeslagen, kunt u de koppelingen onder aan de pagina **Bedrijfsportal** van de beheerconsole gebruiken om de bedrijfsportalwebsite weer te geven. Deze koppelingen kunnen niet worden gewijzigd. Wanneer een gebruiker zich aanmeldt, worden via deze koppelingen uw abonnementen weergegeven in de bedrijfsportal.

