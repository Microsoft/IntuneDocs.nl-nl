---
title: VPN-instellingen toevoegen aan apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Gebruik voor Android-, Android Enterprise-, iOS-, macOS- en Windows-apparaten ingebouwde instellingen voor het maken van VPN-verbindingen (virtueel particulier netwerk) in Microsoft Intune.
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
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9fab50e0aefd926b4dc7a2b3559576642d5d6b79
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059313"
---
# <a name="create-vpn-profiles-to-connect-to-vpn-servers-in-intune"></a>VPN-profielen maken om verbinding te maken met VPN-servers in Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Met virtuele particuliere netwerken (VPN's) geeft u uw gebruikers veilige externe toegang tot het netwerk van uw organisatie. Apparaten gebruiken een VPN-verbindingsprofiel om een verbinding met de VPN-server op te zetten. Met **VPN-profielen** in Microsoft Intune worden VPN-instellingen toegewezen aan gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk van uw organisatie kunnen maken.

U wilt bijvoorbeeld alle iOS-apparaten configureren met de instellingen die vereist zijn om verbinding te maken met een bestandsshare in het netwerk van de organisatie. U maakt een VPN-profiel dat deze instellingen bevat. U wijst dit profiel vervolgens toe aan alle gebruikers die over iOS-apparaten beschikken. De gebruikers zien de VPN-verbinding in de lijst met beschikbare netwerken en kunnen moeiteloos verbinding maken.

> [!NOTE]
> U kunt [aangepast Intune-configuratiebeleid](custom-settings-configure.md) gebruiken om VPN-profielen te maken voor de volgende platformen:
>
> * Android 4 en hoger
> * Geregistreerde apparaten met Windows 8.1 en hoger
> * Windows Phone 8.1 en hoger
> * Geregistreerde apparaten met Windows 10 Desktop
> * Windows 10 Mobile
> * Windows Holographic for Business

## <a name="vpn-connection-types"></a>VPN-verbindingstypen

U kunt VPN-profielen met de volgende verbindingstypen maken:

|Type verbinding|Platform|
|-|-|
|Automatisch|Windows 10|
|Check Point Capsule VPN|- Android<br/>- Android Enterprise-werkprofielen<br/>- iOS<br/>- macOS<br/>- Windows 10<br/>- Windows 8.1<br/>- Windows Phone 8.1|
|Cisco AnyConnect|- Android<br/>- Android Enterprise-werkprofielen<br/>- Android Enterprise-apparaateigenaar (volledig beheerd)<br/>- iOS<br/>- macOS|
|Cisco (IPsec)|iOS|
|Citrix SSO|- Android<br/>- Android Enterprise-werkprofielen: [App-configuratiebeleid](../apps/app-configuration-policies-use-android.md) gebruiken<br/>- Android Enterprise-apparaateigenaar (volledig beheerd): [App-configuratiebeleid](../apps/app-configuration-policies-use-android.md) gebruiken<br/>- iOS<br/>- Windows 10|
|Aangepaste VPN|- iOS<br/>- macOS|
|F5-toegang|- Android<br/>- Android Enterprise-werkprofielen<br/>- Android Enterprise-apparaateigenaar (volledig beheerd)<br/>- iOS<br/>- macOS<br/>- Windows 10<br/>- Windows 8.1<br/>- Windows Phone 8.1|
|IKEv2| - iOS<br/>- Windows 10|
|L2TP|Windows 10|
|Palo Alto Networks GlobalProtect|- Android Enterprise-werkprofielen: [App-configuratiebeleid](../apps/app-configuration-policies-use-android.md) gebruiken<br/>- iOS<br/>- Windows 10|
|PPTP|Windows 10|
|Pulse Secure|- Android<br/>- Android Enterprise-werkprofielen<br/>- Android Enterprise-apparaateigenaar (volledig beheerd)<br/>- iOS<br/>- macOS<br/>- Windows 10<br/>- Windows 8.1<br/>- Windows Phone 8.1|
|SonicWall Mobile Connect|- Android<br/>- Android Enterprise-werkprofielen<br/>- iOS<br/>- macOS<br/>- Windows 10<br/>- Windows 8.1<br/>- Windows Phone 8.1|
|Zscaler|- Android Enterprise-werkprofielen: [App-configuratiebeleid](../apps/app-configuration-policies-use-android.md) gebruiken<br/>- iOS|

