---
title: Apparaten inschrijven met de apparaatinschrijvingsmanager
description: De apparaatinschrijvingsmanager (DEM) kan een groot aantal mobiele apparaten in bedrijfseigendom beheren via één gebruikersaccount.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4973e896109589a91891545bbf6db6ca6df45aad
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune"></a>Apparaten in bedrijfseigendom inschrijven met de apparaatinschrijvingsmanager in Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Organisaties kunnen Intune gebruiken voor het beheren van een groot aantal mobiele apparaten met één gebruikersaccount. Het account voor de *apparaatinschrijvingsmanager* (DEM-account) is een speciaal gebruikersaccount waarmee maximaal duizend apparaten kunnen worden ingeschreven. U voegt bestaande gebruikers toe aan het DEM-account om ze speciale DEM-mogelijkheden te bieden. Voor elk geregistreerd apparaat is een licentie nodig. Gebruik apparaten die zijn geregistreerd met dit account als gedeelde apparaten (dat wil zeggen, apparaten zonder gebruikersaffiniteit) in plaats van persoonlijke (BYOD)-apparaten.  

Gebruikers moeten in Azure Portal bestaan om ze te kunnen toevoegen aan apparaatinschrijvingsmanagers. Voor een optimale beveiliging mag de DEM-gebruiker géén Intune-beheerder zijn.

>[!NOTE]
>De DEM-inschrijvingsmethode kan niet worden gebruikt in combinatie met de [Apple Configurator Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md), de methode voor [directe inschrijving](ios-direct-enrollment-in-microsoft-intune.md), inschrijving voor macOS en de [DEP-inschrijvingsmethode](ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Voorbeeld van een scenario voor apparaatinschrijvingsmanager

Een restaurant wil 50 verkooptablets inzetten voor zijn bedienend personeel en bestellingsmonitors voor het keukenpersoneel. De werknemers hebben geen toegang tot bedrijfsgegevens nodig of moeten zich aanmelden als gebruikers. De Intune-beheerder maakt een apparaatinschrijvingsmanageraccount en voegt een restaurantsupervisor toe aan het DEM-account. Daarmee krijgt die supervisor DEM-mogelijkheden. De supervisor kan de 50 tablets nu inschrijven met de DEM-referenties.

Alleen gebruikers in de Intune-console kunnen apparaatinschrijvingsbeheerders zijn. De gebruiker van het account voor apparaatinschrijvingsmanagers mag geen Intune-beheerder zijn.

De DEM-gebruiker kan:

-   Maximaal 1000 apparaten inschrijven bij Intune
-   De bedrijfsportal gebruiken om bedrijfsapps te downloaden
-   Toegang tot bedrijfsgegevens configureren door rolspecifieke apps te implementeren op de tablets

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

1. Zorg ervoor dat de gebruiker die u wilt toevoegen aan het DEM-account al bestaat. Als u de gebruiker wilt toevoegen, meldt u zich aan bij de [Office 365-portal](https://go.microsoft.com/fwlink/p/?LinkId=698854) en volgt u de stappen in [Gebruikers afzonderlijk of bulksgewijs toevoegen aan de Office 365-portal](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

2. Meld u aan bij de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) met uw beheerdersreferenties.

3. Kies in het navigatievenster **Beheer**, ga naar **Beheerdersbeheer** en selecteer **Apparaatinschrijvingsmanager**. De pagina **Apparaatinschrijvingsmanagers** wordt geopend.

4. Kies **Toevoegen**. Het dialoogvenster **Apparaatinschrijvingsbeheerder toevoegen** wordt geopend.

5. Voer de **gebruikers-id** van het Intune-account in en kies **OK**.

   De DEM-gebruiker kan nu mobiele apparaten inschrijven met behulp van dezelfde procedure die een eindgebruiker gebruikt voor een BYOD-scenario in de bedrijfsportal. De eindgebruiker van het manageraccount kan de bedrijfsportal-app installeren en het apparaat inschrijven met zijn of haar DEM-referenties, op maximaal 1000 apparaten. Zie de volgende onderwerpen voor de stappen die voor elk platform gelden voor inschrijving door eindgebruikers:

   - [Uw iOS-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
   - [Uw Mac OS-apparaat registreren bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
   - [Uw Android-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
   - [Uw Windows-apparaat inschrijven bij Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <a name="delete-a-device-enrollment-manager-from-intune"></a>Een apparaatinschrijvingsbeheerder uit Intune verwijderen

1.  Meld u aan bij de [Microsoft Intune-accountportal](https://manage.microsoft.com) met uw beheerdersreferenties.

2.  Kies in het navigatievenster **Beheer**, ga naar **Beheerdersbeheer** en selecteer **Apparaatinschrijvingsmanager**. De pagina **Apparaatinschrijvingsmanagers** wordt geopend.

3.  Selecteer de apparaatregistratiemanager **Gebruiker** die u wilt verwijderen, en kies vervolgens **Verwijderen**. Deze gebruiker wordt niet uit Intune verwijderd en de apparaten die deze gebruiker beheert, blijven ingeschreven in Intune. Het verwijderen van een apparaatinschrijvingsbeheerder verhindert dat de betreffende gebruiker meer apparaten in Intune inschrijft.

4.  Kies **Ja** om te bevestigen dat u de apparaatinschrijvingsmanager wilt verwijderen.

Het verwijderen van een apparaatinschrijvingsbeheerder heeft geen invloed op ingeschreven apparaten. Wanneer een apparaatinschrijvingsbeheerder wordt verwijderd:

-   Heeft dat geen invloed op ingeschreven apparaten.

-   Blijven ingeschreven apparaten volledig beheerd.

-   Blijven de accountreferenties van de verwijderde apparaatinschrijvingsmanager geldig voor aanmelding bij de bedrijfsportal om toegang tot apps te krijgen.

-   Kunnen apparaten nog steeds niet worden gewist of buiten gebruik worden gesteld met de accountreferenties van de verwijderde apparaatinschrijvingsmanager.

-   Blijft het account van de verwijderde apparaatinschrijvingsmanager gerelateerd aan ingeschreven apparaten, maar kunnen er geen extra apparaten worden ingeschreven.
