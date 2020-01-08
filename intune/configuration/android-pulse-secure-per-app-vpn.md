---
title: Aangepast VPN-profiel per app voor Android
titleSuffix: Microsoft Intune
description: Meer informatie over het maken van een VPN-profiel per app maken voor Android-apparaten die worden beheerd met Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 83b2ffc7e942492be4560a56af0f3514cb1638a4
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206853"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Een aangepast Microsoft Intune-profiel gebruiken voor het maken van een VPN-profiel per app voor Android-apparaten

U kunt een VPN-profiel per app maken voor apparaten met Android 5.0 en hoger die worden beheerd met Intune. Maak eerst een VPN-profiel met het verbindingstype Pulse Secure of Citrix. Maak vervolgens een aangepast configuratiebeleid dat het VPN-profiel aan specifieke apps koppelt.

> [!NOTE]
> Als u VPN per app wilt gebruiken op Android Enterprise-apparaten, kunt u deze stappen ook gebruiken. Het is echter raadzaam een [app-configuratiebeleid te gebruiken](../apps/app-configuration-policies-use-android.md) voor uw VPN-client-app.

Nadat u het beleid aan uw Android-apparaat of gebruikersgroepen hebt toegewezen, moeten gebruikers de Pulse Secure- of Citrix-VPN-client starten. De VPN-client staat vervolgens alleen verkeer van de opgegeven apps toe om gebruik te maken van de open VPN-verbinding.

> [!NOTE]
>
> Alleen de verbindingstypen Pulse Secure en Citrix worden ondersteund voor dit profiel.

## <a name="step-1-create-a-vpn-profile"></a>Stap 1: Een VPN-profiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Een goede profielnaam is bijvoorbeeld **Android VPN-profiel voor apps voor hele bedrijf**.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer **Android**.
    - **Profieltype**: Selecteer **VPN**.

4. Kies **Instellingen** > **Configureren**. Configureer vervolgens het VPN-profiel. Zie [VPN-instellingen configureren](vpn-settings-configure.md) en [VPN-instellingen voor Android-apparaten in Intune ](vpn-settings-android.md) voor meer informatie.

Noteer de waarde die u voor **Naam van de verbinding** opgeeft wanneer u het VPN-profiel maakt. Deze naam is nodig tijdens de volgend stap. Bijvoorbeeld **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Stap 2: Een aangepast configuratiebeleid maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het aangepaste profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Een goede profielnaam is bijvoorbeeld **Aangepast OMA-URI Android VPN-profiel voor hele bedrijf**.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Selecteer **Android**.
    - **Profieltype**: Selecteer **Aangepast**.

4. Kies **Instellingen** > **Configureren**.
5. Kies **Toevoegen** in het deelvenster **Aangepaste OMA-URI-instellingen**.
    - **Naam**: Voer een naam voor de instelling in.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **OMA-URI**: Voer `./Vendor/MSFT/VPN/Profile/*Name*/PackageList` in, waarbij *Naam* de naam is van de verbinding die u in stap 1 hebt genoteerd. In dit voorbeeld is de tekenreeks `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList`.
    - **Gegevenstype**: Voer **Tekenreeks** in.
    - **Waarde**: Voer een lijst met door puntkomma's gescheiden pakketten in om aan het profiel te koppelen. Als u bijvoorbeeld wilt dat Excel en de Google Chrome-browser de VPN-verbinding gebruiken, voert u `com.microsoft.office.excel;com.android.chrome` in.

![Voorbeeld van een aangepast VPN-beleid per app voor Android](./media/android-pulse-secure-per-app-vpn/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uw lijst met apps instellen als een blacklist of whitelist (optioneel)

Gebruik de waarde **BLACKLIST** om een lijst met apps in te voeren die de VPN-verbinding *niet* mogen gebruiken. Alle andere apps kunnen verbinding maken via de VPN. Of gebruik de waarde **WHITELIST** om een lijst met apps in te voeren die de VPN-verbinding *wel* mogen gebruiken. Apps die niet in de lijst staan, kunnen geen verbinding via de VPN maken.

1. Kies **Toevoegen** in het deelvenster **Aangepaste OMA-URI-instellingen**.
2. Geef een naam op voor de instelling.
3. Voer in **OMA-URI-** `./Vendor/MSFT/VPN/Profile/*Name*/Mode` in, waarbij *Naam* de naam is van het VPN-profiel dat u in stap 1 hebt genoteerd. In dit voorbeeld is de tekenreeks `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode`.
4. Voer in **Gegevenstype** **Tekenreeks** in.
5. Geef voor **Waarde** **BLACKLIST** of **WHITELIST** op.

## <a name="step-3-assign-both-policies"></a>Stap 3: Beide beleidsregels toewijzen

[Wijs beide apparaatprofielen toe](device-profile-assign.md) aan de vereiste gebruikers of apparaten.
