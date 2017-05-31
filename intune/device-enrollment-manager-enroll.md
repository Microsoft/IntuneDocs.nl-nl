---
title: Apparaten inschrijven - apparaatinschrijvingsmanager
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: u kunt de apparaatinschrijvingsmanager gebruiken om apparaten in Intune in te schrijven. '
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: aded0826c2628e4dc72859387fbe4a76d683db9e
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017

---

# <a name="enroll-devices-using-device-enrollment-manager"></a>Apparaten inschrijven met de apparaatinschrijvingsmanager

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Organisaties kunnen Intune gebruiken voor het beheren van een groot aantal mobiele apparaten met één gebruikersaccount. Het account voor de *apparaatinschrijvingsmanager* (DEM-account) is een speciaal gebruikersaccount waarmee maximaal duizend apparaten kunnen worden ingeschreven. U voegt bestaande gebruikers toe aan het DEM-account om ze speciale DEM-mogelijkheden te bieden. Voor elk geregistreerd apparaat is een licentie nodig. Gebruik apparaten die zijn geregistreerd met dit account als gedeelde apparaten in plaats van persoonlijke (BYOD)-apparaten.  

Gebruikers moeten in Azure Portal bestaan om ze te kunnen toevoegen aan apparaatinschrijvingsmanagers. Voor een optimale beveiliging mag de DEM-gebruiker géén Intune-beheerder zijn.

>[!NOTE]
>De DEM-inschrijvingsmethode kan niet worden gebruikt met de volgende andere inschrijvingsmethoden: [Apple Configurator met Configuratieassistent](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator met directe inschrijving](apple-configurator-direct-enroll-ios.md) of [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md). 

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Voorbeeld van een scenario voor apparaatinschrijvingsmanager

Een restaurant wil 50 verkooptablets inzetten voor zijn bedienend personeel en bestellingsmonitors voor het keukenpersoneel. De werknemers hebben geen toegang tot bedrijfsgegevens nodig of moeten zich aanmelden als gebruikers. De Intune-beheerder maakt een apparaatinschrijvingsmanageraccount en voegt een restaurantsupervisor toe aan het DEM-account. Daarmee krijgt die supervisor DEM-mogelijkheden. De supervisor kan de 50 tablets nu inschrijven met de DEM-referenties.

Alleen gebruikers in de Intune-console kunnen apparaatinschrijvingsbeheerders zijn. De gebruiker van het account voor apparaatinschrijvingsmanagers mag geen Intune-beheerder zijn.

De DEM-gebruiker kan:

-   Maximaal 1000 apparaten inschrijven in Intune.
-   Aanmelden bij de bedrijfsportal om bedrijfsapps op te halen.
-   Toegang tot bedrijfsgegevens configureren door rolspecifieke apps te implementeren op de tablets.

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Beperkingen van apparaten die zijn ingeschreven bij een DEM-account

Apparaten die zijn geregistreerd met een account voor apparaatinschrijvingsmanagers, hebben de volgende beperkingen:

  - Er is geen specifieke 'gebruiker' van een apparaat. Er is daarom geen e-mailadres of toegang tot bedrijfsgegevens. VPN kan echter nog wel worden gebruikt om apps op apparaten leveren met toegang tot gegevens.

  - Er is geen voorwaardelijke toegang mogelijk omdat dit per gebruiker moet worden opgegeven.

  - De DEM-gebruiker kan bij DEM ingeschreven apparaten niet via de bedrijfsportal uitschrijven op het apparaat zelf. De Intune-beheerder heeft deze mogelijkheid, maar de DEM-gebruiker niet.

  - Alleen het lokale apparaat wordt weergegeven in de bedrijfsportal-app of op de website.
 
  - Gebruikers kunnen geen Apple VPP-apps (Volume Purchase Program) gebruiken vanwege de Apple ID-vereisten per gebruiker voor het beheer van apps.
 
  - (alleen iOS) Als u DEM gebruikt om iOS-apparaten in te schrijven, kunt u de Apple Configurator of het Apple Device Enrollment Program (DEP) niet gebruiken om apparaten in te schrijven.


> [!NOTE]
> Om bedrijfsapps te implementeren op apparaten die worden beheerd met de apparaatinschrijvingsmanager, moet u de bedrijfsportal-app als een **Vereiste installatie** implementeren naar het gebruikersaccount voor de apparaatinschrijvingsmanager.
> Om prestaties te verbeteren wordt bij het weergeven van de bedrijfsportal-app op een DEM-apparaat alleen het lokale apparaat weergegeven. Extern beheer van andere DEM-apparaten is alleen mogelijk via de Intune-beheerconsole.


## <a name="add-a-device-enrollment-manager"></a>Een apparaatinschrijvingsmanager toevoegen

1.  Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2.  Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apparaatinschrijvingsmanagers**.

3.  Selecteer **Toevoegen**.

4.  Voer op de blade **Gebruiker toevoegen** een UPN-naam (User Principal Name) in voor de DEM-gebruiker en selecteer **Toevoegen**. De DEM-gebruiker wordt toegevoegd aan de lijst met DEM-gebruikers.

## <a name="remove-a-device-enrollment-manager"></a>Een apparaatinschrijvingsmanager verwijderen

Het verwijderen van een apparaatinschrijvingsmanager is niet van invloed op ingeschreven apparaten. Het volgende is van toepassing wanneer een apparaatinschrijvingsmanager wordt verwijderd:

-   Het verwijderen van een gebruiker uit de lijst met DEM-gebruikers is niet van invloed op de ingeschreven apparaten en de ingeschreven apparaten blijven volledig beheerd.

-   De accountreferenties van de verwijderde apparaatinschrijvingsmanager blijven geldig.

-   Apparaten kunnen nog steeds niet worden gewist of buiten gebruik worden gesteld met de verwijderde apparaatinschrijvingsmanager.

-   Er kunnen geen extra apparaten met de apparaatinschrijvingsmanager worden ingeschreven, tenzij de limiet per apparaat (geconfigureerd door de Intune-beheerder) nog niet is bereikt.

**Een apparaatinschrijvingsmanager verwijderen**

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apparaatinschrijvingsmanagers**.

3. Klik op de blade **Apparaatinschrijvingsmanagers** met de rechtermuisknop op de DEM-gebruiker en selecteer **Verwijderen**.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>De eigenschappen van een apparaatinschrijvingsmanager weergeven

1. Kies in Azure Portal **Meer services** > **Bewaking en beheer** > **Intune**.

2. Kies **Apparaten inschrijven** op de blade Intune en kies vervolgens **Apparaatinschrijvingsmanagers**.

3. Klik op de blade **Apparaatinschrijvingsmanagers** met de rechtermuisknop op de DEM-gebruiker en selecteer **Eigenschappen**.

