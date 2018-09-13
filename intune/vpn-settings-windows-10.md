---
title: De VPN-instellingen voor Windows 10 configureren in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over de beschikbare VPN-instellingen in Microsoft Intune, waarvoor ze worden gebruikt en wat ze doen, zoals regels voor netwerkverkeer, voorwaardelijke toegang en DNS- en proxy-instellingen voor Windows 10-apparaten en Windows Holographic for Business-apparaten.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 0b064c6f0eaa67157c5c50ddad3a8fd863295b8b
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43312847"
---
# <a name="windows-10-vpn-settings-in-intune"></a>VPN-instellingen voor Windows 10 in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

U kunt VPN-verbindingen configureren met Intune. In dit artikel worden deze instellingen, de regels voor netwerkverkeer, voorwaardelijke toegang en DNS- en proxy-instellingen beschreven.

Deze instellingen zijn van toepassing op:

- Apparaten met Windows 10
- Apparaten met Windows Holographic for Business

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

- **Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Servers**: voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken. Als u een server toevoegt, voert u de volgende gegevens in:
  - **Beschrijving**: voer een beschrijvende naam in voor de server, zoals **Contoso VPN-server**
  - **IP-adres of FQDN**: voer het IP-adres of de Fully Qualified Domain Name (FQDN) in van de VPN-server waarmee apparaten verbinding maken, zoals **192.168.1.1** of **vpn.contoso.com**
  - **Standaardserver**: hiermee wordt deze server ingeschakeld als de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
  - **Importeren**: blader naar een bestand met een door komma’s gescheiden lijst met servers in de indeling: beschrijving, IP-adres of FQDN, Standaardserver. Kies **OK** om deze servers te importeren in de lijst met **servers**.
  - **Exporteren**: hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand)

- **IP-adressen met interne DNS registreren**: selecteer **Inschakelen** als u het VPN-profiel van Windows 10 zo wilt configureren dat de IP-adressen die zijn toegewezen aan de VPN-interface met de interne DNS dynamisch worden geregistreerd, of selecteer  **Uitschakelen** als u de IP-adressen niet dynamisch wilt registreren.

- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWall Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Palo Alto Networks GlobalProtect**
  - **Automatisch**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  Als u een VPN-verbindingstype kiest, wordt u mogelijk ook om de volgende instellingen gevraagd:  
    - **Altijd aan**: schakel deze optie in om automatisch verbinding te maken met de VPN-verbinding wanneer het volgende gebeurt: 
      - Gebruikers zich aanmelden op hun apparaten
      - Het netwerk op het apparaat wijzigt
      - Het scherm op het apparaat wordt ingeschakeld nadat het was uitgeschakeld 

    - **Verificatiemethode**: selecteer hoe gebruikers zich moeten verifiëren bij de VPN-server. Het gebruik van **certificaten** biedt uitgebreide mogelijkheden, zoals zero-touch, VPN op aanvraag en VPN per app.
    - **Referenties onthouden bij elke aanmelding**: kies ervoor om de verificatiereferenties in cache te plaatsen.
    - **Aangepaste XML**: voer aangepaste XML-opdrachten in waarmee de VPN-verbinding wordt geconfigureerd.
    - **EAP XML**: voer EAP XML-opdrachten in waarmee de VPN-verbinding wordt geconfigureerd

#### <a name="pulse-secure-example"></a>Voorbeeld van Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### <a name="f5-edge-client-example"></a>Voorbeeld van F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### <a name="sonicwall-mobile-connect-example"></a>Voorbeeld van SonicWALL Mobile Connect
**Aanmeldingsgroep of -domein**: deze eigenschap kan niet worden ingesteld in het VPN-profiel. In plaats daarvan parseert Mobile Connect deze waarde wanneer de gebruikersnaam en het domein worden ingevoerd in de indelingen `username@domain` of `DOMAIN\username`.

Voorbeeld:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

#### <a name="checkpoint-mobile-vpn-example"></a>Voorbeeld van CheckPoint Mobile VPN

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

#### <a name="writing-custom-xml"></a>Aangepaste XML schrijven
Raadpleeg de VPN-documentatie van de fabrikant voor meer informatie over het schrijven van aangepaste XML-opdrachten.

Zie [EAP-configuratie](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration) voor meer informatie over het maken van aangepaste XML-EAP.

