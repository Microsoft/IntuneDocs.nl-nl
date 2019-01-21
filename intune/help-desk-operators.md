---
title: Helpdesk voor portal voor probleemoplossing
titlesuffix: Microsoft Intune
description: Medewerkers van de helpdesk gebruiken de Portal voor problemen oplossen voor het oplossen van technische problemen van gebruikers.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 37483f0fa33db109510ee537772a7bdead79e4f3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203549"
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

De portal voor probleemoplossing biedt helpdeskmedewerkers en Intune-beheerders toegang tot gebruikersgegevens om te reageren op hulpaanvragen van gebruikers. Organisaties met een helpdesk kunnen de **Helpdeskmedewerker** toewijzen aan een groep gebruikers. De rol Helpdeskmedewerker kan gebruikmaken van het deelvenster **Problemen oplossen**.

In het deelvenster **Problemen oplossen** worden ook problemen met gebruikersinschrijving vermeld. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen.

Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Intune](/intune/role-based-access-control) voor de stappen voor het toevoegen van een rol helpdeskmedewerker

Wanneer een gebruiker contact opneemt met de ondersteuning vanwege een technisch probleem met Intune, voert de helpdeskmedewerker de naam van de gebruiker in. Intune toont nuttige gegevens waarmee veel laag-1-problemen kunnen worden opgelost, waaronder:

- Gebruikersstatus
- Toewijzingen
- Problemen met naleving
- Apparaat reageert niet
- Ophalen van VPN- of Wi-Fi-instellingen lukt niet apparaat
- Fout tijdens installatie van app

## <a name="to-review-troubleshooting-details"></a>Details voor probleemoplossing weergeven

In het deelvenster Problemen oplossen kiest u **Gebruiker selecteren** om gebruikersgegevens weer te geven. Met gebruikersgegevens kunt u inzicht krijgen in de huidige status van gebruikers en hun apparaten.  

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Problemen oplossen**.
4. Klik op **Selecteren** om een gebruiker te selecteren om problemen voor op te lossen.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven in het deelvenster Problemenoplossing. In de volgende tabel wordt de informatie uitgelegd.

> [!Note]  
> U kunt het deelvenster **Probleemoplossing** ook openen door in uw browser naar het volgende adres te gaan: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Gebieden in het dashboard problemen oplossen

U kunt het deelvenster **Probleemoplossing** gebruiken om gebruikersgegevens weer te geven.

![](/intune/media/troubleshooting-dash.png)

| Gebied | Naam | Beschrijving |
| ---  | ---  | ---         |
| 1.   | Accountstatus  | Geeft de status van de huidige Intune-tenant weer als **Actief** of **Inactief**.       |
| 2.   | Gebruikersselectie  | De naam van de momenteel geselecteerde gebruiker. Klik op **Gebruiker wijzigen** om een nieuwe gebruiker te kiezen.       |
| 3.   | Gebruikersstatus  | Geeft de status weer van de Intune-licentie van de gebruiker, het aantal apparaten, de nalevingsstatus van elk apparaat, het aantal apps en de nalevingsstatus van de apps.       |
| 4.   | Gebruikersgegevens  | U kunt de lijst gebruiken om de gegevens te selecteren die u in het deelvenster wilt weergeven. <br>U kunt de volgende selecties maken: <ul><li>Client-apps<li>Nalevingsbeleid<li> Configuratiebeleid<li>Beleid voor app-beveiliging <li>Registratiebeperkingen</ul>      |
| 5.   | Groepslidmaatschap  | Hiermee geeft u de groepen weer waarvan de geselecteerde gebruiker momenteel lid is.       |

## <a name="client-apps-reference"></a>Verwijzing client-apps

De apps waarop apparaten worden uitgevoerd die
- worden beheerd door Intune en Azure Active Directory (AD) 
- het eigendom zijn van gebruikers die in Intune en Azure Active Directory (AD) worden beheerd.

### <a name="properties"></a>Eigenschappen

De eigenschappen van client-apps.

| Eigenschap      | Beschrijving                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Naam          | De naam van de toepassing.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Besturingssysteem            | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Type          | U kunt een toewijzingstype kiezen voor elk apparaat.  <br> **Beschikbaar**: gebruikers installeren de app vanuit de bedrijfsportal-app of vanaf de website.  <br> **Niet van toepassing**: de app wordt niet geïnstalleerd en niet weergegeven in de bedrijfsportal. <br> **Verwijderen**: de app wordt verwijderd van apparaten in de geselecteerde groepen.  <br> **Beschikbaar met of zonder inschrijving**: deze app wordt toegewezen aan groepen met gebruikers van wie de apparaten niet zijn ingeschreven met Intune. |
| Laatst gewijzigd | De naam van het type apparaat.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### <a name="devices"></a>Apparaten

