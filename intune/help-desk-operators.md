---
title: Helpdesk voor portal voor probleemoplossing
titlesuffix: Microsoft Intune
description: Medewerkers van de helpdesk gebruiken de Portal voor problemen oplossen voor het oplossen van technische problemen van gebruikers.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7997bf0494ff52ad25b09301173b65f2478dca37
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="use-the-troubleshooting-portal-to-help-users-at-your-company"></a>De portal voor probleemoplossing gebruiken om gebruikers in uw bedrijf te helpen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

De portal voor probleemoplossing biedt helpdeskmedewerkers en Intune-beheerders toegang tot gebruikersgegevens om te reageren op hulpaanvragen van gebruikers. Organisaties met een helpdesk kunnen de **Helpdeskmedewerker** toewijzen aan een groep gebruikers. De rol helpdeskmedewerker kan gebruikmaken van de blade **Problemen oplossen**.

Op de blade **Problemen oplossen** staan ook problemen met gebruikersinschrijving vermeld. Details over het probleem en voorgestelde herstelstappen kunnen beheerders en helpdeskmedewerkers helpen problemen op te lossen. Bepaalde inschrijvingsproblemen worden niet vastgelegd en voor sommige fouten zijn er misschien geen herstelvoorstellen. 

Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Intune](/intune/role-based-access-control) voor de stappen voor het toevoegen van een rol helpdeskmedewerker

Wanneer een gebruiker contact opneemt met de ondersteuning vanwege een technisch probleem met Intune, voert de helpdeskmedewerker de naam van de gebruiker in. Intune toont nuttige gegevens waarmee veel laag-1-problemen kunnen worden opgelost, waaronder:

- Gebruikersstatus
- Toewijzingen
- Problemen met naleving
- Apparaat niet
- Ophalen van VPN- of Wi-Fi-instellingen lukt niet apparaat
- Fout tijdens installatie van app

## <a name="to-review-troubleshooting-details"></a>Details voor probleemoplossing weergeven

In de blade problemen oplossen kiest u **Gebruiker selecteren** om gebruikersgegevens weer te geven. Met gebruikersgegevens kunt u inzicht krijgen in de huidige status van gebruikers en hun apparaten.  

1. Meld u aan bij Azure-portal.
2. Kies **Meer services** > **Bewaking en beheer** > **Intune**.
3. Kies **Problemen oplossen** op de blade **Intune**.
4. Klik op **Gebruiker selecteren**.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven op de blade Problemen oplossen. In de volgende tabellen wordt de informatie uitgelegd.

> [!Note]  
> U gaat ook naar de blade **Problemen oplossen** door in uw browser naar het volgende adres te gaan: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Gebieden in het dashboard problemen oplossen

U kunt de blade **Problemen oplossen** gebruik om gebruikersgegevens weer te geven. 

![](/intune/media/troubleshooting-dash.png)

| Gebied | Naam | Beschrijving |
| ---  | ---  | ---         |
| 1.   | Accountstatus  | Geeft de status van de huidige Intune-tenant weer als **Actief** of **Inactief**.       |
| 2.   | Gebruikersselectie  | De naam van de momenteel geselecteerde gebruiker. Klik op **Gebruiker wijzigen** om een nieuwe gebruiker te kiezen.       |
| 3.   | Gebruikersstatus  | Geeft de status weer van de Intune-licentie van de gebruiker, het aantal apparaten, de nalevingsstatus van elk apparaat, het aantal apps en de nalevingsstatus van de apps.       |
| 4.   | Gebruikersgegevens  | U kunt de lijst gebruiken om de details te selecteren die u in de blade wilt weergeven. <br>U kunt de volgende selecties maken: <ul><li>Mobiele apps<li>Beleid voor app-beveiliging<li>Nalevingsbeleid<li> Configuratiebeleid<li> Registratiebeperkingen</ul>      |
| 5.   | Groepslidmaatschap  | Yadda       |

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

## <a name="next-steps"></a>Volgende stappen

Ontdek meer over op rollen gebaseerd toegangsbeheer (RBAC) voor het definiëren van rollen in uw bedrijfsapparaten, beheer van mobiele toepassingen, gegevensbeveiligingstaken. Zie [Op rollen gebaseerd toegangsbeheer (RBAC) met Intune](/intune/role-based-access-control) voor meer informatie.

Ontdek meer over bekende problemen in Microsoft Intune. Zie [Bekende problemen in Microsoft Intune](/intune/known-issues) voor meer informatie.

Informatie over het maken van een ondersteuningsticket en hulp vragen wanneer u deze nodig hebt. [Ondersteuning krijgen](/intune/get-support).