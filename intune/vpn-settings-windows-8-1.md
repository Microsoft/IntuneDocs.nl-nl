---
title: Microsoft Intune VPN-instellingen voor Windows 8.1-apparaten
titleSuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met Windows 8.1. te configureren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/6/2018
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 521243d2c6560fbac77a4ee2aba6ed9577d3abe1
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2019
ms.locfileid: "71303242"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-81"></a>VPN-instellingen in Microsoft Intune configureren voor apparaten met Windows 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met Windows 8.1. te configureren.

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de volgende lijst worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen


- **Alle instellingen alleen op Windows 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, worden de instellingen alleen toegepast op Windows 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10-apparaten.
- **Verbindingsnaam**: voer een naam voor deze verbinding in. Gebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Servers**: voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken.
  - **Toevoegen**: hiermee opent u het deelvenster **Rij toevoegen** waar u de volgende informatie kunt opgeven:
    - **Beschrijving**: geef een beschrijvende naam op voor de server, zoals **Contoso VPN-server**.
    - **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
    - **Standaardserver**: hiermee wordt deze server ingeschakeld als de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
  - **Importeren**: blader naar een bestand met een kommagescheiden lijst met servers in de indelingsbeschrijving, IP-adres of FQDN, Standaardserver. Kies **OK** om deze in de lijst **Servers** te importeren.
  - **Exporteren**: hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand).

- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
- **Check Point Capsule VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Aanmeldingsgroep of -domein** (alleen SonicWall Mobile Connect): geef de naam op van de aanmeldingsgroep of het aanmeldingsdomein waarmee u verbinding wilt maken.

- **Rol** (alleen Pulse Secure): geef de naam op van de gebruikersrol die toegang tot deze verbinding heeft. Een gebruikersrol definieert persoonlijke instellingen en opties en schakelt bepaalde toegangsfuncties in of uit.

- **Realm** (alleen Pulse Secure): geef de naam op van de verificatierealm die u wilt gebruiken. Een verificatierealm is een groepering van verificatieresources die worden gebruikt door het verbindingstype Pulse Secure.


- **Aangepaste XML**: geef aangepaste XML-opdrachten op waarmee de VPN-verbinding wordt geconfigureerd.

**Voorbeeld voor Pulse Secure:**

```xml
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Voorbeeld voor CheckPoint Mobile VPN:**

```xml
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Voorbeeld voor SonicWall Mobile Connect:**

```xml
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Voorbeeld voor F5 Edge Client:**

```xml
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Raadpleeg de VPN-documentatie van de respectievelijke fabrikanten voor meer informatie over het schrijven van aangepaste XML-opdrachten.


## <a name="proxy-settings"></a>Proxyinstellingen

- **Automatisch proxyinstellingen detecteren**: als de VPN-server een proxyserver voor de verbinding vereist, geeft u op of apparaten de verbindingsinstellingen automatisch moeten detecteren. Raadpleeg de Windows Server-documentatie voor meer informatie.
- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** in die het configuratiebestand bevat. Voer bijvoorbeeld `http://proxy.contoso.com` in.
- **Proxyserver gebruiken**: schakel deze optie in als u de proxyserverinstellingen handmatig wilt invoeren.
  - **Adres**: voer het adres van de proxyserver in (als IP-adres).
  - **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.
- **Proxy niet gebruiken voor lokale adressen**: als de VPN-server een proxyserver voor de verbinding vereist, selecteert u deze optie als u de proxyserver niet wilt gebruiken voor lokale adressen die u opgeeft. Raadpleeg de Windows Server-documentatie voor meer informatie.
