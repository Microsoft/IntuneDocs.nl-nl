---
title: Apparaten inschrijven met een apparaatinschrijvingsmanageraccount
titlesuffix: Microsoft Intune
description: Gebruik het manageraccount voor apparaatregistratie om apparaten in te registreren. "
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e0d8d6aba74a37d1c07fa8445aa98adf5943be2
ms.sourcegitcommit: 8fdddb684ecf5eabf071907168413bcd89a2f702
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/07/2018
ms.locfileid: "44141606"
---
# <a name="enroll-devices-by-using-a-device-enrollment-manager-account"></a>Apparaten inschrijven met een apparaatinschrijvingsmanageraccount

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Organisaties kunnen Intune gebruiken voor het beheren van een groot aantal mobiele apparaten met één gebruikersaccount. Het account voor de *apparaatinschrijvingsmanager* (DEM-account) is een speciaal gebruikersaccount waarmee maximaal duizend apparaten kunnen worden ingeschreven. U voegt bestaande gebruikers toe aan het DEM-account om hen speciale DEM-mogelijkheden te bieden. Voor elk geregistreerd apparaat is een licentie nodig. Gebruik apparaten die zijn geregistreerd met dit account als gedeelde apparaten in plaats van persoonlijke (BYOD)-apparaten.  

