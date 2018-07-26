---
title: VPN-instellingen voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk de beschikbare configuratie-instellingen voor virtuele privénetwerken (VPN), inclusief de verbindingsgegevens, verificatiemethode en split tunneling in de basisinstellingen; de aangepaste VPN-instellingen met de id, en de paren van sleutels en waarden; de VPN-instellingen per app met inbegrip van Safari-URL's, en on-demand VPN's met SSID's of DNS-zoekdomeinen; en de proxy-instellingen die deel moeten uitmaken van een configuratiescript, IP- of FQDN-adres, en TCP-poort in Microsoft Intune op apparaten waarop iOS wordt uitgevoerd.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d35c9e32b7a0720d5d84a93a7edde6f2bd51911f
ms.sourcegitcommit: 08e1b0d45c84eb9525a0a59f5540d41434da2814
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39146625"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>VPN-instellingen in Microsoft Intune configureren voor iOS-apparaten

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In dit artikel leest u meer over de Intune-instellingen die u kunt gebruiken om VPN-verbindingen op iOS-apparaten te configureren.

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden in de volgende lijst worden geconfigureerd.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

- **Verbindingsnaam**: voer een naam voor deze verbinding in. Eindgebruikers zien deze naam wanneer ze op hun apparaat in een lijst met beschikbare VPN-verbindingen zoeken.
- **IP-adres of FQDN**: geef het IP-adres of de FQDN (Fully Qualified Domain Name) op van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld **192.168.1.1** of **vpn.contoso.com** in.
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server vanaf:
  - **Certificaten**: selecteer onder **Verificatiecertificaat** een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](certificates-configure.md) bevat enkele richtlijnen voor certificaatprofielen.
  - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.

    > [!NOTE]
    > Als gebruikersnaam en wachtwoord worden gebruikt als verificatiemethode voor Cisco IPsec VPN, moeten deze het SharedSecret bieden via een aangepast profiel voor de Apple Configurator.
  
- **Verbindingstype**: selecteer het type VPN-verbinding in de volgende lijst met leveranciers:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **Cisco Legacy AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Palo Alto Networks GlobalProtect**
  - **Pulse Secure**
  - **Cisco (IPSec)**
  - **Citrix**
  - **Aangepaste VPN**

    > [!NOTE]
    > - **Cisco Legacy AnyConnect VPN**-profielen zijn voor de [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924)-app-versie 4.0.5x en oudere versies
    > - **Cisco AnyConnect VPN**-profielen zijn voor de [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690)-app-versie 4.0.7x en nieuwere versies

- **Split tunneling**: u kunt deze optie **inschakelen**  of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar gebruikt het standaardnetwerk van het hotel om gewoon op het web te surfen.

## <a name="custom-vpn-settings"></a>Basis-VPN-instellingen

Als u **Aangepaste VPN** als verbindingstype hebt geselecteerd, configureert u ook de volgende instellingen:

- **VPN-id**: dit is een id voor de VPN-app die u gebruikt en wordt geleverd door uw VPN-provider.
- **Sleutel- en waardeparen voor de aangepaste VPN-kenmerken invoeren**: voeg **sleutel-** en **waardeparen** toe of importeer deze om uw VPN-verbinding aan te passen. Deze waarden worden doorgaans geleverd door uw VPN-aanbieder.

## <a name="automatic-vpn-settings"></a>Automatische VPN-instellingen

- **VPN per app**: als u deze optie kiest, wordt VPN per app ingeschakeld. Hiermee kan de VPN-verbinding automatisch worden ingeschakeld wanneer bepaalde apps worden geopend. Als u deze optie kiest, moet u de desbetreffende apps ook aan het VPN-profiel koppelen. Voor meer informatie ziet u de [instructies voor het instellen van 'VPN per app' voor iOS](vpn-setting-configure-per-app.md). 
  - **Safari-URL's die deze VPN activeren**: selecteer een of meer website-URL's om toe te voegen. Wanneer deze URL's worden bezocht via de Safari-browser op het apparaat, wordt er automatisch een VPN-verbinding ingesteld.

- **On-demand VPN**: configureer voorwaardelijke regels om te bepalen wanneer de VPN-verbinding wordt gestart. Stel bijvoorbeeld een voorwaarde in waarmee de VPN-verbinding alleen wordt gebruikt als een apparaat niet met een Wi-Fi-netwerk van het bedrijf is verbonden. U kunt ook een voorwaarde instellen dat de VPN-verbinding niet wordt gestart als een apparaat geen toegang heeft tot een DNS-zoekdomein dat u opgeeft.

  - **SSID's of DNS-zoekdomeinen**: selecteer of voor deze voorwaarde het draadloze netwerk,  **SSID's** of **DNS-zoekdomeinen** worden gebruikt. Kies **Toevoegen** om een of meerdere SSID's of zoekdomeinen te configureren.
  - **URL-tekenreekstest**: optioneel. Voer een URL die door de regel als een test wordt gebruikt. Als het apparaat waarop dit profiel is geïnstalleerd in staat is om zonder omleiding toegang tot deze URL te krijgen, wordt de VPN-verbinding tot stand gebracht en maakt het apparaat verbinding met de doel-URL. De gebruiker ziet de tekenreeks testsite voor de URL niet. Een voorbeeld van een URL-tekenreekstest is het adres van een controlewebserver die de apparaatcompatibiliteit controleert voordat u verbinding maakt met de VPN-verbinding. Een andere mogelijkheid is dat de URL de VPN-verbinding voor een site controleert, voordat het apparaat verbinding maakt met de doel-URL via de VPN-verbinding.
  - **Domeinactie**: kies een van de volgende items:
    - Verbinding maken indien nodig
    - Nooit verbinding maken
  - **Actie**: kies een van de volgende items:
    - Verbinden
    - Verbinding evalueren
    - Negeren
    - Verbinding verbreken

## <a name="proxy-settings"></a>Proxyinstellingen

- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld **http://proxy.contoso.com**) in die het configuratiebestand bevat.
- **Adres**: voer het IP-adres van de volledig gekwalificeerde hostnaam van de proxyserver in.
- **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.

## <a name="next-step"></a>Volgende stap
[VPN-profielen maken in Intune](vpn-settings-configure.md)
