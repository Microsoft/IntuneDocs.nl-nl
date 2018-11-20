---
title: Microsoft Intune VPN-instellingen voor Windows Phone 8.1-apparaten
titleSuffix: ''
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met Windows Phone 8.1. te configureren.
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
ms.openlocfilehash: 147431f6143d1ff81e170c656c636d0bd4f3837f
ms.sourcegitcommit: dec09e9c91322ca347276785aca3c50036956f32
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2018
ms.locfileid: "51859525"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-windows-phone-81"></a>VPN-instellingen in Microsoft Intune configureren voor apparaten met Windows Phone 8.1

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op apparaten met Windows Phone 8.1. te configureren.


Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de volgende lijst worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

- **Alle instellingen alleen op Windows Phone 8.1 toepassen**: dit is een instelling die u in de klassieke Intune-portal kunt configureren. In Azure Portal kan deze instelling niet worden gewijzigd. Als de instelling is ingesteld op **Geconfigureerd**, worden instellingen alleen toegepast op Windows Phone 8.1-apparaten. Als de instelling is ingesteld op **Niet geconfigureerd**, gelden deze instellingen ook voor Windows 10 Mobile-apparaten.
- **Verbindingsnaam**: voer een naam voor deze verbinding in. Gebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server vanaf:
    - **Certificaten**: kies onder **Verificatiecertificaat** een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt om de verbinding te verifiëren. Zie [Certificaten configureren](certificates-configure.md) voor meer informatie over certificaatprofielen.
    - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.
- **Servers**: voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken.
    - **Toevoegen**: hiermee opent u de blade **Rij toevoegen** waar u de volgende informatie kunt opgeven:
        - **Beschrijving**: geef een beschrijvende naam op voor de server, zoals **Contoso VPN-server**.
        - **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
        - **Standaardserver**: hiermee wordt deze server ingeschakeld als de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
    - **Importeren**: blader naar een bestand met een kommagescheiden lijst met servers in de indelingsbeschrijving, IP-adres of FQDN, Standaardserver. Kies **OK** om deze in de lijst **Servers** te importeren.
    - **Exporteren**: hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand).

- **VPN niet gebruiken op het Wi-Fi-netwerk van het bedrijf**: selecteer deze optie om aan te geven dat de VPN-verbinding niet wordt gebruikt wanneer het apparaat is verbonden met het Wi-Fi-netwerk van het bedrijf.
- **VPN niet gebruiken op het Wi-Fi-thuisnetwerk**: selecteer deze optie om aan te geven dat de VPN-verbinding niet wordt gebruikt wanneer het apparaat is verbonden met een Wi-Fi-thuisnetwerk.

- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
    - **Check Point Capsule VPN**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Aanmeldingsgroep of -domein** (alleen SonicWall Mobile Connect): geef de naam op van de aanmeldingsgroep of het aanmeldingsdomein waarmee u verbinding wilt maken.
- **Rol** (alleen Pulse Secure): geef de naam op van de gebruikersrol die toegang tot deze verbinding heeft. Een gebruikersrol definieert persoonlijke instellingen en opties en schakelt bepaalde toegangsfuncties in of uit.
- **Realm** (alleen Pulse Secure): geef de naam op van de verificatierealm die u wilt gebruiken. Een verificatierealm is een groepering van verificatieresources die worden gebruikt door het verbindingstype Pulse Secure.

- **Zoeklijst voor DNS-achtervoegsels** - **Voeg** een of meer DNS-achtervoegsels toe. Elk DNS-achtervoegsel dat u opgeeft, wordt doorzocht wanneer met behulp van een korte naam verbinding met een website wordt gemaakt. U geeft bijvoorbeeld de DNS-achtervoegsels **domain1.contoso.com** en **domain2.contoso.com** op en gaat vervolgens naar de URL `http://mywebsite`. Vervolgens worden de URL’s `http://mywebsite.domain1.contoso.com` en `http://mywebsite.domain2.contoso.com` gezocht.

- **Aangepaste XML**: geef aangepaste XML-opdrachten op waarmee de VPN-verbinding wordt geconfigureerd.

    **Voorbeeld voor Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Voorbeeld voor CheckPoint Mobile VPN:**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Voorbeeld voor SonicWall Mobile Connect:**
```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Voorbeeld voor F5 Edge Client:**
```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Raadpleeg de VPN-documentatie van de respectievelijke fabrikanten voor meer informatie over het schrijven van aangepaste XML-opdrachten.

- **Split tunneling** - : u kunt deze optie **inschakelen** of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar het standaardnetwerk van het hotel om gewoon op het web te surfen.




## <a name="proxy-settings"></a>Proxyinstellingen

- **Automatisch proxyinstellingen detecteren**: als de VPN-server een proxyserver voor de verbinding vereist, geeft u op of apparaten de verbindingsinstellingen automatisch moeten detecteren. Raadpleeg de Windows Server-documentatie voor meer informatie.
- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.
- **Proxyserver gebruiken**: schakel deze optie in als u de proxyserverinstellingen handmatig wilt invoeren.
    - **Adres**: voer het adres van de proxyserver in (als IP-adres).
    - **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.
- **Proxy niet gebruiken voor lokale adressen**: als de VPN-server een proxyserver voor de verbinding vereist, selecteert u deze optie als u de proxyserver niet wilt gebruiken voor lokale adressen die u opgeeft. Raadpleeg de Windows Server-documentatie voor meer informatie.
