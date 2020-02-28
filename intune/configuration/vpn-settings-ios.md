---
title: VPN-instellingen configureren voor iOS-/iPadOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Voeg een VPN-configuratieprofiel toe of maak er een met configuratie-instellingen voor virtuele privénetwerken (VPN), inclusief de verbindingsgegevens, verificatiemethode en split tunneling in de basisinstellingen; de aangepaste VPN-instellingen met de id, en de paren van sleutels en waarden; de VPN-instellingen per app met inbegrip van Safari-URL's, en on-demand VPN's met SSID's of DNS-zoekdomeinen; en de proxy-instellingen die deel moeten uitmaken van een configuratiescript, IP- of FQDN-adres, en TCP-poort in Microsoft Intune op apparaten waarop iOS/iPadOS wordt uitgevoerd.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 01c6ae06459590fa9bb9842e90ad53e6c522d6a6
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512480"
---
# <a name="add-vpn-settings-on-ios-and-ipados-devices-in-microsoft-intune"></a>VPN-instellingen toevoegen aan iOS- en iPadOS-apparaten in Microsoft Intune

Microsoft Intune biedt veel VPN-instellingen die kunnen worden geïmplementeerd op uw iOS-/iPadOS-apparaten. Deze instellingen worden gebruikt om VPN-verbindingen te maken en configureren voor het netwerk van uw organisatie. In dit artikel worden deze instellingen beschreven. Sommige instellingen zijn alleen beschikbaar voor sommige VPN-clients, zoals Citrix en Zscaler.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een apparaatconfiguratieprofiel](vpn-settings-configure.md).

> [!NOTE]
> Deze instellingen zijn beschikbaar voor alle inschrijvingstypen. Zie [iOS-/iPadOS-inschrijving](../enrollment/ios-enroll.md) voor meer informatie over de inschrijvingstypen.

## <a name="connection-type"></a>Type verbinding

Selecteer het type VPN-verbinding in de volgende lijst met leveranciers:

