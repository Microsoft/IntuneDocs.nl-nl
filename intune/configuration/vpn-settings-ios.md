---
title: VPN-instellingen configureren voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Voeg een VPN-configuratieprofiel toe of maak er een met configuratie-instellingen voor virtuele privénetwerken (VPN), inclusief de verbindingsgegevens, verificatiemethode en split tunneling in de basisinstellingen; de aangepaste VPN-instellingen met de id, en de paren van sleutels en waarden; de VPN-instellingen per app met inbegrip van Safari-URL's, en on-demand VPN's met SSID's of DNS-zoekdomeinen; en de proxy-instellingen die deel moeten uitmaken van een configuratiescript, IP- of FQDN-adres, en TCP-poort in Microsoft Intune op apparaten waarop iOS wordt uitgevoerd.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 52fb1ea5077b424a1d3cf10812d8d9b5f79e4752
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059803"
---
# <a name="add-vpn-settings-on-ios-devices-in-microsoft-intune"></a>VPN-instellingen toevoegen aan iOS-apparaten in Microsoft Intune

Microsoft Intune biedt veel VPN-instellingen die kunnen worden geïmplementeerd op uw iOS-apparaten. Deze instellingen worden gebruikt om VPN-verbindingen te maken en configureren voor het netwerk van uw organisatie. In dit artikel worden deze instellingen beschreven. Sommige instellingen zijn alleen beschikbaar voor sommige VPN-clients, zoals Citrix en Zscaler.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](vpn-settings-configure.md).

> [!NOTE]
> Deze instellingen zijn beschikbaar voor alle inschrijvings typen. Zie [IOS-inschrijving](../enrollment/ios-enroll.md)voor meer informatie over de inschrijvings typen.

## <a name="connection-type"></a>Type verbinding

Selecteer het type VPN-verbinding in de volgende lijst met leveranciers:

- **Check Point Capsule VPN**
- **Cisco Legacy AnyConnect**: dit is van toepassing op de app [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) versie 4.0.5x en eerder.
- **Cisco AnyConnect**: dit is van toepassing op de app [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) versie 4.0.7x en later.
- **SonicWall Mobile Connect**
- **F5 Access Legacy**: dit is van toepassing op de app F5 Access versie 2.1 en eerder.
- **F5 Access**: dit is van toepassing op de app F5 Access versie 3.0 en later.
- **Palo Alto Networks GlobalProtect (verouderd)** : dit is van toepassing op de app Palo Alto Networks GlobalProtect versie 4.1 en eerder.
- **Palo Alto Networks GlobalProtect**: dit is van toepassing op de app Palo Alto Networks GlobalProtect versie 5.0 en later.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: Als u gebruik wilt maken van voorwaardelijke toegang of gebruikers wilt toestaan om het Zscaler-aanmeldingsscherm over te slaan, moet u Zscaler Private Access (ZPA) integreren met uw Microsoft Azure AD-account. Zie de [Zscaler documentatie](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad) voor gedetailleerde instructies. 
- **Ikev2**: [ikev2-instellingen](#ikev2-settings) (in dit artikel) beschrijven de eigenschappen.
- **Aangepaste VPN**

> [!NOTE]
> Cisco, Citrix, F5 en Palo Alto hebben aangekondigd dat hun verouderde clients niet werken in iOS 12. U moet zo snel mogelijk migreren naar de nieuwe apps. Zie de [blog van het Microsoft Intune-ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409) voor meer informatie.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

Welke instellingen in de volgende lijst worden weergegeven, is afhankelijk van het VPN-verbindingstype dat u selecteert.  

- **Verbindingsnaam**: eindgebruikers zien deze naam wanneer ze op hun apparaat in een lijst met beschikbare VPN-verbindingen zoeken.
- **Aangepaste domeinnaam** (alleen Zscaler): Vul het aanmeldingsveld van de Zscaler-app vooraf met het domein waarvan uw gebruikers deel uitmaken. Als bijvoorbeeld de gebruikersnaam `Joe@contoso.net` is, wordt het domein `contoso.net` statisch in het veld weergegeven wanneer de app wordt geopend. Als u geen domeinnaam invoert, wordt het domeingedeelte van de UPN in Azure Active Directory (AD) gebruikt.
- **IP-adres of FQDN**: dit is het IP-adres of de FQDN (Fully Qualified Domain Name) van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld `192.168.1.1` of `vpn.contoso.com` in.
- **Cloudnaam van organisatie** (alleen Zscaler): voer de naam in van de cloud waarin uw organisatie is ingericht. De URL waarmee u zich aanmeldt bij Zscaler bevat de naam.  
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. 
  - **Certificaten**: selecteer onder **Verificatiecertificaat** een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](../protect/certificates-configure.md) bevat enkele richtlijnen voor certificaatprofielen.
  - **Gebruikersnaam en wachtwoord**: eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.  

    > [!NOTE]
    > Als gebruikersnaam en wachtwoord worden gebruikt als verificatiemethode voor Cisco IPsec VPN, moeten deze het SharedSecret bieden via een aangepast profiel voor de Apple Configurator.

  - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de Smart Card van een gebruiker. Als er geen afgeleide referentie verlener is geconfigureerd, wordt u door intune gevraagd om er een toe te voegen. Zie [afgeleide referenties gebruiken in Microsoft intune](../protect/derived-credentials.md)voor meer informatie.