Gebruikers moeten in [Azure Portal](https://portal.azure.com) bestaan om ze te kunnen toevoegen als apparaatinschrijvingsmanagers. Voor een optimale beveiliging mag de DEM-gebruiker niet ook Intune-beheerder zijn.

>[!NOTE]
>De DEM-registratiemethode kan niet worden gebruikt met de volgende andere registratiemethoden: [Apple Configurator met Configuratieassistent](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator met directe enrollment](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) of [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Voorbeeld van een scenario voor apparaatinschrijvingsmanager

Een restaurant wil 50 verkooptablets inzetten voor zijn bedienend personeel en bestellingsmonitors voor het keukenpersoneel. De werknemers hebben geen toegang tot bedrijfsgegevens nodig of moeten zich aanmelden als gebruikers. De Intune-beheerder maakt een nieuw beheeraccount voor apparaatinschrijving voor de restaurantsupervisor.  Dit account is gescheiden van het hoofdaccount van de supervisor en wordt uitsluitend gebruikt voor het bij Intune registreren van gedeelde apparaten. De supervisor kan de 50 tablets nu inschrijven met de DEM-referenties.

Alleen gebruikers in [Azure Portal](https://portal.azure.com) kunnen apparaatinschrijvingsmanagers zijn. De gebruiker van het account voor apparaatinschrijvingsmanagers mag geen Intune-beheerder zijn.

De DEM-gebruiker kan:

-   Maximaal 1000 apparaten inschrijven bij Intune
-   Aanmelden bij de bedrijfsportal om bedrijfsapps op te halen
-   Toegang tot bedrijfsgegevens configureren door rolspecifieke apps te implementeren op de tablets

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Beperkingen van apparaten die zijn ingeschreven bij een DEM-account

Apparaten die zijn geregistreerd met een account voor apparaatinschrijvingsmanagers, hebben de volgende beperkingen:

  - Geen toegang per gebruiker. Omdat apparaten geen toegewezen gebruiker hebben, heeft het apparaat geen toegang tot e-mail of bedrijfsgegevens. VPN-configuraties kunnen echter nog wel worden gebruikt om apps op apparaten te leveren met toegang tot gegevens.
  - De DEM-gebruiker kan bij DEM ingeschreven apparaten niet via de bedrijfsportal uitschrijven op het apparaat zelf. De Intune-beheerder kan uitschrijvingen uitvoeren.
  - Alleen het lokale apparaat wordt weergegeven in de bedrijfsportal-app of op de website.
  - Gebruikers kunnen geen Apple VPP-apps (Volume Purchase Program) met gebruikerslicenties gebruiken vanwege de Apple ID-vereisten per gebruiker voor het beheer van apps.
  - (alleen iOS) Als u DEM gebruikt om iOS-apparaten in te schrijven, kunt u de Apple Configurator of het Apple Device Enrollment Program (DEP) of Apple School Manager (ASM) niet gebruiken om apparaten te registreren. Dit wil zeggen dat u een apparaat niet in supervisiemodus kunt zetten en dus geen toegang hebt tot sommige configuratie-opties.
  - (alleen Android) Er is een limiet voor het aantal apparaten met een Android-werkprofiel dat kan worden geregistreerd met één DEM-account. Per DEM-account kunt u tot tien werkprofielen voor Android-apparaten registreren. Deze beperking geldt niet voor de inschrijving van oudere Android-apparaten.
  - Apparaten kunnen VPP-apps installeren als ze over apparaatlicenties beschikken.
  - Er is geen apparaatlicentie voor Intune vereist om DEM te gebruiken. Meer informatie over [gebruikers- en apparaatlicenties](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> U kunt bedrijfs-apps implementeren op apparaten die worden beheerd door de apparaatinschrijvingsmanager. Implementeer de bedrijfsportal-app als een **vereiste installatie** in het gebruikersaccount van de apparaatinschrijvingsmanager.
> Om prestaties te verbeteren wordt bij het weergeven van de bedrijfsportal-app op een DEM-apparaat alleen het lokale apparaat weergegeven. Extern beheer van andere DEM-apparaten is alleen mogelijk via de Intune-beheerconsole.


## <a name="add-a-device-enrollment-manager"></a>Een apparaatinschrijvingsmanager toevoegen

1.  Ga naar [Intune in de Azure-portal](https://aka.ms/intuneportal) en kies **Apparaatregistratie** > **Beheerders voor apparaatregistratie**.

2.  Selecteer **Toevoegen**.

3.  Voer op de blade **Gebruiker toevoegen** een UPN-naam (User Principal Name) in voor de DEM-gebruiker en selecteer **Toevoegen**. De DEM-gebruiker wordt toegevoegd aan de lijst met DEM-gebruikers.

## <a name="permissions-for-dem"></a>Machtigingen voor DEM

De Azure AD-rollen Globale beheerder of Intune-servicebeheerder zijn vereist voor
- het uitvoeren van taken die zijn gerelateerd aan de DEM-registratie in de beheerportal;
- het weergeven van alle DEM-gebruikers, ondanks dat er RBAC-machtigingen worden vermeld en beschikbaar zijn onder de aangepaste gebruikersrol.

Een gebruiker zonder de rol van globale beheerder of Intune-servicebeheerder maar met leesmachtigingen voor de DEM-rol, kan alleen de DEM-gebruikers weergeven die door de gebruiker zijn gemaakt. RBAC-rolondersteuning voor deze functies wordt in de toekomst aangekondigd.


## <a name="remove-a-device-enrollment-manager"></a>Een apparaatinschrijvingsmanager verwijderen

Het volgende is van toepassing wanneer een apparaatinschrijvingsmanager wordt verwijderd:

-   Dit is niet van invloed op geregistreerde apparaten. Deze blijven volledig beheerd.
-   De referenties van het verwijderde DEM-account zijn nog steeds geldig.
-   De verwijderde DEM kan nog steeds geen apparaat wissen of buiten gebruik stellen.
-   De verwijderde DEM kan slechts een bepaald aantal apparaten registreren, overeenkomstig de gebruikerslimiet die door de Intune-beheerder is geconfigureerd.

**Een apparaatinschrijvingsmanager verwijderen**

1. Kies in [Intune in Azure Portal](https://aka.ms/intuneportal) de optie **Apparaatinschrijving** en kies vervolgens **Apparaatinschrijvingsmanagers**.
2. Klik op de blade **Apparaatinschrijvingsmanagers** op de DEM-gebruiker en selecteer **Verwijderen**.

