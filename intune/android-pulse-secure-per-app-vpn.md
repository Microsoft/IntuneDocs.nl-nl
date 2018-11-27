---
title: Aangepast VPN-profiel per app voor Android
titlesuffix: Microsoft Intune
description: Meer informatie over het maken van een VPN-profiel per app maken voor Android-apparaten die worden beheerd met Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 48f1227da6260217105120d31301f60b6e06110c
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186015"
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Een aangepast Microsoft Intune-profiel gebruiken voor het maken van een VPN-profiel per app voor Android-apparaten

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

U kunt een VPN-profiel per app maken voor apparaten met Android 5.0 en hoger die worden beheerd met Intune. Maak eerst een VPN-profiel met het verbindingstype Pulse Secure of Citrix. Maak vervolgens een aangepast configuratiebeleid dat het VPN-profiel aan specifieke apps koppelt.

Nadat u het beleid aan uw Android-apparaat of gebruikersgroepen hebt toegewezen, moeten gebruikers de Pulse Secure- of Citrix-VPN-client starten. De VPN-client staat vervolgens alleen verkeer van de opgegeven apps toe om gebruik te maken van de open VPN-verbinding.

> [!NOTE]
>
> Alleen de verbindingstypen Pulse Secure en Citrix worden ondersteund voor dit profiel.


## <a name="step-1-create-a-vpn-profile"></a>Stap 1: Een VPN-profiel maken


1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
2. Kies **Profiel maken** in het deelvenster met de profielenlijst.
3. Voer in het deelvenster **Profiel maken** een **naam** en desgewenst een **beschrijving** in voor het VPN-profiel.
4. Kies **Android** in de vervolgkeuzelijst **Platform**.
5. Kies **VPN** in de vervolgkeuzelijst **Profieltype**.
3. Kies **Instellingen** > **Configureren** en configureer het VPN-profiel aan de hand van de instellingen in de artikelen [How to configure VPN settings](vpn-settings-configure.md) (VPN-instellingen configureren) en [Intune VPN settings for Android devices](vpn-settings-android.md) (VPN-instellingen in Intune voor Android-apparaten).

Noteer de waarde die u voor **Naam van de verbinding** opgeeft wanneer u het VPN-profiel maakt. Deze naam is nodig tijdens de volgend stap. Bijvoorbeeld **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Stap 2: Een aangepast configuratiebeleid maken

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Kies **Alle services** > **Intune**. Intune bevindt zich in de sectie **Controle en beheer**.
3. Kies in het deelvenster **Intune** de optie **Apparaatconfiguratie**.
2. Kies in het deelvenster **Apparaatconfiguratie** onder de sectie **Beheren** de optie **Profielen**.
3. Klik op **Profiel maken** in het deelvenster Profielen.
4. Voer in het deelvenster **Profiel maken** een **naam** en een **beschrijving** in voor het aangepaste profiel.
5. Kies **Android** in de vervolgkeuzelijst **Platform**.
6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Kies **Instellingen** > **Configureren**.
3. Kies **Toevoegen** in het deelvenster **Aangepaste OMA-URI-instellingen**.
    - Geef een naam op voor de instelling.
    - Geef voor **OMA-URI** de volgende tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, waarbij *Name* de naam van de verbinding is die u in stap 1 hebt genoteerd. In dit voorbeeld is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - Geef voor **Gegevenstype** de optie **Tekenreeks** op.
    - Geef bij **Waarde** een lijst met door puntkomma’s gescheiden pakketten op die aan het profiel moeten worden gekoppeld. Als u bijvoorbeeld wilt dat Excel en de Google Chrome-browser de VPN-verbinding gebruiken, voert u **com.microsoft.office.excel;com.android.chrome** in.

![Voorbeeld van een aangepast VPN-beleid per app voor Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uw lijst met apps instellen als een blacklist of whitelist (optioneel)
  U kunt een lijst met apps opgeven die de VPN-verbinding *niet* mogen gebruiken, door de waarde **BLACKLIST** te gebruiken. Alle andere apps kunnen verbinding maken via de VPN.
U kunt ook de waarde **WHITELIST** gebruiken om een lijst met apps op te geven die de VPN-verbinding *wel* mogen gebruiken. Apps die niet op de lijst staan, kunnen geen verbinding via de VPN maken.
  1.    Kies **Toevoegen** in het deelvenster **Aangepaste OMA-URI-instellingen**.
  2.    Geef een naam op voor de instelling.
  3.    Geef voor **OMA-URI** de volgende tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, waarbij *Name* de naam is van het VPN-profiel die u in stap 1 hebt genoteerd. In het voorbeeld dat hier wordt gebruikt, is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
  4.    Geef voor **Gegevenstype** de optie **Tekenreeks** op.
  5.    Geef bij **Waarde** **BLACKLIST** of **WHITELIST** op.



## <a name="step-3-assign-both-policies"></a>Stap 3: beide beleidsregels toewijzen

Volg de instructies in [How to assign device profiles](device-profile-assign.md) (Apparaatprofielen toewijzen) om beide profielen aan de vereiste gebruikers of apparaten toe te wijzen.