Apparaten die worden beheerd door Intune of gebruikers die worden beheerd door Intune of Azure AD.

| Eigenschap           | Beschrijving                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Apparaatnaam        | De naam van het type apparaat.                                                                                                     |
| Beheerd door         | De timestamp van een beleidswijziging.                                                                                              |
| Het type Azure AD-join | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Eigendom          | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**).                                               |
| Compatibel met Intune   | De naam van het type apparaat.                                                                                                     |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| App-installatie | Geeft aan of het installeren van een app op verschillende apparaten is voltooid of mislukt. |
| Besturingssysteem                 | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Besturingssysteemversie         | Het versienummer van het besturingssysteem van het apparaat.                                                                                  |
| Laatste check-in      | De naam van het type apparaat.                                                                                                     |

### <a name="app-protection-status"></a>Status app-beveiliging

Er is een beveiligingsbeleid voor apps beschikbaar voor mobiele apps die integreren met Enterprise Mobility Solution-technologieën (EMS). Deze beleidsregels bieden een basisbeveiliging voor uw bedrijfsgegevens wanneer deze worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

| Eigenschap    | Beschrijving                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**). |
| App-naam    | De naam van de toepassing                                                           |
| Apparaatnaam | De naam van het type apparaat.                                                       |
| Apparaattype | De naam van het type apparaat.                                                       |
| Beleid    | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**). |
| Laatste synchronisatie   | De timestamp van de laatste keer dat het apparaat is gesynchroniseerd met Intune.                   |

## <a name="app-protection-policies-reference"></a>Verwijzing beveiligingsbeleid voor apps

Er is een app-beschermingsbeleid beschikbaar voor mobiele apps die worden geïntegreerd met EMS-technologieën. Deze beleidsregels bieden een basisbeveiliging voor uw bedrijfsgegevens wanneer deze worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

### <a name="properties"></a>Eigenschappen

Deze tabel bevat de status van het app-beveiligingsbeleid voor apparaten die worden beheerd door Intune.

| Eigenschap    | Beschrijving                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Naam        | De naam van de toepassing.                                                                                                        |
| Geïmplementeerd    | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Platform    | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**).                                               |
| Inschrijving  | De naam van het type apparaat.                                                                                                     |
| Laatst bijgewerkt | De timestamp van een beleidswijziging.                                                                                              |

### <a name="devices"></a>Apparaten

Apparaten die worden beheerd door Intune of gebruikers die worden beheerd door Intune of Azure AD.

| Eigenschap           | Tekst                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Apparaatnaam        | De naam van het type apparaat.                                                                                                     |
| Beheerd door         | De timestamp van een beleidswijziging.                                                                                              |
| Het type Azure AD-join | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Eigendom          | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**).                                               |
| Compatibel met Intune   | De naam van het type apparaat.                                                                                                     |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Besturingssysteem                 | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Besturingssysteemversie         | Het versienummer van het besturingssysteem van het apparaat.                                                                                  |
| Laatste check-in      | De naam van het type apparaat.                                                                                                     |

## <a name="compliance-policies-reference"></a>Verwijzing nalevingsbeleid

U moet ervoor zorgen dat de apparaten die worden gebruikt voor toegang tot bedrijfs-apps en -gegevens, voldoen aan bepaalde regels, zoals het gebruik van een pincode voor toegang tot het apparaat en versleuteling van gegevens die op het apparaat zijn opgeslagen.

### <a name="properties"></a>Eigenschappen

De eigenschappen het nalevingsbeleid.

| Eigenschap      | Beschrijving                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Toewijzing    | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Naam          | De naam van de toepassing.                                                                                                        |
| Besturingssysteem            | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Beleidstype   | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** en **Onbekend**).                                               |
| Laatst gewijzigd | De naam van het type apparaat.                                                                                                     |

### <a name="devices"></a>Apparaten

Apparaten die worden beheerd door Intune of gebruikers die worden beheerd door Intune of Azure AD.

| Eigenschap           | Beschrijving                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Apparaatnaam        | De naam van het type apparaat.                                                                                                     |
| Beheerd door         | De timestamp van een beleidswijziging.                                                                                              |
| Het type Azure AD-join | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Eigendom          | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** en **Onbekend**).                                               |
| Compatibel met Intune   | De naam van het type apparaat.                                                                                                     |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Besturingssysteem                 | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Besturingssysteemversie         | Het versienummer van het besturingssysteem van het apparaat.                                                                                  |
| Laatste check-in      | De naam van het type apparaat.                                                                                                     |

