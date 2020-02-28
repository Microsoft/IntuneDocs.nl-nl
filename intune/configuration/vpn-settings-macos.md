---
title: VPN-instellingen configureren voor macOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Een VPN-configuratieprofiel (virtueel particulier netwerk) toevoegen of maken, met inbegrip van de verbindingsgegevens, split tunneling, aangepaste VPN-instellingen met de id, sleutel- en waardeparen, proxy-instellingen met een configuratiescript, IP-adres of FQDN en TCP-poort in Microsoft Intune op apparaten met macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b20a7eca6f71d46380f9fcdb1674226cc54a104f
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77510776"
---
# <a name="add-vpn-settings-on-macos-devices-in-microsoft-intune"></a>VPN-instellingen toevoegen voor macOS-apparaten in Microsoft Intune



In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met macOS te configureren.

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de volgende lijst worden geconfigureerd.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](vpn-settings-configure.md).

> [!NOTE]
> Deze instellingen zijn beschikbaar voor alle inschrijvingstypen. Zie [macOS-inschrijving](../enrollment/macos-enroll.md) voor meer informatie over de inschrijvingstypen.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

**Verbindingsnaam**: Voer een naam in voor deze verbinding. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: Geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
- **Verificatiemethode**: Kies hoe apparaten worden geverifieerd bij de VPN-server vanuit:
  - **Certificaten**: Kies onder **Verificatiecertificaat** een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt om de verbinding te verifiëren. Zie [Certificaten configureren](../protect/certificates-configure.md) voor meer informatie over certificaatprofielen.
  - **Gebruikersnaam en wachtwoord**: Eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.
- **Type verbinding**: Selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Aangepaste VPN**
- **Split tunneling**: U kunt deze optie **Inschakelen** of **Uitschakelen** om apparaten op basis van het verkeer te laten bepalen welke verbinding moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar het standaardnetwerk van het hotel om gewoon op het web te surfen.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS/iPadOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../apps/apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Basis-VPN-instellingen

Als u **Aangepaste VPN** hebt geselecteerd, configureert u deze instellingen:

- **VPN-id**: voer een id in voor de VPN-app die u gebruikt. Deze id wordt aangeleverd door uw VPN-aanbieder.
- **Sleutel-waardeparen voor de aangepaste VPN-kenmerken invoeren**: Voeg **Sleutels** en **Waarden** toe of importeer deze om uw VPN-verbinding aan te passen. Deze waarden worden doorgaans aangeleverd door uw VPN-aanbieder.

## <a name="proxy-settings"></a>Proxyinstellingen

- **Script voor automatische configuratie**: Gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** in die het configuratiebestand bevat. Voer bijvoorbeeld `http://proxy.contoso.com` in.
- **Adres**: Voer het adres van de proxyserver in (als een IP-adres).
- **Poortnummer**: Voer het poortnummer in dat is gekoppeld aan de proxyserver.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Configureer VPN-instellingen op apparaten met [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [iOS/iPadOS](vpn-settings-ios.md) en [Windows 10](vpn-settings-windows-10.md).
