---
title: VPN-instellingen toevoegen aan iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Voeg een VPN-configuratieprofiel toe of maak er een met configuratie-instellingen voor virtuele privénetwerken (VPN), inclusief de verbindingsgegevens, verificatiemethode en split tunneling in de basisinstellingen; de aangepaste VPN-instellingen met de id, en de paren van sleutels en waarden; de VPN-instellingen per app met inbegrip van Safari-URL's, en on-demand VPN's met SSID's of DNS-zoekdomeinen; en de proxy-instellingen die deel moeten uitmaken van een configuratiescript, IP- of FQDN-adres, en TCP-poort in Microsoft Intune op apparaten waarop iOS wordt uitgevoerd.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 23e993f883b149e86ce83e0e028572f55468b84b
ms.sourcegitcommit: be6f6b750635ebc7956dd2d60a0e131d124b2fc3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2018
ms.locfileid: "51947306"
---
# <a name="configure-vpn-settings-on-ios-devices-in-microsoft-intune"></a>VPN-instellingen voor iOS-apparaten configureren in Microsoft Intune

Microsoft Intune biedt veel VPN-instellingen die kunnen worden geïmplementeerd op uw iOS-apparaten. Deze instellingen worden gebruikt om VPN-verbindingen te maken en configureren voor het netwerk van uw organisatie. In dit artikel worden deze instellingen beschreven. Sommige instellingen zijn alleen beschikbaar voor sommige VPN-clients, zoals Citrix en Zscaler.

## <a name="connection-type"></a>Type verbinding

Selecteer het type VPN-verbinding in de volgende lijst met leveranciers:

- **Check Point Capsule VPN**
- **Cisco Legacy AnyConnect**: dit is van toepassing op de app [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) versie 4.0.5x en eerder.
- **Cisco AnyConnect**: dit is van toepassing op de app [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) versie 4.0.7x en later.
- **SonicWall Mobile Connect**
- **F5 Access Legacy**: dit is van toepassing op de app F5 Access versie 2.1 en eerder.
- **F5 Access**: dit is van toepassing op de app F5 Access versie 3.0 en later.
- **Palo Alto Networks GlobalProtect (verouderd)**: dit is van toepassing op de app Palo Alto Networks GlobalProtect versie 4.1 en eerder.
- **Palo Alto Networks GlobalProtect**: dit is van toepassing op de app Palo Alto Networks GlobalProtect versie 5.0 en later.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: hiervoor moet u Zscaler Private Access (ZPA) integreren met uw Azure AD-account. Zie de [Zscaler documentatie](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO) voor gedetailleerde instructies. 
- **Aangepaste VPN**

> [!NOTE]
> Cisco, Citrix, F5 en Palo Alto hebben aangekondigd dat hun verouderde clients niet werken in iOS 12. U moet zo snel mogelijk migreren naar de nieuwe apps. Zie de [blog van het Microsoft Intune-ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409) voor meer informatie.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

Welke instellingen in de volgende lijst worden weergegeven, is afhankelijk van het VPN-verbindingstype dat u selecteert.  

- **Verbindingsnaam**: eindgebruikers zien deze naam wanneer ze op hun apparaat in een lijst met beschikbare VPN-verbindingen zoeken.
- **Aangepaste domeinnaam** (alleen Zscaler): hiermee vullen u het aanmeldveld van de Zscaler-app vooraf in met het domein waarvan uw gebruikers deel uitmaken. Als bijvoorbeeld de gebruikersnaam `Joe@contoso.net` is, wordt het domein `contoso.net` statisch in het veld weergegeven wanneer de app wordt geopend. Als u geen domeinnaam invoert, wordt het domeingedeelte van de UPN in Azure Active Directory (AD) gebruikt.
- **IP-adres of FQDN**: dit is het IP-adres of de FQDN (Fully Qualified Domain Name) van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld `192.168.1.1` of `vpn.contoso.com` in.
- **Cloudnaam van organisatie** (alleen Zscaler): voer de naam in van de cloud waarin uw organisatie is ingericht. De URL waarmee u zich aanmeldt bij Zscaler bevat de naam.  
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. 
  - **Certificaten**: selecteer onder **Verificatiecertificaat** een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](certificates-configure.md) bevat enkele richtlijnen voor certificaatprofielen.
  - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.  

    > [!NOTE]
    > Als gebruikersnaam en wachtwoord worden gebruikt als verificatiemethode voor Cisco IPsec VPN, moeten deze het SharedSecret bieden via een aangepast profiel voor de Apple Configurator.

- **Uitgesloten URL's** (alleen Zscaler): wanneer u verbonden bent met het VPN van Zscaler, zijn de vermelde URL's toegankelijk buiten de Zscaler-cloud. 

- **Split tunneling**: u kunt deze optie **inschakelen**  of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar gebruikt het standaardnetwerk van het hotel om gewoon op het web te surfen.

- **VPN-id** (aangepaste VPN, Zscaler en Citrix): dit is een id voor de VPN-app die u gebruikt en wordt geleverd door uw VPN-provider.
  - **Sleutel-/waardeparen voor de aangepaste VPN-kenmerken van uw organisatie invoeren**: voeg **sleutel-** en **waardeparen** toe of importeer deze om uw VPN-verbinding aan te passen. Deze waarden worden doorgaans aangeleverd door uw VPN-provider.

