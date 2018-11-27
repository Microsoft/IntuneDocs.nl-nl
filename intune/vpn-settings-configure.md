---
title: VPN-apparaatprofielen maken in Microsoft Intune - Azure | Microsoft Docs
description: Voor iOS-apparaten kunt u de VPN-verbindingstypen (virtuele privénetwerken) bekijken, een VPN-apparaatprofiel maken in Azure Portal en uw opties bekijken voor het beveiligen van het VPN-profiel met certificaten, of een gebruikersnaam met wachtwoord in Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cd605542a0711e27f87d68af51662fd318f3250e
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184876"
---
# <a name="create-vpn-profiles-in-intune"></a>VPN-profielen maken in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Met virtuele particuliere netwerken (VPN's) geeft u uw gebruikers veilige externe toegang tot uw bedrijfsnetwerk. Apparaten gebruiken een VPN-verbindingsprofiel om een verbinding met de VPN-server op te zetten. Gebruik **VPN-profielen** in Microsoft Intune om VPN-instellingen toe te wijzen aan gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk kunnen maken.

U wilt bijvoorbeeld alle iOS-apparaten voorzien van de instellingen die vereist zijn om verbinding te maken met een bestandsshare op het bedrijfsnetwerk. U maakt een VPN-profiel dat de instellingen bevat om verbinding te maken met het bedrijfsnetwerk. U kunt dit profiel vervolgens toewijzen aan alle gebruikers die over iOS-apparaten beschikken. De gebruikers zien de VPN-verbinding in de lijst met beschikbare netwerken en kunnen moeiteloos verbinding maken.

U kunt aangepast Intune-configuratiebeleid gebruiken om VPN-profielen te maken voor de volgende platformen:

* Android 4 en hoger
* Geregistreerde apparaten met Windows 8.1 en hoger
* Windows Phone 8.1 en hoger
* Geregistreerde apparaten met Windows 10 Desktop
* Windows 10 Mobile
* Windows Holographic for Business

## <a name="vpn-connection-types"></a>VPN-verbindingstypen

U kunt VPN-profielen met de volgende verbindingstypen maken:

|Type verbinding|Android<br>Android-werkprofielen|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Automatisch|Nee|Nee|Nee|Nee|Nee|Ja|
|Check Point Capsule VPN|Ja|Ja|Ja|Ja|Ja|Ja|
|Cisco AnyConnect|Ja|Ja|Ja|Nee|Nee|Nee|
|SonicWall Mobile Connect|Ja|Ja|Ja|Ja|Ja|Ja|
|F5 Edge Client|Ja|Ja|Ja|Ja|Ja|Ja|
|Palo Alto Networks GlobalProtect|Nee|Ja|Nee|Nee|Nee|Ja|
|Pulse Secure|Ja|Ja|Ja|Ja|Ja|Ja|
|Cisco (IPsec)|Nee|Ja|Nee|Nee|Nee|Nee|
|Citrix|Ja (alleen Android)|Ja|Nee|Nee|Nee|Ja|
|IKEv2|Nee|Nee|Nee|Nee|Nee|Ja|
|L2TP|Nee|Nee|Nee|Nee|Nee|Ja|
|PPTP|Nee|Nee|Nee|Nee|Nee|Ja|
|Zscaler|Nee|Ja|Nee|Nee|Nee|Nee|
|Aangepaste VPN|Nee|Ja|Ja|Nee|Nee|Nee|

> [!IMPORTANT]
> U kunt VPN-profielen die zijn toegewezen aan een apparaat pas gebruiken nadat de betreffende VPN-app voor het profiel is geïnstalleerd. U kunt de informatie in het artikel [Wat is Microsoft Intune-appbeheer?](app-management.md) gebruiken bij het toewijzen van de app met behulp van Intune.  

Zie [Profielen met aangepaste instellingen maken](custom-settings-configure.md) voor meer informatie over het maken van aangepaste VPN-profielen met URI-instellingen.

## <a name="create-a-device-profile-containing-vpn-settings"></a>Een apparaatprofiel met VPN-instellingen maken

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Selecteer **Apparaatconfiguratie** > **Profielen** > **Profiel maken**.
4. Voer een **naam** en **beschrijving** in voor het VPN-profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de VPN-instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor VPN-apparaatinstellingen:
   - **Android**
   - **Android Enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 en hoger**
   - **Windows 10 en hoger**
6. Kies **VPN** in de vervolgkeuzelijst **Profieltype**.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
   - [Android en Android-werkprofielinstellingen](vpn-settings-android.md)
   - [iOS-instellingen](vpn-settings-ios.md)
   - [macOS-instellingen](vpn-settings-macos.md)
   - [Windows Phone 8.1-instellingen](vpn-settings-windows-phone-8-1.md)
   - [Windows 8.1-instellingen](vpn-settings-windows-8-1.md)
   - [Instellingen voor Windows 10](vpn-settings-windows-10.md) (inclusief Windows Holographic for Business)
8. Wanneer u bent klaar, **maakt** u uw profiel

Het profiel wordt gemaakt en wordt weergegeven in de profielenlijst. Zie [Apparaatprofielen toewijzen](device-profile-assign.md) om dit profiel toe te wijzen aan groepen.

## <a name="methods-of-securing-vpn-profiles"></a>Methoden voor het beveiligen van VPN-profielen

Voor VPN-profielen kan een aantal verschillende verbindingstypen en -protocollen van verschillende fabrikanten worden gebruikt. Deze verbindingen zijn doorgaans beveiligd met een van de volgende twee methoden.

### <a name="certificates"></a>Certificaten

Wanneer u het VPN-profiel maakt, kiest u een SCEP- of PFX-certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit profiel wordt het identiteitscertificaat genoemd. Dit wordt gebruikt voor verificatie aan de hand van een vertrouwd-certificaatprofiel (of *basiscertificaat*) dat u hebt gemaakt om het apparaat van de gebruiker verbinding te laten maken. Het vertrouwde certificaat wordt toegewezen aan de computer die de VPN-verbinding verifieert. Dit is meestal de VPN-server.

Zie [How to configure certificates with Microsoft Intune](certificates-configure.md) (Certificaten configureren met Microsoft Intune) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.

### <a name="user-name-and-password"></a>Gebruikersnaam en wachtwoord

De gebruiker wordt geverifieerd op de VPN-server door een gebruikersnaam en wachtwoord op te geven.
