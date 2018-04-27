---
title: De VPN-instellingen weergeven in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over de beschikbare VPN-instellingen in Microsoft Intune, waarvoor ze worden gebruikt en wat ze doen, zoals regels voor netwerkverkeer, voorwaardelijke toegang en DNS- en proxy-instellingen voor Windows 10-apparaten en Windows Holographic for Business-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 787501892d0955e3396bc8f37e5da8ba0d312c74
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="read-about-the-vpn-settings-in-intune"></a>Meer informatie over de VPN-instellingen in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

U kunt VPN-verbindingen configureren met Intune. In dit artikel worden deze instellingen, de regels voor netwerkverkeer, voorwaardelijke toegang en DNS- en proxy-instellingen beschreven.

Deze instellingen zijn van toepassing op:

- Apparaten met Windows 10
- Apparaten met Windows Holographic for Business

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

- **Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Servers**: voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken.
  - **Toevoegen**: hiermee opent u **Rij toevoegen** waarin u de volgende informatie kunt invoeren:
    - **Beschrijving**: voer een beschrijvende naam in voor de server, zoals **Contoso VPN-server**
    - **IP-adres of FQDN**: voer het IP-adres of de Fully Qualified Domain Name (FQDN) in van de VPN-server waarmee apparaten verbinding maken, zoals **192.168.1.1** of **vpn.contoso.com**
    - **Standaardserver**: hiermee wordt deze server ingeschakeld als de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
  - **Importeren**: blader naar een bestand met een door komma’s gescheiden lijst met servers in de indeling: beschrijving, IP-adres of FQDN, Standaardserver. Kies **OK** om deze servers in de lijst **Servers** te importeren.
  - **Exporteren**: hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand)

**Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:

- **Automatisch**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **SonicWall Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Aanmeldingsgroep of -domein** (alleen SonicWall Mobile Connect): deze eigenschap kan niet worden ingesteld in het VPN-profiel. In plaats daarvan parseert Mobile Connect deze waarde wanneer de gebruikersnaam en het domein worden ingevoerd in de indelingen `username@domain` of `DOMAIN\username`.

**Aangepaste XML**/**EAP XML**: voer aangepaste XML-opdrachten in waarmee de VPN-verbinding wordt geconfigureerd.

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

Raadpleeg de VPN-documentatie van de fabrikant voor meer informatie over het schrijven van aangepaste XML-opdrachten.

Zie [EAP-configuratie](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration) voor meer informatie over het maken van aangepaste XML-EAP.

**Split tunneling**: u kunt deze optie **inschakelen**  of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar gebruikt het standaardnetwerk van het hotel om gewoon op het web te surfen.
- **Split tunneling-routes voor deze VPN-verbinding**: voeg desgewenst routes voor VPN-providers van derden toe. Voer voor elk een bestemmingsvoorvoegsel en vaste grootte in.

## <a name="apps-and-traffic-rules"></a>Apps en verkeersregels

**VPN-verbinding beperken tot deze apps**: schakel deze instelling in als u wilt dat alleen bepaalde apps de VPN-verbinding gebruiken.

**Gekoppelde apps**: voer een lijst in met apps die automatisch gebruikmaken van de VPN-verbinding. De app-id is afhankelijk van het type app. Voer voor een universele app de naam van de productfamilie in waartoe het pakket behoort. Voer voor een bureaublad-app het bestandspad van de app in.

>[!IMPORTANT]
>Het is raadzaam dat u alle app-lijsten beveiligt die zijn gemaakt voor VPN’s per app. Als een ongeautoriseerde gebruiker deze lijst wijzigt en u deze importeert in de app-lijst VPN per app, verleent u onbevoegde gebruikers mogelijk VPN-toegang tot apps die niet toegankelijk zouden moeten zijn. Een manier om uw lijsten met apps te beveiligen, is het gebruik van een toegangsbeheerlijst (ACL).

**Regels voor netwerkverkeer voor deze VPN-verbinding**: selecteer welke protocollen en welke lokale en externe poort- en adresbereiken voor de VPN-verbinding worden ingeschakeld. Als u geen netwerkverkeersregel maakt, worden alle protocollen, poorten en adresbereiken ingeschakeld. Nadat u een regel hebt gemaakt, worden door de VPN-verbinding alleen de protocollen, poorten en adresbereiken gebruikt die u in die regel invoert.

## <a name="conditional-access"></a>Voorwaardelijke toegang

**Voorwaardelijke toegang voor deze VPN-verbinding**: schakelt een nalevingsstroom voor het apparaat in via de client. Als deze is ingeschakeld, probeert de VPN-client te communiceren met Azure Active Directory om een certificaat te ontvangen dat voor verificatie kan worden gebruikt. De VPN moet worden ingesteld voor het gebruik van certificaatverificatie. Ook moet de VPN-server de server die door Azure Active Directory wordt geretourneerd vertrouwen.

**Eenmalige aanmelding (SSO) met alternatief certificaat**: gebruik voor apparaatcompatibiliteit een ander certificaat dan het VPN-verificatiecertificaat voor Kerberos-verificatie. Voer de volgende instellingen in voor het certificaat:

- **Uitgebreid sleutelgebruik**: naam voor het uitgebreide sleutelgebruik (EKU)
- **Object-id**: object-id voor EKU
- **Hash voor de verlener**: vingerafdruk van certificaat voor eenmalige aanmelding

## <a name="dns-settings"></a>DNS-instellingen

**DNS-namen en servers voor deze VPN-verbinding**: selecteer welke DNS-servers de VPN-verbinding gebruiken nadat de verbinding tot stand is gebracht.
Voer voor elke server het volgende in:
- **DNS-naam**
- **DNS-server**
- **Proxy**

## <a name="proxy-settings"></a>Proxyinstellingen

- **Automatisch proxyinstellingen detecteren**: als de VPN-server een proxyserver voor de verbinding vereist, kiest u of apparaten de verbindingsinstellingen automatisch moeten detecteren.
- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van proxyserver** in, zoals `http://proxy.contoso.com`, die het configuratiebestand bevat.
- **Proxyserver gebruiken**: schakel deze optie om de proxyserverinstellingen handmatig in te voeren.
  - **Adres**: voer het adres van de proxyserver in (als IP-adres)
  - **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver
- **Proxy niet gebruiken voor lokale adressen**: als de VPN-server een proxyserver voor de verbinding vereist, selecteert u deze instelling als u de proxyserver niet wilt gebruiken voor lokale adressen die u invoert.