> [!IMPORTANT]
> U kunt VPN-profielen die zijn toegewezen aan een apparaat pas gebruiken nadat de betreffende VPN-app voor het profiel is geïnstalleerd. U kunt de informatie in het artikel [Wat is Microsoft Intune-appbeheer?](../apps/app-management.md) gebruiken bij het toewijzen van de app met behulp van Intune.  

Zie [Profielen met aangepaste instellingen maken](custom-settings-configure.md) voor meer informatie over het maken van aangepaste VPN-profielen met URI-instellingen.

## <a name="create-a-device-profile"></a>Een apparaatprofiel maken

1. Meld u aan bij het [Microsoft Endpoint Manager-beheercentrum](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecteer **Apparaten** > **Configuratieprofielen** > **Profiel maken**.
3. Voer de volgende eigenschappen in:

    - **Naam**: Voer een beschrijvende naam in voor het profiel. Geef uw profielen een naam zodat u ze later eenvoudig kunt identificeren. Een goede profielnaam is bijvoorbeeld **VPN-profiel voor hele bedrijf**.
    - **Beschrijving**: Voer een beschrijving in voor het profiel. Deze instelling is optioneel, maar wordt aanbevolen.
    - **Platform**: Kies het platform van uw apparaten. Uw opties zijn:

      - **Android**
      - **Alleen Android Enterprise** >  **-apparaateigenaar**
      - **Alleen Android Enterprise** >  **-werkprofiel**
      - **iOS/iPadOS**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 en hoger**
      - **Windows 10 en hoger**

    - **Profieltype**: Selecteer **VPN**.

4. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg de volgende artikelen voor gedetailleerde instellingen voor elk platform:

    - [Android-instellingen](vpn-settings-android.md)
    - [Instellingen voor Android Enterprise](vpn-settings-android-enterprise.md)
    - [Instellingen voor iOS/iPadOS](vpn-settings-ios.md)
    - [macOS-instellingen](vpn-settings-macos.md)
    - [Windows Phone 8.1-instellingen](vpn-settings-windows-phone-8-1.md)
    - [Windows 8.1-instellingen](vpn-settings-windows-8-1.md)
    - [Instellingen voor Windows 10](vpn-settings-windows-10.md) (inclusief Windows Holographic for Business)

5. Wanneer u klaar bent, selecteert u **OK** > **Maken** om uw wijzigingen op te slaan.

Het profiel wordt gemaakt en wordt weergegeven in de profielenlijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om dit profiel toe te wijzen aan groepen.

## <a name="secure-your-vpn-profiles"></a>Uw VPN-profielen beveiligen

Voor VPN-profielen kan een aantal verschillende verbindingstypen en -protocollen van verschillende fabrikanten worden gebruikt. Deze verbindingen zijn doorgaans beveiligd met een of meer van de volgende methoden.

### <a name="certificates"></a>Certificaten

Wanneer u het VPN-profiel maakt, kiest u een SCEP- of PFX-certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit profiel wordt het identiteitscertificaat genoemd. Dit wordt gebruikt voor verificatie aan de hand van een vertrouwd-certificaatprofiel (of *basiscertificaat*) dat u hebt gemaakt om het apparaat van de gebruiker verbinding te laten maken. Het vertrouwde certificaat wordt toegewezen aan de computer die de VPN-verbinding verifieert. Dit is meestal de VPN-server.

Zie [How to configure certificates with Microsoft Intune](../protect/certificates-configure.md) (Certificaten configureren met Microsoft Intune) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.

### <a name="user-name-and-password"></a>Gebruikersnaam en wachtwoord

De gebruiker wordt geverifieerd op de VPN-server door een gebruikersnaam en wachtwoord op te geven.

## <a name="next-steps"></a>Volgende stappen

Als het profiel is gemaakt, doet het nog niets. [Wijs het profiel vervolgens toe](device-profile-assign.md) aan enkele apparaten.

U kunt ook VPN's per app maken en gebruiken op [Android](android-pulse-secure-per-app-vpn.md)- en [iOS](vpn-setting-configure-per-app.md)-apparaten.
