---
title: VPN-instellingen configureren in Intune
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: in dit onderwerp leest u hoe u Intune kunt gebruiken voor het configureren van VPN-verbindingen op de apparaten die u beheert.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 2d93edb688dbf296137a133f0b7ae065fc1cc89d
ms.lasthandoff: 02/18/2017


---

# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>VPN-instellingen configureren in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Met virtuele particuliere netwerken (VPN's) geeft u uw gebruikers veilige externe toegang tot uw bedrijfsnetwerk. Apparaten gebruiken een VPN-verbindingsprofiel om een verbinding met de VPN-server op te zetten. Gebruik **VPN-profielen** in Microsoft Intune om VPN-instellingen te implementeren voor gebruikers en apparaten in uw organisatie, zodat deze gemakkelijk en veilig verbinding met het netwerk kunnen maken.

U wilt bijvoorbeeld alle iOS-apparaten voorzien van de instellingen die vereist zijn om verbinding te maken met een bestandsshare op het bedrijfsnetwerk. U maakt een VPN-profiel met de instellingen die nodig zijn om verbinding te maken met het bedrijfsnetwerk en vervolgens wijst u dit profiel toe aan alle gebruikers met iOS-apparaten. De gebruikers zien de VPN-verbinding in de lijst met beschikbare netwerken en kunnen moeiteloos verbinding maken.

## <a name="vpn-connection-types"></a>VPN-verbindingstypen

U kunt VPN-profielen met de volgende verbindingstypen maken:

|||
|-|-|
|Type verbinding|Android|iOS|macOS|Windows Phone 8,1|Windows 8.1|Windows 10|
|Pulse Secure|Ja|Ja|Ja|Ja|Ja|Yes|
|Cisco (IPsec)|Nee|Ja|Nee|Nee|Nee|Nee|
|Citrix|Yes|Ja|Nee|Nee|Nee|Nee|
|F5 Edge Client|Ja|Ja|Ja|Ja|Ja|Ja|
|Dell SonicWALL Mobile Connect|Ja|Ja|Ja|Ja|Ja|Yes|
|Check Point Capsule VPN|Yes|Ja|Ja|Ja|Ja|Yes|
|Cisco AnyConnect|Ja|Ja|Ja|Nee|Nee|Nee|
|Automatisch|Nee|Nee|Nee|Nee|Nee|Yes|
|IKEv2|Nee|Nee|Nee|Nee|Nee|Ja|
|L2TP|Nee|Nee|Nee|Nee|Nee|Yes|
|PPTP|Nee|Nee|Nee|Nee|Nee|Yes|
|Aangepast|Nee|Ja|Ja|Nee|Nee|Nee|


> [!IMPORTANT]
> Voordat u VPN-profielen die op een apparaat zijn geïmplementeerd kunt gebruiken, moet u de betreffende VPN-app voor het profiel installeren. U kunt de informatie in het onderwerp [What is app management in Microsoft Intune?](/intune-azure/manage-apps/what-is-app-management) (Wat is app-beheer in Microsoft Intune?) gebruiken bij het implementeren van de betreffende app met behulp van Intune.  

Zie [Create custom VPN profiles](create-custom-vpn-profiles.md) (Aangepaste VPN-profielen maken) voor meer informatie over het maken van aangepaste VPN-profielen met behulp van URI-instellingen.     

## <a name="create-a-device-profile-containing-vpn-settings"></a>Een apparaatprofiel met VPN-instellingen maken

1. Meld u aan bij Azure Portal.
2. Kies **Meer services** > **Overige** > **Intune**.
3. Kies **Apparaten configureren** op de blade **Intune**.
2. Kies **Beheren** > **Profielen** op de blade **Apparaatconfiguratie**.
3. Kies **Profiel maken** op de blade Profielen.
4. Voer op de blade **Profiel maken** een **naam** en een **beschrijving** in voor het VPN-profiel.
5. Selecteer in de vervolgkeuzelijst **Platform** het apparaatplatform waarop u de VPN-instellingen wilt toepassen. Op dit moment kunt u een van de volgende platformen kiezen voor VPN-apparaatinstellingen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 en hoger**
    - **Windows 10 en hoger**
6. Kies **VPN** in de vervolgkeuzelijst **Profieltype**.
7. Welke instellingen u kunt configureren, is afhankelijk van het platform dat u hebt gekozen. Raadpleeg een van de volgende onderwerpen voor gedetailleerde instellingen voor elk platform:
    - [Android-instellingen](vpn-for-android.md)
    - [iOS-instellingen](vpn-for-ios.md)
    - [macOS-instellingen](vpn-for-macos.md)
    - [Windows Phone 8.1-instellingen](vpn-for-windows-phone-8-1.md)
    - [Windows 8.1-instellingen](vpn-for-windows-8-1.md)
    - [Windows 10-instellingen](vpn-for-windows-10.md)
8. Als u klaar bent, gaat u terug naar de blade **Profiel maken** en kiest u **Maken**.

Het profiel wordt gemaakt en wordt weergegeven op de blade met de profielenlijst.
Zie [How to assign device profiles](how-to-assign-device-profiles.md) (Apparaatprofielen toewijzen) als u wilt doorgaan en dit profiel wilt toewijzen aan groepen.


## <a name="methods-of-securing-vpn-profiles"></a>Methoden voor het beveiligen van VPN-profielen

Voor VPN-profielen kan een aantal verschillende verbindingstypen en -protocollen van verschillende fabrikanten worden gebruikt. Deze verbindingen zijn doorgaans beveiligd met een van de volgende twee methoden.

### <a name="certificates"></a>Certificaten

Wanneer u het VPN-profiel maakt, kiest u een SCEP- of PFX-certificaatprofiel dat u eerder hebt gemaakt in Intune. Dit wordt het identiteitscertificaat genoemd. Het wordt gebruikt voor verificatie aan de hand van een vertrouwd-certificaatprofiel (*basiscertificaat*) dat u hebt gemaakt om te bepalen of het apparaat van de gebruiker verbinding mag maken. Het vertrouwde certificaat wordt geïmplementeerd op de computer die de VPN-verbinding verifieert, meestal is dat de VPN-server.

Zie [How to configure certificates with Microsoft Intune](how-to-configure-certificates.md) (Certificaten configureren met Microsoft Intune) voor meer informatie over het gebruiken en maken van certificaatprofielen in Intune.

### <a name="user-name-and-password"></a>Gebruikersnaam en wachtwoord

De gebruiker wordt geverifieerd op de VPN-server door een gebruikersnaam en wachtwoord op te geven.