### <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Er is een beveiligingsbeleid voor apps beschikbaar voor mobiele apps die integreren met EMS-technologieën. Deze beleidsregels bieden een basisbeveiliging voor uw bedrijfsgegevens wanneer deze worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

| Eigenschap    | Beschrijving                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**). |
| App-naam    | De naam van de toepassing                                                           |
| Apparaatnaam | De naam van het type apparaat.                                                       |
| Apparaattype | De naam van het type apparaat.                                                       |
| Beleid    | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**). |
| Laatste synchronisatie   | De timestamp van de laatste keer dat het apparaat is gesynchroniseerd met Intune.                   |

## <a name="configuration-policies-reference"></a>Referentie voor configuratiebeleid

Er is een app-configuratiebeleid beschikbaar voor mobiele apps met leverancierspecifieke configuraties. 

### <a name="properties"></a>Eigenschappen

De eigenschappen van het configuratiebeleid.

| Eigenschap      | Beschrijving                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Toewijzing    | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Naam          | De naam van de toepassing.                                                                                                        |
| Besturingssysteem            | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Beleidstype   | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**).                                               |
| Laatst gewijzigd | De naam van het type apparaat.                                                                                                     |

### <a name="devices"></a>Apparaten

Apparaten die worden beheerd door Intune of gebruikers die worden beheerd door Intune of Azure AD.

| Eigenschap           | Beschrijving                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Apparaatnaam        | De naam van het type apparaat.                                                                                                     |
| Beheerd door         | De timestamp van een beleidswijziging.                                                                                              |
| Het type Azure AD-join | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Eigendom          | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**).                                               |
| Compatibel met Intune   | De naam van het type apparaat.                                                                                                     |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Besturingssysteem                 | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Besturingssysteemversie         | Het versienummer van het besturingssysteem van het apparaat.                                                                                  |
| Laatste check-in      | De naam van het type apparaat.                                                                                                     |


### <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Er is een beveiligingsbeleid voor apps beschikbaar voor mobiele apps die integreren met EMS-technologieën. Deze beleidsregels bieden een basisbeveiliging voor uw bedrijfsgegevens wanneer deze worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

| Eigenschap    | Beschrijving                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**). |
| App-naam    | De naam van de toepassing                                                           |
| Apparaatnaam | De naam van het type apparaat.                                                       |
| Apparaattype | De naam van het type apparaat.                                                       |
| Beleid    | Het type apparaateigendom (**Bedrijf**, **Persoonlijk** of **Onbekend**). |
| Laatste synchronisatie   | De timestamp van de laatste keer dat het apparaat is gesynchroniseerd met Intune.                   |

## <a name="enrollment-failure-reference"></a>Verwijzing naar inschrijvingsfouten

De tabel met inschrijvingsfouten bevat een lijst met mislukte inschrijvingspogingen. Een apparaat dat in de onderstaande tabel staat, is tijdens een andere poging mogelijk wel goed ingeschreven. Mogelijk worden niet alle mislukte pogingen genoemd. Er is niet voor alle fouten informatie over risicobeperking beschikbaar.

| Tabelkolom | Beschrijving |
|-------------|----------|
| Start inschrijving | De begintijd waarop de gebruiker de inschrijving is gestart. |
| Besturingssysteem | Het besturingssysteem van het apparaat. |
| Besturingssysteemversie | De versie van het besturingssysteem van het apparaat. |
| Mislukt | De reden voor de fout. |

### <a name="failure-details"></a>Foutdetails

Wanneer u een foutenrij kiest, worden meer details weergegeven.

| Sectie | Beschrijving |
|-------------|----------|
| Foutdetails | Een gedetailleerdere verklaring van de fout. |
| Mogelijke herstelbewerkingen | Aanbevolen stappen om de fout op te lossen. Voor sommige fouten zijn mogelijk geen herstelbewerkingen beschikbaar. |
| Resources (optioneel) | Koppelingen voor verder lezen of gebieden in de portal om actie te ondernemen. |

### <a name="enrollment-errors"></a>Inschrijvingsfouten