- **Check Point Capsule VPN**
- **Cisco Legacy AnyConnect**: Dit is van toepassing op de app [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) versie 4.0.5x en eerder.
- **Cisco AnyConnect**: Dit is van toepassing op de app [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) versie 4.0.7x en later.
- **SonicWall Mobile Connect**
- **F5 Access Legacy**: Dit is van toepassing op de app F5 Access versie 2.1 en eerder.
- **F5 Access**: Dit is van toepassing op de app F5 Access versie 3.0 en later.
- **Palo Alto Networks GlobalProtect (verouderd)** : Dit is van toepassing op de app Palo Alto Networks GlobalProtect versie 4.1 en eerder.
- **Palo Alto Networks GlobalProtect**: Dit is van toepassing op de app Palo Alto Networks GlobalProtect versie 5.0 en later.
- **Pulse Secure**
- **Cisco (IPSec)**
- **Citrix VPN**
- **Citrix SSO**
- **Zscaler**: Als u gebruik wilt maken van voorwaardelijke toegang of gebruikers wilt toestaan om het Zscaler-aanmeldingsscherm over te slaan, moet u Zscaler Private Access (ZPA) integreren met uw Microsoft Azure AD-account. Zie de [Zscaler documentatie](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad) voor gedetailleerde instructies. 
- **IKEv2**: in [IKEv2-instellingen](#ikev2-settings) (in dit artikel) worden de eigenschappen beschreven.
- **Aangepaste VPN**

> [!NOTE]
> Cisco, Citrix, F5 en Palo Alto hebben aangekondigd dat hun verouderde clients niet werken in iOS 12. U moet zo snel mogelijk migreren naar de nieuwe apps. Zie de [blog van het Microsoft Intune-ondersteuningsteam](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409) voor meer informatie.

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

Welke instellingen in de volgende lijst worden weergegeven, is afhankelijk van het VPN-verbindingstype dat u selecteert.  

- **Verbindingsnaam**: Eindgebruikers zien deze naam wanneer ze op hun apparaat in een lijst met beschikbare VPN-verbindingen zoeken.
- **Aangepaste domeinnaam** (alleen Zscaler): Vul het aanmeldingsveld van de Zscaler-app vooraf in met het domein waarvan uw gebruikers deel uitmaken. Als bijvoorbeeld de gebruikersnaam `Joe@contoso.net` is, wordt het domein `contoso.net` statisch in het veld weergegeven wanneer de app wordt geopend. Als u geen domeinnaam invoert, wordt het domeingedeelte van de UPN in Azure Active Directory (AD) gebruikt.
- **IP-adres of FQDN**: Het IP-adres of de FQDN (Fully Qualified Domain Name) van de VPN-server waarmee apparaten verbinding maken. Voer bijvoorbeeld `192.168.1.1` of `vpn.contoso.com` in.
- **Cloudnaam van organisatie** (alleen Zscaler): Voer de naam in van de cloud waarin uw organisatie is ingericht. De URL waarmee u zich aanmeldt bij Zscaler bevat de naam.  
- **Verificatiemethode**: kies hoe apparaten worden geverifieerd bij de VPN-server. 
  - **Certificaten**: Selecteer onder **Verificatiecertificaat** een bestaand SCEP- of PKCS-certificaatprofiel om de verbinding te verifiëren. [Certificaten configureren](../protect/certificates-configure.md) bevat enkele richtlijnen voor certificaatprofielen.
  - **Gebruikersnaam en wachtwoord**: Eindgebruikers moeten een gebruikersnaam en wachtwoord opgeven om zich aan te melden bij de VPN-server.  

    > [!NOTE]
    > Als gebruikersnaam en wachtwoord worden gebruikt als verificatiemethode voor Cisco IPsec VPN, moeten deze het SharedSecret bieden via een aangepast profiel voor de Apple Configurator.

  - **Afgeleide referentie**: gebruik een certificaat dat is afgeleid van de smartcard van een gebruiker. Als er geen uitgever voor afgeleide referenties is geconfigureerd, wordt u door Intune gevraagd om er een toe te voegen. Zie [Afgeleide referenties gebruiken in Microsoft Intune](../protect/derived-credentials.md) voor meer informatie.

- **Uitgesloten URL's** (alleen Zscaler): Wanneer u verbonden bent met het VPN van Zscaler, zijn de vermelde URL's toegankelijk buiten de Zscaler-cloud. 

- **Split tunneling**: U kunt deze optie **Inschakelen**  of **Uitschakelen** om apparaten op basis van het verkeer te laten bepalen welke verbinding moet worden gebruikt. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar gebruikt het standaardnetwerk van het hotel om gewoon op het web te surfen.

- **VPN-id** (aangepaste VPN, Zscaler en Citrix): Dit is een id voor de VPN-app die u gebruikt en wordt verstrekt door uw VPN-provider.
  - **Sleutel-/waardeparen voor de aangepaste VPN-kenmerken van uw organisatie invoeren**: Voeg **Sleutels** en **Waarden** toe of importeer deze om uw VPN-verbinding aan te passen. Deze waarden worden doorgaans aangeleverd door uw VPN-provider.

- **Netwerktoegangsbeheer (NAC) inschakelen** (Citrix SSO, F5 Access): Als u **Ik ga akkoord** kiest, wordt de apparaat-id opgenomen in het VPN-profiel. Deze id kan worden gebruikt voor verificatie bij de VPN om netwerktoegang toe te staan of te voorkomen.

  Zorg **bij het gebruik van F5-toegang** voor het volgende:

  - Bevestig dat u F5 BIG-IP 13.1.1.5 gebruikt. BIG-IP 14 wordt niet ondersteund.
  - Integreer BIG-IP met Intune voor NAC. Zie de F5-handleiding [Overzicht: APM configureren voor apparaatpostuurcontroles met eindpuntbeheersystemen](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89).
  - NAC is ingeschakeld in het VPN-profiel.

  **Wanneer u Citrix SSO met Gateway gebruikt**, moet u ervoor zorgen dat:

  - U Citrix Gateway 12.0.59 of hoger gebruikt.
  - Uw gebruikers Citrix SSO 1.1.6 of hoger hebben geïnstalleerd op hun apparaten.
  - Integreer Citrix Gateway met Intune voor NAC. Zie de Citrix-implementatiehandleiding[Microsoft Intune/Enterprise Mobility Suite integreren met NetScaler (LDAP- ENOTP-scenario)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf).
  - NAC is ingeschakeld in het VPN-profiel.

  **Belangrijke informatie:**  

  - Als NAC wordt ingeschakeld, wordt de verbinding met de VPN elke 24 uur verbroken. De VPN-verbinding wordt onmiddellijk hersteld.
  - De apparaat-id maakt deel uit van het profiel, maar is niet zichtbaar in Intune. De id wordt nergens door Microsoft opgeslagen en wordt niet door Microsoft gedeeld.

  Wanneer de apparaat-id wordt ondersteund door VPN-partners, kan de VPN-client, zoals Citrix SSO, de id ophalen. Vervolgens kan de VPN-client een query in Intune uitvoeren om te bevestigen dat het apparaat is geregistreerd en om na te gaan of het VPN-profiel wel of niet conform is.

  - Als u deze instelling wilt verwijderen, maakt u het profiel opnieuw en selecteert u de optie **Ik ga akkoord** niet. Wijs het profiel vervolgens opnieuw toe.

## <a name="ikev2-settings"></a>IKEv2-instellingen

Deze instellingen zijn van toepassing wanneer u het **verbindingstype** > **IKEv2** kiest.

- **Externe id**: voer het netwerk-IP-adres, de FQDN, de UserFQDN of de ASN1DN van de IKEv2-server in. Voer bijvoorbeeld `10.0.0.3` of `vpn.contoso.com` in. Normaal gesproken voert u dezelfde waarde in als bij [**Verbindingsnaam**](#base-vpn-settings) (in dit artikel). Maar dit is afhankelijk van de instellingen van uw IKEv2-server.

- **Type clientverificatie**: kies hoe de VPN-client wordt geverifieerd bij het VPN. Uw opties zijn:
  - **Gebruikersverificatie** (standaard): de gebruikersreferenties worden geverifieerd bij het VPN.
  - **Computerverificatie**: de referenties van het apparaat worden geverifieerd bij het VPN.

- **Verificatiemethode**: kies het type clientreferenties dat naar de server moet worden verzonden. Uw opties zijn:
  - **Certificaten**: maakt gebruik van een bestaand certificaatprofiel voor verificatie bij het VPN. Zorg ervoor dat dit certificaatprofiel al aan de gebruiker of het apparaat is toegewezen. Anders mislukt de VPN-verbinding.
    - **Certificaattype**: selecteer het type versleuteling dat wordt gebruikt door het certificaat. Zorg ervoor dat de VPN-server zo is geconfigureerd dat dit type certificaat wordt geaccepteerd. Uw opties zijn:
      - **RSA** (standaard)
      - **ECDSA256**
      - **ECDSA384**
      - **ECDSA521**

  - **Gebruikersnaam en wachtwoord** (alleen gebruikersverificatie): wanneer gebruikers verbinding maken met het VPN, moeten zij hun gebruikersnaam en wachtwoord invoeren.
  - **Gedeeld geheim** (alleen computerverificatie): hiermee kunt u een gedeeld geheim invoeren dat naar de VPN-server moet worden verzonden.
    - **Gedeeld geheim**: voer het gedeelde geheim in, ook wel bekend als de vooraf gedeelde sleutel (PSK). Zorg ervoor dat de waarde overeenkomt met het gedeelde geheim dat is geconfigureerd op de VPN-server.

- **Algemene naam voor verlener van servercertificaat**: hiermee kan de VPN-server worden geverifieerd bij de VPN-client. Voer de algemene naam (CN) in van de verlener van het VPN-servercertificaat dat wordt verzonden naar de VPN-client op het apparaat. Zorg ervoor dat de CN-waarde overeenkomt met de configuratie op de VPN-server. Anders mislukt de VPN-verbinding.
- **Algemene naam voor servercertificaat**: voer de CN in voor het certificaat zelf. Als dit veld leeg blijft, wordt de waarde van de externe id gebruikt.

- **Detectiesnelheid voor inactieve peer**: kies hoe vaak de VPN-client controleert of de VPN-tunnel actief is. Uw opties zijn:
  - **Niet geconfigureerd**: maakt gebruik van de standaardinstelling voor het iOS-/iPadOS-systeem. Dit kan hetzelfde zijn als het kiezen van **Gemiddeld**.
  - **Geen**: de detectie van inactieve peers wordt uitgeschakeld.
  - **Laag**: elke 30 minuten wordt een keepalive-bericht verzonden.
  - **Gemiddeld** (standaard): elke 10 minuten wordt een keepalive-bericht verzonden.
  - **Hoog**: elke 60 seconden wordt een keepalive-bericht verzonden.

- **Minimum TLS-versiebereik**: voer de minimale TLS-versie in die moet worden gebruikt. Voer `1.0`, `1.1` of `1.2` in. Als dit veld leeg blijft, wordt de standaardwaarde `1.0` gebruikt.
- **Maximum TLS-versiebereik**: voer de maximale TLS-versie in die moet worden gebruikt. Voer `1.0`, `1.1` of `1.2` in. Als dit veld leeg blijft, wordt de standaardwaarde `1.2` gebruikt.

> [!NOTE]
> Bij gebruik van gebruikersverificatie en certificaten moeten het minimum en maximum van het TLS-versiebereik zijn ingesteld.

- **Perfect Forward Secrecy**: selecteer **Inschakelen** om PFS (Perfect Forward Secrecy) in te schakelen. PFS is een IP-beveiligingsfunctie die de impact vermindert als een sessiesleutel gecompromitteerd is. **Uitschakelen** (standaard): PFS wordt niet gebruikt.
- **Controle van certificaatintrekking**: selecteer **Inschakelen** als moet worden gecontroleerd of de certificaten niet zijn ingetrokken voordat wordt toegestaan dat de VPN-verbinding tot stand wordt gebracht. Dit is een 'best effort'-controle. Als er een time-out optreedt voor de VPN-server voordat wordt vastgesteld of het certificaat is ingetrokken, wordt toegang verleend. **Uitschakelen** (standaard): er wordt niet gecontroleerd of de certificaten zijn ingetrokken.

- **Parameters voor beveiligingskoppelingen configureren**: **Niet geconfigureerd** (standaard): gebruikt de standaardwaarde van het iOS-/iPadOS-systeem. Selecteer **Inschakelen** om de parameters in te voeren die worden gebruikt bij het maken van beveiligingskoppelingen met de VPN-server:
  - **Versleutelingsalgoritme**: selecteer het gewenste algoritme:
    - DES
    - 3DES
    - AES-128
    - AES-256 (standaard)
    - AES-128-GCM
    - AES-256-GCM
  - **Integriteitsalgoritme**: selecteer het gewenste algoritme:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (standaard)
    - SHA2-384
    - SHA2-512
  - **Diffie-Hellman-groep**: selecteer de gewenste groep. De standaardinstelling is groep `2`.
  - **Levensduur** (minuten): kies hoe lang de beveiligingskoppeling actief blijft totdat de sleutels worden gedraaid. Voer een geheel getal tussen `10` en `1440` in (1440 minuten is 24 uur). De standaardinstelling is `1440`.

- **Een afzonderlijke set parameters voor onderliggende beveiligingskoppelingen configureren**: met iOS/iPadOS kunt u afzonderlijke parameters voor de IKE-verbinding en eventuele onderliggende verbindingen configureren. 

  **Niet geconfigureerd** (standaard): gebruikt de waarden die u eerder bij **Parameters voor beveiligingskoppelingen configureren** hebt opgegeven. Selecteer **Inschakelen** als u de parameters voor het maken van *onderliggende* beveiligingskoppelingen met de VPN-server wilt invoeren:
  - **Versleutelingsalgoritme**: selecteer het gewenste algoritme:
    - DES
    - 3DES
    - AES-128
    - AES-256 (standaard)
    - AES-128-GCM
    - AES-256-GCM
  - **Integriteitsalgoritme**: selecteer het gewenste algoritme:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (standaard)
    - SHA2-384
    - SHA2-512
  - **Diffie-Hellman-groep**: selecteer de gewenste groep. De standaardinstelling is groep `2`.
  - **Levensduur** (minuten): kies hoe lang de beveiligingskoppeling actief blijft totdat de sleutels worden gedraaid. Voer een geheel getal tussen `10` en `1440` in (1440 minuten is 24 uur). De standaardinstelling is `1440`.

## <a name="automatic-vpn-settings"></a>Automatische VPN-instellingen

- **VPN per app**: Hiermee schakelt u VPN per app in. Er kan dan automatisch een VPN-verbinding worden gemaakt wanneer bepaalde apps worden geopend. U kunt ook apps koppelen aan het VPN-profiel. VPN per app wordt niet ondersteund voor IKEv2. Zie de [instructies voor het instellen van VPN per app voor iOS/iPadOS](vpn-setting-configure-per-app.md) voor meer informatie. 
  - **Providertype**: Alleen beschikbaar voor Pulse Secure en aangepaste VPN.
  - Wanneer u in iOS/iPadOS **VPN per app**-profielen met Pulse Secure of een aangepast VPN gebruikt, kiest u voor tunnels op app-niveau (app-proxy) of op pakketniveau (pakkettunnel). Stel de waarde **ProviderType** in op **app-proxy** voor tunneling op app-niveau of **pakkettunnel** voor tunneling op pakketniveau. Als u niet zeker weet welke waarde u moet gebruiken, bekijkt u de documentatie van uw VPN-provider.
  - **Safari-URL's waarmee dit VPN wordt geactiveerd**: Voeg een of meer website-URL's toe. Wanneer deze URL's worden bezocht via de Safari-browser op het apparaat, wordt er automatisch een VPN-verbinding ingesteld.

- **VPN op aanvraag**: Configureer voorwaardelijke regels om te bepalen wanneer de VPN-verbinding wordt gestart. Stel bijvoorbeeld een voorwaarde in waarmee de VPN-verbinding alleen wordt gebruikt als een apparaat niet met een Wi-Fi-netwerk van het bedrijf is verbonden. Of maak een voorwaarde. Voorbeeld: de VPN-verbinding wordt niet gestart als een apparaat geen toegang heeft tot een DNS-zoekdomein dat u opgeeft.

  - **SSID's of DNS-zoekdomeinen**: Selecteer of voor deze voorwaarde het draadloze netwerk,  **SSID's** of **DNS-zoekdomeinen** worden gebruikt. Kies **Toevoegen** om een of meerdere SSID's of zoekdomeinen te configureren.
  - **URL-tekenreekstest**: Optioneel. Voer een URL die door de regel als een test wordt gebruikt. Als het apparaat zonder omleiding toegang wil verkrijgen tot deze URL, wordt de VPN-verbinding gestart. Het apparaat maakt dan verbinding met de doel-URL. De gebruiker ziet de tekenreekstestsite voor de URL niet.

    Een voorbeeld van een URL-tekenreekstest is een controlewebserver-URL die de apparaatcompatibiliteit controleert voordat u verbinding maakt met de VPN-verbinding. Een andere mogelijkheid is dat de URL de VPN-verbinding voor een site controleert voordat het apparaat verbinding maakt met de doel-URL via de VPN-verbinding.
.
  - **Domeinactie**: Kies een van de volgende items:
    - Verbinding maken indien nodig
    - Nooit verbinding maken
  - **Actie**: Kies een van de volgende items:
    - Verbinden
    - Verbinding evalueren
    - Negeren
    - Verbinding verbreken

## <a name="proxy-settings"></a>Proxyinstellingen

Als u een proxy gebruikt, configureert u de volgende instellingen. Proxyinstellingen zijn niet beschikbaar voor VPN-verbindingen van Zscaler.  

- **Script voor automatische configuratie**: Gebruik een bestand om de proxyserver te configureren. Voer de **URL van de proxyserver** (bijvoorbeeld `http://proxy.contoso.com`) in die het configuratiebestand bevat.
- **Adres**: Voer het IP-adres van de volledig gekwalificeerde hostnaam van de proxyserver in.
- **Poortnummer**: Voer het poortnummer in dat is gekoppeld aan de proxyserver.

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens kunt u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Configureer VPN-instellingen op apparaten met [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [macOS](vpn-settings-macos.md) en [Windows 10](vpn-settings-windows-10.md).
