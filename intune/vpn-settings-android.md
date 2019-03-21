---
title: VPN-instellingen configureren voor Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Wanneer u een VPN-configuratieprofiel voor Android- en Android for Work-apparaten wilt maken, voert u de naam van de verbinding, het IP-adres of de FQDN-naam van de VPN-server in, kiest u de wijze waarop gebruikers bij de VPN-server moeten verifiëren en kiest u vervolgens Citrix, SonicWall, Check Point Capsule, Pulse Secure en Microsoft Edge-verbindingstypen.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 666b61eec021fa6a2cdad5126f572234d97b6883
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566094"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>VPN-instellingen configureren voor Android-apparaten in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met Android te configureren.

U kunt VPN-instellingen voor de volgende platforms configureren:

- [Android](#android-vpn-settings)
- [Android Enterprise](#android-enterprise-vpn-settings)

Afhankelijk van de instellingen die u kiest, kunnen niet alle volgende waarden worden geconfigureerd.

## <a name="android-vpn-settings"></a>VPN-instellingen voor Android

- **Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat de beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: geef het IP-adres of de FQDN (Fully Qualified Domain Name) op van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld **192.168.1.1** of **vpn.contoso.com** in.

  - **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. Uw opties zijn:

    - **Certificaten**: selecteer een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](certificates-configure.md) bevat de stappen voor het maken van een certificaatprofiel.
    - **Gebruikersnaam en wachtwoord**: tijdens het aanmelden bij de VPN-server worden de eindgebruikers gevraagd een gebruikersnaam en wachtwoord in te voeren.

- **Verbindingstype**: selecteer het type VPN-verbinding. Uw opties zijn:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Vingerafdruk** (alleen voor VPN Check Point Capsule): geef een tekenreeks op (bijvoorbeeld **Contoso-vingerafdrukcode**) om te verifiëren dat de VPN-server kan worden vertrouwd. Een vingerafdruk kan worden verzonden naar de client zodat deze alle servers vertrouwt die over dezelfde vingerafdruk beschikken wanneer er verbinding wordt gemaakt. Als het apparaat niet over de vingerafdruk beschikt, wordt de gebruiker gevraagd om de VPN-server te vertrouwen terwijl de vingerafdruk wordt weergegeven. De gebruiker controleert de vingerafdruk handmatig en kiest Vertrouwen om verbinding te maken.
- **Sleutel- en waardeparen voor de kenmerken van de Citrix VPN invoeren** (alleen voor Citrix): voer sleutel- en waardeparen in, afkomstig van Citrix. Met deze waarden configureert u de eigenschappen van de VPN-verbinding.

## <a name="android-enterprise-vpn-settings"></a>VPN-instellingen voor Android Enterprise

- **Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat de beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: geef het IP-adres of de FQDN (Fully Qualified Domain Name) op van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld **192.168.1.1** of **vpn.contoso.com** in.

  - **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. Uw opties zijn:
  
    - **Certificaten**: selecteer een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](certificates-configure.md) bevat de stappen voor het maken van een certificaatprofiel.
    - **Gebruikersnaam en wachtwoord**: tijdens het aanmelden bij de VPN-server worden de eindgebruikers gevraagd een gebruikersnaam en wachtwoord in te voeren.

- **Verbindingstype**: selecteer het type VPN-verbinding. Uw opties zijn:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5-toegang**
  - **Pulse Secure**

## <a name="next-steps"></a>Volgende stappen
[VPN-profielen in Intune](vpn-settings-configure.md)
