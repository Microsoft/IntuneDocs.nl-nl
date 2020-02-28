---
title: VPN-instellingen gebruiken voor Android-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk alle instellingen voor het maken van VPN-verbindingen op Android-apparaten in Microsoft Intune. Voer de verbindingsnaam, het IP-adres of de FQDN van de VPN-server in, kies de gewenste gebruikersverificatie en kies verbindingstypen voor Citrix, SonicWall, Check Point Capsule en Pulse Secure.
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
ms.openlocfilehash: 3f82cc74aa2e351ee63ffba2629e9ddddb57fc76
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512514"
---
# <a name="android-device-settings-to-configure-vpn-in-intune"></a>Instellingen voor Android-apparaten voor het configureren van VPN in Intune

In dit artikel vindt u een overzicht en beschrijving van de verschillende instellingen die u voor VPN-verbindingen kunt beheren op Android-apparaten. U kunt deze instellingen onder meer gebruiken als onderdeel van uw MDM-oplossing (Mobile Device Management) om een VPN-verbinding te maken, de VPN-verificatiemethode te kiezen en een VPN-servertype te selecteren.

Als Intune-beheerder kunt u VPN-instellingen maken en toewijzen aan Android-apparaten. 

Zie [VPN-profielen](vpn-settings-configure.md) voor meer informatie over VPN-profielen in Intune.

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

- **Vingerafdruk** (alleen voor VPN Check Point Capsule): geef een tekenreeks op (bijvoorbeeld **Contoso-vingerafdrukcode**) om te verifiëren dat de VPN-server kan worden vertrouwd. Er wordt een vingerafdruk verzonden naar de client zodat deze alle servers vertrouwt die over dezelfde vingerafdruk beschikken. Als het apparaat niet over de vingerafdruk beschikt, wordt de gebruiker gevraagd om de VPN-server te vertrouwen terwijl de vingerafdruk wordt weergegeven. De gebruiker controleert de vingerafdruk handmatig en kiest ervoor om de verbinding te vertrouwen.
- **Sleutel- en waardeparen voor de kenmerken van de Citrix VPN invoeren** (alleen voor Citrix): voer sleutel- en waardeparen in, afkomstig van Citrix. Met deze waarden configureert u de eigenschappen van de VPN-verbinding. 

  U kunt ook een bestand met door komma's gescheiden waarden (.csv) met sleutel- en waardeparen **importeren**. Controleer de eigenschappen **Mijn gegevens bevatten kopteksten** en **Sleutel**.

  Nadat u de sleutel- en waardeparen hebt toegevoegd, gebruikt u **Exporteren** om een back-up van uw gegevens te maken in de vorm van een CSV-bestand.

## <a name="next-steps"></a>Volgende stappen

[Het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

U kunt ook VPN-profielen maken voor apparaten met [Android Enterprise](vpn-settings-android-enterprise.md), [iOS/iPadOS](vpn-settings-ios.md), [macOS](vpn-settings-macos.md), [Windows 10 en hoger](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md) en [Windows Phone 8.1](vpn-settings-windows-phone-8-1.md).
