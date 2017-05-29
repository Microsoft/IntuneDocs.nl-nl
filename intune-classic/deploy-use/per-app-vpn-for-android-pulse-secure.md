---
title: VPN per app voor Android met behulp van Pulse Secure | Microsoft Docs
description: U kunt een VPN-profiel per app maken voor Android-apparaten die worden beheerd door Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 6786ac87c34e913ba71cd203f431f746df816459
ms.contentlocale: nl-nl
ms.lasthandoff: 05/23/2017


---

# <a name="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices"></a>Een aangepast beleid gebruiken voor een VPN-profiel per app voor Android-apparaten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

U kunt een VPN-profiel per app maken voor apparaten met Android 5.0 en hoger die worden beheerd met Intune. Maak eerst een VPN-profiel met het verbindingstype Pulse Secure of Citrix. Maak vervolgens een aangepast configuratiebeleid dat het VPN-profiel aan specifieke apps koppelt. 

Nadat u het beleid op uw Android-apparaat of in uw gebruikersgroepen hebt geïmplementeerd, moeten gebruikers het PulseSecure- of Citrix-VPN starten. De verbinding staat vervolgens alleen verkeer van de opgegeven apps toe om een open VPN-verbinding te gebruiken.

> [!NOTE]
>
> Alleen de verbindingstypen Pulse Secure en Citrix worden ondersteund voor dit profiel.


### <a name="step-1-create-a-vpn-profile"></a>Stap 1: Een VPN-profiel maken

1. Ga naar de [Microsoft Intune-beheerconsole](https://manage.microsoft.com) en kies **Beleid** > **Beleid toevoegen**.
2. Als u een sjabloon wilt selecteren voor het nieuwe beleid, vouwt u **Android** uit en kiest u vervolgens **VPN-profiel (Android 4 en hoger)**.
3. In de sjabloon kiest u voor **Verbindingstype** de optie **Pulse Secure** of **Citrix**.
4. Voltooi het VPN-profiel en sla het op. Zie [VPN-verbindingen](../deploy-use/vpn-connections-in-microsoft-intune.md) voor meer informatie over VPN-profielen.

> [!NOTE]
>
> Noteer de naam van het VPN-profiel voor gebruik in de volgende stap. Bijvoorbeeld MyAppVpnProfile.

### <a name="step-2-create-a-custom-configuration-policy"></a>Stap 2: Een aangepast configuratiebeleid maken

   1. Kies in de Intune-beheerconsole achtereenvolgens **Beleid** > **Beleid toevoegen** > **Android** > **Aangepaste configuratie** > **Beleid maken**.
   2. Geef een naam op voor het beleid.
   3. Kies onder **OMA-URI-instellingen** de optie **Toevoegen**.
   4. Geef een naam op voor de instelling.
   5. Geef voor **Gegevenstype** de optie **Tekenreeks** op.
   6. Geef voor **OMA-URI** de volgende tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Naam*/PackageList**, waarbij *Naam* de naam van het VPN-profiel is die u in stap 1 hebt genoteerd. In het voorbeeld dat hier wordt gebruikt, is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
   7.    Geef bij **Waarde** een lijst met door puntkomma’s gescheiden pakketten op die aan het profiel moeten worden gekoppeld. Als u bijvoorbeeld wilt dat Excel en de Google Chrome-browser de VPN-verbinding gebruiken, voert u **com.microsoft.office.excel;com.android.chrome** in.

![Voorbeeld van een aangepast VPN-beleid per app voor Android](./media/android_per_app_vpn_oma_uri.png)

#### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Uw lijst met apps instellen als een blacklist of whitelist (optioneel)
  U kunt een lijst met apps opgeven die de VPN-verbinding *niet* mogen gebruiken, door de waarde **BLACKLIST** te gebruiken. Alle andere apps kunnen wel gebruikmaken van de VPN-verbinding.
U kunt ook de waarde **WHITELIST** gebruiken om een lijst met apps op te geven die de VPN-verbinding *wel* mogen gebruiken. Apps die niet op de lijst staan, kunnen in dat geval geen gebruikmaken van de VPN-verbinding.
  1.    Kies onder **OMA-URI-instellingen** de optie **Toevoegen**.
  2.    Geef een naam op voor de instelling.
  3.    Geef voor **Gegevenstype** de optie **Tekenreeks** op.
  4.    Geef voor **OMA-URI** de volgende tekenreeks op: **./Vendor/MSFT/VPN/Profile/*Naam*/Mode**, waarbij *Naam* de naam is van het VPN-profiel dat u in stap 1 hebt genoteerd. In het voorbeeld dat hier wordt gebruikt, is de tekenreeks **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.
  5.    Geef bij **Waarde** **BLACKLIST** of **WHITELIST** op.



### <a name="step-3-deploy-both-policies"></a>Stap 3: Beide beleidsregels implementeren

U moet *beide* beleidsregels naar *dezelfde* Intune-groepen implementeren.

1.  Selecteer in de werkruimte **Beleid** het beleid dat u wilt implementeren en kies vervolgens **Implementatie beheren**.
2.  In het dialoogvenster **Implementatie beheren** :
    -   **Als u het beleid wilt implementeren**, selecteert u een of meer groepen waarvoor u het beleid wilt implementeren en klikt u vervolgens op **Toevoegen**  >  **OK**.
    -   **Als u het dialoogvenster wilt sluiten zonder het beleid te implementeren**, kiest u **Annuleren**.

Een statusoverzicht en waarschuwingen op de pagina **Overzicht** van de werkruimte **Beleid** identificeren beleidsproblemen die uw aandacht nodig hebben. Er wordt ook een statusoverzicht weergegeven in de werkruimte **Dashboard**.

