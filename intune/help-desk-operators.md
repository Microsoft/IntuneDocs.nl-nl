---
title: Helpdesk voor portal voor probleemoplossing
titlesuffix: Microsoft Intune
description: Medewerkers van de helpdesk gebruiken de Portal voor problemen oplossen voor het oplossen van technische problemen van gebruikers.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 108382a04095330745ca82dc1d70ab48e70362e5
ms.sourcegitcommit: 0ac196d1d06f4f52f01610eb26060419d248168b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2018
ms.locfileid: "40251865"
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
- Apparaat niet
- Ophalen van VPN- of Wi-Fi-instellingen lukt niet apparaat
- Fout tijdens installatie van app

## <a name="to-review-troubleshooting-details"></a>Details voor probleemoplossing weergeven

In het deelvenster Problemen oplossen kiest u **Gebruiker selecteren** om gebruikersgegevens weer te geven. Met gebruikersgegevens kunt u inzicht krijgen in de huidige status van gebruikers en hun apparaten.  

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Problemen oplossen**.
4. Klik op **Selecteren** om een gebruiker te selecteren om problemen voor op te lossen.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven in het deelvenster Problemenoplossing. In de volgende tabellen wordt de informatie uitgelegd.

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
| 4.   | Gebruikersgegevens  | U kunt de lijst gebruiken om de gegevens te selecteren die u in het deelvenster wilt weergeven. <br>U kunt de volgende selecties maken: <ul><li>Mobiele apps<li>Beleid voor app-beveiliging<li>Nalevingsbeleid<li> Configuratiebeleid</ul>      |
| 5.   | Groepslidmaatschap  | Hiermee geeft u de groepen weer waarvan de geselecteerde gebruiker momenteel lid is.       |

## <a name="mobile-apps-reference"></a>Verwijzing mobiele apps

De apps die worden uitgevoerd op apparaten, of de apparaten die eigendom zijn van gebruikers die worden beheerd door Intune en Azure Active Directory (AD).

### <a name="properties"></a>Eigenschappen

De eigenschappen van mobiele apps.

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
| Eigendom          | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn.                                               |
| Compatibel met Intune   | De naam van het type apparaat.                                                                                                     |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Besturingssysteem                 | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Besturingssysteemversie         | Het versienummer van het besturingssysteem van het apparaat.                                                                                  |
| Laatste check-in      | De naam van het type apparaat.                                                                                                     |

### <a name="app-protection-status"></a>Status app-beveiliging

Er is een beveiligingsbeleid voor apps beschikbaar voor mobiele apps die integreren met Enterprise Mobility Solution-technologieën (EMS). Dit biedt een basisbeveiliging voor uw bedrijfsgegevens wanneer die worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

| Eigenschap    | Beschrijving                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn. |
| App-naam    | De naam van de toepassing                                                           |
| Apparaatnaam | De naam van het type apparaat.                                                       |
| Apparaattype | De naam van het type apparaat.                                                       |
| Beleid    | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn. |
| Laatste synchronisatie   | De timestamp van de laatste keer dat het apparaat is gesynchroniseerd met Intune.                   |

## <a name="app-protection-policies-reference"></a>Verwijzing beveiligingsbeleid voor apps

Er is een beveiligingsbeleid voor apps beschikbaar voor mobiele apps die integreren met EMS-technologieën. Dit biedt een basisbeveiliging voor uw bedrijfsgegevens wanneer die worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

### <a name="properties"></a>Eigenschappen

Deze tabel bevat de status van het app-beveiligingsbeleid voor apparaten die worden beheerd door Intune.

| Eigenschap    | Beschrijving                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Naam        | De naam van de toepassing.                                                                                                        |
| Geïmplementeerd    | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Platform    | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn.                                               |
| Inschrijving  | De naam van het type apparaat.                                                                                                     |
| Laatst bijgewerkt | De timestamp van een beleidswijziging.                                                                                              |

### <a name="devices"></a>Apparaten

Apparaten die worden beheerd door Intune of gebruikers die worden beheerd door Intune of Azure AD.

| Eigenschap           | Tekst                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Apparaatnaam        | De naam van het type apparaat.                                                                                                     |
| Beheerd door         | De timestamp van een beleidswijziging.                                                                                              |
| Het type Azure AD-join | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Eigendom          | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn.                                               |
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
| Beleidstype   | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn.                                               |
| Laatst gewijzigd | De naam van het type apparaat.                                                                                                     |

### <a name="devices"></a>Apparaten

Apparaten die worden beheerd door Intune of gebruikers die worden beheerd door Intune of Azure AD.

| Eigenschap           | Beschrijving                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Apparaatnaam        | De naam van het type apparaat.                                                                                                     |
| Beheerd door         | De timestamp van een beleidswijziging.                                                                                              |
| Het type Azure AD-join | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Eigendom          | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn.                                               |
| Compatibel met Intune   | De naam van het type apparaat.                                                                                                     |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Besturingssysteem                 | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Besturingssysteemversie         | Het versienummer van het besturingssysteem van het apparaat.                                                                                  |
| Laatste check-in      | De naam van het type apparaat.                                                                                                     |

### <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Er is een beveiligingsbeleid voor apps beschikbaar voor mobiele apps die integreren met EMS-technologieën. Dit biedt een basisbeveiliging voor uw bedrijfsgegevens wanneer die worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

| Eigenschap    | Beschrijving                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn. |
| App-naam    | De naam van de toepassing                                                           |
| Apparaatnaam | De naam van het type apparaat.                                                       |
| Apparaattype | De naam van het type apparaat.                                                       |
| Beleid    | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn. |
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
| Beleidstype   | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn.                                               |
| Laatst gewijzigd | De naam van het type apparaat.                                                                                                     |

### <a name="devices"></a>Apparaten

Apparaten die worden beheerd door Intune of gebruikers die worden beheerd door Intune of Azure AD.

| Eigenschap           | Beschrijving                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Apparaatnaam        | De naam van het type apparaat.                                                                                                     |
| Beheerd door         | De timestamp van een beleidswijziging.                                                                                              |
| Het type Azure AD-join | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Eigendom          | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn.                                               |
| Compatibel met Intune   | De naam van het type apparaat.                                                                                                     |
| Compatibel met Azure AD | De status van alle app-beveiligingsapps van de gebruikers. De apps kunnen de status **Ingecheckt** of **Niet ingecheckt** hebben. |
| Besturingssysteem                 | Het besturingssysteem dat op het apparaat is geïnstalleerd.                                                                                       |
| Besturingssysteemversie         | Het versienummer van het besturingssysteem van het apparaat.                                                                                  |
| Laatste check-in      | De naam van het type apparaat.                                                                                                     |


### <a name="app-protection-policies"></a>Beleid voor app-beveiliging

Er is een beveiligingsbeleid voor apps beschikbaar voor mobiele apps die integreren met EMS-technologieën. Dit biedt een basisbeveiliging voor uw bedrijfsgegevens wanneer die worden gedownload naar mobiele apps, inclusief de mobiele Office-apps. 

| Eigenschap    | Beschrijving                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn. |
| App-naam    | De naam van de toepassing                                                           |
| Apparaatnaam | De naam van het type apparaat.                                                       |
| Apparaattype | De naam van het type apparaat.                                                       |
| Beleid    | Het soort apparaateigendom. Dit kan **Bedrijf**, **Persoonlijk** of **Onbekend** zijn. |
| Laatste synchronisatie   | De timestamp van de laatste keer dat het apparaat is gesynchroniseerd met Intune.                   |

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
