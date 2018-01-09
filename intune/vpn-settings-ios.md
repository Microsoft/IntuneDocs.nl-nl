---
title: VPN-instellingen voor iOS-apparaten in Intune
titlesuffix: Azure portal
description: Meer informatie over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op iOS-apparaten te configureren.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fe6878601f84ccf6c7296a039060b4049a17e22d
ms.sourcegitcommit: a3a744ea55f38a360ca9f788c77a5b3018d1add5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/30/2017
---
# <a name="vpn-settings-for-ios-devices-in-microsoft-intune"></a>VPN-instellingen voor iOS-apparaten in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de volgende lijst worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen


**Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: geef het IP-adres of de Fully Qualified Domain Name (FQDN) op van de VPN-server waarmee apparaten verbinding maken. Voorbeelden: **192.168.1.1**, **vpn.contoso.com**.
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server vanaf:
    - **Certificaten**: kies onder **Verificatiecertificaat** een SCEP- of PKCS-certificaatprofiel dat u eerder hebt gemaakt om de verbinding te verifiëren. Zie [Certificaten configureren](certificates-configure.md) voor meer informatie over certificaatprofielen.
    - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.
- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPSec)**
    - **Citrix**
    - **Aangepaste VPN**
- **Split tunneling** - : u kunt deze optie **inschakelen** of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar het standaardnetwerk van het hotel om gewoon op het web te surfen.


## <a name="custom-vpn-settings"></a>Basis-VPN-instellingen

Als u **Aangepaste VPN** als verbindingstype hebt geselecteerd, configureert u deze instellingen:

- **VPN-id**: dit is een id voor de VPN-app die u gebruikt en wordt geleverd door uw VPN-aanbieder.
- **Sleutel- en waardeparen voor de aangepaste VPN-kenmerken invoeren**: voeg **sleutel-** en **waardeparen** toe of importeer deze om uw VPN-verbinding aan te passen. Deze waarden worden doorgaans geleverd door uw VPN-aanbieder.

## <a name="apps-per-app-vpn-settings"></a>Apps-instellingen (VPN per app)

- **VPN per app**: schakel deze optie in als u wilt dat URL's de VPN-verbinding maken als ze vanuit de Safari-browser worden bezocht. Als u dit wilt configureren, moet u **Certificaten** als verificatiemethode hebben geselecteerd in de basis-VPN-instellingen.
- **URL's waarmee de VPN-verbinding wordt ingeschakeld terwijl u de Safari-browser gebruikt**: klik op Toevoegen om een of meer website-URL's toe te voegen. De VPN-verbinding wordt ingeschakeld als deze URL's worden bezocht.

- **On-demand regels**: hiermee kunt u voorwaardelijke regels configureren om te bepalen wanneer de VPN-verbinding wordt gestart. U kunt bijvoorbeeld een voorwaarde instellen waarmee de VPN-verbinding alleen wordt gebruikt als een apparaat niet met een van de Wi-Fi-netwerken van het bedrijf verbonden is. U kunt ook een voorwaarde instellen, dat als een apparaat geen toegang heeft tot een DNS-zoekdomein dat u opgeeft, de VPN-verbinding niet wordt gestart.

    - **SSID's of DNS-zoekdomeinen**: selecteer of voor deze voorwaarde het draadloze netwerk,  **SSID's** of **DNS-zoekdomeinen** worden gebruikt. Kies Toevoegen om een of meerdere SSID's of zoekdomeinen te configureren.
    - **URL-tekenreekstest**: (optioneel) geef een URL op die gebruikmaakt van de regel als een test. Als het apparaat waarop dit profiel is geïnstalleerd in staat is om zonder omleiding toegang tot deze URL te krijgen, wordt de VPN-verbinding tot stand gebracht en maakt het apparaat verbinding met de doel-URL. De gebruiker ziet de tekenreeks testsite voor de URL niet. Een voorbeeld van een URL-tekenreekstest is het adres van een controlewebserver die de apparaatcompatibiliteit controleert voordat u verbinding maakt met de VPN-verbinding. Een andere mogelijkheid is dat de URL de VPN-verbinding voor een site controleert, voordat het apparaat verbinding maakt met de doel-URL via de VPN-verbinding.
    - **Domeinactie**: kies een van de volgende items:
        - Verbinding maken indien nodig - 
        - Nooit verbinding - 
    - **Actie**: kies een van de volgende items:
        - Verbinden - 
        - Verbinding evalueren - 
        - Negeren - 
        - Verbinding verbreken - 


## <a name="proxy-settings"></a>Proxyinstellingen

- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld **http://proxy.contoso.com**) in die het configuratiebestand bevat.
- **Adres**: voer het adres van de proxyserver in (als IP-adres).
- **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.