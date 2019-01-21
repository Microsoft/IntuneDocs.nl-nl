---
title: VPN-instellingen per app instellen voor iOS-apparaten in Microsoft Intune - Azure | Microsoft Docs
description: Bekijk de voorwaarden, maak een groep aan voor VPN-gebruikers (Virtual Private Network), voeg een SCEP-certificaatprofiel toe, configureer VPN-profiel per app en wijs enkele apps toe aan het VPN-profiel in Microsoft Intune op iOS-apparaten. Vermeld ook de stappen om de VPN-verbinding op het apparaat te verifiëren.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 12131fe0b78814850cfadee15533620dd5813f6c
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297397"
---
# <a name="set-up-per-app-virtual-private-network-vpn-in-intune-for-ios-devices"></a>VPN per app instellen in Intune voor iOS-apparaten

U kunt specificeren welke beheerde apps uw virtueel particulier netwerk (VPN) mogen gebruiken op iOS-apparaten die met Intune worden beheerd. Wanneer u in Intune een VPN per app maakt, maakt een eindgebruiker bij het openen van zakelijke documenten automatisch verbinding via uw VPN.

VPN per app is momenteel beschikbaar voor de volgende providers:

 - Checkpoint Remote Access VPN
 - Cisco AnyConnect
 - Citrix
 - F5
 - Pulse Connect Secure
 - Palo Alto Networks
 - SonicWall
 - Zscaler Private Access

## <a name="prerequisites-for-per-app-vpn"></a>Vereisten voor VPN per app

> [!IMPORTANT]
> Uw VPN-leverancier heeft wellicht andere specifieke vereisten voor Per-App VPN, zoals bepaalde hardware of -licentieverlening. Raadpleeg de documentatie en zorg ervoor dat u voldoet aan deze vereisten voordat u Per-App VPN in Intune instelt.

Ter bevestiging van de identiteit van de VPN-server legt deze het certificaat voor. Dit moet door het apparaat zonder prompt worden geaccepteerd. Om ervoor te zorgen dat het certificaat automatisch wordt goedgekeurd, moet u een vertrouwd certificaatprofiel maken dat het door de certificeringsinstantie (CA) uitgegeven basiscertificaat van de VPN-server bevat. 

Exporteer het certificaat en voeg de CA toe.

1. Open de beheerconsole op de VPN-server.
2. Controleer of door de VPN-server verificatie op basis van certificaten wordt gebruikt. 
3. Exporteer het bestand met het vertrouwde basiscertificaat. Dit bestand heeft de extensie .CER. U voegt dit toe wanneer u een vertrouwd certificaatprofiel maakt.
4. Voeg de naam toe van de CA die het certificaat heeft uitgegeven voor verificatie bij de VPN-server.
    Als de CA die door het apparaat wordt voorgelegd, overeenkomt met een van de CA's in de lijst met vertrouwde CA's op de VPN-server, wordt het apparaat door de VPN-server geverifieerd.

## <a name="create-a-group-for-your-vpn-users"></a>Een groep maken voor uw VPN-gebruikers

Maak of kies in Azure Active Directory (Azure AD) een bestaande groep die de leden gaat bevatten die toegang hebben tot het VPN per app.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Kies **Groepen** en klik op **Nieuwe groep**.
3. Selecteer een **groepstype** voor de groep. 
3. Typ de **groepsnaam** van de groep. 
4. Typ de **groepsbeschrijving** van de groep. 
5. Selecteer **Toegewezen** bij **Type lidmaatschap**.
7. Zoek de VPN-gebruikers op basis van naam of e-mailadres op in het deelvenster **Leden**.
8. Selecteer elke gebruiker en klik op **Selecteren**.
9. Klik op **Maken**

## <a name="create-a-trusted-certificate-profile"></a>Een vertrouwd certificaatprofiel maken

Importeer het door de CA uitgegeven basiscertificaat van de VPN-server in een profiel dat in Intune is gemaakt. Op basis van het vertrouwde certificaatprofiel vertrouwt het iOS-apparaat automatisch de CA die door de VPN-server wordt voorgelegd.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Kies **Apparaatconfiguratie** en klik vervolgens op **Profielen**.
3. Klik op **Profiel maken**. Doe het volgende in **Profiel maken**:
    1. Typ de **naam**.
    2. Typ de **beschrijving**.
    3. Selecteer **iOS** bij **Platform**.
    4. Selecteer **Vertrouwd certificaat** bij **Profieltype**.
