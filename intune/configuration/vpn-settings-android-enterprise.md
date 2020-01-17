---
title: VPN-instellingen gebruiken voor Android Enterprise in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk alle instellingen voor het maken van VPN-verbindingen op Android Enter prise-apparaten in Microsoft Intune. Voer de verbindings naam, het IP-adres of de FQDN van de VPN-server in, Kies hoe gebruikers verifiëren en kies Citrix, SonicWall, Check Point capsule en Pulse Secure Connect types.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a0c11be374e36ec32feb9540f6cfd4f1bc794e9c
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206309"
---
# <a name="android-enterprise-device-settings-to-configure-vpn-in-intune"></a>Instellingen voor het Android-bedrijfs apparaat voor het configureren van VPN in intune



In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u voor VPN-verbindingen kunt beheren op Android Enterprise-apparaten. Als onderdeel van uw Mobile Device Management-oplossing (MDM) kunt u deze instellingen gebruiken om een VPN-verbinding te maken, kiezen hoe de VPN verifieert, een VPN-server type en meer.

Als Intune-beheerder kunt u VPN-instellingen maken en toewijzen aan Android Enterprise-apparaten. 

Zie [VPN-profielen](vpn-settings-configure.md)voor meer informatie over VPN-profielen in intune.

> [!NOTE]
> Als u de optie altijd-op-VPN wilt configureren, moet u een VPN-profiel maken en ook een profiel voor [beperkingen voor apparaten](device-restrictions-android-for-work.md#connectivity) maken met de instelling altijd-op-VPN geconfigureerd.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](vpn-settings-configure.md#create-a-device-profile) en kies **Android Enterprise**.

## <a name="device-owner-only"></a>Alleen eigenaar van het apparaat

- **Verbindingsnaam**: Voer een naam in voor deze verbinding. Eindgebruikers zien deze naam wanneer ze op hun apparaat de beschikbare VPN-verbindingen zoeken. Voer bijvoorbeeld `Contoso VPN` in.
- **IP-adres of FQDN**: geef het IP-adres of de FQDN (Fully Qualified Domain Name) op van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld **192.168.1.1** of **vpn.contoso.com** in.

  - **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. Uw opties zijn:
  
    - **Certificaten**: selecteer een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](../protect/certificates-configure.md) bevat de stappen voor het maken van een certificaatprofiel.
    - **Gebruikersnaam en wachtwoord**: Tijdens het aanmelden bij de VPN-server wordt de eindgebruikers gevraagd hun gebruikersnaam en wachtwoord in te voeren.

- **Type verbinding**: selecteer het type van de VPN-verbinding. Uw opties zijn:

  - **Cisco AnyConnect**
  - **F5-toegang**
  - **Pulse Secure**

## <a name="work-profile-only"></a>Alleen werkprofiel

- **Verbindingsnaam**: Voer een naam in voor deze verbinding. Eindgebruikers zien deze naam wanneer ze op hun apparaat de beschikbare VPN-verbindingen zoeken. Voer bijvoorbeeld `Contoso VPN` in.
- **IP-adres of FQDN**: geef het IP-adres of de FQDN (Fully Qualified Domain Name) op van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld **192.168.1.1** of **vpn.contoso.com** in.

  - **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. Uw opties zijn:
  
    - **Certificaten**: selecteer een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](../protect/certificates-configure.md) bevat de stappen voor het maken van een certificaatprofiel.
    - **Gebruikersnaam en wachtwoord**: Tijdens het aanmelden bij de VPN-server wordt de eindgebruikers gevraagd hun gebruikersnaam en wachtwoord in te voeren.

- **Type verbinding**: selecteer het type van de VPN-verbinding. Uw opties zijn:

  - **Cisco AnyConnect**
  - **F5-toegang**
  - **Pulse Secure**
  - **SonicWall Mobile Connect**
  - **Check Point Capsule VPN**

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook VPN-profielen maken voor [Android](vpn-settings-android.md), [IOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 en hoger](vpn-settings-windows-10.md), [Windows 8,1](vpn-settings-windows-8-1.md)en [Windows Phone 8,1](vpn-settings-windows-phone-8-1.md) -apparaten.
