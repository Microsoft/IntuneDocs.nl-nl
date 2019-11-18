---
title: Aangepast VPN-profiel per app voor Android
titleSuffix: Microsoft Intune
description: Meer informatie over het maken van een VPN-profiel per app maken voor Android-apparaten die worden beheerd met Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f044d42a36717e970abba37009df2e3d0516a046
ms.sourcegitcommit: 1a7f04c80548e035be82308d2618492f6542d3c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2019
ms.locfileid: "73756749"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Een aangepast Microsoft Intune-profiel gebruiken voor het maken van een VPN-profiel per app voor Android-apparaten

[!INCLUDE[azure_portal](../includes/azure_portal.md)]

U kunt een VPN-profiel per app maken voor apparaten met Android 5.0 en hoger die worden beheerd met Intune. Maak eerst een VPN-profiel met het verbindingstype Pulse Secure of Citrix. Maak vervolgens een aangepast configuratiebeleid dat het VPN-profiel aan specifieke apps koppelt.

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

4. Kies **Instellingen** > **Configureren** en configureer het VPN-profiel aan de hand van de instellingen in de artikelen [How to configure VPN settings](vpn-settings-configure.md) (VPN-instellingen configureren) en [Intune VPN settings for Android devices](vpn-settings-android.md) (VPN-instellingen in Intune voor Android-apparaten).

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

U kunt een lijst met apps invoeren die de VPN-verbinding *niet* mogen gebruiken, door de waarde **BLACKLIST** te gebruiken. Alle andere apps kunnen verbinding maken via de VPN. U kunt ook de waarde **WHITELIST** gebruiken om een lijst met apps in te voeren die de VPN-verbinding *wel* mogen gebruiken. Apps die niet in de lijst staan, kunnen geen verbinding via de VPN maken.

1. Kies **Toevoegen** in het deelvenster **Aangepaste OMA-URI-instellingen**.
2. Geef een naam op voor de instelling.
3. Voer in **OMA-URI-** `./Vendor/MSFT/VPN/Profile/*Name*/Mode` in, waarbij *Naam* de naam is van het VPN-profiel dat u in stap 1 hebt genoteerd. In dit voorbeeld is de tekenreeks `./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode`.
4. Voer in **Gegevenstype** **Tekenreeks** in.
5. Geef voor **Waarde** **BLACKLIST** of **WHITELIST** op.

## <a name="step-3-assign-both-policies"></a>Stap 3: Beide beleidsregels toewijzen

[Wijs beide apparaatprofielen toe](device-profile-assign.md) aan de vereiste gebruikers of apparaten.
