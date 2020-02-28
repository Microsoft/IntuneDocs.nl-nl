---
title: VPN-instellingen voor Windows 10 in Microsoft Intune - Azure | Microsoft Docs
description: Meer informatie over alle beschikbare VPN-instellingen in Microsoft Intune, waarvoor ze worden gebruikt en wat ze doen, zoals regels voor netwerkverkeer, voorwaardelijke toegang en DNS- en proxy-instellingen voor Windows 10- en Windows Holographic for Business-apparaten.
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
ms.reviewer: tycast
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 47be57dece7867109565622ec2a1380e9a9d57d7
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "77512497"
---
# <a name="windows-10-and-windows-holographic-device-settings-to-add-vpn-connections-using-intune"></a>Instellingen voor Windows 10- en Windows Holographic-apparaten om VPN-verbindingen met Intune toe te voegen



U kunt met Microsoft Intune VPN-verbindingen toevoegen aan en configureren voor apparaten. Dit artikel bevat een overzicht en beschrijvingen van veelgebruikte instellingen en functies bij het maken van virtuele particuliere netwerken (VPN's). Deze VPN-instellingen en -functies worden gebruikt in apparaatconfiguratieprofielen in Intune die worden gepusht of geïmplementeerd naar gebruikers.

U kunt deze instellingen gebruiken als onderdeel van uw MDM-oplossing (Mobile Device Management) om functies toe te staan of uit te schakelen, zoals het gebruik van een VPN-leverancier, het inschakelen van AlwaysOn, het gebruik van DNS, het toevoegen van een proxy en meer.

Deze instellingen gelden voor apparaten met:

- Windows 10
- Windows Holographic for Business

Afhankelijk van de instellingen die u kiest, kunnen niet alle waarden worden geconfigureerd.

## <a name="before-you-begin"></a>Voordat u begint

[Maak een VPN-apparaatconfiguratieprofiel](vpn-settings-configure.md).

## <a name="base-vpn-settings"></a>Basis-VPN-instellingen

- **Verbindingsnaam**: Voer een naam in voor deze verbinding. Eindgebruikers zien deze naam wanneer ze op hun apparaat in de lijst met beschikbare VPN-verbindingen zoeken.
- **Servers**: Voeg een of meer VPN-servers toe waarmee de apparaten verbinding maken. Als u een server toevoegt, voert u de volgende gegevens in:
  - **Beschrijving**: Voer een beschrijvende naam in voor de server, zoals **Contoso VPN-server**
  - **IP-adres of FQDN**: Voer het IP-adres of de Fully Qualified Domain Name (FQDN) in van de VPN-server waarmee apparaten verbinding maken, zoals **192.168.1.1** of **vpn.contoso.com**
  - **Standaardserver**: Hiermee wordt deze server ingeschakeld als de standaardserver die apparaten gebruiken om de verbinding te maken. U kunt slechts één server als standaard instellen.
  - **Importeren**: Blader naar een bestand met een door komma's gescheiden lijst met servers in de indeling: beschrijving, IP-adres of FQDN, Standaardserver. Kies **OK** om deze servers te importeren in de lijst met **servers**.
  - **Exporteren**: Hiermee exporteert u de lijst met servers naar een bestand met door komma's gescheiden waarden (CSV-bestand)

- **IP-adressen met interne DNS registreren**: Selecteer **Inschakelen** als u het VPN-profiel van Windows 10 zo wilt configureren dat de IP-adressen die zijn toegewezen aan de VPN-interface met de interne DNS, dynamisch worden geregistreerd. Selecteer **Uitschakelen** als u de IP-adressen niet dynamisch wilt registreren.

- **Type verbinding**: Selecteer het type VPN-verbinding in de volgende lijst met leveranciers:

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
  - **AlwaysOn**: Kies **Inschakelen** om automatisch verbinding te maken met de VPN-verbinding wanneer het volgende gebeurt: 
    - Gebruikers zich aanmelden op hun apparaten
    - Het netwerk op het apparaat wijzigt
    - Het scherm op het apparaat wordt ingeschakeld nadat het was uitgeschakeld 

  - **Verificatiemethode**: Selecteer hoe gebruikers zich moeten verifiëren bij de VPN-server. Het gebruik van **certificaten** biedt verbeterde functies, zoals zero-touch, VPN op aanvraag en VPN per app.
  - **Referenties onthouden bij elke aanmelding**: Kies ervoor om de verificatiereferenties op te slaan in het cachegeheugen.
  - **Aangepaste XML**: Geef aangepaste XML-opdrachten op waarmee de VPN-verbinding wordt geconfigureerd.
  - **EAP XML**: Voer EAP XML-opdrachten in waarmee de VPN-verbinding wordt geconfigureerd

### <a name="pulse-secure-example"></a>Voorbeeld van Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

### <a name="f5-edge-client-example"></a>Voorbeeld van F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

### <a name="sonicwall-mobile-connect-example"></a>Voorbeeld van SonicWALL Mobile Connect
**Aanmeldingsgroep of -domein**: Deze eigenschap kan niet worden ingesteld in het VPN-profiel. In plaats daarvan parseert Mobile Connect deze waarde wanneer de gebruikersnaam en het domein worden ingevoerd in de indelingen `username@domain` of `DOMAIN\username`.

Voorbeeld:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

### <a name="checkpoint-mobile-vpn-example"></a>Voorbeeld van CheckPoint Mobile VPN

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

### <a name="writing-custom-xml"></a>Aangepaste XML schrijven
Raadpleeg de VPN-documentatie van de fabrikant voor meer informatie over het schrijven van aangepaste XML-opdrachten.

Zie [EAP-configuratie](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration) voor meer informatie over het maken van aangepaste XML-EAP.

## <a name="apps-and-traffic-rules"></a>Apps en verkeersregels

- **WIP of apps koppelen aan deze VPN**: Schakel deze instelling in als u wilt dat alleen bepaalde apps de VPN-verbinding gebruiken. Uw opties zijn:

  - **Een WIP aan deze verbinding koppelen**: Voer een **WIP-domein voor deze verbinding** in
  - **Apps aan deze verbinding koppelen**: U kunt **een VPN-verbinding beperken tot deze apps** en vervolgens deze **gekoppelde apps** toevoegen. De apps die u invoert, maken automatisch gebruik van de VPN-verbinding. De app-id is afhankelijk van het type app. Voer voor een universele app de naam van de productfamilie in waartoe het pakket behoort. Voer voor een bureaublad-app het bestandspad van de app in.
  >[!IMPORTANT]
  >Het is raadzaam dat u alle app-lijsten beveiligt die zijn gemaakt voor VPN’s per app. Als een ongeautoriseerde gebruiker deze lijst wijzigt en u deze importeert in de app-lijst VPN per app, verleent u onbevoegde gebruikers mogelijk VPN-toegang tot apps die niet toegankelijk zouden moeten zijn. Een manier om uw lijsten met apps te beveiligen, is het gebruik van een toegangsbeheerlijst (ACL).

- **Regels voor netwerkverkeer voor deze VPN-verbinding**: Selecteer welke protocollen en bereiken voor lokale en externe poorten voor de VPN-verbinding worden ingeschakeld. Als u geen netwerkverkeersregel maakt, worden alle protocollen, poorten en adresbereiken ingeschakeld. Nadat u een regel hebt gemaakt, worden door de VPN-verbinding alleen de protocollen, poorten en adresbereiken gebruikt die u in die regel invoert.

## <a name="conditional-access"></a>Voorwaardelijke toegang

- **Voorwaardelijke toegang voor deze VPN-verbinding**: Hiermee wordt de apparaatcompatibiliteitsstroom vanaf de client ingeschakeld. Als de VPN-client is ingeschakeld, communiceert deze met Azure AD (Active Directory) om een certificaat te ontvangen dat kan worden gebruikt voor verificatie. De VPN moet zijn ingesteld voor het gebruik van certificaatverificatie. Ook moet de VPN-server de server vertrouwen die met Azure AD wordt geretourneerd.

- **Eenmalige aanmelding (SSO) met alternatief certificaat inschakelen**: Gebruik voor apparaatcompatibiliteit een ander certificaat dan het VPN-verificatiecertificaat voor Kerberos-verificatie. Voer de volgende instellingen in voor het certificaat:

  - **Naam**: Naam voor EKU (uitgebreide-sleutelgebruik)
  - **Object-id**: Object-id voor EKU
  - **Hash van verlener**: Vingerafdruk voor het SSO-certificaat

## <a name="dns-settings"></a>DNS-instellingen

- **Zoeklijst voor DNS-achtervoegsels**: Voer bij **DNS-achtervoegsels** een DNS-achtervoegsel in en selecteer **Toevoegen**. U kunt meerdere achtervoegsels toevoegen.

  Wanneer u DNS-achtervoegsels gebruikt, kunt u naar een netwerkbron zoeken met behulp van de korte naam, in plaats van met de Fully Qualified Domain Name (FQDN). Bij het zoeken met behulp van de korte naam wordt het achtervoegsel automatisch door de DNS-server bepaald. `utah.contoso.com` staat bijvoorbeeld in de lijst met DNS-achtervoegsels. U pingt `DEV-comp`. In dit scenario wordt deze omgezet in `DEV-comp.utah.contoso.com`.

  DNS-achtervoegsels worden omgezet in de weergegeven volgorde. De volgorde kan worden gewijzigd. `colorado.contoso.com` en `utah.contoso.com` staan bijvoorbeeld in de lijst met DNS-achtervoegsels en hebben beide een resource met de naam `DEV-comp`. Aangezien `colorado.contoso.com` eerst op de lijst komt, wordt deze omgezet in `DEV-comp.colorado.contoso.com`.
  
  Als u de volgorde wilt wijzigen, klikt u op de puntjes links van het DNS-achtervoegsel en sleept u het achtervoegsel naar boven:

  ![Selecteer de drie puntjes en klik en sleep om het DNS-achtervoegsel te verplaatsen](./media/vpn-settings-windows-10/vpn-settings-windows10-move-dns-suffix.png)

- **NRPT-regels (tabel voor naamomzettingsbeleid)** : hiermee kunt u definiëren hoe via DNS namen worden omgezet wanneer verbinding met het VPN is gemaakt. Nadat de VPN-verbinding tot stand is gebracht, kunt u kiezen van welke DNS-servers de VPN-verbinding gebruikmaakt.

  U kunt regels aan de tabel toevoegen die de DNS-server, proxy en andere gegevens bevatten om het domein om te zetten dat u opgeeft. De VPN-verbinding gebruikt deze regels wanneer gebruikers verbinding maken met de domeinen die u hebt opgegeven.

  Selecteer **Toevoegen** om een nieuwe regel toe te voegen. Voer voor elke server het volgende in:

  - **Domein**: Voer de Fully Qualified Domain Name (FQDN) of een DNS-achtervoegsel in om de regel toe te passen. U kunt ook een punt (.) aan het begin invoeren voor een DNS-achtervoegsel. Voer bijvoorbeeld `contoso.com` of `.allcontososubdomains.com` in.
  - **DNS-servers**: Voer het IP-adres of de DNS-server in waarmee het domein wordt omgezet. Voer bijvoorbeeld `10.0.0.3` of `vpn.contoso.com` in.
  - **Proxy**: Voer de webproxyserver in waarmee het domein wordt omgezet. Voer bijvoorbeeld `http://proxy.com` in.
  - **Automatisch verbinding maken**: Als deze optie is **ingeschakeld**, maakt het apparaat automatisch verbinding met VPN wanneer een apparaat een domein oproept dat u invoert, bijvoorbeeld `contoso.com`. Wanneer deze optie **niet is geconfigureerd** (standaard), maakt het apparaat niet automatisch verbinding met het VPN
  - **Permanent**: Als **Ingeschakeld** is ingesteld, blijft de regel in de tabel voor naamomzettingsbeleid (NRPT) totdat de regel handmatig van het apparaat wordt verwijderd, zelfs nadat de verbinding met de VPN is verbroken. Als **Niet geconfigureerd** (standaard) is ingesteld, worden de NRPT-regels in het VPN-profiel verwijderd van het apparaat zodra de VPN-verbinding wordt verbroken.

## <a name="proxy-settings"></a>Proxyinstellingen

- **Script voor automatische configuratie**: Gebruik een bestand om de proxyserver te configureren. Voer de **URL van proxyserver** in, zoals `http://proxy.contoso.com`, die het configuratiebestand bevat.
- **Adres**: Voer het adres van de proxyserver in, zoals een IP-adres of `vpn.contoso.com`
- **Poortnummer**: Voer het TCP-poortnummer in dat wordt gebruikt voor uw proxyserver
- **Proxy niet gebruiken voor lokale adressen**: Als u geen proxyserver wilt gebruiken voor lokale adressen, kiest u Inschakelen. Deze instelling is van toepassing als voor de VPN-server een proxyserver is vereist voor de verbinding.

## <a name="split-tunneling"></a>Split tunneling

- **Split tunneling**: U kunt deze optie **inschakelen**  of **uitschakelen** om apparaten te laten bepalen welke verbinding moet worden gebruikt, afhankelijk van het verkeer. Een gebruiker in een hotel gebruikt bijvoorbeeld de VPN-verbinding voor werkbestanden, maar gebruikt het standaardnetwerk van het hotel om gewoon op het web te surfen.
- **Split tunneling-routes voor deze VPN-verbinding**: U kunt desgewenst routes toevoegen voor externe VPN-providers. Voer voor elke verbinding een bestemmingsvoorvoegsel en voorvoegselgrootte in.

## <a name="trusted-network-detection"></a>Vertrouwd netwerk detecteren

**DNS-achtervoegsels voor vertrouwde netwerken**: Wanneer gebruiker al verbonden zijn met een vertrouwd netwerk, kunt u voorkomen dat apparaten automatisch verbinding maken met andere VPN-verbindingen.

Geef bij **DNS-achtervoegsels** het DNS-achtervoegsel op dat u wilt vertrouwen, zoals contoso.com, en selecteer **Toevoegen**. U kunt zoveel achtervoegsels toevoegen als u wilt.

Als een gebruiker is verbonden met een DNS-achtervoegsel in de lijst, kan de gebruiker niet automatisch verbinding maken met een andere VPN-verbinding. De gebruiker blijft de vertrouwde lijst met DNS-achtervoegsels gebruiken die u opgeeft. Het vertrouwde netwerk wordt nog steeds gebruikt, zelfs als er autotriggers zijn ingesteld.

Als de gebruiker bijvoorbeeld al verbinding heeft met een vertrouwd DNS-achtervoegsel, worden de volgende autotriggers genegeerd. De DNS-achtervoegsels in de lijst zorgen ervoor dat alle andere autotriggers voor verbindingen worden geannuleerd, met inbegrip van:

- AlwaysOn
- Trigger op basis van een app
- DNS-autotrigger

## <a name="next-steps"></a>Volgende stappen

Het profiel is gemaakt, maar er gebeurt nog niets. Vervolgens moet u [het profiel toewijzen](device-profile-assign.md) en [de status ervan controleren](device-profile-monitor.md).

Configureer VPN-instellingen voor apparaten met [Android](vpn-settings-android.md), [iOS](vpn-settings-ios.md) en [macOS](vpn-settings-macos.md).
