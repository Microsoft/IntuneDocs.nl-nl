---
title: Helpdesk voor portal voor probleemoplossing
titleSuffix: Microsoft Intune
description: Medewerkers van de helpdesk gebruiken de Portal voor problemen oplossen voor het oplossen van technische problemen van gebruikers.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/11/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8a4e6cbf2d9edcff83ae756c2dbcf098cae0ae54
ms.sourcegitcommit: 73fbecf7cee4fdfc37d3c30ea2007d2a9a6d2d12
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2019
ms.locfileid: "71301861"
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

1. Meld u aan bij [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Kies in het deelvenster **Intune** de optie **Problemen oplossen**.
4. Klik op **Selecteren** om een gebruiker te selecteren om problemen voor op te lossen.
5. Selecteer de gebruiker door een naam of e-mailadres te typen. Klik op **Selecteren**. De informatie voor het oplossen van problemen voor de gebruiker wordt weergegeven in het deelvenster Problemenoplossing. In de volgende tabel wordt de informatie uitgelegd.

> [!Note]  
> U kunt het deelvenster **Probleemoplossing** ook openen door in uw browser naar het volgende adres te gaan: [https://aka.ms/intunetroubleshooting](https://aka.ms/intunetroubleshooting).

## <a name="areas-of-troubleshooting-dashboard"></a>Gebieden in het dashboard problemen oplossen

U kunt het deelvenster **Probleemoplossing** gebruiken om gebruikersgegevens weer te geven.

![Dash board voor probleem oplossing, met genummerde gebieden die worden beschreven door de volgende tabel](/intune/media/troubleshooting-dash.png)

| Gebied | Naam | Beschrijving |
| ---  | ---  | ---         |
| 1.   | Accountstatus  | Geeft de status van de huidige Intune-tenant weer als **Actief** of **Inactief**.       |
| 2.   | Gebruikersselectie  | De naam van de momenteel geselecteerde gebruiker. Klik op **Gebruiker wijzigen** om een nieuwe gebruiker te kiezen.       |
| 3.   | Gebruikersstatus  | Geeft de status weer van de Intune-licentie van de gebruiker, het aantal apparaten, de nalevingsstatus van elk apparaat, het aantal apps en de nalevingsstatus van de apps.       |
| 4.   | Gebruikersgegevens  | U kunt de lijst gebruiken om de gegevens te selecteren die u in het deelvenster wilt weergeven. <br>U kunt de volgende selecties maken: <ul><li>Client-apps<li>Nalevingsbeleid<li> Configuratiebeleid<li>Beleid voor app-beveiliging <li>Registratiebeperkingen</ul>      |
| 5.   | Groepslidmaatschap  | Hiermee geeft u de groepen weer waarvan de geselecteerde gebruiker momenteel lid is.       |

<!-- this section needs to be updated

## Client apps reference

The apps that are running devices
- managed by Intune and Azure Active Directory (AD) 
- owned by users managed by Intune and Azure Active Directory (AD).

### Properties

The properties of client apps.

| Property      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Name          | The name of the application.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| OS            | The operating system installed on the device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| Type          | You can choose an assignment type for each app.  <br> **Available** - Users install the app from the Company Portal app or website.  <br> **Not Applicable** - The app is not installed or shown in the Company Portal. <br> **Uninstall** - The app is uninstalled from devices in the selected groups.  <br> **Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune. |
| Last Modified | The name of the type of device.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| App install | Denotes whether an app install failure or success has occurred on the individual device. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection status

An app protection policy is available to mobile apps that integrate with Enterprise Mobility Solution (EMS) technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## App protection policies reference

An app protection policy is available to mobile apps that integrate with EMS technologies.These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

### Properties

The table summarizes app protection policies status for devices managed by Intune.

| Property    | Description                                                                                                                                |
|-------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Name        | The name of the application.                                                                                                        |
| Deployed    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Platform    | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Enrollment  | The name of the type of device.                                                                                                     |
| Last Update | The timestamp the policy was modified.                                                                                              |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Text                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device Name        | The name of the type of device.                                                                                                     |
| Managed By         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last Check in      | The name of the type of device.                                                                                                     |

## Compliance policies reference

Makes sure that the devices used to access company apps and data, comply with certain rules like using a PIN to access the device, and encryption of data stored on the device.

### Properties

The properties of the compliance policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, and **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |

### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

## Configuration policies reference

An app configuration policy is available to mobile apps with vendor-specific configuration. 

### Properties

The properties of the configuration policies.

| Property      | Description                                                                                                                         |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Assignment    | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Name          | The name of the application.                                                                                                        |
| OS            | The operating system installed on the device.                                                                                       |
| Policy Type   | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Last Modified | The name of the type of device.                                                                                                     |

### Devices

Devices managed by Intune or by users managed by Intune or Azure AD.

| Property           | Description                                                                                                                         |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| Device name        | The name of the type of device.                                                                                                     |
| Managed by         | The timestamp the policy was modified.                                                                                              |
| Azure AD join type | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| Ownership          | The type of device ownership (**Company**, **Personal**, or **Unknown**).                                               |
| Intune compliant   | The name of the type of device.                                                                                                     |
| Azure AD compliant | The status of each of the users' app protection apps. The possible statuses for the apps are **Checked in** and **Not checked in**. |
| OS                 | The operating system installed on the device.                                                                                       |
| OS version         | The Operating System version number of the device.                                                                                  |
| Last check-in      | The name of the type of device.                                                                                                     |


### App protection policies

An app protection policy is available to mobile apps that integrate with EMS technologies. These policies give a baseline of protection for your corporate data when it is downloaded to mobile apps, including the Office mobile apps. 

| Property    | Description                                                                           |
|-------------|---------------------------------------------------------------------------------------|
| Status      | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| App name    | The name of the application                                                           |
| Device name | The name of the type of device.                                                       |
| Device type | The name of the type of device.                                                       |
| Policies    | The type of device ownership (**Company**, **Personal**, or **Unknown**). |
| Last sync   | The timestamp of the last time the device synchronized with Intune.                   |

-->

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
