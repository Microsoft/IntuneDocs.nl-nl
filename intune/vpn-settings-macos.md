---
title: Microsoft Intune VPN-instellingen voor macOS-apparaten
titlesuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op macOS-apparaten te configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4330d8e8095df49b14ab60c4b08aae44d134452
ms.sourcegitcommit: cac71802b2782700f0d52ea114089d73620cd1ed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50679216"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-macos"></a>VPN-instellingen in Microsoft Intune configureren voor apparaten met macOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met macOS te configureren.

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de volgende lijst worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

**Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server vanaf:
    - **Certificaten**: kies onder **Verificatiecertificaat** een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt om de verbinding te verifiëren. Zie [Certificaten configureren](certificates-configure.md) voor meer informatie over certificaatprofielen.
    - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.
- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Aangepaste VPN**
- **Split tunneling** - : u kunt deze optie **inschakelen** of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar het standaardnetwerk van het hotel om gewoon op het web te surfen.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Basis-VPN-instellingen

Als u **Aangepaste VPN** hebt geselecteerd, configureert u deze instellingen:

- **VPN-id** dit is een id voor de VPN-app die u gebruikt en wordt geleverd door uw VPN-aanbieder.
- **Sleutel- en waardeparen voor de aangepaste VPN-kenmerken invoeren**: voeg **sleutel-** en **waardeparen** toe of importeer deze om uw VPN-verbinding aan te passen. Deze waarden worden doorgaans geleverd door uw VPN-aanbieder.


## <a name="proxy-settings"></a>Proxyinstellingen

- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `** http://proxy.contoso.com**`) in die het configuratiebestand bevat.
- **Adres**: voer het adres van de proxyserver in (als IP-adres).
- **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.