- **Netwerktoegangsbeheer (NAC) inschakelen** (alleen voor Citrix SSO): wanneer u **Ik ga akkoord** selecteert, wordt de apparaat-id opgenomen in het VPN-profiel. Deze id kan worden gebruikt voor verificatie bij de VPN om netwerktoegang toe te staan of te voorkomen.

  **Wanneer u Citrix SSO met Gateway gebruikt**, moet u ervoor zorgen dat:

  - U Citrix Gateway 12.0.59 of hoger gebruikt.
  - Uw gebruikers Citrix SSO 1.1.6 of hoger hebben geïnstalleerd op hun apparaten.
  - Citrix Gateway met Intune voor NAC is geïntegreerd, zoals staat beschreven in de Citrix-implementatiegids [Integrating Microsoft Intune/Enterprise Mobility Suite with NetScaler (LDAP+OTP Scenario)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf).
  - NAC is ingeschakeld in het VPN-profiel.

  Belangrijke informatie:  

  - Als NAC wordt ingeschakeld, wordt de verbinding met de VPN elke 24 uur verbroken.
  - De apparaat-id maakt deel uit van het profiel, maar is niet zichtbaar in Intune. De id wordt nergens door Microsoft opgeslagen en wordt niet door Microsoft gedeeld. Zodra dit wordt ondersteund door VPN-partners, kunnen de VPN-clients, zoals Citrix SSO, de id ontvangen en bij Intune opvragen of het apparaat is ingeschreven en of het VPN-profiel wel of niet voldoet aan de vereisten.
  - Als u deze instelling wilt verwijderen, maakt u het profiel opnieuw en selecteert u de optie **Ik ga akkoord** niet. Wijs het profiel vervolgens opnieuw toe.

## <a name="automatic-vpn-settings"></a>Automatische VPN-instellingen

- **VPN per app**: hiermee schakelt u VPN per app in. Er kan dan automatisch een VPN-verbinding worden gemaakt wanneer bepaalde apps worden geopend. U kunt ook apps koppelen aan het VPN-profiel. Voor meer informatie ziet u de [instructies voor het instellen van VPN per app voor iOS](vpn-setting-configure-per-app.md).
  - **Providertype**: alleen beschikbaar voor Pulse Secure en aangepaste VPN.
  - Wanneer u in iOS **VPN-profielen voor individuele apps** gebruikt met Pulse Secure en een aangepaste VPN, kiest u voor tunnels op app-niveau (app-proxy) of op pakketniveau (pakkettunnel). Stel de waarde **ProviderType** in op **app-proxy** voor tunneling op app-niveau of **pakkettunnel** voor tunneling op pakketniveau. Als u niet zeker weet welke waarde u moet gebruiken, bekijkt u de documentatie van uw VPN-provider.
  - **Safari-URL's die deze VPN activeren**: voeg een of meer website-URL's toe. Wanneer deze URL's worden bezocht via de Safari-browser op het apparaat, wordt er automatisch een VPN-verbinding ingesteld.

- **On-demand VPN**: configureer voorwaardelijke regels om te bepalen wanneer de VPN-verbinding wordt gestart. Stel bijvoorbeeld een voorwaarde in waarmee de VPN-verbinding alleen wordt gebruikt als een apparaat niet met een Wi-Fi-netwerk van het bedrijf is verbonden. U kunt ook de voorwaarde instellen dat de VPN-verbinding niet wordt gestart als een apparaat geen toegang heeft tot een DNS-zoekdomein dat u opgeeft.

  - **SSID's of DNS-zoekdomeinen**: selecteer of voor deze voorwaarde het draadloze netwerk,  **SSID's** of **DNS-zoekdomeinen** worden gebruikt. Kies **Toevoegen** om een of meerdere SSID's of zoekdomeinen te configureren.
  - **URL-tekenreekstest**: optioneel. Voer een URL die door de regel als een test wordt gebruikt. Als het apparaat met dit profiel toegang wilt verkrijgen tot deze URL (zonder omleiding), wordt er een VPN-verbinding gemaakt. Het apparaat maakt dan verbinding met de doel-URL. De gebruiker ziet de tekenreekstestsite voor de URL niet. Een voorbeeld van een URL-tekenreekstest is het adres van een controlewebserver die de apparaatcompatibiliteit controleert voordat u verbinding maakt met de VPN-verbinding. Een andere mogelijkheid is dat de URL de VPN-verbinding voor een site controleert, voordat het apparaat verbinding maakt met de doel-URL via de VPN-verbinding.
  - **Domeinactie**: kies een van de volgende items:
    - Verbinding maken indien nodig
    - Nooit verbinding maken
  - **Actie**: kies een van de volgende items:
    - Verbinden
    - Verbinding evalueren
    - Negeren
    - Verbinding verbreken

## <a name="proxy-settings"></a>Proxyinstellingen

Als u een proxy gebruikt, configureert u de volgende instellingen. Proxyinstellingen zijn niet beschikbaar voor VPN-verbindingen van Zscaler.  

- **Script voor automatische configuratie**: gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.
- **Adres**: voer het IP-adres van de volledig gekwalificeerde hostnaam van de proxyserver in.
- **Poortnummer**: voer het poortnummer in dat is gekoppeld aan de proxyserver.

## <a name="next-step"></a>Volgende stap
[VPN-profielen maken in Intune](vpn-settings-configure.md)  
