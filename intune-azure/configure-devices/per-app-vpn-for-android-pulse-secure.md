---
title: VPN per app voor Android - Pulse Secure
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u een VPN-profiel per app kunt maken voor Android-apparaten die worden beheerd door Intune.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 0cf638348df2f01d70c0765a4932abc3eb801f23
ms.lasthandoff: 02/18/2017


---

# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Een aangepast Microsoft Intune-profiel gebruiken voor het maken van een VPN-profiel per app voor Android-apparaten

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

U kunt een VPN-profiel per app maken voor apparaten met Android 5.0 en hoger die worden beheerd met Intune. Maak eerst een VPN-profiel met het verbindingstype Pulse Secure. Maak vervolgens een aangepast configuratiebeleid dat het VPN-profiel aan specifieke apps koppelt.

Nadat u het beleid op uw Android-apparaat of in uw gebruikersgroepen hebt geïmplementeerd, moeten gebruikers het PulseSecure-VPN starten. PulseSecure staat vervolgens alleen verkeer van de opgegeven apps toe om een VPN-verbinding te maken.

> [!NOTE]
>
> Alleen het verbindingstype Pulse Secure wordt ondersteund voor dit profiel.


## <a name="step-1-create-a-vpn-profile"></a>Stap 1: Een VPN-profiel maken


1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
2. Kies **Profiel maken** op de blade met de profielenlijst.
3. Voer op de blade **Profiel maken** een **naam** en desgewenst een **beschrijving** in voor het VPN-profiel.
4. Kies **Android** in de vervolgkeuzelijst **Platform**.
5. Kies **VPN** in de vervolgkeuzelijst **Profieltype**.
3. Kies **Instellingen** > **Configureren** en configureer het VPN-profiel aan de hand van de instellingen in de artikelen [How to configure VPN settings](how-to-configure-vpn-settings.md) (VPN-instellingen configureren) en [Intune VPN settings for Android devices](vpn-for-android.md) (VPN-instellingen in Intune voor Android-apparaten).

Noteer de naam van het VPN-profiel voor gebruik in de volgende stap. Bijvoorbeeld **MyAppVpnProfile**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Stap 2: Een aangepast configuratiebeleid maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Klik op **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het aangepaste profiel.
5. Kies **Android** in de vervolgkeuzelijst **Platform**.
6. Kies **Aangepast** in de vervolgkeuzelijst **Profieltype**.
7. Kies **Instellingen** > **Configureren**.
3. Kies **Toevoegen** op de blade **Aangepaste OMA-URI-instellingen**.
    - Geef een naam op voor de instelling.
    - Geef voor **Gegevenstype** de optie **Tekenreeks** op.
    - Geef voor **OMA-URI** de volgende tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Naam*/PackageList**, waarbij *Naam* de naam van het VPN-profiel is die u in stap 1 hebt genoteerd. In dit voorbeeld is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - Geef bij **Waarde** een lijst met door puntkomma’s gescheiden pakketten op die aan het profiel moeten worden gekoppeld. Als u bijvoorbeeld wilt dat Excel en de Google Chrome-browser de VPN-verbinding gebruiken, voert u **com.microsoft.office.excel;com.android.chrome** in.

![Voorbeeld van een aangepast VPN-beleid per app voor Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uw lijst met apps instellen als een blacklist of whitelist (optioneel)
  U kunt een lijst met apps opgeven die de VPN-verbinding *niet* mogen gebruiken, door de waarde **BLACKLIST** te gebruiken. Alle andere apps kunnen wel gebruikmaken van de VPN-verbinding.
U kunt ook de waarde **WHITELIST** gebruiken om een lijst met apps op te geven die de VPN-verbinding *wel* mogen gebruiken. Apps die niet op de lijst staan, kunnen in dat geval geen gebruikmaken van de VPN-verbinding.
  1.    Kies **Toevoegen** op de blade **Aangepaste OMA-URI-instellingen**.
  2.    Geef een naam op voor de instelling.
  3.    Geef voor **Gegevenstype** de optie **Tekenreeks** op.
  4.    Geef voor **OMA-URI** deze tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Naam*/Mode**, waarbij *Naam* de naam is van het VPN-profiel dat u in stap 1 hebt genoteerd. In het voorbeeld dat hier wordt gebruikt, is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
  5.    Geef bij **Waarde** **BLACKLIST** of **WHITELIST** op.



## <a name="step-3-assign-both-policies"></a>Stap 3: beide beleidsregels toewijzen

Volg de instructies in [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) om beide profielen aan de vereiste gebruikers of apparaten toe te wijzen.