- **Uitgesloten URL's** (alleen Zscaler): wanneer u verbonden bent met het VPN van Zscaler, zijn de vermelde URL's toegankelijk buiten de Zscaler-cloud. 

- **Split tunneling**: u kunt deze optie **inschakelen**  of **uitschakelen** om apparaten te laten bepalen welke verbinding afhankelijk van het verkeer moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar gebruikt het standaardnetwerk van het hotel om gewoon op het web te surfen.

- **VPN-id** (aangepaste VPN, Zscaler en Citrix): dit is een id voor de VPN-app die u gebruikt en wordt geleverd door uw VPN-provider.
  - **Sleutel-/waardeparen voor de aangepaste VPN-kenmerken van uw organisatie invoeren**: voeg **sleutel-** en **waardeparen** toe of importeer deze om uw VPN-verbinding aan te passen. Deze waarden worden doorgaans aangeleverd door uw VPN-provider.

- **Netwerktoegangsbeheer (NAC) inschakelen** (Citrix SSO, F5-toegang): Wanneer u **Ik ga akkoord** selecteert, wordt de apparaat-id opgenomen in het VPN-profiel. Deze id kan worden gebruikt voor verificatie bij de VPN om netwerktoegang toe te staan of te voorkomen.

  Zorg **bij het gebruik van F5-toegang** voor het volgende:

  - Bevestig dat u F5 BIG-IP 13.1.1.5 gebruikt. BIG-IP 14 wordt niet ondersteund.
  - Integreer BIG-IP met Intune voor NAC. Zie F5-handleiding [Overzicht: APM configureren voor apparaatpostuurcontroles met eindpuntbeheersystemen](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
  - NAC is ingeschakeld in het VPN-profiel.

  **Wanneer u Citrix SSO met Gateway gebruikt**, moet u ervoor zorgen dat:

  - U Citrix Gateway 12.0.59 of hoger gebruikt.
  - Uw gebruikers Citrix SSO 1.1.6 of hoger hebben geïnstalleerd op hun apparaten.
  - Integreer Citrix Gateway met Intune voor NAC. Zie de Citrix-implementatiehandleiding[Microsoft Intune/Enterprise Mobility Suite integreren met NetScaler (LDAP- ENOTP-scenario)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf).
  - NAC is ingeschakeld in het VPN-profiel.

  **Belangrijke informatie:**  

  - Als NAC wordt ingeschakeld, wordt de verbinding met de VPN elke 24 uur verbroken. De VPN-verbinding wordt onmiddellijk hersteld.
  - De apparaat-id maakt deel uit van het profiel, maar is niet zichtbaar in Intune. De id wordt nergens door Microsoft opgeslagen en wordt niet door Microsoft gedeeld.

  Voor de VPN-partners die de apparaat-ID ondersteunen, kan de VPN-client, zoals Citrix SSO, de ID ophalen. Vervolgens kan de VPN-client een query in Intune uitvoeren om te bevestigen dat het apparaat is geregistreerd en om na te gaan of het VPN-profiel wel of niet conform is.

  - Als u deze instelling wilt verwijderen, maakt u het profiel opnieuw en selecteert u de optie **Ik ga akkoord** niet. Wijs het profiel vervolgens opnieuw toe.

## <a name="ikev2-settings"></a>IKEv2-instellingen

Deze instellingen zijn van toepassing wanneer u **verbindings type**  > **IKEv2**kiest.

- **Externe ID**: Voer het netwerk-IP-adres, de FQDN-naam, de UserFQDN of de ASN1DN van de IKEv2-server in. Voer bijvoorbeeld `10.0.0.3` of `vpn.contoso.com` in. Normaal gesp roken voert u dezelfde waarde in als de naam van de [**verbinding**](#base-vpn-settings) (in dit artikel). Maar dit is afhankelijk van de instellingen van uw IKEv2-server.

- **Type client verificatie**: Kies hoe de VPN-client wordt geverifieerd bij de VPN. Uw opties zijn:
  - **Gebruikers verificatie** (standaard): de gebruikers referenties worden geverifieerd bij de VPN-verbinding.
  - **Computer authenticatie**: de referenties van het apparaat worden geverifieerd bij de VPN-verbinding.

- **Verificatie methode**: Kies het type client referenties dat naar de server moet worden verzonden. Uw opties zijn:
  - **Certificaten**: maakt gebruik van een bestaand certificaat profiel voor verificatie bij het VPN. Zorg ervoor dat dit certificaat profiel al aan de gebruiker of het apparaat is toegewezen. Anders mislukt de VPN-verbinding.
    - **Certificaat type**: Selecteer het type versleuteling dat wordt gebruikt door het certificaat. Zorg ervoor dat de VPN-server zo is geconfigureerd dat dit type certificaat wordt geaccepteerd. Uw opties zijn:
      - **RSA** (standaard)
      - **ECDSA256**
      - **ECDSA384**
      - **ECDSA521**

  - **Gebruikers naam en wacht woord** (alleen gebruikers verificatie): wanneer gebruikers verbinding maken met het VPN, wordt ze gevraagd om hun gebruikers naam en wacht woord.
  - **Gedeeld geheim** (alleen computer authenticatie): Hiermee kunt u een gedeeld geheim invoeren dat naar de VPN-server moet worden verzonden.
    - **Gedeeld geheim**: Voer het gedeelde geheim in, ook wel bekend als de vooraf gedeelde sleutel (PSK). Zorg ervoor dat de waarde overeenkomt met het gedeelde geheim dat is geconfigureerd op de VPN-server.

- **Algemene naam**van de uitgever van de server certificaat: Hiermee kan de VPN-server worden geverifieerd bij de VPN-client. Voer de algemene naam (CN) van de certificaat verlener in van het VPN-server certificaat dat wordt verzonden naar de VPN-client op het apparaat. Zorg ervoor dat de CN-waarde overeenkomt met de configuratie op de VPN-server. Anders mislukt de VPN-verbinding.
- **Algemene naam van het server certificaat**: Voer de cn in voor het certificaat zelf. Als dit veld leeg blijft, wordt de waarde voor de externe ID gebruikt.

- **Detectie frequentie van onbestelbare peer**: Kies hoe vaak de VPN-client controleert of de VPN-tunnel actief is. Uw opties zijn:
  - **Niet geconfigureerd**: gebruikt de standaard waarde van het IOS-systeem. Dit kan hetzelfde zijn als het selecteren van **medium**.
  - **Geen**: de detectie van onbestelbare peers wordt uitgeschakeld.
  - **Low**: Hiermee wordt elke 30 minuten een keepalive-bericht verzonden.
  - **Gemiddeld** (standaard): Hiermee wordt elke 10 minuten een keepalive-bericht verzonden.
  - **Hoog**: Hiermee wordt elke 60 seconden een keepalive-bericht verzonden.

- **Minimum TLS-versie bereik**: Voer de minimale TLS-versie in die moet worden gebruikt. Voer `1.0`, `1.1` of `1.2` in. Als dit veld leeg blijft, wordt de standaard waarde van `1.0` gebruikt.
- **TLS-versie bereik maximum**: Voer de maximale TLS-versie in die u wilt gebruiken. Voer `1.0`, `1.1` of `1.2` in. Als dit veld leeg blijft, wordt de standaard waarde van `1.2` gebruikt.
- **Perfect Forward Secrecy**: Selecteer **inschakelen** om PFS (Perfect Forward Secrecy) in te scha kelen. PFS is een IP-beveiligings functie die de impact vermindert als een sessie sleutel wordt aangetast. Met **uitschakelen** (standaard) wordt PFS niet gebruikt.
- **Controle van certificaat intrekking**: Selecteer **inschakelen** om ervoor te zorgen dat de certificaten niet worden ingetrokken voordat de VPN-verbinding kan slagen. Deze controle is de beste inspanning. Als er een time-out optreedt voor de VPN-server voordat wordt vastgesteld of het certificaat is ingetrokken, wordt toegang verleend. **Uitschakelen** (standaard) controleert niet op ingetrokken certificaten.

- **Para meters voor beveiligings koppeling configureren**: **niet geconfigureerd** (standaard) maakt gebruik van de standaard IOS-systeem. Selecteer **inschakelen** om de para meters in te voeren die worden gebruikt bij het maken van beveiligings koppelingen met de VPN-server:
  - **Versleutelings algoritme**: Selecteer het gewenste algoritme:
    - DES
    - 3DES
    - AES-128
    - AES-256 (standaard)
    - AES-128-GCM
    - AES-256-GCM
  - **Integriteits algoritme**: Selecteer het gewenste algoritme:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (standaard)
    - SHA2-384
    - SHA2-512
  - **Diffie-Hellman-groep**: Selecteer de groep die u wilt. De standaard instelling is groeps `2`.
  - **Levens duur** (minuten): Kies hoe lang de beveiligings koppeling actief blijft totdat de sleutels worden gedraaid. Voer een gehele waarde tussen `10` en `1440` (1440 minuten is 24 uur). De standaard waarde is `1440`.

- **Een afzonderlijke set para meters voor onderliggende beveiligings koppelingen configureren**: met IOS kunt u afzonderlijke para meters voor de IKE-verbinding en eventuele onderliggende verbindingen configureren. 

  **Niet geconfigureerd** (standaard) gebruikt de waarden die u in de vorige instelling **beveiligings koppeling instellen para meters** hebt opgegeven. Selecteer **inschakelen** om de para meters in te voeren die worden gebruikt bij het maken van *onderliggende* beveiligings koppelingen met de VPN-server:
  - **Versleutelings algoritme**: Selecteer het gewenste algoritme:
    - DES
    - 3DES
    - AES-128
    - AES-256 (standaard)
    - AES-128-GCM
    - AES-256-GCM
  - **Integriteits algoritme**: Selecteer het gewenste algoritme:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (standaard)
    - SHA2-384
    - SHA2-512
  - **Diffie-Hellman-groep**: Selecteer de groep die u wilt. De standaard instelling is groeps `2`.
  - **Levens duur** (minuten): Kies hoe lang de beveiligings koppeling actief blijft totdat de sleutels worden gedraaid. Voer een gehele waarde tussen `10` en `1440` (1440 minuten is 24 uur). De standaard waarde is `1440`.

## <a name="automatic-vpn-settings"></a>Automatische VPN-instellingen

- **VPN per app**: hiermee schakelt u VPN per app in. Er kan dan automatisch een VPN-verbinding worden gemaakt wanneer bepaalde apps worden geopend. U kunt ook apps koppelen aan het VPN-profiel. Voor meer informatie ziet u de [instructies voor het instellen van VPN per app voor iOS](vpn-setting-configure-per-app.md).
  - **Providertype**: alleen beschikbaar voor Pulse Secure en aangepaste VPN.
  - Wanneer u in iOS **VPN-profielen voor individuele apps** gebruikt met Pulse Secure en een aangepaste VPN, kiest u voor tunnels op app-niveau (app-proxy) of op pakketniveau (pakkettunnel). Stel de waarde **ProviderType** in op **app-proxy** voor tunneling op app-niveau of **pakkettunnel** voor tunneling op pakketniveau. Als u niet zeker weet welke waarde u moet gebruiken, bekijkt u de documentatie van uw VPN-provider.
  - **Safari-URL's die deze VPN activeren**: voeg een of meer website-URL's toe. Wanneer deze URL's worden bezocht via de Safari-browser op het apparaat, wordt er automatisch een VPN-verbinding ingesteld.

- **On-demand VPN**: configureer voorwaardelijke regels om te bepalen wanneer de VPN-verbinding wordt gestart. Stel bijvoorbeeld een voorwaarde in waarmee de VPN-verbinding alleen wordt gebruikt als een apparaat niet met een Wi-Fi-netwerk van het bedrijf is verbonden. Of maak een voorwaarde. Voorbeeld: de VPN-verbinding wordt niet gestart als een apparaat geen toegang heeft tot een DNS-zoekdomein dat u opgeeft.

  - **SSID's of DNS-zoekdomeinen**: selecteer of voor deze voorwaarde het draadloze netwerk,  **SSID's** of **DNS-zoekdomeinen** worden gebruikt. Kies **Toevoegen** om een of meerdere SSID's of zoekdomeinen te configureren.
  - **URL-tekenreekstest**: optioneel. Voer een URL die door de regel als een test wordt gebruikt. Als het apparaat zonder omleiding toegang wil verkrijgen tot deze URL, wordt de VPN-verbinding gestart. Het apparaat maakt dan verbinding met de doel-URL. De gebruiker ziet de tekenreekstestsite voor de URL niet.

    Een voorbeeld van een URL-tekenreekstest is een controlewebserver-URL die de apparaatcompatibiliteit controleert voordat u verbinding maakt met de VPN-verbinding. Of de URL test of de VPN-verbinding kan maken met een site voordat u het apparaat verbindt met de doel-URL via de VPN-verbinding.
.
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

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Configureer VPN-instellingen op apparaten met [Android](vpn-settings-android.md), [Android Enter prise](vpn-settings-android-enterprise.md), [macOS](vpn-settings-macos.md)en [Windows 10](vpn-settings-windows-10.md) .
