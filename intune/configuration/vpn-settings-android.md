---
title: VPN-instellingen gebruiken voor Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk alle instellingen voor het maken van VPN-verbindingen op Android-apparaten in Microsoft Intune. Voer de verbindings naam, het IP-adres of de FQDN van de VPN-server in, Kies hoe gebruikers verifiëren en kies Citrix, SonicWall, Check Point capsule en Pulse Secure Connect types.
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
ms.openlocfilehash: 458c38e4cce7022d7a56e86cc171365f1496741e
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206292"
---
# <a name="android-device-settings-to-configure-vpn-in-intune"></a>Instellingen voor Android-apparaten voor het configureren van VPN in intune



In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u voor VPN-verbindingen kunt beheren op Android-apparaten. Als onderdeel van uw Mobile Device Management-oplossing (MDM) kunt u deze instellingen gebruiken om een VPN-verbinding te maken, kiezen hoe de VPN verifieert, een VPN-server type en meer.

Als Intune-beheerder kunt u VPN-instellingen maken en toewijzen aan Android-apparaten. 

Zie [VPN-profielen](vpn-settings-configure.md)voor meer informatie over VPN-profielen in intune.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](vpn-settings-configure.md#create-a-device-profile) en kies **Android**.

## <a name="base-vpn"></a>Basis-VPN

- **Verbindingsnaam**: Voer een naam in voor deze verbinding. Eindgebruikers zien deze naam wanneer ze op hun apparaat de beschikbare VPN-verbindingen zoeken. Voer bijvoorbeeld `Contoso VPN` in.
- **IP-adres of FQDN**: geef het IP-adres of de FQDN (Fully Qualified Domain Name) op van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld **192.168.1.1** of **vpn.contoso.com** in.

  - **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. Uw opties zijn:

    - **Certificaten**: selecteer een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](../protect/certificates-configure.md) bevat de stappen voor het maken van een certificaatprofiel.
    - **Gebruikersnaam en wachtwoord**: Tijdens het aanmelden bij de VPN-server wordt de eindgebruikers gevraagd hun gebruikersnaam en wachtwoord in te voeren.

- **Type verbinding**: selecteer het type van de VPN-verbinding. Uw opties zijn:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5-toegang**
  - **Pulse Secure**
  - **Citrix SSO**

- **Vingerafdruk** (alleen voor VPN Check Point Capsule): geef een tekenreeks op (bijvoorbeeld **Contoso-vingerafdrukcode**) om te verifiëren dat de VPN-server kan worden vertrouwd. Er wordt een vinger afdruk verzonden naar de client, zodat de client weet dat alle servers met dezelfde vinger afdruk moeten worden vertrouwd. Als het apparaat niet over de vingerafdruk beschikt, wordt de gebruiker gevraagd om de VPN-server te vertrouwen terwijl de vingerafdruk wordt weergegeven. De gebruiker controleert de vingerafdruk handmatig en kiest ervoor om de verbinding te vertrouwen.
- **Sleutel- en waardeparen voor de kenmerken van de Citrix VPN invoeren** (alleen voor Citrix): voer sleutel- en waardeparen in, afkomstig van Citrix. Met deze waarden configureert u de eigenschappen van de VPN-verbinding. 

  U kunt ook een bestand met door komma's gescheiden waarden (. CSV) met sleutels en waardeparen **importeren** . Controleer of de gegevens voor de eigenschappen de namen en **sleutels** **hebben** .

  Nadat u de sleutel-en waarden paren hebt toegevoegd, gebruikt u **exporteren** om een back-up van uw gegevens naar een CSV-bestand te maken.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook VPN-profielen maken voor [Android Enter prise](vpn-settings-android-enterprise.md), [IOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 en hoger](vpn-settings-windows-10.md), [Windows 8,1](vpn-settings-windows-8-1.md)en [Windows Phone 8,1](vpn-settings-windows-phone-8-1.md) -apparaten.
