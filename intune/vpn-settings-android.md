---
title: Microsoft Intune VPN-instellingen voor Android-apparaten
titlesuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op Android-apparaten te configureren
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6753e0232548d862b46a273f1be0105ad7f16d63
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-android"></a>VPN-instellingen in Microsoft Intune configureren voor Android-apparaten 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met Android te configureren.


U kunt VPN-instellingen voor de volgende platforms configureren:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Afhankelijk van de instellingen die u kiest, kunnen niet alle volgende waarden worden geconfigureerd.

## <a name="android-vpn-settings"></a>VPN-instellingen voor Android
**Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server vanaf:
    - **Certificaten**: kies een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt om de verbinding te verifiëren. Zie [Certificaten configureren](certificates-configure.md) voor meer informatie over certificaatprofielen.
    - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.
- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Vingerafdruk** (alleen voor Check Point Capsule VPN): geef een tekenreeks op (bijvoorbeeld 'Contoso-vingerafdrukcode') die wordt gebruikt om te controleren of de VPN-server kan worden vertrouwd. Een vingerafdruk kan worden verzonden naar de client zodat deze alle servers vertrouwt die dezelfde vingerafdruk presenteren wanneer er verbinding wordt gemaakt. Als het apparaat nog niet over de vingerafdruk beschikt, wordt de gebruiker gevraagd om de VPN-server waarmee deze verbinding maakt, te vertrouwen terwijl de vingerafdruk wordt weergegeven (de gebruiker controleert de vingerafdruk handmatig en kiest Vertrouwen om verbinding te maken).
- **Sleutel- en waardeparen voor de kenmerken van de Citrix VPN invoeren** (alleen voor Citrix): voer sleutel- en waardeparen in, afkomstig van Citrix, om de eigenschappen van de VPN-verbinding te configureren.

## <a name="android-for-work-vpn-settings"></a>VPN-instellingen voor Android for Work

**Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server vanaf:
    - **Certificaten**: kies een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt om de verbinding te verifiëren. Zie [Certificaten configureren](certificates-configure.md) voor meer informatie over certificaatprofielen.
    - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.
- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

