---
title: In ontwikkeling - Microsoft Intune
titleSuffix: ''
description: Microsoft Intune-functies in ontwikkeling
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 06/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: cacampbell
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: f7dd6f62cb53dd0cc373fb3f2ffa7d9434b135cd
ms.sourcegitcommit: 116ef72b9da4d114782d4b8dd9f57556c9b01511
ms.translationtype: MTE75
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2019
ms.locfileid: "67494243"
---
# <a name="in-development-for-microsoft-intune---july-2019"></a>In ontwikkeling voor Microsoft Intune - juli 2019

Als ondersteuning bij uw gereedheid en planning worden op deze pagina updates voor en functies van de Intune-gebruikersinterface vermeld die in ontwikkeling zijn, maar nog niet zijn uitgebracht. Daarnaast:

- Als we verwachten dat u actie moet ondernemen voorafgaand aan een wijziging, publiceren we een aanvullend bericht in het Office-berichtencentrum.
- Als er een functie wordt uitgebracht in productie, ofwel als preview ofwel als algemeen beschikbare functie, wordt de functiebeschrijving verplaatst van deze pagina naar de [pagina Nieuwe functies](whats-new.md).
- Deze pagina en de pagina [Nieuwe functies](whats-new.md) worden regelmatig bijgewerkt. Controleer op andere updates.
- Raadpleeg de [M365-roadmap](https://www.microsoft.com/microsoft-365/roadmap?rtc=2&filters=EMS) voor strategische producten en tijdlijnen.

> [!Note]
> Deze items representeren de huidige verwachtingen van Microsoft over Intune-mogelijkheden in een toekomstige release. Datums en afzonderlijke functies kunnen worden gewijzigd. Niet alle items in ontwikkeling hebben een functieomschrijving op deze pagina.

**RSS feed**: ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en plakken: `https://docs.microsoft.com/api/search/rss?search=%22in+development+-+microsoft+intune%22&locale=en-us`

<!--
## What's coming to Intune in the Azure portal 
## What's coming to Intune apps
## Notices
-->

<!-- Common categories:  
#### App management
#### Device configuration
#### Device enrollment
#### Device management
#### Intune apps
#### Monitor and troubleshoot
#### Role-based access control
#### Security

-->
 
<!-- ***********************************************-->
## <a name="app-management"></a>Appbeheer


### <a name="customized-notifications-for-users-and-groups-------16766574-----"></a>Aangepaste meldingen voor gebruikers en groepen    <!-- 16766574   -->
Binnenkort kunnen aangepaste ad-hoc-pushmeldingen verzenden vanuit de bedrijfsportal-App voor gebruikers van iOS en Android-apparaten die u met Intune beheert. Deze aangepaste meldingen zijn niet gekoppeld aan specifieke Intune-functies en kan worden gebruikt voor enig doel dat u nodig hebt, met inbegrip van algemene meldingen die u wilt verzenden naar enkele of alle uw werknemers.  

### <a name="configure-app-notification-content-for-organization-accounts----2576686---"></a>De inhoud van de app-melding voor organisatie-accounts configureren <!-- 2576686 -->
Intune app-beveiligingsbeleid (APP) op Android en iOS-apparaten kunt u beheer app-melding inhoud voor organisatie-accounts. Deze functie moet ondersteuning van toepassingen en mogelijk niet beschikbaar voor alle toepassingen van de APP in te schakelen. Zie [Wat is beveiligingsbeleid voor apps?](app-protection-policy.md) voor meer informatie over APP.

### <a name="available-google-play-app-reporting-for-android-work-profiles----3041956----"></a>Beschikbare rapportage over Google Play-apps voor Android-werkprofielen <!-- 3041956  -->
U kunt voor beschikbare app-installaties op apparaten met Android-werkprofielen de status van de app-installatie evenals de geïnstalleerde versie van beheerde Google Play-apps bekijken. Zie [How to monitor app protection policies](app-protection-policies-monitor.md) (App-beveiligingsbeleid controleren), [Manage Android work profile devices with Intune](android-enterprise-overview.md) (Apparaten met Android-werkprofielen beheren met Intune) en [Managed Google Play app type](apps-add-android-for-work.md#managed-google-play-app-type) (Type beheerde Google Play-app) voor meer informatie.

<!-- ***********************************************-->
## <a name="device-configuration"></a>Apparaatconfiguratie


### <a name="support-for-ikev2-vpn-profiles-for-ios----1943438---"></a>Ondersteuning voor IKEv2 VPN-profielen voor iOS <!-- 1943438 -->
U kunt met het IKEv2-protocol VPN-profielen voor de systeemeigen VPN-client van iOS maken. IKEv2 is een nieuw verbindingstype in **Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **iOS** voor platform > **VPN** voor profieltype > **Instellingen**.

Met deze VPN-profielen wordt de systeemeigen VPN-client geconfigureerd. Er worden dus geen VPN-client-apps geïnstalleerd of naar beheerde apparaten gepusht. Deze functie vereist dat apparaten zijn ingeschreven bij Intune (MDM-inschrijving).

Als u wilt zien welke VPN-instellingen u momenteel kunt configureren, gaat u naar [Configure VPN settings on iOS devices in Microsoft Intune](vpn-settings-ios.md) (VPN-instellingen configureren op iOS-apparaten in Microsoft Intune).

Van toepassing op: iOS

### <a name="use-applicability-rules-when-creating-windows-10-device-configuration-profiles----2549910---"></a>Toepasselijkheidsregels gebruiken bij het maken van Windows 10-apparaatconfiguratieprofielen <!-- 2549910 -->
U kunt Windows 10-apparaatconfiguratieprofielen maken (**Apparaatconfiguratie** > **Profielen** > **Profiel maken** > **Windows 10** als platform). U kunt een **toepassingsregel** maken zodat het profiel alleen van toepassing is op een specifieke editie of versie. U maakt bijvoorbeeld een profiel waarmee bepaalde BitLocker-instellingen worden ingeschakeld. Als u het profiel toevoegt, gebruikt u een toepassingsregel zodat het profiel alleen van toepassing is op apparaten met Windows 10 Enterprise.

Van toepassing op: 
- Windows 10 en hoger

### <a name="administrative-templates-for-group-policy---------3510695---"></a>Beheersjablonen voor groepsbeleid     <!--  3510695 -->
Ter verbetering van de beveiliging van apparaten in de cloud worden er beheersjablonen uitgebracht waarmee u Intune kunt gebruiken om bepaalde instellingen voor groepsbeleid te configureren voor Windows-pc's.  Bij deze sjablonen wordt Policy Configuration Service Provider (CSP) gebruikt om maximaal 2500 extra instellingen van Office, Windows en OneDrive te bieden.

### <a name="manage-filevault-for-macos-------3858502--1210104-----"></a>Beheren van FileVault voor macOS   <!--  3858502 + 1210104   -->
U zult kunnen een apparaatconfiguratieprofiel van Intune endpoint protection gebruiken voor het beheren van FileVault key-versleuteling voor macOS-apparaten. Dit omvat escrow van weergave van en het draaien van de versleutelingssleutels van uw zakelijke apparaten. Eindgebruikers kunnen zich om op te halen die sleutels via de bedrijfsportal-website.

### <a name="advanced-settings-for-windows-defender-firewall-------1311949-------"></a>Geavanceerde instellingen voor Windows Defender Firewall   <!--  1311949     -->
Als openbare preview kunt u binnenkort Intune gebruiken om de aangepaste firewallregels op clients voor Windows Defender te beheren.  

### <a name="new-configuration-designer-when-creating-an-oemconfig-profile-for-android-enterprise----3712769----"></a>Nieuwe configuratieontwerper bij het maken van een profiel OEMConfig voor Android Enterprise <!-- 3712769  -->
In Intune, kunt u een apparaatconfiguratieprofiel die gebruikmaakt van een app OEMConfig (apparaatconfiguratie > profielen > profiel maken > Android enterprise voor platform > OEMConfig voor profieltype). Als u dit doet, wordt een JSON-editor wordt geopend met een sjabloon en de waarden voor u om te wijzigen. Deze update bevat de ontwerper van een configuratie met een verbeterde gebruikerservaring en worden ingesloten in de app, met inbegrip van titels, beschrijvingen en meer details weergegeven. De JSON-editor is nog steeds beschikbaar en bevat wijzigingen die u in de Configuration Designer.

Als u wilt zien van de huidige instellingen, gaat u naar [gebruiken en beheren van Android-bedrijfsapparaten met OEMConfig](android-oem-configuration-overview.md).

Van toepassing op: Android Enterprise


<!-- ***********************************************-->
## <a name="device-management"></a>Apparaatbeheer

### <a name="improve-device-location---3855417---"></a>De locatie van het apparaat te verbeteren<!-- 3855417 -->
Zal het mogelijk om in te zoomen naar de exacte coördinaten van het gebruik van een apparaat de **apparaat zoeken** actie. Zie voor meer informatie over het vinden van verloren iOS-apparaten, [verloren iOS-apparaten zoeken](device-locate.md).

### <a name="configure-automatic-device-clean-up-time-limit-down-to-30-days---4231059----"></a>Configureren van automatische inrichting opschonen tijdslimiet tot 30 dagen <!--4231059  -->
U moet mogelijk zijn om in te stellen van automatische inrichting opschonen termijn zo kort 30 dagen (in plaats van de huidige limiet van 90 dagen) na de laatste aanmelding. Om dit te doen, gaat u naar **Intune** > **apparaten** > **Setup** > **Clean Up Apparaatregels**.


<!-- ***********************************************-->
## <a name="security"></a>Beveiliging

### <a name="import-and-export-security-baselines------3408610------------"></a>Beveiligingsbasislijnen importeren en exporteren    <!--3408610          -->  
We voegen de mogelijkheid om te exporteren en importeren van basisbeveiliging zodat u kunt uw aanpassingen met u nemen en deze tussen Intune omgevingen delen toe.



<!-- ***********************************************-->
## <a name="notices"></a>Mededelingen

[!INCLUDE [Intune notices](./includes/intune-notices.md)]

## <a name="see-also"></a>Zie tevens
Zie [Wat is er nieuw in Microsoft Intune?](whats-new.md) voor meer informatie over recente ontwikkelingen.


