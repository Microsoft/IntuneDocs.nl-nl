---
title: Intune VPN-instellingen voor Windows 10-apparaten
titlesuffix: Azure portal
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op Windows 10-apparaten te configureren.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6de18a341f684730c74aa824c0ae8f7bdca1a4f8
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/02/2017
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>VPN-instellingen voor Windows 10-apparaten in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de onderstaande lijst worden geconfigureerd.


## <a name="base-vpn-settings"></a>Basis-VPN-instellingen


- **Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers kunnen deze naam zien wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Servers**: voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken.
    - **Toevoegen**: hiermee opent u de blade **Rij toevoegen** waar u de volgende informatie kunt opgeven:
        - **Beschrijving**: geef een beschrijvende naam op voor de server, zoals **Contoso VPN-server**.
        - **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
        - **Standaardserver**: hiermee wordt deze server ingeschakeld als de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
    - **Importeren**: blader naar een bestand met een kommagescheiden lijst met servers in de indelingsbeschrijving, IP-adres of FQDN, Standaardserver. Kies **OK** om deze in de lijst **Servers** te importeren.
    - **Exporteren**: hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand).

**Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
- **Automatisch**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**


**Aanmeldingsgroep of -domein** (alleen Dell SonicWALL Mobile Connect): geef de naam op van de aanmeldingsgroep of het aanmeldingsdomein waarmee u verbinding wilt maken.

**Aangepaste XML**/**EAP XML**: geef aangepaste XML-opdrachten op waarmee de VPN-verbinding wordt geconfigureerd.

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

**Split tunneling** - U kunt deze optie **inschakelen** of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Bijvoorbeeld: een gebruiker in een hotel gebruikt de VPN-verbinding voor werkbestanden, maar het standaardnetwerk van het hotel om gewoon op het web te surfen.
- **Split tunneling-routes voor deze VPN-verbinding**: voeg desgewenst routes voor VPN-providers van derden toe. Geef voor elk een bestemmingsvoorvoegsel en vaste grootte op.

## <a name="apps-and-traffic-rules"></a>Apps en verkeersregels

**VPN-verbinding beperken tot deze apps**: schakel deze optie in als alleen apps die u opgeeft, de VPN-verbinding mogen gebruiken.
**Gekoppelde apps**: geef een lijst op met apps die automatisch gebruikmaken van de VPN-verbinding. De app-id is afhankelijk van het type app. Geef voor een universele app de naam van de productfamilie op waartoe het pakket behoort. Geef voor een bureaublad-app het bestandspad van de app op.

>[!IMPORTANT]
>Het is raadzaam dat u alle lijsten met apps die u compileert voor gebruik in de configuratie van per-app VPN, beveiligt. Als een ongeautoriseerde gebruiker uw lijst wijzigt en u deze importeert in de app-lijst VPN per app, verleent u onbevoegde gebruikers mogelijk VPN-toegang tot apps die niet toegankelijk zouden moeten zijn. Een manier om uw lijsten met apps te beveiligen, is het gebruik van een toegangsbeheerlijst (ACL).

**Regels voor netwerkverkeer voor deze VPN-verbinding**: selecteer welke protocollen en welke lokale en externe poort- en adresbereiken voor de VPN-verbinding worden ingeschakeld. Als u geen netwerkverkeersregel maakt, worden alle protocollen, poorten en adresbereiken ingeschakeld. Nadat u een regel hebt gemaakt, worden door de VPN-verbinding alleen de protocollen, poorten en adresbereiken gebruikt die u in die regel opgeeft.


## <a name="conditional-access"></a>Voorwaardelijke toegang

**Voorwaardelijke toegang voor deze VPN-verbinding**: schakelt een nalevingsstroom voor het apparaat in via de client. Als deze is ingeschakeld, zal de VPN-client proberen te communiceren met Azure Active Directory om een certificaat te ontvangen dat voor verificatie kan worden gebruikt. De VPN moet worden ingesteld voor het gebruik van certificaatverificatie. Ook moet de VPN-server de server die door Azure Active Directory wordt geretourneerd vertrouwen.

**Eenmalige aanmelding (SSO) met alternatief certificaat**: gebruik voor apparaatcompatibiliteit een ander certificaat dan het VPN-verificatiecertificaat voor Kerberos-verificatie. Geef de volgende instellingen op voor het certificaat: 

- **Uitgebreid sleutelgebruik**: naam voor het uitgebreide sleutelgebruik (EKU).
- **Object-id**: object-id voor EKU.
- **Hash voor de verlener**: vingerafdruk van certificaat voor eenmalige aanmelding.

## <a name="dns-settings"></a>DNS-instellingen

**DNS-namen en servers voor deze VPN-verbinding**: selecteer welke DNS-servers de VPN-verbinding gebruiken nadat de verbinding tot stand is gebracht.
Voor elke server. geef op:
- **DNS-naam**
- **DNS-server**
- **Proxy**

## <a name="proxy-settings"></a>Proxyinstellingen

- **Automatisch proxyinstellingen detecteren**: als de VPN-server een proxyserver voor de verbinding vereist, geeft u op of apparaten de verbindingsinstellingen automatisch moeten detecteren. Raadpleeg de Windows Server-documentatie voor meer informatie.
- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld **http://proxy.contoso.com**) in die het configuratiebestand bevat.
- **Proxyserver gebruiken**: schakel deze optie in als u de proxyserverinstellingen handmatig wilt invoeren.
    - **Adres**: voer het adres van de proxyserver in (als IP-adres).
    - **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.
- **Proxy niet gebruiken voor lokale adressen**: als de VPN-server een proxyserver voor de verbinding vereist, selecteert u deze optie als u de proxyserver niet wilt gebruiken voor lokale adressen die u opgeeft. Raadpleeg de Windows Server-documentatie voor meer informatie.