## <a name="apps-and-traffic-rules"></a>Apps en verkeersregels

- **WIP of apps koppelen aan deze VPN**: schakel deze instelling in als u wilt dat alleen bepaalde apps de VPN-verbinding gebruiken. Uw opties zijn:

  - **Een WIP koppelen aan deze verbinding**: voer een **WIP-domein in voor deze verbinding**
  - **Apps koppelen met deze verbinding**: u kunt **een VPN-verbinding beperken tot deze apps** en vervolgens deze **gekoppelde apps** toevoegen. De apps die u invoert, maken automatisch gebruik van de VPN-verbinding. De app-id is afhankelijk van het type app. Voer voor een universele app de naam van de productfamilie in waartoe het pakket behoort. Voer voor een bureaublad-app het bestandspad van de app in.
  >[!IMPORTANT]
  >Het is raadzaam dat u alle app-lijsten beveiligt die zijn gemaakt voor VPN’s per app. Als een ongeautoriseerde gebruiker deze lijst wijzigt en u deze importeert in de app-lijst VPN per app, verleent u onbevoegde gebruikers mogelijk VPN-toegang tot apps die niet toegankelijk zouden moeten zijn. Een manier om uw lijsten met apps te beveiligen, is het gebruik van een toegangsbeheerlijst (ACL).

- **Regels voor netwerkverkeer voor deze VPN-verbinding**: selecteer welke protocollen en welke lokale en externe poort- en adresbereiken voor de VPN-verbinding worden ingeschakeld. Als u geen netwerkverkeersregel maakt, worden alle protocollen, poorten en adresbereiken ingeschakeld. Nadat u een regel hebt gemaakt, worden door de VPN-verbinding alleen de protocollen, poorten en adresbereiken gebruikt die u in die regel invoert.

## <a name="conditional-access"></a>Voorwaardelijke toegang

- **Voorwaardelijke toegang voor deze VPN-verbinding**: schakelt een nalevingsstroom voor het apparaat in via de client. Als de VPN-client is ingeschakeld, wordt er een poging gedaan deze te laten communiceren met Azure AD (Active Directory) en een certificaat te ontvangen dat kan worden gebruikt voor verificatie. De VPN moet zijn ingesteld voor het gebruik van certificaatverificatie. Ook moet de VPN-server de server vertrouwen die met Azure AD wordt geretourneerd.

- **Eenmalige aanmelding (SSO) met alternatief certificaat**: gebruik voor apparaatcompatibiliteit een ander certificaat dan het VPN-verificatiecertificaat voor Kerberos-verificatie. Voer de volgende instellingen in voor het certificaat:

  - **Naam**: naam voor EKU (uitgebreide-sleutelgebruik)
  - **Object-id**: object-id voor EKU
  - **Hash voor de verlener**: vingerafdruk van certificaat voor eenmalige aanmelding

## <a name="dns-settings"></a>DNS-instellingen

**Domein en servers voor deze VP-verbinding**: voeg domeinen en DNS-server toe waarvan de VPN gebruik kan maken. U kunt kiezen van welke DNS-servers de VPN-verbinding gebruikmaakt nadat de verbinding tot stand is gebracht. Voer voor elke server het volgende in:
- **Domein**
- **DNS-server**
- **Proxy**

## <a name="proxy-settings"></a>Proxyinstellingen

- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van proxyserver** in, zoals `http://proxy.contoso.com`, die het configuratiebestand bevat.
- **Adres**: voer het adres van de proxyserver in, zoals een IP-adres of `vpn.contoso.com`
- **Poortnummer**: voer het TCP-poortnummer in dat wordt gebruikt voor uw proxyserver
- **Proxy overslaan voor lokale adressen**: als u geen proxyserver wilt gebruiken voor lokale adressen, kiest u Inschakelen. Deze instelling is van toepassing als voor de VPN-server een proxyserver is vereist voor de verbinding.

## <a name="split-tunneling"></a>Split tunneling

- **Split tunneling**: u kunt deze optie **inschakelen**  of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar gebruikt het standaardnetwerk van het hotel om gewoon op het web te surfen.
- **Split tunneling-routes voor deze VPN-verbinding**: voeg desgewenst routes voor VPN-providers van derden toe. Voer voor elke verbinding een bestemmingsvoorvoegsel en voorvoegselgrootte in.