4. Klik op het mappictogram en blader naar het VPN-certificaat (CER-bestand) dat u vanuit de VPN-beheerconsole hebt geëxporteerd. Klik op **OK**.
5. Klik op **Maken**.

    ![Een vertrouwd certificaatprofiel maken](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Een SCEP-certificaatprofiel maken

Op basis van het vertrouwde certificaatprofiel vertrouwt iOS automatisch de VPN-server. De SCEP-certificaat geeft referenties van de iOS-VPN-client door aan de VPN-server. Door het certificaat kan het apparaat op de achtergrond verifiëren zonder dat de gebruiker van het iOS-apparaat om een gebruikersnaam en wachtwoord wordt gevraagd. 

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Kies **Apparaatconfiguratie** en klik vervolgens op **Profielen**.
3. Klik op **Profiel maken**. Doe het volgende in **Profiel maken**:
    1. Typ de **naam**.
    2. Typ de **beschrijving**.
    3. Selecteer **iOS** bij **Platform**.
    4. Selecteer **SCEP-certificaat** bij **Profieltype**.
4. Selecteer **Jaren** en typ `2` bij **Geldigheidsduur van certificaat**.
5. Selecteer **Algemene naam** bij **Indeling van de onderwerpnaam**.
6. Selecteer **User principal name (UPN)** bij **Alternatieve onderwerpnaam**.
7. Selecteer **Digitale handtekening** en **sleutelcodering** bij **Sleutelgebruik**.
8. Selecteer **2048** bij **Sleutelgrootte (bits)**.
9. Klik op Basiscertificaat en selecteer een SCEP-certificaat. Klik op **OK**.
10. Typ `Client Authentication` in **Naam** bij **Uitgebreide-sleutelgebruik**.
11. Typ `1.3.6.1.5.5.7.3.2` bij **Object-id**.
12. Klik op **Toevoegen**.
13. Typ de ***Server-URL*** en klik op **Toevoegen**.
14. Klik op **OK**.
15. Klik op **Maken**.

    ![Een SCEP-certificaatprofiel maken](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Een profiel voor VPN per app maken

Het VPN-profiel bevat het SCEP-certificaat met de referenties van de client, de verbindingsgegevens voor de VPN-verbinding en de markering voor VPN per app voor het inschakelen van de functie VPN per app voor gebruik door de iOS-toepassing.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
2. Kies **Apparaatconfiguratie** en klik vervolgens op **Profielen**.
3. Klik op **Profiel maken**. Doe het volgende in **Profiel maken**:
    1. Typ de **naam**.
    2. Typ de **beschrijving**.
    3. Selecteer **iOS** bij **Platform**.
    4. Selecteer **VPN** bij **Profieltype**.
4. Selecteer **Basis-VPN**. Doe het volgende in **Basis-VPN**:
    1. Typ de **verbindingsnaam**.
    2. Typ het **IP-adres of de FQDN**.
    3. Selecteer **Certificaten** bij **Verificatiemethode**.
    4. Selecteer het SCEP-certificaat onder **Verificatiecertificaat** en klik op **OK**.
    5. Selecteer uw VPN bij **Verbindingstype**.
    6. Configureer zo nodig de kenmerken van uw VPN.
    7. Selecteer **Split tunneling uitschakelen**.
5. Klik op **Automatische VPN**. Doe het volgende in **Automatische VPN**:
    1. Selecteer **VPN per app** bij **Type automatische VPN**.
    2. Typ de URL van het VPN en klik op **Toevoegen**.
    3. Klik op **OK**.
6. Klik op **OK**.
7. Klik op **Maken**.

    ![Een profiel voor VPN per app maken](./media/vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Een app aan het VPN-profiel koppelen

Na het toevoegen van uw VPN-profiel moet u de app en de Azure AD-groep (Microsoft Azure Active Directory) aan het profiel koppelen.

1. Meld u aan bij de [Azure-portal](https://portal.azure.com).
2. Selecteer **Alle services**, filter op **Intune** en selecteer **Microsoft Intune**.
3. Kies **Client-apps**.
4. Klik op **Apps**.
5. Selecteer de app in de lijst met apps.
6. Klik op **Toewijzingen**.
7. Klik op **Groep toevoegen**.
8. Selecteer **Vereist** bij **Toewijzingstype** in het deelvenster **Groep toevoegen**.
9. Selecteer de groep die u eerder hebt gedefinieerd en selecteer **Deze app vereist maken**.
10. Selecteer uw VPN-definitie voor de **VPN**.
 
    > [!NOTE]  
    > Soms duurt het een minuutje voordat de VPN-definitie de waarde heeft opgehaald. Wacht 3 tot 5 minuten voordat u op **Opslaan** klikt.

11. Klik op **OK** en op **Opslaan**.

    ![Een app aan het VPN koppelen](./media/vpn-per-app-app-to-vpn.png)

Een koppeling tussen een app en een profiel wordt verwijderd wanneer het apparaat de volgende keer wordt ingecheckt als aan de volgende voorwaarden wordt voldaan:
- De app is het doel van vereiste installatie.
- Zowel het profiel als de app zijn gericht op dezelfde groep.
- U kunt de configuratie van VPN per app verwijderen uit de app-toewijzing.

Een koppeling tussen een app en een profiel blijft bestaan totdat de eindgebruiker opnieuw installeren vanuit de bedrijfsportal aanvraagt als aan de volgende voorwaarden is voldaan:
- De app is het doel van de intentie beschikbare installatie.
- Zowel het profiel als de app zijn gericht op dezelfde groep.
- De eindgebruiker heeft installatie van de app aangevraagd vanuit de bedrijfsportal. Hierdoor worden de app en het profiel op het apparaat geïnstalleerd.
- U kunt de configuratie van VPN per app verwijderen of wijzigen uit de app-toewijzing.

## <a name="verify-the-connection-on-the-ios-device"></a>De verbinding controleren op het iOS-apparaat

Wanneer uw VPN per app is geconfigureerd en aan uw app is gekoppeld, controleert u vanaf een apparaat of de verbinding werkt.

### <a name="before-you-attempt-to-connect"></a>Voordat u verbinding probeert te maken

 - Zorg dat u iOS 9 of hoger uitvoert.
 - Zorg ervoor dat u *alle* hierboven genoemde beleidsregels implementeert naar dezelfde groep gebruikers. Als u dit niet doet, zal de VPN per app-ervaring absoluut mislukken.  
 - Zorg ervoor dat u de ondersteunde VPN-app van derden hebt geïnstalleerd. De volgende VPN-apps worden ondersteund:
    - Check Point Capsule Connect
    - Cisco AnyConnect
    - Citrix VPN
    - Citrix SSO
    - F5-toegang
    - Palo Alto Networks GlobalProtect
    - Pulse Secure
    - SonicWall Mobile Connect
    - Zscaler

    > [!NOTE]
    > Als u de Pulse Secure VPN-app gebruikt, kunt u ervoor kiezen om tunneling op app-niveau of pakketniveau te gebruiken. Stel de waarde **ProviderType** in op **app-proxy** voor tunneling op app-niveau of **pakkettunnel** voor tunneling op pakketniveau.

### <a name="connect-using-the-per-app-vpn"></a>Verbinding maken via VPN per app

Controleer de zero-touch-ervaring door verbinding te maken zonder dat u de VPN-verbinding hoeft te selecteren of uw referenties hoeft te typen. De zero-touch-ervaring betekent:

 - Het apparaat vraagt u niet of u de VPN-server wilt vertrouwen. U ziet wel het dialoogvenster **Dynamisch vertrouwen**.
 - U hoeft geen referenties te typen.
 - U wordt met het VPN verbonden nadat u op de verbindingsknop hebt getikt.

Controleer de verbinding op een iOS-apparaat.

1. Tik op de VPN-app.
2. Tik op **Verbinding maken**.  
U wordt zonder extra prompts met het VPN verbonden.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Volgende stappen

- Raadpleeg [VPN-instellingen voor iOS-apparaten in Microsoft Intune](vpn-settings-ios.md) om iOS-instellingen te controleren.
-  Zie [VPN-instellingen configureren in Microsoft Intune](vpn-settings-configure.md) voor meer informatie over VPN-instellingen en Intune.
