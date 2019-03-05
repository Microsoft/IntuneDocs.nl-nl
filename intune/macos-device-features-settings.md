---
title: Instellingen van apparaatfuncties voor macOS in Microsoft Intune - Azure | Microsoft Docs
description: Raadpleeg alle instellingen om macOS-apparaten te configureren voor AirPrint in Microsoft Intune. Raadpleeg tevens de stappen om het pad, het IP-adres en de poortinstellingen van een AirPrint-server in uw netwerk te krijgen. Gebruik deze instellingen in een apparaatconfiguratieprofiel voor het configureren van macOS-apparaten voor het gebruik van AirPrint-servers in uw netwerk.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/05/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e0707226412d314ac1d44ba339b4c9151b394919
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233896"
---
# <a name="macos-device-feature-settings-in-intune"></a>Instellingen van apparaatfuncties voor macOS in Intune

Intune bevat enkele ingebouwde instellingen waarmee macOS-gebruikers printopdrachten naar AirPrint-printers in uw netwerk kunnen sturen. Dit artikel beschrijft deze instellingen en wat elke instelling doet. Het beschrijft tevens de stappen voor het ophalen van het IP-adres, het pad en de poort van AirPrint-printers via de Terminal-app (emulator).

## <a name="before-you-begin"></a>Voordat u begint

[Maak een macOS-apparaatconfiguratieprofiel](device-features-configure.md).

## <a name="airprint-settings"></a>AirPrint-instellingen

1. Selecteer in **Instellingen** de optie **AirPrint**. Voer de volgende eigenschappen van de AirPrint-server in:

    - **IP-adres**: Voer het IPv4- of IPv6-adres van de printer in. Als u hostnamen gebruikt om printers te identificeren, krijgt u het IP-adres door de printer in de Terminal-app te pingen. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
    - **Pad**: Voer het pad van de printer in. Het pad is doorgaans `ipp/print` voor printers in uw netwerk. In [Haal het IP-adres en het pad op](#get-the-ip-address-and-path) (in dit artikel) vindt u meer informatie.
    - **Poort**: Voer de luisterpoort van de AirPrint-bestemming in. Als u deze eigenschap leeg laat, maakt AirPrint gebruik van de standaardpoort. Beschikbaar in iOS 11.0 en hoger.
    - **TLS**: Kies **Inschakelen** voor het beveiligen van AirPrint-verbindingen met Transport Layer Security (TLS). Beschikbaar in iOS 11.0 en hoger.

2. Selecteer **Toevoegen**. De AirPrint-server is toegevoegd aan de lijst. U kunt veel AirPrint-servers toevoegen.

    U kunt ook een door komma's gescheiden bestand (.csv) **importeren** met een lijst van AirPrint-printers. Nadat u AirPrint-printers aan Intune hebt toegevoegd, kunt u bovendien deze lijst **exporteren**.

3. Selecteer als u klaar bent **OK** om uw wijzigingen op te slaan.

## <a name="get-the-ip-address-and-path"></a>IP-adres en pad ophalen

Om AirPrinter-servers toe te voegen, hebt u het IP-adres van de printer, het bronpad en de poort nodig. De volgende stappen laten zien hoe u aan deze informatie komt.

1. Open op een Mac die verbonden is met hetzelfde lokale netwerk (subnet) als de AirPrint-printers de **Terminal** (via **/Programma's/Hulpprogramma's**).
2. Typ in de Terminal-app `ippfind` en selecteer Enter.

    Noteer de printergegevens. Er wordt bijvoorbeeld iets in de trant van `ipp://myprinter.local.:631/ipp/port1` geretourneerd. Het eerste deel is de naam van de printer. Het laatste deel (`ipp/port1`) is het bronpad.

3. Typ in de terminal `ping myprinter.local` en selecteer Enter.

   Noteer het IP-adres. Er wordt bijvoorbeeld iets in de trant van `PING myprinter.local (10.50.25.21)` geretourneerd.

4. Gebruik de waarden van het IP-adres en het bronpad. In dit voorbeeld is het IP-adres `10.50.25.21` en het bronpad `/ipp/port1`.

## <a name="next-steps"></a>Volgende stappen

- Bekijk alle instellingen voor [iOS](ios-device-features-settings.md)-apparaten.
- Wijs dit profiel aan groepen toe; zie [Apparaatprofielen toewijzen](device-profile-assign.md).