| Fout | Details |
|-------------|----------|
| iOS-time-out of -fout | Een time-out tussen het apparaat en Intune omdat de gebruiker te lang over het voltooien van de inschrijving doet. |
| Gebruiker niet gevonden of gelicentieerd | De gebruiker mist een licentie of is verwijderd uit de service. |
| Het apparaat is al ingeschreven | Iemand heeft geprobeerd om een apparaat in te schrijven met behulp van de bedrijfsportal op een apparaat dat nog door een andere gebruiker staat ingeschreven. |
| Geen onboarding uitgevoerd in Intune | Er is een geprobeerd het apparaat in te schrijven toen de Intune-autoriteit voor Mobile Device Management (MDM) niet was geconfigureerd. |
| Inschrijvingsautorisatie mislukt | Er is geprobeerd een apparaat in te schrijven met een oude versie van de bedrijfsportal. |
| Apparaat niet ondersteund | Het apparaat voldoet niet aan de minimumvereisten voor Intune-inschrijving. |
| Registratiebeperkingen niet nageleefd | Deze inschrijving is geblokkeerd vanwege een door de beheerder geconfigureerde inschrijvingsbeperking. |
| De apparaatversie is te laag | De beheerder heeft een inschrijvingsbeperking geconfigureerd waarvoor een hogere apparaatversie vereist is. |
| De apparaatversie is te hoog | De beheerder heeft een inschrijvingsbeperking geconfigureerd waarvoor een lagere apparaatversie vereist is. |
| Apparaat kan niet als persoonlijk worden ingeschreven | De beheerder heeft een inschrijvingsbeperking geconfigureerd voor het blokkeren van persoonlijke inschrijvingen en het mislukte apparaat is niet vooraf gedefinieerd als bedrijfseigendom. |
| Apparaatplatform geblokkeerd | De beheerder heeft een inschrijvingsbeperking geconfigureerd die het platform van dit apparaat blokkeert. |
| Bulktoken is verlopen | Het bulktoken in het inrichtingspakket is verlopen. |
| Autopilot-apparaat of -gegevens niet gevonden | Het Autopilot-apparaat is niet gevonden voor inschrijving. |
| Autopilot-profiel niet gevonden of niet toegewezen | Het apparaat beschikt niet over een actief Autopilot-profiel. |
| Onverwachte Autopilot-inschrijvingsmethode | Er is geprobeerd het apparaat in te schrijven met behulp van een niet-toegestane methode. |
| Autopilot-apparaat is verwijderd | Het in te schrijven apparaat is voor dit account uit Autopilot verwijderd. |
| Apparaatlimiet bereikt | Deze inschrijving is geblokkeerd vanwege een door de beheerder geconfigureerde beperking voor de apparaatlimiet. |
| Apple-onboarding | Alle iOS-apparaten zijn op dit moment geblokkeerd voor inschrijving vanwege een ontbrekend of verlopen Apple MDM-pushcertificaat in Intune. |
| Apparaat niet vooraf geregistreerd | Het apparaat is niet vooraf als zakelijk geregistreerd en alle persoonlijke inschrijvingen zijn door een beheerder geblokkeerd. |
| Functie niet ondersteund | De gebruiker probeert zich waarschijnlijk in te schrijven via een methode die niet compatibel is met uw Intune-configuratie. |

## <a name="collect-available-data-from-mobile-device"></a>Beschikbare gegevens verzamelen van mobiel apparaat

Gebruik de volgende bronnen bij het verzamelen van gegevens van apparaten bij het oplossen van problemen van de apparaten van de gebruiker:
  - [iOS-registratiefouten verzenden naar de IT-beheerder](/intune-user-help/send-errors-to-your-it-admin-ios)
  - [Het ondersteuningsteam van het bedrijf helpen met het oplossen van problemen met het apparaat via uitgebreide logboekregistratie](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android)
  - [Android-logboeken naar het ondersteuningsteam van het bedrijf verzenden met een USB-kabel](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [Logboeken met diagnostische gegevens over Android naar de IT-beheerder verzenden via e-mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android)
  - [Android-registratiefouten verzenden naar de IT-beheerder](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)

## <a name="next-steps"></a>Volgende stappen

Ontdek meer over op rollen gebaseerd toegangsbeheer (RBAC) voor het definiëren van rollen in uw bedrijfsapparaten, beheer van mobiele toepassingen, gegevensbeveiligingstaken. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Intune](/intune/role-based-access-control) voor meer informatie.

Ontdek meer over bekende problemen in Microsoft Intune. Zie [Bekende problemen in Microsoft Intune](/intune/known-issues) voor meer informatie.

Informatie over het maken van een ondersteuningsticket en hulp vragen wanneer u deze nodig hebt. [Ondersteuning krijgen](/intune/get-support).
