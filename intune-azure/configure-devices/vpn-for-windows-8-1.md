---
title: VPN-instellingen voor Windows 8.1-apparaten
titleSuffix: Intune Azure preview
description: 'Intune Azure Preview: meer informatie over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op Windows 8.1-apparaten te configureren.'
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: f38526a3e60f2a6628e61ffca5f5d179a2718e9b
ms.lasthandoff: 02/18/2017


---

# <a name="vpn-settings-for-windows-81-devices-in-microsoft-intune"></a>VPN-instellingen voor Windows 8.1-apparaten in Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de onderstaande lijst worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen


- **Alle instellingen alleen op Windows 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, zijn de instellingen alleen van toepassing op Windows 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10-apparaten.
- **Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers kunnen deze naam zien wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Servers**: voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken.
    - **Toevoegen**: hiermee opent u de blade **Rij toevoegen** waar u de volgende informatie kunt opgeven:
        - **Beschrijving**: geef een beschrijvende naam op voor de server, zoals **Contoso VPN-server**.
        - **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
        - **Standaardserver**: hiermee wordt deze server de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
    - **Importeren**: blader naar een bestand met een kommagescheiden lijst met servers in de indelingsbeschrijving, IP-adres of FQDN, Standaardserver. Kies **OK** om deze in de lijst **Servers** te importeren.
    - **Exporteren**: hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand).

- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
- **Check Point Capsule VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **Pulse Secure**

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- **Aanmeldingsgroep of -domein** (alleen Dell SonicWALL Mobile Connect): geef de naam op van de aanmeldingsgroep of het aanmeldingsdomein waarmee u verbinding wilt maken.

- **Rol** (alleen Pulse Secure): geef de naam op van de gebruikersrol die toegang tot deze verbinding heeft. Een gebruikersrol definieert persoonlijke instellingen en opties en schakelt bepaalde toegangsfuncties in of uit.

- **Realm** (alleen Pulse Secure): geef de naam op van de verificatierealm die u wilt gebruiken. Een verificatierealm is een groepering van verificatieresources die worden gebruikt door het verbindingstype Pulse Secure.


- **Aangepaste XML**: geef aangepaste XML-opdrachten op waarmee de VPN-verbinding wordt geconfigureerd.

**Voorbeeld voor Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

**Voorbeeld voor CheckPoint Mobile VPN:**
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />

```

**Voorbeeld voor Dell SonicWALL Mobile Connect:**
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

**Voorbeeld voor F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

Raadpleeg de VPN-documentatie van de respectievelijke fabrikanten voor meer informatie over het schrijven van aangepaste XML-opdrachten.


## <a name="proxy-settings"></a>Proxyinstellingen

- **Automatisch proxyinstellingen detecteren**: als de VPN-server een proxyserver voor de verbinding vereist, geeft u op of apparaten de verbindingsinstellingen automatisch moeten detecteren. Raadpleeg de Windows Server-documentatie voor meer informatie.
- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL in van de proxyserver** (bijvoorbeeld **http://proxy.contoso.com**) die het configuratiebestand bevat.
- **Proxyserver gebruiken**: schakel deze optie in als u de proxyserverinstellingen handmatig wilt invoeren.
    - **Adres**: voer het adres van de proxyserver in (als IP-adres).
    - **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.
- **Proxy niet gebruiken voor lokale adressen**: als de VPN-server een proxyserver voor de verbinding vereist, selecteert u deze optie als u de proxyserver niet wilt gebruiken voor lokale adressen die u opgeeft. Raadpleeg de Windows Server-documentatie voor meer informatie.

