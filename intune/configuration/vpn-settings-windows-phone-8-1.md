---
title: VPN-instellingen configureren voor Windows Phone 8.1-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Voeg een VPN-configuratie profiel toe of maak dit met behulp van VPN-configuratie-instellingen (virtueel particulier netwerk), met inbegrip van de verbindings gegevens en de proxy-instellingen om IP-of FQDN-adres op te nemen, en TCP-poort in Microsoft Intune op apparaten met Windows Phone 8,1.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/19/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 70f33fe132eb6c3dbf91c5dc313369d75f4f3e24
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207023"
---
# <a name="add-vpn-settings-on-windows-phone-81-devices-in-microsoft-intune"></a>VPN-instellingen toevoegen op Windows Phone 8.1-apparaten in Microsoft Intune



In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met Windows Phone 8.1. te configureren. 

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de volgende lijst worden geconfigureerd.

>[!IMPORTANT]
>Windows Phone 8,1 VPN-profielen worden ook toegepast op Windows 10-apparaten.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

- **Alle instellingen alleen Toep assen op Windows Phone 8,1**: Configureer deze instelling in de klassieke intune-Portal. In het beheer centrum van micro soft Endpoint Manager kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, worden instellingen alleen toegepast op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
- **Verbindingsnaam**: Voer een naam in voor deze verbinding. Gebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Verificatiemethode**: Kies hoe apparaten worden geverifieerd bij de VPN-server vanuit:
  - **Certificaten**: Kies onder **Verificatiecertificaat** een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt om de verbinding te verifiëren. Zie [Certificaten configureren](../protect/certificates-configure.md) voor meer informatie over certificaatprofielen.
  - **Gebruikersnaam en wachtwoord**: Eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.
- **Servers**: Voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken.
  - **Toevoegen**: Hiermee opent u de blade **Rij toevoegen** waar u de volgende informatie kunt opgeven:
    - **Beschrijving**: Geef een beschrijvende naam op voor de server, zoals **Contoso VPN-server**.
    - **IP-adres of FQDN**: Geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
    - **Standaardserver**: Hiermee wordt deze server ingeschakeld als de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
  - **Importeren**: Blader naar een bestand met een door komma's gescheiden lijst met servers in de indeling: beschrijving, IP-adres of FQDN, standaardserver. Kies **OK** om deze servers te importeren in de lijst met **servers**.
  - **Exporteren**: Hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand).

- **VPN niet gebruiken op het Wi-Fi-netwerk van het bedrijf**: Schakel deze optie in om aan te geven dat de VPN-verbindingen niet worden gebruikt wanneer het apparaat is verbonden met het Wi-Fi-netwerk van het bedrijf.
- **VPN niet gebruiken op het Wi-Fi-thuisnetwerk**: Schakel deze optie in om aan te geven dat de VPN-verbinding niet wordt gebruikt wanneer het apparaat is verbonden met een Wi-Fi-netwerk thuis.

- **Type verbinding**: Selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
  - **Check Point Capsule VPN**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**

- **Aanmeldingsgroep of domein** (alleen SonicWall Mobile Connect): Geef de naam op van de aanmeldingsgroep of het aanmeldingsdomein waarmee u verbinding wilt maken.
- **Rol** (alleen Pulse Secure): Geef de naam op van de gebruikersrol die toegang tot deze verbinding heeft. Een gebruikersrol definieert persoonlijke instellingen en opties en schakelt bepaalde toegangsfuncties in of uit.
- **Realm** (alleen Pulse Secure): Geef de naam op van de verificatierealm die u wilt gebruiken. Een verificatierealm is een groepering van verificatieresources die worden gebruikt door het verbindingstype Pulse Secure.

- **Zoeklijst voor DNS-achtervoegsels**: Hier kunt u een of meer DNS-achtervoegsels **Toevoegen**. Elk DNS-achtervoegsel dat u opgeeft, wordt doorzocht wanneer met behulp van een korte naam verbinding met een website wordt gemaakt. U geeft bijvoorbeeld de DNS-achtervoegsels **domain1.contoso.com** en **domain2.contoso.com** op en gaat vervolgens naar de URL `http://mywebsite`. Vervolgens worden de URL’s `http://mywebsite.domain1.contoso.com` en `http://mywebsite.domain2.contoso.com` gezocht.

- **Aangepaste XML**: Geef aangepaste XML-opdrachten op waarmee de VPN-verbinding wordt geconfigureerd.

  **Voorbeeld van Pulse Secure**:

  ```xml
  <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
  ```

  **Voorbeeld van CheckPoint Mobile VPN**:

  ```xml
  <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
  ```

  **Voorbeeld van SonicWall Mobile Connect**:

  ```xml
  <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
  ```

  **Voorbeeld van F5 Edge Client**:

  ```xml
  <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
  ```

  Raadpleeg de VPN-documentatie van de fabrikant voor meer informatie over het schrijven van aangepaste XML-opdrachten.

- **Split tunneling**: U kunt deze optie **Inschakelen** of **Uitschakelen** om apparaten op basis van het verkeer te laten bepalen welke verbinding moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar het standaardnetwerk van het hotel om gewoon op het web te surfen.

## <a name="proxy-settings"></a>Proxyinstellingen

- **Proxy-instellingen automatisch detecteren**: Als de VPN-server een proxyserver voor de verbinding vereist, geeft u op of u wilt dat apparaten de verbindingsinstellingen automatisch detecteren.
- **Script voor automatische configuratie**: Gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.
- **Proxyserver gebruiken**: Schakel deze optie in als u de proxyserverinstellingen handmatig wilt invoeren.
  - **Adres**: Voer het adres van de proxyserver in (als een IP-adres).
  - **Poortnummer**: Voer het poortnummer in dat is gekoppeld aan de proxyserver.
- **Proxy niet gebruiken voor lokale adressen**: Als voor de VPN-server een proxyserver voor de verbinding is vereist en u de proxyserver niet wilt gebruiken voor lokale adressen die u opgeeft, selecteert u deze optie.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Configureer VPN-instellingen op apparaten met [Android](vpn-settings-android.md), [Android Enter prise](vpn-settings-android-enterprise.md), [macOS](vpn-settings-macos.md)en [Windows 10](vpn-settings-windows-10.md) .
